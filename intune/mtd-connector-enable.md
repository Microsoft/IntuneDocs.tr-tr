---
title: Microsoft Intune'da Mobile Threat Defense bağlayıcısını etkinleştirme
titleSuffix: Microsoft Intune
description: Mobile Threat Defense (MTD) iş ortağınız ile Microsoft Intune arasında bağlayıcıyı etkinleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ab9fef5a577783ebbdd512de6d00ab98483e754c
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292270"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Intune'da Mobil Threat Defense bağlayıcısını etkinleştirme

> [!NOTE] 
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Mobile Threat Defense (MTD) kurulumu sırasında, MTD iş ortağı konsolunuzdaki tehditleri sınıflandırmak için bir ilke yapılandırdınız ve Intune’da cihaz uyumluluk ilkesi oluşturdunuz. MTD iş ortağı konsolunda Intune bağlayıcısını zaten yapılandırdıysanız, şimdi Intune’da MTD bağlantısını etkinleştirebilirsiniz.

## <a name="to-enable-the-mtd-connector"></a>MTD bağlayıcısını etkinleştirmek için

1. [Azure portalı](https://portal.azure.com)’na gidin ve Intune kimlik bilgilerinizle oturum açın. Oturumunuz başarıyla açıldıktan sonra **Azure Panosu**'nu görürsünüz.

2. **Azure Panosu**'nda, soldaki menüden **Tüm hizmetler**’i seçtikten sonra, metin kutusu filtresine **Intune** yazın.

3. **Intune**'u seçin; **Intune Panosu** açılır.

4. **Intune Panosunda**, **Cihaz uyumluluğu**’nu, ardından **Mobile Threat Defense**’i **Kurulum** bölümü altında seçin.

5. **Mobile Threat Defense** bölmesinde **Ekle**’yi seçin.

6. Açılan listeden MTD çözümünü **Kurulacak Mobile Threat Defense bağlayıcısı** olarak seçin.

    ![Intune Azure portalında MTD kurulumu](./media/enable-mtd-connector-1.png)

7. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin. Görünen geçişli seçenekler MTD iş ortağına bağlı olarak değişir.

## <a name="mtd-toggle-options"></a>MTD geçiş seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi MTD geçiş seçeneklerini etkinleştirmeniz gerektiğine karar verebilirsiniz. Daha fazla ayrıntı aşağıdadır:

- **Bağlan: Android 4.1 + cihazları [MTD iş ortağı adı] for Work mtd'ye Bağla**: Bu seçeneği etkinleştirdiğinizde, Android 4.1 + olabilir cihazların raporlama güvenlik riskini Intune'a geri.
    - **Veri alınmazsa uyumsuz olarak işaretle**: Intune veri hakkında bu platformdaki bir cihaz hakkında MTD iş ortağından almazsa cihazın uyumsuz olarak değerlendirin.
<br></br>
- **İOS 8.0 + cihazları, [MTD iş ortağı adı] for Work MTD'ye Bağla**: Bu seçeneği etkinleştirdiğinizde, iOS 8.0 + cihazların güvenlik riskini Intune'a geri bildirimi olabilir.
    - **Veri alınmazsa uyumsuz olarak işaretle**: Intune veri hakkında bu platformdaki bir cihaz hakkında MTD iş ortağından almazsa cihazın uyumsuz olarak değerlendirin.
<br></br>
- **İOS cihazları için uygulama eşitlemeyi etkinleştir**: Bu mobil tehdit savunması iş ortağının tehdit analizi amacıyla kullanılmak üzere ıntune'dan iOS uygulamalarının meta verilerini istemesine izin verir.

- **Desteklenmeyen işletim sistemi sürümlerini engelle**: Cihaz desteklenen en düşük sürüm'den küçük bir işletim sistemini çalıştırıyorsa engelleyin.

- **İş ortağının yanıt vermediği gün sayısı**: Intune iş ortağı bağlantısı kesildiği için yanıt vermiyor olarak değerlendirmeden önceki etkin olunmayan gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!IMPORTANT] 
> Cihaz uyumluluğunu ve koşullu erişim ilkesi kurallarını oluşturmadan önce MTD uygulamalarını ekleyip atamanız gerekir. Bu, MTD uygulamasının, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

> [!TIP]
> Intune ve MTD ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense bölmesinden görebilirsiniz.
