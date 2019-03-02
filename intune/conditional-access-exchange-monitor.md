---
title: Microsoft Intune Exchange koşullu erişimi izleme | Microsoft Intune
description: Intune Azure portalı üzerinden şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0078a8abfa6675d7df49b62b347fd5ede2a06d03
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233827"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Intune'da şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleme

Intune 1704 sürümü ve sonrasında yöneticiler, şirket içi Exchange Bağlayıcısı veya Intune hizmetten hizmete bağlayıcısı (Exchange Online bağlayıcısı) aracılığıyla Intune ile eşitlenen Exchange ActiveSync cihaz kayıtlarıyla ilgili raporlama bilgilerini görebilmektedir. Koşullu erişim uyumluluk raporlaması, farklı eşitleme durumları olan cihazların bir özetini sunar:

-   **İzin ver**

-   **Engelle**

-   **Karantina**

## <a name="to-monitor-conditional-access-compliance"></a>Koşullu erişim uyumluluğunu izlemek için

1.  [Azure Portal](https://portal.azure.com/)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Oturumunuz başarıyla açıldıktan sonra **Azure Panosu**'nu görürsünüz.

3.  Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

4.  **Intune**’u seçin, **Intune Panosu**’nu görürsünüz.

5.  **Koşullu erişim**’i, ardından **Genel bakış**’ı seçin.

6.  Koşullu erişim uyumluluk raporunuzu görüntülemek için, grafikte üç alandan birini (**İzin Verilen**, **Engellenen** ve **Karantina**) seçin.

    ![Koşullu Erişim Panosunun resmi](./media/CA-reporting-intune-1.png)

Üç alandan birini seçtikten sonra izin verilen, engellenen veya karantinada olan cihazlar hakkında daha fazla bilgi görebilirsiniz.

Ayrıca, daha fazla bilgi için belirli cihazlarda detaya gidebilirsiniz. Örneğin aşağıdaki resimde seçili olan cihaz engellenmiştir. Intune, kurumsal verilerinizi koşullu erişim uyumluluk raporu bölmesinden kaldırma seçeneği sunar.

![Koşullu erişim cihaz ayrıntısı raporu resmi](./media/CA-reporting-intune-3.png)

Cihaz ayrıntıları bölmesinde, daha fazla bilgi görebilirsiniz:

-   **Genel Bakış:** Gibi cihaz özelliklerini görebilirsiniz: İşletim sistemi sürümü, cihaz modeli, sahipliği, seri numarası, cihaz üreticisi, telefon numarası ve son iade cihaz saat.

-   **Özellikler:** Cihaz sahipliği (Kişisel veya Kurumsal) ayarlayabilirsiniz.

-   **Donanım:** Sistem kutusu, ağ ayrıntıları, ağ hizmeti ve daha fazla koşullu erişim engelleme ayrıntılarını genel bakış ve depolama ayrıntıları (toplam alan ve boş alan), ayrıca bkz bilgilere yer verilmiştir.

-   **Bulunan uygulamalar:** Bu, cihazınıza yüklü tüm uygulamaları gösterir. Ayrıca yüklü uygulamaların listesini .CSV biçiminde dışa aktarabilirsiniz.

-   **Uyumluluk:** Bu, tüm cihaz uyumluluk ilkesi ayrıntılarını gösterir.

-   **Cihaz yapılandırması:** Bu, tüm cihaz yapılandırma ayrıntılarını gösterir.

-   **Exchange erişimi:** Burada, cihaz durumu hakkında daha fazla koşullu erişim ilkeleri uygulandıktan sonra öğrenebilirsiniz.
