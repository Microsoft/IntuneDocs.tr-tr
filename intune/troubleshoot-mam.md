---
title: Mobil uygulama yönetimi sorunlarını giderme
titleSuffix: Microsoft Intune
description: Bu konuda, koşullu erişim dağıtımları için bazı sorun giderme ipuçları açıklanır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cf8f7753a92ad45a68f976359560ef6da2d1cec
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/08/2019
ms.locfileid: "67648715"
---
# <a name="troubleshoot-mobile-application-management"></a>Mobil uygulama yönetimi sorunlarını giderme

Bu konu, Intune Uygulama Koruması (MAM ya da mobil uygulama yönetimi olarak da bilinir) kullanırken ortaya çıkan sık karşılaşılan sorunlara çözümler sağlar.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](get-support.md).

## <a name="common-it-administrator-issues"></a>Yaygın BT yöneticisi sorunları

Bunlar BT yöneticisi Intune uygulama koruma ilkelerini kullanırken karşılaşabileceği yaygın sorunlardır.

| Sorun | Açıklama | Çözüm |
| -- | -- | -- |
| İlke, Skype Kurumsal’a uygulanmamış | Azure portalında yapılan cihaz kaydı olmadan uygulama koruma ilkesi, iOS ve Android cihazlardaki Skype Kurumsal uygulaması için uygulanmıyor. | Skype Kurumsal’ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulamasını ayarlamak için lütfen [Modern kimlik doğrulaması için kiracınızı etkinleştirme](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin. |
| Office uygulama ilkesi uygulanmamış | Uygulama koruma ilkeleri, tüm kullanıcılar için hiçbir [desteklenen Office Uygulamasına](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) uygulanmıyor. | Kullanıcının Intune lisansı olduğunu ve Office uygulamalarının dağıtılmış bir uygulama koruma ilkesi tarafından hedeflendiğini doğrulayın. Yeni dağıtılmış bir uygulama koruma ilkesinin uygulanması 8 saate kadar sürebilir. |
| Yönetici, uygulama koruma ilkesini Azure portalında yapılandıramıyor | BT yönetici kullanıcı Azure portalında uygulama koruma ilkelerini yapılandıramıyor. | Aşağıdaki kullanıcı rolleri, Azure portalına erişim vardır: <ul><li>Nda ayarlayabileceğiniz genel yönetici [Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com/)</li><li>Nda ayarlayabileceğiniz sahip [Azure portalında](https://portal.azure.com/).</li><li>Nda ayarlayabileceğiniz katkıda bulunan [Azure portalında](https://portal.azure.com/).</li></ul> Başvurmak [Intune rol tabanlı yönetim denetimi (RBAC)](role-based-access-control.md) bu rolleri ayarlama konusunda yardım için.|
|Uygulama koruma ilkesi raporlarında eksik kullanıcı hesapları var | Yönetim konsolu raporları, uygulama koruma ilkesinin en son dağıtıldığı kullanıcı hesaplarını göstermiyor. | Kullanıcı bir uygulama koruma ilkesiyle henüz hedeflenmişse, bu kullanıcının raporlarda hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir. |
| İlke değişiklikleri çalışmıyor | Uygulama koruma ilkesinde yapılan değişikliklerin ve güncelleştirmelerin uygulanması 8 saate kadar sürebilir. | Mümkünse, son kullanıcı uygulama oturumunu kapatıp hizmetle eşitlemeyi zorlayarak tekrar oturum açabilir. |
| Uygulama koruma ilkesi DEP ile çalışmıyor | Uygulama koruma ilkesi Apple DEP cihazlara uygulanmıyor. | Lütfen Kullanıcı Benzeşimi’ni Apple Aygıt Kayıt Programı (DEP) ile kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında kullanıcı kimlik doğrulaması gerektiren her uygulama için gereklidir. <br><br>Başvurmak [otomatik olarak Apple aygıt kayıt programı ile iOS cihazlarını kaydetme](device-enrollment-program-enroll-ios.md) iOS DEP kaydı hakkında daha fazla bilgi için.|
| Veri aktarım ilkesi iOS ile çalışmıyor | **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** ve **Uygulamanın diğer uygulamalardan veri almasına izin ver** ilkeleri iOS’ta veri aktarımı gerçekleştiremiyor. | Bkz: [Microsoft Intune iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Yaygın son kullanıcı sorunları

Yaygın son kullanıcı sorunları aşağıdaki kategorilere ayrılmıştır:

* **Normal kullanım senaryoları**: Bir son kullanıcı bu senaryoları Intune uygulama koruma ilkesi olan uygulamalara karşılaşabilirsiniz. Bunlar gerçek sorunlar olmamakla birlikte, hata veya arıza olarak algılanabilir.

* **Normal kullanım iletişim kutuları**: Bu bir son kullanıcı, bir Intune uygulama koruma ilkesine sahip uygulamalarda görebilirsiniz kullanım iletişim kutularıdır. Bu iletiler ve iletişim kutuları bir hata veya arıza olduğunu **göstermez**.

* **Hata iletileri ve iletişim kutuları**: Bunlar hata iletileri ve iletişim kutuları bir son kullanıcı Intune uygulama koruma ilkesi olan uygulamalara üzerinde görebilirsiniz. Bunlar, genellikle BT yöneticisi tarafından yapılan bir hatayı veya bir Intune uygulama koruma hatasını belirtir.

### <a name="normal-usage-scenarios"></a>Normal kullanım senaryoları

Platform | Senaryo | Açıklama |
---| --- | --- |
iOS | Son kullanıcı, veri aktarımı ilkesi **Yalnızca yönetilen uygulamalar** veya **Uygulama yok** olarak ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS paylaşım uzantısını kullanabilir. Bu veri sızıntısına neden olmaz mı? | Intune uygulama koruma ilkesi cihazı yönetmiyorsa iOS paylaşım uzantısını denetleyemez. Bu nedenle **Intune, “kurumsal” verileri uygulama dışında paylaşmadan önce şifreler**. Bunu, yönetilen uygulama dışında "kurumsal" dosyayı açmaya çalışarak doğrulayabilirsiniz. Bu dosya şifrelenmiş olmalı ve yönetilen bir uygulama dışında açılamamalıdır.
iOS | Son kullanıcı neden olduğunu **Microsoft Authenticator uygulamasını yüklemeniz isteniyor** | Uygulama tabanlı koşullu erişim uygulandığında bu gereklidir, bkz: [onaylı istemci uygulaması gerektir](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access).
Android | MAM uygulama korumasını cihaz kaydı olmadan kullanıyor olsam bile son kullanıcının neden **Şirket Portalı uygulamasını yüklemesi gerekir**?  | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.
iOS/Android | Uygulama koruma İlkesi Outlook uygulaması e-posta taslağı uygulanmadı | Outlook Kurumsal ve kişisel bağlam desteklediğinden, taslak e-MAM uygulamaz.
iOS/Android | Uygulama koruma İlkesi WXP (Word, Excel, PowerPoint) yeni belgelerinde uygulanmadı | WXP, kurumsal ve kişisel bağlam desteklediğinden, OneDrive gibi bir tanımlanan Kurumsal konumda kaydedilene kadar MAM yeni belgeleri uygulamaz.
iOS/Android | Uygulama ilkesi etkinleştirildiğinde yerel depolamaya Kaydet izin vermiyor | Bu ayar uygulama davranışını uygulama geliştiricisi tarafından denetlenir.
Android | Android "yerel" hangi uygulamaların MAM erişim iOS korumalı içeriği çok daha fazla kısıtlama vardır. | Android açık bir platformdur ve "yerel" uygulama ilişkilendirme olmayabilecek uygulamaları için son kullanıcı tarafından değiştirilebilir. Uygulama [veri aktarım İlkesi özel durumları](app-protection-policies-exception.md) muaf belirli uygulamalar için.
Android | Farklı Kaydet engellendiğinde, azure Information Protection (AIP) PDF olarak kaydedebilir | AIP geliştirir 'Devre dışı bırakma yazdırma' için MAM İlkesi kaydetme PDF olarak kullanıldığında.
iOS | Outlook uygulamasında PDF eklerini açma "eyleme izin verilmiyor ile başarısız oluyor | Kullanıcı Intune için Acrobat okuyucuya doğrulaması yapılmadı ya da parmak izi için kuruluş kimlik doğrulaması için kullanılan bu durum oluşabilir. Acrobat okuyucu önceden açın ve UPN kimlik bilgileri kullanılarak kimlik doğrulaması.


### <a name="normal-usage-dialogs"></a>Normal kullanım iletişim kutuları

Platform | İleti veya iletişim kutusu | Açıklama |
--- | --- | --- |
iOS, Android | **Oturum açma**: Kuruluşunuz, verilerini korumak için bu uygulamayı yönetmesi gerekir. Bu işlemi tamamlamak için iş veya okul hesabınızla oturum açın. | Son kullanıcı uygulama koruma İlkesi gerektirir. Bu uygulamayı kullanmak için kendi iş veya Okul hesabınızla oturum açmanız gerekir. İlkenin uygulanabilmesi sırada kullanıcının Azure Active Directory'de kimlik doğrulaması gerekir.
iOS, Android |**Yeniden başlatma gerekli**: Kuruluşunuz artık bu uygulamadaki verilerini koruyor. Devam etmek için uygulamayı yeniden başlatmanız gerekir. | Uygulama, yalnızca Intune uygulama koruma İlkesi aldı ve ilkenin uygulanabilmesi yeniden başlatmanız gerekir.
iOS, Android |**Eyleme izin verilmiyor**: Kuruluşunuz yalnızca bu uygulamada iş veya Okul verilerini açmak izin verir. | BT yöneticiniz **Uygulamanın diğer uygulamalardan veri almasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, son kullanıcı yalnızca verilerin bu uygulamaya bir uygulama koruma ilkesine sahip diğer uygulamalardan aktarabilir.
iOS, Android |**Eyleme izin verilmiyor**: Kuruluşunuz yalnızca verilerini diğer yönetilen uygulamalara aktarmanıza izin veriyor. | BT yöneticiniz **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, son kullanıcı bir uygulama koruma ilkesine sahip diğer uygulamalara yalnızca bu uygulamadan veri aktarabilir.
iOS, Android |**Uyarı silme**: Kuruluşunuz bu uygulamayla ilişkili verilerini kaldırdı. Devam etmek için uygulamayı yeniden başlatın. | BT yöneticisi Intune uygulama koruması kullanarak bir uygulama silme işlemi başlattı.
Android | **Şirket portalı gerekli**: İş veya Okul hesabınızı bu uygulamayla kullanabilmeniz için Intune Şirket portalı uygulamasını yüklemeniz gerekir. "Mağazaya Git"'a tıklayın. devam etmek için. | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.

### <a name="error-messages-and-dialogs-on-ios"></a>iOS’ta hata iletileri ve iletişim kutuları

Hata iletisi veya iletişim kutusu | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulamayı kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Gerekli uygulama koruma İlkesi uygulama için algılama hatası. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Intune Managed Browser hoşgeldiniz**: Bu uygulama, Microsoft Intune tarafından yönetildiğinde en iyi şekilde çalışır. Bu uygulamayı web'de gezinmek için her zaman kullanabilirsiniz ve uygulama Microsoft Intune tarafından yönetildiğinde ek veri koruma özelliklerine erişiminiz olur. | Intune Managed Browser uygulaması için bir gerekli uygulama koruma İlkesi algılanamadı hatası. <br><br>Kullanıcı web’de gezinmek için uygulamayı kullanmaya devam edebilir ancak uygulama Intune tarafından yönetilmez. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve Intune Managed Browser uygulamasını hedeflediğinden emin olun.
**Başarısız oturum**: Şu anda oturumunuzu açamıyoruz. Lütfen daha sonra tekrar deneyin. | Kullanıcı iş veya okul hesabıyla oturum açmayı denedikten sonra MAM hizmetine kaydedilemiyor. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Hesap ayarlanmadı**: Kuruluşunuz hesabınızı iş veya Okul verilerini ayarlı değil. Yardım için lütfen BT yöneticinizle görüşün. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcı hesabına atanan bir Intune lisansı olduğundan emin olun [Microsoft 365 Yönetim merkezini](https://admin.microsoft.com).
**Cihaz uyumlu**: Jailbreak uygulanmış bir cihaz kullandığınızdan bu uygulama kullanılamıyor. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının jailbreak uygulanmış bir cihaz kullandığını algıladı. | Cihazı fabrika ayarlarına sıfırlayın. Apple destek sitesindeki [bu yönergeleri](https://support.apple.com/HT201274) izleyin.
**Internet bağlantısı gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için Internet'e bağlanması gerekir. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Bilinmeyen hata**: Bu uygulamayı yeniden başlatmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Bilinmeyen bir hata oluştu. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, oluşturun bir [destek bileti](get-support.md#create-an-online-support-ticket) Intune ile.
**Kuruluşunuzun verilerine erişme**: Belirttiğiniz iş veya Okul hesabının bu uygulamaya erişim yok. Farklı bir hesapla oturum açmanız gerekebilir. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının cihaz için MAM kaydı olan hesaptan farklı bir ikinci iş veya okul hesabıyla oturum açmayı denediğini algılar. Cihaz başına aynı anda yalnızca bir iş veya okul hesabı MAM tarafından yönetilebilir. | Kullanıcının, kullanıcı adı oturum açma ekranı tarafından önceden doldurulan hesapla oturum açmasını sağlayın. Gerekebilir [Intune için Kullanıcı UPN ayarını yapılandırma](https://docs.microsoft.com/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). <br> <br> Veya kullanıcının yeni iş veya okul hesabıyla oturum açmasını ve mevcut MAM kaydı olan hesabı kaldırmasını sağlayın.
**Bir bağlantı sorunu**: Beklenmeyen bir bağlantı sorunu oluştu. Bağlantınızı denetleyin ve yeniden deneyin.  |  Beklenmeyen hata. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, oluşturun bir [destek bileti](get-support.md#create-an-online-support-ticket) Intune ile.
**Uyarı**: Bu uygulama artık kullanılabilir. Daha fazla bilgi için BT yöneticinize başvurun. | Uygulamanın sertifikası doğrulanamadı. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.
**Hata**: Bu uygulama bir sorunla karşılaştı ve kapatılması gerekiyor. Bu hata devam ederse lütfen BT yöneticinize başvurun. | Apple iOS Anahtarlığından MAM uygulaması PIN’ini okuma hatası. | Cihazı yeniden başlatın. Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.

### <a name="error-messages-and-dialogs-on-android"></a>Android’de hata iletileri ve iletişim kutuları

İletişim/Hata iletisi | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulamayı kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Gerekli uygulama koruma İlkesi uygulama için algılama hatası. |Kullanıcının güvenlik grubuna bir Android uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Uygulama başlatma başarısız oldu**: Uygulamanız başlatılırken bir sorun oluştu. Uygulamayı ya da Intune Şirket Portalı uygulamasını güncelleştirmeyi deneyin. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin. | Intune uygulama için uygulama koruma ilkesinin geçerli olduğunu algıladı, ancak uygulama MAM başlatılırken kilitleniyor. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Intune Şirket Portalı uygulamasının cihazda yüklü ve güncel olduğundan emin olun. <br><br> Sorun devam ederse, Intune'a günlükleri göndermek için veya oluşturmak için Şirket portalı uygulamasını kullanan bir [destek bileti](get-support.md#create-an-online-support-ticket).
**Uygulama bulunamadı**: Kuruluşunuzun bu içeriği açmasına izin verdiği bu cihazda uygulama vardır. Yardım için BT yöneticinize başvurun. | Kullanıcı iş veya okul hesabını başka bir uygulamayla açmayı denedi ancak Intune verileri açma izni olan başka yönetilen uygulama bulamıyor. | Kullanıcının güvenliğine bir Android uygulama koruma ilkesi dağıtıldığından ve bu ilkenin söz konusu veriyi açabilen en azından başka bir MAM özellikli uygulamayı hedeflediğinden emin olun.
**Başarısız oturum**: Yeniden oturum açmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Kullanıcının oturum açmayı denediği hesabın kimlik doğrulaması başarısız oldu. | Kullanıcının Intune MAM hizmetine zaten kayıtlı bir iş veya okul hesabıyla oturum açtığından emin olun (Bu uygulamada başarıyla oturum açılan ilk iş veya okul hesabı). <br><br> Uygulamanın verilerini temizleyin. <br><br> Uygulama sürümünün güncel olduğundan emin olun. <br><br> Şirket Portalı sürümünün güncel olduğundan emin olun.
**Internet bağlantısı gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için Internet'e bağlanması gerekir. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Cihazı uyumsuz olarak**: Kök erişim izni verilmiş bir cihaz kullandığınızdan bu uygulama kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının kök erişim izni verilmiş bir cihaz kullandığını algılandı. | Cihazı fabrika ayarlarına sıfırlayın.
**Hesap ayarlanmadı**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor, ancak hesabınız ayarlanmış değil. Yardım için BT yöneticinize başvurun. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcı hesabına atanan bir Intune lisansı olduğundan emin olun [Microsoft 365 Yönetim merkezini](https://admin.microsoft.com).
**App kaydedilemiyor**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor, ancak Biz bu uygulama şu anda kaydedilemedi. Yardım için BT yöneticinize başvurun. | Uygulama koruma ilkesi gerekli olduğunda uygulama MAM hizmetine otomatik olarak kaydedilemedi. | Uygulamanın verilerini temizleyin. <br><br> Günlükleri Şirket portalı uygulaması ile Intune'a gönderin veya bir destek bileti çıkartın. Daha fazla bilgi için [Intune için destek alma](get-support.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Mobil uygulama yönetimi kurulumunuzu doğrulama](app-protection-policies-validate.md)
- Intune uygulama koruma İlkesi sorun giderme için bkz: günlük dosyaları kullanmayı öğrenin [https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372)
- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](known-issues.md).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
