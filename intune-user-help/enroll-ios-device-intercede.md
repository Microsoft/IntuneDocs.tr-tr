---
title: İOS veya ıpados cihazını Intune Şirket Portalı ve ıntercede ile kaydetme
description: İOS veya ıpados cihazını kaydetmeyi ve ıntercede ile türetilmiş kimlik bilgisi kimlik doğrulamasını ayarlamayı öğrenin.
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02293b29f8634161582af2348b1cb30039ca3c52
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415575"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-intercede"></a>İOS veya ıpados cihazını Şirket Portalı ve ıntercede ile ayarlama

Kuruluşunuzun e-postasına, dosyalarına ve uygulamalarına güvenli, mobil erişim kazanmak için cihazınızı Intune Şirket Portalı uygulamasına kaydedin.  Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir.  

Kayıt sırasında, bir türetilmiş kimlik bilgisini cihazınıza de yüklersiniz. Kuruluşunuz, kaynaklara erişirken veya e-postaları imzalama ve şifreleme için türetilmiş kimlik bilgilerini bir kimlik doğrulama yöntemi olarak kullanmanızı gerektirebilir. 

Şunları yapmak için bir akıllı kart kullanıyorsanız, büyük olasılıkla türetilmiş bir kimlik bilgisi ayarlamanız gerekir:

* Okul veya iş uygulamalarında oturum açma, Wi-Fi ve sanal özel ağlar (VPN)
* Okul veya iş e-postalarını S/MIME sertifikaları kullanarak imzalama ve şifreleme  

Bu makalede şunları yapmanız gerekir:  

* Intune Şirket Portalı ile bir mobil iOS veya ıpados cihazı kaydedin.  
* Kuruluşunuzun türetilmiş kimlik bilgisi sağlayıcısından, [ıntercede](https://www.intercede.com/)tarafından türetilmiş bir kimlik bilgisi alın.   


## <a name="what-are-derived-credentials"></a>Türetilmiş kimlik bilgileri nelerdir?  
Türetilmiş kimlik bilgileri, akıllı kart kimlik bilgilerinizle derlenen ve cihazınızda yüklü olan bir sertifikadır. Bu, iş kaynaklarına uzaktan erişim izni verir, ancak yetkisiz kullanıcıların hassas bilgilere erişmesini önler.  

Türetilmiş kimlik bilgileri şu şekilde kullanılır: 
* Okul veya iş uygulamalarında, Wi-Fi ve VPN 'de oturum açan öğrencilerin ve çalışanların kimliklerini doğrulama
* Okul veya iş e-postalarını S/MIME sertifikaları ile imzalama ve şifreleme  

Türetilmiş kimlik bilgileri, özel yayın (SP) 800-157 kapsamında türetilmiş kişisel kimlik doğrulama (PıV) kimlik bilgileri için ulusal standartlar ve Teknoloji Enstitüsü (NıST) kuralları uygulamasıdır.  

## <a name="prerequisites"></a>Önkoşullar

 Kaydı tamamlayabilmeniz için, şunları yapmanız gerekir:

* Okulunuz veya iş tarafından sağlanmış akıllı kartınız
* Akıllı kartınızla oturum açabilmeniz için bir bilgisayara veya self servis bilgi noktasında erişim
* Mobil cihazınız
* Cihazınızda yüklü iOS ve Idos Intune Şirket Portalı uygulaması


## <a name="enroll-device"></a>Cihazı kaydetme  
1. Mobil cihazınızda iOS için Şirket Portalı App/ıpados ' i açın ve iş hesabınızla oturum açın.  
2. Ekranda görüntülenen kodu yazın.  

    ![Ekran ileti ve kodu ile Şirket Portalı uygulamasının örnek görüntüsü.](./media/copy-code-intercede.png)  
1. Akıllı kart etkin cihazınıza geçin ve https://microsoft.com/devicelogin gidin. 

1. Daha önce yazdığınız kodu girin.
 
2. Oturum açmak için akıllı kartınızı ekleyin.   

3. Mobil cihazınızda Şirket Portalı uygulamasına dönün ve cihazınızı kaydetmek için ekrandaki yönergeleri izleyin.  
4. Kayıt tamamlandıktan sonra, Şirket Portalı akıllı kartınızı ayarlama konusunda sizi uyarır. Bildirime dokunun. Bildirim alamazsanız, e-postanızı kontrol edin.   

    ![Cihaz giriş ekranında Şirket Portalı anında iletme bildiriminin örnek ekran görüntüsü.](./media/action-required-in-app-intercede.png)  

5. **Mobil akıllı kart erişim ekranında kurulum** :  
    a. Kuruluşunuzun kurulum yönergelerinin bağlantısına dokunun. Kuruluşunuz ek yönergeler sağlamıyorsa, bu makaleye gönderilir.  
    b. **Başlat**' a dokunun.  

    ![Şirket Portalı mobil akıllı kart erişimini ayarlama ekranının örnek ekran görüntüsü.](./media/smart-card-info-intercede.png)  

6. Akıllı kart etkin cihazınıza veya self servis bilgi noktası 'na geçin ve MyID uygulamasını açın. İş kimlik bilgilerinizle oturum açın.  
7. KIMLIĞINIZI isteme seçeneğini belirleyin. 
8. Kullanmak istediğiniz profil sorulduğunda, mobil kimlik bilgileriyle etkinleştirme seçeneğini belirleyin. QR kodu görüntülenir.  
9. Mobil cihazınıza geri dönün. **QR kod** Şirket Portalı > Al ekranında **devam**' a dokunun.  

    ![Şirket Portalı QR kodu alma ekranının örnek ekran görüntüsü.](./media/get-qr-code-intercede.png) 
 
10. **Kamera kullan** > **Tamam**' a dokunun.  

    ![Kamera erişimine izin vermek için izin isteyen Şirket Portalı isteminin örnek ekran görüntüsü.](./media/allow-cp-camera-access-intercede.png)  

11. Akıllı kart özellikli cihazınızda bulunan QR kodunun görüntüsünü tarayın. 
12. Şirket Portalı cihazınızın kurulumunu tamamlamasını bekleyin.  

## <a name="next-steps"></a>Sonraki adımlar  
Kayıt tamamlandıktan sonra e-posta, Wi-Fi ve kuruluşunuzun kullanabildiği tüm uygulamalar gibi iş kaynaklarına erişebilirsiniz. Şirket Portalı uygulamaları alma, arama, yükleme ve kaldırma hakkında daha fazla bilgi için bkz.:

* [Şirket Portalı Web sitesinden uygulamaları yönetme](manage-apps-cpweb.md)  
* [Cihazınızdaki yönetilen uygulamaları kullanma](use-managed-apps-on-your-device-ios.md)  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
