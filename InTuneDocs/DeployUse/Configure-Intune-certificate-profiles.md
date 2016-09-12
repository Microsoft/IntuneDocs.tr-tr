---
title: "Sertifika profillerini yapılandırma | Microsoft Intune"
description: "Intune sertifika profilinin nasıl oluşturulacağını öğrenin."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6a7f2eeb0114f525890d1dcb61344d60a19943d1
ms.openlocfilehash: 14419092edc77b2229cf980a74e81048941a2c28


---

# Intune sertifika profillerini yapılandırma
Altyapınız ve sertifikalarınız [Sertifika altyapısını SCEP için yapılandırma](configure-certificate-infrastructure-for-scep.md) veya [Sertifika altyapısını PFX için yapılandırma](configure-certificate-infrastructure-for-pfx.md) konu başlığı altında açıklandığı gibi yapılandırıldıktan sonra, sertifika profillerini yapılandırabilirsiniz:

**Görev 1** - Güvenilen Kök CA sertifikasını dışarı aktarma **Görev 2** - Güvenilen CA sertifika profilleri oluşturma **Görev 3** - Şunlardan biri:

SCEP sertifika profilleri oluşturma

.PFX sertifika profilleri oluşturma

### Görev 1 - Güvenilen Kök sertifikayı dışarı aktarma
Güvenilen Kök CA sertifikasını, sertifika veren CA'dan veya CA'nıza herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın. Özel anahtarı dışarı aktarmazsınız.

Güvenilen sertifika profili yapılandırırken bu sertifikayı içeri aktaracaksınız.

### Görev 2 - Güvenilen sertifika profilleri oluşturma
Bir SCEP veya .PFX sertifika profili oluşturabilmeniz için önce bir **Güvenilen sertifika profili** oluşturmanız gerekir. Her mobil cihaz platformu için bir Güvenilen sertifika profiline ve SCEP veya .PFS profiline ihtiyacınız vardır.

##### Güvenilen bir sertifika profili oluşturmak için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **İlke** &gt; **İlke Ekle** öğesine tıklayın.

2.  Aşağıdaki ilke türlerinden birini yapılandırın:

    **Android &gt; Güvenilen Sertifika Profili (Android 4 ve üzeri)**

    **iOS &gt; Güvenilen Sertifika Profili (iOS 7.1 ve üzeri)**

    **Mac OS X &gt; Güvenilen Sertifika Profili (Mac OS X 10.9 ve üzeri)**

    **Windows &gt; Güvenilen Sertifika Profili (Windows 8.1 ve üzeri)**

    **Windows &gt; Güvenilen Sertifika Profili (Windows Phone 8.1 ve üzeri)**

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Android, iOS, Mac OS X, Windows 8.1 veya Windows Phone 8.1'e yönelik güvenilen sertifika profili ayarlarını yapılandırmak için gerekli bilgileri sağlayın. 

    - **Sertifika dosyası** ayarında, sertifika veren CA’nızdan dışarı aktardığınız Güvenilen Kök CA sertifikasını (**.cer**) içeri aktarın. **Hedef depo** ayarı yalnızca Windows 8.1 ve üstünü çalıştıran cihazlara, cihazın birden çok hedef deposu olması durumunda uygulanır.

    
    - **Konu adı biçimi** altında, **Özel**’i seçerek özel bir konu adı biçimi sağlayın.  

        Özel biçim için şu an desteklenen iki değişken **Ortak Ad (CN)** ve **E-posta (E)**’dır. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak aşağıdaki örnekte görüldüğü gibi özel bir konu adı biçimi oluşturabilirsiniz:  

        `CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US`  

        Örnekte yönetici, CN ve E değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Durum ve Ülke dizeleri kullanan bir konu adı biçimi oluşturmuştur. Desteklenen dizelerin listesi [CertStrToName işlevi](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx). konusunda verilmiştir.  


4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır.

