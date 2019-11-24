---
title: Kayıtlı olmayan cihazlar için Mobile Threat Defense bağlayıcısını etkinleştirme
titleSuffix: Microsoft Intune
description: Kayıtlı olmayan cihazlar için Microsoft Intune mobil tehdit savunma bağlayıcısını etkinleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2744a27a733824bab9d920f4de0b49e951c1c34
ms.sourcegitcommit: a4c7339ec9ff5b1b846cb3cca887cf91b5cd4baa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627633"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>Kayıtlı olmayan cihazlar için Intune 'da Mobile Threat Defense bağlayıcısını etkinleştirme

Mobile Threat Defense (MTD) kurulumu sırasında, Mobile Threat Defense iş ortağı konsolinizdeki tehditleri sınıflandırmak için bir ilke yapılandırdınız ve Intune 'da uygulama koruma ilkesi oluşturdunuz. Intune bağlayıcısını MTD iş ortağı konsolunda zaten yapılandırdıysanız MTD iş ortağı uygulamaları için MTD bağlantısını etkinleştirebilirsiniz.

> [!NOTE] 
> Bu makale, uygulama koruma ilkelerini destekleyen tüm Mobile Threat Defense iş ortakları için geçerlidir: daha Iyi mobil (Android), Zkusuren IUM (iOS), Lookout for Work (Android/iOS).

## <a name="to-enable-the-mtd-connector"></a>MTD bağlayıcısını etkinleştirmek için

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.

2. **Intune Panosunda**, **Cihaz uyumluluğu**’nu, ardından **Mobile Threat Defense**’i **Kurulum** bölümü altında seçin.

3. **Mobile Threat Defense** bölmesinde **Ekle**’yi seçin.

4. Açılan listeden MTD çözümünü **Kurulacak Mobile Threat Defense bağlayıcısı** olarak seçin.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin. Görünen geçişli seçenekler MTD iş ortağına bağlı olarak değişir.

## <a name="mtd-toggle-options"></a>MTD geçiş seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi MTD geçiş seçeneklerini etkinleştirmeniz gerektiğine karar verebilirsiniz. Daha fazla ayrıntı aşağıdadır:

**Uygulama koruma Ilkesi ayarları**
- **4,4 ve üzeri sürüm Android cihazlarını uygulama koruma ilkesi değerlendirmesi için *\<MTD iş ortağı adı >* bağlayın**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri, bu bağlayıcıdaki veriler dahil olmak üzere cihazları değerlentirecektir.
- ***\<MTD iş ortağı adı >* , uygulama koruma Ilkesi değerlendirmesi için iOS cihazları sürüm 11 ve üstünü bağlayın**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri, bu bağlayıcıdaki veriler dahil olmak üzere cihazları değerlendirir.

**Ortak paylaşılan ayarlar**
- **İş ortağının yanıt vermediği gün sayısı**: Bağlantı kesildiği için Intune’un iş ortağının yanıt vermiyor olarak değerlendirmesi için işlem yapılmadan geçmesi gereken gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!TIP]
> Intune ve MTD ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense bölmesinden görebilirsiniz.

> [!NOTE] 
> Intune ile Mobile Threat Defense bağlantısını etkinleştirdiğinizde, Intune Azure Active Directory bir klasik koşullu erişim ilkesi oluşturur. [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri dahil olmak üzere tümleştirilen her MTD uygulaması yeni bir klasik koşullu erişim ilkesi oluşturur. **Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinmemelidir veya devre dışı bırakılmalıdır.**
> 
> MTD uygulamaları için klasik koşullu erişim ilkeleri: 
> - , Cihazların Azure AD 'ye kaydolmasını gerektirmek için, MTD iş ortaklarıyla iletişim kurmadan önce cihaz KIMLIĞI olması için Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.  
> - Diğer bulut uygulamaları veya kaynakları üzerinde hiçbir etkisi yoktur.  
> - , MTD 'yi yönetmeye yardımcı olmak veya uygulama koruma CA 'sı Istemek için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır
> - Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.  
>
> Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilkeleri**' ne gidin.

## <a name="next-steps"></a>Sonraki Adımlar

- [Intune Ile Mobile Threat Defense (MTD) uygulama koruma Ilkesi oluşturun](~/protect/mtd-app-protection-policy.md).
