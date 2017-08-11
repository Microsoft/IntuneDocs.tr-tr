---
title: "Intune’u kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlara yükleme"
titleSuffix: Intune on Azure
description: "Windows 10 cihazlarda Office 365 uygulamalarını yüklemeyi kolaylaştırmak için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a97e58f1d108932e44b0b4e36bda5a30b7a90da
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Microsoft Intune ile Office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlara atama

Bu uygulama türü, yönettiğiniz Windows 10 cihazlara Office 365 ProPlus 2016 uygulamaları atamanızı kolaylaştırır. Ayrıca, lisanslarına sahip olmanız kaydıyla Microsoft Project Online masaüstü istemcisi ve Office 365 için Microsoft Visio Pro için de uygulama yükleyebilirsiniz. Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görünmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

>[!IMPORTANT]
>Bu Office yükleme yöntemi, yalnızca cihazda başka Microsoft Office sürümleri yüklü olmadığında desteklenir.

- Bu uygulamaları dağıtacağınız cihazların Windows 10 Creators Update veya üzerini çalıştırıyor olması gerekir.
- Intune, yalnızca Office 365 ProPlus 2016 paketinden Office uygulamaları eklemeyi destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa kaydedilmeyen dosyalardaki veriler kaybedilebilir.
- Bu yükleme yöntemi, Windows 10S cihazlarda desteklenmez.
- Bu uygulama türünü Uygun olarak atar ve farklı atamaları birden çok kullanıcıya hedeflerseniz kullanıcılar yalnızca son hedeflenen atamayı görür.


## <a name="get-started"></a>Başlarken

1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3.  **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4.  **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5.  Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6.  **Uygulama ekle** dikey penceresinde **Office 365 ProPlus Suite (Windows 10)**’u seçin.

## <a name="configure-the-app-suite"></a>Uygulama paketini yapılandırma

Bu adımda, cihazlara atamak istediğiniz Office uygulamalarını seçin.

1.  **Uygulama ekle** dikey penceresinde **Uygulama Paketini Yapılandır**’ı seçin.
2.  **Uygulama Paketini Yapılandır** dikey penceresinde, cihazlara atamak istediğiniz standart Office uygulamalarını seçin. Ayrıca, lisanslarına sahip olmanız kaydıyla Microsoft Project Online masaüstü istemcisi ve Office 365 Microsoft Visio Pro için uygulama yükleyebilirsiniz.
3.  Bitirdiğinizde, **Tamam**’a tıklayın.

>[!IMPORTANT]
> Uygulama paketini oluşturduktan sonra paketin özelliklerini düzenleyemezsiniz. Farklı özellikler yapılandırmak için uygulama paketini silin ve yeni bir tane oluşturun.

## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma

Bu adımda, uygulama paketi hakkında bilgi sağlayın. Bu bilgiler, Intune konsolunda paketi bulmanıza yardımcı olur ve son kullanıcıların Şirket Portalı uygulamasında paketi bulması kolaylaşır.

1.  **Uygulama Ekle** dikey penceresinde **Uygulama Paketi Bilgileri**’ni seçin.
2.  **Uygulama Paketi Bilgileri** dikey penceresinde aşağıdaki bilgileri belirtin: 
    - **Paket Adı** - Uygulama paketinin şirket portalında görüntülenen adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket Açıklaması** - Uygulama paketi için bir açıklama girin. Örneğin dahil etmek üzere seçtiğiniz uygulamaları listeleyebilirsiniz.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Kategori** - İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Kategorileri kullanmak, kullanıcıların şirket portalına gözatarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle** - Uygulama paketini, kullanıcılar uygulamalara gözatarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Simge Yükle** - Kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
3.  Bitirdiğinizde, **Tamam**’a tıklayın.

## <a name="configure-app-settings"></a>Uygulama ayarlarını yapılandırma

Bu adımda, uygulama paketi için yükleme seçeneklerini yapılandırın. Pakete eklenen tüm uygulamalar için bu ayarlar uygulanır.