### Görev 3: SCEP veya .PFX sertifika profilleri oluşturma
Güvenilen CA sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya .PFX sertifika profillerini oluşturun. Bir SCEP sertifika profili oluştururken, aynı platform için bir Güvenilen sertifika profili belirtmeniz gerekir. Bu, iki sertifika profilini bağlasa da her profili ayrı olarak dağıtmalısınız.

##### Bir SCEP sertifika profili oluşturmak için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **İlke** &gt; **İlke Ekle** öğesine tıklayın.

2.  Aşağıdaki ilke türlerinden birini yapılandırın:

    **Android &gt; SCEP Sertifika Profili (Android 4 ve üzeri)**

    **iOS &gt; SCEP Sertifika Profili (iOS 7.1 ve üzeri)**

    **Mac OS X &gt; SCEP Sertifika Profili (Mac OS X 10.9 ve üzeri)**

    **Windows &gt; SCEP Sertifika Profili (Windows 8.1 ve üzeri)**

    **Windows &gt; SCEP Sertifika Profili (Windows Phone 8.1 ve üzeri)**

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  SCEP sertifika profili ayarlarını yapılandırmak için, profil yapılandırma sayfasındaki yönergeleri izleyin.
    > [!NOTE]
    > 
    > **Konu adı biçimi** altında **Özel**’i seçerek özel bir konu adı biçimi sağlayın.
    > 
    >  Özel biçim için şu an desteklenen iki değişken Ortak Ad (CN) ve E-posta (E)’dır. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak aşağıdaki örnekte görüldüğü gibi özel bir konu adı biçimi oluşturabilirsiniz:
    
    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US
    
    >    Örnekte yönetici, *CN* ve *E* değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Durum ve Ülke dizeleri kullanan bir konu adı biçimi oluşturmuştur. Desteklenen dizelerin listesi [CertStrToName işlevi](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) konusunda verilmiştir.

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır.

##### Bir .PFX sertifika profili oluşturmak için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **İlke** &gt; **İlke Ekle** öğesine tıklayın.

2.  Aşağıdaki ilke türlerinden birini yapılandırın:



-   **Android &gt; .PFX Sertifika Profili (Android 4 ve üzeri)**

    -   **Windows &gt; PKCS #12 (.PFX)  Sertifika Profili (Windows 10 ve üzeri)**

    -   **Windows &gt; PKCS #12 (.PFX)  Sertifika Profili (Windows Phone 10 ve üzeri)**

    -    **iOS > PKCS #12 (.PFX) Sertifika Profili (iOS 7.1 ve üzeri)**    

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  İlke formunda istenen bilgileri girin.

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır.

## Sertifika profilleri dağıtma
Sertifika profillerini dağıtırken, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihazlara yüklenir ve SCEP veya .PFX sertifika profili cihaz tarafından bir sertifika isteği oluşturmak için kullanılır.

Sertifika profilleri, yalnızca profili oluştururken kullanılan platforma bağlı olarak geçerli cihazlara yüklenir.

-   Sertifika profillerini kullanıcı koleksiyonları veya cihaz koleksiyonlarına dağıtabilirsiniz.

    > [!TIP]
    > Sertifikaların cihaz kayıtlarından sonra cihazlara hızlı bir şekilde yayımlanmasını sağlamak için sertifika profilini bir kullanıcı grubuna (cihaz grubuna değil) dağıtın. Bir cihaz grubuna dağıtırsanız, cihaz ilkeyi almadan önce tam cihaz kaydı gerçekleşmelidir.

-   Her profil ayrı ayrı dağıtılsa da, hem Güvenilen Kök hem de SCEP/.PFX profili dağıtılmalıdır; aksi takdirde, SCEP/.PFX sertifika ilkesi başarısız olur.

Sertifika profillerini, Intune için diğer ilkeleri dağıttığınız şekilde dağıtırsınız:

1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.
###  Sonraki adımlar

Artık e-posta, Wi-Fi ve VPN profillerinin güvenliğini sağlamaya yardımcı olmak için sertifikaları kullanabilirsiniz:

-  [E-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md)
-  [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


