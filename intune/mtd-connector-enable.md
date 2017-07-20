---
title: "Intune ile Mobil Threat Defense bağlayıcısını etkinleştirme"
titleSuffix: Intune on Azure
description: "Intune'da Mobil Threat Defense bağlayıcısını etkinleştirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 38fb9977ed8af05380a265ee254259acef7b43f0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Intune’da Mobile Threat Defense’i etkinleştirme

Intune'da Mobile Threat Defense (MTD) bağlantısını etkinleştirmek için MTD çözüm konsolunda Intune Bağlayıcısı'nı zaten yapılandırmış olmanız gerekir.

## <a name="to-enable-the-mtd-connector"></a>MTD bağlayıcısını etkinleştirmek için

1. [Azure Portal](https://portal.azure.com)’a gidin ve Intune kimlik bilgilerinizle oturum açın. Oturumunuz başarıyla açıldıktan sonra **Azure Panosu**'nu görürsünüz.

2. **Azure Panosunda**, soldaki menüden **Diğer hizmetler**’i seçtikten sonra, metin kutusu filtresine **Intune** yazın.

3. **Intune**'u seçin, **Intune Panosu** açılır.

4. **Intune Panosunda**, **Cihaz uyumluluğu**’nu, ardından **Mobile Threat Defense**’i **Kurulum** bölümü altında seçin.

5. **Mobile Threat Defense** dikey penceresinde, **Ekle**’yi seçin.

6. Açılan listeden MTD çözümünü **Kurulacak Mobile Threat Defense bağlayıcısı** olarak seçin.

    ![Intune Azure portalında MTD kurulumu](./media/enable-mtd-connector-1.png)

7. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin.

## <a name="mtd-toggle-options"></a>MTD geçiş seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi MTD geçiş seçeneklerini etkinleştirmeniz gerektiğine karar verebilirsiniz. Daha ayrıntılı anlatmak gerekirse:

- **Android 4.1+ cihazları, [MTD iş ortağı adı] for Work MTD'ye bağla**: Bu seçeneği etkinleştirdiğinizde, Android 4.1+ cihazların güvenlik riskini Intune’a geri raporlamasını sağlayabilirsiniz.
    - **Veri alınmazsa uyumsuz olarak işaretle**: Intune, bu platformdaki bir cihaz hakkında MTD iş ortağından herhangi bir veri almazsa cihazın uyumsuz kabul edilmesini sağlar.
<br></br>
- **iOS 8.0+ cihazları, [MTD iş ortağı adı] for Work MTD'ye bağla**: Bu seçeneği etkinleştirdiğinizde, Android 4.1+ cihazların güvenlik riskini Intune’a geri raporlamasını sağlayabilirsiniz.
    - **Veri alınmazsa uyumsuz olarak işaretle**: Intune, bu platformdaki bir cihaz hakkında MTD iş ortağından herhangi bir veri almazsa cihazın uyumsuz kabul edilmesini sağlar.
<br></br>
- **Desteklenmeyen işletim sistemi sürümlerini engelle**: Cihaz, desteklenen en düşük sürümden düşük bir işletim sistemi çalıştırıyorsa engellenir.

- **İş ortağının yanıt vermediği gün sayısı**: Bağlantı kesildiği için Intune’un iş ortağının yanıt vermiyor olarak değerlendirmesi için işlem yapılmadan geçmesi gereken gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!IMPORTANT] 
> Cihaz uyumluluğunu ve koşullu erişim ilkesi kurallarını oluşturmadan önce MTD uygulamalarını ekleyip atamanız gerekir. Bu, MTD uygulamasının, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

> [!TIP]
> Intune ve MTD iş ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense dikey penceresinden görebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile Mobile Threat Defense cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)