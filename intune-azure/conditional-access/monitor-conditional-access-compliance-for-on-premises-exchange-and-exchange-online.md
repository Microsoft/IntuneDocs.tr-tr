---
title: "Şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleme"
titleSuffix: Intune Azure preview
description: "Intune Azure portalı üzerinden şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleme"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 9d5521de8709bf232dedfeeb1874f8db1898f2d0
ms.lasthandoff: 04/26/2017


---

# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune-azure-preview"></a>Intune Azure önizlemede şirket içi Exchange ve Exchange Online için koşullu erişim uyumluluğunu izleme

Intune 1704 sürümü ve sonrasında yöneticiler, şirket içi Exchange Bağlayıcısı veya Intune hizmetten hizmete bağlayıcısı (Exchange Online bağlayıcısı) aracılığıyla Intune ile eşitlenen Exchange ActiveSync cihaz kayıtlarıyla ilgili raporlama bilgilerini görebilmektedir. Koşullu erişim uyumluluk raporlaması, farklı eşitleme durumları olan cihazların bir özetini sunar:

-   **İzin ver**

-   **Engelle**

-   **Karantina**

## <a name="to-monitor-conditional-access-compliance"></a>Koşullu erişim uyumluluğunu izlemek için

1.  [Azure Portal](https://portal.azure.com/)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Oturumunuz başarıyla açıldıktan sonra **Azure Panosu**'nu görürsünüz.

3.  Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

4.  **Intune**’u seçin, **Intune Panosu**’nu görürsünüz.

5.  **Koşullu Erişim**’i, ardından **Genel Bakış**’ı seçin.

6.  Koşullu erişim uyumluluk raporunuzu görüntülemek için, grafikte üç alandan birini (**Engellenen**, **Karantina** ve **İzin Verilen**) seçin.

    ![Koşullu Erişim Panosu](../media/CA-reporting-intune-1.png)

Üç alandan birini seçtikten sonra izin verilen, engellenen veya karantinada olan cihazlar hakkında daha fazla bilgi görebilirsiniz.

Ayrıca, daha fazla bilgi için belirli cihazlarda detaya gidebilirsiniz. Örneğin aşağıdaki görüntüde seçili olan cihaz engellenmiştir. Intune, kurumsal verilerinizi koşullu erişim uyumluluk raporu dikey penceresinden kaldırma seçeneği sunar.

![Koşullu erişim cihaz ayrıntısı raporlama](../media/CA-reporting-intune-3.png)

Cihaz ayrıntıları dikey penceresinde, daha fazla bilgi görebilirsiniz:

-   **Genel Bakış:** İşletim Sistemi sürümü, cihaz modeli, sahibi, seri numarası, cihaz üreticisi, telefon numarası ve cihazın en son giriş yaptığı zaman gibi cihaz özelliklerini görebilirsiniz.

-   **Özellikler:** Cihazın sahibini (Kişisel veya Kurumsal) ayarlayabilirsiniz.

-   **Donanım:** Genel Bakış’ta gördüğünüz bilgileri, ayrıca depolama bilgileri (toplam alan ve boş alan), sistem kapatma, ağ ayrıntıları, ağ hizmeti ve diğer koşullu erişim engelleme ayrıntılarını sunar.

-   **Bulunan Uygulamalar:** Cihazınıza yüklü olan tüm uygulamaları gösterir. Ayrıca yüklü uygulamaların listesini .CSV biçiminde dışa aktarabilirsiniz.

-   **Uyumluluk:** Tüm cihaz uyumluluk ilkesi ayrıntılarını gösterir.

-   **Cihaz Yapılandırması:** Tüm cihaz yapılandırma ayrıntılarını gösterir.

-   **Exchange Erişimi:** Burada cihazın koşullu erişim ilkeleri uygulandıktan sonraki durumu hakkında daha fazla bilgi alabilirsiniz.

