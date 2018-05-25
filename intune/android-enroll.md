---
title: Intune’da Android cihazları kaydetme
titlesuffix: Microsoft Intune
description: Intune’da Android cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3212d1a3d3454542dd9d34409fc788558f2d7eed
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2018
---
# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak, Samsung Knox Standard cihazları dahil olmak üzere Android cihazları yönetebilirsiniz. Ayrıca, [Android for Work cihazlarda](#enable-enrollment-of-android-for-work-devices) iş profilini de yönetebilirsiniz.

Samsung Knox Standard çalıştıran cihazlarda Intune ile birden çok kullanıcı yönetimi gerçekleştirilebilir. Yani son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da merkezi olarak yönetilir. Son kullanıcılar oturum açtıklarında, uygulamalara erişir ve ek olarak kendilerine uygulanan ilkeler varsa bunları alırlar. Kullanıcılar oturumu kapattığında tüm veriler silinir.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlayabilirsiniz.

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak izin verir.

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın Intune Şirket Portalı uygulamasını (Google Play’de bulunur) indirmeleri ve ardından uygulamayı açıp istemleri izleyerek cihazlarını kaydetmeleri gerekir. Android cihazları yönetilir duruma geldikten sonra [uyumluluk ilkeleri atayabilir](compliance-policy-create-android.md), [uygulamaları yönetebilir](app-management.md) ve daha fazlasını yapabilirsiniz.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work cihazlarının kaydını etkinleştirme

[Android for Work desteği olan](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) cihazlarda iş profilinin yönetimini etkinleştirmek için Intune'a bir Android for Work bağlaması eklemeniz gerekir. Android for Work’e cihaz kaydetmek istiyorsanız ancak bu cihazlar zaten normal Android cihazlar olarak kayıtlıysa, cihazların kaydını kaldırmalı ve ardından tekrar kaydetmelisiniz.

Android for Work cihazları bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı kullanarak kaydediyorsanız, hesap başına yalnızca 10 cihaz sınırı vardır.

Daha fazla bilgi için bkz. [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md).

## <a name="add-android-for-work-binding-for-intune"></a>Intune için Android for Work Bağlaması ekleme

> [!NOTE]
> Google ve Microsoft etki alanları arasındaki etkileşim nedeniyle, bu adımı başarıyla tamamlamanız için tarayıcı ayarlarınızı değiştirmeniz gerekebilir.  “portal.azure.com” ve “play.google.com” adreslerinin tarayıcınızda aynı güvenlik bölgesinde olduğundan emin olun.

