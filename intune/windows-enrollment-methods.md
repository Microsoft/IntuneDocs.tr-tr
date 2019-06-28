---
title: Windows cihazlar için Intune kayıt yöntemleri
titleSuffix: Microsoft Intune
description: Intune'da Windows cihazları kaydedebilmeniz için farklı yollarını öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: 91df913c6daa5cad5f004cff7e448e8a34d63925
ms.sourcegitcommit: 690e680e854b7d707421c5e06f134e493f4f4194
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67416872"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Windows cihazlar için Intune kayıt yöntemleri

Intune'da cihazları yönetmek için cihazları Intune hizmetine ilk kaydedilmesi gerekir. Hem de kişisel ve şirkete ait cihazları Intune yönetimi için kaydedilebilir. 

Intune'a kayıtlı cihazlar almanın iki yolu vardır:
- Kullanıcılar, Windows bilgisayarlarını kendileri kaydedebilir 
- Yöneticiler, herhangi bir kullanıcı katılımı olmadan otomatik kayıt zorlamak için ilkeleri yapılandırabilir

## <a name="user-self-enrollment-in-intune"></a>Intune kullanıcı Self Servis kayıt

Kullanıcılar Windows cihazlarını bu yöntemlerden birini kullanarak kendileri kaydedebilir:

- [Kendi cihazını getir (KCG)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): Kullanıcıları cihazlarını, kişilere ait bağlanmak seçerek bir **iş ve Okul** öğesinden hesap **ayarları** cihaz. Bu işlem:
    - E-posta gibi şirket kaynağı erişim kazanmak için Azure Active Directory ile cihazı kaydeder.
    - Cihazınızı ıntune'a kişisel şirkete ait cihaz (KCG) kaydeder.
Yönetici (Azure AD premium abonelikleri ile kullanılabilir) otomatik kayıt yapılandırdıysa, kullanıcının yalnızca kendi kimlik bilgilerini bir kere girmeniz gerekir. Aksi halde, bunlar ayrı olarak yalnızca MDM kaydı kaydetmek ve kimlik bilgilerini girmek gerekir.  
- **Yalnızca MDM kaydı** sağlayan kullanıcıları kaydetmek mevcut bir çalışma, Active Directory veya Azure Active Directory'ye katılmış bilgisayarı Intune'a. Kullanıcıların, var olan Windows PC Ayarları'ndan kaydedin. Bu yöntem, cihazın Azure Active Directory'ye kaydetmediği önerilmez. Ayrıca, koşullu erişim gibi özelliklerinin kullanımını engeller.
- [Azure Active Directory (Azure AD) birleştirme](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) – cihazın Azure Active Directory'ye katılır ve Windows için kendi Azure AD kimlik bilgileriyle oturum açmalarını sağlar. Otomatik kayıt etkinse, cihaz Intune'da otomatik olarak kaydedilir. Otomatik kayıt avantajı, kullanıcı için tek adımlı bir işlemdir. Aksi halde, bunlar ayrı olarak yalnızca MDM kaydı kaydetmek ve kimlik bilgilerini girmek gerekir. İlk Windows OOBE sırasında veya ayarları, kullanıcıların bu yolla kayıt. Cihaz, ıntune şirket şirkete ait cihaz olarak işaretlenir.
- [AutoPilot](enrollment-autopilot.md) - Azure AD Join otomatikleştirir ve yeni şirkete ait cihazları Intune'a kaydeder. Bu yöntem,-deneyimini basitleştirir ve özel işletim sistemi görüntülerini cihazları üzerine uygulamak için ihtiyacını ortadan kaldırır. Yöneticileri, Autopilot cihazları yönetmek için Intune kullandığınızda, kaydolduktan sonra ilkeler, profiller, uygulamalar ve yönetebilirsiniz.  Autopilot dağıtım dört tür vardır: [Kendi kendine modu dağıtımı](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (bilgi noktaları, dijital Tabela veya için paylaşılan cihazlar), [kullanıcı temelli modu](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (Geleneksel, kullanıcılar için) [beyaz Eldiven] (https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/white-glove) iş ortakları veya BT personeliniz bu nedenle bir Windows 10 bilgisayarı ön sağlamasını yapma sağlar, BT tam olarak yapılandırılmış ve çalışma ortamına hazır durumda ve [var olan cihazlar için Autopilot] (https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/existing-devices) , Windows 10 'un en son sürümü mevcut cihazlarınızı kolayca dağıtmanızı sağlar.

## <a name="administrator-based-enrollment-in-intune"></a>Intune yönetici tabanlı kayıt

Yöneticiler, kullanıcı etkileşimi gerektiren aşağıdaki yöntemlerini kayıt ayarlayabilirsiniz:

- [Hibrit Azure AD'ye katılımı](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) yöneticilerin Active Directory Grup İlkesi'hibrit Azure AD'ye katılmış cihazlar otomatik olarak kaydetmek için yapılandırma sağlar. 
- [Configuration Manager ikincil Yönetimi](https://docs.microsoft.com/sccm/comanage/overview) mevcut Configuration Manager ile yönetilen cihazlarını Intune ile Configuration Manager'ın çift avantajlarından yararlanabilmek için ıntune'a yöneticilerin sağlar. 
- [Cihaz kayıt Yöneticisi](device-enrollment-manager-enroll.md) (DEM), bir özel hizmet hesabıdır. DEM hesapları, şirkete ait birden çok cihazı kaydetmek ve yönetmek, yetkili kullanıcıların izinlere sahip. Bu tür cihazlar örneğin satış noktası veya yardımcı uygulamalara uygundur ancak e-postaya veya şirket kaynaklarına erişmesi gereken kullanıcılar için uygun değildir. Bu yöntem, koşullu erişim gibi özellikleri izin vermez. 
- [Toplu kayıt](windows-bulk-enroll.md) yetkili bir kullanıcı Azure Active Directory ve Intune'a yeni cihazları şirkete ait çok sayıda katılmasını sağlar. Windows yapılandırma Tasarımcısı (WCD) uygulaması ile bir sağlama paketi oluşturun. Ardından, USB kullanarak ilk Windows OOBE sırasında medya deneyimi veya var olan Windows Bilgisayardan, otomatik olarak cihazlarını Intune'a kaydetmeleri için sağlama paketi yükleyin. Bu yöntem koşullu erişim kullanılmasına izin vermez. 
- [Windows IOT Core cihazları kaydetmenin](https://docs.microsoft.com/en-us/windows/iot-core/manage-your-device/intunedeviceenrollment) panoyu Windows IOT Core cihazı hazırlamak için kullanarak ve ardından bir sağlama paketi oluşturmak için Windows yapılandırma Tasarımcısı kullanarak gerçekleştirilir. Ardından, ilk önyükleme sırasında SD kart medya kullanarak, onu otomatik olarak cihazlarını Intune'a kaydetmeleri için sağlama paketi yükler.

## <a name="next-steps"></a>Sonraki adımlar

[Windows kayıt yöntemleri özelliklerini öğrenin](enrollment-method-capab.md)
