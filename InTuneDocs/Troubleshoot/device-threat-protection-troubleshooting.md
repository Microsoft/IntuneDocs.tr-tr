---
title: "Lookout Tümleştirmesi Sorunlarını Giderme | Microsoft Docs"
description: "Bu bölüm, Lookout Tümleştirmesinde sıkça meydana gelen sorun giderme konularını açıklar"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: de2f224f203257fe539196557180f0b5da5d8373
ms.lasthandoff: 04/14/2017


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Intune ile Lookout Tümleştirmesi Sorunlarını Giderme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu, Lookout mobil tehdit koruması (MTP) kurulumunuzda karşılaşabileceğiniz bazı yaygın sorunları açıklar.

**Oturum açma hataları**

## <a name="403-errors"></a>403 hataları
[Lookout MTP konsolunda](https://aad.lookout.com) oturum açtığınızda bir 403 hatası görüyorsunuz:  **hizmete erişim yetkiniz yok**  Belirtilen kullanıcı adı Lookout MTP’ye erişim sağlamak için yapılandırılmış Azure Active Directory (AD) grubunun bir üyesi değilse bu durum oluşabilir.

Lookout MTP yalnızca yapılandırılmış Azure AD grubundan kullanıcıların hizmete erişmesine izin verir. Hangi grubun Lookout MTP erişimi olacak şekilde yapılandırıldığını belirlemek için Lookout Desteğine başvurun:

* E-posta: enterprisesupport@lookout.com
* [MTP Konsolunda](http://aad.lookout.com) oturum açıp **Destek** modülüne gidin.
* Şuraya gidin: https://enterprise.support.lookout.com/hc/requests ve bir destek isteğinde bulunun.

## <a name="unable-to-sign-in"></a>Oturum açılamıyor
Azure AD genel yöneticisi ilk Lookout kurulumunu kabul etmediğinde aşağıdaki hatayı görüyorsunuz.

![Lookout oturum açma ekranında oturum açma hatası gösteren ekran görüntüsü](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Bu sorunu çözmek için genel yöneticinin https://aad.lookout.com/les?action=consent adresinde oturum açıp kurulumu başlatma isteğini kabul etmesi gerekir. Daha ayrıntılı bilgi [Lookout MTP aboneliğinizi oluşturma](../deploy-use/set-up-your-subscription-with-lookout-mtp.md) konusunda bulunabilir

**Cihaz durum denetimi**

## <a name="device-missing-from-lookout-device-list"></a>Cihaz Lookout cihaz listesinde yok

Bu aşağıdaki senaryolardan birinde oluşabilir:
* Cihaz **Lookout MTP Konsolunda** belirtilen **Kayıt Grubu**’nda değildir.  [Lookout konsolunda](http://aad.lookout.com), **Sistem** > **Intune Connector** > **Kayıt Yönetimi**’ne gidin.  Kayıt için yapılandırılmış Azure AD gruplarını gözden geçirin ve cihaz kullanıcısının Azure AD gruplarının bir parçası olduğunu doğrulayın.  Kayıt grubuna bir kullanıcı eklendikten sonra, cihazın Lookout MTP Konsolunun **Cihazlar** modülünde görünmesi yapılandırılmış yoklama aralığı (varsayılan süre 5 dakikadır) kadar sürer.
* Cihaz Lookout MTP tarafından desteklemiyorsa.  Desteklenmeyen cihazlar Lookout MTP Konsolundaki bağlayıcı ayarlarının **Yönetilen Cihazlar** bölümünde görünür.

### <a name="device-reported-as-pending"></a>**Beklemede** olarak bildirilen cihaz

Bir cihazın **Beklemede** görünmesi, son kullanıcının Lookout for Work uygulamasını açmadığı ve **Etkinleştir** düğmesine dokunmadığı anlamına gelir. Lookout for Work uygulamasında cihaz etkinleştirme hakkında daha fazla bilgi için bkz. [Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android) veya [iOS cihazınızda Lookout for Work uygulamasını yüklemeniz istendi](https://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-ios)

## <a name="device-whos-active-but-has-no-device-id"></a>Etkin olan ancak cihaz kimliği olmayan cihaz
Lookout MTP konsolunda etkin bir cihazın cihaz kimliği yoksa bu, cihaz kullanıcısının kayıt grubunda olmadığı anlamına gelir. Cihaz kullanıcısı kayıt grubundan çıkarıldıysa veya kayıt grubu kaldırıldıysa bir cihaz bu duruma gelebilir.

[Lookout konsolunda](http://aad.lookout.com), **Sistem** > **Intune Connector** > **Kayıt**’a gidin ve ayarları gözden geçirin.  Azure AD gruplarını gözden geçirin ve cihaz kullanıcısının Azure AD gruplarının bir parçası olduğunu doğrulayın.

Cihaz bu durumda olduğunda, Lookout algılanan her tehdidi kullanıcıya bildirmeye devam eder ancak Intune’a herhangi bir tehdit bilgisi göndermez.

## <a name="device-reported-as-disconnected"></a>**Bağlantısı kesildi** olarak bildirilen cihaz

**Bağlantısı kesildi**, cihazın yapılandırılan aralık içinde (en az 7 gün olacak şekilde varsayılan olarak 30 gün) Lookout MTP ile eşitlenmediği anlamına gelir. Şirket Portalı uygulaması veya Lookout for Work uygulaması cihazda yok. Uygulamaları yeniden yüklemek bu sorunu çözecektir. Kullanıcı Lookout for Work uygulamasını açıp etkinleştirdikten sonra, cihaz Lookout MTP ve Intune ile yeniden eşitlenir.

### <a name="forcing-a-device-sync"></a>Cihaz eşitlemeyi zorlama
Lookout MTP konsolunun **Cihazlar** modülünde, yönetici cihazı seçebilir ve silebilir.   Cihaz sahibi Lookout for Work uygulamasını bir daha açtığında ve **Etkinleştir**’e dokunduğunda, cihaz durumu tam yeniden eşitleme yapar.

## <a name="device-has-a-new-user"></a>Cihazın yeni bir kullanıcısı var
Cihazı tamamen silip, yeni kullanıcıdan kaydolmasını istemelisiniz.  [Intune Yönetici konsolunda](https://manage.microsoft.com) cihazı seçin, sağ tıklayın ve cihazı yönetimden kaldırmak için **Devre Dışı Bırak/Sil**’i seçin. Cihazı devre dışı bıraktıktan sonra silebilirsiniz.

![Intune Yönetici konsolunda devre dışı bırak/sil seçeneği görüntülenen cihaz modülünün ekran görüntüsü](../media/mtp/mtp-retire-device-intune-console.png)

Ayrıca **Lookout konsolunun** [Cihazlar](http://aad.lookout.com) modülüne giderek **Sil**’i seçebilirsiniz.

Yeni kullanıcı bir Lookout MTP kayıt grubundaysa Azure AD cihazı yeni kullanıcıyla ilişkilendirdiği an cihaz görünür.

## <a name="compliance-remediation-workflows"></a>Uyumluluk düzeltmesi iş akışları
- [Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)
- [Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Lookout for Work’ün iOS cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](https://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Ayrıca bkz.
[Lookout MTP ile aboneliğinizi ayarlama](https://docs.microsoft.com/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)

