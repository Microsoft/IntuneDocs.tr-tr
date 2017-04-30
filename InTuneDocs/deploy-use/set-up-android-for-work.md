---
title: "Android for Work’ü ayarlama| Microsoft Docs"
description: "Microsoft Intune ile, Android for Work cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 660d0c69fc09c6ec8b82185b3808269ef4bb6852
ms.lasthandoff: 04/24/2017


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Android for Work cihazlarının kaydını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work cihazlarının yönetimini etkinleştirmek için Intune'a bir Android for Work bağlaması eklemeniz gerekir. Android for Work'ü destekleyen ancak daha önce normal Android cihazları olarak kaydedilen cihazları kaydetmek için cihazların kaydının silinmesi ve yeniden kaydedilmesi gerekir.

## <a name="add-android-for-work-binding-for-intune"></a>Intune İçin Android for Work Bağlaması Ekleme

1. **Intune’u ayarlama**<br>
Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2. **Android for Work bağlamasını yapılandırma**<br>
    Bir Intune yöneticisi olarak [Microsoft Intune yönetici konsolunu](https://manage.microsoft.com) açarak **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Android for Work**’e gidin ve Google Play’in Android for Work web sitesini açmak için **Yapılandır**’a tıklayın. Bu, tarayıcınızda yeni bir sekme açar.

3. **Google'da oturum açma**<br>
   Google'ın oturum açma sayfasında, bu kiracı için tüm Android for Work yönetim görevleriyle ilişkilendirilecek Google hesabını girin. Bu, kuruluşunuzun BT yöneticilerinin Play for Work konsolunda uygulama yönetmek ve yayımlamak için kullandığı ortak Google hesabıdır.

4. **Kuruluş ayrıntıları sağlama**<br>
   Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında *Microsoft Intune* görüntülenmelidir. Android for Work sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="specify-android-for-work-enrollment-settings"></a>Android for Work Kayıt Ayarlarını Belirtme
   Android for Work yalnızca belirli Android cihazlarda desteklenmektedir. Google'ın [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window")’ne bakın.  Android for Work destekleyen tüm cihazlar geleneksel Android yönetimini de destekler.  Intune, Android for Work destekleyen cihazların nasıl yönetileceğinizi belirtmenize olanak sağlar:

   - **Tüm cihazları Android olarak yönet** - Android for Work destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar geleneksel Android cihaz olarak kaydedilir.
   - **Desteklenen cihazları Android for Work olarak yönet** - Android for Work destekleyen tüm cihazlar Android for Work cihazlar olarak kaydedilir. Android for Work desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
   - **Yalnızca bu kullanıcı gruplarındaki desteklenen cihazları Android for Work olarak yönet** - Android for Work yönetimini sınırlı bir kullanıcı grubuna hedeflemenize olanak sağlar. Yalnızca Android for Work destekleyen bir cihaz kaydeden seçili grupların üyeleri Android for Work cihazlar olarak kaydedilir. Diğerlerinin tümü Android cihaz olarak kaydedilir. Bu, Android for Work pilot çalışmalarında kullanışlıdır.

## <a name="next-steps-for-android-for-work"></a>Android for Work için sonraki adımlar
Android for Work bağlamasını ve ayarlarını yapılandırdıktan sonra aşağıdakileri yapabilirsiniz:
- [Android for Work uygulamalarını dağıtma](android-for-work-apps.md)
- [Android for Work yapılandırma ilkeleri ekleme](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Android for Work yönetici hesabınızın bağlamasını kaldırma

Android for Work kaydı ve yönetimini kapatabilirsiniz. Intune yönetim konsolundaki **Bağlamayı Kaldır**'a tıklamak tüm kayıtlı Android for Work cihazlarının kaydını siler ve Android for Work ile Intune arasındaki ilişkiyi kaldırır.

### <a name="how-to-unbind-an-android-for-work-account"></a>Bir Android for Work hesabının bağlamasını kaldırma

1. **Android for Work bağlamasını kaldırma**<br>
    Yönetim kullanıcısı olarak [Microsoft Intune yönetici konsolunu](https://manage.microsoft.com) açarak **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Android for Work**’e gidin ve **Bağlamayı Kaldır**’a tıklayın.

2. **Android for Work bağlamasını kaldırmayı kabul etme**<br>
  Bağlamayı silmek için **Evet**’e tıklayın tüm Android for Work cihazların Intune kaydını silin.

