---
title: Windows cihazları için Intune kayıt yöntemleri
titleSuffix: Microsoft Intune
description: Windows cihazlarını Intune 'A kaydedebilmeniz için kullanabileceğiniz farklı yolları öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: 060c3c00a228794d3f237a6362b048bf23e1a933
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547714"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Windows cihazları için Intune kayıt yöntemleri

Intune 'da cihazları yönetmek için önce cihazların Intune hizmetine kaydolması gerekir. Kişisel ve şirkete ait cihazlar, Intune yönetimi için kaydedilebilir. 

Intune 'a kayıtlı cihazları almanın iki yolu vardır:
- Kullanıcılar, Windows bilgisayarlarını kendi kendilerine kaydedebilir 
- Yöneticiler, Kullanıcı katılımı olmadan otomatik kaydı zorlamak için ilkeleri yapılandırabilir

## <a name="user-self-enrollment-in-intune"></a>Intune 'da Kullanıcı kendini kaydetme

Kullanıcılar, aşağıdaki yöntemlerden herhangi birini kullanarak Windows cihazlarını kendi kendilerine kaydedebilir:

- [Kendi cihazını getir (](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device)KCG): kullanıcılar, cihazın **ayarlarından** **iş ve okul** hesabı bağlamayı seçerek kendi kişisel cihazlarını kaydeder. Bu işlem:
  - E-posta gibi kurumsal kaynağa erişim kazanmak için cihazı Azure Active Directory kaydeder.
  - Cihazı Intune 'A bir kişiye ait cihaz (KCG) olarak kaydeder.
Bir yönetici otomatik kaydı yapılandırmışsa (Azure AD Premium abonelikleri ile kullanılabilir), kullanıcının kimlik bilgilerini yalnızca bir kez girmesi gerekir. Aksi takdirde, yalnızca MDM kaydı aracılığıyla ayrı olarak kaydolmaları ve kimlik bilgilerini yeniden girmeniz gerekir.  
- **Yalnızca MDM kaydı** , kullanıcıların var olan bir çalışma grubunu, Active Directory veya Azure Active Directory 'ye KATıLMıŞ bir bilgisayarı Intune 'a kaydetmelerini sağlar. Kullanıcılar, mevcut Windows bilgisayarındaki ayarlardan kaydolmasını ister. Bu yöntem, cihazı Azure Active Directory 'ye kaydetmediği için önerilmez. Koşullu erişim gibi özelliklerin kullanılmasını da engeller.
- [Azure Active Directory (Azure AD) katılma](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) -cihazı Azure Active Directory ile birleştirir ve KULLANıCıLARıN Azure AD kimlik bilgileriyle Windows 'da oturum açmasını sağlar. Otomatik kayıt etkinse cihaz otomatik olarak Intune 'A kaydedilir. Otomatik kayıt 'nin avantajı, Kullanıcı için tek adımlı bir işlemdir. Aksi takdirde, yalnızca MDM kaydı aracılığıyla ayrı olarak kaydolmaları ve kimlik bilgilerini yeniden girmeniz gerekir. Kullanıcılar bu şekilde, ilk Windows OOBE veya ayarlardan bu şekilde kaydolmalarını ister. Cihaz, Intune 'da şirkete ait cihaz olarak işaretlenir.
- [Autopilot](enrollment-autopilot.md) -Azure AD JOIN 'i otomatikleştirir ve şirkete ait yeni cihazları Intune 'a kaydeder. Bu yöntem, kullanıma hazır deneyimi basitleştirir ve cihazlara özel işletim sistemi görüntüleri uygulama gereksinimini ortadan kaldırır. Yöneticiler, Autopilot cihazlarını yönetmek için Intune 'u kullanırken, ilkeler, profiller, uygulamalar ve daha fazlasını kaydolduktan sonra yönetebilir.  Dört tür Autopilot dağıtımı vardır: [kendi kendine dağıtım modu](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (kiosks, dijital imza, veya paylaşılan bir cihaz için), [Kullanıcı odaklı mod](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (geleneksel KULLANıCıLAR için) ve BT personelinin, tam olarak yapılandırılması ve [mevcut cihazlara yönelik](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) olarak Windows 10 ' un en son sürümünü kolayca dağıtmanıza olanak sağlamak için bir Windows 10 PC 'nin ön [sağlamasını sağlar.](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove)

## <a name="administrator-based-enrollment-in-intune"></a>Intune 'da yönetici tabanlı kayıt

Yöneticiler, Kullanıcı etkileşimi gerektirmeyen kayıt için aşağıdaki yöntemleri ayarlayabilir:

- [Karma Azure AD katılım](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) , yöneticilerin karma Azure AD 'ye katılmış cihazları otomatik olarak kaydetmesi için Active Directory Grup İlkesi 'ni yapılandırmalarına olanak tanır. 
- [Configuration Manager ortak yönetimi](https://docs.microsoft.com/configmgr/comanage/overview) , yöneticilerin, ıntune ve Configuration Manager 'nin iki avantajına sahip olan mevcut Configuration Manager yönetilen cihazlarını Intune 'a kaydetmelerini sağlar. 
- [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) (DEM) özel bir hizmet hesabıdır. DEM hesaplarının, yetkili kullanıcıların birden çok şirkete ait cihazı kaydetmesine ve yönetmesine izin veren izinleri vardır. Bu tür cihazlar örneğin satış noktası veya yardımcı uygulamalara uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir. Bu yöntem, koşullu erişim gibi özelliklerin kullanılmasına izin vermez. 
- [Toplu kayıt](../windows-bulk-enroll.md) , yetkili bir kullanıcının çok sayıda yeni şirkete ait cihazı Azure Active Directory ve Intune 'a katılılabilmesi için izin verir. Windows yapılandırma Tasarımcısı (WCD) uygulamasıyla bir sağlama paketi oluşturun. Daha sonra, ilk Windows OOBE deneyimi sırasında veya mevcut Windows PC 'den USB medyası kullanarak cihazları Intune 'a otomatik olarak kaydetmek için sağlama paketini yüklersiniz. Bu yöntem Koşullu erişimin kullanılmasına izin vermez. 
- Windows [IoT çekirdek cihazlarını](https://docs.microsoft.com/windows/iot-core/manage-your-device/intunedeviceenrollment) kaydetmek, Windows IoT çekirdek Panosu kullanılarak, cihazı hazırlamak için ve ardından Windows yapılandırma Tasarımcısı kullanılarak bir sağlama paketi oluşturmak için gerçekleştirilir. Ardından, ilk önyükleme sırasında SD kart medyasını kullanarak cihazları Intune 'a otomatik olarak kaydetmek için sağlama paketini yükler.

## <a name="next-steps"></a>Sonraki adımlar

[Windows kayıt yöntemlerinin yeteneklerini öğrenin](enrollment-method-capab.md)
