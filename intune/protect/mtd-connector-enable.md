---
title: Microsoft Intune'da Mobile Threat Defense bağlayıcısını etkinleştirme
titleSuffix: Microsoft Intune
description: Mobile Threat Defense (MTD) iş ortağınız ile Microsoft Intune arasında bağlayıcıyı etkinleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4f917167baecc643e045610e86e582957e535978
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810295"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Intune'da Mobil Threat Defense bağlayıcısını etkinleştirme

> [!NOTE] 
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Mobile Threat Defense (MTD) kurulumu sırasında, MTD iş ortağı konsolunuzdaki tehditleri sınıflandırmak için bir ilke yapılandırdınız ve Intune’da cihaz uyumluluk ilkesi oluşturdunuz. Intune bağlayıcısını MTD iş ortağı konsolunda zaten yapılandırdıysanız MTD iş ortağı uygulamaları için MTD bağlantısını etkinleştirebilirsiniz.

Yeni bir uygulamayı Intune mobil tehdit savunması ile tümleştirdiğinizde ve Intune bağlantısını etkinleştirdiğinizde, Intune Azure Active Directory içinde klasik bir koşullu erişim ilkesi oluşturur. [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri dahil olmak üzere tümleştirilen her MTD uygulaması yeni bir klasik koşullu erişim ilkesi oluşturur. Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinmemelidir veya devre dışı bırakılmalıdır.

MTD uygulamaları için klasik koşullu erişim ilkeleri: 

- , Cihazların Azure AD 'ye kaydolmasını gerektirmek için, MTD iş ortaklarıyla iletişim kurmadan önce cihaz KIMLIĞI olması için Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.  
- Diğer bulut uygulamaları veya kaynakları üzerinde hiçbir etkisi yoktur.  
- , MTD 'leri yönetmeye yardımcı olmak için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır.
- Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.  

Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilke**' ye gidin.


## <a name="to-enable-the-mobile-threat-defense-connector"></a>Mobile Threat Defense bağlayıcısını etkinleştirmek için

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.

4. **Intune Panosunda**, **Cihaz uyumluluğu**’nu, ardından **Mobile Threat Defense**’i **Kurulum** bölümü altında seçin.

5. **Mobile Threat Defense** bölmesinde **Ekle**’yi seçin.

6. Açılan listeden MTD çözümünü **Kurulacak Mobile Threat Defense bağlayıcısı** olarak seçin.

    ![Intune Azure portalında MTD kurulumu](./media/mtd-connector-enable/enable-mtd-connector-1.png)

7. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin. Görünen geçişli seçenekler MTD iş ortağına bağlı olarak değişir.

## <a name="mobile-threat-defense-toggle-options"></a>Mobil tehdit savunma değiştirme seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi mobil tehdit savunması için etkinleştirmeniz gerektiğine karar verebilirsiniz. Daha fazla ayrıntı aşağıdadır:

**MDM uyumluluk Ilkesi ayarları**
- \* * Android 4.1 + cihazlarını *\<MTD iş ortağı adına bağlama > * * *: Bu seçeneği etkinleştirdiğinizde, Android 4.1 + cihazların güvenlik riskini Intune 'a geri bildirimini sağlayabilirsiniz.
- \* * İOS 8.0 + cihazlarını *\<MTD iş ortağı adına bağlama > * * *: Bu seçeneği etkinleştirdiğinizde, iOS 8.0 + cihazların güvenlik riskini Intune 'a geri bildirimini sağlayabilirsiniz.
- **iOS Cihazlar için Uygulama Eşitlemeyi etkinleştir**: Bu Mobil Tehdit Savunması iş ortağının tehdit analizi için kullanmak amacıyla Intune’dan iOS uygulamalarının meta verilerini istemesine izin verir.
- **Desteklenmeyen işletim sistemi sürümlerini engelle**: Cihaz, desteklenen en düşük sürümden düşük bir işletim sistemi çalıştırıyorsa engellenir.

**Uygulama koruma Ilkesi ayarları**
- **4,1 ve üzeri sürüm Android cihazlarını uygulama koruma ilkesi değerlendirmesi için *\<MTD iş ortağı adı >* bağlayın**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri cihazları değerlendirir Bu bağlayıcıdaki veriler.
- **@No__t_2MTD iOS 8,0 cihazlarını uygulama koruma ilkesi değerlendirmesi için *> iş ortağı adına* bağlama**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri, verileri de içeren cihazları değerlentirecektir Bu bağlayıcı.

Intune Uygulama Koruması Ilkesi değerlendirmesi için Mobile Threat Defense bağlayıcıları kullanma hakkında daha fazla bilgi edinmek için bkz. [kayıtlı olmayan cihazlar Için mobil tehdit savunması ayarlama](~/protect/mtd-enable-unenrolled-devices.md).

**Ortak paylaşılan ayarlar**
- **İş ortağının yanıt vermediği gün sayısı**: Bağlantı kesildiği için Intune’un iş ortağının yanıt vermiyor olarak değerlendirmesi için işlem yapılmadan geçmesi gereken gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!IMPORTANT] 
> Mümkün olduğunda, cihaz uyumluluğunu ve koşullu erişim ilkesi kurallarını oluşturmadan önce MTD uygulamalarını eklemenizi ve atamanızı öneririz. Bu, MTD uygulamasının, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce, son kullanıcıların yüklemesine hazır ve kullanılabilir olmasını sağlamaya yardımcı olur.

> [!TIP]
> Intune ve MTD ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense bölmesinden görebilirsiniz.
