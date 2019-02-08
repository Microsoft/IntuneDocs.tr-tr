---
title: Android cihazınızdaki yönetilen uygulamaları kullanma | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ed10a62c-b026-4ad3-ac41-641933522df2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3ba4ca5ccc9083f2132a8b8893c3bc2070ed3c50
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841343"
---
# <a name="use-managed-apps-on-your-android-device"></a>Android cihazınızdaki yönetilen uygulamaları kullanma
Yönetilen uygulamalar, kuruluşunuzun güvenlik gereksinimlerini karşılamak ve iş veya okul verilerini korumak üzere yapılandırılmıştır. Bu uygulamalar, otomatik olarak yüklemeniz veya kullanmanız için cihazınızda sunulmuştur. 

Siz bir yönetilen uygulamayı alıp yüklemeden önce kuruluşunuz bu uygulamanın izinlerini yapılandırır. Kuruluşunuz, uygulama verilerinin yetkisiz kişiler tarafından paylaşılmasını veya görülmesini engellemek için uygulama işlevselliğini veya kullanıcı etkileşimlerini kısıtlayabilir. Örneğin bir kuruluş, uygulama içerisinde kopyalama ve yapıştırma işlemlerini engelleyebilir. Veya cihazınızın yerel depolama alanına veri kaydetmenizi önleyebilir.

Veri korumasını en üst düzeye çıkarmak için kuruluşunuz, birkaç yönetilen uygulamayı birlikte çalışmak üzere yapılandırabilir. Örneğin:
1. Kuruluşunuzun ağına Microsoft Edge gibi bir yönetilen tarayıcı uygulaması ile bağlanırsınız.
2. İş arkadaşınızın sunu dosyasını açmak için bir bağlantıya tıklarsınız.
3. Microsoft PowerPoint gibi uygun bir yönetilen uygulama bu dosyayı açar.

Kuruluşlar, bir iş dosyasını açmak veya bir web bağlantısına erişmek gibi işlemler için yönetilen uygulamalar kullanmanızı gerektirebilir. Gereken uygulamaya sahip değilseniz işleme devam edemeyebilirsiniz. Bazı yönetilen uygulamalar yüklenmeye açık olsa da gerekli değildir.

## <a name="how-do-i-know-im-using-a-managed-app"></a>Yönetilen uygulama kullandığımı nasıl anlarım?
Yönetilen uygulamalarda iş veya okul verilerinize ilk eriştiğinizde, aşağıdaki ekran görüntüsündekine benzer bir ileti alırsınız. İleti, devam etmek için uygulamayı yeniden başlatmanızı ister.

![Bir kullanıcı cihazında yönetilen uygulama açtığında görüntülenen iletinin ekran görüntüsü. İletide “Kuruluşunuz artık bu uygulama içerisindeki verilerini korumuyor. Devam etmek için uygulamayı yeniden başlatmanız gerekiyor.” ifadesi ve ardından Tamam düğmesi yer alır.](./media/managed-apps-message.png)

## <a name="commonly-managed-apps"></a>Yaygın olarak yönetilen uygulamalar  
Okullar ve iş yerlerinde yaygın olarak gerekli veya kullanılabilir hale getirilen yönetilen uygulama örnekleri:

-   Microsoft Edge

-   Microsoft Outlook

-   Microsoft Word, Excel ve PowerPoint

## <a name="how-do-i-get-managed-apps"></a>Yönetilen uygulamaları nasıl edinirim?
Önce Şirket Portalı uygulamasını yüklemeniz ve daha sonra gerekirse cihazınızı yönetime kaydetmeniz gerekir. Sonrasında yönetilen uygulama edinmenin üç yolu vardır.
* Kuruluşunuz, kayıt sırasında cihazınıza uygulamaları otomatik olarak yükler. Kayıt hakkında daha fazla bilgi edinmek için bkz. [Cihazınızı Intune’a kaydetme](enroll-your-device-in-Intune-android.md).
* Kuruluşunuz, yönetilen uygulamaları Şirket Portalı’nda sizin için kullanılabilir hale getirir. Şirket Portalı uygulamasına veya Web sitesine giderek bu uygulamaları arayabilir, görüntüleyebilir ve yükleyebilirsiniz. 
* Google Play mağazasından bir uygulama yükleyip uygulamada iş veya okul hesabınızla oturum açarsınız.  

 ## <a name="available-apps"></a>Kullanılabilir uygulamalar   
 Kuruluşunuz sizin için işe veya okula uygun ve kullanışlı uygulamalar seçer. Bu uygulamalar, şirket Portalı'nda bulabilirsiniz yalnızca olanlardır.   

 Uygulamalar Ayrıca, cihaz türüne göre sunulur. Örneğin, Android için Şirket portalı uygulamasını kullanıyorsanız, Android uygulamaları, ancak iOS uygulamaları için erişim gerekir.   

 ## <a name="request-an-app-for-work-or-school"></a>İş veya Okul için uygulama istek   
 Bir uygulama gerekir, ancak şirket portalında görmüyorum varsa, isteyebilirsiniz. İletişim ayrıntılarını bulun, **Yardım Masası** Şirket portalı uygulamasının **BT'ye** sekmesi. Aynı iletişim bilgilerini bulabilirsiniz [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980).   

## <a name="what-can-my-company-support-manage-in-an-app"></a>Şirketimin destek birimi bir uygulamada neleri yönetebilir?  
Aşağıdaki liste, şirketinizin destek biriminin bir uygulama içerisinde yönetebileceği ayarları açıklar. Bu ayarlar, cihazınızda iş veya okul verilerini görüntülemenizi, bunlara erişiminizi ve bunları nasıl kullanacağınızı etkiler:

* Belirli web sitelerine erişim  

* Edge ve Azure Active Directory ara sunucusunu kullanarak dahili şirket web sitelerine erişim  

* En düşük uygulama sürümü, işletim sistemi sürümü

* Uygulamalar arasında veri paylaşımı ve aktarımı özelliği  

* Dosyaların nasıl ve nereye kaydedileceği  

* Kopyalama ve yapıştırma işlevi  

* PIN erişimi gereksinimleri  

* Şirket kimlik bilgilerini kullanarak oturum açma  

* Buluta veri yedekleme özelliği  

* Ekran görüntüleri alma özelliği  

* Veri şifreleme gereksinimleri  

Cihazınızdaki yönetilen uygulamalar hakkında daha fazla bilgi için şirketinizin destek birimiyle iletişim kurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
