---
title: "Microsoft Intune’da Exchange koşullu erişimi izleme"
titlesuffix: 
description: "Intune Azure portalı üzerinden şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleyin."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 932dfe32c6df5741615d9db9f303aaee7785d3a3
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
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

-   **Genel Bakış:** İşletim Sistemi sürümü, cihaz modeli, sahibi, seri numarası, cihaz üreticisi, telefon numarası ve cihazın en son giriş yaptığı zaman gibi cihaz özelliklerini görebilirsiniz.

-   **Özellikler:** Cihazın sahibini (Kişisel veya Kurumsal) ayarlayabilirsiniz.

-   **Donanım:** Genel Bakış’ta gördüğünüz bilgileri, ayrıca depolama bilgileri (toplam alan ve boş alan), sistem kapatma, ağ ayrıntıları, ağ hizmeti ve diğer koşullu erişim engelleme ayrıntılarını sunar.

-   **Bulunan Uygulamalar:** Cihazınıza yüklü olan tüm uygulamaları gösterir. Ayrıca yüklü uygulamaların listesini .CSV biçiminde dışa aktarabilirsiniz.

-   **Uyumluluk:** Tüm cihaz uyumluluk ilkesi ayrıntılarını gösterir.

-   **Cihaz Yapılandırması:** Tüm cihaz yapılandırma ayrıntılarını gösterir.

-   **Exchange Erişimi:** Burada cihazın koşullu erişim ilkeleri uygulandıktan sonraki durumu hakkında daha fazla bilgi alabilirsiniz.
