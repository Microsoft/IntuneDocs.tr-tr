---
# required metadata

title: Sertifika profillerini yapılandırma | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune sertifika profillerini yapılandırma
Altyapınız ve sertifikalarınız [Sertifika altyapısını yapılandırma](configure-certificate-infrastructure.md) konu başlığı altında açıklandığı gibi yapılandırıldıktan sonra, sertifika profillerini yapılandırabilirsiniz:

**Görev 1** - Güvenilen Kök CA sertifikasını dışarı aktarma

**Görev 2** - Güvenilen CA sertifika profilleri oluşturma

**Görev 3** - Şunlardan biri:

### SCEP sertifika profilleri oluşturma
.PFX sertifika profilleri oluşturma Görev 1 - Güvenilen Kök sertifikayı dışarı aktarma

Güvenilen Kök CA sertifikasını, sertifika veren CA'dan veya CA'nıza herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın.

### Özel anahtarı dışarı aktarmazsınız.
Güvenilen sertifika profili yapılandırırken bu sertifikayı içeri aktaracaksınız. Görev 2 - Güvenilen sertifika profilleri oluşturma

##### Bir SCEP veya .PFX sertifika profili oluşturabilmeniz için önce bir **Güvenilen sertifika profili** oluşturmanız gerekir.

1.  Her mobil cihaz platformu için bir Güvenilen sertifika profiline ve SCEP veya .PFS profiline ihtiyacınız vardır.

2.  Güvenilen bir sertifika profili oluşturmak için

    **[Intune yönetim konsolunu](https://manage.microsoft.com) açın ve **İlke** &gt; **İlke Ekle**’ye tıklayın.**

    **Aşağıdaki ilke türlerinden birini yapılandırın:**

    **Android &gt; Güvenilen Sertifika Profili (Android 4 ve üzeri)**

    **iOS &gt; Güvenilen Sertifika Profili (iOS 7.1 ve üzeri)**

    **Mac OS X &gt; Güvenilen Sertifika Profili (Mac OS X 10.9 ve üzeri)**

    Windows &gt; Güvenilen Sertifika Profili (Windows 8.1 ve üzeri)

3.  Windows &gt; Güvenilen Sertifika Profili (Windows Phone 8.1 ve üzeri) Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Android, iOS, Mac OS X, Windows 8.1 veya Windows Phone 8.1'e yönelik güvenilen sertifika profili ayarlarını yapılandırmak için gerekli bilgileri sağlayın.


4.  **Sertifika dosyası** ayarında, sertifika veren CA’nızdan dışarı aktardığınız Güvenilen Kök CA sertifikasını (**.cer**) içeri aktarın.

**Hedef depo** ayarı yalnızca Windows 8.1 ve üstünü çalıştıran cihazlara, cihazın birden çok hedef deposu olması durumunda uygulanır.

### İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.
Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır. Görev 3: SCEP veya .PFX sertifika profilleri oluşturma Güvenilen CA sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya .PFX sertifika profillerini oluşturun.

##### Bir SCEP sertifika profili oluştururken, aynı platform için bir Güvenilen sertifika profili belirtmeniz gerekir.

1.  Bu, iki sertifika profilini bağlasa da her profili ayrı olarak dağıtmalısınız.

2.  Bir SCEP sertifika profili oluşturmak için

    **[Intune yönetim konsolunu](https://manage.microsoft.com) açın, **İlke** &gt; **İlke Ekle**’ye tıklayın.**

    **Aşağıdaki ilke türlerinden birini yapılandırın:**

    **Android &gt; SCEP Sertifika Profili (Android 4 ve üzeri)**

    **iOS &gt; SCEP Sertifika Profili (iOS 7.1 ve üzeri)**

    **Mac OS X &gt; SCEP Sertifika Profili (Mac OS X 10.9 ve üzeri)**

    Windows &gt; SCEP Sertifika Profili (Windows 8.1 ve üzeri)

3.  Windows &gt; SCEP Sertifika Profili (Windows Phone 8.1 ve üzeri)

4.  Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

SCEP sertifika profili ayarlarını yapılandırmak için, profil yapılandırma sayfasındaki yönergeleri izleyin.

##### İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

1.  Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır.

2.  Bir .PFX sertifika profili oluşturmak için



-   **[Intune yönetim konsolunu](https://manage.microsoft.com) açın, **İlke** &gt; **İlke Ekle**’ye tıklayın.**

    -   **Aşağıdaki ilke türlerinden birini yapılandırın:**

    -   **Android &gt; .PFX Sertifika Profili (Android 4 ve üzeri)**

    -    **Windows &gt; PKCS #12 (.PFX)  Sertifika Profili (Windows 10 ve üzeri)**    

    Windows &gt; PKCS #12 (.PFX)  Sertifika Profili (Windows Phone 10 ve üzeri)

3.  iOS > PKCS #12 (.PFX) Sertifika Profili (iOS 7.1 ve üzeri)

4.  Daha fazla bilgi edinin: [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

İlke formunda istenen bilgileri girin.

## İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.
Yeni ilke, **İlke** çalışma alanında görüntülenir ve dağıtıma hazırdır.

Sertifika profilleri dağıtma

-   Sertifika profillerini dağıtırken, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihazlara yüklenir ve SCEP veya .PFX sertifika profili cihaz tarafından bir sertifika isteği oluşturmak için kullanılır.

    > [!TIP]
    > Sertifika profilleri, yalnızca profili oluştururken kullanılan platforma bağlı olarak geçerli cihazlara yüklenir. Sertifika profillerini kullanıcı koleksiyonları veya cihaz koleksiyonlarına dağıtabilirsiniz.

-   Sertifikaların cihaz kayıtlarından sonra cihazlara hızlı bir şekilde yayımlanmasını sağlamak için sertifika profilini bir kullanıcı grubuna (cihaz grubuna değil) dağıtın.

Bir cihaz grubuna dağıtırsanız, cihaz ilkeyi almadan önce tam cihaz kaydı gerçekleşmelidir.

1.  Her profil ayrı ayrı dağıtılsa da, hem Güvenilen Kök hem de SCEP/.PFX profili dağıtılmalıdır; aksi takdirde, SCEP/.PFX sertifika ilkesi başarısız olur.

2.  Sertifika profillerini, Intune için diğer ilkeleri dağıttığınız şekilde dağıtırsınız:

    -   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

    -    **Dağıtımı Yönet** iletişim kutusunda:

**İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.
###  **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

-  [Sonraki adımlar](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Artık e-posta, Wi-Fi ve VPN profillerinin güvenliğini sağlamaya yardımcı olmak için sertifikaları kullanabilirsiniz:](wi-fi-connections-in-microsoft-intune.md)
-  [E-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


