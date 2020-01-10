---
title: Intune Şirket Portalı Windows cihaz kaydı | Microsoft Docs
description: Şirket Portalı Windows cihazını kaydetmeye başlama
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 86c158f73d820fa2e719fe92b884c77f315fcb94
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75858820"
---
# <a name="windows-device-enrollment-in-intune-company-portal"></a>Intune Şirket Portalı Windows cihaz kaydı  

İş ve okul uygulamalarına, e-postalarına ve dosyalarına güvenli erişim sağlamak için Windows cihazınızı Intune Şirket Portalı uygulamasına kaydedin. Kuruluşunuz Office veya OneDrive gibi belirli uygulamalar gerektiriyorsa veya öneriyorlarsa, bunları kayıt sırasında alacaksınız ya da kayıt sonrasında Şirket Portalı kullanılabilir.  

Windows 10 cihazlarını Şirket Portalı Web sitesi *veya* uygulaması aracılığıyla kaydedebilirsiniz. Windows 'un önceki bir sürümüyle bir cihaz kaydediyorsanız, cihazı Şirket Portalı Web sitesinden kaydetmeniz gerekir.  

## <a name="install-company-portal-app"></a>Şirket Portalı uygulamasını yükler  
Cihazınızda Şirket Portalı uygulamanız zaten yüklü olabilir. __Tüm uygulamalar__ listenizde uygulamayı denetleyin.  Uygulama listenizde Şirket Portalı görmüyorsanız, yüklemek için aşağıdaki adımları izleyin.  

1. Cihazınızda **Microsoft Store** açın.

2. **Arama** alanına **Şirket portalı**yazın.

3. Sonuçlar listesinde **Şirket Portalı** > **Yükle**’yi seçin.

4. **Yükle** veya **Ücretsiz**’i seçin. Bu iki seçenek arasında fark yoktur; sözcükler, kuruluşunuzun uygulamayı nasıl ayarlauna göre görünür.  

## <a name="find-windows-10-version-number"></a>Windows 10 sürüm numarasını bul  
Kayıt adımları farklı Windows 10 cihazlarının sürümleri için farklılık gösterir. Aşağıdaki adımlarda, Windows 10 Masaüstü ve mobil cihazlarda sürüm numarasının nasıl bulunacağı açıklanır. Sürümünüzü öğrendikten sonra, önerilen kayıt adımlarına devam edin.  

### <a name="windows-10-desktop-devices"></a>Windows 10 Masaüstü cihazlar  

1. **Başlat**'a gidin.

2. Arama çubuğuna "Bilgisayarınız hakkında" ifadesini yazın. Sonuçlardan Bilgisayarınız __hakkında__ ' yı seçin.  


   ![bilgisayarınız hakkında araması için arama ayarları](media/searching_for_about_your_pc.png)  

3. Bilgisayarınızda yüklü olan Windows 10 **sürümünü** bulmak için **Windows belirtimlerine** gidin.  


   ![Windows 10 Masaüstü Bilgisayarınız Hakkında](media/settings_about_pc.png)  

4. Sürümünüz  

    * __1607 veya üzeri__: [ > **Hesap** > **iş veya okul rotası erişimine erişim** ](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device)için cihazınızı kaydedin.   
    * __1511 veya önceki sürümler__: hesap [yönlendirmenize > **ayarları** > **Hesap** ](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device)yoluyla cihazınızı kaydedin.  

### <a name="windows-10-mobile-devices"></a>Windows 10 Mobile cihazları

1. __Tüm uygulamalar__ ' a gidin ve __Ayarlar__ uygulamasını seçin.
2. __Sistem__ > __Hakkında__’yı seçin.
3. __Cihaz bilgileri__altında __sürümü__bulun.  
4. Sürümünüz  

    * __1607 veya üzeri__: [ **Iş veya okul rotası erişimi** > **ayarları** ](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device)kullanarak cihazınızı kaydedin.   
    * __1511 veya önceki sürümler__: [ **ayarları** > **hesapları** yolunu](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device)kullanarak cihazınızı kaydedin.  

## <a name="enroll-non-windows-10-devices"></a>Windows 10 olmayan cihazları kaydetme  
Şirket Portalı Web sitesi aracılığıyla desteklenen diğer Windows cihazlarını kaydetmek için aşağıdaki makaleleri kullanın:   
* [Windows 8.1. veya Windows RT 8,1 cihazı](enroll-your-W81-or-rt81-windows.md)  
* [Windows Phone 8,1 cihazı](enroll-your-wp81-windows.md)    

## <a name="it-administrator-support"></a>BT yöneticisi desteği  
BT yöneticisiyseniz ve cihazları kaydederken sorun yaşıyorsanız, bkz. [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](https://support.microsoft.com/help/4469913). Bu makalede, sık karşılaşılan hatalar, nedenler ve bunları çözmeye yönelik adımlar listelenir.  

## <a name="next-steps"></a>Sonraki adımlar  
Artık desteklenen cihazları ve Windows 10 sürüm numaranızı bildiğinize göre önerilen kayıt makalesine ilerleyin.  
 
Cihaz yönetimi, Şirket Portalı ve her ikisinin de okulda ve iş üzerinde nasıl kullanıldığı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
* [İş veya okul kaynağına erişmek için yönetilen cihazları kullanma](use-managed-devices-to-get-work-done.md)  
* [Cihazınızı Intune 'A kaydettiğinizde ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)  
* [Cihazımı kaydettiğimde kuruluşumdaki bilgiler neleri görebilir?](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)  

Yardıma mı ihtiyacınız var? Şirketinizin destek bölümüne başvurun. Kuruluşunuzun BT iletişim bilgilerini bulmak için [Şirket portalı Web sitesine gidin](https://go.microsoft.com/fwlink/?linkid=2010980) .  
