---
title: Microsoft Intune kullanarak cihazlara Office 365 uygulamalarını yükleme
titlesuffix: ''
description: Windows 10 cihazlarda Office 365 uygulamalarını yüklemeyi kolaylaştırmak için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11f1a48b5b2dcff421603dd4538ff054d174fe66
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223416"
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Microsoft Intune ile Office 365 uygulamalarını Windows 10 cihazlara atama

Bu uygulama türü, yönettiğiniz Windows 10 cihazlara Office 365 uygulamaları atamanızı kolaylaştırır. Ayrıca, lisanslarına sahip olmanız kaydıyla Microsoft Project Online masaüstü istemcisi ve Office 365 için Microsoft Visio Pro için de uygulama yükleyebilirsiniz. Intune konsolundaki uygulamalar listesinde tek bir girdi olarak görüntülenmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

>[!IMPORTANT]
>Bu Office yükleme yöntemi, yalnızca cihazda başka Microsoft Office sürümleri yüklü olmadığında desteklenir.

- Bu uygulamaları dağıtacağınız cihazların Windows 10 Creators Update veya üzerini çalıştırıyor olması gerekir.
- Intune, yalnızca Office 365 paketinden Office uygulamaları eklemeyi destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa yükleme başarısız olabilir ve kullanıcılar kaydedilmeyen dosyalardaki veriler kaybedebilir.
- Bu yükleme yöntemi Windows 10S, Windows Home, Windows Team, Windows Holographic veya Windows Holographic for Business çalıştıran cihazlarda desteklenmez.
- Intune, daha önce Intune ile Office 365 uygulamalarını dağıttığınız bir cihaza Microsoft Mağazası’ndan Office 365 masaüstü uygulamalarının (Office Centennial uygulamaları olarak bilinir) yüklenmesini desteklemez. Bu yapılandırmayı yüklerseniz veri kaybına veya bozulmasına neden olabilir.
- Birden fazla gerekli veya kullanılabilir uygulama ataması aynı anda çalışmaz. Bir uygulama ataması, kendinden önce yüklenmiş diğer uygulama atamalarının üzerine yazar. Örneğin ilk Office uygulamaları kümesi Word’ü barındırıyor ve sonraki barındırmıyorsa, Word kaldırılır. Bu koşul Visio ve Project uygulamaları için geçerli değildir.


## <a name="get-started"></a>Başlarken

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm Hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükü bölmesindeki **Yönet**'in altında **Uygulamalar**’ı seçin.
5. **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesindeki **Uygulama türü** listesinde, **Office 365 Office**'in altında **Windows 10**'u seçin.

Böylece uygulama paketini yapılandırabilirsiniz.

## <a name="configure-the-app-suite"></a>Uygulama paketini yapılandırma

Cihazlara atamak istediğiniz Office uygulamalarını seçin.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketini Yapılandır**’ı seçin.
2. **Uygulama Paketini Yapılandır** bölmesinde, cihazlara atamak istediğiniz standart Office uygulamalarını seçin.  
    Ayrıca, lisanslarına sahip olmanız kaydıyla Microsoft Project Online masaüstü istemcisi ve Office 365 Microsoft Visio Pro için uygulama yükleyebilirsiniz.
3. **Tamam**’ı seçin.

>[!IMPORTANT]
> Uygulama paketini oluşturduktan sonra paketin özelliklerini düzenleyemezsiniz. Farklı özellikler yapılandırmak için uygulama paketini silin ve yeni bir tane oluşturun.

## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma

Bu adımda, uygulama paketi hakkında bilgi sağlarsınız. Bu bilgiler, Intune'da uygulama paketini bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı'nda paketi bulması kolaylaşır.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketi Bilgileri**’ni seçin.
2. **Uygulama Paketi Bilgileri** bölmesinde aşağıdakileri yapın:
    - **Paket Adı**: Uygulama paketinin Şirket Portalı’nda görüntülenen adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket Açıklaması**: Uygulama paketi için bir açıklama girin. Örneğin dahil etmek üzere seçtiğiniz uygulamaları listeleyebilirsiniz.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Bu ayar, kullanıcıların şirket portalına göz atarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin, örneğin *İK departmanı*.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
3. **Tamam**’ı seçin.

## <a name="configure-app-settings"></a>Uygulama ayarlarını yapılandırma

