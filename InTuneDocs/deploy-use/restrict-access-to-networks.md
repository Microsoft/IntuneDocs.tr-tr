---
title: "Cisco ISE ile ağlara erişimi koruma| Microsoft Docs"
description: "Cihazların, Cisco ISE ile denetlenen Wi-Fi ve VPN’e erişmeden önce Intune kayıtlı ve ilke uyumlu olmasını sağlamak için, Intune ile Cisco ISE kullanabilirsiniz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f34d54710f0ec662eecec85f7fa041061132a0d
ms.openlocfilehash: 8ef24e4d413662012f091c1be318d1d274e16439


---

# <a name="using-cisco-ise-with-microsoft-intune"></a>Microsoft Intune ile Cisco ISE kullanma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune’un Cisco Identity Services Engine (ISE) ile tümleştirmesi, Intune cihaz kaydı ve uyum durumunu kullanarak ISE ortamınızda ağ ilkeleri yazmanızı sağlar. Bu ilkeleri kullanarak, şirket ağınıza erişimin, Intune tarafından yönetilen ve Intune ilkeleriyle uyumlu cihazlarla kısıtlandığından emin olabilirsiniz.

## <a name="configuration-steps"></a>Yapılandırma adımları

Bu tümleştirmeyi etkinleştirmek için, Intune kiracınızda herhangi bir ayar yapmanız gerekmez. Intune kiracınıza erişebilmesi için Cisco ISE sunucunuza izinler sağlamanız gerekir. Bu yapıldıktan sonra, kurulumun kalan bölümü Cisco ISE sunucunuzda gerçekleştirilir. Bu makalede, ISE sunucunuza, Intune kiracınıza erişim izinleri sağlamayla ilgili yönergeler sağlanır.

### <a name="step-1-manage-the-certificates"></a>1. Adım: Sertifikaları yönetme
Azure Active Directory (Azure AD) konsolundan sertifikayı dışarı aktardıktan sonra ISE konsolunun Güvenilen Sertifikalar deposuna aktarın:

#### <a name="internet-explorer-11"></a>Internet Explorer 11


   a. Internet Explorer'ı yönetici olarak çalıştırın ve Azure AD konsoluna oturum açın.

   b. Adres çubuğunda kilit simgesini seçin ve **Sertifikaları görüntüle**’yi seçin.

   c. Sertifika özelliklerinin **Ayrıntılar** sekmesinde, **Dosyaya kopyala**’yı seçin.

   d. **Sertifika dışarı aktarma sihirbazı** karşılama sayfasında, **İleri**’yi seçin.

   e. **Dışarı aktarma dosya biçimi** sayfasında, varsayılan **DER ile kodlanmış ikili x.509 (.CER)** ayarını bırakın ve **İleri**’yi seçin.  

   f. **Dışarı aktarılacak dosya** sayfasında, dosyanın kaydedileceği bir konum seçmek üzere **Gözat**’ı seçin ve bir dosya adı sağlayın. Dışarı aktarılacak bir dosya seçiyor gibi gözükseniz de, aslında dışarı aktarılan sertifikanın kaydedileceği dosyayı yeniden adlandırıyorsunuz. **İleri** &gt; **Son**’u seçin.

   g. ISE konsolunda, Intune sertifikasını (dışarı aktardığınız dosya) **Güvenilen Sertifikalar** deposuna aktarın.

#### <a name="safari"></a>Safari

 a. Azure AD konsolunda oturum açın.

b. Kilit simgesini &gt;  **Daha fazla bilgi**’yi seçin.

   c. **Sertifika görüntüle** &gt; **Ayrıntılar**’ı seçin.

   d. Sertifikayı seçin ve ardından **Dışa aktar**’ı seçin. 

   e. ISE konsolunda, Intune sertifikasını (dışarı aktardığınız dosya) **Güvenilen Sertifikalar** deposuna aktarın.

> [!IMPORTANT]
>
> Sertifikanın son kullanma tarihini denetleyin, bunun süresi dolduğunda yeni bir sertifika dışarı aktarmanız ve içeri aktarmanız gerekecektir.


