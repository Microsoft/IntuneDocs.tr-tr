---
title: İOS veya ıpados cihazını Intune Şirket Portalı ve DıŞA purebred ile kaydetme
description: İOS veya ıpados cihazını kaydetmeyi ve DıŞA yönelik kimlik doğrulaması ile birlikte bulunan kimlik doğrulamasını nasıl ayarlayacağınızı öğrenin.
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
ms.openlocfilehash: 5c484b98466c1418016f4ebc6cc805e412d7891e
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415599"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-disa-purebred"></a>İOS veya ıpados cihazını Şirket Portalı ve DıŞA purebred ile ayarlama  

Kuruluşunuzun e-postasına, dosyalarına ve uygulamalarına güvenli, mobil erişim kazanmak için cihazınızı Intune Şirket Portalı uygulamasına kaydedin. Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir.  

Kayıt sırasında, bir türetilmiş kimlik bilgisini cihazınıza de yüklersiniz. Kuruluşunuz, kaynaklara erişirken veya e-postaları imzalama ve şifreleme için türetilmiş kimlik bilgilerini bir kimlik doğrulama yöntemi olarak kullanmanızı gerektirebilir. 

Şunları yapmak için bir akıllı kart kullanıyorsanız, büyük olasılıkla türetilmiş bir kimlik bilgisi ayarlamanız gerekir:

* Okul veya iş uygulamalarında oturum açma, Wi-Fi ve sanal özel ağlar (VPN)
* Okul veya iş e-postalarını S/MIME sertifikaları kullanarak imzalama ve şifreleme  

