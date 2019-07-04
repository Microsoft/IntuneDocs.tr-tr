---
title: Intune şirket Portalı'nda Windows cihaz kaydı | Microsoft Docs
description: Şirket portalı'nda Windows cihaz kaydetmeye başlama
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: df0afecb006ef8837f888b3b9209d5892d90a228
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546374"
---
# <a name="windows-device-enrollment-in-intune-company-portal"></a>Intune şirket Portalı'nda Windows cihaz kaydı  

Windows Cihazınızı iş ve Okulunuzun uygulamalarına, e-postaları ve dosyalarına güvenli erişim elde etmek için Intune Şirket portalı uygulamasını kaydetme. Kuruluşunuz gerektirir ya da belirli uygulamaları önerir, Office veya OneDrive gibi ya da bunları kayıt sırasında alırsınız veya kayıttan sonra şirket Portalı'nda kullanılabilir olmaları.  

Şirket portalı Web sitesi aracılığıyla Windows 10 cihazları kaydedebilirsiniz *veya* uygulama. Önceki bir Windows sürümü ile cihaz kaydetme, Şirket portalı Web sitesinden bir cihazı kaydetmesi gerekir.  

## <a name="install-company-portal-app"></a>Yükleme Şirket portalı uygulaması  
Zaten Şirket portalı uygulamasının Cihazınızda yüklü olabilir. Uygulamada denetle, __tüm uygulamalar__ listesi.  Uygulamalar listenizde şirket Portalı'nı görmüyorsanız, yüklemek için aşağıdaki adımları izleyin.  

1. Açık **Microsoft Store** Cihazınızda.

2. İçinde **arama** alanına **Şirket portalı**.

3. Sonuçlar listesinde **Şirket Portalı** > **Yükle**’yi seçin.

4. **Yükle** veya **Ücretsiz**’i seçin. Bu iki seçenek arasındaki fark yoktur; sözcükleri kuruluşunuz uygulamasını nasıl ayarlama göre görüntülenir.  

## <a name="find-windows-10-version-number"></a>Windows 10 sürüm numarası bulun  
Kayıt adımları Windows 10 cihazlarını farklı sürümleri için farklıdır. Aşağıdaki adımlar, Windows 10'da sürüm numarasını bulmak açıklanmaktadır Masaüstü ve mobil cihazlar. Sürümünüzü bulduktan sonra önerilen kayıt adımlara devam edin.  

### <a name="windows-10-desktop-devices"></a>Windows 10 Masaüstü cihazlar  

1. **Başlat**'a gidin.

2. Bilgisayarınız hakkında"." tümceciği Arama çubuğuna yazın Seçin __bilgisayarınız hakkında__ sonuçlarından.  


   ![bilgisayarınız hakkında araması için arama ayarları](media/searching_for_about_your_pc.png)  

3. Ekranı aşağı kaydırarak **Windows belirtimleri** bulmak için **sürüm** Bilgisayarınızda yüklü olan Windows 10 'un.  


   ![Windows 10 Masaüstü Bilgisayarınız Hakkında](media/settings_about_pc.png)  

4. Sürümünüz  

    * __1607 veya üzeri__: Sunar kaydetme [ **ayarları** > **hesabı** > **işe veya okula erişim** rota](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 veya önceki__: Sunar kaydetme [ **ayarları** > **hesabı** > **hesaplarınızı** rota](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

### <a name="windows-10-mobile-devices"></a>Windows 10 Mobile cihazları

1. Git __tüm uygulamalar__ seçip __ayarları__ uygulama.
2. __Sistem__ > __Hakkında__’yı seçin.
3. Altında __cihaz bilgilerini__, bulma __sürüm__.  
4. Sürümünüz  

    * __1607 veya üzeri__: Cihaz kullanarak kaydolmayı [ **ayarları** > **işe veya okula erişim** rota](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 veya önceki__: Cihaz kullanarak kaydolmayı [ **ayarları** > **hesapları** rota](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

## <a name="enroll-non-windows-10-devices"></a>Windows 10 olmayan cihazları kaydetme  
Şirket portalı Web sitesi üzerinden desteklenen diğer Windows cihazlarını kaydetmek için aşağıdaki makaleleri kullanın:   
* [Windows 8.1. veya Windows RT 8.1 cihazınız](enroll-your-W81-or-rt81-windows.md)  
* [Windows Phone 8.1 cihaz](enroll-your-wp81-windows.md)    

## <a name="it-administrator-support"></a>BT yöneticisi desteği  
Bir BT yöneticisi olduğunuzu ve cihazlarını kaydederken sorunları Çalıştır bkz [sorun giderme Windows cihaz kaydı sorunlarını Microsoft Intune](https://support.microsoft.com/help/4469913). Yaygın hatalar, nedenleri ve adımları bunları gidermek için bu makalede listelenmektedir.  

## <a name="next-steps"></a>Sonraki adımlar  
Desteklenen cihazlar ve Windows 10 sürüm numaranızın bildiğiniz, önerilen kayıt makaleden devam edin.  
 
Şirket portalı ve her ikisi de okullar ve iş kullanılma, cihaz yönetimi hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
* [İş veya Okul kaynak yönetilen cihazları kullanma](use-managed-devices-to-get-work-done.md)  
* [Cihazınızı ıntune'a kaydettiğinizde ne olur](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)  
* [Ben cihazımı kaydettiğimde Kuruluşum hangi bilgileri görebilir?](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)  

Yardım mı gerekiyor? Şirketinizin destek bölümüne başvurun. [Şirket portalı Web sitesine gidin](https://go.microsoft.com/fwlink/?linkid=2010980) kuruluşunuzun bulmak için BT iletişim bilgileri.  
