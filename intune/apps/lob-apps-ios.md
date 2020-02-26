---
title: Microsoft Intune’a bir iOS iş kolu uygulaması ekleme
titleSuffix: ''
description: Microsoft Intune için bir iOS iş kolu (LOB) uygulaması ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 507c7ecff9715ebf9f24567c735592f3f255ccc9
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609166"
---
# <a name="add-an-ios-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir iOS iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir iOS iş kolu uygulamasını Microsoft Intune’a eklemek için bu makaledeki bilgileri kullanın. İş kolu (LOB) uygulaması, bir IPA uygulama yükleme dosyasından Intune 'a eklediğiniz bir uygulamadır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Önce iOS Geliştirici kurumsal programı 'na katılmanız gerekir. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. [Apple Web sitesi](https://developer.apple.com/programs/ios/enterprise/).

> [!NOTE]
> iOS kullanıcıları, Stocks ve Harita gibi bazı yerleşik iOS uygulamalarını kaldırabilir. Ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.
>
> iOS LOB uygulamaları, uygulama başına 4 GB üst sınıra sahiptir.

> [!NOTE]
> Paket tanımlayıcıları (örneğin, *com. contoso. app*), bir uygulamanın benzersiz tanımlayıcıları olacak şekilde tasarlanmıştır. Örneğin, test amacıyla üretim sürümünün yanına bir LOB uygulamasının beta sürümünü yüklemek için beta sürümü farklı bir benzersiz tanımlayıcıya sahip olmalıdır (örneğin, *com. contoso. app-Beta*). Aksi halde beta sürümü üretimle örtüşüyor ve yükseltme olarak değerlendirilir. . İpa dosyasının yeniden adlandırılması bu davranışı etkilemez.

## <a name="select-the-app-type"></a>Uygulama türünü seçin

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, **diğer** uygulama türleri altında **iş kolu uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.

## <a name="step-1---app-information"></a>1\. adım-uygulama bilgileri

### <a name="select-the-app-package-file"></a>Uygulama paketi dosyasını seçin

1. **Uygulama Ekle** bölmesinde **uygulama paketi dosyası seç**' e tıklayın. 
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Sonra, **. ipa**uzantısına sahip bir iOS yükleme dosyası seçin.
   Uygulama ayrıntıları görüntülenir.
3. İşiniz bittiğinde uygulamayı eklemek için **uygulama paketi dosyası** bölmesinde **Tamam** ' ı seçin.

### <a name="set-app-information"></a>Uygulama bilgilerini ayarla

1. **Uygulama bilgileri** sayfasında uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama açıklamasını girin. Açıklama Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayıncısının adını girin.
    - **En Düşük İşletim Sistemi**: Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
2. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.

## <a name="step-2---select-scope-tags-optional"></a>2\. adım-kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).

1. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. 
2. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.

## <a name="step-3---assignments"></a>3\. adım-atamalar

1. **Gerekli**, **Kayıtlı cihazlar için kullanılabilir**veya uygulama için Grup atamalarını **Kaldır** ' ı seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md) ve [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md).
2. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. 

## <a name="step-4---review--create"></a>4\. adım-Inceleme ve oluşturma

1. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
2. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

    İş kolu uygulaması için **genel bakış** dikey penceresi görüntülenir.

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
