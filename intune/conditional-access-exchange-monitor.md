---
title: Microsoft Intune Exchange koşullu erişimi izleme | Microsoft Intune
description: Intune Azure portalı üzerinden şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ebca668ba3e02ec6088bb72370d7d5061241627
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394934"
---
# <a name="monitor-conditional-access-compliance-for-exchange-on-premises-in-intune"></a>Exchange şirket içi için ıntune koşullu erişim uyumluluğunu izleme

Intune yöneticileri için şirket içi Exchange bağlayıcısını Intune ile eşitlenen Exchange ActiveSync cihaz kayıtlarıyla ilgili raporlama görüntüleyebilirsiniz. Koşullu erişim uyumluluk raporlaması, farklı eşitleme durumları olan cihazların bir özetini sunar:

- **İzin ver**

- **Engelle**

- **Karantina**

## <a name="to-monitor-conditional-access-compliance"></a>Koşullu erişim uyumluluğunu izlemek için

1. Oturum [Intune](https://aka.ms/intuneportal)ve Git **koşullu erişim**, ardından **genel bakış**.

2. Koşullu erişim uyumluluk raporunuzu görüntülemek için, grafikte üç alandan birini (**İzin Verilen**, **Engellenen** ve **Karantina**) seçin.

   ![Koşullu Erişim Panosunun resmi](./media/CA-reporting-intune-1.png)

Üç alandan birini seçtikten sonra izin verilen, engellenen veya karantinada olan cihazlar hakkında daha fazla bilgi görebilirsiniz.

Ayrıca, daha fazla bilgi için belirli cihazlarda detaya gidebilirsiniz. Örneğin aşağıdaki resimde seçili olan cihaz engellenmiştir. Intune, kurumsal verilerinizi koşullu erişim uyumluluk raporu bölmesinden kaldırma seçeneği sunar.

![Koşullu erişim cihaz ayrıntısı raporu resmi](./media/CA-reporting-intune-3.png)

Cihaz ayrıntıları bölmesinde, daha fazla bilgi görebilirsiniz:

- **Genel Bakış:** Gibi cihaz özelliklerini görebilirsiniz: İşletim sistemi sürümü, cihaz modeli, sahipliği, seri numarası, cihaz üreticisi, telefon numarası ve son iade cihaz saat.

- **Özellikler:** Cihaz sahipliği (Kişisel veya Kurumsal) ayarlayabilirsiniz.

- **Donanım:** Sistem kutusu, ağ ayrıntıları, ağ hizmeti ve daha fazla koşullu erişim engelleme ayrıntılarını genel bakış ve depolama ayrıntıları (toplam alan ve boş alan), ayrıca bkz bilgilere yer verilmiştir.

- **Bulunan uygulamalar:** Bu, cihazınıza yüklü tüm uygulamaları gösterir. Ayrıca yüklü uygulamaların listesini .CSV biçiminde dışa aktarabilirsiniz.

- **Uyumluluk:** Bu, tüm cihaz uyumluluk ilkesi ayrıntılarını gösterir.

- **Cihaz yapılandırması:** Bu, tüm cihaz yapılandırma ayrıntılarını gösterir.

- **Exchange erişimi:** Burada, cihaz durumu hakkında daha fazla koşullu erişim ilkeleri uygulandıktan sonra öğrenebilirsiniz.
