---
title: Kılavuzlu senaryo-bulutta yönetilen modern masaüstü
titleSuffix: Microsoft Intune
description: Microsoft 365 cihaz yönetim portalından temel bir modern masaüstü kurmak ve yapılandırmak için Kılavuzlu senaryo hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f78f3696827ebd50084f0e4b012c5f94427eeb35
ms.sourcegitcommit: 15e099a9a1e18296580bb345610aee7cc4acd126
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74164574"
---
# <a name="guided-scenario---cloud-managed-modern-desktop"></a>Kılavuzlu senaryo-bulutta yönetilen modern masaüstü

Modern masaüstü, bilgi çalışanı için son teknoloji üretkenlik platformudur. Office 365 ProPlus ve Windows 10, Windows 10 ve Microsoft Defender Gelişmiş tehdit koruması için en son güvenlik temelleriyle birlikte modern masaüstünün temel bileşenleridir. 

Modern masaüstü 'nü buluttan yönetmek, internet genelindeki uzak eylemlerin ek avantajını getirir. Bulut yönetimi, yerleşik Windows mobil cihaz yönetimi ilkelerini kullanır ve yerel Active Directory Grup İlkesi bağımlılıklarını kaldırır. 

Bulutta yönetilen bir modern masaüstünü kendi kuruluşunuzda değerlendirmek istiyorsanız, Bu Kılavuzlu senaryo temel bir dağıtım için gerekli tüm konfigürasyonları önceden tanımlar. Bu Kılavuzlu senaryoda, Intune cihaz yönetimi yeteneklerini deneyebileceğiniz güvenli bir ortam oluşturacaksınız. 

