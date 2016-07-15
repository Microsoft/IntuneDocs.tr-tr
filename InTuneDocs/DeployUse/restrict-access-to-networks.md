---
title: "Cisco ISE ile ağlara erişimi kısıtlama| Microsoft Intune"
description: "Cihazların, Cisco ISE ile denetlenen Wi-Fi ve VPN’e erişmeden önce Intune kayıtlı ve ilke uyumlu olması adına, Intune ile Cisco ISE kullanabilirsiniz."
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: 78945498a951e7b897164ae6f33c4e87d521ca5b


---

# Microsoft Intune ile Cisco ISE kullanma
Intune’un Cisco ISE ile entegrasyonu, Intune cihaz kaydı ve uyum durumunu kullanarak ISE ortamınızda ağ ilkeleri yazmanızı sağlar. Bu ilkeler, şirket ağınıza erişimin, Intune tarafından yönetilen ve Intune ilkeleriyle uyumlu cihazlarla kısıtlanmasını sağlamaya yarayabilir. 

## Yapılandırma

Bu tümleştirmeyi etkinleştirmek için, Intune kiracınızda herhangi bir ayar yapmanız gerekmez. Intune kiracınıza erişmek için, Cisco ISE sunucunuza izinler sağlamanız gerekir ve bu yapıldığında, kurulumun kalan kısmı Cisco ISE sunucunuzda gerçekleşir. Bu makalede, ISE sunucunuza, Intune kiracınıza erişim izinleri sağlamayla ilgili yönergeler sağlanır. 

### 1. Adım: Sertifikaları yönetme
1. Azure Active Directory (AAD) konsolunda, sertifikayı dışa aktarın. 

    #### Internet Explorer 11
        
    a. Internet Explorer'ı yönetici olarak çalıştırın ve AAD konsoluna oturum açın.
  
    b. Adres çubuğunda kilit simgesini seçin ve seçin **Sertifikaları görüntüle**’yi seçin
    
    c. Sertifika özelliklerinin **Ayrıntılar** sekmesinde, **Dosyaya kopyala**’yı seçin.

    d. **Sertifika dışa aktarma sihirbazı** karşılama sayfasında, **İleri**’yi seçin. 

    e. **Dışa aktarma dosya biçimi** sayfasında, varsayılan **DER ile kodlanmış ikili x.509 (.CER)** ayarını bırakın ve **İleri**’yi seçin.  

    f. **Dışa aktarılacak dosya** sayfasında, dosyanın kaydedileceği bir konum seçmek üzere **Gözat**’ı seçin ve bir dosya adı sağlayın. Dışa aktarılacak bir dosya seçiyor gibi gözükseniz de, aslında dışa aktarılan sertifikanın kaydedileceği dosyayı yeniden adlandırıyorsunuz. **İleri** &gt; **Son**’u seçin.

    #### Safari
    
    a. AAD konsoluna oturum açın.

    b. Kilit simgesini &gt;  **Daha fazla bilgi**’yi seçin.
    
    c. **Sertifika görüntüle** &gt; **Ayrıntılar**’ı seçin.

    d. Sertifikayı seçin ve ardından **Dışa aktar**’ı seçin.  


> [!IMPORTANT]
> Sertifikanın son kullanma tarihini denetleyin, bunun süresi dolduğunda yeni bir sertifika dışa aktarmanız ve içe aktarmanız gerekecektir.

    

2. ISE konsolunda, Intune sertifikasını (dışa aktardığınız dosya) **Güvenilen Sertifikalar** deposuna aktarın.
3. ISE konsolunuzda, **Yönetim** > **Sertifikalar** > **Sistem Sertifikaları**’na gidin.
4. ISE sertifikasını seçin ve ardından **Dışa aktar**’ı seçin.
5. Bir metin düzenleyicide, dışa aktarılan sertifikayı düzenleyin:
 - ** -----BEGIN CERTIFICATE-----** metnini silin
 - ** -----END CERTIFICATE-----** metnini silin
 - Tüm metnin tek bir satırda olduğundan emin olun

### 2. Adım: AAD kiracınızda ISE için uygulama oluşturma
1. Azure Active Directory (AAD) konsolunda, **Uygulamalar** > **Uygulama Ekleme** > **Kuruluşumun geliştirmekte olduğu bir uygulama ekle**’yi seçin.
2. Uygulama için bir ad ve URL belirtin. URL, şirketinizin web sitesi olabilir.
3. Uygulama bildirimini (bir JSON dosyası) indirin.
4. Bildirim JSON dosyasını düzenleyin. **keyCredentials** adlı ayarda, 1. Adımdan düzenlenen sertifika metnini, ayar değeri olarak sağlayın.
5. Dosyayı, adını değiştirmeden kaydedin.
6. Uygulamanıza, Microsoft Graph ve Microsoft Intune API için izinler sağlayın.
    1. Microsoft Graph için, aşağıdakileri seçin
        - **Uygulama izinleri**: Dizin verilerini oku
        - **Temsilci izinleri**: 
            - Kullanıcının verilerine istendiği zaman eriş
          - Kullanıcıların oturumunu açma
   2. Microsoft Intune API'si için, **Uygulama izinlerinde**, **Intune'dan cihaz durumunu ve uyumluluğunu al**’ı seçin.

