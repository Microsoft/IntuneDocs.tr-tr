---
title: Şirket kaynaklarına iOS cihaz erişimini ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d0c7ac239a67a51ba7165771206883f3c46f5f55
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61498186"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Şirket kaynaklarınıza iOS cihaz erişimi ayarlayın  

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Cihazınız kaydedildikten sonra bu duruma *yönetilen*. Kuruluşunuz, ilkeler ve uygulamalar, Intune gibi bir mobil cihaz Yönetimi (MDM) sağlayıcısı aracılığıyla cihaza atayabilirsiniz.  

İş veya Okul cihazınızdan bilgi erişimi korumak için cihazınızın, kuruluşunuzun tercih edilen ayarlarınızla eşleşecek şekilde yapılandırmanız gerekir. Bu makalede, cihaz, kaydetmek için Şirket portalı kullanmak ve kuruluşunuzun gereksinimlerine açıklar. 

> [!NOTE]
> Mail uygulamasında şirket e-postasına erişmeyi denediğinizde cihazınızı yönettirmeniz istendiyse, doğru yere geldiniz. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz  

### <a name="security"></a>Güvenlik  
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra güncelleştirmeniz gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.     

### <a name="protection"></a>Protection  
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bu tür bir ilke, kuruluşlarda yaygın bir durumdur ve genellikle erişebilmek önce güvenilmeyen uygulamayı kaldırma gerektirir.  

### <a name="setting-notifications"></a>Bildirimleri ayarlama  
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>İOS Cihazınızı kaydetme  

İndirmek ve yüklemek için mağazaya gidin [Intune Şirket portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) Cihazınızda. Bir Wi-Fi bağlantısını korumak ve kayıt sırasında Safari için erişiminiz olması gerekir. 

Kayıt sırasında birkaç dakika duraklatma kapatın veya Kurulumu sonlandırmak için uygulamayı neden olabilir. Bu durumda, Şirket portalı uygulamasını açın ve yeniden deneyin.  

1. Şirket portalı ve iş veya Okul hesabınızla oturum açın. 

    ![Örnek Şirket portalı uygulamasının, oturum açma ekran görüntüsü.](./media/ios-01-cp-enroll-1903.PNG)  

2. Şirket portalı bildirimleri almak isteyip istemediğiniz sorulduğunda dokunun **izin.** Şirket portalı bildirimleri gibi cihaz ayarlarınızı güncelleştirilmesi gerekiyorsa, sizi uyarmak için kullanır. 

    ![Şirket portalı giriş sayfasının "Bildirimler" istemi örnek ekran görüntüsü.](./media/ios-04-cp-enroll-1903.PNG)  

3. Üzerinde **erişimi ayarlama** ekranındayken **başlayın.**  

     ![Örnek Şirket portalı, "erişim ayarlama" ekran görüntüsü.](./media/ios-05-cp-enroll-1903.PNG)  

4. Kuruluşunuz görebileceği ve göremeyeceği cihaz bilgilerini listesi üzerinden okuyun. Ardından dokunun **devam**.  

5. Yönergeleri okuyup **sonraki nedir?** ekran. İndirin ve yönetim profili yüklemek dokunun hazır olduğunuzda **devam**.  

 > [!IMPORTANT]
> Bu sonraki adımları ve ekranlar, iOS sürümüne göre farklılık gösterir. İOS sürümünüze uygun adımları izleyin. 

6. Safari'nin Cihazınızda Şirket portalı Web sitesini açar. Yapılandırma profilini indirmek için istendiğinde dokunun **izin**. Çalıştıran bir cihazda kullanıyorsanız:  
    * iOS 12.2 ve daha sonra: Yükleme tamamlandığında, dokunun **bitti.** Bu makalede adım 7'için devam edin.
    * iOS 12,1 ve önceki sürümler: Otomatik olarak ayarlar uygulamasına yönlendirilirsiniz. Bu makalede 8 adıma atlayın.  
 
    Yanlışlıkla dokunursanız **Yoksay**, sayfayı yenileyin. Şirket portalı uygulamasını açın istenir. Uygulamadan öğesine dokunarak **yeniden indirmeniz**.

  > [!NOTE]
  > Sonraki adımlarda bu indirme, 8 dakika içinde anlatıldığı gibi yönetim profili yüklemeniz gerekir. Aksi takdirde profili kaldırılacak ve kayıt'ı yeniden başlatmanız gerekir.  