Bu makalede şunları yapmanız gerekir:  

   * Intune Şirket Portalı ile bir mobil iOS veya ıpados cihazı kaydedin.  
   * Kuruluşunuzun türetilmiş kimlik bilgisi sağlayıcısından, [dışa purebred](https://cyber.mil/pki-pke/purebred/)'nin türetilmiş bir kimlik bilgisini alın.  

## <a name="what-are-derived-credentials"></a>Türetilmiş kimlik bilgileri nelerdir?  
Türetilmiş kimlik bilgileri, akıllı kart kimlik bilgilerinizle derlenen ve cihazınızda yüklü olan bir sertifikadır. Bu, iş kaynaklarına uzaktan erişim izni verir, ancak yetkisiz kullanıcıların hassas bilgilere erişmesini önler.  

Türetilmiş kimlik bilgileri şu şekilde kullanılır: 
* Okul veya iş uygulamalarında, Wi-Fi ve VPN 'de oturum açan öğrencilerin ve çalışanların kimliklerini doğrulama
* Okul veya iş e-postalarını S/MIME sertifikaları ile imzalama ve şifreleme

Türetilmiş kimlik bilgileri, özel yayın (SP) 800-157 kapsamında türetilmiş kişisel kimlik doğrulama (PıV) kimlik bilgileri için ulusal standartlar ve Teknoloji Enstitüsü (NıST) kuralları uygulamasıdır.  

## <a name="prerequisites"></a>Önkoşullar

 Kaydı tamamlayabilmeniz için, şunları yapmanız gerekir:

* Okulunuz veya iş tarafından sağlanmış akıllı kartınız
* Akıllı kartınızla oturum açabileceğiniz bir bilgisayar veya bilgi noktası erişimi
* Mobil cihazınız
* Cihazınızda yüklü iOS ve Idos Intune Şirket Portalı uygulaması   

Ayrıca, kurulum sırasında purebred Aracısı veya temsilcisiyle iletişim kurmanız gerekecektir.      

## <a name="enroll-device"></a>Cihazı kaydetme  
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
    b. Purebred uygulamasını açmak için **Aç** ' a tıklayın.  

    ![Şirket Portalı mobil akıllı kart erişimini ayarlama ekranının örnek ekran görüntüsü.](./media/smart-card-open-disa-purebred.png)  
9. Purebred kayıt uygulamasını açmak Şirket Portalı izin vermeniz istendiğinde **Aç**' ı seçin.   

    ![Rekkred uygulamasını açmak için Şirket Portalı isteminin örnek ekran görüntüsü.](./media/open-app-prompt-disa-purbred.png)  
10. Uygulama çalışırken, purebred kayıt yapılandırma profilini yapılandırmak ve indirmek için kuruluşunuzun purebred aracısıyla birlikte çalışın.   
11. Ayarlar uygulaması > **genel** > **profilleri & cihaz yönetimi** > **profil yüklemesi** ' ne gidin ve ardından **Install**' a dokunun.  
12. Cihaz geçiş kodunuzu girin.  
13. Profili yükler. Yüklemeyi başlatmak için birden çok kez **yükleme** ' ye dokunmanız gerekebilir. 
14. Purebred kayıt uygulamasına geri dönün. Devam etmek için purebred aracısının yönergelerini izleyin.  
 
15. Yapılandırma profilini indirdikten sonra, ayarlar uygulaması > **genel** > **profilleri & cihaz yönetimi** > **profil yükle** ' ye gidin ve **Yükle**' ye dokunun.   
16.  Cihaz geçiş kodunuzu girin.
17. Profili yükler. Yüklemeyi başlatmak için birden çok kez **yükleme** ' ye dokunmanız gerekebilir. 
18. Yükleme tamamlandıktan sonra Şirket Portalı uygulamasına geri dönün.  
19.  **Mobil akıllı kart erişimi kurulumu** ekranında, **devam**' a dokunun.  

20. **Sertifikaları Içeri aktar** ekranında, dışarı aktarılan türetilmiş kimlik bilgisini alıp içeri aktarırsınız.  

    a. **Devam**’a dokunun.   

    ![sertifikaları Içeri aktarma ekranını Şirket Portalı örnek ekran görüntüsü.](./media/import-certificate-disa-purebred.png)  
    b. İCloud **sürücüsüne gidin** > **konumlara** gidip **diğer konumlar**' a dokunun.  

    iCloud sürücüsünün örnek ekran görüntüsünü ![, menü daha fazla konum seçeneğine gözatıp.](./media/icloud-drive-more-locations.png)  
    c. **Purebred anahtar zincirini**etkinleştirmek için anahtara dokunun.  

    ![İCloud sürücüsünün örnek ekran görüntüsü, purebred anahtar zinciri anahtarının etkin olduğunu vurgulama görünümü.](./media/icloud-drive-enable-purebred-keychain.png)   

    d. **Purebred kimlik bilgisi paketi**' ne dokunun.  

    seçilebilir purebred kimlik bilgisi paket seçeneği içeren bir iOS ekranının örnek ekran görüntüsü ![.](./media/purebred-credential-package.png)  
    f. Sertifika listesi görüntülenir. Bir tane seçin ve ardından **anahtarı Içeri aktar**' a dokunun.  

    ![Seçilebilir sertifikaların listesinin örnek ekran görüntüsü, önceden seçilmiş bir.](./media/import-purebred-keychain.png) 
21. Şirket Portalı uygulamasına dönün ve Şirket Portalı cihazınızın kurulumunu tamamlamasını bekleyin.   

## <a name="next-steps"></a>Sonraki adımlar  
Kayıt tamamlandıktan sonra e-posta, Wi-Fi ve kuruluşunuzun kullanabildiği tüm uygulamalar gibi iş kaynaklarına erişebilirsiniz. Şirket Portalı uygulamaları alma, arama, yükleme ve kaldırma hakkında daha fazla bilgi için bkz.:

* [Şirket Portalı Web sitesinden uygulamaları yönetme](manage-apps-cpweb.md)  
* [Cihazınızdaki yönetilen uygulamaları kullanma](use-managed-apps-on-your-device-ios.md)  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
