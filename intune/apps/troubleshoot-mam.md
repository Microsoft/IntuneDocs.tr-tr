---
title: Mobil uygulama yönetimi sorunlarını giderme
titleSuffix: Microsoft Intune
description: Bu konuda, koşullu erişim dağıtımları için bazı sorun giderme ipuçları açıklanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 49bf59805476ebbcce3148738e40bfd11e4744eb
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839323"
---
# <a name="troubleshoot-mobile-application-management"></a>Mobil uygulama yönetimi sorunlarını giderme

Bu konu, Intune Uygulama Koruması kullanılırken gerçekleşen yaygın sorunlara çözümler sağlar (Ayrıca MAM veya mobil uygulama yönetimi olarak da adlandırılır).

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).

## <a name="common-it-administrator-issues"></a>Yaygın BT yöneticisi sorunları

Bunlar, Intune uygulama koruma ilkelerini kullanırken BT yöneticisinin karşılaşabileceği yaygın sorunlardır.

| Sorun | Description | Çözüm |
| -- | -- | -- |
| İlke, Skype Kurumsal’a uygulanmamış | Azure portalında yapılan cihaz kaydı olmadan uygulama koruma ilkesi, iOS ve Android cihazlardaki Skype Kurumsal uygulaması için uygulanmıyor. | Skype Kurumsal’ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulamasını ayarlamak için lütfen [Modern kimlik doğrulaması için kiracınızı etkinleştirme](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin. |
| Office uygulama ilkesi uygulanmamış | Uygulama koruma ilkeleri, tüm kullanıcılar için hiçbir [desteklenen Office Uygulamasına](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) uygulanmıyor. | Kullanıcının Intune lisansı olduğunu ve Office uygulamalarının dağıtılmış bir uygulama koruma ilkesi tarafından hedeflendiğini doğrulayın. Yeni dağıtılmış bir uygulama koruma ilkesinin uygulanması 8 saate kadar sürebilir. |
| Yönetici, uygulama koruma ilkesini Azure portalında yapılandıramıyor | BT Yöneticisi Kullanıcı Azure portal 'de uygulama koruma ilkelerini yapılandıramıyor. | Aşağıdaki kullanıcı rollerinin Azure portal erişimi vardır: <ul><li>[Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com/) 'nde ayarlayabileceğiniz genel yönetici</li><li>[Azure Portal](https://portal.azure.com/)ayarlayabileceğiniz sahip.</li><li>[Azure Portal](https://portal.azure.com/)ayarlayabileceğiniz katkıda bulunan.</li></ul> Bu rolleri ayarlamayla ilgili yardım için [Microsoft Intune Ile rol tabanlı yönetim denetimine (RBAC)](../fundamentals/role-based-access-control.md) bakın.|
|Uygulama koruma ilkesi raporlarında eksik kullanıcı hesapları var | Yönetim konsolu raporları, uygulama koruma ilkesinin en son dağıtıldığı kullanıcı hesaplarını göstermiyor. | Kullanıcı bir uygulama koruma ilkesiyle henüz hedeflenmişse, bu kullanıcının raporlarda hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir. |
| İlke değişiklikleri çalışmıyor | Uygulama koruma ilkesinde yapılan değişikliklerin ve güncelleştirmelerin uygulanması 8 saate kadar sürebilir. | Mümkünse, son kullanıcı uygulama oturumunu kapatıp hizmetle eşitlemeyi zorlayarak tekrar oturum açabilir. |
| Uygulama koruma ilkesi DEP ile çalışmıyor | Uygulama koruma ilkesi Apple DEP cihazlara uygulanmıyor. | Lütfen Kullanıcı Benzeşimi’ni Apple Aygıt Kayıt Programı (DEP) ile kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında kullanıcı kimlik doğrulaması gerektiren her uygulama için gereklidir. <br><br>İOS DEP kaydı hakkında daha fazla bilgi için [iOS cihazlarını Apple 'ın aygıt kayıt programı otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-ios.md) bölümüne bakın.|
| Veri aktarım ilkesi iOS ile çalışmıyor | **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** ve **Uygulamanın diğer uygulamalardan veri almasına izin ver** ilkeleri iOS’ta veri aktarımı gerçekleştiremiyor. | Bkz. [Microsoft Intune iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Yaygın son kullanıcı sorunları

Yaygın son kullanıcı sorunları aşağıdaki kategorilere ayrılmıştır:

* **Normal kullanım senaryoları**: bir son kullanıcı, Intune uygulama koruma ilkesine sahip uygulamalarda bu senaryolara karşılaşabilir. Bunlar gerçek sorunlar olmamakla birlikte, hata veya arıza olarak algılanabilir.

* **Normal kullanım iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği kullanım iletişim kutulardır. Bu iletiler ve iletişim kutuları bir hata veya arıza olduğunu **göstermez**.

* **Hata iletileri ve iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği hata iletilerdir ve iletişim kutulardır. Bunlar, genellikle BT yöneticisi tarafından yapılan bir hatayı veya bir Intune uygulama koruma hatasını belirtir.

### <a name="normal-usage-scenarios"></a>Normal kullanım senaryoları

Platfveyam | Senaryo | Açıklama |
---| --- | --- |
iOS | Son kullanıcı, veri aktarımı ilkesi **Yalnızca yönetilen uygulamalar** veya **Uygulama yok** olarak ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS paylaşım uzantısını kullanabilir. Bu veri sızıntısına neden olmaz mı? | Intune uygulama koruma ilkesi, cihaz yönetilmeden iOS paylaşım uzantısını denetleyemez. Bu nedenle **Intune, “kurumsal” verileri uygulama dışında paylaşmadan önce şifreler**. Bunu, yönetilen uygulama dışında "kurumsal" dosyayı açmaya çalışarak doğrulayabilirsiniz. Bu dosya şifrelenmiş olmalı ve yönetilen bir uygulama dışında açılamamalıdır.
iOS | Son kullanıcıdan **Microsoft Authenticator uygulamasını neden yüklemesi isteniyor** | Bu, uygulama tabanlı koşullu erişim uygulandığında gereklidir, bkz. [onaylanan istemci uygulaması gerektir](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access).
Android | MAM uygulama korumasını cihaz kaydı olmadan kullanıyor olsam bile son kullanıcının neden **Şirket Portalı uygulamasını yüklemesi gerekir**?  | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.
iOS/Android | Uygulama koruma ilkesi, Outlook uygulamasında taslak e-postasına uygulanmadı | Outlook hem kurumsal hem de kişisel bağlamı desteklediğinden, taslak e-postada MAM uygulamaz.
iOS/Android | WXP 'de yeni belgelere uygulama koruma ilkesi uygulanmadı (Word, Excel, PowerPoint) | WXP hem kurumsal hem de kişisel bağlamı desteklediğinden, OneDrive gibi tanımlı bir kurumsal konuma kaydedilinceye kadar yeni belgeler üzerinde MAM uygulamaz.
iOS/Android | İlke etkinleştirildiğinde, uygulamalar yerel depolamaya farklı kaydetmeye izin vermiyor | Bu ayar için uygulama davranışı, uygulama geliştiricisi tarafından denetlenir.
Android | Android, "yerel" uygulamaların MAM korumalı içeriğe erişebileceği iOS 'tan daha fazla kısıtlamaya sahiptir | Android açık bir platformdur ve "yerel" uygulama ilişkilendirmesi, son kullanıcı tarafından güvensiz olabilecek uygulamalar ile değiştirilebilir. Belirli uygulamaları muaf tutmak için [veri aktarım ilkesi özel durumları](app-protection-policies-exception.md) uygulayın.
Android | Azure Information Protection (AıP), farklı kaydet engellenmeye karşı PDF olarak kaydedebilir | AıP, PDF olarak kaydet kullanılırken ' yazdırmayı devre dışı bırak ' için MAM ilkesini kullanır.
iOS | Outlook uygulamasında PDF eklerini açmak "eyleme Izin verilmiyor | Bu durum, kullanıcının Intune için Acrobat Reader 'a kimlik doğrulaması yapamadığı veya kuruluşlarında kimlik doğrulaması yapmak için parmak izi kullanmış olması durumunda ortaya çıkabilir. Acrobat Reader 'ı önceden açın ve UPN kimlik bilgilerini kullanarak kimlik doğrulaması yapın.


### <a name="normal-usage-dialogs"></a>Normal kullanım iletişim kutuları

Platfveyam | İleti veya iletişim kutusu | Açıklama |
--- | --- | --- |
iOS, Android | **Oturum açma**: Kuruluşunuzun, verilerini korumak için bu uygulamayı yönetmesi gerekir. Bu işlemi tamamlamak için iş veya okul hesabınızla oturum açın. | Son kullanıcının, uygulama koruma ilkesi gerektiren bu uygulamayı kullanabilmesi için iş veya okul hesabıyla oturum açması gerekir. İlkenin uygulanabilmesi için, kullanıcının Azure Active Directory karşı kimlik doğrulaması gerekir.
iOS, Android |**Yeniden Başlatma Gerekli**: Kuruluşunuz artık verilerini bu uygulama içinde koruyor. Devam etmek için uygulamayı yeniden başlatmanız gerekir. | Uygulama, bir Intune uygulama koruma ilkesi aldı ve ilkenin uygulanabilmesi için yeniden başlatılması gerekiyor.
iOS, Android |**Eyleme İzin Verilmiyor**: Kuruluşunuz bu uygulamada yalnızca iş veya okul verilerinizi açmanıza izin veriyor. | BT yöneticiniz **Uygulamanın diğer uygulamalardan veri almasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, Son Kullanıcı yalnızca uygulama koruma ilkesine sahip diğer uygulamalardan bu uygulamaya veri aktarabilir.
iOS, Android |**Eyleme İzin Verilmiyor**: Kuruluşunuz verilerini yalnızca diğer yönetilen uygulamalara aktarmanıza izin veriyor. | BT yöneticiniz **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, Son Kullanıcı yalnızca bu uygulamadan gelen verileri, uygulama koruma ilkesine sahip diğer uygulamalara aktarabilir.
iOS, Android |**Silme Alarmı**: Kuruluşunuz bu uygulama ile ilişkili verilerini kaldırdı. Devam etmek için uygulamayı yeniden başlatın. | BT yöneticisi Intune uygulama koruması kullanarak bir uygulama silme işlemi başlattı.
Android | **Şirket Portalı gerekli**: İş veya okul hesabınızı bu uygulamayla kullanabilmeniz için Intune Şirket Portalı uygulamasını yüklemeniz gerekir. Devam etmek için "mağazaya git" e tıklayın. | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.

### <a name="error-messages-and-dialogs-on-ios"></a>iOS’ta hata iletileri ve iletişim kutuları

Hata iletisi veya iletişim kutusu | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama Ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli bir uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Intune Managed Browser'a Hoş Geldiniz**: Bu uygulama, Microsoft Intune tarafından yönetildiğinde en iyi şekilde çalışır. Bu uygulamayı web'de gezinmek için her zaman kullanabilirsiniz ve uygulama Microsoft Intune tarafından yönetildiğinde ek veri koruma özelliklerine erişiminiz olur. | Intune Managed Browser uygulaması için gerekli uygulama koruma ilkesi algılanamadı. <br><br>Kullanıcı web’de gezinmek için uygulamayı kullanmaya devam edebilir ancak uygulama Intune tarafından yönetilmez. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve Intune Managed Browser uygulamasını hedeflediğinden emin olun.
**Oturum Açma Başarısız**: Şu an oturumunuzu açamıyoruz. Lütfen daha sonra tekrar deneyin. | Kullanıcı iş veya okul hesabıyla oturum açmayı denedikten sonra MAM hizmetine kaydedilemiyor. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Hesap Ayarlanmadı**: Kuruluşunuz hesabınızı iş veya okul verilerine erişecek şekilde ayarlamadı. Yardım için lütfen BT yöneticinizle görüşün. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcı hesabının [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bir Intune lisansı atanmış olduğundan emin olun.
**Cihaz Uyumlu Değil**: Bu uygulama, cihazınıza jailbreak uygulandığı içi kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının jailbreak uygulanmış bir cihaz kullandığını algıladı. | Cihazı fabrika ayarlarına sıfırlayın. Apple destek sitesindeki [bu yönergeleri](https://support.apple.com/HT201274) izleyin.
**İnternet Bağlantısı Gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Bilinmeyen Hata**: Bu uygulamayı yeniden başlatmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Bilinmeyen bir hata oluştu. | Bir süre bekleyin ve yeniden deneyin. Hata devam ederse, Intune ile bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket) oluşturun.
**Kuruluşunuzun Verilerine Erişme**: Belirttiğiniz iş veya okul hesabının bu uygulamaya erişimi yok. Farklı bir hesapla oturum açmanız gerekebilir. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının cihaz için MAM kaydı olan hesaptan farklı bir ikinci iş veya okul hesabıyla oturum açmayı denediğini algılar. Cihaz başına aynı anda yalnızca bir iş veya okul hesabı MAM tarafından yönetilebilir. | Kullanıcının, kullanıcı adı oturum açma ekranı tarafından önceden doldurulan hesapla oturum açmasını sağlayın. [Intune için Kullanıcı UPN ayarını yapılandırmanız](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm)gerekebilir. <br> <br> Veya kullanıcının yeni iş veya okul hesabıyla oturum açmasını ve mevcut MAM kaydı olan hesabı kaldırmasını sağlayın.
**Bağlantı Sorunu**: Beklenmeyen bir bağlantı sorunu oluştu. Bağlantınızı denetleyin ve yeniden deneyin.  |  Beklenmeyen hata. | Bir süre bekleyin ve yeniden deneyin. Hata devam ederse, Intune ile bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket) oluşturun.
**Uyarı**: Bu uygulama artık kullanılamaz. Daha fazla bilgi için BT yöneticinize başvurun. | Uygulamanın sertifikası doğrulanamadı. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.
**Hata**: Bu uygulama bir sorunla karşılaştı ve kapatılması gerekiyor. Bu hata devam ederse lütfen BT yöneticinize başvurun. | Apple iOS Anahtarlığından MAM uygulaması PIN’ini okuma hatası. | Cihazı yeniden başlatın. Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.

### <a name="error-messages-and-dialogs-on-android"></a>Android’de hata iletileri ve iletişim kutuları

İletişim/Hata iletisi | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli bir uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir Android uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Uygulama başlatma başarısız oldu**: Uygulamanız başlatılırken bir sorun oluştu. Uygulamayı ya da Intune Şirket Portalı uygulamasını güncelleştirmeyi deneyin. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin. | Intune uygulama için uygulama koruma ilkesinin geçerli olduğunu algıladı, ancak uygulama MAM başlatılırken kilitleniyor. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Intune Şirket Portalı uygulamasının cihazda yüklü ve güncel olduğundan emin olun. <br><br> Hata devam ederse, günlükleri Intune 'a göndermek veya bir [destek bileti](../fundamentals/get-support.md#create-an-online-support-ticket)oluşturmak için şirket portalı uygulamasını kullanın.
**Uygulama bulunamadı**: Bu cihazda, kuruluşunuzun bu içeriği açmasına izin verdiği herhangi bir uygulama yok. Yardım için BT yöneticinize başvurun. | Kullanıcı iş veya okul hesabını başka bir uygulamayla açmayı denedi ancak Intune verileri açma izni olan başka yönetilen uygulama bulamıyor. | Kullanıcının güvenliğine bir Android uygulama koruma ilkesi dağıtıldığından ve bu ilkenin söz konusu veriyi açabilen en azından başka bir MAM özellikli uygulamayı hedeflediğinden emin olun.
**Oturum açma başarısız oldu**: Oturum açmayı yeniden deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Kullanıcının oturum açmayı denediği hesabın kimlik doğrulaması başarısız oldu. | Kullanıcının Intune MAM hizmetine zaten kayıtlı bir iş veya okul hesabıyla oturum açtığından emin olun (Bu uygulamada başarıyla oturum açılan ilk iş veya okul hesabı). <br><br> Uygulamanın verilerini temizleyin. <br><br> Uygulama sürümünün güncel olduğundan emin olun. <br><br> Şirket Portalı sürümünün güncel olduğundan emin olun.
**İnternet bağlantısı gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Cihaz uyumlu değil**: Bu uygulama, cihazınıza kök erişim izni verildiğinden kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının kök erişim izni verilmiş bir cihaz kullandığını algılandı. | Cihazı fabrika ayarlarına sıfırlayın.
**Hesap ayarlanmadı**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor, ancak hesabınız henüz ayarlanmamış. Yardım için BT yöneticinize başvurun. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcı hesabının [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)bir Intune lisansı atanmış olduğundan emin olun.
**Uygulama kaydedilemedi**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor ancak uygulama şu anda kaydedilemedi. Yardım için BT yöneticinize başvurun. | Uygulama koruma ilkesi gerekli olduğunda uygulama MAM hizmetine otomatik olarak kaydedilemedi. | Uygulamanın verilerini temizleyin. <br><br> Şirket Portalı uygulama aracılığıyla veya bir destek bileti dosyası aracılığıyla Intune 'a günlük gönderin. Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Mobil uygulama yönetimi kurulumunuzu doğrulama](app-protection-policies-validate.md)
- Intune Uygulama Koruması ilke sorunlarını gidermek için günlük dosyalarını nasıl kullanacağınızı öğrenin, bkz. [https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372)
- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](../fundamentals/help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](../known-issues.md).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).
