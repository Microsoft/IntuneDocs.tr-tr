---
title: "Şirket kaynaklarına erişimi ayarlama | Microsoft Docs"
description: "IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar"
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: fa96b26e526e5eca1606dbd2444ee7ebeb2d0d43
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-access-to-your-company-resources"></a>Şirket kaynaklarına erişimi ayarlama

Şirketiniz e-postadan dosyalara, ağlara ve daha fazlasına kadar çok sayıda şirket dosyası içeriyor. Şirketiniz, bu bilgiyi iOS cihazınızdan eriştiğinizde korumak için Microsoft Intune kullanıyor. Bu, onların bu kaynakları yönetmelerini, onları daha güvenli tutmalarını ve işinizi tamamlamak için tercih edilen cihazınızı kullanma özgürlüğünü sağlar.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> Posta uygulamasından şirket e-postalarına erişmeye çalışıyorsanız cihazınızın güvenliğini sağlamak için büyük olasılıkla cihazı yönetime kaydetmeniz istenmiştir. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.

## <a name="before-you-start"></a>Başlamadan önce

- Başladığınızda tüm işlemi tamamladığınızdan emin olun. Birkaç dakikadan daha uzun süre duraklatmak genellikle ilerlemenizi durdurur ve baştan başlamanızı gerektirir.
- Bu işlemin başarısız olması durumunda, yeniden denemek için Şirket Portalı uygulamasına dönmeniz gerekir.
- Wi-Fi'nin çalıştığından ve Safari'nin cihazınızda çalıştığından emin olun.
- [Intune Şirket Portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) indirin ve yükleyin.


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Şirket kaynaklarına erişimi ayarlamak için Şirket Portalı uygulamasını kullanma

