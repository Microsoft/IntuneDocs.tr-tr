---
title: Şirket kaynaklarına erişimi ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
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
ms.openlocfilehash: 51492c1a8d7e32ab7dbdd5d896e7726c877d62d5
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43149592"
---
# <a name="set-up-access-to-your-company-resources"></a>Şirket kaynaklarına erişimi ayarlama

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Kuruluşlar çoğu zaman cihazınızın özel verilere erişmesi için yönetilmesini gerektirir. Bir cihaz yönetilmeye başladığında kuruluşlar, mobil cihaz yönetimi sağlayıcısı yoluyla cihaza ilke ve uygulama gönderebilir. 

Cihazınızdan iş veya okul bilgilerine sürekli erişim edinmek için cihazınızı ilke ayarlarına uyum sağlayacak şekilde yapılandırmanız gerekir. Bu makale, cihazınızın kuruluş gereksinimlerine uyum sağlaması amacıyla iOS için Intune Şirket Portalı uygulamasının cihazı kaydetmenize, yapılandırmanıza ve cihaz bakımını yapmanıza nasıl yardımcı olduğunu açıklar.

> [!NOTE]
> Posta uygulamasından şirket e-postalarına erişmeye çalışıyorsanız cihazınızın güvenliğini sağlamak için büyük olasılıkla cihazı yönetime kaydetmeniz istenmiştir. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.

## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz

### <a name="security"></a>Güvenlik
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra yapmanız gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.    

### <a name="protection"></a>Protection
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bunun gibi uygulama koruma ilkeleri, kuruluşlarda yaygın olarak kullanılır ve erişimi geri almanız için güvenilmeyen uygulamaları kaldırmanızı gerektirir.

### <a name="setting-notifications"></a>Bildirimleri ayarlama
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md). 

## <a name="before-you-start"></a>Başlamadan önce

- Başladıktan sonra tüm işlemi tamamladığınızdan emin olun. Birkaç dakikadan uzun süre duraklarsanız kurulum sonlanabilir ve baştan başlamanız gerekebilir.  
    - Bu işlemin başarısız olması durumunda, Şirket Portalı uygulamasına dönün ve yeniden deneyin.  
- Wi-Fi bağlantısının ve Safari’nin cihazınızda çalıştığından emin olun.
- [Intune Şirket Portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) indirin ve yükleyin.


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Şirket kaynaklarına erişimi ayarlamak için Şirket Portalı uygulamasını kullanma

