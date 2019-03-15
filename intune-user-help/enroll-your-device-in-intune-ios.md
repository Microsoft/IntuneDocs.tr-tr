---
title: Şirket kaynaklarına iOS cihaz erişimini ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: e7db319586b9375b8c88f177197e2fdf15378ab4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "55847310"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Şirket kaynaklarınıza iOS cihaz erişimi ayarlayın

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Kurumsal veya kişisel bir cihazda şirkete ait verilere erişebilmeniz için önce cihazınızı yönettirmeniz gerekir. Cihazınız yönetimli hale geldikten sonra kuruluşunuz, kendi mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atar. 

Cihazınızdan iş veya okul bilgilerine erişim sağlamak için cihazınızı kuruluşunuzun tercih ettiği ayarlara göre yapılandırmalısınız. Bu makale Şirket Portalı'nın cihazınızı bu gereksinimleri karşılayacak şekilde kaydetmenize, yapılandırmanıza ve bu durumda tutmanıza nasıl yardımcı olduğunu açıklamaktadır.

> [!NOTE]
> Mail uygulamasında şirket e-postasına erişmeyi denediğinizde cihazınızı yönettirmeniz istendiyse, doğru yere geldiniz. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz

### <a name="security"></a>Güvenlik
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra güncelleştirmeniz gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.    

### <a name="protection"></a>Protection
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bunun gibi uygulama koruma ilkeleri kuruluşlarda yaygındır. Genellikle yeniden erişim elde edebilmeniz için önce güvenilmeyen bir uygulamayı kaldırmanızı isterler.

### <a name="setting-notifications"></a>Bildirimleri ayarlama
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios). 

## <a name="before-you-start"></a>Başlamadan önce

- Kaydolmaya başladıktan sonra tüm işlemi tamamladığınızdan emin olun. Birkaç dakikadan uzun süre duraklarsanız kurulum sonlanabilir ve baştan başlamanız gerekebilir.  
- Bu işlemin başarısız olması durumunda, Şirket Portalı uygulamasına dönün ve yeniden deneyin.  
- Wi-Fi bağlantısının ve Safari’nin cihazınızda çalıştığından emin olun.
- [Intune Şirket Portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) indirin ve yükleyin.  


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Şirket kaynaklarına erişimi ayarlamak için Şirket Portalı uygulamasını kullanma

