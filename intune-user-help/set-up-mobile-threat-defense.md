---
title: Mobil cihazınıza mobil tehdit savunması 'nı yükler
description: Mobil cihazınıza mobil tehdit savunması yüklemeyi öğrenin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f395a9cedc72a8184cfe3e29d6fcd3117a1473d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72987451"
---
# <a name="install-mobile-threat-defense"></a>Mobil tehdit savunması 'nı yükler   

Kuruluşunuzun güvenlik gereksinimlerinin bir parçası olarak, bir Mobile Threat Defense (MTD) satıcı uygulaması yüklemenize gerek duyabilirsiniz. Bu tür bir uygulama, cihazınızdaki şüpheli uygulamalar, ağlar veya işletim sistemi güvenlik açıkları gibi tehditleri algılar ve sizi uyarır.  

Gerekli MTD uygulamanız yoksa, iş veya okul hesabınızla korunan uygulamalarda oturum açmanız engellenir. Bu makalede, engeli kaldırılacak [BIR MTD uygulamasını nasıl yükleyeceğinizi](set-up-mobile-threat-defense.md#install-app) öğreneceksiniz.  

Yüklemek için kullanabileceğiniz çeşitli MTD satıcı uygulamaları vardır; Kuruluşunuz hangisini kullanacağınızı bilmenizi sağlayacak. 


## <a name="information-your-organization-can-see"></a>Kuruluşunuzun görebileceği bilgiler   

Kuruluşunuz, kişisel uygulamalarınızda metin, e-posta ve resim gibi verileri göremez. MTD uygulaması, uygulamalarınız hakkında ad ve sürüm gibi bilgileri kuruluşunuza bildirir. Bildirilen gerçek bilgiler, şirketinizin kullandığı MTD satıcısına bağlıdır. Kuruluşunuz şunları görebilir:   

* Uygulama adı  
* Uygulama KIMLIĞI: Google Play içinde uygulamayı tanımlayan benzersiz ad.  
* Uygulama sürümü ve kısa sürüm numarası: bir uygulama için belirli sürüm numaraları.  
* Uygulama paketi ve dinamik Boyut: bir uygulamanın cihazınızda kullandığı alan miktarı. 


## <a name="install-app"></a>Uygulamayı yükleme    
Korumalı bir uygulamada oturum açtığınızda, otomatik olarak bir MTD uygulaması kurmanız istenir. Yüklemeyi tamamlamaya yönelik ekrandaki adımları izleyin. Ek Yardım için bu bölümdeki adımları kullanın.  
 
Cihazınızı kaydetmeniz de istenebilir. Kayıt, kimliğinizi doğrulamak ve okul veya iş hesabınızı cihazınıza bağlamak için gereklidir. Kaydolmadıysanız, MTD uygulamasını yüklemeden önce bu kurulum üzerinden otomatik olarak gezinirsiniz. **Erişim al** ekranına geldiğinizde, yükleme adımlarını başlatabilirsiniz.  

Cihaz kaydı hakkında daha fazla bilgi için bkz. [kuruluşunuzun ağına kişisel cihazınızı kaydetme](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network).  

### <a name="ios-setup"></a>iOS kurulumu  

1. **Erişim al** ekranında, kuruluşunuzun gerektirdiği MTD uygulamasını yüklemek için yönergeleri izleyin.   
2. **Erişim al** ekranına dönün ve **Aç**' ı seçin.  
3. MTD uygulaması Microsoft Authenticator açmak için izin ister. **Aç**'ı seçin. 
4. Oturum açmak için iş hesabınızı seçin. 
5. MTD uygulaması cihazınızı güvenlik tehditleri için taradığında bekleyin. 
6. İlk olarak erişmeye çalıştığınız okul veya iş uygulamasına geri dönün. Bu noktada, kuruluşunuz PIN oluşturma gibi diğer uygulama güvenlik gereksinimlerini yapılandırmanızı isteyebilir.   
7. Artık uygulamaya erişiminizin olması gerekir. Hala bloke ediyorsanız:  
    * **Erişim al** ekranında yeniden **Denetle**' yi seçin.  
    * MTD uygulamasına gidin ve mevcut tehditleri denetleyin. Tehdidi çözümlemek ve erişimi yeniden kazanmak için önerilen adımları izleyin.    

### <a name="android-setup"></a>Android kurulumu 

1. **Erişim al** ekranında, kuruluşunuzun gerektirdiği MTD uygulamasını yüklemek için yönergeleri izleyin.  
2. **Erişim al** ekranına dönün ve **Aç**' ı seçin.  
3. MTD uygulaması, cihazınızın belirli alanlara erişmesi için izin ister. Bu uygulamanın düzgün çalışması için kişilere erişime **Izin vermeniz** gerekir. İstenen izinler, MTD satıcıları genelinde farklılık gösterir.  
4. Oturum açmak için iş hesabınızı seçin.  
5. MTD uygulaması cihazınızı güvenlik tehditleri için taradığında bekleyin.  
6. İlk olarak erişmeye çalıştığınız okul veya iş uygulamasına geri dönün. Bu noktada, kuruluşunuz PIN oluşturma gibi diğer uygulama güvenlik gereksinimlerini yapılandırmanızı isteyebilir.  
7. Artık uygulamaya erişiminizin olması gerekir. Hala bloke ediyorsanız:  
    * **Erişim al** ekranında yeniden **Denetle**' yi seçin.  
    * MTD uygulamasına gidin ve mevcut tehditleri denetleyin. Tehdidi çözümlemek ve erişimi yeniden kazanmak için önerilen adımları izleyin.  

### <a name="installation-failed"></a>Yükleme başarısız oldu  

Yükleme başarısız olursa BT destek sorumlunuza başvurun. Kuruluşunuzun iletişim bilgilerini bulmak için [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) gidin.  

Uygulama günlüklerinizi, yükleme hakkında daha fazla bağlam sağlamak için BT destek sorumlunuza da gönderebilirsiniz.  
* Android kullanıcıları: Şirket Portalı [günlüklerinizi karşıya yükleyin ve e-posta ile gönderin](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) .   

* iOS cihaz kullanıcıları: iOS için Microsoft Edge 'ten [günlüklerinizi alın ve gönderin](https://docs.microsoft.com/intune/apps/manage-microsoft-edge#use-microsoft-edge-on-ios-to-access-managed-app-logs) .  

## <a name="resolve-a-threat"></a>Tehdidi çözümleyin  
Bir tehdit kuruluşunuzun tanımlı tehdit düzeyini aşarsa, kuruluşunuzun şunları yapmanız gerekir:  
   
* Erişimi engelle: iş veya okul hesabınızda oturum açtığınızda kuruluşunuzun korunan uygulamalarını kullanmanızı engeller.  
* Verileri silme: kuruluşunuzun korunan uygulamalarından bir veya daha fazla iş veya okul verilerini siler.  

Bir tehdidi çözümlemek ve erişimi yeniden kazanmak için cihazınızda MTD uygulamasını açın. Tehdidin cihazınızı nasıl etkileyebileceğini ve nasıl çözümleneceğini öğrenmek için, belirtilen bilgileri okuyun. Tehdidi çözümlemek için adımları izledikten sonra MTD uygulamasına dönün ve yeni bir tarama başlatın. Kuruluşunuza yeniden erişim kazanmak birkaç dakika sürebilir.  

## <a name="next-steps"></a>Sonraki adımlar  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.

