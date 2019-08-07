---
title: Şirketin sağladığı macOS cihazınızı yönetime kaydetme | Microsoft Docs
description: Kuruluşunuz tarafından satın alınan ve verilen bir macOS cihazının Intune'a nasıl kaydedildiği açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 273342f7181bcc577a44126404d145ca9b5bff3e
ms.sourcegitcommit: e6edfbfd63dd7c2500ce1123205aa2af9a7e8e2e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/05/2019
ms.locfileid: "68783031"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Kuruluş tarafından sağlanan macOS cihazınızı yönetime kaydedin

Yeni macOS cihazınızı Intune yönetimine kaydetmeyi öğrenin.  

İş veya okul tarafından sağlanan cihazlar genellikle elinize ulaşmadan önce yapılandırılmış olur. Cihazınızı ilk kez açtığınızda ve oturum açtığınızda kuruluşunuz cihaza bu önceden yapılandırılmış ayarları gönderir. Cihazınızın kurulumu tamamlandıktan sonra, iş veya okul kaynaklarınıza erişim elde edersiniz. 

Yönetim kurulumuna başlamak için, cihazınızın güç düğmesini açın ve iş veya okul kimlik bilgilerinizle oturum açın. Bu makalenin kalan bölümünde Kurulum Yardımcısı'nda ilerlerken göreceğiniz adımlar ve ekranlar açıklanır.   

