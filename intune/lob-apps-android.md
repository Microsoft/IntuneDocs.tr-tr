---
title: "Android iş kolu uygulamalarını Microsoft Intune’a ekleme"
titlesuffix: 
description: "Android iş kolu (LOB) uygulamalarını Microsoft Intune’a eklemeyi öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f336fb295dba396dad3a399aafc17435edb70b3
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Android iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından Intune'a eklediğiniz uygulamadır. Bu tür uygulamalar genellikle şirket içinde yazılanlardır. Intune LOB uygulamasını kullanıcıların cihazlarına yükler. 

> [!Note]
> Google Play for Work mağazasındaki iş kolu (LOB) uygulamaları hakkında daha fazla bilgi edinmek için, bkz. [Google Play for Work mağazasından bir iş kolu uygulaması ile çalışma](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1---specify-the-software-setup-file"></a>1. Adım - Yazılım kurulum dosyasını belirtme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2---configure-the-app-package-file"></a>Adım 2 - Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi dosyası**’nı seçin.
2. **Uygulama paketi dosyası** bölmesinde gözat düğmesini seçin ve **.apk** uzantısına sahip Android yükleme dosyasını seçin.
3. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="step-3---configure-app-information"></a>Adım 3 - Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** - Şirket portalında görüntülenmek üzere bir uygulama adı girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Şirket portalında kullanıcılara görüntülenmek üzere bir uygulama açıklaması girin.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Minimum İşletim Sistemi** - Listeden uygulamanın yüklenebileceği minimum işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Uygulama sürümünü yoksay** - Uygulama, uygulama geliştiricisi tarafından otomatik olarak güncelleştiriliyorsa **Evet** olarak ayarlayın.
    - **Kategori** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Böylelikle, şirket portalına göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** - Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülen simgedir.
3. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="step-4---finish-up"></a>Adım 4 - Bitirme

1. **Uygulama ekle** bölmesinde uygulama ayrıntılarınızı doğrulayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>5. Adım - Bir iş kolu uygulamasını güncelleştirme

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Yeni bir APK dosyasını cihaza başarılı bir şekilde dağıtmak için Intune hizmetinde APK paketinizdeki AndroidManifest.xml dosyasında android: versionCode dizesini artırmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Cihaz ve uygulama yaşam döngülerine genel bakış](introduction-device-app-lifecycles.md)
