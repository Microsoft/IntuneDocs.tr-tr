---
title: "Sertifika profillerini yapılandırma | Microsoft Intune"
description: "Intune sertifika profilinin nasıl oluşturulacağını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: bafb86b1e388163c07110559e2a51bbe0dadc5ed


---

# <a name="configure-intune-certificate-profiles"></a>Intune sertifika profillerini yapılandırma
Altyapınızı ve sertifikalarınızı [SCEP için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-scep.md) veya [PFX için sertifika altyapısını yapılandırma](configure-certificate-infrastructure-for-pfx.md) bölümlerinde anlatıldığı gibi yapılandırdıktan sonra sertifika profilleri oluşturabilirsiniz. İşlem şöyledir:

- **Görev 1**: Güvenilen Kök CA sertifikasını dışarı aktarın
- **Görev 2**: Güvenilen sertifika profilleri oluşturun
- **Görev 3**: İki sertifika profili türünden birini oluşturun:
  - SCEP sertifika profilleri
  - .PFX Sertifika profilleri

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>**Görev 1**: Güvenilen Kök CA sertifikasını dışarı aktarın
Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın. Özel anahtarı dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktaracaksınız.

## <a name="task-2-create-trusted-certificate-profiles"></a>**Görev 2**: Güvenilen sertifika profilleri oluşturun
Bir Basit Sertifika Kayıt Protokolü (SCEP) veya PKCS #12 (.PFX) sertifika profili oluşturabilmeniz için önce bir Güvenilen sertifika profili oluşturmalısınız. Her mobil cihaz platformu için bir Güvenilen sertifika profiline ve bir SCEP veya .PFX profiline ihtiyacınız vardır.

### <a name="to-create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin ve bir cihaz platformu seçin. Bu cihazlar için bir güvenilen sertifika profili oluşturabilirsiniz:

-  Android 4 ve üzeri

-  Android for Work

-  iOS 7.1 ve üzeri

-  Mac OS X 10.9 ve üzeri

-  Windows 8.1 ve üzeri

-  Windows Phone 8.1 ve üzeri

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

2.  Bir **Güvenilen Sertifika Profili** ekleyin.

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Android, iOS, Mac OS X, Windows 8.1 veya Windows Phone 8.1 Güvenilen sertifika profili ayarlarını yapılandırmak için istenen bilgileri girin.
4.  **Sertifika dosyası** ayarında, sertifika veren CA’nızdan dışarı aktardığınız Güvenilen Kök CA sertifikasını (.cer dosyası) içeri aktarın. **Hedef depo** ayarı yalnızca Windows 8.1 ve üstünü çalıştıran cihazlara, cihazın birden çok hedef deposu olması durumunda uygulanır.

4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

> [!NOTE]
>
> Android ve Android for Work cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir bildirim görüntüler.


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a>**Görev 3**: SCEP veya .PFX sertifika profilleri oluşturma
Güvenilen CA sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya .PFX sertifika profilleri oluşturun. Bir SCEP sertifika profili oluştururken, aynı platform için bir Güvenilen sertifika profili belirtmeniz gerekir. Bu, iki sertifika profilini birbirine bağlasa da her profili ayrı olarak dağıtmalısınız.

### <a name="to-create-an-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin ve bir cihaz platformu seçin.  Bu cihazlar için bir SCEP sertifika profili oluşturabilirsiniz:

-  Android 4 ve üzeri

-  Android for Work

-  iOS 7.1 ve üzeri

-  Mac OS X 10.9 ve üzeri

-  Windows 8.1 ve üzeri

-  Windows Phone 8.1 ve üzeri

2.  Bir **SCEP Sertifika Profili** ilkesi ekleme

    Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  SCEP sertifika profili ayarlarını yapılandırmak için, profil yapılandırma sayfasındaki yönergeleri izleyin.
    > [!NOTE]
    >
    > **Konu adı biçimi**’nin altında **Özel**’i seçerek özel bir konu adı biçimi girin (yalnızca iOS profillerinde).
    >
    > Özel biçim için şu an desteklenen iki değişken şunlardır: `Common Name (CN)` ve `Email (E)`. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak şunun gibi özel bir konu adı biçimi oluşturabilirsiniz:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > Bu örnekte, yönetici, `CN` ve `E` değişkenlerinin yanı sıra Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için dizeler kullanan bir konu adı biçimi oluşturmuştur. [CertStrToName işlevi](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) desteklenen dizeleri listeler.

4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

### <a name="to-create-a-pfx-certificate-profile"></a>Bir .PFX sertifika profili oluşturmak için

1.  [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin ve bir cihaz platformu seçin. . PFX sertifikaları aşağıdakilerde desteklenir:
  - Android 4 ve üzeri
  - Android for Work
  - Windows 10 ve üzeri
  - Windows Phone 10 ve üzeri
  - iOS 8.0 ve üzeri)    


2.  Bir **.PFX Sertifika Profili** ilkesi ekleyin.
      Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  İlke formunda istenen bilgileri girin.
4.  **İlkeyi Kaydet**’i seçin.

Yeni ilke, **İlke** çalışma alanında gösterilir. Artık ilkeyi dağıtabilirsiniz.

## <a name="deploy-certificate-profiles"></a>Sertifika profilleri dağıtma
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

### <a name="next-steps"></a>Sonraki adımlar

Bundan sonra sertifikaları e-posta, Wi-Fi ve VPN profillerinin güvenliğini sağlamak için nasıl kullanacağınızı öğrenin.

-  [E-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md)
-  [Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


