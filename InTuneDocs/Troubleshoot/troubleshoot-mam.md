---
title: "Mobil uygulama yönetimi sorunlarını giderme | Microsoft Docs"
description: "Bu konu başlığında koşullu erişim dağıtımları için bazı sorun giderme ipuçları açıklanır."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Mobil uygulama yönetimi sorunlarını giderme

Intune mobil uygulama yönetimi ile ilgili sorun yaşıyorsanız, buradan başlayın. Bu konu başlığında bazı yaygın sorunlara çözümler ve sorularınıza yanıtlar sağlanır.

## <a name="common-it-administrator-issues"></a>Yaygın BT yöneticisi sorunları

1. **Sorun:** Azure portalında yapılan, cihaz kaydı olmadan uygulama koruma ilkesi, iOS ve Android cihazlardaki Skype Kurumsal uygulaması için uygulanmıyor.

  **Çözüm**: Skype Kurumsal’ın modern kimlik doğrulaması için ayarlanması gerekir.  Skype için modern kimlik doğrulamasını ayarlamak için lütfen [Modern kimlik doğrulaması için kiracınızı etkinleştirme](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) bölümündeki yönergeleri izleyin.

2. **Sorun:** Uygulama koruma ilkeleri, tüm kullanıcılar için hiçbir [desteklenen Office Uygulamasına](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) uygulanmıyor.

  **Çözüm**: Kullanıcının Intune lisansı olduğunu ve Office uygulamalarının dağıtılmış bir uygulama koruma ilkesi tarafından hedeflendiğini doğrulayın. Yeni dağıtılmış bir uygulama koruma ilkesinin uygulanması 8 saate kadar sürebilir.