### <a name="obtain-a-self-signed-cert-from-ise"></a>ISE’den otomatik olarak imzalanan sertifika alma 

1.  ISE konsolunda, **Yönetim** > **Sertifikalar** > **Sistem Sertifikaları** > **Otomatik Olarak İmzalanan Sertifika Oluştur**’a gidin.  
2.       Otomatik olarak imzalanan sertifikayı dışarı aktarın.
3. Bir metin düzenleyicide, dışa aktarılan sertifikayı düzenleyin:

 - ** -----BEGIN CERTIFICATE-----** metnini silin
 - ** -----END CERTIFICATE-----** metnini silin
 
Tüm metnin tek bir satırda olduğundan emin olun


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a>2. Adım: Azure AD kiracınızda ISE için uygulama oluşturma
1. Azure AD konsolunda, **Uygulamalar** > **Uygulama Ekleme** > **Kuruluşumun geliştirmekte olduğu bir uygulama ekle**’yi seçin.
2. Uygulama için bir ad ve URL belirtin. URL, şirketinizin web sitesi olabilir.
3. Uygulama bildirimini (bir JSON dosyası) indirin.
4. Bildirim JSON dosyasını düzenleyin. **keyCredentials** adlı ayarda, 1. Adımdan düzenlenen sertifika metnini, ayar değeri olarak sağlayın.
5. Dosyayı, adını değiştirmeden kaydedin.
6. Uygulamanıza, Microsoft Graph ve Microsoft Intune API için izinler sağlayın.

 a. Microsoft Graph için, aşağıdakileri seçin:
    - **Uygulama izinleri**: Dizin verilerini oku
    - **Temsilci izinleri**:
        - Kullanıcının verilerine istendiği zaman eriş
        - Kullanıcıların oturumunu açma

 b. Microsoft Intune API'si için, **Uygulama izinlerinde**, **Intune'dan cihaz durumunu ve uyumluluğunu al**’ı seçin.

7. **Uç Noktalarını Görüntüle**’yi seçin ve ISE ayarlarını yapılandırmada kullanmak için aşağıdaki değerleri kopyalayın:

|Azure AD portalındaki değer|ISE portalında karşılık gelen alan|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph API uç noktası|Otomatik Bulma URL’si|
|Oauth 2.0 Belirteç uç noktası|Belirteci Veren URL|
|Kodunuzu, İstemci kimliğinizle güncelleştirme|İstemci Kimliği|

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a>4. Adım: ISE’nin otomatik olarak imzalanan sertifikasını Azure AD'de oluşturduğunuz ISE uygulamasına yükleyin
1.     Bir .cer X509 ortak sertifika dosyasından base64 olarak kodlanmış sertifika değerini ve parmak izini alın. Bu örnek PowerShell'i kullanmaktadır:
   
      
      $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()
 
    Bir sonraki adımda kullanmak üzere $base64Thumbprint, $base64Value ve $keyid değerlerini kaydedin.
2.       Sertifikayı bildirim dosyası ile karşıya yükleyin. [Azure Yönetim Portalı](https://manage.windowsazure.com)'nda oturum açın
2.      Azure AD ek bileşenine girerek bir X.509 sertifikası ile yapılandırmak istediğiniz uygulamayı bulun.
3.      Uygulama bildirim dosyasını indirin. 
5.      Boş "KeyCredentials": [], özelliğini aşağıdaki JSON ile değiştirin.  KeyCredentials karmaşık türü [Varlık ve karmaşık tür başvurusu](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType)’nda belgelenir.

 
    “keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2. 
     ], 
 
Örneğin:
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      Değişiklikleri uygulama bildirim dosyasına kaydedin.
7.      Düzenlenen uygulama bildirim dosyasını Azure yönetim portalı aracılığıyla yükleyin.
8.      İsteğe bağlı: X.509 sertifikanızın uygulamada mevcut olduğunu denetlemek için bildirimi yeniden indirin.

>[!NOTE]
>
> KeyCredentials bir koleksiyon olduğundan geçiş senaryoları için birden fazla X.509 sertifikası yükleyebilir veya güvenliğin aşılması senaryolarında sertifikaları silebilirsiniz.


