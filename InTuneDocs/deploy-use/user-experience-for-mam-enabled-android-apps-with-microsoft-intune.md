---
title: "MAM ilkeleri içeren Android uygulamaları | Microsoft Docs"
description: "Bu konu başlığı altında, uygulamanız mobil uygulama yönetimi ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında, mobil uygulama yönetimi (MAM) ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. MAM ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: Örneğin, kullanıcı iş hesabını kullanarak uygulamalara veya şirketinizin OneDrive iş konumunda depolanan dosyalara eriştiğinde.
##  <a name="access-apps"></a>Erişim uygulamaları

Şirket Portalı uygulaması, Android cihazlarda MAM ilkeleriyle ilişkili olan tüm uygulamalar için gereklidir.

Intune'a kayıtlı olmayan cihazlarda, Şirket Portalı uygulamasının cihaza yüklenmesi gerekir. Ancak kullanıcının MAM ilkeleri tarafından yönetilen uygulamaları kullanabilmesi için önce Şirket Portalı uygulamasını açması veya uygulamada oturum açması gerekmez.

Şirket Portalı uygulaması, Intune’un güvenli bir konumda veri paylaşmasının bir yoludur. Bu nedenle cihaz Intune'a kayıtlı olmasa bile, Şirket Portalı uygulaması MAM ilkeleri ile ilişkili olan tüm uygulamalar için gereklidir.


##  <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

MAM ilkeleri yalnızca iş bağlamında uygulanır. Bu nedenle uygulama, bağlamın iş veya kişisel olmasına göre farklı davranış gösterebilir.

Örneğin, kullanıcı iş verilerine erişirken kendisinden bir PIN istenir. **Outlook uygulamasında**, kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, kullanıcı iş hesabında yazdığında bir PIN istenir. Microsoft **Word**, **PowerPoint** ve **Excel** için kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde PIN istenir.

##  <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune, MAM ilkelerinin cihaz başına yalnızca bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir. Ancak her durumda, yalnızca MAM ilkelerini alan ilk kullanıcı, ilkeden etkilenir.

  * **Microsoft Word**, **Excel**, ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez, ancak ikinci kullanıcı, MAM ilkelerinden etkilenmez.

  * **OneDrive** ve **Outlook uygulamaları** için yalnızca bir iş hesabı kullanabilirsiniz.  Bu uygulamalar için birden çok iş hesabı ekleyemezsiniz.  Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.


* Bir cihazda, MAM ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, MAM ilkelerinin dağıtıldığı hedef hesap, Intune MAM ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor—**Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de MAM ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, MAM ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap MAM ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının MAM ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.
### <a name="add-a-second-account"></a>İkinci hesap ekleme
####  <a name="android"></a>Android
Android cihaz kullanıyorsanız, mevcut hesabı kaldırıp yenisini eklemeye ilişkin yönergeler bulunan bir engelleme iletisi görebilirsiniz.  Mevcut hesabı kaldırmak için **Ayarlar &gt;Genel &gt; Uygulama Yöneticisi &gt;Şirket Portalı**’na gidin. Ardından **Verileri Temizle**’yi seçin.

![Hata iletisi ve hesabı kaldırma yönergeleri ekran görüntüsü](../media/AppManagement/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Azure Information Protection uygulamasıyla medya dosyalarını görüntüleme
Şirket AV, PDF ve görüntü dosyalarını Android cihazlarda görüntülemek için [Azure Information Protection uygulamasını](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (önceden Rights Management özellikli paylaşım uygulaması olarak biliniyordu) kullanın.

Bu uygulamayı Google Play mağazasından indirin.  

Aşağıdaki dosya türleri desteklenir:

* **Ses:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (gelişmiş AAC+), AAC ELD (gelişmiş düşük gecikme AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Resim:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg
* **Belgeler:** PDF, PPDF


|**pfile**|**metin**|
|----|----|
|Pfile, korumalı dosyalar için şifrelenmiş içerik ve Azure Information Protection lisanslarını kapsayan genel bir "sarmalayıcı" biçimidir. Herhangi bir dosya türünü korumak için kullanılabilir.|XML, CSV, vb. gibi metin dosyaları, korumalı olduklarında dahi uygulamada görüntülenmek üzere açılabilir. Dosya türleri: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.|

## <a name="next-steps"></a>Sonraki adımlar
[iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


