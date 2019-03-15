---
title: Uygulamalar için veri aktarım ilkesi özel durumları
titleSuffix: Microsoft Intune
description: Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturun.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9948bd1dbad7b130b434a1595484d3371cd18cf
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57391385"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturma

Yönetici olarak, Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesi için özel durumlar oluşturabilirsiniz. Bir özel durum, hangi yönetilmeyen uygulamaların yönetilen uygulamalara/uygulamalardan veri aktarabileceğini seçmenizi sağlar. Özel durum listesine dâhil et yönetilmeyen uygulamalara BT güvenmesi gerekir. 

>[!WARNING] 
> Veri aktarımı özel durum ilkesinde değişiklik yapmaktan siz sorumlusunuz. Bu ilkeye yapılan eklemeler, yönetilmeyen uygulamaların (Intune tarafından yönetilmeyen uygulamalar) yönetilen uygulamalar tarafından korunan verilere erişmesine izin verir. Korunan verilere bu erişim, veri güvenliği sızıntılarına neden olabilir. Yalnızca kuruluşunuzun kullanması gereken, ancak Intune APP'yi (Uygulama Koruma İlkeleri) desteklemeyen uygulamalar için veri aktarımı özel durumları ekleyin. Ayrıca, yalnızca veri sızıntısı riski içerdiğini düşünmediğiniz uygulamalar için özel durumlar ekleyin.

Bir Intune uygulama koruması ilke ayarı içinde **uygulamanın diğer uygulamalara veri aktarmasına izin ver** için **ilke ile yönetilen uygulamalar** uygulamayı yalnızca Intune tarafından yönetilen uygulamalara veri aktarabilir anlamına gelir. Verilerin Intune APP'yi desteklemeyen belirli uygulamalarla aktarılmasına izin vermeniz gerekiyorsa, bu ilke için özel durumları kullanarak oluşturabileceğiniz **dışarıda tutulacak uygulamaları seçin**. Muafiyetler, Intune tarafından yönetilen uygulamaların yönetilmeyen uygulamaları URL protokolüne (iOS) veya paket adına (Android) bağlı olarak çağırmasına imkan verir. Varsayılan olarak Intune, önemli yerel uygulamaları bu özel durumlar listesine ekler. 

> [!NOTE]
> Veri aktarımı ilkelerini değiştirmek veya eklemek; kesme, kopyalama ve yapıştırma kısıtlamaları gibi diğer Uygulama Koruma İlkelerini etkilemez. 

## <a name="ios-data-transfer-exceptions"></a>iOS veri aktarımı özel durumları
iOS'u hedefleyen bir ilke için, veri aktarımı özel durumlarını URL protokolü ile yapılandırabilirsiniz. Bir özel durum eklemek için desteklenen URL protokolleri hakkında bilgi bulmak üzere uygulamanın geliştiricisi tarafından sağlanan belgelere bakın. İOS veri aktarımı özel durumları hakkında daha fazla bilgi için bkz: [iOS uygulama koruma İlkesi ayarları - veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> Microsoft’un üçüncü taraf uygulamalarında uygulama istisnaları oluşturan URL protokollerini el ile bulmak için bir yöntemi yoktur. 

## <a name="android-data-transfer-exceptions"></a>Android veri aktarımı özel durumları
Android'i hedefleyen bir ilke için, uygulama paketi adına göre veri aktarımı özel durumları yapılandırabilirsiniz. Uygulama paketi adını bulmak için bir özel durum eklemek istediğiniz uygulamanın **Google Play** mağaza sayfasını kontrol edebilirsiniz. Android veri aktarımı özel durumları hakkında daha fazla bilgi için bkz. [Android uygulama koruma İlkesi ayarları - veri aktarımı muafiyetleri](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

### <a name="example"></a>Örnek
MAM veri aktarımı ilkesine bir özel durum olarak **Webex** paketinin eklenmesiyle, yönetilen bir Outlook e-posta iletisindeki Webex bağlantılarının doğrudan Webex uygulamasında açılmasına izin verilir. Diğer yönetilmeyen uygulamalarda veri aktarımı kısıtlı olmaya devam eder.

- iOS **Webex** örneği:   Muaf tutmak üzere **Webex** uygulama Intune tarafından çağrılacak olan izin verilen şekilde yönetilen uygulamalar, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>wbx</code>
    
 - iOS **haritalar** örneği:  Yerel muaf tutmak için **haritalar** uygulama Intune tarafından çağrılacak olan izin verilen şekilde yönetilen uygulamalar, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>maps</code>

- Android **Webex** örneği:   Muaf tutmak üzere **Webex** uygulama Intune tarafından çağrılacak olan izin verilen şekilde yönetilen uygulamalar, aşağıdaki dize için bir veri aktarımı özel durumu eklemeniz gerekir: <code>com.cisco.webex.meetings</code>
    
- Android **SMS** örneği:   Yerel muaf tutmak için **SMS** farklı Mesajlaşma uygulamaları ve Android cihazlarda Intune tarafından çağrılacak olan izin verilen şekilde uygulama yönetilen uygulamalar, veri aktarımı özel durumları için aşağıdaki dizelerden eklemeniz gerekir: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Android uygulama koruma ilkesi ayarları - Veri aktarımı muafiyetleri](app-protection-policy-settings-android.md#data-transfer-exemptions)