|Gördüğünüz|Açıklama|
|---|---|
|![Şirket Portalı oturum açma ekranında, alttaki "Oturum aç" düğmesi.](./media/ios-0-cp-enroll-1711.png)|Cihazınızda Şirket Portalı uygulamasını açın ve **Oturum Aç**’a dokunun.|
|![Azure AD oturum açma istemi.](./media/ios-0a-cp-enroll-1711.png)|Şirket e-posta adresinizi girin ardından **İleri**’ye dokunun.|
|![Azure AD parola istemi.](./media/ios-0b-cp-enroll-1711.png)|Parolanızı girin ve ardından **Oturum Aç**’a dokunun.|
|![Şirket kaynaklarının açılış ekranı yükleniyor.](./media/ios-1-cp-enroll-1711.png)|Yüklenmesini bekleyin.|
|![Hüküm ve Koşullar.](./media/ios-2-cp-enroll-1711.png)|Hüküm ve Koşulları okuyun ve **Hepsini Kabul Edin**.|
|![Şirket erişim ekranını ayarla. Hem yönetim hem de ayarlar şu anda çözülmeye ihtiyaç duyuyor.](./media/ios-3-cp-enroll-1711.png)|Cihazınızın şirket kaynaklarına erişebilmesi sürecini başlatmak için **Başlat**’a dokunun. Bunu şimdi yapamazsan, işlemi **Erteleyebilirsin**, ancak e-posta,belge ve daha pek çok şey alamayacağınız anlamına gelir.|
|![Şirket ekranım ne görebilir?](./media/ios-4-cp-enroll-1711.png)|En altındaki bağlantıya dokunarak şirketinizin neyi görebileceği hakkında **daha fazla bilgi edinebilirsiniz**. Aksi takdirde **Devam**’a dokunun.|
|![Sırada ne var ekranı.](./media/ios-5-cp-enroll-1711.png)|Bu ekran, kurulumda olan biten hakkında sizi bilgilendirir. Bu işlemi tamamlamak için Safari, Ayarlar uygulaması ve Şirket Portalı uygulamasında vakit geçireceksiniz. **İleri**’ye dokunun.|
|![Sırada ne var?'a dokunduktan sonra yükleme ekranı.](./media/ios-6-cp-enroll-1711.png)||
|![Kaydolmak için Safari'ye geçildi.](./media/ios-7-cp-enroll-1711.png)|Cihazınız için yönetim bilgisi almak için Safari'ye gönderildiniz.|
|![Sistem, Ayarlar uygulaması açılmasını isteyecektir.](./media/ios-8-cp-enroll-1711.png)|Yapılandırma profilini indirmek için Ayarlar uygulamasını açmasına **izin ver**’e dokunun. Şirketinizin şirket bilgilerinizi cihazınızda yönetmesine izin vermek için bunu yükleyin.|
|![Ayarlarda profil açık durumdadır.](./media/ios-9-cp-enroll-1711.png)|**Yükle**’ye dokunun.|
|![Profil kalıcı iletişim kutusunu ekranın alt kısmında yükleme.](./media/ios-10-cp-enroll-1711.png)|**Yükle**’ye dokunun.|
|![Profili yükleme ekranını yüklüyor.](./media/ios-11-cp-enroll-1711.png)|Yüklenmesini bekleyin.|
|![Profil yönetimi uyarı ekranı.](./media/ios-12-cp-enroll-1711.png)|Apple tarafından yazılan bu uyarı, yönetilen bir cihazda hangi tür işlemlerin yapılabileceği hakkında daha fazla bilgi sağlar. [Şirketinizin hangi bilgileri görebileceği](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) hakkında daha fazla bilgi.|
|![Uzaktan yönetim güveni hakkında soran sistem istemi.](./media/ios-13-cp-enroll-1711.png)|Şirketinizin cihazınızdaki kurumsal bilgileri ve ayarları yönetmesine izin vermek için **Güven** 'e dokunun.|
|![Profil sonlandırma yükleme ekranını yüklüyor.](./media/ios-14-cp-enroll-1711.png)|Yüklenmesini bekleyin.|
|![Profil ekranı yükledi.](./media/ios-15-cp-enroll-1711.png)|Profiliniz yüklendi ve cihazınızın kurumsal bilgileri ve ayarları yönetilmeye çok daha yakın.|
|![Kaydolmak için Safari'ye geçildi.](./media/ios-16-cp-enroll-1711.png)|Cihazınızla ilgili yönetim bilgilerini almak için Safari'ye geri gönderildiniz. |
|![Şirket portalını açmak için sistem istemi.](./media/ios-17-cp-enroll-1711.png)|**Aç**’a dokunun.|
|![Şirket kaynaklarının ekranı yükleniyor.](./media/ios-18-cp-enroll-1711.png)|Yüklenmesini bekleyin.|
|![Şirket portalı uygulamasında cihaz kategorisini seçin.](./media/ios-19-cp-enroll-1711.png)|Cihazınız için en uygun kategoriyi seçin. Bu genellikle cihazın sahibi kiminle veya genelde nerede bulunduğuyla ilgilidir.|
|![Kategori seçildi.](./media/ios-20-cp-enroll-1711.png)||
|![Cihaz yönetimi başarılı; şimdi ayarları güncelleştirmeniz gerekir.](./media/ios-21-cp-enroll-1711.png)|Cihazınızı başarıyla yönettiniz. Şirketinizin güncelleştirme yapması gerekebileceği, şifrenizin uzunluğu gibi muhtemel ayarlar hala mevcut. Devam etmek için **Devam**’a dokunun.|
|![Cihaz ayarları onaylanıyor.](./media/ios-22-cp-enroll-1711.png)|Şirket Portalı, ayarlarınızdan herhangi birinin güncelleştirilmesinin gerekip gerekmediğini kontrol edecektir.|
|![Ayarlar denetimi, yanlış bir işletim sistemi sürümü ile tamamlandı](./media/ios-23-cp-enroll-1711.png)|Şirket Portalı, ayarlarınızla ilgili tüm sorunları nasıl çözebileceğiniz konusunda yönergeler verecektir. Sorunlarını giderme tamamladıktan sonra **Ayarları Denetle**’ye dokunun.|
|![Cihaz ayarları yükleme ekranını onaylama](./media/ios-24-cp-enroll-1711.png)|Cihazınız ayarlarınızın şirket kaynaklarına erişecek kadar güvenli olup olmadığını kontrol edecektir.|
|![Başarıyla kaydedilmiş ve güncelleştirilmiş ayarlar](./media/ios-25-cp-enroll-1711.png)|Tebrikler! Cihazınız artık Intune'a kaydedilmiştir.|

> [!Note]
> Cihazınız tamamen yönetilmeden önce birkaç adım daha kaldı. [Telekom gider yönetimini kullanarak cihazınızı kaydetme](enroll-your-device-with-telecom-expense-management-ios.md) hakkında daha fazla bilgi edinin. Kuruluşunuz Apple’ın Aygıt Kayıt Programı’nı kullanıyorsa [buraya](enroll-your-device-dep-ios.md) tıklayarak daha fazla bilgi edinebilirsiniz.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın.
