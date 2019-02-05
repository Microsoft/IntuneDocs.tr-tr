---
title: Şirket Portalı ile macOS cihazınızı Intune’a kaydetme | Microsoft Docs
description: Bir macOS cihazın Şirket Portalı ile Intune’a nasıl kaydedildiği açıklanır
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d54c778923b0d217187f6e4c70e4bc8730788fbc
ms.sourcegitcommit: dde9e1e1d15c412751a186410c2a04974ff1b102
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690810"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Şirket Portalı uygulaması ile macOS cihazınızı Intune’a kaydetme

macOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Kuruluşlar çoğu zaman cihazınızın özel verilere erişmesi için yönetilmesini gerektirir. Bir cihaz yönetilmeye başladığında kuruluşlar, mobil cihaz yönetimi sağlayıcısı yoluyla cihaza ilke ve uygulama gönderebilir. Cihazınızdan iş veya okul bilgilerine sürekli erişim edinmek için cihazınızı ilke ayarlarına uyum sağlayacak şekilde yapılandırmanız gerekir.  

Bu makale, cihazınızın kuruluş gereksinimlerine uyum sağlaması amacıyla macOS için Intune Şirket Portalı uygulamasının cihazı kaydetmenize, yapılandırmanıza ve cihaz bakımını yapmanıza nasıl yardımcı olduğunu açıklar.

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz

İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra yapmanız gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.    

Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bunun gibi uygulama koruma ilkeleri, kuruluşlarda yaygın olarak kullanılır ve erişimi geri almanız için güvenilmeyen uygulamaları kaldırmanızı gerektirir.

Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md).  

## <a name="get-your-device-managed"></a>Cihazınızı yönetime kaydetme  
OS X El Capitan 10.11 ve sonrasını çalıştıran macOS cihazları kaydetmek için aşağıdaki adımları kullanın.   


1. Şirket Portalı web sitesine erişmek için __Safari__’de yeni bir pencere açın ve https://portal.manage.microsoft.com adresine gidin.  

2. İş veya okul hesabınızla Şirket Portalı web sitesinde oturum açın.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Sayfanın sol üst köşesine gidin ve **Menü** > **Cihazlar**’a tıklayın.  

4. __Cihazlar__ sayfasında yönetilen cihazlar listesi veya bir başlık görüntülenir. Göreceğiniz şey, yönetilen bir cihazınız olup olmamasına bağlıdır. 
    * Listede olmayan bir cihazı eklemek için **Hangi cihazı kullandığınızı bizimle paylaşmak veya yeni bir cihaz eklemek için buraya dokunun** yazılı başlığı seçin.
    * Herhangi bir cihaza yoksa, başlık okur: **Yönetilen cihazınız yok. Buraya dokunup cihazı ekleyin.** Cihazınızı eklemek için başlığa tıklayın.  

     ![Tıklanacak yeri vurgulamak için başlık seçeneği etrafında kırmızı kare bulunan Cihazlar sayfasının ekran görüntüsü.](./media/CP-enroll-MACOS-1808.png)  
5.  Aşağıdaki adımlardan hangisi Şirket Portalı’nda görmekte olduğunuz iletiyle eşleşiyorsa onu tamamlayın.  
    * Bir cihazı ilk kez ekliyorsanız cihaza Şirket Portalı uygulamasını indirmeniz istenir. **İndir**’e tıklayarak devam edin.  

         ![macOS Şirket Portalı uygulamasını indirme istemi örnek ekran görüntüsü. Kullanıcının, istemin sol altındaki mavi renkli İndir düğmesine veya sağ altındaki gri renkli İptal düğmesine basma seçeneği vardır.](./media/CP-enroll-download-macOS-1808.png)  

    * Zaten yönetilen bir macOS cihazınız varsa, mevcut yönetilen cihazlarınızın listesini içeren bir istem alırsınız. **Cihazım burada listelenmemiş** > **İndir**’i seçerek eklemekte olduğunuz cihaza Şirket Portalı uygulamasını indirin.  

         ![macOS Şirket Portalı uygulamasını indirme istemi örnek ekran görüntüsü. Kullanıcı, *Cihazım burada listelenmemiş* seçeneğini veya sayfasının ortasından belirli bir cihazı seçebilir. İstemin sol altında mavi renkli bir İndir düğmesi ve sağ altında gri renkli bir İptal düğmesi belirir](./media/cp-mac-os-device-isnt-here-1808.png)  

6. Cihazınız, **CompanyPortal.pkg** yükleme dosyasını açmanın güvenli olup olmadığını denetleyecektir. Denetim tamamlandıktan sonra yükleyicisi açın ve yüklemeyi tamamlayın.  

7. Yükleyici tamamlandığında **Başlatma çubuğuna** gidin ve **Şirket Portalı**’nı açın.  

8. macOS cihazınız, Şirket Portalı uygulamasını açmak istediğinizi onaylamanızı ister. Tıklayın **açık**.  

   > [!TIP]
   > Cihazınızın, kuruluşunuzun kaynaklarına erişmek için yeterli güvenliğe sahip olduğunu doğrulamak için Intune'un bilgisayarınıza erişmesi gerekir. Bilgisayarınız Şirket Portalı uygulamasını açmazsa [ağ geçidi denetleyicisini kapatın](https://support.apple.com/HT202491). Ardından uygulamayı açın.

9. Şirket Portalı’nda ilk göreceğiniz ekran, **oturum açmanızı** ister. Şirket Portalı web sitesinde oturum açarken kullandığınız iş veya okul hesabını kullanın.

10. Şirket Portalı hesap bilgilerinizi onaylar ve **Cihaz Kaydı** ve **Cihaz Uyumluluğu** durumlarınızı gösterir. Okul veya iş için macOS cihazınızı güvenlik altına almak adına uygulamanız gereken eylemler, sarı üçgenlerle vurgulanır. Kayda başlamak için **Başla**’ya tıklayın. 

11. İstenirse bilgisayarınızın oturum açma bilgilerini yazın.  

Cihazınızı yönetime kaydetmek birkaç dakika alabilir. Bu süre boyunca cihazınızda başka şeyler yapabilirsiniz. Şirket Portalı kurulumu tamamlandıktan sonra işiniz bittiğine dair bir ileti alırsınız.  

## <a name="unverified-profiles"></a>Doğrulanmamış profiller
MacOS cihazınızda yüklü mobil cihaz yönetimi (MDM) profillerini görüntülediğinizde, bazı profiller bir **Doğrulanmamış** durumu gösterebilir. **Yönetim profili** bir **Doğrulandı** durumu gösterdiği sürece kaygılanmanız gerekmez.  

MDM kanalı bağlantısını tanımlayan yönetim profilidir. Yönetim profili doğrulandığı sürece bu kanal yoluyla makineye teslim edilen profiller yönetim profilinin güvenlik özelliklerini devralır.

Ayrıca, bu diğer profiller bireysel doğrulama gerektirmediğinden bunlar daha hızlı oluşturulur ve cihazlara teslim edilir. 

## <a name="updating-the-company-portal-app"></a>Şirket Portalı uygulamasını güncelleştirme

Şirket Portalı uygulamasını güncelleştirmek, diğer Office uygulamalarında olduğu gibi Mac için Microsoft AutoUpdate yoluyla yapılır. [Buraya tıklayarak macOS için Microsoft uygulamalarını güncelleştirme](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1) hakkında daha fazla bilgi edinin.  

## <a name="next-steps"></a>Sonraki Adımlar  
Ek Yardım mı gerekiyor? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  