3. **Sorun:** BT yöneticisi Azure Portalı’nda uygulama koruma ilkelerini yapılandıramıyor.

  **Çözüm**:

  Azure Portalı’na aşağıdaki kullanıcı rollerinin erişimi vardır:

  - [Office Portalı](http://portal.office.com/)’nda ayarlayabileceğiniz genel yönetici
  - [Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz sahip.
  - [Azure Portalı](https://portal.azure.com/)’nda ayarlayabileceğiniz katkıda bulunan.<br>

  Bu rolleri ayarlama konusunda yardım almak için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

4. **Sorun:** Yönetici konsolu raporları, uygulama koruma ilkesinin en son dağıtıldığı kullanıcı hesabını veya hesaplarını göstermiyor.

  **Çözüm**: Kullanıcı bir uygulama koruma ilkesiyle henüz hedeflenmişse, raporlarda bu kullanıcının hedeflenen kullanıcı olarak görünmesi 24 saate kadar sürebilir.

5. **Sorun:** İlke değişiklikleri/güncelleştirmelerinin uygulanması 8 saate kadar sürebiliyor.  

  **Çözüm**: Son kullanıcı uygulama oturumunu kapatıp hizmetle eşitlemeyi zorlayarak tekrar oturum açabilir.  

6. **Sorun:** Uygulama koruma ilkesi Apple DEP cihazlara uygulanmıyor.

  **Çözüm**: Lütfen Kullanıcı Benzeşimini Apple Aygıt Kayıt Programı (DEP) ile kullandığınızdan emin olun. Kullanıcı benzeşimi, DEP altında kullanıcı kimlik doğrulaması gerektiren her uygulama için gereklidir.
iOS DEP kaydı hakkında daha fazla bilgi için bkz. [Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="common-end-user-issues"></a>Yaygın son kullanıcı sorunları

### <a name="issues-on-ios"></a>iOS sorunları

İletişim/Hata iletisi | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama Ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Intune Managed Browser'a Hoş Geldiniz**: Bu uygulama, Microsoft Intune tarafından yönetildiğinde en iyi şekilde çalışır. Bu uygulamayı web'de gezinmek için her zaman kullanabilirsiniz ve uygulama Microsoft Intune tarafından yönetildiğinde ek veri koruma özelliklerine erişiminiz olur. | Intune Managed Browser uygulaması için gerekli uygulama koruma ilkesi algılanamadı. <br><br>Kullanıcı web’de gezinmek için uygulamayı kullanmaya devam edebilir ancak uygulama Intune tarafından yönetilmez. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve Intune Managed Browser uygulamasını hedeflediğinden emin olun.
**Oturum Açma Başarısız**: Şu an oturumunuzu açamıyoruz. Lütfen daha sonra tekrar deneyin. | Kullanıcı iş veya okul hesabıyla oturum açmayı denedikten sonra MAM hizmetine kaydedilemiyor. | Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Hesap Ayarlanmadı**: Kuruluşunuz hesabınızı iş veya okul verilerine erişecek şekilde ayarlamadı. Yardım için lütfen BT yöneticinizle görüşün. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcının hesabına [Office portalında](http://portal.office.com) bir Intune lisansı atandığından emin olun.
**Cihaz Uyumlu Değil**: Bu uygulama, cihazınıza jailbreak uygulandığı içi kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının jailbreak uygulanmış bir cihaz kullandığını algıladı. | Cihazı fabrika ayarlarına sıfırlayın. Apple destek sitesindeki [bu yönergeleri](https://support.apple.com/en-us/HT201274) izleyin.
**İnternet Bağlantısı Gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Bilinmeyen Hata**: Bu uygulamayı yeniden başlatmayı deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Bilinmeyen bir hata oluştu. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, [buradan](/how-to-get-support-for-microsoft-intune.md) Intune ile bir destek bileti oluşturun.
**Kuruluşunuzun Verilerine Erişme**: Belirttiğiniz iş veya okul hesabının bu uygulamaya erişimi yok. Farklı bir hesapla oturum açmanız gerekebilir. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının cihaz için MAM kaydı olan hesaptan farklı bir ikinci iş veya okul hesabıyla oturum açmayı denediğini algılar. Cihaz başına aynı anda yalnızca bir iş veya okul hesabı MAM tarafından yönetilebilir. | Kullanıcının, kullanıcı adı oturum açma ekranı tarafından önceden doldurulan hesapla oturum açmasını sağlayın. <br> <br> Veya kullanıcının yeni iş veya okul hesabıyla oturum açmasını ve mevcut MAM kaydı olan hesabı kaldırmasını sağlayın.
**Bağlantı Sorunu**: Beklenmeyen bir bağlantı sorunu oluştu. Bağlantınızı denetleyin ve yeniden deneyin.  |  Beklenmeyen hata. | Bir süre bekleyin ve yeniden deneyin. Sorun devam ederse, [buradan](/how-to-get-support-for-microsoft-intune.md) Intune ile bir destek bileti oluşturun.
**Uyarı**: Bu uygulama artık kullanılamaz. Daha fazla bilgi için BT yöneticinize başvurun. | Uygulamanın sertifikası doğrulanamadı. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.
**Hata**: Bu uygulama bir sorunla karşılaştı ve kapatılması gerekiyor. Bu hata devam ederse lütfen BT yöneticinize başvurun. | Apple iOS Anahtarlığından MAM uygulaması PIN’ini okuma hatası. | Cihazı yeniden başlatın. Uygulama sürümünün güncel olduğundan emin olun. <br><br> Uygulamayı yeniden yükleyin.


### <a name="issues-on-android"></a>Android sorunları

İletişim/Hata iletisi | Nedeni | Düzeltme |
-- | --- | --- |
**Uygulama ayarlanmadı**: Bu uygulama, kullanabilmeniz için ayarlanmamış. Yardım için BT yöneticinize başvurun. | Uygulama için gerekli uygulama koruma ilkesi algılanamadı. |Kullanıcının güvenlik grubuna bir iOS uygulama koruma ilkesi dağıtıldığından ve bu uygulamayı hedeflediğinden emin olun.
**Uygulama başlatma başarısız oldu**: Uygulamanız başlatılırken bir sorun oluştu. Uygulamayı ya da Intune Şirket Portalı uygulamasını güncelleştirmeyi deneyin. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin. | Intune uygulama için uygulama koruma ilkesinin geçerli olduğunu algıladı, ancak uygulama MAM başlatılırken kilitleniyor. | Uygulama sürümünün güncel olduğundan emin olun. <br><br> Intune Şirket Portalı uygulamasının cihazda yüklü ve güncel olduğundan emin olun. <br><br> Hata devam ederse, Intune'a günlükleri göndermek için Şirket Portal uygulamasını kullanın veya [burada](/how-to-get-support-for-microsoft-intune.md) bir destek bileti oluşturun.
**Uygulama bulunamadı**: Bu cihazda, kuruluşunuzun bu içeriği açmasına izin verdiği herhangi bir uygulama yok. Yardım için BT yöneticinize başvurun. | Kullanıcı iş veya okul hesabını başka bir uygulamayla açmayı denedi ancak Intune verileri açma izni olan başka yönetilen uygulama bulamıyor. | Kullanıcının güvenliğine bir Android uygulama koruma ilkesi dağıtıldığından ve bu ilkenin söz konusu veriyi açabilen en azından başka bir MAM özellikli uygulamayı hedeflediğinden emin olun.
**Oturum açma başarısız oldu**: Oturum açmayı yeniden deneyin. Sorun devam ederse yardım için BT yöneticinize başvurun. | Kullanıcının oturum açmayı denediği hesabın kimlik doğrulaması başarısız oldu. | Kullanıcının Intune MAM hizmetine zaten kayıtlı bir iş veya okul hesabıyla oturum açtığından emin olun (Bu uygulamada başarıyla oturum açılan ilk iş veya okul hesabı). <br><br> Uygulamanın verilerini temizleyin. <br><br> Uygulama sürümünün güncel olduğundan emin olun. <br><br> Şirket Portalı sürümünün güncel olduğundan emin olun.
**İnternet bağlantısı gerekli**: Bu uygulamayı kullanabileceğinizi doğrulamak için İnternet'e bağlı olmalısınız. | Cihaz, İnternet'e bağlı değil. | Cihazı bir WiFi veya Veri ağına bağlayın.
**Cihaz uyumlu değil**: Bu uygulama, cihazınıza kök erişim izni verildiğinden kullanılamaz. Yardım için BT yöneticinize başvurun. | Intune, kullanıcının kök erişim izni verilmiş bir cihaz kullandığını algılandı. | Cihazı fabrika ayarlarına sıfırlayın.
**Hesap ayarlanmadı**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor, ancak hesabınız henüz ayarlanmamış. Yardım için BT yöneticinize başvurun. | Kullanıcı hesabının Intune A Direct lisansı yok. | Kullanıcının hesabına [Office portalında](http://portal.office.com) bir Intune lisansı atandığından emin olun.
**Uygulama kaydedilemedi**: Bu uygulamanın Microsoft Intune tarafından yönetilmesi gerekiyor ancak uygulama şu anda kaydedilemedi. Yardım için BT yöneticinize başvurun. | Uygulama koruma ilkesi gerekli olduğunda uygulama MAM hizmetine otomatik olarak kaydedilemedi. | Uygulamanın verilerini temizleyin. <br><br> Günlükleri Şirket Portalı uygulaması ile Intune'a gönderin veya [buradan](/how-to-get-support-for-microsoft-intune.md) bir destek bileti başvurusu yapın.





### <a name="see-also"></a>Ayrıca bkz.
- [Mobil uygulama yönetimi kurulumunuzu doğrulama](../deploy-use/validate-mobile-application-management.md)
- [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlanma](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