1. **Intune MDM’yi ayarlama**<br>
Henüz yapmadıysanız, [mobil cihaz yönetimi yetkilisini](mdm-authority-set.md) **Microsoft Intune** olarak ayarlayarak mobil cihaz yönetimine hazırlanın.
2. **Android for Work bağlamasını yapılandırma**<br>
    
   a. [Azure portalında Intune](https://aka.ms/intuneportal)’da oturum açın, **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play**’i seçin.  Özel bir Intune yönetici rolü kullanıyorsanız bu seçeneğe erişim, Kuruluş Okuma ve Güncelleştirme izinlerini gerektirir.
   
   ![Android for Work kayıt ekranı](./media/android-work-bind.png)

   b. **Kabul ediyorum**’u seçerek Microsoft’un [Google’a kullanıcı ve cihaz bilgilerini göndermesine](data-intune-sends-to-google.md) izin verin. 
   
   c. **Hemen bağlanmak için Google’ı başlat**’ı seçerek Google Play’in Android for Work web sitesini açın. Web sitesi, tarayıcınızda yeni bir sekmede açılır.
  
   d. **Google’da oturum açma**<br>
   Google'ın oturum açma sayfasında, bu kiracı için tüm Android for Work yönetim görevleriyle ilişkilendirilecek Google hesabını girin. Bu, şirketinizin BT yöneticilerinin Play for Work konsolunda uygulama yönetmek ve yayımlamak için paylaştığı Google hesabıdır. Mevcut bir Google hesabını kullanabilir veya yeni bir tane oluşturabilirsiniz.  Seçtiğiniz hesabın bir G-Suite etki alanıyla ilişkilendirilmemiş olması gerekir.

   e. **Kuruluş ayrıntıları sağlama**<br>
   Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında **Microsoft Intune** görüntülenmelidir. Android for Work sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work kayıt ayarlarını belirtme
Android for Work yalnızca belirli Android cihazlarda desteklenmektedir. Google'ın [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22)’ne bakın. Android for Work destekleyen tüm cihazlar geleneksel Android yönetimini de destekler. Intune, Android for Work destekleyen cihazların [Kayıt Kısıtlamaları](enrollment-restrictions-set.md) içerisinde nasıl yönetileceğini belirtmenize olanak sağlar.

- **Engelle (varsayılan ayar)**: Android for Work destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar geleneksel Android cihaz olarak kaydedilir.
- **İzin ver**: Android for Work destekleyen tüm cihazlar Android for Work cihazlar olarak kaydedilir. Android for Work desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Yönetilen Google Play Store'da Şirket Portalı uygulamasını onaylama
Android için Şirket Portalı uygulamasının otomatik uygulama güncelleştirmelerini alabilmesi için bu uygulamayı yönetilen Google Play Store'da onaylamanız gerekir. Onaylamazsanız, Şirket Portalı zamanla güncelliğini yitirir ve Microsoft'un kullanıma sunduğu önemli hata düzeltmelerini veya yeni özellikleri alamaz.

Intune Şirket Portalı'nı onaylamak için aşağıdaki adımları izleyin:

1.  [Yönetilen Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal)’da Şirket Portalı uygulamasına göz atın.
2.  Yönetilen Google Play Store'da, Android for Work bağlamasını yapılandırırken kullandığınız Google hesabıyla oturum açın.
3.  **Onayla**’ya tıkladığınızda yeni bir iletişim kutusu açılır.
4.  Bu iletişim kutusunda izinleri gözden geçirin ve ardından **Onayla**'ya tıklayın. Şirket Portalı uygulamasının cihazdaki iş profilini yönetmesine olanak tanımak için bu izinlerin verilmesi gerekir.
5.  **Uygulama yeni izinler istediğinde onaylı durumda tut** öğesini seçin ve **Kaydet**'e tıklayın.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın

Kullanıcılarınıza, Google Play’e gidip Intune Şirket Portalı uygulamasını indirmelerini ve ardından uygulamayı açıp istemleri izleyerek cihazlarını kaydetmelerini bildirin. Uygulama, kullanıcılara kayıt süreci boyunca yol gösterir, kullanıcıların neler bekleyebileceklerini ve BT yöneticilerinin cihazlarında neler görüp göremeyeceklerini açıklar.

Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [Android cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Diğer kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Android for Work yönetici hesabınızın bağlamasını kaldırma

Android for Work kaydı ve yönetimini kapatabilirsiniz. Intune yönetim konsolunda **Bağlamayı kaldır**’ı seçmek, tüm Android for Work cihazların kaydını kaldırır. Ayrıca Android for Work hesabı ve Intune arasında ilişkiyi de kaldırır.

### <a name="to-unbind-an-android-for-work-account"></a>Bir Android for Work hesabının bağlamasını kaldırmak için

1. **Android for Work bağlamasını kaldırma**<br>
    Bir Intune yöneticisi olarak [Azure portalında](https://portal.azure.com) **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.  **Intune** bölmesinde **Cihaz kaydı**, > **Android for Work Kaydı**’nı seçin ve **Bağlamayı kaldır**’a tıklayın.

2. **Android for Work bağlamasını kaldırmayı kabul etme**<br>
  Bağlamayı silmek için **Evet**’i seçin tüm Android for Work cihazların Intune kaydını silin.

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Bir Samsung Knox cihazı kaydederken son kullanıcı deneyimi
Samsung Knox cihazları kaydederken göz önünde bulundurulması gereken birkaç nokta vardır:
-   Hiçbir ilke PIN gerektirmiyorsa bile cihazın kaydedilebilmesi için en az dört basamaklı bir PIN’i olmalıdır. Cihazın PIN’i yoksa, kullanıcıdan bir PIN oluşturması istenir.
-   Workplace Join Sertifikaları (WPJ) için kullanıcı etkileşimi yoktur.
-   Kullanıcıya Hizmet Kaydı bilgileri ve uygulamanın yapabilecekleri anlatılır.
-   Kullanıcıya Knox Kaydı bilgileri ve Knox’un yapabilecekleri anlatılır.
-   Bir Şifreleme İlkesi zorlanmışsa, kullanıcıların cihaz geçiş kodu olarak altı karakterlik karmaşık parola ayarlamaları gereklidir.
-   Şirket Kaynağı Erişimi için bir hizmet tarafından gönderilen sertifikaların yüklenmesi için başka kullanıcı istemi yoktur.
- Bazı eski Knox cihazlar, kullanıcıdan Şirket Kaynağı Erişimi için kullanılan ek sertifikalar isteyebilir.
- Bir Samsung Mini cihaz, **Sertifika Bulunamadı** veya **Cihaz Kaydedilemedi** hataları ile WPJ’yi yükleyemezse, en son Samsung Üretici Yazılımı Güncelleştirmelerini yükleyin.
