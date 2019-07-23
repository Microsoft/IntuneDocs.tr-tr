---
title: Microsoft Intune kullanıcılara özel bildirimler gönderme
titleSuffix: ''
description: İOS ve Android cihazlarının kullanıcılarına özel anında iletme bildirimleri oluşturmak ve göndermek için Intune 'U kullanın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 7/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1caff820daf2e278c50d154873f569163b264315
ms.sourcegitcommit: c3a4fefbac8ff7badc42b1711b7ed2da81d1ad67
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68377087"
---
# <a name="send-custom-notifications-in-intune"></a>Intune 'da özel bildirimler gönderme  

Yönetilen iOS ve Android cihazların kullanıcılarına özel bildirimler göndermek için Microsoft Intune kullanın. Bu iletiler, bir kullanıcının aygıtındaki Şirket Portalı uygulamadan standart anında iletme bildirimleri gibi görünür, böylece cihazdaki diğer uygulamalardan gelen bildirimler görüntülenir. Intune özel bildirimleri Windows cihazları tarafından desteklenmez.   

Özel bildirim iletileri, kısa bir başlık ve 500 karakter veya daha kısa bir ileti gövdesi içerir. Bu iletiler, herhangi bir genel iletişim amacı için özelleştirilebilir.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Özel bildirimler göndermek için yaygın senaryolar  

- Şirket Portalı bulunan yeni bir uygulama hakkında belirli kullanıcıları uyarmak için özel bildirimleri kullanın.  
- Inlement Hava durumu nedeniyle kapanışları oluşturma gibi, zamanlamaya göre değişiklik için tüm çalışanları bilgilendirin.  

## <a name="considerations-for-using-custom-notifications"></a>Özel bildirimler kullanma konuları  

**Cihaz yapılandırması**:  
- Kullanıcıların özel bildirimler alabilmesi için cihazda Şirket Portalı uygulamasının yüklü olması gerekir. Ayrıca, Şirket Portalı uygulamasının anında iletme bildirimleri göndermesini sağlamak için izinleri de yapılandırmış olmaları gerekir. Şirket Portalı, kullanıcılardan bildirimlere izin vermesi istenir.  
- Android 'de Google Play Hizmetleri gerekli bir bağımlılıkdır.  

**Bildirimler oluşturuluyor**:  
- Bir ileti oluşturmak için, **kuruluş**için **güncelleştirme** izni içeren bir Intune rolü atanmış bir hesap kullanın. Bir kullanıcıya izin atamak için bkz. [rol atamaları](role-based-access-control.md#role-assignments)  
- Özel bildirimler 50 karakterlik başlıklar ve 500 karakterlik iletilerle sınırlıdır.  
- Intune gönderilen iletileri kaydetmez. Bir iletiyi yeniden göndermek için bu iletiyi yeniden oluşturmanız gerekir.  
- Saat başına en fazla 25 ileti gönderebilirsiniz. Bu kısıtlama kiracı düzeyindedir.  
- Her bildirim, 25 gruba kadar doğrudan hedefleyebilir. İç içe gruplar bu toplama göre sayılmaz.  
- Gruplar, kullanıcıları veya cihazları içerebilir ancak iletiler yalnızca kullanıcılara gönderilir ve Kullanıcı tarafından kaydedilen her bir iOS veya Android cihazına gönderilir.  

**Teslim**:  
- Intune, bir bildirim gönderildikten sonra teslimi bir saate kadar dener.  
- Intune, kullanıcıların Şirket Portalı uygulamasına iletiler göndererek anında iletme bildirimi oluşturur. Bildirimin cihaza itilmesi için kullanıcıların uygulamada oturum açmış olması gerekmez.  
- Intune ve Şirket Portalı uygulaması, özel bir bildirimin teslimini garanti edemez. Özel bildirimler, her biri bir süre sonra, acil iletilerde kullanılmamalıdır.  
- Intune 'dan gelen özel bildirim iletileri cihazlarda standart anında iletme bildirimleri olarak görünür. Şirket Portalı uygulaması bildirimi aldığında bir iOS cihazında açıksa bildirim, bir anında iletme bildirimi yerine uygulamada görüntülenir.  
- Özel bildirimler, cihaz ayarlarına bağlı olarak hem iOS hem de Android cihazlarda kilit ekranlarında görülebilir.  
- Android cihazlarda, diğer uygulamaların özel Bildiriminizdeki verilere erişimi olabilir. Bunları hassas iletişimler için kullanmayın.  
- Son kaydedilmemiş veya bir gruptan kaldırılmış olan kullanıcıların bir cihaz kullanıcıları daha sonra bu gruba gönderilen özel bir bildirim alabilir.  Benzer şekilde, gruba özel bir bildirim gönderildikten sonra bir Kullanıcı eklerseniz, yeni eklenen kullanım için daha önce gönderilen bildirim iletisini almak mümkündür.  

## <a name="send-a-custom-notification"></a>Özel bildirim gönder  

1. Bildirim oluşturma ve gönderme izinlerine sahip bir hesapla [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihazlara** > **özel bildirimler gönder**' e gidin.  

2. Temel bilgiler sekmesinde, aşağıdakileri belirtin ve devam etmek için **İleri** ' yi seçin.  
   - **Title** : Bu bildirim için bir başlık belirtin. Başlıklar 50 karakterle sınırlıdır.  
   - **Gövde** – iletiyi belirtin. İletiler 500 karakterle sınırlıdır

   ![Özel bildirim oluşturma](./media/custom-notifications/custom-notifications.png)  

3. **Atamalar** sekmesinde, bu özel bildirimi göndermek istediğiniz grupları seçin ve ardından devam etmek için ileri ' yi seçin.  

4. **Gözden geçir + oluştur** sekmesinde, bilgileri gözden geçirin ve bildirimi göndermeye hazırsanız **Oluştur**' u seçin.  

Intune, hemen oluşturduğunuz iletileri işler. İletinin gönderildiği tek onay, özel bildirimin gönderildiğini doğrulayan Intune bildirimidir.  

![Gönderilen bildirim onayı](./media/custom-notifications/notification-sent.png)  

Intune, göndereceğiniz özel bildirimleri izlemez ve cihazlar, bilgileri cihazın Bildirim Merkezi dışında günlüğe kaydetmez.  

## <a name="receive-a-custom-notification"></a>Özel bir bildirim alın  

Bir cihazda, kullanıcılar Şirket Portalı uygulamadan standart bir anında iletme bildirimi olarak Intune tarafından gönderilen özel bildirim iletilerini görürler. Bu bildirimler, kullanıcıların cihazdaki diğer uygulamalardan aldığı anında iletme bildirimlerine benzer.  

İOS cihazlarında, bildirim alındığında Şirket Portalı uygulama açıksa bildirim, anında iletme bildirimi yerine uygulamada görüntülenir.  

Bildirim, Kullanıcı tarafından kesilene kadar kalır.  

## <a name="next-steps"></a>Sonraki adımlar  
[Cihazları yönetme](device-management.md)
