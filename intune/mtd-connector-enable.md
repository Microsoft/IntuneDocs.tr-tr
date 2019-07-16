---
title: Microsoft Intune'da Mobile Threat Defense bağlayıcısını etkinleştirme
titleSuffix: Microsoft Intune
description: Mobile Threat Defense (MTD) iş ortağınız ile Microsoft Intune arasında bağlayıcıyı etkinleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2084ad1ec0deefd24c0d61f69d99ee11149af96
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882745"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Intune'da Mobil Threat Defense bağlayıcısını etkinleştirme

> [!NOTE] 
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Mobile Threat Defense (MTD) kurulumu sırasında, MTD iş ortağı konsolunuzdaki tehditleri sınıflandırmak için bir ilke yapılandırdınız ve Intune’da cihaz uyumluluk ilkesi oluşturdunuz. MTD iş ortağı konsolunda Intune bağlayıcısını zaten yapılandırdıysanız, şimdi Intune’da MTD bağlantısını etkinleştirebilirsiniz.

## <a name="to-enable-the-mtd-connector"></a>MTD bağlayıcısını etkinleştirmek için

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.

4. **Intune Panosunda**, **Cihaz uyumluluğu**’nu, ardından **Mobile Threat Defense**’i **Kurulum** bölümü altında seçin.

5. **Mobile Threat Defense** bölmesinde **Ekle**’yi seçin.

6. Açılan listeden MTD çözümünü **Kurulacak Mobile Threat Defense bağlayıcısı** olarak seçin.

    ![Intune Azure portalında MTD kurulumu](./media/enable-mtd-connector-1.png)

7. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin. Görünen geçişli seçenekler MTD iş ortağına bağlı olarak değişir.

## <a name="mtd-toggle-options"></a>MTD geçiş seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi MTD geçiş seçeneklerini etkinleştirmeniz gerektiğine karar verebilirsiniz. Daha fazla ayrıntı aşağıdadır:

- **Android 4.1 + cihazlarını Iş MTD için [MTD iş ortağı adı]** ' na bağlayın: Bu seçeneği etkinleştirdiğinizde, Android 4.1 + cihazların güvenlik riskini Intune 'a geri bildirimini sağlayabilirsiniz.
  - **Veri alınmadığında uyumsuz olarak işaretle**: Intune, bu platformdaki bir cihaz hakkında MTD iş ortağından veri almazsa, cihazı uyumsuz olarak değerlendirin.
<br></br>
- **İOS 8.0 + cihazlarını Work MTD için [MTD iş ortağı adı] bağlayın**: Bu seçeneği etkinleştirdiğinizde, iOS 8.0 + cihazların güvenlik riskini Intune 'a geri bildirimini sağlayabilirsiniz.
  - **Veri alınmadığında uyumsuz olarak işaretle**: Intune, bu platformdaki bir cihaz hakkında MTD iş ortağından veri almazsa, cihazı uyumsuz olarak değerlendirin.
<br></br>
- **IOS cihazları Için uygulama eşitlemesini etkinleştir**: Bu mobil tehdit savunması iş ortağının, iOS uygulamalarının Intune 'dan tehdit analizi amacıyla kullanması için meta veri istemesine izin verir.

- **Desteklenmeyen işletim sistemi sürümlerini engelle**: Cihazın desteklenen en düşük sürümden daha düşük bir işletim sistemi çalıştırıyorsa engelleyin.

- **İş ortağının yanıt vermemesine kadar geçen gün sayısı**: Bağlantı kaybolduğu için Intune 'un iş ortağının yanıt vermemesine neden olmadan önce geçen işlem yapılmayan gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!IMPORTANT] 
> Mümkün olduğunda, cihaz uyumluluğunu ve koşullu erişim ilkesi kurallarını oluşturmadan önce MTD uygulamalarını eklemenizi ve atamanızı öneririz. Bu, MTD uygulamasının, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce, son kullanıcıların yüklemesine hazır ve kullanılabilir olmasını sağlamaya yardımcı olur.

> [!TIP]
> Intune ve MTD ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense bölmesinden görebilirsiniz.
