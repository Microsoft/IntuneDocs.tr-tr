---
title: Mac 'nizi Intune Şirket Portalı kaydetme | Microsoft Docs
description: Şirket Portalı App ile Mac 'i Intune 'a kaydetmeyi öğrenin.
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: kakyker
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f26594435689a4f7a178035264e006a497719d3e
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75205522"
---
# <a name="enroll-your-macos-device-using-the-company-portal-app"></a>Şirket Portalı uygulamasını kullanarak macOS cihazınızı kaydetme  

İş veya okul e-postanıza, dosyalarınıza ve uygulamalarınıza güvenli erişim kazanmak için macOS cihazınızı Intune Şirket Portalı uygulamasına kaydedin.

Kuruluşlar, özel verilere erişebilmek için genellikle cihazınızı kaydetmeniz gerekir. Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir. Cihazınızdaki iş veya okul bilgilerine sürekli erişim sağlamak için cihazınızı kuruluşunuzun ilke ayarlarıyla eşleşecek şekilde yapılandırmanız gerekir.  

Bu makalede, macOS için Şirket Portalı uygulamasının, kuruluşunuzun gereksinimlerini karşılamanız için cihazınızı kaydetmek, yapılandırmak ve sürdürmek üzere nasıl kullanılacağı açıklanır.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz

İlk kurulum sırasında Şirket Portalı uygulama oturum açmanızı ve kuruluşunuzla kimlik doğrulamasından geçmesini gerektirir. Şirket Portalı, kuruluşunuzun gereksinimlerini karşılamak için yapılandırmanız gereken cihaz ayarlarını size bildirir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.    

Cihazınızı kaydettikten sonra, Şirket Portalı cihazın kuruluşunuzun gereksinimlerine göre korunduğundan her zaman emin olur. Örneğin, güvenilir olmayan bir kaynaktan bir uygulama yüklerseniz, Şirket Portalı sizi uyarır ve kuruluşunuzun kaynaklarına erişimi kısıtlayabilir. Bunun gibi uygulama koruma ilkeleri yaygın bir uygulamadır. Erişimi yeniden kazanmak için, büyük olasılıkla güvenilmeyen uygulamayı kaldırmanız gerekecektir. 

Kayıt sonrasında, kuruluşunuz Multi-Factor Authentication gibi yeni bir güvenlik gereksinimini zorlarsa Şirket Portalı sizi uyarır. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-macos-device-managed"></a>MacOS cihazınızın yönetilmesini sağlayın  
MacOS cihazınızı kuruluşunuza kaydetmek için aşağıdaki adımları kullanın. Cihazınızın macOS 10,12 veya sonraki bir sürümü çalıştırması gerekir.   

> [!NOTE]
> Bu süreç boyunca, Şirket Portalı anahtarlığınıza depolanmış gizli bilgilerin kullanılmasına izin vermeniz istenebilir. Bu istemler Apple Security 'nin bir parçasıdır. İstemi aldığınızda, oturum açma Anahtarlık parolanızı yazın ve **her zaman Izin ver**' i seçin. Klavyenizde **ENTER** veya **Return** tuşuna basarsanız, Istem bunun yerine **izin ver**' i seçerek ek istemlere neden olabilir.  

### <a name="install-company-portal-app"></a>Şirket Portalı uygulamasını yükler  
1. Mac 'i [Kaydet](https://go.microsoft.com/fwlink/?linkid=853070)'e gidin.  
2. Şirket Portalı Installer. pkg dosyası indirilir. Yükleyiciyi açın ve adımlarla devam edin. 
3. Yazılım lisans sözleşmesini kabul edin. 
4. Yazılımı yüklemek için cihaz parolanızı veya kayıtlı parmak izini girin.  
5. Şirket Portalı açın. 

> [!IMPORTANT]
> Microsoft yazılımlarını güncelleştirmek için Microsoft otomatik güncelleştirme açılabilir. Tüm güncelleştirmeler yüklendikten sonra Şirket Portalı uygulamasını açın. En iyi kurulum deneyimi için en son Microsoft otomatik güncelleştirme ve Şirket Portalı sürümlerini kurun.  


### <a name="enroll-your-mac"></a>Mac 'nizi kaydetme  


