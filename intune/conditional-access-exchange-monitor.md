---
title: Microsoft Intune’da Exchange koşullu erişimi izleme
titlesuffix: ''
description: Intune Azure portalı üzerinden şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 20a99290d2a84c22bc2bee823d7a3bb42e43aced
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180587"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Intune'da şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleme

Intune 1704 sürümünden başlayarak, yöneticiler şirket içi Exchange Bağlayıcısı'nı veya Intune hizmetten hizmete Bağlayıcısı (Exchange aracılığıyla Intune ile eşitlenen Exchange ActiveSync cihaz kayıtlarıyla ilgili raporlama bilgilerini görebilmektedir Online Bağlayıcısı). Koşullu erişim uyumluluk raporlaması, farklı eşitleme durumları olan cihazların bir özetini sağlar:

-   **İzin ver**

-   **Engelle**

-   **Karantina**

## <a name="to-monitor-conditional-access-compliance"></a>Koşullu erişim uyumluluğunu izlemek için

1.  [Azure portalı](https://portal.azure.com/)’na gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Oturumunuz başarıyla açıldıktan sonra gördüğünüz **Azure Panosu**.

3.  Seçin **tüm hizmetleri** sol menüden yazın **Intune** metin kutusu filtresine.

4.  Seçin **Intune**, gördüğünüz **Intune Panosu**.

5.  **Koşullu erişim**’i, ardından **Genel bakış**’ı seçin.

6.  Koşullu erişim uyumluluk raporunuzu görüntülemek için, grafikte üç alandan birini (**İzin Verilen**, **Engellenen** ve **Karantina**) seçin.

    ![Koşullu Erişim Panosunun resmi](./media/CA-reporting-intune-1.png)

Üç alandan birini seçtikten sonra izin verilen, engellenen veya karantinada olan cihazlar hakkında daha fazla bilgi görebilirsiniz.

Ayrıca daha fazla ayrıntı görmek için belirli cihazlarda detaya gidebilirsiniz. Örneğin aşağıdaki resimde seçili olan cihaz engellenmiştir. Intune, kurumsal verilerinizi koşullu erişim uyumluluk raporu bölmesinden kaldırma seçeneği sunar.

![Koşullu erişim cihaz ayrıntısı raporu resmi](./media/CA-reporting-intune-3.png)

Cihaz ayrıntıları bölmesinde, daha fazla bilgi görebilirsiniz:

-   **Genel Bakış:** İşletim Sistemi sürümü, cihaz modeli, sahibi, seri numarası, cihaz üreticisi, telefon numarası ve cihazın en son giriş yaptığı zaman gibi cihaz özelliklerini görebilirsiniz.

-   **Özellikler:** Cihazın sahibini (Kişisel veya Kurumsal) ayarlayabilirsiniz.

-   **Donanım:** Genel Bakış’ta gördüğünüz bilgileri, ayrıca depolama bilgileri (toplam alan ve boş alan), sistem kapatma, ağ ayrıntıları, ağ hizmeti ve diğer koşullu erişim engelleme ayrıntılarını sunar.

-   **Bulunan Uygulamalar:** Cihazınıza yüklü olan tüm uygulamaları gösterir. Ayrıca yüklü uygulamaların listesini .CSV biçiminde dışa aktarabilirsiniz.

-   **Uyumluluk:** Tüm cihaz uyumluluk ilkesi ayrıntılarını gösterir.

-   **Cihaz Yapılandırması:** Tüm cihaz yapılandırma ayrıntılarını gösterir.

-   **Exchange Erişimi:** Burada cihazın koşullu erişim ilkeleri uygulandıktan sonraki durumu hakkında daha fazla bilgi alabilirsiniz.
