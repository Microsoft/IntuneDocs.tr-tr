---
title: "Lookout Tümleştirmesi Sorunlarını Giderme | Microsoft Docs"
description: "Bu bölüm, Lookout Tümleştirmesinde sıkça meydana gelen sorun giderme konularını açıklar"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 416f200bdb72bae98897cb8d279dbdb767757da9


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Intune ile Lookout Tümleştirmesi Sorunlarını Giderme
Bu konu, Lookout mobil tehdit koruması (MTP) kurulumunuzda karşılaşabileceğiniz bazı yaygın sorunları açıklar.
## <a name="troubleshoot-login-errors"></a>Oturum açma sorunlarını giderme
### <a name="403-errors"></a>403 hataları
[Lookout MTP konsolunda](https://aad.lookout.com) oturum açtığınızda bir 403 hatası görebilirsiniz:  **hizmete erişim yetkiniz yok**  Girdiğiniz kullanıcı adı Lookout MTP’ye erişim sağlamak için yapılandırılmış Azure Active Directory (Azure AD) grubunun bir üyesi değilse bu durum oluşabilir.

Lookout MTP yalnızca, erişim sağlamak için yapılandırılmış bir Azure AD grubundan kullanıcılara izin verecek şekilde yapılandırılır. Hangi grubun Lookout MTP erişimi olacak şekilde yapılandırıldığından emin değilseniz, Lookout Desteğine başvurun.

Lookout Desteği ile aşağıdaki şekillerde irtibat kurabilirsiniz:

* E-posta: enterprisesupport@lookout.com
* [MTP Konsolunda](http://aad.lookout.com) oturum açıp **Destek** modülüne gidin.
* Şuraya gidin: https://enterprise.support.lookout.com/hc/en-us/requests ve bir destek isteğinde bulunun.

### <a name="unable-to-sign-in"></a>Oturum açılamıyor
Azure AD genel yöneticisi ilk Lookout kurulumunu kabul etmediğinde aşağıdaki hatayı görebilirsiniz.

![Lookout oturum açma ekranında oturum açma hatası gösteren ekran görüntüsü](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Bu sorunu çözmek için genel yöneticinin https://aad.lookout.com/les?action=consent adresinde oturum açıp kurulumu başlatma isteğini kabul etmesi gerekir. Daha ayrıntılı bilgi [Lookout MTP aboneliğinizi oluşturma](../deploy-use/set-up-your-subscription-with-lookout-mtp.md) konusunda bulunabilir

## <a name="troubleshoot-device-status-issues"></a>Cihaz durumu sorunlarını giderme

### <a name="device-not-showing-up-in-the-lookout-mtp-console-device-list"></a>Cihaz Lookout MTP konsolu cihaz listesinde gösterilmiyor

Bu aşağıdaki senaryolardan birinde oluşabilir:
* Bu cihazın sahibi olan kullanıcı **Lookout MTP Konsolunda** belirtilen **Kayıt Grubu**’nda değildir.  **Sistem** modülünde, **Intune Bağlayıcısı** sekmesine gidin ve **Kayıt Yönetimi** ayarlarına bakın.  Kayıt için yapılandırılmış bir veya daha fazla Azure AD grubu görmeniz gerekir.  Eksik cihazın sahibi olan kullanıcının belirlenen Azure AD gruplarından birinin üyesi olduğunu doğrulayın.  Kayıt grubuna yeni bir kullanıcı eklendikten sonra, cihazın Lookout MTP Konsolunun **Cihazlar** modülünde gösterilmesi yapılandırılmış yoklama aralığı (varsayılan süre 5 dakikadır) kadar sürer.

* Cihaz Lookout MTP tarafından desteklemiyorsa.  Desteklenmeyen cihazlar Lookout MTP Konsolundaki bağlayıcı ayarlarının **Yönetilen Cihazlar** bölümünde görünür.

### <a name="device-continues-to-be-reported-as-pending"></a>Cihaz **beklemede** olarak bildirilmeye devam ediyor

Bir cihazın **Beklemede** görünmesi, son kullanıcının Lookout for Work uygulamasını açmadığı ve **Etkinleştir** düğmesine dokunmadığı anlamına gelir. Lookout for Work uygulamasında cihaz etkinleştirme hakkında daha fazla bilgi için aşağıdaki konuyu okuyun:

[Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### <a name="in-the-lookout-mtp-console-a-device-is-showing-as-active-but-does-not-have-a-device-id"></a>Lookout MTP konsolunda, bir cihaz etkin olarak görünüyor ancak cihaz kimliğine sahip değil.  
Bu, cihazın sahibi olan kullanıcının Lookout MTP Konsolunda belirtilen Kayıt Grubu’nda olmadığı anlamına gelir.   Cihazın sahibi olan kullanıcı kayıt grubundan çıkarıldıysa veya kullanıcının dahil olduğu kayıt grubu kaldırıldıysa cihaz bu duruma gelebilir.

Lookout MTP konsolunun **Sistem** modülünde **Intune Bağlayıcısı** sekmesine giderek **Kayıt** ayarlarını gözden geçirin.  Kayıt için yapılandırılmış bir veya daha fazla Azure AD grubu görmeniz gerekir.  Cihazın sahibi olan kullanıcının belirtilen Azure AD gruplarından birinin üyesi olduğunu doğrulayın.  

Cihaz bu durumda olduğunda, Lookout algılanan her tehdidi kullanıcıya bildirmeye devam eder ancak Intune’a herhangi bir tehdit bilgisi göndermez.

### <a name="device-shows-disconnected-state"></a>Cihaz durumu bağlantı kesildi olarak görünüyor

Bağlantı kesildi durumu, Lookout MTP’nin önceden yapılandırılmış zaman aralığı içinde cihazdan sinyal alamadığı anlamına gelir (varsayılan değer en az 7 gün olacak şekilde 30 gündür). Bu, Şirket portalı ya da Lookout for Work uygulamasının cihazda yüklenmediği veya cihazdan kaldırıldığı anlamına gelir. Uygulamaları yeniden yüklemek bu sorunu çözecektir. Kullanıcı Lookout for Work uygulamasını açıp etkinleştirdikten sonra, cihaz Lookout MTP ve Intune ile yeniden eşitlenir.    

### <a name="forcing-a-resync-on-the-device"></a>Cihazda yeniden eşitleme işlemini zorlama
Lookout MTP konsolunun **Cihazlar** modülünde, yönetici cihazı seçebilir ve silebilir.   Cihaz sahibi Lookout for Work uygulamasını bir daha açtığında ve **Etkinleştir**’e dokunduğunda, cihaz durumu tam yeniden eşitleme yapar.

### <a name="the-owner-of-the-device-is-no-longer-using-this-device"></a>Cihaz sahibi artık bu cihazı kullanmıyor
Cihazı tamamen silip, yeni kullanıcıdan kaydolmasını istemeniz gerekir.  [Intune Yönetici konsolunda](https://manage.microsoft.com) cihazı seçin, sağ tıklayın ve cihazı yönetimden kaldırmak için **Devre Dışı Bırak/Sil**’i seçin. Cihazı devre dışı bıraktıktan sonra silebilirsiniz.

![Intune Yönetici konsolunda devre dışı bırak/sil seçeneği görüntülenen cihaz modülünün ekran görüntüsü](../media/mtp/mtp-retire-device-intune-console.png)

Ayrıca Lookout MTP Konsolunun **Cihazlar** modülüne giderek **Sil**’i seçebilirsiniz.  

Yeni kullanıcı Lookout MTP konsolunda belirtilen kayıt gruplarından birine dahil olduğu sürece, Azure AD cihazı yeni kullanıcıyla ilişkilendirdikten sonra cihaz görünür.

## <a name="compliance-remediation-workflows"></a>Uyumluluk düzeltmesi iş akışları
[Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### <a name="see-also"></a>Ayrıca bkz.
[Lookout MTP ile aboneliğinizi ayarlama](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Dec16_HO2-->


