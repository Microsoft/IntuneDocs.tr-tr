---
title: Microsoft Intune’a bir iOS iş kolu uygulaması ekleme
titleSuffix: ''
description: Microsoft Intune için bir iOS iş kolu (LOB) uygulaması ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59cde9d38523c3683d56c54b66b563b7a95c49f9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731117"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir iOS iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir iOS iş kolu uygulamasını Microsoft Intune’a eklemek için bu makaledeki bilgileri kullanın. İş kolu (LOB) uygulaması, bir IPA uygulama yükleme dosyasından Intune 'a eklediğiniz bir uygulamadır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Önce iOS Geliştirici kurumsal programı 'na katılmanız gerekir. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [Apple Web sitesi](https://developer.apple.com/programs/ios/enterprise/).

>[!NOTE]
>iOS kullanıcıları, Stocks ve Harita gibi bazı yerleşik iOS uygulamalarını kaldırabilir. Ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.
>
>iOS LOB uygulamaları, uygulama başına 4 GB üst sınıra sahiptir.

## <a name="step-1-specify-the-software-setup-file"></a>1\. Adım: Yazılım kurulum dosyasını belirtme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2-configure-the-app-package-file"></a>2\. Adım: Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra **.ipa** uzantısına sahip bir iOS yükleme dosyası seçin.
3. İşiniz bittiğinde **Tamam**’a tıklayın.


## <a name="step-3-configure-app-information"></a>3\. Adım: Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **En Düşük İşletim Sistemi**: Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

## <a name="step-4-finish-up"></a>4\. Adım: Bitirme

1. **Uygulama ekle** bölmesinde uygulama ayrıntılarınızı doğrulayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

Oluşturduğunuz uygulama artık uygulamalar listesinde görünür. Bu listede, seçtiğiniz gruplara uygulamaları atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

> [!NOTE]
> iOS LOB uygulamaları için profiller sağlanırken, bunların süresi dolmadan önce 30 günlük bir bildirim süresi vardır.

## <a name="step-5-update-a-line-of-business-app"></a>5\. Adım: Bir iş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

İş kolu uygulamasına yönelik güncelleştirme otomatik olarak yüklenir.

> [!NOTE]
> Intune hizmeti için yeni bir IPA dosyasını cihaza başarıyla dağıtmak için IPA paketinizdeki Info.plist dosyasındaki `CFBundleVersion` dizesini artırmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görünür. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md) makalesine bakın.

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. [Cihaz ve uygulama yaşam döngülerine genel bakış](../fundamentals/device-lifecycle.md) makalesine bakın.
