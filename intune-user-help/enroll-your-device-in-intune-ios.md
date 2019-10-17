---
title: Şirket kaynaklarına iOS cihaz erişimini ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: e468042ab81d563c9fa4b272661508a340d61aa9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506240"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Şirket kaynaklarınıza iOS cihaz erişimi ayarlayın  

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir.  

> [!NOTE]
> Her nedenden dolayı hizmetimizin tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.  

Cihazınızdaki iş veya okul bilgilerine erişimi sürdürmek için cihazınızı kuruluşunuzun tercih ettiğiniz ayarlarla eşleşecek şekilde yapılandırmanız gerekir. Bu makalede, cihazınızı kaydetmek ve kuruluşunuzun ayar gereksinimlerini korumak için Şirket Portalı nasıl kullanılacağı açıklanır.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Mail uygulamasında şirket e-postasına erişmeyi denediğinizde cihazınızı yönettirmeniz istendiyse, doğru yere geldiniz. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz  

### <a name="security"></a>Güvenlik  
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra güncelleştirmeniz gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.

### <a name="protection"></a>Protection  
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bu tür bir ilke kuruluşlarda yaygındır ve genellikle, erişimi yeniden kazanabilmeniz için güvenilmeyen uygulamayı kaldırmanızı gerektirir.  

### <a name="setting-notifications"></a>Bildirimleri ayarlama  
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>İOS cihazınızı kaydetme  

[Intune şirket portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) cihazınıza indirip yüklemek için App Store 'a gidin. Ayrıca, bir Wi-Fi bağlantısı sürdürmenize ve kayıt sırasında Safari 'ye erişiminizin olması gerekir. 

Kayıt sırasında birkaç dakikadan uzun bir süre durakladığında uygulamanın kurulum 'u kapatması veya sonlandırmasına neden olabilir. Bu durumda Şirket Portalı uygulamasını açın ve yeniden deneyin.  

1. Şirket Portalı açın ve iş veya okul hesabınızla oturum açın. 

    ![Şirket Portalı uygulamasının örnek ekran görüntüsü, oturum açın.](./media/ios-01-cp-enroll-1904.PNG)  

2. Şirket Portalı bildirimleri almanız istendiğinde, **Izin ver** ' e dokunun. Şirket Portalı, örneğin cihaz ayarlarınızın güncellenmesi gerekiyorsa sizi uyarmak için bildirimleri kullanır. 

    ![Şirket Portalı giriş sayfasının örnek ekran görüntüsü, "Bildirimler" istemi.](./media/ios-02-cp-enroll-1904.PNG)  

3. **Erişim ayarla** ekranında, Başlat ' ı seçin **.**  

     ![Şirket Portalı, "erişim ayarlama" ekranının örnek ekran görüntüsü.](./media/ios-03-cp-enroll-1904.PNG)  

4. Kuruluşunuzun görebileceği cihaz bilgileri listesini okuyun. Sonra **devam**' a dokunun.  

5. **İleri git?** ekranında yönergeleri okuyun. Yönetim profilini indirip yüklemeye hazırsanız **devam**' a dokunun.  

 > [!IMPORTANT]
> Bu sonraki adımlar ve ekranlar, iOS sürümünüze bağlı olarak farklılık gösterir. İOS sürümünüz için adımları izleyin. 

6. Safari, cihazınızda Şirket Portalı Web sitesini açar. Yapılandırma profilini indirmeniz istendiğinde, **Izin ver**' e dokunun. Çalıştıran bir cihazımız varsa:  
    * iOS 12,2 ve üzeri: İndirme tamamlandığında bitti ' ye dokunun **.** Bu makalede 7. adıma geçin.
    * iOS 12,1 ve öncesi: Ayarlar uygulamasına otomatik olarak yönlendirilirsiniz. Bu makaledeki 8. adıma atlayın.  
 
    Yanlışlıkla **Yoksay**' a dokunmanız durumunda sayfayı yenileyin. Şirket Portalı uygulamasını açmanız istenir. Uygulamadan **tekrar indir**' e dokunabilirsiniz.

  > [!NOTE]
  > Yönetim profilini, bir sonraki adımlarda 8 dakika içinde açıklandığı gibi yüklemeniz gerekir. Aksi takdirde, profil kaldırılır ve kayıt işlemini yeniden başlatmanız gerekir.  