1.  **Uygulama ekle** dikey penceresinde **Uygulama Paketi Ayarları**’nı seçin.
2.  **Uygulama Paketi Ayarları** dikey penceresinde aşağıdaki bilgileri belirtin: 
    - **Office sürümü** - Office’in hangi sürümünü atamak istediğinizi seçin, 32 bit veya 64 bit. 32 bit sürümünü hem 32 bit hem de 64 bit cihazlara yükleyebilirsiniz ancak 64 bit sürümü yalnızca 64 bit cihazlara yüklenebilir.
    - **Güncelleştirme Kanalı** - Office’in cihazlarda nasıl güncelleştirileceğini seçin. Farklı güncelleştirme kanalları hakkında bilgi için bkz. Office 365 ProPlus güncelleştirme kanallarına genel bakış. Aşağıdakilerden birini seçin: 
        - **Geçerli**
        - **Gecikmeli**
        - **Geçerli Kanalın İlk Sürümü**
        - **Gecikmeli Kanalın İlk Sürümü**
    - **Uygulama son kullanıcı lisans sözleşmesini otomatik olarak kabul et** - Son kullanıcıların lisans sözleşmesini kabul etmesini gerekli kılmak istemiyorsanız bunu seçin. Ardından Intune, sözleşmeyi otomatik olarak kabul eder.
    - **Paylaşılan bilgisayar etkinleştirmeyi kullan** - Paylaşılan bilgisayar etkinleştirme, birden çok kullanıcı tek bir bilgisayarı paylaşıyorsa kullanılır. Daha fazla bilgi için bkz. Office 365 ProPlus için paylaşılan bilgisayar etkinleştirmeye genel bakış.
    - **Diller** - Office, son kullanıcının bilgisayarında Windows ile yüklenen tüm dillerde otomatik olarak yüklenir. Uygulama paketiyle birlikte ilave diller yüklemek istiyorsanız bunu seçin.

>[!IMPORTANT]
> Uygulama paketini oluşturduktan sonra paketin özelliklerini düzenleyemezsiniz. Farklı özellikler yapılandırmak için uygulama paketini silin ve yeni bir tane oluşturun.

## <a name="finish-up"></a>Bitirme

İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Kaydet**’i seçin. Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir.

## <a name="error-codes-when-installing-the-app-suite"></a>Uygulama paketini yüklerken çıkabilecek hata kodları

Karşınıza çıkabilecek hata kodları ve anlamları, aşağıdaki tabloda listelenmiştir.

### <a name="status-for-office-csp"></a>Office CSP durumu: 

||||
|-|-|-|
|Durum|Aşama|Açıklama|
|1460 (ERROR_TIMEOUT)|İndir|Office Dağıtım Aracı’nı indirme başarısız|    
|13 (ERROR_INVALID_DATA)|-|İndirilen Office Dağıtım Aracı’nın imzası doğrulanamıyor| 
|CertVerifyCertificateChainPolicy hata kodu|-|İndirilen Office Dağıtım Aracı için sertifika denetimi başarısız|    
|997|Süren İş|Yükleniyor| 
|0|Yükleme sonrası|Yükleme başarılı|    
|1603 (ERROR_INSTALL_FAILURE)|-|Önkoşul denetimi başarısız, örneğin:<br>- SxS (2016 MSI yüklüyken yüklenmeye çalışıldı)<br>- sürüm uyumsuzluğu<br>- vb.|     
|0x8000ffff (E_UNEXPECTED)|-|Makinede Tıkla-Çalıştır Office yokken kaldırılmaya çalışıldı.|    
|17002|-|Senaryoyu tamamlama başarısız (yükleme). Olası nedenler:<br>- Yükleme kullanıcı tarafından iptal edildi<br>- Yükleme başka bir yükleme tarafından iptal edildi<br>- Yükleme sırasında disk alanı tükendi<br>- Bilinmeyen dil kimliği| 
|17004|-|Bilinmeyen SKU’lar|   


### <a name="office-deployment-tool-error-codes"></a>Office Dağıtım Aracı Hata Kodları

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

Artık seçtiğiniz gruplara uygulamaları atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](/intune-azure/manage-apps/deploy-apps).

             


