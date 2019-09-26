---
title: Microsoft Intune’a bir Windows iş kolu uygulaması ekleme
titleSuffix: ''
description: Microsoft Intune'u kullanarak Windows iş kolu (LOB) uygulaması eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eae10cc2a7e1965d83d2c0c59d138b44eafcddf0
ms.sourcegitcommit: 3baa9965095bb874d9b8c7a3cbb4aa925ed52cae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "71303379"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Microsoft Intune’a bir Windows iş kolu uygulaması ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından eklediğiniz bir uygulamadır. Bu tür bir uygulama genellikle şirket içinde yazılmıştır. Aşağıdaki adımlar, Microsoft Intune'a bir Windows LOB uygulaması eklemenize yardımcı olan yönergeler sağlar.

## <a name="step-1-specify-the-software-setup-file"></a>1\. adım: Yazılım kurulum dosyasını belirtme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2-configure-the-app-package-file"></a>2\. adım: Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi**’ni seçin.
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra **.msi**, **.appx** veya **.appxbundle** uzantısına sahip bir Windows yükleme dosyası seçin.

    > [!NOTE]
    > Windows uygulamaları için dosya uzantıları **.msi**, **.appx**, **.appxbundle**, **.msix** ve **.msixbundle**'dır.  

1. İşiniz bittiğinde **Tamam**’a tıklayın.


## <a name="step-3-configure-app-information"></a>3\. adım: Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Uygulama sürümünü yoksay**: Uygulama geliştiricisi uygulamayı otomatik olarak güncelleştiriyorsa bunu **Evet** olarak ayarlayın. Bu seçenek, yalnızca mobil .msi uygulamalarında geçerlidir.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulamayı şirket portalının ana sayfasında önce çıkacak şekilde görüntüleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Komut satırı bağımsız değişkenleri**: İsteğe bağlı olarak, çalıştığında .msi dosyasına uygulamak istediğiniz komut satırı bağımsız değişkenleri girin.  Örneğin **/q**. Otomatik olarak kullanıldıkları için, MSIEXEC komutunu veya **/ı** veya **/x**gibi bağımsız değişkenleri eklemeyin. Daha fazla bilgi için bkz. [komut satırı seçenekleri](https://docs.microsoft.com/windows/desktop/Msi/command-line-options). . MSI dosyası için ek komut satırı seçenekleri gereklidir [Win32 App Management](apps-win32-app-management.md)kullanmayı düşünün.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na gözatarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

## <a name="step-4-finish-up"></a>Adım 4: Bitirme

1. **Uygulama ekle** bölmesinde, uygulama bilgilerini doğru yapılandırdığınızı onaylayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

## <a name="step-5-update-a-line-of-business-app"></a>Adım 5: İş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Intune hizmetinin yeni bir appx dosyasını cihaza başarıyla dağıtması için, appx paketinizin appxmanifest. xml dosyasındaki `Version` dizeyi artırmanız gerekir.
    
## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Sürüm denetim işlemini yoksaymak için bir kendi kendini güncelleştiren MSI uygulaması yapılandırma

Sürüm denetim işlemini yoksaymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabilirsiniz. 

Bazı MSI yükleyici tabanlı uygulamalar, uygulama geliştiricisi tarafından otomatik olarak güncelleştirilir. Otomatik olarak güncelleştirilen bu MSI uygulamaları için **Uygulama bilgileri** bölmesindeki **Uygulama sürümünü yoksay** ayarını yapılandırabilirsiniz. Bu ayarı **Evet** olarak değiştirdiğinizde Microsoft Intune, Windows istemcisinde yüklü olan uygulama sürümünü çalıştırmaz. 

Bu yetenek, bir yarış durumuna girmeyi önlemek açısından kullanışlıdır. Örneğin bir uygulama, uygulama geliştiricisi ve Intune tarafından güncelleştirilirse bir yarış durumu ortaya çıkabilir. Her iki taraf da bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkar.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde görünür. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. [Uygulama bilgilerini ve atamaları izleme](apps-monitor.md) makalesine bakın.

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Bkz. [Microsoft Intune'da uygulama yaşam döngüsüne genel bakış](app-lifecycle.md).
