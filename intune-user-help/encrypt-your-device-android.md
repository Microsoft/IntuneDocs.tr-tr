---
title: Intune için Android cihazını şifreleme | Microsoft Docs
description: Intune için gerektiğinde Android cihaz şifrelemesini açma adımları
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2965d6a017d92bd4535a29a2257c0cac5e6deaf
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506355"
---
# <a name="encrypting-your-android-device"></a>Android cihazınızı şifreleme

Cihazınız kaybolur veya çalınırsa, cihaz şifreleme, dosyalarınızı ve klasörlerinizi yetkisiz erişimden korur. Cihaz şifrelemesini etkinleştirdikten sonra, yalnızca doğru parolaya veya PIN 'e sahip kişiler cihazınızda oturum açabilirler. 

Okul veya iş kaynaklarına erişebilmek için kuruluşunuz, Android cihazınızı şifrelemenizi gerektirebilir. Yeni bazı Android cihazlar varsayılan olarak, kullanıma hazır olarak şifrelenir.  

## <a name="turn-on-encryption"></a>Şifrelemeyi aç

Şirket Portalı veya Microsoft Intune uygulama cihazınızı şifrelemenizi isterse, aşağıdaki adımları uygulayın. 

> [!Note]
> Huawei, vivo ve OPPO 'dan gelen belirli Android cihazları şifrelenemez. Daha fazla bilgiyi [burada](your-device-appears-encrypted-but-cp-says-otherwise-android.md) bulabilirsiniz.  

1. Bir cihaz ekranı kilidi ayarlayın.  
    a. **Ayarlar** > **kilit ekranı ve güvenlik** > **ekran kilit türü**' ne gidin.  
    b. **PIN**, **parola**veya **model**seçeneklerinden birini belirleyin.  
    c. Ekran kilitinizi yapılandırmak için ekrandaki yönergeleri izleyin.  

2. **Kilit ekranı ve güvenlik** bölümüne dönüp **güvenli başlatma**' yı seçin.
3. Cihaz > **Tamam ' ı** **açtığında PIN gerektir '** i seçin.
4. Cihazınızı doğrulamak ve şifrelemek için PIN 'inizi girin.
5. Şirket Portalı veya Microsoft Intune uygulamasını açın.
    * Şirket Portalı kullanıcılar: cihazınızı seçin ve **cihaz ayarlarını denetle**' ye dokunun. 
    * Microsoft Intune kullanıcılar: sayfa güncellene kadar beklemeniz gerekir, ancak bunu yaparken şifreleme durumunuz uyumlu olarak değiştirilmelidir.  

Android 4,4 ve öncesini çalıştıran cihazlarda **güvenli başlangıç** seçeneği bulunmayabilir. Bu durumda, cihazınızı şifrelemek için aşağıdaki adımları izleyin.

1. **Ayarlar** > **güvenlik** > **cihazı şifreleme**' ye gidin. Ekran etiketleri, Android cihazlar arasında farklılık gösterir. **Cihaz şifreleme** seçeneğini görmüyorsanız, iade edin:
    * **Depolama** > **depolama şifrelemesi**
    * **Depolama** > **kilit ekranı ve güvenlik** > **diğer güvenlik ayarları** 

2. Ekrandaki yönergeleri takip edin. Şifreleme sırasında, cihazınız birkaç kez yeniden başlatılabilir.
3. Şirket Portalı veya Microsoft Intune uygulamasını açın.
    * Şirket Portalı kullanıcılar: cihazınızı seçin ve **cihaz ayarlarını denetle**' ye dokunun.  
    * Microsoft Intune kullanıcılar: sayfa güncellene kadar beklemeniz gerekir, ancak bunu yaparken şifreleme durumunuz uyumlu olarak değiştirilmelidir.

## <a name="troubleshoot"></a>Sorun giderme  
**Sorun**: cihazınızı zaten şifreledi ve

- Şifreleme düğmesi devre dışı.
- Yine de şifrelemeniz gerektiğini bildiren bir iletiyle karşılaşıyorsunuz.
- Şirket Portalı veya Microsoft Intune uygulamasını kullanmaya çalışırken hata alırsınız.

**Bunları deneyin:**

- Cihazınızın şarjının dolu olduğundan ve prize takılı olduğundan emin olun.  
- Cihazınızda bir PIN veya parola ayarladığınızdan emin olun.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  
