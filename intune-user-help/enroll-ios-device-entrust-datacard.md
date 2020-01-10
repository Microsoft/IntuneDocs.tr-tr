---
title: İOS veya ıpados cihazını Intune Şirket Portalı ve Entrust Datacard kaydetme
description: İOS veya ıpados cihazı kaydedin ve Entrust Datacard ile türetilmiş kimlik bilgisi kimlik doğrulamasını ayarlayın.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilver
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: b976e9a47a56c7af1e754f5b5b0162410e278025
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856401"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-entrust-datacard"></a>İOS veya ıpados cihazını Şirket Portalı ve Entrust Datacard ile ayarlama

Kuruluşunuzun e-postasına, dosyalarına ve uygulamalarına güvenli, mobil erişim kazanmak için cihazınızı Intune Şirket Portalı uygulamasına kaydedin. Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir.  

Kayıt sırasında, bir türetilmiş kimlik bilgisini cihazınıza de yüklersiniz. Kuruluşunuz, kaynaklara erişirken veya e-postaları imzalama ve şifreleme için türetilmiş kimlik bilgilerini bir kimlik doğrulama yöntemi olarak kullanmanızı gerektirebilir. 

Şunları yapmak için bir akıllı kart kullanıyorsanız, büyük olasılıkla türetilmiş bir kimlik bilgisi ayarlamanız gerekir:  

* Okul veya iş uygulamalarında oturum açma, Wi-Fi ve sanal özel ağlar (VPN)
* Okul veya iş e-postalarını S/MIME sertifikaları kullanarak imzalama ve şifreleme  