7. yalnızca iOS 12,2 ve üzeri: Şirket Portalı açmanız istendiğinde **Aç**' a dokunun. **Yönetim profilini yükleme** ekranında, profili yükleme adımları listelenir.

    ![Şirket Portalı örnek ekran görüntüsü, yönetim profilini yükleme ekranı yükleniyor.](./media/ios-07-cp-enroll-1904.PNG)  

8. Ayarlar uygulamasına gidin ve **profil indirildi**' a dokunun.  

    **Indirilen profil** bir seçenek olarak görünmezse, **genel** > **profillerine**gidin. Profili hala görmüyorsanız, yeniden indirmeniz gerekebilir.  

    ![Ayarlar uygulaması, profil Indirilen ayarı örnek ekran görüntüsü.](./media/ios-1904-settings-badge.PNG)  

9. **Yükle**’ye dokunun.  
    
10. Cihaz parolanızı girin. Ardından **Install**' a dokunun.    

    ![Ayarlar uygulamasının, profil yükleme, * * yükleme * * düğmesi üzerinde bir imleç içeren örnek ekran görüntüsü.](./media/ios-10-cp-enroll-1904.PNG)  


11. Sonraki ekran, cihaz yönetimi için standart bir sistem uyarısına sahiptir. Yüklemeye devam etmek için, **yükleme**' ye dokunun. Uzaktan yönetime güvenmesi istenirse **güven**' e dokunun.  

    ![Ayarlar uygulamasının örnek ekran görüntüsü, kök sertifika ve mobil cihaz yönetimi için standart sistem uyarı ekranı.](./media/ios-11-cp-enroll-1904.PNG)  

12. Yükleme tamamlandıktan sonra **bitti**' ye dokunun. Profilin yüklendiğini doğrulamak için, **cihaz yönetimi ayarları & profiller** ' e gidin. **Mobil cihaz yönetimi**altında listelenen profili görmeniz gerekir.   

    ![Ayarlar uygulamasının, yönetim profilini gösteren cihaz yönetimi ayarlarının &, profil ekran görüntüsü örneği.](./media/ios-12-cp-enroll-1904.PNG)  

13. Şirket Portalı uygulamasına geri dönün. Şirket Portalı, cihazınızı eşitlemeye ve ayarlamaya başlayacaktır. Şirket Portalı ek cihaz ayarlarını güncelleştirmenizi isteyebilir. Varsa, **devam**' a dokunun.  

    ![Şirket Portalı, "erişim ayarlama" ekranının örnek ekran görüntüsü, gereksinim ayarı yanında sarı üçgenle.](./media/ios-13-cp-enroll-1904.PNG)  

14. Listedeki tüm öğeler yeşil bir daire gösterdiğinizde kurulumun tamamlandığını bilirsiniz. **Bitti**’ye dokunun.   
    
    ![Örnek ekran görüntüsü Şirket Portalı, "Tamamen hazırsınız!" ekran, tüm yeşil daireleri gösteriliyor.](./media/ios-14-cp-enroll-1904.PNG)  

> [!Note]
> Kuruluşunuz ses ve veri sınırlarını izliyor veya size şirkete ait bir cihaz sağlıyorsa, birkaç adım daha doldurmanız gerekebilir. **Datalert** uygulamasını yüklemek isteyip istemediğiniz sorulursa, bkz. [cihazınızı Telekom gider yönetimine kaydetme](enroll-your-device-with-telecom-expense-management-ios.md). Kuruluşunuz Apple Aygıt Kayıt Programı bir parçasıysa [şirkete ait cihazınızı nasıl kaydedebileceğinizi](enroll-your-device-dep-ios.md)öğrenin.  

## <a name="it-administrator-support"></a>BT yöneticisi desteği  
BT yöneticisiyseniz ve cihazları kaydederken sorun yaşıyorsanız, bkz. [Microsoft Intune iOS cihaz kaydı sorunlarını giderme](https://support.microsoft.com/en-us/help/4039809). Bu makalede, sık karşılaşılan hatalar, nedenler ve bunları çözmeye yönelik adımlar listelenir.  

## <a name="next-steps"></a>Sonraki adımlar  
İş veya okul işlerinde size yardımcı olacak uygulamalar bulun. Uygulamaları Şirket Portalı aracılığıyla [nasıl kullanabileceğiniz hakkında](use-managed-apps-on-your-device-ios.md) bilgi edinin.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  