## <a name="prerequisites"></a>Önkoşullar
- [MDM yetkilisini Intune olarak ayarlama](~/fundamentals/mdm-authority-set.md#set-mdm-authority-to-intune) -mobil cihaz YÖNETIMI (MDM) yetkilisi ayarı, cihazlarınızı nasıl yöneteceğinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.
- M365 E3 en düşük (veya en iyi güvenlik için M365 E5)
- Windows 10 1903 cihazı (en iyi Son Kullanıcı deneyimi için Windows Autopilot ile kaydedilir)
- Bu Kılavuzlu senaryoyu gerçekleştirmek için Intune yönetici izinleri gereklidir:
  - Cihaz yapılandırması okuma, oluşturma, silme, atama ve güncelleştirme
  - Kayıt programları cihazı okur, profil okur, profil oluştur, profil ata, profili sil
  - Mobil uygulamalar okuma, oluşturma, silme, atama ve güncelleştirme
  - Kuruluş okuma ve güncelleştirme
  - Güvenlik temelleri okuma, oluşturma, silme, atama ve güncelleştirme
  - İlke ayarları okuma, oluşturma, silme, atama ve güncelleştirme

## <a name="step-1---introduction"></a>1\. adım-giriş

Bu Kılavuzlu senaryoyu kullanarak bir test kullanıcısı ayarlayabilir, bir cihazı Intune 'a kaydedebilir ve Intune tarafından önerilen ayarlarla, ayrıca Windows 10 ve Office ProPlus ile cihazı dağıtabilirsiniz. [Bu korumayı Intune 'da etkinleştirmeyi](~/protect/advanced-threat-protection.md#enable-microsoft-defender-atp-in-intune)seçerseniz cihazınız Microsoft Defender Gelişmiş tehdit koruması için de yapılandırılır. Ayarladığınız Kullanıcı ve Kaydolmakta olduğunuz cihaz yeni bir güvenlik grubuna eklenir ve güvenlik ve üretkenlik için önerilen ayarlarla yapılandırılır. 

### <a name="what-you-will-need-to-continue"></a>Devam etmeniz gerekenler

Bu Kılavuzlu senaryoda test cihazınızı ve test kullanıcısını sağlamanız gerekir. Aşağıdaki görevleri tamamladığınızdan emin olun:
- Azure Active Directory bir test Kullanıcı hesabı ayarlayın.
- Windows 10, sürüm 1903 veya üstünü çalıştıran bir test cihazı oluşturun.
- Seçim [Test cihazını Windows Autopilot 'ye kaydedin](~/enrollment/enrollment-autopilot.md#add-devices).
- Seçim [Kuruluşunuzun Azure Active Directory oturum açma sayfasına marka](https://go.microsoft.com/fwlink/?linkid=2102455)özelliğini etkinleştirin.

## <a name="step-2---user"></a>2\. Adım-Kullanıcı

Cihazda ayarlanacak bir kullanıcı seçin. Bu kişi, cihazın birincil kullanıcısı olacak.

Bu yapılandırmaya daha fazla Kullanıcı veya cihaz eklemek istiyorsanız, Kullanıcı ve cihazları sihirbaz tarafından oluşturulan AAD güvenlik gruplarına eklemeniz yeterlidir. Diğer Kılavuzlu senaryolardan farklı olarak, yapılandırma özelleştirilemez olduğundan Sihirbazı birden çok kez çalıştırmanız gerekmez. Oluşturulan AAD gruplarına daha fazla Kullanıcı ve cihaz eklemeniz yeterlidir. Sihirbazı tamamladıktan sonra, dağıtılan önerilen ilkeler ile oluşturulan grubu görüntüleyebileceksiniz. 

## <a name="step-3---device"></a>3\. adım-cihaz

Cihazınızın Windows 10, sürüm 1903 veya sonraki bir sürümü çalıştırdığından emin olun.  Birincil kullanıcının, aldığı sırada cihazı ayarlaması gerekir. Kullanıcının kullanabileceği iki kurulum seçeneği vardır. 

### <a name="option-a--windows-autopilot"></a>Seçenek A – Windows Autopilot
Windows Autopilot, kullanıcıların bunları BT yardımı olmadan kullanıma hazır hale abilmeleri için yeni cihazların yapılandırmasını otomatikleştirir. Cihazınız zaten Windows Autopilot ile kaydedilmişse, seri numarasına göre seçin. Windows Autopilot kullanma hakkında daha fazla bilgi için bkz. [Windows otomatik pilot ile cihaz kaydetme (Isteğe bağlı)](~/fundamentals/guided-scenarios-cloud-managed-pc.md#register-device-with-windows-autopilot-optional).

### <a name="option-b--manual-device-enrollment"></a>Seçenek B – El Ile cihaz kaydı
Kullanıcılar, mobil cihaz yönetiminde yeni cihazlarını el ile ayarlayıp kaydeder. Bu senaryoyu tamamladıktan sonra, cihazı sıfırlayın ve birincil kullanıcıya Windows cihazları için kayıt yönergeleri verin. Daha fazla bilgi için, [ilk çalıştırma deneyimi sırasında Windows 10 cihazını Azure AD 'ye katma](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device)bölümüne bakın.

## <a name="step-4---review--create"></a>4\. adım-Inceleme ve oluşturma

Son adım, yapılandırdığınız ayarların özetini incelemenizi sağlar. Seçimlerinizi inceledikten sonra, Kılavuzlu senaryoyu gerçekleştirmek için **Dağıt** ' a tıklayın. Kılavuzlu senaryo tamamlandıktan sonra bir kaynak tablosu görüntülenir. Bu kaynakları daha sonra düzenleyebilirsiniz, ancak Özet görünümden ayrıldığınızda tablo kaydedilmez.

> [!IMPORTANT]
> Kılavuzlu senaryo tamamlandıktan sonra bir özet görüntülenir. Özette listelenen kaynakları daha sonra değiştirebilirsiniz, ancak bu kaynağı görüntüleyen tablo kaydedilmez.

### <a name="verification"></a>Doğrulama
1. Seçili olan MDM Kullanıcı kapsamına atandığını doğrulayın
    - [MDM Kullanıcı kapsamının](~/enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) şu olduğundan emin olun:
        - **Microsoft Intune** uygulaması veya için **tümüne** ayarla
        - **Bir**olarak ayarlayın. Ayrıca, Bu Kılavuzlu senaryo tarafından oluşturulan kullanıcı grubunu da ekleyin.
2. Seçili kullanıcının cihazlara Azure Active Directory katılabildiğini doğrulayın.
    - AAD JOIN 'in olduğundan emin olun:
        - **Tümü** veya,
        - **Bir**olarak ayarlayın. Ayrıca, Bu Kılavuzlu senaryo tarafından oluşturulan kullanıcı grubunu da ekleyin.
3. Aşağıdaki temel alınarak Azure AD 'ye katmak için cihazda uygun adımları izleyin:
    - Autopilot. Daha fazla bilgi için bkz. [Windows Autopilot Kullanıcı odaklı mod](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven).
    - Autopilot olmadan: daha fazla bilgi Için, [ilk çalıştırma deneyimi sırasında Windows 10 cihazını Azure AD 'ye ekleme](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device)bölümüne bakın.

### <a name="what-happens-when-i-click-deploy"></a>Dağıt 'ı tıkladığımda ne olur?
Kullanıcı ve cihaz yeni güvenlik gruplarına eklenecektir. Ayrıca, iş veya okul sırasında güvenlik ve üretkenlik için Intune tarafından önerilen ayarlarla de yapılandırılır. Kullanıcı, cihazı Azure AD 'ye katıldıktan sonra cihaza ek uygulamalar ve ayarlar eklenecektir. Bu ek konfigürasyonlar hakkında daha fazla bilgi edinmek için bkz. [hızlı başlangıç: Windows 10 cihazınızı kaydetme](~/enrollment/quickstart-enroll-windows-device.md).

## <a name="additional-information"></a>Ek bilgiler

### <a name="register-device-with-windows-autopilot-optional"></a>Windows Autopilot ile cihaz kaydetme (Isteğe bağlı)

İsteğe bağlı olarak, kayıtlı bir Autopilot cihazı kullanmayı seçebilirsiniz. Autopilot için, Bu Kılavuzlu senaryo bir Autopilot dağıtım profili ve kayıt durumu sayfası profili atayacaktır. Autopilot dağıtım profili aşağıdaki şekilde yapılandırılır:
- Kullanıcı odaklı mod – Yani, son kullanıcının Windows kurulumu sırasında Kullanıcı adı ve parola girmelerini gerektir.
- Azure AD katılımı.
- Windows kurulumunu Özelleştir:
  - Microsoft yazılım lisansı koşulları ekranını gizle
  - Gizlilik ayarlarını gizle 
  - Kullanıcının yerel profilini yerel yönetici ayrıcalıkları olmadan oluşturma
  - Şirket oturum açma sayfasında hesap değiştirme seçeneklerini gizleyin

Kayıt durumu sayfası yalnızca Autopilot cihazları için etkinleştirilecek şekilde yapılandırılacak ve tüm uygulamaların yüklenmesi için beklemeyi engellemez.

Ayrıca, Kılavuzlu senaryo kişiselleştirilmiş bir kurulum deneyimi için kullanıcıyı seçilen Autopilot cihazına de atayacaktır.

#### <a name="post-requisites"></a>Koşul sonrası
Kullanıcı cihazı Azure Active Directory katıldıktan sonra cihaza aşağıdaki yapılandırma uygulanır:
1. Office 365 ProPlus, bulut tarafından yönetilen BILGISAYARA otomatik olarak yüklenir. Erişim, Excel, OneNote, Outlook, PowerPoint, Yayımcı, Skype Kurumsal ve Word dahil olmak üzere, bildiğiniz uygulamaları içerir. Bu uygulamaları, SharePoint Online, Exchange Online ve Skype Kurumsal Çevrimiçi gibi Office 365 hizmetleriyle bağlantı kurmak için kullanabilirsiniz. Office 365 ProPlus, Office 'in abonelik dışı sürümlerinden farklı olarak yeni özelliklerle düzenli olarak güncelleştirilir. Yeni özelliklerin listesi için bkz. Office 365 ' deki yenilikler.
2. Windows güvenlik temelleri, bulut tarafından yönetilen BILGISAYARA yüklenir. Microsoft Defender Gelişmiş tehdit koruması kurulumu yaptıysanız, Kılavuzlu senaryo da Defender için taban çizgisi ayarlarını yapılandırır. Defender Gelişmiş tehdit koruması, Windows 10 güvenlik yığınına yeni bir ihlal sonrası koruma katmanı sağlar. Windows 10 ' da ve güçlü bir bulut hizmetinde yerleşik olarak bulunan istemci teknolojisinin bir birleşimi sayesinde, diğer savunmaları geçmiş tehditleri algılamaya yardımcı olur. 

## <a name="next-steps"></a>Sonraki adımlar

- Microsoft Defender Gelişmiş tehdit algılama kullanıyorsanız, Defender tehdit analizinin uyumluluğu karşılaması için bir [Intune uyumluluk ilkesi](~/protect/advanced-threat-protection.md#create-and-assign-the-compliance-policy) oluşturun.
- Cihaz Intune uyumluluğunu karşılamıyorsa, erişimi engellemek için [cihaz tabanlı bir koşullu erişim ilkesi](~/protect/advanced-threat-protection.md#create-a-conditional-access-policy) oluşturun.