7. iOS 12.2 ve üzeri içindir: Şirket portalı'nı açmak isteyip istemediğiniz sorulduğunda dokunun **açın**. **Yönetim profilini yükleme** ekran profili yüklemek için adımları listeler.

    ![Örnek Şirket portalı, yönetim profilini yükleme ekran görüntüsü.](./media/ios-1904-settings-icon.PNG)  

8. Ayarlar uygulamasına gidip dokunun **profilinin indirilip**.  

    Varsa **profilinin indirilip** değil bir seçenek olarak görüntülenir, Git **genel** > **profilleri**. Profil hala görmüyorsanız, yeniden indirmeniz gerekebilir.  

    ![Örnek ekran ayarlar uygulamasının ayarı profili indirilir.](./media/ios-1904-settings-badge.PNG)  

9. **Yükle**’ye dokunun.  
    
10. Cihaz parolanızı girin. Ardından dokunun **yükleme**.    

    ![Örnek ekran ayarlar uygulamasının, yükleme profili ekranında, bir imleç üzerinde ** yükle ** düğmesine.](./media/ios-1904-password-install.PNG)  


11. Sonraki ekranda, cihaz yönetimi için standart sistem bir uyarıdır. Yüklemeye devam etmek için dokunun **yükleme**. Uzaktan yönetime güvenin istenirse dokunun **güven**.  

    ![Örnek ekran ayarlar uygulamasında, kök sertifika ve mobil cihaz yönetimi için standart sistem uyarı ekranı.](./media/ios-15-cp-enroll-1903.PNG)  

12. Yükleme tamamlandıktan sonra dokunun **Bitti**. Profilin yüklendiğini doğrulamak için Git **profiller ve cihaz Yönetimi** ayarları. Altında listelenen profili görmelisiniz **mobil cihaz Yönetimi**.   

    ![Örnek uygulamasının ekran görüntüsü ayarları, Profiller ve cihaz yönetimi ayarları, yönetim profili gösteriliyor.](./media/ios-00-cp-enroll-1903.PNG)  

13. Şirket portalı uygulamasını döndürür. Şirket portalı, eşitleme ve Cihazınızı ayarlamak başlar. Şirket portalı ek cihaz ayarları güncelleştirmek için isteyebilir. Dokunun varsa **devam**.  

    ![Örnek ekran Şirket portalı, gereksinim ayarı yanındaki sarı üçgen ile "erişimi ayarlama" ekran görüntüsü.](./media/ios-12-cp-enroll-1903.PNG)  

14. Listedeki tüm öğeler yeşil bir daire gösterdiğinizde bu kurulumu tamamlanmadı anlarsınız. **Bitti**’ye dokunun.   
    
    ![Örnek ekran şirket Portalı'nın "her şey Tamam!" Tüm yeşil daire gösteren ekran.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Kuruluşunuz, ses ve veri sınırları izler veya şirkete bir cihazla sağlar, tamamlanması için birkaç adım daha olabilir. Yüklemek için istenirse **Datalert** uygulaması, bakın [Cihazınızı telekomünikasyon gider yönetimine kaydetme](enroll-your-device-with-telecom-expense-management-ios.md). Kuruluşunuzun Apple aygıt kayıt programı bir parçası olup olmadığını öğrenmek [şirkete Cihazınızı kaydetmek nasıl](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Sonraki adımlar  
İşte veya okulda yardımcı olacak uygulamalar bulun. Bilgi [nasıl uygulamaları kullanılabilir](use-managed-apps-on-your-device-ios.md) size Şirket portalı üzerinden.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  
