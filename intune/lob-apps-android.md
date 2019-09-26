---
title: Microsoft Intune’a bir Android iş kolu uygulaması ekleme
description: Microsoft Intune için Android iş kolu (LOB) uygulaması ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5456fe2b8553c61a81a86aa72c0f34fff86fcd3c
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71303400"
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir Android iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından Intune'a eklediğiniz uygulamadır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Intune, LOB uygulamasını kullanıcının cihazına yükler. 

> [!Note]
> LOB uygulamaları ve Google Play Geliştirici Konsolu hakkında daha fazla bilgi için bkz. [Google Geliştirici Konsolu kullanılarak yönetilen Google Play özel (LOB) uygulama yayımlama](apps-add-android-for-work.md?#managed-google-play-private-lob-app-publishing-using-the-google-developer-console). 

> [!Note]
> Android for Work cihazlar için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](apps-add-android-for-work.md). 

## <a name="step-1-specify-the-software-setup-file"></a>1\. adım: Yazılım kurulum dosyasını belirtme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
3. **İstemci uygulamaları** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
4. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
5. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2-configure-the-app-package-file"></a>2\. adım: Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra **.apk** uzantısına sahip bir Android yükleme dosyası seçin.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

## <a name="step-3-configure-app-information"></a>3\. adım: Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulamanın açıklamasını girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **En düşük Işletim sistemi**: Listeden, uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulamayı şirket portalının ana sayfasında önce çıkacak şekilde görüntüleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

## <a name="step-4-finish-up"></a>Adım 4: Bitirme

1. **Uygulama ekle** bölmesinde uygulama ayrıntılarınızı doğrulayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

Oluşturduğunuz uygulama artık uygulamalar listesinde görünür. Bu listede, seçtiğiniz gruplara uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

## <a name="step-5-update-a-line-of-business-app"></a>Adım 5: İş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

Android cihazında **uygulamalar dış kaynaklardan** etkin olarak etkinleştirilmişse, bu güncelleştirme yüklenmeden önce kullanıcıya sorulur. Aksi takdirde güncelleştirme otomatik olarak yüklenir.

> [!Note]
> Yeni bir APK dosyasını cihaza başarılı bir şekilde dağıtmak için Intune hizmetinde APK paketinizdeki AndroidManifest.xml dosyasında `android:versionCode` dizesini artırmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görünür. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md) makalesine bakın.

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. [Cihaz ve uygulama yaşam döngülerine genel bakış](introduction-device-app-lifecycles.md) makalesine bakın.
