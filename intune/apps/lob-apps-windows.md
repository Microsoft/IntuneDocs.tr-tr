---
title: Microsoft Intune’a bir Windows iş kolu uygulaması ekleme
titleSuffix: ''
description: Microsoft Intune'u kullanarak Windows iş kolu (LOB) uygulaması eklemeyi öğrenin.
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
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3deb9f3c96a4c2c2de72b7016aca855f679bbd7
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755145"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir Windows iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından eklediğiniz bir uygulamadır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Aşağıdaki adımlar, Microsoft Intune'a bir Windows LOB uygulaması eklemenize yardımcı olan yönergeler sağlar.

> [!IMPORTANT]
> *. Msi* uzantısına sahip bir yükleme dosyası kullanarak Win32 uygulamaları dağıttığınızda, [Intune yönetim uzantısı](../apps/intune-management-extension.md)'nı kullanmayı düşünün. AutoPilot kaydı sırasında Win32 uygulamaları ve iş kolu uygulamaları yüklemesini karıştırırsanız, uygulama yüklemesi başarısız olabilir.  

## <a name="select-the-app-type"></a>Uygulama türünü seçin

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, **diğer** uygulama türleri altında **iş kolu uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.

## <a name="step-1---app-information"></a>1\. adım-uygulama bilgileri

### <a name="select-the-app-package-file"></a>Uygulama paketi dosyasını seçin

1. **Uygulama Ekle** bölmesinde **uygulama paketi dosyası seç**' e tıklayın. 
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Ardından, **. msi**, **. appx**veya **. appxdemeti**uzantılı bir Windows yükleme dosyası seçin.
   Uygulama ayrıntıları görüntülenir.

    > [!NOTE]
    > Windows uygulamaları için dosya uzantıları **.msi**, **.appx**, **.appxbundle**, **.msix** ve **.msixbundle**'dır.  

3. İşiniz bittiğinde uygulamayı eklemek için **uygulama paketi dosyası** bölmesinde **Tamam** ' ı seçin.

### <a name="set-app-information"></a>Uygulama bilgilerini ayarla

1. **Uygulama bilgileri** sayfasında uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama açıklamasını girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **En Düşük İşletim Sistemi**: Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
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

## <a name="update-a-line-of-business-app"></a>İş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Intune hizmetinin yeni bir APPX dosyasını cihaza başarıyla dağıtması için, APPX paketinizin AppxManifest. xml dosyasında `Version` dizesini artırmanız gerekir.

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Sürüm denetim işlemini yoksaymak için bir kendi kendini güncelleştiren MSI uygulaması yapılandırma

Sürüm denetim işlemini yoksaymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabilirsiniz.

Bazı MSI yükleyici tabanlı uygulamalar, uygulama geliştiricisi veya başka bir güncelleştirme yöntemi tarafından otomatik olarak güncelleştirilir. Otomatik olarak güncelleştirilen bu MSI uygulamaları için **Uygulama bilgileri** bölmesindeki **Uygulama sürümünü yoksay** ayarını yapılandırabilirsiniz. Bu ayarı **Evet** olarak değiştirdiğinizde Microsoft Intune, Windows istemcisinde yüklü olan uygulama sürümünü çalıştırmaz.

Bu yetenek, bir yarış durumuna girmeyi önlemek açısından kullanışlıdır. Örneğin bir uygulama, uygulama geliştiricisi ve Intune tarafından güncelleştirilirse bir yarış durumu ortaya çıkabilir. Her iki taraf da bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkar.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görünür. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md) makalesine bakın.

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Bkz. [Microsoft Intune'da uygulama yaşam döngüsüne genel bakış](app-lifecycle.md).

- Win32 uygulamaları hakkında daha fazla bilgi edinin. Bkz. [Win32 uygulama yönetimi](~/apps/apps-win32-app-management.md).
