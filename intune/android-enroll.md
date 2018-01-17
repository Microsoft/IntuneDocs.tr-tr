---
title: "Android cihazları Intune’a kaydetme | Microsoft Docs"
titlesuffix: Azure portal
description: "Intune’da Android cihazları kaydetmeyi öğrenin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7877d0bb6ba7a9c9d51cd261a7f1fbf555f88961
ms.sourcegitcommit: 0795870bfe941612259ebec0fe313a783a44d9b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2018
---
# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak, Samsung Knox Standard cihazları dahil olmak üzere Android cihazları yönetebilirsiniz. Ayrıca, [Android for Work cihazlarda](#enable-enrollment-of-android-for-work-devices) iş profilini de yönetebilirsiniz.

Samsung Knox Standard çalıştıran cihazlarda Intune ile birden çok kullanıcı yönetimi gerçekleştirilebilir. Yani son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da merkezi olarak yönetilir. Son kullanıcılar oturum açtıklarında, uygulamalara erişir ve ek olarak kendilerine uygulanan ilkeler varsa bunları alırlar. Kullanıcılar oturumu kapattığında tüm veriler silinir.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlayabilirsiniz.

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak izin verir.

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

Cihaz yönetimini etkinleştirmek için, kullanıcılarınızın Intune Şirket Portalı uygulamasını (Google Play’de bulunur) indirmeleri ve ardından uygulamayı açıp istemleri izleyerek cihazlarını kaydetmeleri gerekir. Android cihazları yönetilir duruma geldikten sonra [uyumluluk ilkeleri atayabilir](compliance-policy-create-android.md), [uygulamaları yönetebilir](app-management.md) ve daha fazlasını yapabilirsiniz.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work cihazlarının kaydını etkinleştirme

[Android for Work desteği olan](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) cihazlarda iş profilinin yönetimini etkinleştirmek için Intune'a bir Android for Work bağlaması eklemeniz gerekir. Android for Work destekleyen ancak önceden normal Android cihazlar olarak kaydedilmiş olan cihazları kaydetmek için, bu cihazların kaydını kaldırmalı ve daha sonra bunları tekrar kaydetmelisiniz.

Android for Work cihazları bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı kullanarak kaydediyorsanız, hesap başına yalnızca 10 cihaz sınırı vardır.

## <a name="add-android-for-work-binding-for-intune"></a>Intune için Android for Work Bağlaması ekleme

1. **Intune MDM’yi ayarlama**<br>
Henüz yapmadıysanız, [mobil cihaz yönetimi yetkilisini](mdm-authority-set.md) **Microsoft Intune** olarak ayarlayarak mobil cihaz yönetimine hazırlanın.
2. **Android for Work bağlamasını yapılandırma**<br>
    Bir Intune yöneticisi olarak Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**'u seçin.

   a. **Intune** dikey penceresinde **Cihaz kaydı** > **Android for Work Kaydı**’nı seçin ve **Yapılandır**’a tıklayarak Google Play’in Android for Work web sitesini açın. Web sitesi, tarayıcınızda yeni bir sekmede açılır.
   ![Android for Work bağlamasını yapılandır bağlantısını gösteren ekran görüntüsü](./media/android-work-bind.png)

   b. **Google’da oturum açma**<br>
   Google'ın oturum açma sayfasında, bu kiracı için tüm Android for Work yönetim görevleriyle ilişkilendirilecek Google hesabını girin. Bu, şirketinizin BT yöneticilerinin Play for Work konsolunda uygulama yönetmek ve yayımlamak için paylaştığı Google hesabıdır.

   c. **Kuruluş ayrıntıları sağlama**<br>
   Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında **Microsoft Intune** görüntülenmelidir. Android for Work sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work kayıt ayarlarını belirtme
   Android for Work yalnızca belirli Android cihazlarda desteklenmektedir. Google'ın [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")’ne bakın. Android for Work destekleyen tüm cihazlar geleneksel Android yönetimini de destekler. Intune, Android for Work destekleyen cihazların nasıl yönetileceğinizi belirtmenize olanak sağlar:

   - **Tüm cihazları Android olarak yönet**. Android for Work destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar geleneksel Android cihaz olarak kaydedilir.
   - **Desteklenen cihazları Android for Work olarak yönet**. Android for Work destekleyen tüm cihazlar Android for Work cihazlar olarak kaydedilir. Android for Work desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
   - **Yalnızca bu kullanıcı gruplarındaki kullanıcılar için desteklenen cihazları Android for Work olarak yönet**. Android for Work yönetimini sınırlı bir kullanıcı kümesine hedefleyebilirsiniz. Yalnızca Android for Work destekleyen bir cihaz kaydeden seçili grupların üyeleri Android for Work cihazlar olarak kaydedilir. Diğerlerinin tümü Android cihaz olarak kaydedilir. Bu, Android for Work pilot çalışmalarında kullanışlıdır.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Yönetilen Google Play Store'da Şirket Portalı uygulamasını onaylama
Android için Şirket Portalı uygulamasının otomatik uygulama güncelleştirmelerini alabilmesi için, bu uygulamayı yönetilen Google Play Store'da onaylamanız gerekir. Onaylamazsanız, Şirket Portalı zamanla güncelliğini yitirir ve Microsoft'un kullanıma sunduğu önemli hata düzeltmelerini veya yeni özellikleri alamaz.

Intune Şirket Portalı'nı onaylamak için aşağıdaki adımları izleyin:

1.  [Yönetilen Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal)’da Şirket Portalı uygulamasına göz atın.
2.  Yönetilen Google Play Store'da, Android for Work bağlamasını yapılandırırken kullandığınız Google hesabıyla oturum açın.
3.  **Onayla**'ya tıklayın.  Yeni bir iletişim kutusu açılır.
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
    Bir Intune yöneticisi olarak Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**'u seçin.  **Intune** dikey penceresinde **Cihaz kaydı**, > **Android for Work Kaydı**’nı seçin ve **Bağlamayı kaldır**’a tıklayın.

2. **Android for Work bağlamasını kaldırmayı kabul etme**<br>
  Bağlamayı silmek için **Evet**’i seçin tüm Android for Work cihazların Intune kaydını silin.