Bu adımda, uygulama paketi için yükleme seçeneklerini yapılandırın. Pakete eklediğiniz tüm uygulamalar için bu ayarlar uygulanır.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketi Ayarları**’nı seçin.
2. **Uygulama Paketi Ayarları** bölmesinde aşağıdakileri yapın:
    - **Office sürümü**: Office’in hangi sürümünü (32 bit veya 64 bit) atamak istediğinizi seçin. 32 bit sürümünü hem 32 bit hem de 64 bit cihazlara yükleyebilirsiniz ancak 64 bit sürümünü yalnızca 64 bit cihazlara yükleyebilirsiniz.
    - **Güncelleştirme Kanalı**: Office’in cihazlarda nasıl güncelleştirileceğini seçin. Çeşitli güncelleştirme kanalları hakkında bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Aşağıdakilerden birini seçin:
        - **Aylık**
        - **Aylık (Hedeflenen)**
        - **Yarı Yıllık**
        - **Yarı Yıllık (Hedeflenen)**
    - **Uygulama son kullanıcı lisans sözleşmesini otomatik kabul edin**: Son kullanıcıların lisans sözleşmesini kabul etmesinin gerekli olmasını istemiyorsanız bunu seçin. Ardından Intune, sözleşmeyi otomatik olarak kabul eder.
    - **Paylaşımlı bilgisayar etkinleştirme kullanın**: Birden çok kullanıcı tek bir bilgisayarı kullanıyorsa bu seçeneği belirtin. Daha fazla bilgi için bkz. Office 365 için paylaşılan bilgisayar etkinleştirmeye genel bakış.
    - **Diller**: Office, son kullanıcının bilgisayarında Windows ile yüklenmiş olan tüm dillerde otomatik olarak yüklenir. Uygulama paketiyle birlikte ilave diller yüklemek istiyorsanız bunu seçin.

>[!IMPORTANT]
> Uygulama paketini oluşturduktan sonra paketin özelliklerini düzenleyemezsiniz. Farklı özellikler yapılandırmak için uygulama paketini silin ve yeni bir tane oluşturun.

## <a name="finish-up"></a>Bitirme

İşiniz bittiğinde, **Uygulama Ekle** bölmesinde **Ekle**’yi seçin. Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir.

## <a name="errors-during-installation-of-the-app-suite"></a>Uygulama paketinin yüklenmesi sırasında karşılaşılan hatalar

Karşınıza çıkabilecek yaygın hata kodları ve anlamları, aşağıdaki tablolarda listelenmiştir.

### <a name="status-for-office-csp"></a>Office CSP durumu

||||
|-|-|-|
|Durum|Aşama|Description|
|1460 (ERROR_TIMEOUT)|İndir|Office Dağıtım Aracı’nı indirme başarısız|    
|13 (ERROR_INVALID_DATA)|-|İndirilen Office Dağıtım Aracı’nın imzası doğrulanamıyor|
|CertVerifyCertificateChainPolicy hata kodu|-|İndirilen Office Dağıtım Aracı için sertifika denetimi başarısız|    
|997|Süren İş|Yükleniyor|
|0|Yükleme sonrası|Yükleme başarılı|    
|1603 (ERROR_INSTALL_FAILURE)|-|Önkoşul denetimi başarısız, örneğin:<ul><li>SxS (2016 MSI yüklüyken yüklenmeye çalışıldı)</li><li>Sürüm uyumsuzluğu</li><li>Diğerleri</li></ul>|  
|0x8000ffff (E_UNEXPECTED)|-|Makinede Tıkla-Çalıştır Office yokken kaldırılmaya çalışıldı|     
|17002|-|Senaryoyu tamamlama başarısız (yükleme). Olası nedenler:<ul><li>Yükleme kullanıcı tarafından iptal edildi</li><li>Yükleme, başka bir yükleme tarafından iptal edildi</li><li>Yükleme sırasında disk alanı tükendi</li><li>Bilinmeyen dil kimliği</li></ul>|
|17004|-|Bilinmeyen SKU’lar|   


### <a name="office-deployment-tool-error-codes"></a>Office Dağıtım Aracı hata kodları

|||||
|-|-|-|-|
|Senaryo|Dönüş kodu|Kullanıcı Arabirimi|Not|
|Etkin bir Tıkla-Çalıştır yükleme yokken kaldırma çabası|-2147418113, 0x8000ffff veya 2147549183|Hata Kodu: 30088-1008<br>Hata Kodu: 30125-1011 (404)|Office Dağıtım Aracı|
|MSI sürümü yüklü olduğunda yükleyin|1603|-|Office Dağıtım Aracı|
|Yükleme, kullanıcı veya başka bir yükleme tarafından iptal edildi|17002|-|Tıkla-çalıştır|
|32 bit yüklü olan bir cihaza 64 bit yüklemeyi deneyin.|1603|-|Office Dağıtım Aracı dönüş kodu|
|Bilinmeyen bir SKU yüklemeyi deneyin (yalnızca geçerli SKU’lardan geçmemiz gerektiğinden, Office CSP için yasal bir kullanım durumu değildir)|17004|-|Tıkla-çalıştır|
|Yetersiz alan|17002|-|Tıkla-çalıştır|
|Tıkla-çalıştır istemci başlatılamadı (beklenmeyen)|17000|-|Tıkla-çalıştır|
|Tıkla-çalıştır istemci, senaryoyu sıraya alamadı (beklenmeyen)|17001|-|Tıkla-çalıştır|

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamaları seçtiğiniz gruplara atamak için bkz. [Uygulamaları gruplara atama](/intune-azure/manage-apps/deploy-apps).
