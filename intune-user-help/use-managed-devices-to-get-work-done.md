---
title: İşleri halletmek için yönetilen cihazları kullanma | Microsoft Docs
description: Cihazınızı Intune yönetimine kaydetmenin ne anlama geldiğini anlayın.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54bdef2252467de9cd06e5b5f0a7c38acc38ba88
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61505327"
---
# <a name="enroll-device-for-access-to-work-or-school-resources"></a>İş veya Okul kaynaklarına erişim için Cihazınızı kaydetme
Cihazınızı kaydetme ve e-posta ve uygulamalarına erişmesini almak için Intune Şirket portalı uygulaması veya Microsoft Intune uygulama yüklemeniz gerekir. Kaydolduğunuzda, kuruluşunuz, parola, PIN ve şifreleme gibi yapılandırılmış temel yönetim ilkeleri, cihazınıza uygulanır. Cihaz ayarlarınızı tüm kuruluşunuzun gereksinimlerini karşılayan sonra iş bilgilerinize hemen her yerden güvenli bir şekilde erişebilirsiniz.  

Şirket portalı ve Microsoft Intune uygulamalar, cihaz ayarlarınızı kuruluşunuzun ilkeleriyle eşleştirmek sağlayarak kayıtlı cihazınızın güvenli tutun. 

Şirket portalı uygulamasını da:  
* Kişisel bilgilerle iş bilgilerini birbirinden ayrı tutar.  
* Bulmak ve ilgili iş ve Okul uygulamaları yüklemek kolaylaştırır.   

## <a name="get-the-apps"></a>Uygulama edinin
Şirket portalı almak için:

- Platforma özgü uygulama Mağazası'ndan Şirket portalı uygulamasını yükleyin. Bazı durumlarda, kuruluşunuzun şirket portalı uygulamasını sizin için yükler.  
- Git [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) uygulamaya bir tarayıcıdan erişim.  

Intune uygulamayı kullanmak için gereken, kuruluşunuzun bunu sizin için yükler.  


## <a name="what-information-can-my-company-see-when-i-enroll"></a>Miyim kaydettiğimde Şirketim hangi bilgileri görebilir?
Cihazınız kaydedildikten sonra kuruluşunuzun destek kişiler yalnızca çalışmak ilgili bilgiler görebilirsiniz. Bunlar, kişisel bilgilerinizi göremez. Varsa, işte kullanmak için kişisel bir cihazı kaydetme [tam olarak neleri görebileceği ve neleri görülemeyen öğrenin](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).  


## <a name="whats-the-difference-between-the-apps-and-the-website"></a>Uygulamaları ve Web sitesi arasındaki fark nedir?
Şirket portalı uygulaması, Windows 10, iOS, macOS ve Android cihazlar için kullanılabilir. Cihazınızın ilgili platformu ile sorunsuz şekilde entegre olur. Web sitesi sürümü herhangi bir CİHAZDAN erişilebilir olduğundan ve hangi cihazı kullanıyor olursanız ne olursa olsun aynı, Evrensel deneyimi sağlar. 

Şirkete ait Android cihazlar için Microsoft Intune uygulamasıdır.  

## <a name="what-kind-of-devices-can-you-enroll-with-company-portal"></a>Ne tür cihazlar Şirket portalı ile kaydolabilir mi?
-   iOS kullanan Apple cihazları (iPhone ve iPad gibi) ve macOS (MacBook ve iMac gibi)
-   Android cihazlar
-   Windows cihazları
    -   Windows 10 Mobile
    -   Windows 10 Masaüstü
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="what-kind-of-devices-can-you-enroll-with-the-microsoft-intune-app"></a>Ne tür cihazlar Intune uygulamayla kaydolabilir mi?  
Kuruluşunuz bu uygulamayla kullanabilmeniz için ayarlanmış şirkete ait Android cihazlarını kaydedebilir. Uygulaması, Android 6.0 ve sonraki sürümleri destekler. 

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Bir bilgisayarı veya cihazı Şirket Portalı’ndan kaldırabilir misiniz?
Bir bilgisayarı veya cihazı Şirket Portalı’ndan kaldırabilir ya da sıfırlayabilirsiniz. **Kaldırma** ile **sıfırlama** işlemi birbirinden farklıdır.

