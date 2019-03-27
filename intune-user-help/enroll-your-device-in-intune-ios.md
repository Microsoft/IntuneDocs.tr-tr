---
title: Şirket kaynaklarına iOS cihaz erişimini ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490651"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Şirket kaynaklarınıza iOS cihaz erişimi ayarlayın  

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Kurumsal veya kişisel bir CİHAZDAN özel verilere erişmeden önce cihazınızın yönetilmesini isteniyor. Cihazınızı yönetilen sonra kuruluşunuz ilkeler ve uygulamalar gibi Intune bir mobil cihaz Yönetimi (MDM) sağlayıcısı üzerinden cihazı atar. 

Cihazınızdan iş veya okul bilgilerine erişim sağlamak için cihazınızı kuruluşunuzun tercih ettiği ayarlara göre yapılandırmalısınız. Bu makalede, cihaz, kaydetmek için Şirket portalı kullanmak ve kuruluşunuzun gereksinimlerine açıklar. 

> [!NOTE]
> Mail uygulamasında şirket e-postasına erişmeyi denediğinizde cihazınızı yönettirmeniz istendiyse, doğru yere geldiniz. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz  

### <a name="security"></a>Güvenlik  
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra güncelleştirmeniz gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.     

### <a name="protection"></a>Protection  
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Böyle bir ilke, kuruluşlarda yaygın bir durumdur ve genellikle erişebilmek önce güvenilmeyen uygulamayı kaldırma gerektirir.  

### <a name="setting-notifications"></a>Bildirimleri ayarlama  
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>İOS Cihazınızı kaydetme   

> [!IMPORTANT]
> Bu bölümdeki ekran görüntüleri 12,1 ve daha önceki iOS sürümü çalıştıran cihazlar için deneyimi gösterir. Uygunsa, üstü ve iOS sürümü 12.2 özel yönergeler ekledik. Deneyiminizi gösterildiği ekran görüntüleri farklı olduğunu fark ederseniz, lütfen 12.2 yönergelerine başvurun.      

İndirmek ve yüklemek için mağazaya gidin [Intune Şirket portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) cihazınıza. Kayıt sırasında bir Wi-Fi bağlantısı ve Safari erişimi de gerekir. 

Kayıt sırasında birkaç dakika duraklatırsanız, uygulamayı kapatın veya Kurulumu sonlandırmak. Bu durumda, Şirket portalı uygulamasını açın ve yeniden deneyin.  

1. Şirket portalı ve iş veya Okul hesabınızla oturum açın. 

    ![Örnek Şirket portalı uygulamasının, oturum açma ekran görüntüsü.](./media/ios-01-cp-enroll-1903.PNG)  

2. Şirket portalı bildirimleri almak isteyip istemediğiniz sorulduğunda dokunun **izin.** Şirket portalı bildirimleri gibi cihaz ayarlarınızı güncelleştirilmesi gerekiyorsa, sizi uyarmak için kullanır. 

    ![Şirket portalı giriş sayfasının "Bildirimler" istemi örnek ekran görüntüsü.](./media/ios-04-cp-enroll-1903.PNG)  

3. Üzerinde **erişimi ayarlama** ekranındayken **başlayın.**  

     ![Örnek Şirket portalı, "erişim ayarlama" ekran görüntüsü.](./media/ios-05-cp-enroll-1903.PNG)  

