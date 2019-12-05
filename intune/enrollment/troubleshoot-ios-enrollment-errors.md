---
title: Microsoft Intune 'de iOS cihaz kaydı sorunlarını giderme
titleSuffix: Microsoft Intune
description: Intune 'A iOS cihazlarını kaydettiğinizde en yaygın sorunlardan bazılarının sorunlarını gidermeye yönelik öneriler.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 46b46cd4a407df686e094198c588371ed4a01bb6
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74832569"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Microsoft Intune 'de iOS cihaz kaydı sorunlarını giderme

Bu makale, Intune yöneticilerinin iOS cihazlarını Intune 'A kaydetme sırasında sorunları anlamalarına ve sorunlarını gidermenize yardımcı olur.

## <a name="prerequisites"></a>Önkoşullar

Sorun gidermeye başlamadan önce bazı temel bilgilerin toplanması önemlidir. Bu bilgiler sorunu daha iyi anlamanıza ve çözüm bulma süresini azaltmanıza yardımcı olabilir.

Sorunla ilgili olarak aşağıdaki bilgileri toplayın:

- Hata iletisinde tam olarak ne yazıyor?
- Hata iletisini nerede görüyorsunuz?
- Sorun ne zaman başladı? Kayıt hiç çalıştı mı?
- Hangi platform (Android, iOS, Windows) soruna sahip?
- Kaç Kullanıcı etkilendi? Tüm kullanıcılar mı etkilendi?
- Kaç cihaz etkilendi? Tüm cihazlar etkileniyor mu ya da yalnızca bir şey var mı?
- MDM yetkilisi nedir? System Center Configuration Manager, Configuration Manager hangi sürümü kullanıyorsunuz?
- Kayıt nasıl gerçekleştirilir? Kayıt profilleriyle "kendi cihazını getir" (BYOD) veya Apple Aygıt Kayıt Programı (DEP) mi?

## <a name="error-messages"></a>Hata iletileri

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>Profil yüklemesi başarısız oldu. Bir ağ hatası oluştu.

**Neden:** Cihazda iOS ile ilgili belirtilmeyen bir sorun var.

#### <a name="resolution"></a>Çözüm