|Gördüğünüz|Açıklama|
|---|---|
|![Şirket Portalı oturum açma ekranında, alttaki “Oturum aç” düğmesi.](./media/ios-01-cp-enroll-1802.PNG)|Şirket Portalı uygulamasını açın ve **Oturum Aç**’a dokunun.|
|![Azure AD oturum açma istemi.](./media/ios-02-cp-enroll-1802.PNG)|Şirket e-posta adresinizi girin ardından **İleri**’ye dokunun.|
|![Azure AD parola istemi.](./media/ios-03-cp-enroll-1802.PNG)|Parolanızı girin ve ardından **Oturum Aç**’a dokunun.|
|![Şirket kaynaklarının açılış ekranı yükleniyor.](./media/ios-04-cp-enroll-1802.PNG)|Bu ekranın yüklenmesini bekleyin.|
|![Hüküm ve koşullar sayfası.](./media/ios-05-cp-enroll-1802.PNG)|Hüküm ve Koşulları okuyun ve **Hepsini Kabul Edin**.|
|![Şirket erişim ekranını ayarla. Hem yönetim hem de ayarlar şu anda çözülmeye ihtiyaç duyuyor.](./media/ios-06-cp-enroll-1802.PNG)|Cihazınızın şirket kaynaklarına erişebilmesi sürecini başlatmak için **Başlat**’a dokunun. Bunu şimdi yapamazsan, işlemi **Erteleyebilirsin**, ancak e-posta,belge ve daha pek çok şey alamayacağınız anlamına gelir.|
|![Şirket ekranım ne görebilir?](./media/ios-07-cp-enroll-1802.PNG)|En altındaki bağlantıya dokunarak şirketinizin neyi görebileceği hakkında **daha fazla bilgi edinebilirsiniz**. Aksi takdirde **Devam**’a dokunun.|
|![Sırada ne var ekranı.](./media/ios-08-cp-enroll-1802.PNG)|Bu ekran, kurulumda olan biten hakkında sizi bilgilendirir. Safari'de, Ayarlar uygulamasında ve Şirket Portalı uygulamasında zaman geçireceksiniz. **Devam**’a dokunun.|
|![Sırada ne var?'a dokunduktan sonra yükleme ekranı.](./media/ios-09-cp-enroll-1802.PNG)|Bu ekranın yüklenmesini bekleyin.|
|![Kaydolmak için Safari'ye geçildi.](./media/ios-cp-sent-to-safari-1808.png)|Cihazınız için yönetim bilgisi almak için Safari'ye gönderildiniz.|
|![Sistem, Ayarlar uygulaması açılmasını isteyecektir.](./media/ios-8-cp-enroll-1711.PNG)|Yapılandırma profilini indirmek için Ayarlar uygulamasını açmasına **izin ver**’e dokunun. Şirketinizin şirket bilgilerinizi cihazınızda yönetmesine izin vermek için bunu yükleyin.|
|![Cihaz ayarlarındaki Profili Yükle ekranının görüntüsü.](./media/ios-9-cp-enroll-1711.PNG)|**Yükle**’ye dokunun.|
|![Profil kalıcı iletişim kutusunu ekranın alt kısmında yükleme.](./media/ios-10-cp-enroll-1711.PNG)|**Yükle**’ye dokunun.|
|![Profili yükleme ekranını yüklüyor.](./media/ios-11-cp-enroll-1711.PNG)|Bu ekranın yüklenmesini bekleyin.|
|![Profil yönetimi uyarı ekranı.](./media/ios-12-cp-enroll-1711.PNG)|Apple tarafından yazılan bu uyarı, yönetilen bir cihazda hangi tür işlemlerin yapılabileceği hakkında daha fazla bilgi sağlar. [Şirketinizin hangi bilgileri görebileceği](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) hakkında daha fazla bilgi.|
|![Uzaktan yönetim güveni hakkında soran sistem istemi.](./media/ios-13-cp-enroll-1711.PNG)|Şirketinizin cihazınızdaki kurumsal bilgileri ve ayarları yönetmesine izin vermek için **Güven** 'e dokunun.|
|![Profil sonlandırma yükleme ekranını yüklüyor.](./media/ios-14-cp-enroll-1711.PNG)|Bu ekranın yüklenmesini bekleyin.|
|![Profil ekranı yükledi.](./media/ios-15-cp-enroll-1711.PNG)|Profiliniz yüklendi ve cihazınızın kurumsal bilgileri ve ayarları yönetilmeye çok daha yakın.|
|![Kaydolmak için Safari'ye geçildi.](./media/ios-16-cp-enroll-1711.PNG)|Cihazınızla ilgili yönetim bilgilerini almak için Safari'ye geri gönderildiniz. |
|![Şirket portalını açmak için sistem istemi.](./media/ios-17-cp-enroll-1711.PNG)|**Aç**’a dokunun.|
|![Şirket kaynaklarının ekranı yükleniyor.](./media/ios-21-cp-enroll-1802.PNG)|Bu ekranın yüklenmesini bekleyin.|
|![Şirket portalı uygulamasında cihaz kategorisini seçin.](./media/ios-22-cp-enroll-1802.PNG)|Cihazınız için en uygun kategoriyi seçin. Bu genellikle cihazın sahibi kiminle veya genelde nerede bulunduğuyla ilgilidir.|
|![Kategori seçildi.](./media/ios-23-cp-enroll-1802.PNG)||
|![Cihaz yönetimi başarılı; şimdi ayarları güncelleştirmeniz gerekir.](./media/ios-24-cp-enroll-1802.PNG)|Cihazınızı başarıyla yönettiniz. Şirketinizin güncelleştirme yapması gerekebileceği, şifrenizin uzunluğu gibi muhtemel ayarlar hala mevcut. Devam etmek için **Devam**’a dokunun.|
|![Cihaz ayarları onaylanıyor.](./media/ios-25-cp-enroll-1802.PNG)|Şirket Portalı, ayarlarınızdan herhangi birinin güncelleştirilmesinin gerekip gerekmediğini kontrol edecektir.|
|![Ayarlar denetimi, yanlış bir işletim sistemi sürümü ile tamamlandı](./media/ios-26-cp-enroll-1802.PNG)|Şirket Portalı, ayarlarınızla ilgili tüm sorunları nasıl çözebileceğiniz konusunda yönergeler verecektir. Sorunlarını giderme tamamladıktan sonra **Ayarları Denetle**’ye dokunun.|
|![Cihaz ayarları yükleme ekranını onaylama](./media/ios-27-cp-enroll-1802.PNG)|Cihazınız ayarlarınızın şirket kaynaklarına erişecek kadar güvenli olup olmadığını kontrol edecektir.|
|![Başarıyla kaydedilmiş ve güncelleştirilmiş ayarlar](./media/ios-28-cp-enroll-1802.PNG)|Tebrikler! Cihazınız artık Intune'a kaydedilmiştir.|

> [!Note]
> Cihazınız tamamen yönetilmeden önce birkaç adım daha kaldı. [Telekom gider yönetimini kullanarak cihazınızı kaydetme](enroll-your-device-with-telecom-expense-management-ios.md) hakkında daha fazla bilgi edinin. Kuruluşunuz Apple’ın Aygıt Kayıt Programı’nı kullanıyorsa [buraya](enroll-your-device-dep-ios.md) tıklayarak daha fazla bilgi edinebilirsiniz.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  