Bu makalede şunları yapacaksınız:  

   * Intune Şirket Portalı ile bir mobil iOS veya ıpados cihazı kaydedin.  
   * Kuruluşunuzun türetilmiş kimlik bilgisi sağlayıcısından, [Entrust Datacard](https://www.entrustdatacard.com/)türetilmiş bir kimlik bilgisi alın.  

### <a name="what-are-derived-credentials"></a>Türetilmiş kimlik bilgileri nelerdir?  
Türetilmiş kimlik bilgileri, akıllı kart kimlik bilgilerinizle derlenen ve cihazınızda yüklü olan bir sertifikadır. Bu, iş kaynaklarına uzaktan erişim izni verir, ancak yetkisiz kullanıcıların hassas bilgilere erişmesini önler.  

Türetilmiş kimlik bilgileri şu şekilde kullanılır: 
* Okul veya iş uygulamalarında, Wi-Fi ve VPN 'de oturum açan öğrencilerin ve çalışanların kimliklerini doğrulama
* Okul veya iş e-postalarını S/MIME sertifikaları ile imzalama ve şifreleme

Türetilmiş kimlik bilgileri, özel yayın (SP) 800-157 kapsamında türetilmiş kişisel kimlik doğrulama (PıV) kimlik bilgileri için ulusal standartlar ve Teknoloji Enstitüsü (NıST) kuralları uygulamasıdır.  

## <a name="prerequisites"></a>Prerequisites

 Kaydı tamamlayabilmeniz için, şunları yapmanız gerekir:

* Okulunuz veya iş tarafından sağlanmış akıllı kartınız
* Akıllı kartınızla oturum açabileceğiniz bir bilgisayar veya bilgi noktası erişimi
* Mobil cihazınız
* Cihazınızda yüklü iOS ve Idos Intune Şirket Portalı uygulaması  


## <a name="enroll-device"></a>Cihaz kaydetme  
1. Mobil cihazınızda iOS için Şirket Portalı App/ıpados ' i açın ve iş hesabınızla oturum açın.  

2. Ekrandaki kodu yazın.  

    ![Ekran ileti ve kodu ile Şirket Portalı uygulamasının örnek görüntüsü.](./media/copy-code-intercede.png)   

3. Akıllı kart etkin cihazınıza geçin ve https://microsoft.com/devicelogin gidin. 
4. Daha önce yazdığınız kodu girin.  

    ![Şirket Portalı Web sitesinin örnek ekran görüntüsü "kodu gir" istemi.](./media/enter-code-intercede.png)   

5. Oturum açmak için akıllı kartınızı ekleyin.   
6. Mobil cihazınızda Şirket Portalı uygulamasına dönün ve cihazınızı kaydetmek için ekrandaki yönergeleri izleyin.  
7. Kayıt tamamlandıktan sonra, Şirket Portalı akıllı kartınızı ayarlama konusunda sizi uyarır. Bildirime dokunun. Bildirim alamazsanız, e-postanızı kontrol edin.   

    ![Cihaz giriş ekranında Şirket Portalı anında iletme bildiriminin örnek ekran görüntüsü.](./media/action-required-in-app-intercede.png)  

8. **Mobil akıllı kart erişim ekranında kurulum** :   
    a. Kuruluşunuzun kurulum yönergelerinin bağlantısına dokunun. Kuruluşunuz ek yönergeler sağlamıyorsa, bu makaleye gönderilir.  
    b. **Başlat**' a dokunun.  

    ![Şirket Portalı mobil akıllı kart erişimini ayarlama ekranının örnek ekran görüntüsü.](./media/smart-card-info-intercede.png)

9. Akıllı kart etkin cihazınıza geçiş yapın ve ıdentityguard 'ı açın. 
10. Akıllı kimlik bilgisi oturum açma alanını bulun ve oturum aç düğmesini seçin.  
11. Bir sertifika seçmeniz istendiğinde, akıllı kart kimlik bilgilerinizi seçin. Sonra **Tamam**’ı seçin. 
12. Akıllı kart PIN 'inizi girin.  
13. Eylem listesinden seçim yapmanız istenir. Türetilmiş bir mobil akıllı kimlik bilgileri için kaydolmanızı sağlayan birini seçin. Bağlantı veya düğme, **türetilmiş bir mobil akıllı kart kimlik bilgisi için kaydolmak istiyorum gibi görünebilir.**  
14. Başarılı bir şekilde indirdiğiniz ve akıllı kimlik bilgileri etkinleştirilmiş uygulamayı yüklediğinizden emin olmalısınız. Sonra bir sonraki ekrana geçin.   
15. Türetilmiş akıllı kart kimlik bilgilerinizin bilgilerini girin.  
    a. Kimlik adı için, *türetilmiş kimlik bilgileri*gibi bir ad girin.  
    b. Açılan menüde, **Entrust ıdentitygudard mobil akıllı kimlik bilgileri**' ni seçin.  
    c. Sonraki ekrana devam edin. Bir QR kodunu, altında sayısal parolaya sahip olacak şekilde görürsünüz.  

16. Mobil cihazınıza geri dönün. **QR kod** Şirket Portalı > Al ekranında **devam**' a dokunun. 

    ![Şirket Portalı QR kodu alma ekranının örnek ekran görüntüsü.](./media/get-qr-code-intercede.png)  
17. **Kamera kullan** > **Tamam**' a dokunun.  

    ![Kamera erişimine izin vermek için izin isteyen Şirket Portalı isteminin örnek ekran görüntüsü.](./media/allow-cp-camera-access-intercede.png)  
18. Akıllı kart özellikli cihazınızda bulunan QR kodunun görüntüsünü tarayın.  
19. QR kodu altında görüntülenen sayısal parolayı girin.  

    ![Parola gerekli Şirket Portalı ekranının örnek ekran görüntüsü, parola alanına girin.](./media/enter-password-derived-credentials.png)   

20. Şirket Portalı cihazınızın kurulumunu tamamlamasını bekleyin.  


## <a name="next-steps"></a>Sonraki adımlar  
Kayıt tamamlandıktan sonra e-posta, Wi-Fi ve kuruluşunuzun kullanabildiği tüm uygulamalar gibi iş kaynaklarına erişebilirsiniz. Şirket Portalı uygulamaları alma, arama, yükleme ve kaldırma hakkında daha fazla bilgi için bkz.:

* [Şirket Portalı Web sitesinden uygulamaları yönetme](manage-apps-cpweb.md)  
* [Cihazınızdaki yönetilen uygulamaları kullanma](use-managed-apps-on-your-device-ios.md)  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  