1. Aşağıdaki adımlarda veri kaybını engellemek için (iOS geri yüklendiğinde cihazdaki tüm veriler silinir), verilerinizi yedeklediğinizden emin olun.
2. Cihazı kurtarma moduna alın ve geri yükleyin. Bunu yeni bir cihaz olarak ayarladığınızdan emin olun. İOS cihazlarını geri yükleme hakkında daha fazla bilgi için bkz. [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. Cihazı yeniden kaydedin.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>Profil yüklemesi başarısız oldu. Sunucuyla bağlantı kurulamadı.

**Neden:** Intune kiracınız yalnızca şirkete ait cihazlara izin verecek şekilde yapılandırılmıştır. 

#### <a name="resolution"></a>Çözüm
1. Azure portalında oturum açın.
2. **Diğer hizmetler**' i seçin, Intune ' u arayın ve ardından **Intune**' u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz türü kısıtlamaları**' nın altında, **özellikleri** > ayarlamak istediğiniz kısıtlamayı seçin > **platformları seçin** > **iOS**Için **izin ver** ' i seçin ve ardından **Tamam**' a tıklayın.
5. **Platformları Yapılandır**' ı seçin, kişisel IOS cihazlarına **izin ver** ' i seçin ve ardından **Tamam**' a tıklayın.
6. Cihazı yeniden kaydedin.

**Neden:** DNS 'de gerekli CNAME kayıtları yok.

#### <a name="resolution"></a>Çözüm
Şirketinizin etki alanı için CNAME DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin etki alanı contoso.com ise, DNS 'de EnterpriseEnrollment.contoso.com EnterpriseEnrollment-s.manage.microsoft.com 'e yönlendiren bir CNAME oluşturun.

CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

Birden fazla doğrulanan etki alanı varsa, her etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

|TÜR|Konak adı|Şunu gösterir:|TTL|
|------|------|------|------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com|1 sa|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 sa|

Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

> [!NOTE]
> DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yayılıncaya kadar DNS değişikliğini Intune'da doğrulayamazsınız.

**Neden:** Daha önce farklı bir kullanıcı hesabıyla kaydedilmiş bir cihazı kaydeder ve önceki Kullanıcı Intune 'dan uygun şekilde kaldırılmadı.

#### <a name="resolution"></a>Çözüm
1. Geçerli profil yüklemesini iptal edin.
2. Safari 'de [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) açın.
3. Cihazı yeniden kaydedin.

> [!NOTE]
> Kayıt hala başarısız olursa, Safari 'de tanımlama bilgilerini kaldırın (tanımlama bilgilerini engellemez) ve ardından cihazı yeniden kaydedin.

**Neden:** Cihaz zaten başka bir MDM sağlayıcısına kayıtlı.

#### <a name="resolution"></a>Çözüm
1. İOS cihazında **ayarları** açın, **Genel > cihaz yönetimi**' ne gidin.
2. Var olan tüm yönetim profillerini kaldırın.
3. Cihazı yeniden kaydedin.

**Neden:** Cihazı kaydetmeye çalışan kullanıcının Microsoft Intune lisansı yok.

#### <a name="resolution"></a>Çözüm
1. [Office 365 yönetim merkezine](https://portal.office.com/adminportal/home#/homepage)gidin ve ardından **etkin kullanıcılar > Kullanıcılar**' ı seçin.
2. Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve ardından **düzenle > ürün lisansları**' nı seçin.
3. Bu kullanıcıya atamak istediğiniz lisansın konumunu **Açık** konumuna geçirin ve ardından **Kaydet**' i seçin.
4. Cihazı yeniden kaydedin.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Bu Hizmet desteklenmiyor. Kayıt Ilkesi yok.

**Neden**: Intune 'Da BIR Apple MDM anında iletme sertifikası yapılandırılmamış veya sertifika geçersiz. 

#### <a name="resolution"></a>Çözüm

- MDM anında iletme sertifikası yapılandırılmamışsa, [bir Apple MDM anında iletme sertifikası edinme](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate)bölümündeki adımları izleyin.
- MDM anında iletme sertifikası geçersizse, [Apple MDM anında iletme sertifikasını yenileme](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate)bölümündeki adımları izleyin.

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Şirket Portalı geçici olarak kullanılamıyor. Şirket Portalı uygulama bir sorunla karşılaştı. Sorun devam ederse sistem yöneticinize başvurun.

**Neden:** Şirket Portalı uygulama güncel değil veya bozuk.

#### <a name="resolution"></a>Çözüm
1. Şirket Portalı uygulamayı cihazdan kaldırın.
2. **Microsoft Intune şirket portalı** uygulamasını **App Store**'dan indirin ve yükleyin.
3. Cihazı yeniden kaydedin.
 > [!NOTE]
    > Bu hata, Kullanıcı cihaz kaydı izin verilecek şekilde yapılandırıldığından daha fazla cihaz kaydetmeye çalışıyorsa de oluşabilir. Bu adımlar sorunu gidermezse, aşağıda **ulaşılan cihaz sınırına** yönelik çözüm adımlarını izleyin.

### <a name="device-cap-reached"></a>Cihaz Sınırına Ulaşıldı

**Neden:** Kullanıcı cihaz kayıt sınırından daha fazla cihaz kaydetmeye çalışır.

#### <a name="resolution"></a>Çözüm
1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **cihazlar** > **tüm cihazlar**' ı seçin ve kullanıcının kaydolduğu cihaz sayısını denetleyin.
    > [!NOTE]
    > Ayrıca, etkilenen kullanıcının [Intune kullanıcı portalında](https://portal.manage.microsoft.com/) oturum açmasını ve kaydolmuş cihazları kontrol etmeniz gerekir. Intune [Kullanıcı portalında](https://portal.manage.microsoft.com/) görünen ancak [Intune yönetim portalında](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)yer alan cihazlar olabilir, bu da cihaz kayıt sınırına doğru sayılır.
2. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde **cihazlar** > **kayıt kısıtlamaları** ' nı seçin > cihaz kayıt sınırı ' nı işaretleyin. Varsayılan olarak, sınır 15 olarak ayarlanır. 
3. Kaydedilen cihazların sayısı sınıra ulaştıysa, gereksiz cihazları kaldırın veya cihaz kayıt sınırını artırın. Kayıtlı her cihaz bir Intune lisansı kullandığından, önce gereksiz cihazları her zaman kaldırmanız önerilir.
4. Cihazı yeniden kaydedin.

### <a name="workplace-join-failed"></a>Workplace Join başarısız oldu

**Neden:** Şirket Portalı uygulama güncel değil veya bozuk.  

#### <a name="resolution"></a>Çözüm
1. Şirket Portalı uygulamayı cihazdan kaldırın.
2. **Microsoft Intune şirket portalı** uygulamasını **App Store**'dan indirin ve yükleyin.
3. Cihazı yeniden kaydedin.

### <a name="user-license-type-invalid"></a>Kullanıcı Lisans türü geçersiz

**Neden:** Cihazı kaydetmeye çalışan kullanıcının geçerli bir Intune lisansı yok.

#### <a name="resolution"></a>Çözüm
1. [Microsoft 365 yönetim merkezine](https://portal.office.com/adminportal/home#/homepage)gidin ve ardından **Kullanıcılar** > **etkin kullanıcılar**' ı seçin.
2. Etkilenen Kullanıcı hesabını > **ürün lisansları** > **Düzenle**' yi seçin.
3. Bu kullanıcıya geçerli bir Intune lisansının atandığını doğrulayın.
4. Cihazı yeniden kaydedin.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Kullanıcı adı tanınmıyor. Bu Kullanıcı hesabının Microsoft Intune kullanma yetkisi yok. Bu iletiyi hata halinde aldığınızı düşünüyorsanız, sistem yöneticinize başvurun.

**Neden:** Cihazı kaydetmeye çalışan kullanıcının geçerli bir Intune lisansı yok.

1. [Microsoft 365 yönetim merkezine](https://portal.office.com/adminportal/home#/homepage)gidin ve ardından **Kullanıcılar** > **etkin kullanıcılar**' ı seçin.
2. Etkilenen Kullanıcı hesabını seçin ve ardından **ürün lisansları** > **Düzenle**' yi seçin.
3. Bu kullanıcıya geçerli bir Intune lisansının atandığını doğrulayın.
4. Cihazı yeniden kaydedin.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>Profil yüklemesi başarısız oldu. Yeni MDM yükü eski yük ile eşleşmiyor.

**Neden:** Cihazda bir yönetim profili zaten yüklü.

#### <a name="resolution"></a>Çözüm

1. İOS cihazında **ayarları** , **genel** > **cihaz yönetimi**> açın.
2. Var olan yönetim profiline dokunun ve **yönetimi kaldır**' a dokunun.
3. Cihazı yeniden kaydedin.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Neden:** Apple Anında İletilen Bildirim Servisi (APNs) sertifikası eksik, geçersiz veya zaman aşımına uğradı.

#### <a name="resolution"></a>Çözüm
Intune 'a geçerli bir APNs sertifikası eklendiğini doğrulayın. Daha fazla bilgi için bkz. [iOS ve Mac cihaz yönetimini ayarlama](https://docs.microsoft.com/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune). 

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Neden:** Intune 'da yapılandırılmış Apple Anında Iletilen bildirim hizmeti (APNs) sertifikasıyla ilgili bir sorun var.

#### <a name="resolution"></a>Çözüm
APNs sertifikasını yenileyin ve sonra cihazı yeniden kaydedin.

> [!IMPORTANT]
> APNs sertifikasını yenilediğinizden emin olun. APNs sertifikasını değiştirme. Sertifikayı değiştirirseniz, tüm iOS cihazlarını Intune 'a yeniden kaydetmeniz gerekir. 

- Tek başına Intune 'da APNs sertifikasını yenilemek için bkz. [Apple MDM anında iletme sertifikasını yenileme](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Intune hibrit Configuration Manager ile APNs sertifikasını yenilemek için, bkz. [System Center Configuration Manager ve Microsoft Intune Ile iOS hibrit cihaz yönetimini ayarlama](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac).
- Office 365 ' de APNs sertifikasını yenilemek için bkz. [iOS cihazları Için APNs sertifikası oluşturma](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>XPC_TYPE_ERROR bağlantı geçersiz

Kayıt profili atanan DEP ile yönetilen bir cihazı açtığınızda, kayıt başarısız olur ve aşağıdaki hata iletisini alırsınız:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Neden:** Cihaz ve Apple DEP hizmeti arasında bir bağlantı sorunu var.

#### <a name="resolution"></a>Çözüm
Bağlantı sorununu giderip cihazı kaydetmek için farklı bir ağ bağlantısı kullanın. Sorun devam ederse Apple ile iletişim kurmanız da gerekebilir.


## <a name="other-issues"></a>Diğer sorunlar

### <a name="dep-enrollment-doesnt-start"></a>DEP kaydı başlamıyor
Kayıt profili atanan DEP ile yönetilen bir cihazı açtığınızda, Intune kayıt işlemi başlatılmaz.

**Neden:** Kayıt profili, DEP belirteci Intune 'a yüklenmeden önce oluşturulur.

#### <a name="resolution"></a>Çözüm

1. Kayıt profilini düzenleyin. Profilde herhangi bir değişiklik yapabilirsiniz. Amaç, profilin değiştirilme saatini güncelleştirmedir.
2. DEP ile yönetilen cihazları eşitleme: [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde, > **iOS** > iOS **kaydı** > **kayıt programı belirteçleri** ' ni seçin > bir belirteç > **Şimdi Eşitle**' yi seçin. Apple'a bir eşitleme isteği gönderilir.

### <a name="dep-enrollment-stuck-at-user-login"></a>DEP kaydı kullanıcı oturum açma sırasında takıldı
Kayıt profili atanan DEP ile yönetilen bir cihazı açtığınızda, kimlik bilgilerini girdikten sonra ilk kurulum açılır.

**Neden:** Multi-Factor Authentication (MFA) etkin. Şu anda MFA, DEP cihazlarında kayıt sırasında çalışmaz.

#### <a name="resolution"></a>Çözüm
MFA 'yı devre dışı bırakın ve ardından cihazı yeniden kaydedin.

## <a name="next-steps"></a>Sonraki adımlar

- [Intune’da cihaz kaydı sorunlarını giderme](../troubleshoot-device-enrollment-in-intune.md)
- [Intune forumundan soru sorun](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Microsoft Intune destek ekibi blogunu denetleyin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Microsoft Enterprise Mobility ve Security blogunu denetleyin](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
