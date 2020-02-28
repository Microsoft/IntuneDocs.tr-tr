---
title: Microsoft Intune kullanıcılara özel bildirimler gönderme
titleSuffix: Microsoft Intune
description: İOS/ıpados ve Android cihaz kullanıcılarına özel anında iletme bildirimleri oluşturmak ve göndermek için Intune 'U kullanın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: afcb49447aa044b730d2271603d4966466318193
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782030"
---
# <a name="send-custom-notifications-in-intune"></a>Intune 'da özel bildirimler gönderme

Yönetilen iOS/ıpados ve Android cihazlarındaki kullanıcılara özel bildirimler göndermek için Microsoft Intune kullanın. Bu iletiler, Şirket Portalı uygulamadan ve bir kullanıcının aygıtındaki Microsoft Intune uygulamadan standart anında iletme bildirimleri olarak görünür, böylece cihazdaki diğer uygulamalardan gelen bildirimler görüntülenir. Intune özel bildirimleri macOS ve Windows cihazları tarafından desteklenmez.

Özel bildirim iletileri, kısa bir başlık ve 500 karakter veya daha kısa bir ileti gövdesi içerir. Bu iletiler, herhangi bir genel iletişim amacı için özelleştirilebilir.

### <a name="what-the-notification-looks-like-on-an-iosipados-device"></a>Bir iOS/ıpados cihazında bildirim nasıl görünür?

İOS/ıpados cihazında Şirket Portalı uygulaması açıksa, bildirim aşağıdaki ekran görüntüsüne benzer:

> [!div class="mx-imgBorder"]
> ![Şirket Portalı iOS/ıpados test bildirimi](./media/custom-notifications/105046-1.png)

Cihaz kilitliyse, bildirim aşağıdaki ekran görüntüsüne benzer:

> [!div class="mx-imgBorder"]
> ![kilitli cihaz iOS/ıpados test bildirimi](./media/custom-notifications/105046-2.png)

### <a name="what-the-notification-looks-like-on-an-android-device"></a>Bir Android cihazında bildirim nasıl görünür?

Android cihazda Şirket Portalı uygulaması açıksa, bildirim aşağıdaki ekran görüntüsüne benzer:

> [!div class="mx-imgBorder"]
> ![Android test bildirimi](./media/custom-notifications/105046-3.png)

## <a name="common-scenarios-for-sending-custom-notifications"></a>Özel bildirimler göndermek için yaygın senaryolar  

- Inlement Hava durumu nedeniyle kapanışları oluşturma gibi, zamanlamaya göre bir değişikliği tüm çalışanlara bildirin.
- Bir güncelleştirmenin yüklenmesini tamamlamaya yönelik bir acil istek iletişim kurmak için tek bir cihazın kullanıcısına bir bildirim gönderin.

## <a name="considerations-for-using-custom-notifications"></a>Özel bildirimler kullanma konuları

**Cihaz yapılandırması**

- Cihazların, kullanıcıların özel bildirimler alabilmesi için Şirket Portalı uygulamasının veya Microsoft Intune uygulamasının yüklü olması gerekir. Ayrıca, Şirket Portalı uygulamasının veya Microsoft Intune uygulamasının anında iletme bildirimleri göndermesini sağlamak için izinleri de yapılandırmış olmaları gerekir. Gerekirse, Şirket Portalı uygulaması ve Microsoft Intune uygulaması kullanıcılardan bildirimlere izin vermesi için istemde bulunabilir.
- Android 'de Google Play Hizmetleri gerekli bir bağımlılıkdır.
- Cihazın MDM kaydı yapılmalıdır.

**İzinler**:

- Gruplara bildirim göndermek için, hesabınız Intune 'da şu RBAC iznine sahip olmalıdır: *kuruluş* > **güncelleştirmesi**.
- Bir cihaza bildirim göndermek için, hesabınız Intune 'da şu RBAC iznine sahip olmalıdır: *uzak görevler* > **özel bildirimler gönder**.

