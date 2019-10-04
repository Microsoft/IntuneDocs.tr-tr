---
title: Mobil uygulama yönetimi sorunlarını giderme
titleSuffix: Microsoft Intune
description: Bu konuda, koşullu erişim dağıtımları için bazı sorun giderme ipuçları açıklanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a272da470e206279e68077ce80324183c7a8227
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940447"
---
# <a name="troubleshoot-mobile-application-management"></a>Mobil uygulama yönetimi sorunlarını giderme

Bu konu, Intune Uygulama Koruması kullanılırken gerçekleşen yaygın sorunlara çözümler sağlar (Ayrıca MAM veya mobil uygulama yönetimi olarak da adlandırılır).

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md) .

## <a name="common-it-administrator-issues"></a>Yaygın BT yöneticisi sorunları

Bunlar, Intune uygulama koruma ilkelerini kullanırken BT yöneticisinin karşılaşabileceği yaygın sorunlardır.

| Sorun | Açıklama | Çözüm |
| -- | -- | -- |
| İlke Skype Kurumsal 'e uygulanmadı | Azure portal oluşturulan cihaz kaydı olmadan uygulama koruma ilkesi, iOS ve Android cihazlarda Skype Kurumsal uygulamasına uygulanmıyor. | Skype Kurumsal 'ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulaması ayarlamak için lütfen [modern kimlik doğrulaması için kiracınızı etkinleştirme](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin. |
| Office uygulama ilkesi uygulanmadı | Uygulama koruma ilkeleri, herhangi bir kullanıcı için [desteklenen herhangi bir Office uygulamasına](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) uygulanmıyor. | Kullanıcının Intune lisansı olduğunu ve Office uygulamalarının dağıtılmış bir uygulama koruma ilkesi tarafından hedeflendiğini doğrulayın. Yeni dağıtılan bir uygulama koruma ilkesinin uygulanması 8 saate kadar sürebilir. |
| Yönetici, Azure portal 'de uygulama koruma ilkesini yapılandıramıyor | BT Yöneticisi Kullanıcı Azure portal 'de uygulama koruma ilkelerini yapılandıramıyor. | Aşağıdaki kullanıcı rollerinin Azure portal erişimi vardır: <ul><li>[Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com/) 'nde ayarlayabileceğiniz genel yönetici</li><li>[Azure Portal](https://portal.azure.com/)ayarlayabileceğiniz sahip.</li><li>[Azure Portal](https://portal.azure.com/)ayarlayabileceğiniz katkıda bulunan.</li></ul> Bu rolleri ayarlamayla ilgili yardım için [Microsoft Intune Ile rol tabanlı yönetim denetimine (RBAC)](../fundamentals/role-based-access-control.md) bakın.|
|Uygulama koruma ilkesi raporlarında Kullanıcı hesapları eksik | Yönetici Konsolu raporları, uygulama koruma ilkesinin en son dağıtıldığı kullanıcı hesaplarını göstermez. | Bir Kullanıcı bir uygulama koruma ilkesi tarafından yeni hedeflenirse, bu kullanıcının raporlarda hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir. |
| İlke değişiklikleri çalışmıyor | Uygulama koruma ilkesinde yapılan değişikliklerin ve güncelleştirmelerin uygulanması 8 saate kadar sürebilir. | Uygulanabiliyorsa, son kullanıcı uygulama oturumunu kapatıp hizmetle Eşitlemeyi zorlamak için yeniden oturum açabilir. |
| Uygulama koruma ilkesi DEP ile çalışmıyor | Uygulama koruma ilkesi Apple DEP cihazlarına uygulanmıyor. | Lütfen Apple Aygıt Kayıt Programı (DEP) ile Kullanıcı benzeşimi kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında Kullanıcı kimlik doğrulaması gerektiren tüm uygulamalar için gereklidir. <br><br>İOS DEP kaydı hakkında daha fazla bilgi için [iOS cihazlarını Apple 'ın aygıt kayıt programı otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-ios.md) bölümüne bakın.|
| Veri aktarımı ilkesi iOS ile çalışmıyor | **Uygulamanın diğer uygulamalara veri aktarmasına** ve **uygulamanın diğer uygulamalardan veri almasına** Izin ver ilkesi, iOS 'daki veri aktarımını başarıyla yönetemez. | Bkz. [Microsoft Intune iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Yaygın Son Kullanıcı sorunları

Yaygın Son Kullanıcı sorunları aşağıdaki kategorilerde bölünür:

* **Normal kullanım senaryoları**: bir son kullanıcı, Intune uygulama koruma ilkesine sahip uygulamalarda bu senaryolara karşılaşabilir. Bunlar gerçek sorunlar değildir, ancak hata veya hata olarak algılanır.

* **Normal kullanım iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği kullanım iletişim kutulardır. Bu iletiler ve iletişim kutuları bir hata veya **hata göstermez.**

* **Hata iletileri ve iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği hata iletilerdir ve iletişim kutulardır. Bunlar genellikle BT Yöneticisi tarafından bir hata veya Intune uygulama korumasıyla ilgili bir hata olduğunu gösterir.

### <a name="normal-usage-scenarios"></a>Normal kullanım senaryoları

Platform | Senaryo | Açıklama |
---| --- | --- |
iOS | Son Kullanıcı iOS Share uzantısını kullanarak, veri aktarım ilkesi **yalnızca yönetilen uygulamalar** veya **uygulamalar olmadan** ayarlanmış şekilde yönetilmeyen uygulamalarda iş veya okul verilerini açabilir. Bu veri sızıntısı mı? | Intune uygulama koruma ilkesi, cihazı yönetmeksizin iOS Share uzantısını denetlemez. Bu nedenle, **Intune "Kurumsal" verileri uygulama dışından paylaşmadan önce şifreler**. Bunu, "Kurumsal" dosyayı yönetilen uygulamanın dışında açmaya çalışırken doğrulayabilirsiniz. Dosya şifrelenmeli ve yönetilen uygulama dışında açılamaz.
iOS | Son kullanıcıdan **Microsoft Authenticator uygulamasını neden yüklemesi isteniyor** | Bu, uygulama tabanlı koşullu erişim uygulandığında gereklidir, bkz. [onaylanan istemci uygulaması gerektir](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access).
Android | Cihaz kaydı olmadan MAM uygulama korumasını kullanıyorsam bile, son kullanıcının neden **Şirket portalı uygulamayı yüklemesi gerekir**?  | Android 'de uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazda Şirket Portalı uygulamasının yüklü olması gerekir.
iOS/Android | Uygulama koruma ilkesi, Outlook uygulamasında taslak e-postasına uygulanmadı | Outlook hem kurumsal hem de kişisel bağlamı desteklediğinden, taslak e-postada MAM uygulamaz.
iOS/Android | WXP 'de yeni belgelere uygulama koruma ilkesi uygulanmadı (Word, Excel, PowerPoint) | WXP hem kurumsal hem de kişisel bağlamı desteklediğinden, OneDrive gibi tanımlı bir kurumsal konuma kaydedilinceye kadar yeni belgeler üzerinde MAM uygulamaz.
iOS/Android | İlke etkinleştirildiğinde, uygulamalar yerel depolamaya farklı kaydetmeye izin vermiyor | Bu ayar için uygulama davranışı, uygulama geliştiricisi tarafından denetlenir.
Android | Android, "yerel" uygulamaların MAM korumalı içeriğe erişebileceği iOS 'tan daha fazla kısıtlamaya sahiptir | Android açık bir platformdur ve "yerel" uygulama ilişkilendirmesi, son kullanıcı tarafından güvensiz olabilecek uygulamalar ile değiştirilebilir. Belirli uygulamaları muaf tutmak için [veri aktarım ilkesi özel durumları](app-protection-policies-exception.md) uygulayın.
Android | Azure Information Protection (AıP), farklı kaydet engellenmeye karşı PDF olarak kaydedebilir | AıP, PDF olarak kaydet kullanılırken ' yazdırmayı devre dışı bırak ' için MAM ilkesini kullanır.
iOS | Outlook uygulamasında PDF eklerini açmak "eyleme Izin verilmiyor | Bu durum, kullanıcının Intune için Acrobat Reader 'a kimlik doğrulaması yapamadığı veya kuruluşlarında kimlik doğrulaması yapmak için parmak izi kullanmış olması durumunda ortaya çıkabilir. Acrobat Reader 'ı önceden açın ve UPN kimlik bilgilerini kullanarak kimlik doğrulaması yapın.


### <a name="normal-usage-dialogs"></a>Normal kullanım iletişim kutuları

Platform | İleti veya iletişim kutusu | Açıklama |
--- | --- | --- |
iOS, Android | **Oturum açma**: verileri korumak için kuruluşunuzun bu uygulamayı yönetmesi gerekir. Bu eylemi gerçekleştirmek için iş veya okul hesabınızla oturum açın. | Son kullanıcının, uygulama koruma ilkesi gerektiren bu uygulamayı kullanabilmesi için iş veya okul hesabıyla oturum açması gerekir. İlkenin uygulanabilmesi için, kullanıcının Azure Active Directory karşı kimlik doğrulaması gerekir.
iOS, Android |**Yeniden başlatma gerekli**: Kuruluşunuz artık bu uygulamadaki verilerini koruyor. Devam etmek için uygulamayı yeniden başlatmanız gerekir. | Uygulama, bir Intune uygulama koruma ilkesi aldı ve ilkenin uygulanabilmesi için yeniden başlatılması gerekiyor.
iOS, Android |**Eyleme Izin verilmiyor**: kuruluşunuz yalnızca iş veya okul verilerini bu uygulamada açmanıza izin veriyor. | BT Yöneticisi, uygulamanın diğer uygulamalardan **yalnızca yönetilen uygulamalara** **veri almasına izin ver** ' i ayarladı. Bu nedenle, Son Kullanıcı yalnızca uygulama koruma ilkesine sahip diğer uygulamalardan bu uygulamaya veri aktarabilir.
iOS, Android |**Eyleme Izin verilmiyor**: Kuruluşunuz, verilerini yalnızca diğer yönetilen uygulamalara aktarmanızı sağlar. | BT Yöneticisi, uygulamanın **yalnızca yönetilen uygulamalara** **veri aktarmasına izin ver** ' i ayarladı. Bu nedenle, Son Kullanıcı yalnızca bu uygulamadan gelen verileri, uygulama koruma ilkesine sahip diğer uygulamalara aktarabilir.
iOS, Android |**Silme Uyarısı**: Kuruluşunuz bu uygulamayla ilişkili verilerini kaldırdı. Devam etmek için uygulamayı yeniden başlatın. | BT Yöneticisi, Intune uygulama korumasını kullanarak bir uygulama silme işlemi başlattı.
Android | **Gerekli Şirket portalı**: iş veya okul hesabınızı bu uygulamayla kullanmak için Intune şirket portalı uygulamasını yüklemelisiniz. Devam etmek için "mağazaya git" e tıklayın. | Android 'de uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazda Şirket Portalı uygulamasının yüklü olması gerekir.

### <a name="error-messages-and-dialogs-on-ios"></a>İOS üzerinde hata iletileri ve iletişim kutuları

Hata iletisi veya iletişim kutusu | Sebep | Düzeltmesi |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım almak için BT yöneticinize başvurun. | Uygulama için gerekli bir uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Intune Managed Browser hoş geldiniz**: Bu uygulama, Microsoft Intune tarafından yönetildiğinde en iyi şekilde kullanılır. Bu uygulamayı, Web 'de gezinmek için her zaman kullanabilirsiniz ve Microsoft Intune tarafından yönetildiğinde, ek veri koruma özelliklerine erişim elde edersiniz. | Intune Managed Browser uygulaması için gerekli uygulama koruma ilkesi algılanamadı. <br><br>Kullanıcı Web 'e gözatıp uygulamayı kullanmaya devam edebilir, ancak uygulama Intune tarafından yönetilmez. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve Intune Managed Browser uygulamasını hedeflediğinden emin olun.
**Oturum açma başarısız oldu**: Şu anda oturumunuzu açamıyoruz. Lütfen daha sonra yeniden deneyin. | Kullanıcı iş veya okul hesabıyla oturum açmaya çalıştıktan sonra Kullanıcı MAM hizmetine kaydetme hatası. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Hesap ayarlanmadı**: Kuruluşunuz, iş veya okul verilerine erişmek için hesabınızı ayarladı. Yardım için lütfen BT yöneticinize başvurun. | Kullanıcı hesabının Intune 'A doğrudan lisansı yok. | Kullanıcı hesabının [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bir Intune lisansı atanmış olduğundan emin olun.
**Cihaz uyumlu değil**: bir jailbreak uygulanmış cihazı kullandığınız için bu uygulama kullanılamaz. Yardım almak için BT yöneticinize başvurun. | Intune, kullanıcının bir jailbreak uygulanmış cihazında olduğunu algıladı. | Cihazı varsayılan fabrika ayarlarına sıfırlayın. Apple support sitesinde [Bu yönergeleri](https://support.apple.com/HT201274) izleyin.
**Internet bağlantısı gerekli**: Bu uygulamayı kullanbildiğinizi doğrulamak için internet 'e bağlı olmanız gerekir. | Cihaz Internet 'e bağlı değil. | Cihazı bir WiFi veya veri ağına bağlayın.
**Bilinmeyen hata**: Bu uygulamayı yeniden başlatmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Bilinmeyen bir hata oluştu. | Biraz bekleyip yeniden deneyin. Hata devam ederse, Intune ile bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket) oluşturun.
**Kuruluşunuzun verilerine erişme**: belirttiğiniz iş veya okul hesabının bu uygulamaya erişimi yok. Farklı bir hesapla oturum açmanız gerekebilir. Yardım almak için BT yöneticinize başvurun. | Intune, kullanıcının cihaz için MAM kayıtlı hesabından farklı olan ikinci iş veya okul hesabıyla oturum açmayı denediğine algılar. Yalnızca bir iş veya okul hesabı, cihaz başına bir anda MAM tarafından yönetilebilir. | Kullanıcının Kullanıcı adı oturum açma ekranı tarafından önceden doldurulan hesapla oturum açmasını sağlayabilirsiniz. [Intune için Kullanıcı UPN ayarını yapılandırmanız](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm)gerekebilir. <br> <br> Ya da kullanıcının yeni iş veya okul hesabıyla oturum açmasını ve var olan MAM kayıtlı hesabını kaldırmasını sağlayabilirsiniz.
**Bağlantı sorunu**: beklenmeyen bir bağlantı sorunu oluştu. Bağlantınızı denetleyip yeniden deneyin.  |  Beklenmeyen hata. | Biraz bekleyip yeniden deneyin. Hata devam ederse, Intune ile bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket) oluşturun.
**Uyarı**: Bu uygulama artık kullanılamaz. Daha fazla bilgi için BT yöneticinize başvurun. | Uygulamanın sertifikası doğrulanamadı. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.
**Hata**: Bu uygulama bir sorunla karşılaştı ve kapatılması gerekiyor. Bu hata devam ederse, lütfen BT yöneticinize başvurun. | Apple iOS anahtarlığından MAM uygulama PIN 'ini okuma hatası. | Cihazı yeniden başlatın. Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.

### <a name="error-messages-and-dialogs-on-android"></a>Android 'de hata iletileri ve iletişim kutuları

İletişim kutusu/hata iletisi | Sebep | Düzeltmesi |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım almak için BT yöneticinize başvurun. | Uygulama için gerekli bir uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir Android uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Uygulama başlatma başarısız oldu**: uygulamanız başlatılırken bir sorun oluştu. Uygulamayı veya Intune Şirket Portalı uygulamayı güncelleştirmeyi deneyin. Yardıma ihtiyacınız varsa BT yöneticinize başvurun. | Intune, uygulama için geçerli bir uygulama koruma ilkesi algıladı, ancak uygulama MAM başlatma sırasında kilitlenme. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Intune Şirket Portalı uygulamasının cihazda yüklü ve güncel olduğundan emin olun. <br><br> Hata devam ederse, günlükleri Intune 'a göndermek veya bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket)oluşturmak için şirket portalı uygulamasını kullanın.
**Uygulama bulunamadı**: Bu cihazda, kuruluşunuzun bu içeriği açmasına izin verdiği bir uygulama yok. Yardım almak için BT yöneticinize başvurun. | Kullanıcı başka bir uygulamayla iş veya okul verilerini açmaya çalıştı, ancak Intune, verileri açmasına izin verilen başka bir yönetilen uygulamayı bulamıyor. | Kullanıcının güvenliğine bir Android uygulama koruma ilkesi dağıtıldığından ve söz konusu verileri açan en az bir MAM özellikli uygulamayı hedeflediğinden emin olun.
**Oturum açma başarısız**: yeniden oturum açmayı deneyin. Bu sorun devam ederse yardım için BT yöneticinize başvurun. | Kullanıcının oturum açmaya çalıştığı hesabın kimlik doğrulaması başarısız. | Kullanıcının zaten Intune MAM hizmetine kayıtlı olan iş veya okul hesabıyla oturum açtığından emin olun (Bu uygulamada başarıyla oturum açan ilk iş veya okul hesabı). <br><br> Uygulamanın verilerini temizleyin. <br><br> Uygulama sürümünün güncel olduğundan emin olun. <br><br> Şirket Portalı sürümünün güncel olduğundan emin olun.
**İnternet bağlantısı gerekli**: Bu uygulamayı kullanbildiğinizi doğrulamak için internet 'e bağlı olmanız gerekir. | Cihaz Internet 'e bağlı değil. | Cihazı bir WiFi veya veri ağına bağlayın.
**Cihaz uyumlu değil**: Bu uygulama, kökü belirtilmiş bir cihaz kullandığınızdan kullanılamıyor. Yardım almak için BT yöneticinize başvurun. | Intune, kullanıcının kökü belirtilmiş bir cihazda olduğunu algıladı. | Cihazı varsayılan fabrika ayarlarına sıfırlayın.
**Hesap ayarlanmadı**: bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekir, ancak hesabınız ayarlanmamış. Yardım almak için BT yöneticinize başvurun. | Kullanıcı hesabının Intune 'A doğrudan lisansı yok. | Kullanıcı hesabının [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bir Intune lisansı atanmış olduğundan emin olun.
**Uygulama kaydedilemiyor**: bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekir, ancak bu uygulamayı Şu anda kaydedemedik. Yardım almak için BT yöneticinize başvurun. | Uygulama koruma ilkesi gerektiğinde uygulamayı MAM hizmetine otomatik olarak kaydetme başarısız oldu. | Uygulamanın verilerini temizleyin. <br><br> Şirket Portalı uygulama aracılığıyla veya bir destek bileti dosyası aracılığıyla Intune 'a günlük gönderin. Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Mobil uygulama yönetimi kurulumunuzu doğrulama](app-protection-policies-validate.md)
- Intune Uygulama Koruması ilke sorunlarını gidermek için günlük dosyalarını nasıl kullanacağınızı öğrenin, bkz. [https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372)
- Intune sorun giderme hakkında daha fazla bilgi için bkz. [şirketinizde kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](../fundamentals/help-desk-operators.md). 
- Microsoft Intune bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için [Microsoft Intune Içindeki bilinen sorunlar](../known-issues.md)bölümüne bakın.
- Ek Yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).