|Gördüğünüz|Açıklama|
|---|---|
|![Şirket Portalı oturum açma ekranında, alttaki “Oturum aç” düğmesi.](./media/ios-01-cp-enroll-1802.png)|Şirket Portalı uygulamasını açın ve **Oturum Aç**’a dokunun.|
|![Azure AD oturum açma istemi.](./media/ios-02-cp-enroll-1802.png)|Şirket e-posta adresinizi girin ardından **İleri**’ye dokunun.|
|![Azure AD parola istemi.](./media/ios-03-cp-enroll-1802.png)|Parolanızı girin ve ardından **Oturum Aç**’a dokunun.|
|![Şirket kaynaklarının açılış ekranı yükleniyor.](./media/ios-04-cp-enroll-1802.png)|Bu ekranın yüklenmesini bekleyin.|
|![Hüküm ve koşullar sayfası.](./media/ios-05-cp-enroll-1802.png)|Hüküm ve Koşulları okuyun ve **Hepsini Kabul Edin**.|
|![Şirket erişim ekranını ayarla. Hem yönetim hem de ayarlar şu anda çözülmeye ihtiyaç duyuyor.](./media/ios-06-cp-enroll-1802.png)|Cihazınızın şirket kaynaklarına erişebilmesi sürecini başlatmak için **Başlat**’a dokunun. Bunu şimdi yapamazsan, işlemi **Erteleyebilirsin**, ancak e-posta,belge ve daha pek çok şey alamayacağınız anlamına gelir.|
|![Şirket ekranım ne görebilir?](./media/ios-07-cp-enroll-1802.png)|En altındaki bağlantıya dokunarak şirketinizin neyi görebileceği hakkında **daha fazla bilgi edinebilirsiniz**. Aksi takdirde **Devam**’a dokunun.|
|![Sırada ne var ekranı.](./media/ios-08-cp-enroll-1802.png)|Bu ekran, kurulumda olan biten hakkında sizi bilgilendirir. Bu işlemi tamamlarken Safari, Ayarlar uygulaması ve Şirket Portalı uygulamasında vakit geçireceksiniz. **Devam**’a dokunun.|
|![Sırada ne var?'a dokunduktan sonra yükleme ekranı.](./media/ios-09-cp-enroll-1802.png)|Bu ekranın yüklenmesini bekleyin.|
|![Kaydolmak için Safari'ye geçildi.](./media/ios-7-cp-enroll-1711.png)|Cihazınız için yönetim bilgisi almak için Safari'ye gönderildiniz.|
|![Sistem, Ayarlar uygulaması açılmasını isteyecektir.](./media/ios-8-cp-enroll-1711.png)|Yapılandırma profilini indirmek için Ayarlar uygulamasını açmasına **izin ver**’e dokunun. Şirketinizin şirket bilgilerinizi cihazınızda yönetmesine izin vermek için bunu yükleyin.|
|![Profil, cihaz ayarlarını açar.](./media/ios-9-cp-enroll-1711.png)|**Yükle**’ye dokunun.|
|![Profil kalıcı iletişim kutusunu ekranın alt kısmında yükleme.](./media/ios-10-cp-enroll-1711.png)|**Yükle**’ye dokunun.|
|![Profili yükleme ekranını yüklüyor.](./media/ios-11-cp-enroll-1711.png)|Bu ekranın yüklenmesini bekleyin.|
|![Profil yönetimi uyarı ekranı.](./media/ios-12-cp-enroll-1711.png)|Apple tarafından yazılan bu uyarı, yönetilen bir cihazda hangi tür işlemlerin yapılabileceği hakkında daha fazla bilgi sağlar. [Şirketinizin hangi bilgileri görebileceği](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) hakkında daha fazla bilgi.|
|![Uzaktan yönetim güveni hakkında soran sistem istemi.](./media/ios-13-cp-enroll-1711.png)|Şirketinizin cihazınızdaki kurumsal bilgileri ve ayarları yönetmesine izin vermek için **Güven** 'e dokunun.|
|![Profil sonlandırma yükleme ekranını yüklüyor.](./media/ios-14-cp-enroll-1711.png)|Bu ekranın yüklenmesini bekleyin.|
|![Profil ekranı yükledi.](./media/ios-15-cp-enroll-1711.png)|Profiliniz yüklendi ve cihazınızın kurumsal bilgileri ve ayarları yönetilmeye çok daha yakın.|
|![Kaydolmak için Safari'ye geçildi.](./media/ios-16-cp-enroll-1711.png)|Cihazınızla ilgili yönetim bilgilerini almak için Safari'ye geri gönderildiniz. |
|![Şirket portalını açmak için sistem istemi.](./media/ios-17-cp-enroll-1711.png)|**Aç**’a dokunun.|
|![Şirket kaynaklarının ekranı yükleniyor.](./media/ios-21-cp-enroll-1802.png)|Bu ekranın yüklenmesini bekleyin.|
|![Şirket portalı uygulamasında cihaz kategorisini seçin.](./media/ios-22-cp-enroll-1802.png)|Cihazınız için en uygun kategoriyi seçin. Bu genellikle cihazın sahibi kiminle veya genelde nerede bulunduğuyla ilgilidir.|
|![Kategori seçildi.](./media/ios-23-cp-enroll-1802.png)||
|![Cihaz yönetimi başarılı; şimdi ayarları güncelleştirmeniz gerekir.](./media/ios-24-cp-enroll-1802.png)|Cihazınızı başarıyla yönettiniz. Şirketinizin güncelleştirme yapması gerekebileceği, şifrenizin uzunluğu gibi muhtemel ayarlar hala mevcut. Devam etmek için **Devam**’a dokunun.|
|![Cihaz ayarları onaylanıyor.](./media/ios-25-cp-enroll-1802.png)|Şirket Portalı, ayarlarınızdan herhangi birinin güncelleştirilmesinin gerekip gerekmediğini kontrol edecektir.|
|![Ayarlar denetimi, yanlış bir işletim sistemi sürümü ile tamamlandı](./media/ios-26-cp-enroll-1802.png)|Şirket Portalı, ayarlarınızla ilgili tüm sorunları nasıl çözebileceğiniz konusunda yönergeler verecektir. Sorunlarını giderme tamamladıktan sonra **Ayarları Denetle**’ye dokunun.|
|![Cihaz ayarları yükleme ekranını onaylama](./media/ios-27-cp-enroll-1802.png)|Cihazınız ayarlarınızın şirket kaynaklarına erişecek kadar güvenli olup olmadığını kontrol edecektir.|
|![Başarıyla kaydedilmiş ve güncelleştirilmiş ayarlar](./media/ios-28-cp-enroll-1802.png)|Tebrikler! Cihazınız artık Intune'a kaydedilmiştir.|

> [!Note]
> Cihazınız tamamen yönetilmeden önce birkaç adım daha kaldı. [Telekom gider yönetimini kullanarak cihazınızı kaydetme](enroll-your-device-with-telecom-expense-management-ios.md) hakkında daha fazla bilgi edinin. Kuruluşunuz Apple’ın Aygıt Kayıt Programı’nı kullanıyorsa [buraya](enroll-your-device-dep-ios.md) tıklayarak daha fazla bilgi edinebilirsiniz.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