**Bildirimler oluşturuluyor**:
 
- Bir ileti oluşturmak için, önceki *izinler* bölümünde açıklandığı gibi doğru izni Içeren bir Intune rolü atanmış bir hesap kullanın. Bir kullanıcıya izin atamak için bkz. [rol atamaları](../fundamentals/role-based-access-control.md#role-assignments).
- Özel bildirimler 50 karakterlik başlıklar ve 500 karakterlik iletilerle sınırlıdır.  
- Intune, daha önce gönderilen özel bildirimlerin metnini kaydetmez. Bir iletiyi yeniden göndermek için bu iletiyi yeniden oluşturmanız gerekir.  
- Yalnızca Grup için saat başına en fazla 25 ileti gönderebilirsiniz. Bu kısıtlama kiracı düzeyindedir. Bu sınırlama, ayrı cihazlara bildirim gönderilirken uygulanmaz.
- Yalnızca Grup için saat başına en fazla 25 ileti gönderebilirsiniz. Bu kısıtlama kiracı düzeyindedir. Bu sınırlama, kişilere bildirim gönderilirken uygulanmaz.
- Ayrı cihazlara ileti gönderirken aynı cihaza yalnızca saat başına en fazla 10 ileti gönderebilirsiniz.
- Kullanıcılara, gruplar halinde bildirim gönderebilirsiniz. Gruplara bildirim gönderilirken, her bildirim doğrudan 25 gruba kadar hedefleyebilir. İç içe gruplar bu toplama göre sayılmaz. Bir gruba bildirim gönderilirken iletiler yalnızca gruptaki kullanıcıları hedefleyebilir ve kullanıcının kaydol, her iOS/ıpados veya Android cihazına gönderilir. Bildirim hedeflenirken gruptaki cihazlar göz ardı edilir.
- Tek bir cihaza bildirim gönderebilirsiniz. Grupları kullanmak yerine bir cihaz seçin ve ardından özel bildirimi göndermek için bir uzak [cihaz eylemi](device-management.md#available-device-actions) kullanın.

**Teslim**:

- Intune, kullanıcıların Şirket Portalı uygulamasına veya Microsoft Intune uygulamasına iletiler göndererek anında iletme bildirimi oluşturur. Bildirimin cihaza itilmesi için kullanıcıların uygulamada oturum açmış olması gerekmez, ancak cihazın hedeflenen kullanıcı tarafından kaydedilmiş olması gerekir.
- Intune, Şirket Portalı uygulaması ve Microsoft Intune uygulaması, özel bir bildirimin teslimini garanti edemez. Özel bildirimler, her biri bir süre sonra, acil iletilerde kullanılmamalıdır.
- Intune 'dan gelen özel bildirim iletileri cihazlarda standart anında iletme bildirimleri olarak görünür. Şirket Portalı uygulaması bildirimi aldığında bir iOS/ıpados cihazında açıksa bildirim, sistem anında iletme bildirimi yerine uygulamada görüntülenir.  
- Özel bildirimler, cihaz ayarlarına bağlı olarak hem iOS/ıpados hem de Android cihazlarda kilit ekranlarında görülebilir.  
- Android cihazlarda, diğer uygulamaların özel Bildiriminizdeki verilere erişimi olabilir. Bunları hassas iletişimler için kullanmayın.  
- Son kaydedilmemiş veya bir gruptan kaldırılmış olan kullanıcıların bir cihaz kullanıcıları daha sonra bu gruba gönderilen özel bir bildirim alabilir.  Benzer şekilde, gruba özel bir bildirim gönderildikten sonra bir Kullanıcı eklerseniz, yeni eklenen kullanım için daha önce gönderilen bildirim iletisini almak mümkündür.  

## <a name="send-a-custom-notification-to-groups"></a>Gruplara özel bildirim gönder

1. Bildirim oluşturma ve gönderme izinlerine sahip bir hesapla [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) oturum açın ve **Kiracı Yönetimi** > **özel bildirimler**' e gidin.  

2. Temel bilgiler sekmesinde, aşağıdakileri belirtin ve devam etmek için **İleri** ' yi seçin.  
   - **Title** : Bu bildirim için bir başlık belirtin. Başlıklar 50 karakterle sınırlıdır.  
   - **Gövde** – iletiyi belirtin. İletiler 500 karakterle sınırlıdır.

   ![Özel bildirim oluşturma](./media/custom-notifications/custom-notifications.png)  

3. **Atamalar** sekmesinde, bu özel bildirimi göndermek istediğiniz grupları seçin ve ardından devam etmek için ileri ' yi seçin. Bir gruba bildirim gönderildiğinde yalnızca o grubun kullanıcıları hedeflenecek. bildirim, bu kullanıcı tarafından kaydedilen tüm iOS/ıpados ve Android cihazlarına gider.

4. **Gözden geçir + oluştur** sekmesinde, bilgileri gözden geçirin ve bildirimi göndermeye hazırsanız **Oluştur**' u seçin.  

Intune, hemen oluşturduğunuz iletileri işler. İletinin gönderildiği tek onay, özel bildirimin gönderildiğini doğrulayan Intune bildirimidir.  

![Gönderilen bildirim onayı](./media/custom-notifications/notification-sent.png)  

Intune, göndereceğiniz özel bildirimleri izlemez ve cihazlar, bilgileri cihazın Bildirim Merkezi dışında günlüğe kaydetmez. Kullanıcı Şirket Portalı veya Intune uygulaması içinde destek isterse, bildirim geçici bir tanılama günlüğünde bulunabilir.

## <a name="send-a-custom-notification-to-a-single-device"></a>Tek bir cihaza özel bildirim gönder

1. Bildirim oluşturma ve gönderme izinlerine sahip bir hesapla [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) oturum açın ve ardından **cihazlar** > **tüm cihazlar**' a gidin.

2. Bildirim göndermek istediğiniz yönetilen cihazın adına çift tıklayın, bu cihazlara *genel bakış* sayfasını açın.

3. Cihazlara **genel bakış** sayfasında özel **bildirim cihazı gönder** eylemini seçerek *özel bildirim gönder* bölmesini açın. Bu seçenek kullanılamıyorsa, sayfanın sağ üst tarafındaki **...** (üç nokta) seçeneğini belirleyin ve ardından **özel bildirim gönder**' i seçin.

4. **Özel bildirim gönder** bölmesinde aşağıdaki ileti ayrıntılarını belirtin:  

   - **Title** : Bu bildirim için bir başlık belirtin. Başlıklar 50 karakterle sınırlıdır.  
   - **Gövde** – iletiyi belirtin. İletiler 500 karakterle sınırlıdır.  

5. Cihaza özel bildirim göndermek için **Gönder** ' i seçin. Gruplara gönderdiğiniz bildirimlerin aksine, bir atama yapılandırmaz veya göndermeden önce iletiyi gözden geçirmezsiniz.  

Intune iletiyi hemen işler. İletinin gönderildiği tek onay, konsolunda alacağınız ve gönderdiğiniz iletinin metnini görüntüleyen Intune bildirimidir.  

## <a name="receive-a-custom-notification"></a>Özel bir bildirim alın

Bir cihazda, kullanıcılar Intune tarafından Şirket Portalı uygulamasından veya Microsoft Intune uygulamadan standart bir anında iletme bildirimi olarak gönderilen özel bildirim iletilerini görürler. Bu bildirimler, kullanıcıların cihazdaki diğer uygulamalardan aldığı anında iletme bildirimlerine benzer.  

İOS/ıpados cihazlarında, bildirim alındığında Şirket Portalı uygulama açıksa bildirim, anında iletme bildirimi yerine uygulamada görüntülenir.  

Bildirim, Kullanıcı tarafından kesilene kadar kalır.  

## <a name="next-steps"></a>Sonraki adımlar

[Cihazları yönetme](device-management.md)