## <a name="what-is-apple-dep"></a>Apple DEP nedir?
Kuruluşunuz cihazlarını *Apple Aygıt Kayıt Programı* (DEP) adı verilen bir hizmet yoluyla satın almış olabilir. Apple DEP, kuruluşların çok sayıda iOS veya macOS cihaz satın almasına imkan tanır. Ardından kuruluşlar bu cihazları Intune gibi tercih ettikleri bir mobil cihaz yönetim sağlayıcısında yapılandırabilir ve yönetebilir. Yöneticiyseniz ve Apple DEP hakkında daha fazla bilgi edinmek istiyorsanız bkz. [macOS cihazları Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="get-your-device-managed"></a>Cihazınızı yönetime kaydetme 
macOS cihazınızı yönetime kaydetmek için aşağıdaki adımları tamamlayın. Kuruluş tarafından sağlanan bir cihaz yerine kendi cihazınızı kullanıyorsanız, [kişisel cihazlara ve kendi cihazını getir kapsamındaki cihazlara](enroll-your-device-in-intune-macos-cp.md) yönelik adımları izleyin.  

1. macOS cihazınızın güç düğmesini açın. 
2. Ülkenizi/bölgenizi seçin ve **devam**' a tıklayın.  

   ![Aralarından seçim yapılacak dil listesinin gösterildiği macOS cihazı Kurulum Yardımcısı Hoş Geldiniz ekranının görüntüsü.](./media/macos-dep-welcome-1808.png)   
3. Klavye düzenini seçin. Listede, seçtiğiniz ülkeyi/bölgenizi temel alan bir veya daha fazla seçenek gösterilmektedir. Seçtiğiniz ülke/bölgeinizden bağımsız olarak tüm düzen seçeneklerini görmek için **Tümünü göster**' e tıklayın. İşiniz bittiğinde **Devam**'a tıklayın.  

   ![Aralarından seçim yapılacak listenin, işaretsiz Tümünü Göster seçeneğinin ve Geri ile Devam düğmesinin gösterildiği macOS cihazı Kurulum Yardımcısı Klayve Düzeni ekranının görüntüsü.](./media/macos-dep-keyboard-1808.png)  
4. Wi-Fi ağınıza seçin. Kuruluma devam etmek için İnternet bağlantınız olmalıdır. Ağınızı görmüyorsanız veya kablolu ağ üzerinden bağlanmanız gerekiyorsa, **Diğer Ağ Seçenekleri**'ne tıklayın. İşiniz bittiğinde **Devam**'a tıklayın.  

   ![Aralarından seçim yapılacak kullanılabilir ağlar listesinin gösterildiği macOS cihazı Kurulum Yardımcısı Wi-Fi Ağınızı Seçin ekranının görüntüsü. Ayrıca Diğer Ağ Seçenekleri düğmesi, Geri Düğmesi ve Devam düğmesi de gösterilir.](./media/macos-dep-wifi-1808.png)  
5. Wi-Fi bağlantısı kurduktan sonra, **Uzaktan Yönetim** ekranı görüntülenir. Uzaktan yönetim, kuruluşunuzun yöneticisinin cihazınızı şirketin gerektirdiği hesaplar, ayarlar, uygulamalar ve ağlarla uzaktan yapılandırmasına olanak tanır. Cihazınızın nasıl yönetildiğini anlamanıza yardımcı olması için uzaktan yönetim açıklamasını okuyun. Daha sonra **Devam**’a tıklayın.  

   ![Uzaktan yönetimi açıklayan metin ve daha fazla bilgi sağlayan belgelerin bağlantısıyla, macOS cihazı Kurulum Yardımcısı Yönetim ekranının görüntüsü. Ayrıca Geri düğmesi ve Devam düğmesi de gösterilir.](./media/macos-dep-remote-management-1-1808.png)  
6. İstendiğinde, iş veya okul hesabınızla oturum açın. Kimliğiniz doğrulandıktan sonra cihazınız bir yönetim profili yükler. Profil yapılandırılır ve kuruluşunuzun kaynaklarına erişmenize olanak tanır.  
7. Daha sonra kişisel bilgilerin ne zaman toplandığını belirleyebilmek için, Apple veri ve gizlilik simgesiyle ilgili bilgileri okuyun. Ardından **Devam**'a tıklayın.  

   ![El sıkışan iki kişinin çiziminin gösterildiği ve Apple'ın kişisel bilgileri kullanımının açıklandığı macOS cihazı Kurulum Yardımcısı Veri ve Gizlilik ekranının görüntüsü. Ayrıca Geri ve Devam düğmesi de gösterilir.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Cihazınız kaydedildikten sonra, tamamlamanız gereken ek adımlar olabilir. Gördüğümüz adımlar, kuruluşunuzun kurulum deneyimini nasıl özelleştirdiğine bağlıdır. Şunları yapmanızı gerektirebilir:
    * Apple hesabında oturum açma
    * Hüküm ve koşulları kabul etme
    * Bilgisayar hesabı oluşturma
    * Hızlı kurulumda ilerleme
    * Mac'inizi ayarlama  
## <a name="get-the-company-portal-app"></a>Şirket Portalı uygulamasını alma      
Cihazınızda Mac OS için Intune Şirket Portalı uygulamasını indirin. Uygulama, cihazınızı yönetimde izlemenize, eşitlemenize, eklemenize ve kaldırmanıza, ayrıca uygulamalar yüklemenize olanak tanır. Bu adımlar ayrıca cihazınızı Şirket Portalı'na kaydetmeyi de anlatmaktadır.  
1. Mac OS cihazınızda https://portal.manage.microsoft.com/EnrollmentRedirect.aspx adresine açın.
2. İş veya okul hesabınızla Şirket Portalı web sitesinde oturum açın. 
3. Mac OS için Şirket Portalı yükleyicisini indirmek için **Uygulamayı Al**'a tıklayın.
4. İstendiğinde .pkg dosyasını açın ve yükleme adımlarını tamamlayın.
4. Şirket Portalı’nı açın ve iş veya okul hesabınızla oturum açın.
5. Cihazınızı bulun ve **Kaydol**'a tıklayın.
6. **Devam** > **Bitti**'ye tıklayın. Cihazınız artık Şirket Portalı uygulamasında kurumsal ve uyumlu bir cihaz olarak görünmelidir.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