### <a name="step-4-configure-ise-settings"></a>4. Adım: ISE Ayarlarını Yapılandırma
ISE yönetim konsolunda, aşağıdaki ayar değerlerini sağlayın:
  - **Sunucu Türü**: Mobil cihaz Yöneticisi
  - **Kimlik doğrulama türü**: OAuth – İstemci Kimlik Bilgileri
  - **Otomatik Bulma**: Evet
  - **Otomatik Bulma URL’si**: *1. Adımdaki değeri girin.*
  - **İstemci Kimliği**: *1. Adımdaki değeri girin.*
  - **Belirteç veren URL**: *1. Adımdaki değeri girin.*



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a>Intune kiracınız ve Cisco ISE sunucunuz arasında paylaşılan bilgiler
Bu tabloda, Intune tarafından yönetilen cihazlar için, Intune kiracınız ve Cisco ISE sunucunuz arasında paylaşılan bilgiler listelenir.

|Özellik|  Açıklama|
|---------------|------------------------------------------------------------|
|complianceState|Cihazın uyumlu veya uyumsuz olduğunu belirten true veya false dizesi.|
|isManaged|İstemcinin Intune tarafından yönetildiğini veya yönetilmediğini belirten true veya false dizesi.|
|macAddress|Cihazın MAC adresi.|
|serialNumber|Cihazın seri numarası. Yalnızca iOS cihazları için geçerlidir.|
|imei|IMEI (15 ondalık basamak: 14 basamak, artı bir denetleme basamağı) veya IMEISV (16 basamak) numarası cihaz kökeni, modeli ve seri numarasını hakkında bilgi içerir. Bu numaranın yapısı 3GPP TS 23.003 içinde belirtilir. Yalnızca SIM kartlı cihazlar için geçerlidir.|
|udid|40 harf ve rakamlık bir dizi olan Benzersiz Cihaz Tanımlayıcısı. iOS cihazlarına özgüdür.|
|meid|CDMA mobil istasyonu ekipmanının fiziksel bir parçasını tanımlayan ve genel olarak benzersiz bir numara olan mobil donanım kimliği. Numaranın biçimi 3GPP2 rapor S. R0048 tarafından tanımlanır. Bununla birlikte, pratikte bunun onaltılı basamaklar içeren bir IMEI olduğu düşünülebilir. Bir MEID 56 bit uzunluktadır (14 onaltılık basamak). Üç alandan oluşur, 8 bitlik bölgesel kod (RR), 24 bit üretici kodu ve 24 bit üreticisi tarafından atanmış seri numarası.|
|osVersion|Cihazın işletim sistemi sürümü.
|model|Cihaz modeli.
|üretici|Cihaz üreticisi.
|azureDeviceId|Azure AD ile iş yerine katıldıktan sonraki cihaz kimliği. Katılmamış cihazlar için bu boş bir GUID olacaktır.|
|lastContactTimeUtc|Cihazın, Intune yönetim hizmetiyle son denetlendiği tarih ve saat.


## <a name="user-experience"></a>Kullanıcı deneyimleri

Kullanıcı kayıtsız cihaz kullanarak kaynaklara erişmeye çalıştığında, aşağıda gösterildiği gibi bir kaydetme istemi alır:

![Kayıt istemi örneği](../media/cisco-ise-user-iphone.png)

Kullanıcı kaydolmayı seçtiğinde, Intune kayıt işlemine yönlendirilir. Intune için kullanıcı kayıt deneyimi aşağıdaki konularda açıklanmıştır:

- [Android cihazınızı Intune’a kaydetme](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [iOS cihazınızı Intune'a kaydetme](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Mac OS X cihazınızı Intune’a kaydetme](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Windows cihazınızı Intune'a kaydetme](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Kullanıcı deneyiminiz için, özelleştirilmiş rehberlik oluşturmak üzere kullanabileceğiniz, [indirilebilir kayıt yönergeleri grubu](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) da vardır.


### <a name="see-also"></a>Ayrıca bkz.

[Cisco Kimlik Hizmetleri Altyapısı Yönetici Kılavuzu, Sürüm 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Jan17_HO1-->


