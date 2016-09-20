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
ms.sourcegitcommit: 8e3f7cac8eb3495aad3835ec4713d67a58383c66
ms.openlocfilehash: 8b08f8fde6136b8eca61f6ae7a8c21635f7d452e


---

# Intune sertifika profillerini yapılandırma
Altyapınızı ve sertifikalarınızı [SCEP için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-scep.md) veya [PFX için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-pfx.md) bölümlerinde anlatıldığı gibi yapılandırdıktan sonra sertifika profilleri oluşturabilirsiniz. İşlem şöyledir:

- **Görev 1**: Güvenilen Kök CA sertifikasını dışarı aktarın
- **Görev 2**: Güvenilen sertifika profilleri oluşturun
- **Görev 3**: İki sertifika profili türünden birini oluşturun:
  - SCEP sertifika profilleri
  - .PFX Sertifika profilleri

## **Görev 1**: Güvenilen Kök CA sertifikasını dışarı aktarın
Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın. Özel anahtarı dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktaracaksınız.

## **Görev 2**: Güvenilen sertifika profilleri oluşturun
Bir Basit Sertifika Kayıt Protokolü (SCEP) veya PKCS #12 (.PFX) sertifika profili oluşturabilmeniz için önce bir Güvenilen sertifika profili oluşturmalısınız. Her mobil cihaz platformu için bir Güvenilen sertifika profiline ve bir SCEP veya .PFX profiline ihtiyacınız vardır.

### Güvenilen bir sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.
2.  Aşağıdaki ilke türlerinden birini ekleyin:
    - **Android &gt; Güvenilen Sertifika Profili (Android 4 ve üzeri)**
    - **iOS &gt; Güvenilen Sertifika Profili (iOS 7.1 ve üzeri)**
    - **Mac OS X &gt; Güvenilen Sertifika Profili (Mac OS X 10.9 ve üzeri)**
    - **Windows &gt; Güvenilen Sertifika Profili (Windows 8.1 ve üzeri)**
    - **Windows &gt; Güvenilen Sertifika Profili (Windows Phone 8.1 ve üzeri)**

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Android, iOS, Mac OS X, Windows 8.1 veya Windows Phone 8.1 Güvenilen sertifika profili ayarlarını yapılandırmak için istenen bilgileri girin.

    - **Sertifika dosyası** ayarında, sertifika veren CA’nızdan dışarı aktardığınız Güvenilen Kök CA sertifikasını (.cer dosyası) içeri aktarın. **Hedef depo** ayarı yalnızca Windows 8.1 ve üstünü çalıştıran cihazlara, cihazın birden çok hedef deposu olması durumunda uygulanır.
    -  **Konu adı biçimi** altında **Özel**’i seçerek özel bir konu adı biçimi girin.  
        Özel biçim için şu an desteklenen iki değişken şunlardır: `Common Name (CN)` ve `Email (E)`. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak şunun gibi özel bir konu adı biçimi oluşturabilirsiniz:  

        `CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US`  

        Bu örnekte, yönetici, `CN` ve `E` değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için dizeler kullanan bir konu adı biçimi oluşturmuştur. [CertStrToName işlevi](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) desteklenen dizeleri listeler.  
4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

## **Görev 3**: SCEP veya .PFX sertifika profilleri oluşturma
Güvenilen CA sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya .PFX sertifika profilleri oluşturun. Bir SCEP sertifika profili oluştururken, aynı platform için bir Güvenilen sertifika profili belirtmeniz gerekir. Bu, iki sertifika profilini birbirine bağlasa da her profili ayrı olarak dağıtmalısınız.

### Bir SCEP sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.
2.  Aşağıdaki ilke türlerinden birini ekleyin:
    - **Android &gt; SCEP Sertifika Profili (Android 4 ve üzeri)**
    - **iOS &gt; SCEP Sertifika Profili (iOS 7.1 ve üzeri)**
    - **Mac OS X &gt; SCEP Sertifika Profili (Mac OS X 10.9 ve üzeri)**
    - **Windows &gt; SCEP Sertifika Profili (Windows 8.1 ve üzeri)**
    - **Windows &gt; SCEP Sertifika Profili (Windows Phone 8.1 ve üzeri)**

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  SCEP sertifika profili ayarlarını yapılandırmak için, profil yapılandırma sayfasındaki yönergeleri izleyin.
    > [!NOTE]
    >
    > **Konu adı biçimi** altında **Özel**’i seçerek özel bir konu adı biçimi girin.
    >
    > Özel biçim için şu an desteklenen iki değişken şunlardır: `Common Name (CN)` ve `Email (E)`. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak şunun gibi özel bir konu adı biçimi oluşturabilirsiniz:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > Bu örnekte, yönetici, `CN` ve `E` değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için dizeler kullanan bir konu adı biçimi oluşturmuştur. [CertStrToName işlevi](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) desteklenen dizeleri listeler.

4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

### Bir .PFX sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.
2.  Aşağıdaki ilke türlerinden birini ekleyin:
  - **Android &gt; .PFX Sertifika Profili (Android 4 ve üzeri)**
  - **Windows &gt; PKCS #12 (.PFX) Sertifika Profili (Windows 10 ve üzeri)**
  - **Windows &gt; PKCS #12 (.PFX) Sertifika Profili (Windows Phone 10 ve üzeri)**
  - **iOS > PKCS #12 (.PFX) Sertifika Profili (iOS 7.1 ve üzeri)**    
    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  İlke formunda istenen bilgileri girin.
4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

## Sertifika profilleri dağıtma
Sertifika profilleri dağıtırken Güvenilen CA sertifika profilinden alınan sertifika dosyası cihaza yüklenir. Cihaz, bir sertifika isteği oluşturmak için SCEP veya .PFX sertifika profilini kullanır.

Sertifika profilleri, yalnızca profili oluştururken kullandığınız platformu çalıştıran cihazlara yüklenir.

-   Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına dağıtabilirsiniz.

    > [!TIP]
    > Cihaz kaydolduktan sonra cihaza çabucak bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna dağıtın. Bir cihaz grubuna dağıtırsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.

-   Her profili ayrı olarak dağıtsanız da Güvenilen Kök CA’sını ve SCEP veya .PFX profilini de dağıtmanız gerekir. Aksi takdirde SCEP veya .PFX sertifika ilkesi başarısız olur.

Sertifika profillerini, Intune için diğer ilkeleri dağıttığınız şekilde dağıtın:

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.
2.   **Dağıtımı Yönet** iletişim kutusunda:
    -   **İlkeyi dağıtmak için** ilkenin dağıtılacağı bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'ı seçin.
    -   **Dağıtmadan iletişim kutusunu kapatmak için** **İptal**’i seçin.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt kısmında dağıtım hakkında daha fazla bilgi görebilirsiniz.

### Sonraki adımlar

Bundan sonra sertifikaları e-posta, Wi-Fi ve VPN profillerinin güvenliğini sağlamak için nasıl kullanacağınızı öğrenin.

-  [E-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md)
-  [Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


