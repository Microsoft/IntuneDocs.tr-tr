---
title: Mobil uygulama yönetimi sorunlarını giderme
description: Bu konu başlığında koşullu erişim dağıtımları için bazı sorun giderme ipuçları açıklanır.
keywords: ''
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: ec6e663c570399f0adca02772416904d5a9dcc79
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-mobile-application-management"></a>Mobil uygulama yönetimi sorunlarını giderme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune mobil uygulama yönetimi ile ilgili sorun yaşıyorsanız, buradan başlayın. Bu konu başlığında bazı yaygın sorunlara çözümler ve sorularınıza yanıtlar sağlanır.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).


## <a name="common-it-administrator-issues"></a>Yaygın BT yöneticisi sorunları

Bunlar, bir BT yöneticisinin Intune uygulama koruma ilkesini kullanırken karşılaşabileceği yaygın sorunlardır.

| Sorun | Description | Çözüm |
| -- | -- | -- |
| İlke, Skype Kurumsal’a uygulanmamış | Azure portalında yapılan cihaz kaydı olmadan uygulama koruma ilkesi, iOS ve Android cihazlardaki Skype Kurumsal uygulaması için uygulanmıyor. | Skype Kurumsal’ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulamasını ayarlamak için lütfen [Modern kimlik doğrulaması için kiracınızı etkinleştirme](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin. |
| Office uygulama ilkesi uygulanmamış | Uygulama koruma ilkeleri, tüm kullanıcılar için hiçbir [desteklenen Office Uygulamasına](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) uygulanmıyor. | Kullanıcının Intune lisansı olduğunu ve Office uygulamalarının dağıtılmış bir uygulama koruma ilkesi tarafından hedeflendiğini doğrulayın. Yeni dağıtılmış bir uygulama koruma ilkesinin uygulanması 8 saate kadar sürebilir. |
| Yönetici, uygulama koruma ilkesini Azure portalında yapılandıramıyor | BT yöneticisi, uygulama koruma ilkelerini Azure Portalı’nda yapılandıramıyor. | Azure Portalı’na aşağıdaki kullanıcı rollerinin erişimi vardır: <ul><li>[Office Portalı](http://portal.office.com/)’nda ayarlayabileceğiniz genel yönetici</li><li>[Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz sahip.</li><li>[Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz katkıda bulunan.</li></ul>  Bu rolleri ayarlama konusunda yardım almak için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).|
|Uygulama koruma ilkesi raporlarında eksik kullanıcı hesapları var | Yönetim konsolu raporları, uygulama koruma ilkesinin en son dağıtıldığı kullanıcı hesaplarını göstermiyor. | Kullanıcı bir uygulama koruma ilkesiyle henüz hedeflenmişse, bu kullanıcının raporlarda hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir. |
| İlke değişiklikleri çalışmıyor | Uygulama koruma ilkesinde yapılan değişikliklerin ve güncelleştirmelerin uygulanması 8 saate kadar sürebilir. | Mümkünse, son kullanıcı uygulama oturumunu kapatıp hizmetle eşitlemeyi zorlayarak tekrar oturum açabilir. |
| Uygulama koruma ilkesi DEP ile çalışmıyor | Uygulama koruma ilkesi Apple DEP cihazlara uygulanmıyor. | Lütfen Kullanıcı Benzeşimi’ni Apple Aygıt Kayıt Programı (DEP) ile kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında kullanıcı kimlik doğrulaması gerektiren her uygulama için gereklidir. <br><br>iOS DEP kaydı hakkında daha fazla bilgi için bkz. [Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).|
| Veri aktarım ilkesi iOS ile çalışmıyor | **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** ve **Uygulamanın diğer uygulamalardan veri almasına izin ver** ilkeleri iOS’ta veri aktarımı gerçekleştiremiyor. | Bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>Yaygın son kullanıcı sorunları

Yaygın son kullanıcı sorunları aşağıdaki kategorilere ayrılmıştır:

* **Normal kullanım senaryoları**: Bir son kullanıcı bu senaryoları Intune uygulama koruma ilkesine sahip uygulamalarda görebilir. Bunlar gerçek sorunlar olmamakla birlikte, hata veya arıza olarak algılanabilir.

* **Normal kullanım iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği kullanım iletişim kutularıdır. Bu iletiler ve iletişim kutuları bir hata veya arıza olduğunu **göstermez**.

* **Hata iletileri ve iletişim kutuları**: Bunlar, bir son kullanıcının Intune uygulama koruma ilkesine sahip uygulamalarda görebileceği hata iletileri ve iletişim kutularıdır. Bunlar, genellikle BT yöneticisi tarafından yapılan bir hatayı veya bir Intune uygulama koruma hatasını belirtir.



### <a name="normal-usage-scenarios"></a>Normal kullanım senaryoları

Platform | Senaryo | Açıklama |
---| --- | --- |
iOS | Son kullanıcı, veri aktarımı ilkesi **Yalnızca yönetilen uygulamalar** veya **Uygulama yok** olarak ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS paylaşım uzantısını kullanabilir. Bu veri sızıntısına neden olmaz mı? | Intune uygulama koruma ilkesi cihazı yönetmiyorsa iOS paylaşım uzantısını denetleyemez. Bu nedenle **Intune, “kurumsal” verileri uygulama dışında paylaşmadan önce şifreler**. Bunu, yönetilen uygulama dışında "kurumsal" dosyayı açmaya çalışarak doğrulayabilirsiniz. Bu dosya yalnızca şifrelenmiş ve yönetilen bir uygulama olarak açılmalıdır.
Android | MAM uygulama korumasını cihaz kaydı olmadan kullanıyor olsam bile son kullanıcının neden **Şirket Portalı uygulamasını yüklemesi gerekir**?  | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.

### <a name="normal-usage-dialogs"></a>Normal kullanım iletişim kutuları

Platform | İleti veya iletişim kutusu | Açıklama |
--- | --- | --- |
iOS, Android | **Oturum açma**: Kuruluşunuzun, verilerini korumak için bu uygulamayı yönetmesi gerekir. Bu işlemi tamamlamak için iş veya okul hesabınızla oturum açın. | Son kullanıcının bu uygulamayı kullanabilmesi için kendi iş veya okul hesabıyla oturum açması gerekir ve bunun için uygulama koruma ilkesi gerekir. İlkenin uygulanabilmesi için kullanıcının Azure Active Directory’de kimlik doğrulaması gerekir.
iOS, Android |**Yeniden Başlatma Gerekli**: Kuruluşunuz artık verilerini bu uygulama içinde koruyor. Devam etmek için uygulamayı yeniden başlatmanız gerekir. | Uygulama biraz önce Intune uygulama koruma ilkesini aldı ve ilkenin uygulanması için yeniden başlatmanız gerekir.
iOS, Android |**Eyleme İzin Verilmiyor**: Kuruluşunuz bu uygulamada yalnızca iş veya okul verilerinizi açmanıza izin veriyor. | BT yöneticiniz **Uygulamanın diğer uygulamalardan veri almasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, son kullanıcı bu uygulamaya yalnızca uygulama koruma ilkesine sahip diğer uygulamalardan veri aktarabilir.
iOS, Android |**Eyleme İzin Verilmiyor**: Kuruluşunuz verilerini yalnızca diğer yönetilen uygulamalara aktarmanıza izin veriyor. | BT yöneticiniz **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** değerini **Yalnızca yönetilen uygulamalar** olarak ayarladı. Bu nedenle, son kullanıcı bu uygulamadan yalnızca uygulama koruma ilkesine sahip diğer uygulamalara veri aktarabilir.
iOS, Android |**Silme Alarmı**: Kuruluşunuz bu uygulama ile ilişkili verilerini kaldırdı. Devam etmek için uygulamayı yeniden başlatın. | BT yöneticisi Intune uygulama koruması kullanarak bir uygulama silme işlemi başlattı.
Android | **Şirket Portalı gerekli**: İş veya okul hesabınızı bu uygulamayla kullanabilmeniz için Intune Şirket Portalı uygulamasını yüklemeniz gerekir. Devam etmek için “Mağazaya git” seçeneğine dokunun. | Android’de, uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. **Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı gerekli değildir**. Kayıt olmadan uygulama koruması için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.


### <a name="error-messages-and-dialogs-on-ios"></a>iOS’ta hata iletileri ve iletişim kutuları


Hata iletisi veya iletişim kutusu | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama Ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Intune Managed Browser'a Hoş Geldiniz**: Bu uygulama, Microsoft Intune tarafından yönetildiğinde en iyi şekilde çalışır. Bu uygulamayı web'de gezinmek için her zaman kullanabilirsiniz ve uygulama Microsoft Intune tarafından yönetildiğinde ek veri koruma özelliklerine erişiminiz olur. | Intune Managed Browser uygulaması için gerekli uygulama koruma ilkesi algılanamadı. <br><br>Kullanıcı web’de gezinmek için uygulamayı kullanmaya devam edebilir ancak uygulama Intune tarafından yönetilmez. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve Intune Managed Browser uygulamasını hedeflediğinden emin olun.
**Oturum Açma Başarısız**: Şu an oturumunuzu açamıyoruz. Lütfen daha sonra tekrar deneyin. | Kullanıcı iş veya okul hesabıyla oturum açmayı denedikten sonra MAM hizmetine kaydedilemiyor. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Hesap Ayarlanmadı**: Kuruluşunuz hesabınızı iş veya okul verilerine erişecek şekilde ayarlamadı. Yardım için lütfen BT yöneticinizle görüşün. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcının hesabına [Office portalında](http://portal.office.com) bir Intune lisansı atandığından emin olun.
**Cihaz Uyumlu Değil**: Bu uygulama, cihazınıza jailbreak uygulandığı içi kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının jailbreak uygulanmış bir cihaz kullandığını algıladı. | Cihazı fabrika ayarlarına sıfırlayın. Apple destek sitesindeki [bu yönergeleri](https://support.apple.com/HT201274) izleyin.
**İnternet Bağlantısı Gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Bilinmeyen Hata**: Bu uygulamayı yeniden başlatmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Bilinmeyen bir hata oluştu. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, [buradan](how-to-get-support-for-microsoft-intune.md) Intune ile bir destek bileti oluşturun.
**Kuruluşunuzun Verilerine Erişme**: Belirttiğiniz iş veya okul hesabının bu uygulamaya erişimi yok. Farklı bir hesapla oturum açmanız gerekebilir. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının cihaz için MAM kaydı olan hesaptan farklı bir ikinci iş veya okul hesabıyla oturum açmayı denediğini algılar. Cihaz başına aynı anda yalnızca bir iş veya okul hesabı MAM tarafından yönetilebilir. | Kullanıcının, kullanıcı adı oturum açma ekranı tarafından önceden doldurulan hesapla oturum açmasını sağlayın. <br> <br> Veya kullanıcının yeni iş veya okul hesabıyla oturum açmasını ve mevcut MAM kaydı olan hesabı kaldırmasını sağlayın.
**Bağlantı Sorunu**: Beklenmeyen bir bağlantı sorunu oluştu. Bağlantınızı denetleyin ve yeniden deneyin.  |  Beklenmeyen hata. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, [buradan](how-to-get-support-for-microsoft-intune.md) Intune ile bir destek bileti oluşturun.
**Uyarı**: Bu uygulama artık kullanılamaz. Daha fazla bilgi için BT yöneticinize başvurun. | Uygulamanın sertifikası doğrulanamadı. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.
**Hata**: Bu uygulama bir sorunla karşılaştı ve kapatılması gerekiyor. Bu hata devam ederse lütfen BT yöneticinize başvurun. | Apple iOS Anahtarlığından MAM uygulaması PIN’ini okuma hatası. | Cihazı yeniden başlatın. Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.


### <a name="error-messages-and-dialogs-on-android"></a>Android’de hata iletileri ve iletişim kutuları

İletişim/Hata iletisi | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir Android uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Uygulama başlatma başarısız oldu**: Uygulamanız başlatılırken bir sorun oluştu. Uygulamayı ya da Intune Şirket Portalı uygulamasını güncelleştirmeyi deneyin. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin. | Intune uygulama için uygulama koruma ilkesinin geçerli olduğunu algıladı, ancak uygulama MAM başlatılırken kilitleniyor. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Intune Şirket Portalı uygulamasının cihazda yüklü ve güncel olduğundan emin olun. <br><br> Hata devam ederse, Intune'a günlükleri göndermek için Şirket Portal uygulamasını kullanın veya [burada](how-to-get-support-for-microsoft-intune.md) bir destek bileti oluşturun.
**Uygulama bulunamadı**: Bu cihazda, kuruluşunuzun bu içeriği açmasına izin verdiği herhangi bir uygulama yok. Yardım için BT yöneticinize başvurun. | Kullanıcı iş veya okul hesabını başka bir uygulamayla açmayı denedi ancak Intune verileri açma izni olan başka yönetilen uygulama bulamıyor. | Kullanıcının güvenliğine bir Android uygulama koruma ilkesi dağıtıldığından ve bu ilkenin söz konusu veriyi açabilen en azından başka bir MAM özellikli uygulamayı hedeflediğinden emin olun.
**Oturum açma başarısız oldu**: Oturum açmayı yeniden deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Kullanıcının oturum açmayı denediği hesabın kimlik doğrulaması başarısız oldu. | Kullanıcının Intune MAM hizmetine zaten kayıtlı bir iş veya okul hesabıyla oturum açtığından emin olun (Bu uygulamada başarıyla oturum açılan ilk iş veya okul hesabı). <br><br> Uygulamanın verilerini temizleyin. <br><br> Uygulama sürümünün güncel olduğundan emin olun. <br><br> Şirket Portalı sürümünün güncel olduğundan emin olun.
**İnternet bağlantısı gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Cihaz uyumlu değil**: Bu uygulama, cihazınıza kök erişim izni verildiğinden kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının kök erişim izni verilmiş bir cihaz kullandığını algılandı. | Cihazı fabrika ayarlarına sıfırlayın.
**Hesap ayarlanmadı**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor, ancak hesabınız henüz ayarlanmamış. Yardım için BT yöneticinize başvurun. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcının hesabına [Office portalında](http://portal.office.com) bir Intune lisansı atandığından emin olun.
**Uygulama kaydedilemedi**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor ancak uygulama şu anda kaydedilemedi. Yardım için BT yöneticinize başvurun. | Uygulama koruma ilkesi gerekli olduğunda uygulama MAM hizmetine otomatik olarak kaydedilemedi. | Uygulamanın verilerini temizleyin. <br><br> Günlükleri Şirket Portalı uygulaması ile Intune'a gönderin veya [buradan](how-to-get-support-for-microsoft-intune.md) bir destek bileti başvurusu yapın.




### <a name="see-also"></a>Ayrıca bkz:
- [Mobil uygulama yönetimi kurulumunuzu doğrulama](../deploy-use/validate-mobile-application-management.md)
- [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlanma](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md)
