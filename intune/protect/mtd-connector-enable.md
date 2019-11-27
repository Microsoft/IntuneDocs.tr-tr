---
title: Microsoft Intune'da Mobile Threat Defense bağlayıcısını etkinleştirme
titleSuffix: Microsoft Intune
description: Mobile Threat Defense (MTD) iş ortağınız ile Microsoft Intune arasında bağlayıcıyı etkinleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
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
ms.openlocfilehash: b8243ae4014660a76c6327afd9c970ce8a9eae58
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478838"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>Intune'da Mobil Threat Defense bağlayıcısını etkinleştirme

Mobile Threat Defense (MTD) kurulumu sırasında, Mobile Threat Defense iş ortağı konsolinizdeki tehditleri sınıflandırmak için bir ilke yapılandırdınız ve Intune 'da cihaz Uyumluluk ilkesini oluşturdunuz. Intune bağlayıcısını MTD iş ortağı konsolunda zaten yapılandırdıysanız MTD iş ortağı uygulamaları için MTD bağlantısını etkinleştirebilirsiniz.

> [!NOTE]
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>MTD uygulamaları için klasik koşullu erişim ilkeleri

Yeni bir uygulamayı Intune mobil tehdit savunması ile tümleştirdiğinizde ve Intune bağlantısını etkinleştirdiğinizde, Intune Azure Active Directory içinde klasik bir koşullu erişim ilkesi oluşturur. [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri dahil olmak üzere tümleştirilen her MTD uygulaması yeni bir klasik koşullu erişim ilkesi oluşturur. Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinemez veya devre dışı bırakılmalıdır.

Klasik ilke silinirse, oluşturulduktan sorumlu olan Intune bağlantısını silmeniz ve sonra yeniden ayarlamanız gerekir. Bu işlem, klasik ilkeyi yeniden oluşturur. MTD uygulamaları için klasik ilkelerin, koşullu erişim için yeni ilke türüne geçirilmesi desteklenmez.

MTD uygulamaları için klasik koşullu erişim ilkeleri:

- , Cihazların Azure AD 'ye kaydolmasını gerektirmek için, MTD iş ortaklarıyla iletişim kurmadan önce cihaz KIMLIĞI olması için Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.

- Diğer bulut uygulamaları veya kaynakları üzerinde hiçbir etkisi yoktur.

- , MTD 'leri yönetmeye yardımcı olmak için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır.

- Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.

Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilkeleri**' ne gidin.

## <a name="to-enable-the-mobile-threat-defense-connector"></a>Mobile Threat Defense bağlayıcısını etkinleştirmek için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Mobil tehdit savunması** > **bağlayıcı ve belirteçler** > **Kiracı Yönetimi** ' ni seçin.

3. **Mobile Threat** Defense bölmesinde **Ekle**' yi seçin.

4. **Mobil tehdit savunması bağlayıcısının kurulumunu yapmak**için, açılan listeden MTD çözümünüzü seçin.

5. Kuruluşunuzun gereksinimlerine göre geçiş seçeneklerini etkinleştirin. Görünen geçişli seçenekler MTD iş ortağına bağlı olarak değişir.  Örneğin, aşağıdaki görüntüde Symantec Endpoint Protection için kullanılabilen seçenekler gösterilmektedir:

   ![Intune Azure portalında MTD kurulumu](./media/mtd-connector-enable/enable-mtd-connector-1.png)

## <a name="mobile-threat-defense-toggle-options"></a>Mobil tehdit savunma değiştirme seçenekleri

Kuruluşunuzun gereksinimlerine göre hangi MTD geçiş seçeneklerini etkinleştirmeniz gerektiğine karar verebilirsiniz. Tüm mobil Iş parçacığı savunma iş ortakları tarafından aşağıdaki seçeneklerin tümü desteklenmez:

**MDM uyumluluk Ilkesi ayarları**

- **_Desteklenen sürüm\<_ Android cihazlarını _\<MTD iş ortağı adı >_ > bağlayın**: Bu seçeneği etkinleştirdiğinizde, Android 4.1 + cihazların güvenlik riskini Intune 'a geri raporlamasını sağlayabilirsiniz.

- **İOS cihazları sürümü _\<desteklenen sürümler >_ _\<MTD iş ortağı adına bağlama >_** : Bu seçeneği etkinleştirdiğinizde, IOS 8.0 + cihazların güvenlik riskini Intune 'a geri bildirimini sağlayabilirsiniz.

- **iOS Cihazlar için Uygulama Eşitlemeyi etkinleştir**: Bu Mobil Tehdit Savunması iş ortağının tehdit analizi için kullanmak amacıyla Intune’dan iOS uygulamalarının meta verilerini istemesine izin verir.

- **Desteklenmeyen işletim sistemi sürümlerini engelle**: Cihaz, desteklenen en düşük sürümden düşük bir işletim sistemi çalıştırıyorsa engellenir.

**Uygulama koruma Ilkesi ayarları**

- ***\<desteklenen > sürümlerin* Android cihazlarını *\<MTD iş ortağı adı >* uygulama koruma ilkesi değerlendirmesi için bağlama**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri, bu bağlayıcıdaki veriler dahil olmak üzere cihazları değerlentirecektir.

- **İOS cihazları sürümü *\<desteklenen sürümler >* *\<MTD iş ortağı adı >* uygulama koruma ilkesi değerlendirmesi için bağlama**: Bu seçeneği etkinleştirdiğinizde, cihaz tehdit düzeyi kuralını kullanan uygulama koruma ilkeleri, bu bağlayıcının verileri dahil olan cihazları değerlendirir.

Intune Uygulama Koruması Ilkesi değerlendirmesi için Mobile Threat Defense bağlayıcıları kullanma hakkında daha fazla bilgi edinmek için bkz. [kayıtlı olmayan cihazlar Için mobil tehdit savunması ayarlama](~/protect/mtd-enable-unenrolled-devices.md).

**Ortak paylaşılan ayarlar**

- **İş ortağının yanıt vermediği gün sayısı**: Bağlantı kesildiği için Intune’un iş ortağının yanıt vermiyor olarak değerlendirmesi için işlem yapılmadan geçmesi gereken gün sayısı. Intune, yanıt vermeyen MTD iş ortakları için uyumluluk durumunu yok sayar.

> [!IMPORTANT]
> Mümkün olduğunda, cihaz uyumluluğunu ve koşullu erişim ilkesi kurallarını oluşturmadan önce MTD uygulamalarını eklemenizi ve atamanızı öneririz. Bu, MTD uygulamasının, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce, son kullanıcıların yüklemesine hazır ve kullanılabilir olmasını sağlamaya yardımcı olur.

> [!TIP]
> Intune ve MTD ortağı arasındaki **Bağlantı durumu** ve **Son eşitleme** zamanını Mobile Threat Defense bölmesinden görebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Intune Ile Mobile Threat Defense (MTD) uygulama koruma Ilkesi oluşturun](~/protect/mtd-app-protection-policy.md).
