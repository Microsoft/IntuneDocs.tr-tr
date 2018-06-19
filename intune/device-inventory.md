---
title: Microsoft Intune - Azure ile cihaz ayrıntılarını görüntüleme | Microsoft Docs
description: İşletim sistemleri, depolama alanı, üretim ve modeli içeren cihaz ayrıntılarınızı görüntüleyin. Azure'da Microsoft Intune ile yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin ve TeamViewer'ı ayarlayın. Bu, yönettiğiniz cihazların envanterini görüntülemeye benzer.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34051615"
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarla ilgili olarak donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar.

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-the-device-details"></a>Cihaz ayrıntılarını görüntüleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar** > **Tüm cihazlar**’a gidin ve listelenen cihazlarınızdan birini seçip ayrıntılarını görüntüleyin:

   - **Genel Bakış**, cihazın adını gösterir ve kendi cihazını getir (KCG) cihazı olup olmadığı, ne zaman iade edildiği gibi bazı temel özellikleri listeler. **Diğer**’i seçerek yapabilecekleriniz de şu şekildedir:
     - Şirket verilerini kaldırma
     - Cihazı silme
     - Cihazı uzaktan kilitleme
     - Silme
     - Uzaktan yardım oturumu başlatma
   - **Özellikler**’i kullanarak [oluşturduğunuz bir cihaz kategorisini](device-group-mapping.md) atayabilir ve cihazın sahipliğini kişisel veya şirket olarak değiştirebilirsiniz.
   - **Donanımda** cihaz hakkında pek çok bilgi bulunur. Örneğin cihaz kimliği, işletim sistemi ve sürümü, depolama alanı, model ve üretici, koşullu erişim ayarları vb.
   - **Bulunan uygulamalar**, Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaları ve uygulama sürümlerini listeler. Uygulama listesini bir .csv dosyası olarak **Dışarı Aktarabilirsiniz**.
   - **Cihaz uyumluluğu**, atanmış tüm uyumluluk ilkelerini ve cihazın uyumlu olup olmadığını listeler.
   - **Cihaz yapılandırması**, cihaza atanmış tüm yapılandırma ilkelerini ve ilkenin başarılı olup olmadığını gösterir.

Intune, yalnızca şirkete ait cihazlarda uygulama listesi toplar. Kişisel cihazlarda uygulamalar denetlenmez. Windows 10 bilgisayarlarda, şirkete ait cihazlar için yalnızca modern uygulamalar listelenir. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazlarda kullanılan operatöre bağlı olarak, tüm uygulamalar toplanamayabilir.

|Platform|Kişiye Ait Cihazlar İçin|Şirkete Ait Cihazlar İçin|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|
|Windows 8.1 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows Phone 8|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows RT|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|iOS|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamalar|
|Mac OS|Cihazda yüklü tüm uygulamalar|Cihazda yüklü tüm uygulamalar|  
|Android|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamalar|  

## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.