mdm-authority-set---
# <a name="required-metadata"></a>gerekli meta veriler

başlık: Android cihazları Intune’a kaydetme titleSuffix: “Intune Azure önizlemesi” açıklama: “Intune Azure önizlemesi: Intune Azure önizlemesinde Android cihazları kaydetmeyi öğrenin.”
anahtar kelimeler: author: nathbarn ms.author: nathbarn manager: angrobe ms.date: 04.12.2017 ms.topic: makale ms.prod: ms.service: microsoft-intune ms.technology: ms.assetid: f276d98c-b077-452a-8835-41919d674db5

# <a name="optional-metadata"></a>isteğe bağlı meta veriler

#<a name="robots"></a>ROBOTS:
#<a name="audience"></a>audience:
#<a name="msdevlang"></a>ms.devlang:
ms.reviewer: chrisbal ms.suite: ems
#<a name="mstgtpltfrm"></a>ms.tgt_pltfrm:
ms.custom: intune-azure

---

# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bir Intune yöneticisi olarak, Intune size Samsung Knox Standard cihazları dahil olmak üzere Android cihazlarını yönetme olanağı tanır. Ayrıca, [Android for Work cihazlarında](#enable-enrollment-of-android-for-work-devices) iş profilini de yönetebilirsiniz.

Samsung KNOX Standard çalıştıran cihazlarda Intune ile birden çok kullanıcı yönetimi gerçekleştirilebilir. Bu, son kullanıcıların Azure Active Directory kimlik bilgilerini kullanarak cihazda oturum açıp kapatabileceği ve cihazın kullanım durumundan bağımsız olarak merkezden yönetileceği anlamına gelir. Oturum açan kullanıcılar kendilerine atanan uygulamalara ilkelere otomatik olarak erişir. Kullanıcılar oturumu kapattığında tüm veriler silinir.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a MDM yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Intune’u mobil cihaz yönetimi için ilk kez ayarladığınız sırada bu öğeyi tek bir kez ayarlarsınız; dolayısıyla zaten ayarlamış olabilirsiniz.

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak izin verir.

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md#set-device-type-restrictions).

Bir kullanıcının kaydedebileceği en fazla cihaz sayısını ayarlamak için bkz. [Cihaz sınırı kısıtlamaları ayarlama](enrollment-restrictions-set.md#set-device-limit-restrictions).

Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın Google Play'de bulunan Intune Şirket Portalı uygulamasını indirmeleri ve ardından uygulamayı açıp kaydolmaya yönelik istemleri izleyerek cihazlarını kaydetmeleri gerekir. Android cihazları yönetilir duruma geldikten sonra [uyumluluk ilkeleri atayabilir](compliance-policy-create-android.md), [uygulamaları yönetebilir](app-management.md) ve daha fazlasını yapabilirsiniz.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work cihazlarının kaydını etkinleştirme

[Android for Work desteği olan](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) cihazlarda iş profilinin yönetimini etkinleştirmek için Intune'a bir Android for Work bağlaması eklemeniz gerekir. Android for Work'ü destekleyen ancak daha önce normal Android cihazları olarak kaydedilen cihazları kaydetmek için cihazların kaydının silinmesi ve yeniden kaydedilmesi gerekir.

## <a name="add-android-for-work-binding-for-intune"></a>Intune İçin Android for Work Bağlaması Ekleme

1. **Intune MDM’yi ayarlama**<br>
Henüz yapmadıysanız, [mobil cihaz yönetimi yetkilisini](mdm-authority-set.md) **Microsoft Intune** olarak ayarlayarak mobil cihaz yönetimine hazırlanın.

2. **Android for Work bağlamasını yapılandırma**<br>
    Bir Intune yöneticisi olarak Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

    1. **Intune** dikey penceresinde **Cihaz kaydı**, > **Android for Work Kaydı**’nı seçin ve **Yapılandır**’a tıklayarak Google Play'in Android for Work web sitesini açın. Bu, tarayıcınızda yeni bir sekme açar.
  ![Android for Work bağlamasını yapılandır bağlantısını gösteren ekran görüntüsü](./media/android-work-bind.png)

    2. **Google'da oturum açma**<br>
   Google'ın oturum açma sayfasında, bu kiracı için tüm Android for Work yönetim görevleriyle ilişkilendirilecek Google hesabını girin. Bu, kuruluşunuzun BT yöneticilerinin Play for Work konsolunda uygulama yönetmek ve yayımlamak için kullandığı ortak Google hesabıdır.

    3. **Kuruluş ayrıntıları sağlama**<br>
   Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında *Microsoft Intune* görüntülenmelidir. Android for Work sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work Kayıt Ayarlarını Belirtme
   Android for Work yalnızca belirli Android cihazlarda desteklenmektedir. Google'ın [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")’ne bakın. Android for Work destekleyen tüm cihazlar geleneksel Android yönetimini de destekler.  Intune, Android for Work destekleyen cihazların nasıl yönetileceğinizi belirtmenize olanak sağlar:

   - **Tüm cihazları Android olarak yönet** - Android for Work destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar geleneksel Android cihaz olarak kaydedilir.
   - **Desteklenen cihazları Android for Work olarak yönet** - Android for Work destekleyen tüm cihazlar Android for Work cihazlar olarak kaydedilir. Android for Work desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
   - **Yalnızca bu kullanıcı gruplarındaki desteklenen cihazları Android for Work olarak yönet** - Android for Work yönetimini sınırlı bir kullanıcı grubuna hedeflemenize olanak sağlar. Yalnızca Android for Work destekleyen bir cihaz kaydeden seçili grupların üyeleri Android for Work cihazlar olarak kaydedilir. Diğerlerinin tümü Android cihaz olarak kaydedilir. Bu, Android for Work pilot çalışmalarında kullanışlıdır.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Son kullanıcılarınıza, Google Play’e gidip Intune Şirket Portalı uygulamasını indirmelerini ve ardından uygulamayı açıp istemleri izleyerek cihazlarını kaydetmelerini bildirmeniz gerekir. Uygulama, kullanıcılara kayıt süreci boyunca yol gösterir, kullanıcıların neler bekleyebileceklerini ve BT yöneticilerinin cihazlarında neler görüp göremeyeceklerini açıklar.

Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [Android cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Android for Work yönetici hesabınızın bağlamasını kaldırma

Android for Work kaydı ve yönetimini kapatabilirsiniz. Intune yönetim konsolundaki **Bağlamayı Kaldır**'a tıklamak tüm kayıtlı Android for Work cihazlarının kaydını siler ve Android for Work ile Intune arasındaki ilişkiyi kaldırır.

### <a name="how-to-unbind-an-android-for-work-account"></a>Bir Android for Work hesabının bağlamasını kaldırma

1. **Android for Work bağlamasını kaldırma**<br>
    Bir Intune yöneticisi olarak, Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.  **Intune** dikey penceresinde **Cihaz kaydı**, > **Android for Work Kaydı**’nı seçin ve **Bağlamayı kaldır**’a tıklayın.

2. **Android for Work bağlamasını kaldırmayı kabul etme**<br>
  Bağlamayı silmek için **Evet**’e tıklayın tüm Android for Work cihazların Intune kaydını silin.