Bir bilgisayarı veya cihazı şirket Portalı'ndan kaldırdığınızda, cihazınızın Intune kaydını kaldırmış olursunuz. Kaydını kaldırdıktan sonra, Şirket Portalı’na artık bu cihazdan erişemezsiniz ve bazı şirket verileri cihazınızdan kaldırılabilir. Cihazınızı şirket Portalı'ndan kaldırma hakkında bilgi için aşağıdaki bağlantılara bakın:  

- [Android cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-android.md)
- [iOS cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-ios.md)
- [macOS cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-macos.md)
- [Windows cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-windows.md)

Bir bilgisayarı veya cihazı sıfırladığınızda Şirket portalı bilgisayarınızı veya Cihazınızı üreticinin varsayılan ayarlarına geri döndürebilir dener. Cihazınız sıfırlandığında tüm şirket ve kişisel verilerinizi CİHAZDAN kaldırır. Cihazınızın kaybolması durumunda, ayrıca, uzaktan Şirket portalı Web sitesinden sıfırlayabilirsiniz.  

Cihazınızı sıfırlama konusunda bilgi almak için bkz: [Şirket portalı Web sitesinden Cihazınızı sıfırlama](reset-erase-your-device-cpwebsite.md).  

## <a name="can-you-remove-a-computer-or-device-from-the-microsoft-intune-app"></a>Bir bilgisayarı veya cihazı Intune uygulamadan kaldırabilir miyim?
Hayır, Microsoft Intune uygulamadan bir kuruluşa ait cihaz kaldırmak bir yolu yoktur.  

## <a name="what-if-i-cant-see-my-device-in-the-company-portal-or-microsoft-intune-app"></a>Cihazımı Şirket portalı ya da Microsoft Intune uygulamasında ne göremiyorum?
Bir cihazı görebilmeniz için önce Şirket Portalı’na eklenmesi gerekir. Yöneticinizin önerdiği Şirket Portalı’na gidin ve cihazınıza yönelik adımları izleyin. Ayrıca, sahibi ve yönetimi şirketinize ait olan cihazları görmezsiniz.

Microsoft Intune uygulama kullanıyorsanız, yalnızca şu anda kullanmakta olduğunuz cihaz görürsünüz. Diğer kaydedilen cihazların uygulamada görünür olmaz.  

## <a name="where-else-can-i-go-for-help"></a>Yardım için başka nereye başvurabilirim?  
Yaygın sorunlar ve sorular sorun gidermek için bu platforma özgü belgeleri kullanıma denetleyin:  

- [Android cihazınızdaki yaygın sorunları çözme](check-compliance-on-your-device-android.md)  
- [iOS cihazınızdaki yaygın sorunları çözme](troubleshoot-your-device-ios.md)
- [macOS cihazınızdaki yaygın sorunları çözme](troubleshoot-your-device-macos.md)
- [Windows cihazınızdaki yaygın sorunları çözme](troubleshoot-your-device-windows.md)

Ayrıca için Destek ekibiyle iletişim kurabilirsiniz. Şirket portalı ve Microsoft Intune uygulama Yardım sağlar ve Destek iletişim bilgileri ve sorun bildir yolları listesi sayfaları. İletişim bilgileri kullanılabilir ayrıca kuruluşunuzun [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="next-steps"></a>Sonraki adımlar  

Cihazınızın platforma özgü kayıt başlayarak yardım alın:  

- [Android cihazınızı kullanma](using-your-android-device-with-intune.md)
- [iOS cihazınızı kullanma](using-your-ios-device-with-intune.md)
- [macOS cihazınızı kullanma](using-your-macos-device-with-intune.md)
- [Windows cihazınızı kullanma](using-your-windows-device-with-intune.md)
- [Şirket portalı web sitesini kullanma](using-the-intune-company-portal-website.md)


