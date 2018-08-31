---
title: Şirkete ait veya şirketin sağladığı macOS cihazınızı yönetime kaydetme | Microsoft Docs
description: Kuruluşunuz tarafından satın alınan ve verilen bir macOS cihazının Intune'a nasıl kaydedildiği açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 272a82f7d3d62d117fa5506ccf446b3169ff514f
ms.sourcegitcommit: bb56ada81e6d4950f130415918c4acc455bb52dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43016236"
---
# <a name="get-your-company-owned-macos-device-managed"></a>Şirkete ait macOS cihazının yönetilmesini sağlama

Yeni macOS cihazının Intune'da otomatik olarak yönetilmesini nasıl sağlayacağınızı öğrenin.

İşe veya okula ait cihazlar genellikle size verilmeden önce yapılandırılır. Cihazınızı ilk kez açtığınızda ve oturum açtığınızda kuruluşunuz cihaza önceden yapılandırılmış ayarları gönderir. Cihazınızın kurulumu tamamlandıktan sonra, iş veya okul kaynaklarına erişim elde edersiniz. 

Yönetim kurulumuna başlamak için, cihazınızın güç düğmesini açın ve iş veya okul kimlik bilgilerinizle oturum açın. Bu makalenin kalan bölümünde Kurulum Yardımcısı'nda ilerlerken göreceğiniz adımlar ve ekranlar açıklanır.   

## <a name="what-is-apple-dep"></a>Apple DEP nedir?
Şirkete ait bir cihazınız varsa, bu cihaz Apple Aygıt Kayıt Programı'ndan (DEP) satın alınmış olabilir. Bazı kuruluşlar Apple DEP aracılığıyla çok büyük sayılarda iOS veya macOS cihazı satın alır. Ardından kuruluşlar bu cihazları Intune gibi tercih ettikleri mobil cihaz yönetim sağlayıcısında yapılandırabilir ve yönetebilir. Yöneticiyseniz ve Apple DEP hakkında daha fazla bilgi edinmek istiyorsanız, bkz. [macOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="set-up-your-macos-device"></a>macOS cihazınızı ayarlama  
macOS cihazınızı yönetime kaydetmek için aşağıdaki adımları tamamlayın. Şirkete ait bir cihaz yerine kendi cihazınızı kullanıyorsanız, [kişisel cihazlara ve kendi cihazını getir kapsamındaki cihazlara](enroll-your-device-in-intune-macos-cp.md) yönelik adımları izleyin.  

1. macOS cihazınızın güç düğmesini açın. 
2. **Dil** ayarınızı seçin ve **Devam**'a tıklayın.  

   ![Aralarından seçim yapılacak dil listesinin gösterildiği macOS cihazı Kurulum Yardımcısı Hoş Geldiniz ekranının görüntüsü.](./media/macos-dep-welcome-1808.png)   
3. Klavye düzenini seçin. Seçtiğiniz dil temelinde listede bir veya birden çok seçenek gösterilir. Hangi dili seçmiş olursanız olun, tüm düzen seçeneklerini görmek için **Tümünü Göster**'e tıklayın. İşiniz bittiğinde **Devam**'a tıklayın.  

   ![Aralarından seçim yapılacak listenin, işaretsiz Tümünü Göster seçeneğinin ve Geri ile Devam düğmesinin gösterildiği macOS cihazı Kurulum Yardımcısı Klayve Düzeni ekranının görüntüsü.](./media/macos-dep-keyboard-1808.png)  
4. Wi-Fi ağınıza seçin. Kuruluma devam etmek için İnternet bağlantınız olmalıdır. Ağınızı görmüyorsanız veya kablolu ağ üzerinden bağlanmanız gerekiyorsa, **Diğer Ağ Seçenekleri**'ne tıklayın. İşiniz bittiğinde **Devam**'a tıklayın.  

   ![Aralarından seçim yapılacak kullanılabilir ağlar listesinin gösterildiği macOS cihazı Kurulum Yardımcısı Wi-Fi Ağınızı Seçin ekranının görüntüsü. Ayrıca Diğer Ağ Seçenekleri düğmesi, Geri Düğmesi ve Devam düğmesi de gösterilir.](./media/macos-dep-wifi-1808.png)  
5. Wi-Fi bağlantısı kurduktan sonra, **Uzaktan Yönetim** ekranı görüntülenir. Uzaktan yönetim, kuruluşunuzun yöneticisinin cihazınızı şirketin gerektirdiği hesaplar, ayarlar, uygulamalar ve ağlarla uzaktan yapılandırmasına olanak tanır. Devam etmeden önce, cihazınızın nasıl yönetildiğini anlamanıza yardımcı olması için belgeleri okuyun. Ardından **Devam**'a tıklayın.  

   ![Uzaktan yönetimi açıklayan metin ve daha fazla bilgi sağlayan belgelerin bağlantısıyla, macOS cihazı Kurulum Yardımcısı Yönetim ekranının görüntüsü. Ayrıca Geri düğmesi ve Devam düğmesi de gösterilir.](./media/macos-dep-remote-management-1-1808.png)  
6. İstendiğinde, iş veya okul hesabınızla oturum açın. Kimliğiniz doğrulandıktan sonra, cihazınız bir yönetim profili yükler. Profil yapılandırılır ve kuruluşunuzun kaynaklarına erişmenize olanak tanır.  
7. Daha sonra kişisel bilgilerin ne zaman toplandığını belirleyebilmek için, Apple veri ve gizlilik simgesiyle ilgili bilgileri okuyun. Ardından **Devam**'a tıklayın.  

   ![El sıkışan iki kişinin çiziminin gösterildiği ve Apple'ın kişisel bilgileri kullanımının açıklandığı macOS cihazı Kurulum Yardımcısı Veri ve Gizlilik ekranının görüntüsü. Ayrıca Geri ve Devam düğmesi de gösterilir.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Cihazınız kaydedildikten sonra, tamamlamanız gereken ek adımlar olabilir. Gördüğümüz adımlar, kuruluşunuzun kurulum deneyimini nasıl özelleştirdiğine bağlıdır. Şunları yapmanızı gerektirebilir:
    * Apple hesabında oturum açma
    * Hüküm ve koşulları kabul etme
    * Bilgisayar hesabı oluşturma
    * Hızlı kurulumda ilerleme
    * Mac'inizi ayarlama  
## <a name="get-the-company-portal-app"></a>Şirket Portalı uygulamasını alma      
Cihazınıza Intune Şirket Portalı uygulamasını almak için App Store'a gidin. Uygulama, cihazınızı yönetimde izlemenize, eşitlemenize, eklemenize ve kaldırmanıza, ayrıca uygulamalar yüklemenize olanak tanır.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın.