7. **Uç Noktalarını Görüntüle**’yi seçin ve ISE ayarlarını yapılandırmada kullanmak için aşağıdaki değerleri kopyalayın:

|AAD portalında değer|ISE portalında karşılık gelen alan|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph API uç noktası|Otomatik Bulma URL’si|
|Oauth 2.0 Belirteç uç noktası|Belirteci Veren URL|
|Kodunuzu, İstemci kimliğinizle güncelleştirme|İstemci Kimliği|


### 3. Adım: ISE Ayarlarını Yapılandırma 
2. ISE yönetim konsolunda, aşağıdaki ayar değerlerini sağlayın: 
  - **Sunucu Türü**: Mobil cihaz Yöneticisi
  - **Kimlik doğrulama türü**: OAuth – İstemci Kimlik Bilgileri
  - **Otomatik Bulma**: Evet
  - **Otomatik Bulma URL’si**: 1. Adımdan değer girin
  - **İstemci Kimliği**: 1. Adımdan değer girin
  - **Belirteç veren URL**: 1. Adımdan değer girin



## Intune kiracınız ve Cisco ISE sunucunuz arasında paylaşılan bilgiler
Bu tabloda, Intune tarafından yönetilen cihazlar için, Intune kiracınız ve Cisco ISE sunucunuz arasında paylaşılan bilgiler listelenir.

|Özellik|  Açıklama|
|---------------|------------------------------------------------------------|
|complianceState|   True veya false, cihazın uyumlu veya uyumsuz olduğunu belirtir (dize).|
|isManaged| True veya false (istemcinin Intune ile yönetilip yönetilmediğini belirtir).|
|macAddress|Cihazın MAC Adresi.|
|serialNumber|Cihazın seri numarası. Yalnızca iOS Cihazları için geçerlidir.|
|imei|IMEI (15 ondalık basamak: 14 basamak, artı bir onay basamağı) veya IMEISV (16 basamak) cihaz kökeni, modeli ve seri numarasını hakkında bilgi içerir. IMEI/SV yapısını 3GPP TS 23.003 içinde belirtilir. Yalnızca SIM kartlı cihazlar için geçerlidir.)|
|udid|Benzersiz cihaz tanımlayıcısı, iOS cihazlara özgü 40 harf ve rakamdan oluşan dizi.|
|meid|Mobil donanım kimliği, CDMA mobil istasyonu ekipmanının fiziksel bir parçasını tanımlayan genel olarak benzersiz bir numara. Numara biçimi 3GPP2 rapor S. R0048 ile tanımlanır, ancak pratikte, onaltılık basamaklı bir IMEI olarak görülebilir. Bir MEID 56 bit uzunluktadır (14 onaltılık basamak). Üç alandan oluşur, 8 bitlik bölgesel kod (RR), 24 bit üretici kodu ve 24 bit üreticisi tarafından atanmış seri numarası.| 
|osVersion| Cihazın işletim sistemi sürümü.
|model|Cihaz modeli.
|üretici|Cihaz üreticisi.
|azureDeviceId| Azure Active Directory ile iş yerine birleştirildikten sonraki cihaz kimliği. Birleştirilmemiş cihazlar için boş bir guid olacaktır.|
|lastContactTimeUtc|Cihazın, Intune yönetim hizmetiyle son denetlendiği tarih ve saat. 


## Kullanıcı deneyimleri

Bir kullanıcı kayıtsız cihaz kullanarak kaynaklara erişmeye çalıştığında, aşağıda gösterildiği gibi bir kaydetme istemi alır:

![Kayıt istemi örneği](../media/cisco-ise-user-iphone.png)

Kullanıcı kaydolmayı seçtiğinde, Intune kayıt işlemine yönlendirilir. Intune için kullanıcı kayıt deneyimi aşağıdaki konularda açıklanmıştır:

- [Android cihazınızı Intune’a kaydetme](/intune/end-user/enroll-your-device-in-Intune-android)</br>
- [iOS cihazınızı Intune'a kaydetme](/intune/end-user/enroll-your-device-in-intune-ios)</br>
- [Mac OS X cihazınızı Intune’a kaydetme](/intune/end-user/enroll-your-device-in-intune-mac-os-x)</br>
- [Windows cihazınızı Intune'a kaydetme](/intune/end-user/enroll-your-device-in-intune-windows)</br> 

Kullanıcı deneyiminiz için, özelleştirilmiş rehberlik oluşturmak üzere kullanabileceğiniz, [indirilebilir kayıt yönergeleri grubu](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) da vardır.


### Ayrıca bkz.

[Cisco Kimlik Hizmetleri Altyapısı Yönetici Kılavuzu, Sürüm 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)




<!--HONumber=Jun16_HO4-->


