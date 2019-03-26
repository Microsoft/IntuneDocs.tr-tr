---
title: Intune Şirket portalı için Android Cihazınızı şifrelemenizi | Microsoft Docs
description: Bir Android cihazında cihaz şifrelemeyi etkinleştirmek için adımları
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ad953049b9d2efd6f7a828ee70b5e1cede4ee68
ms.sourcegitcommit: d0749cbc68df41893742f5187ac378a5ade824f2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58406257"
---
# <a name="encrypt-your-android-device"></a>Android Cihazınızı şifreleme

Cihazınız kaybolur veya çalınırsa, cihaz şifreleme, dosya ve klasörlerinizi yetkisiz erişime karşı korur. Cihaz şifreleme etkinleştirdikten sonra sadece bireyleri doğru parolayı veya PIN'i ile cihazınıza oturum açmak mümkün olacaktır. 

Okul veya iş kaynaklarına erişebilmeniz için önce kuruluşunuzun Android Cihazınızı şifrelemenizi gerektirebilir. Varsayılan olarak, bazı yeni Android cihazları şifrelenmiş kullanıma hazır.  

Şirket portalı Cihazınızı şifrelemek için gereken bir ileti alırsanız, aşağıdaki adımları tamamlayın. 

> [!Note]
> Huawei, Vivo ve OPPO belirli Android cihazlar şifrelenemez. Daha fazla bilgiyi [burada](your-device-appears-encrypted-but-cp-says-otherwise-android.md) bulabilirsiniz.  

1.  Bir cihaz ekran kilidi ayarlayın.  
    a. Git **ayarları** > **kilit ekranı ve güvenlik** > **ekran kilidi türünü**.  
    b. Şunlardan birini seçin **PIN**, **parola**, veya **deseni**.  
    c. Ekran kilidinizi yapılandırmak için ekrandaki yönergeleri izleyin.  

2. Geri Git **kilit ekranı ve güvenlik** seçip **güvenli başlangıç**.
3. Seçin **cihazı açtığında PIN gerektir** > **Tamam**.
4. Onayla ve Cihazınızı şifrelemek için bir PIN kodunuzu girin.
5. Şirket portalı uygulamasını açın, Cihazınızı seçin ve dokunun **cihaz ayarlarını denetle**.  

Android 4.4 ve önceki sürümleri çalıştıran cihazlara sahip olmayabilirsiniz **güvenli başlatma** seçeneği. Bu durumda, Cihazınızı şifrelemek için aşağıdaki adımları tamamlayın.

1. Git **ayarları** > **güvenlik** > **Cihazınızı şifrelemenizi**. Ekranda etiketleri Android cihazlar arasında farklılık gösterir. Görmüyorsanız **cihazı şifrele** seçeneğinde, iade:
    * **Depolama** > **depolama şifrelemesi**
    * **Depolama** > **kilit ekranı ve güvenlik** > **diğer güvenlik ayarları** 

2. Ekrandaki yönergeleri takip edin. Şifreleme sırasında cihazınız birkaç kez yeniden başlatılması.
3. Şirket portalı uygulamasını açın, Cihazınızı seçin ve dokunun **cihaz ayarlarını denetle**.  

## <a name="troubleshoot"></a>Sorun giderme  
**Sorunu**: Cihazınızı zaten şifrelediyseniz ve

- Şifreleme düğmesi devre dışı.
- Yine de şifrelemeniz gerektiğini bildiren bir iletiyle karşılaşıyorsunuz.
- Şirket Portalı uygulamasını kullanmaya çalışırken hatayla karşılaşıyorsunuz.

**Bunları deneyin:**

- Cihazınızın şarjının dolu olduğundan ve prize takılı olduğundan emin olun.  
- Cihazınızda bir PIN veya parola ayarladığınızdan emin olun.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  