4. Kuruluşunuz görebileceği ve göremeyeceği cihaz bilgilerini listesi üzerinden okuyun. [Bu konu hakkında ek ayrıntılar](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) aracılığıyla bulunabilir **daha fazla bilgi edinin** bağlantı. İşiniz bittiğinde, dokunun **devam**.  

    ![Örnek ekran Şirket portalı uygulamasının "Ne Kuruluşum görebilirsiniz", devam düğmesi.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. **Sonraki nedir?** ekran kalan adımları özetler. Bu adımları iOS sürümünüzü bağlı olarak farklı olabilir. 
    * **iOS 12.2 ve üzeri**: deneyiminizi yerine başlatmanızı gerektirebilir:  

        a. **Yönetim profili indirilmesini izin**: Tarayıcınız Şirket portalı Web sitesini açın ve indirme işlemine izin ister. İndirme Ayarları uygulamanızda kaydedilir.  

        b. **Ayarlar uygulamasını açın ve profil yükleme**: Ayarlar uygulamasına gidip yönetim profili yüklemeniz gerekir.  

        c. **İade için Şirket portalı uygulamasını**: Kurulumu tamamlamak için Şirket portalı uygulamasına dönmeniz gerekir.  

    Yönetim profili yüklemek hazır olduğunuzda, dokunun **devam**.  

6. Safari, Şirket portalı Web sitesini açar. Yapılandırma profilini indirmek için istendiğinde dokunun **izin**.  
    * **iOS 12.2 ve üzeri**: Safari ve dokunun indirilmesinin profil için bekleme **Bitti**. Açılacağını **ayarları** uygulamasını Cihazınızda.  

    > [!IMPORTANT]
    > Git gerekir **ayarları** uygulama ve bu profili 8 dakika içinde karşıdan yükleyin. Aksi takdirde profili kaldırılacak ve kayıt'ı yeniden başlatmanız gerekir. 

7. İçinde **ayarları** uygulama, dokunun **yükleme indirilen profili** > **yükleme**. Varsa **yükleme indirilen profili** değil bir seçenek olarak görüntülenir, Git **genel** > **profilleri**. Profil hala görmüyorsanız, yeniden indirmeniz gerekebilir.  

    ![Örnek ekran ayarlar uygulamasının yükleme indirilen profili ayarıyla en son indirilen profili gösteren kırmızı bir rozet.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. İstenirse cihaz parolanızı girin. Ardından dokunun **yükleme**.      

9. Sonraki ekranda, cihaz yönetimi için standart sistem bir uyarıdır. Ne kuruluşunuz Cihazınızda görebilecekleri ve göremeyecekleri hakkında daha fazla bilgi için ilgili bkz [Intune docs makaleleri](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Yüklemeye devam etmek için dokunun **yükleme**. Uzaktan yönetime güvenin istenirse, dokunun **güven**.  

    ![Örnek ekran ayarlar uygulamasında, kök sertifika ve mobil cihaz yönetimi için standart sistem uyarı ekranı.](./media/ios-15-cp-enroll-1903.PNG)  

10. Yükleme tamamlandıktan sonra dokunun **Bitti**. Profilin yüklendiğini doğrulamak için Git **profiller ve cihaz Yönetimi** ayarları. Altında listelenen profili görmelisiniz **mobil cihaz Yönetimi**.   

    ![Örnek uygulamasının ekran görüntüsü ayarları, Profiller ve cihaz yönetimi ayarları, yönetim profili gösteriliyor.](./media/ios-00-cp-enroll-1903.PNG)  


11. Geri dönüp **Şirket portalı** uygulama. Şirket portalı, eşitleme ve Cihazınızı ayarlamak başlar. Şirket portalı ek cihaz ayarları güncelleştirmek için isteyebilir. Dokunun varsa **devam**.

    ![Örnek ekran Şirket portalı, gereksinim ayarı yanındaki sarı üçgen ile "erişimi ayarlama" ekran görüntüsü.](./media/ios-12-cp-enroll-1903.PNG)  

12. Listedeki tüm öğeler yeşil bir daire gösterdiğinizde bu kurulumu tamamlanmadı anlarsınız. **Bitti**’ye dokunun.  
    
    ![Örnek ekran şirket Portalı'nın "her şey Tamam!" Tüm yeşil daire gösteren ekran.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Kuruluşunuz, ses ve veri sınırları izler veya şirkete bir cihazla sağlar, tamamlanması için birkaç adım daha olabilir. Yüklemek için istenirse **Datalert** uygulaması, bakın [Cihazınızı telekomünikasyon gider yönetimine kaydetme](enroll-your-device-with-telecom-expense-management-ios.md). Kuruluşunuzun Apple aygıt kayıt programı bir parçası olup olmadığını öğrenmek [şirkete Cihazınızı kaydetmek nasıl](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Sonraki adımlar  
İşte veya okulda yardımcı olacak uygulamalar bulun. Bilgi [nasıl uygulamaları kullanılabilir](use-managed-apps-on-your-device-ios.md) size Şirket portalı üzerinden.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  
