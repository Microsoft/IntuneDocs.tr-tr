---
title: Uygulamalar için veri aktarım ilkesi özel durumları
titleSuffix: Microsoft Intune
description: Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturun.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ada0f7fc7ed21750adf20a63d229f9a188cf34f
ms.sourcegitcommit: d2ac912b834c4840de9cc92ba1815b6ecfbfb52b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68482848"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturma

Yönetici olarak, Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturabilirsiniz. Bir özel durum, hangi yönetilmeyen uygulamaların yönetilen uygulamalara/uygulamalardan veri aktarabileceğini seçmenizi sağlar. Bu, özel durum listesine eklediğiniz yönetilmeyen uygulamalara güvenmelidir. 

>[!WARNING] 
> Veri aktarımı özel durum ilkesinde değişiklik yapmaktan siz sorumlusunuz. Bu ilkeye yapılan eklemeler, yönetilmeyen uygulamaların (Intune tarafından yönetilmeyen uygulamalar) yönetilen uygulamalar tarafından korunan verilere erişmesine izin verir. Korunan verilere bu erişim, veri güvenliği sızıntılarına neden olabilir. Yalnızca kuruluşunuzun kullanması gereken, ancak Intune APP'yi (Uygulama Koruma İlkeleri) desteklemeyen uygulamalar için veri aktarımı özel durumları ekleyin. Ayrıca, yalnızca veri sızıntısı riski içerdiğini düşünmediğiniz uygulamalar için özel durumlar ekleyin.

Bir Intune uygulama koruma Ilkesinde, uygulamanın diğer uygulamalara verileri **ilkeyle yönetilen uygulamalara** **aktarmasına izin ver** ayarı, uygulamanın verileri yalnızca Intune tarafından yönetilen uygulamalara aktarabileceği anlamına gelir. Verilerin Intune UYGULAMASıNı desteklemeyen belirli uygulamalara aktarılmasına izin vermeniz gerekiyorsa, **muaf tutulacak uygulamaları seçin**' i kullanarak bu ilkeye özel durumlar oluşturabilirsiniz. Muafiyetler, Intune tarafından yönetilen uygulamaların yönetilmeyen uygulamaları URL protokolüne (iOS) veya paket adına (Android) bağlı olarak çağırmasına imkan verir. Varsayılan olarak Intune, önemli yerel uygulamaları bu özel durumlar listesine ekler. 

> [!NOTE]
> Veri aktarımı ilkelerini değiştirmek veya eklemek; kesme, kopyalama ve yapıştırma kısıtlamaları gibi diğer Uygulama Koruma İlkelerini etkilemez. 

## <a name="ios-data-transfer-exceptions"></a>iOS veri aktarımı özel durumları
iOS'u hedefleyen bir ilke için, veri aktarımı özel durumlarını URL protokolü ile yapılandırabilirsiniz. Bir özel durum eklemek için desteklenen URL protokolleri hakkında bilgi bulmak üzere uygulamanın geliştiricisi tarafından sağlanan belgelere bakın. İOS veri aktarımı özel durumları hakkında daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları-veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> Microsoft’un üçüncü taraf uygulamalarında uygulama istisnaları oluşturan URL protokollerini el ile bulmak için bir yöntemi yoktur. 

## <a name="android-data-transfer-exceptions"></a>Android veri aktarımı özel durumları
Android'i hedefleyen bir ilke için, uygulama paketi adına göre veri aktarımı özel durumları yapılandırabilirsiniz. Uygulama paketi adını bulmak için bir özel durum eklemek istediğiniz uygulamanın **Google Play** mağaza sayfasını kontrol edebilirsiniz. Android veri aktarımı özel durumları hakkında daha fazla bilgi için bkz. [Android uygulama koruma ilkesi ayarları-veri aktarımı muafiyetleri](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

### <a name="example"></a>Örnek
MAM veri aktarımı ilkesine bir özel durum olarak **Webex** paketinin eklenmesiyle, yönetilen bir Outlook e-posta iletisindeki Webex bağlantılarının doğrudan Webex uygulamasında açılmasına izin verilir. Diğer yönetilmeyen uygulamalarda veri aktarımı kısıtlı olmaya devam eder.

- iOS **WebEx** örneği:   Intune tarafından yönetilen uygulamalar tarafından çağrılmasına izin verilmesi için **WebEx** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir:<code>wbx</code>
    
- iOS **haritaları** örneği:   Intune tarafından yönetilen uygulamalar tarafından çağrılmasına izin verilmesi için yerel **haritalar** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir:<code>maps</code>

- Android **WebEx** örneği:   Intune tarafından yönetilen uygulamalar tarafından çağrılmasına izin verilmesi için **WebEx** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir:<code>com.cisco.webex.meetings</code>
    
- Android **SMS** örneği:   Farklı mesajlaşma uygulamaları ve Android cihazlarda Intune tarafından yönetilen uygulamalar tarafından çağrılmasına izin verilmesi için yerel **SMS** uygulamasını muaf tutmak üzere, aşağıdaki dizeler için veri aktarımı özel durumları eklemeniz gerekir: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Android uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-android.md#data-transfer-exemptions)