1. İş veya okul hesabınızla Şirket Portalı için oturum açın.  
2. Uygulama açıldığında **Başlat**' ı seçin.  
3. Kuruluşunuzun kayıtlı cihazınızda neleri görebileceğini ve neleri görebileceklerini gözden geçirin. Sonra **Devam**'ı seçin.
4.  İstenirse, **Yönetim profili yüklemesi** ekranında cihaz parolanızı girin.

    ![Şirket Portalı örnek ekran görüntüsü, yönetim profilini yükler ekranı, parola istemi 'ni vurgular.](./media/install-management-profile-macos-1912.PNG)   
5. **Cihaz yönetimini Onayla** ekranında **sistem tercihlerini aç**' ı seçin.  

    ![Cihaz yönetimini Onayla ekranının örnek ekran görüntüsü, "sistem tercihlerini aç" düğmesini vurgulıyorum.](./media/confirm-device-management-macos-1912.PNG)  
6. Cihazınızın sistem tercihleri açılır. Cihaz profilleri listesinden **Yönetim profili** ' **ni seçin ve ardından Onayla > Onayla** ' yı **seçin.**  
    Sistem Tercihleri, Yönetim profili ekranının, "Onayla" düğmesinin örnek ekran görüntüsünü ![.](./media/management-profile-approve-macos-1912.PNG)   
1. Şirket Portalı dönün ve **devam**' ı seçin.    
2. Kuruluşunuz, cihaz ayarlarınızı güncelleştirmenizi gerektirebilir. Ayarları güncelleştirmeyi tamamladığınızda **ayarları denetle**' yi seçin.  

    ![Şirket Portalı örnek ekran görüntüsü, cihaz ayarlarını güncelleştirme ekranının "ayarları denetle" düğmesinin vurgulanması.](./media/update-settings-mac-1911.PNG)  
9. Kurulum tamamlandığında **bitti**' yi seçin.  


 ## <a name="troubleshooting-and-feedback"></a>Sorun giderme ve geri bildirim   

Kayıt sırasında sorunlarla karşılaşırsanız, Microsoft uygulama geliştiricilerine sorunu bildirmek için **yardım** > **Tanılama raporu gönder** ' e gidin. Bu bilgiler, uygulamanın iyileştirilmesine yardımcı olmak için kullanılır. Bu bilgiler ayrıca, BT 'nin yardım almak için BT 'yi desteklemesi durumunda sorunu çözmeye yardımcı olması için de kullanılır.  

Sorunu Microsoft 'a bildirdikten sonra, deneyiminizin ayrıntılarını BT destek sorumlunuza gönderebilirsiniz. **E-posta ayrıntılarını**seçin. E-postanın gövdesinde karşılaştığınız şeyleri yazın. Destek sorumlunuza ait e-posta adresini bulmak için Şirket Portalı App > **Contact**adresine gidin. Veya [Şirket portalı Web sitesini](https://go.microsoft.com/fwlink/?linkid=2010980)denetleyin.  
 

Ayrıca, Microsoft Intune Şirket Portalı ekibi görüşlerinizi duymak için çok sevecekti. **Yardım** > düşüncelerinizi ve fikirlerinizi paylaşmak Için **geri bildirim gönder** ' e gidin.  

## <a name="unverified-profiles"></a>Doğrulanmamış profiller  
Yüklü mobil cihaz yönetimi (MDM) profillerini **sistem tercihleri** > **profillerinde**görüntülediğinizde, bazı profiller doğrulanmamış bir durum gösterebilir. Yönetim profilinde doğrulanmış bir durum olduğu sürece, endişelenmeniz gerekmez.  

MDM kanalı bağlantısını tanımlayan yönetim profilidir. Yönetim profili doğrulanmadığı sürece, bu kanal aracılığıyla makineye teslim edilen diğer profiller, yönetim profilinin güvenlik nitelikleri de devralınır.  

## <a name="updating-the-company-portal-app"></a>Şirket Portalı uygulamasını güncelleştirme

Şirket Portalı uygulamasının güncelleştirilmesi, macOS için Microsoft otomatik güncelleştirme aracılığıyla diğer Office uygulamaları ile aynı şekilde yapılır. [MacOS Için Microsoft uygulamalarını güncelleştirme](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1)hakkında daha fazla bilgi edinin.  

## <a name="next-steps"></a>Sonraki Adımlar  
Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  


