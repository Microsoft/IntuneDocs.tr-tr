---
title: Uygulamalar için veri aktarım ilkesi özel durumları
titleSuffix: Microsoft Intune
description: Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturun.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d33768206c53550ec1cb34d5c1ad5e2f33e4f8c8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Yönetici olarak, Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturabilirsiniz. Bir özel durum, hangi yönetilmeyen uygulamaların yönetilen uygulamalara/uygulamalardan veri aktarabileceğini seçmenizi sağlar. Özel durum listesine dahil ettiğiniz yönetilmeyen uygulamalara BT tarafından güvenilmelidir. 

>[!WARNING] 
> Veri aktarımı özel durum ilkesinde değişiklik yapmaktan siz sorumlusunuz. Bu ilkeye yapılan eklemeler, yönetilmeyen uygulamaların (Intune tarafından yönetilmeyen uygulamalar) yönetilen uygulamalar tarafından korunan verilere erişmesine izin verir. Korunan verilere bu erişim, veri güvenliği sızıntılarına neden olabilir. Yalnızca kuruluşunuzun kullanması gereken, ancak Intune APP'yi (Uygulama Koruma İlkeleri) desteklemeyen uygulamalar için veri aktarımı özel durumları ekleyin. Ayrıca, yalnızca veri sızıntısı riski içerdiğini düşünmediğiniz uygulamalar için özel durumlar ekleyin.

Bu özellik, **Yalnızca yönetilen uygulamalar** olarak ayarlanmış veri aktarımı ile bir Intune Uygulama Koruma İlkesi oluşturduğunuzda geçerlidir. Oluşturduğunuz özel durumlar dışında, veri aktarım ilkeniz **Yalnızca yönetilen uygulamalar** olarak ayarlandığında, veri aktarımı Intune tarafından yönetilen uygulamalarla sınırlı kalır. Protokoller (iOS) veya paketler (Android) kullanarak kısıtlamalar oluşturabilirsiniz.

Bu özelliği, Intune MAM Uygulama Koruma ilkesi **veri aktarımını kısıtlama** özel durumlarını etkinleştirmek için yapılandırabilirsiniz. Bu ilke yalnızca verilerin Intune APP'yi desteklemeyen bir uygulamaya aktarılmasına izin vermek istiyorsanız gereklidir. Bu ilke, Intune tarafından yönetilen uygulamaların, veri aktarım ayarlarının **Yalnızca yönetilen uygulamalar** olarak ayarlanması, yönetilmeyen uygulamaların URL protokolüne (iOS) veya paket adına (Android) dayalı olarak çağrılmasına olanak tanır. Intune, önemli yerel uygulamaları varsayılan özel durumlar listesine ekler. 

## <a name="ios-data-transfer-exceptions"></a>iOS veri aktarımı özel durumları
iOS'u hedefleyen bir ilke için, veri aktarımı özel durumlarını URL protokolü ile yapılandırabilirsiniz. Bir özel durum eklemek için desteklenen URL protokolleri hakkında bilgi bulmak üzere uygulamanın geliştiricisi tarafından sağlanan belgelere bakın. iOS veri aktarımı özel durumları hakkında ek bilgi için bkz. [iOS uygulama koruma İlkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Android veri aktarımı özel durumları
Android'i hedefleyen bir ilke için, uygulama paketi adına göre veri aktarımı özel durumları yapılandırabilirsiniz. Uygulama paketi adını bulmak için bir özel durum eklemek istediğiniz uygulamanın **Google Play** mağaza sayfasını kontrol edebilirsiniz. Android veri aktarımı özel durumları hakkında ek bilgi için bkz. [Android uygulama koruma ilkesi ayarları - Veri aktarımı muafiyeti](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

### <a name="example"></a>Örnek
MAM veri aktarımı ilkesine bir özel durum olarak **Webex** paketinin eklenmesiyle, yönetilen bir Outlook e-posta iletisindeki Webex bağlantılarının doğrudan Webex uygulamasında açılmasına izin verilir. Diğer yönetilmeyen uygulamalarda veri aktarımı kısıtlı olmaya devam eder.

- iOS **Webex** örneği: Intune’un yönettiği uygulamalar tarafından çağrılmasına izin verilmesi için **Webex** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>wbx</code>
    
 - iOS **Maps** örneği: Intune’un yönettiği uygulamalar tarafından çağrılmasına izin verilmesi için yerel **Maps** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>maps</code>

- Android **Webex** örneği: Intune’un yönettiği uygulamalar tarafından çağrılmasına izin verilmesi için **Webex** uygulamasını muaf tutmak üzere, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>com.cisco.webex.meetings</code>
    
- Android **SMS** örneği: Farklı mesajlaşma uygulamaları ve Android cihazlarında Intune’un yönettiği uygulamalar tarafından çağrılmasına izin verilmesi için yerel **SMS** uygulamasını muaf tutmak üzere, aşağıdaki dizeler için veri aktarımı özel durumları eklemeniz gerekir: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Android uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-android.md#data-transfer-exemptions)
