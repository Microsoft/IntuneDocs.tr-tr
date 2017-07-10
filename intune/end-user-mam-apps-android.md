---
title: "Uygulama koruma ilkelerine sahip Android uygulamaları"
description: "Bu konu başlığı altında, Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e9dc17cda485be244e05409bca69672edb87969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu konuda, uygulama koruma ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. Uygulama koruma ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: Örneğin, kullanıcı iş hesabı kullanarak uygulamalara veya şirketinizin OneDrive iş konumunda depolanan dosyalara eriştiğinde.
##  <a name="access-apps"></a>Erişim uygulamaları

Şirket Portalı uygulaması, Android cihazlarda uygulama koruma ilkeleriyle ilişkili tüm uygulamalar için gereklidir.

Intune'a kayıtlı olmayan cihazlarda, Şirket Portalı uygulamasının cihaza yüklenmesi gerekir. Ancak kullanıcının uygulama koruma ilkeleri tarafından yönetilen uygulamaları kullanabilmesi için önce Şirket Portalı uygulamasını açması veya uygulamada oturum açması gerekmez.

Şirket Portalı uygulaması, Intune’un güvenli bir konumda veri paylaşmasının bir yoludur. Bu nedenle cihaz Intune'a kayıtlı olmasa bile, Şirket Portalı uygulaması uygulama koruma ilkeleri ile ilişkili olan tüm uygulamalar için gereklidir.


##  <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

Uygulama koruma ilkeleri yalnızca iş bağlamında uygulanır. Bu nedenle uygulama, bağlamın iş veya kişisel olmasına göre farklı davranış gösterebilir.

Örneğin, kullanıcı iş verilerine erişirken kendisinden bir PIN istenir. **Outlook uygulamasında**, kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, kullanıcı iş hesabında yazdığında bir PIN istenir. Microsoft **Word**, **PowerPoint** ve **Excel** için kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde PIN istenir.

##  <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune, uygulama koruma ilkelerinin cihaz başına yalnızca bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir. Ancak her durumda, yalnızca uygulama koruma ilkelerini alan ilk kullanıcı, ilkeden etkilenir.

  * **Microsoft Word**, **Excel** ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez ama ikinci kullanıcı uygulama koruma ilkelerinden etkilenmez.

  * **OneDrive** ve **Outlook uygulamaları** için yalnızca bir iş hesabı kullanabilirsiniz.  Bu uygulamalar için birden çok iş hesabı ekleyemezsiniz.  Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.


* Bir cihazda, uygulama koruma ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, uygulama koruma ilkelerinin ilk dağıtıldığı hedef hesap, Intune uygulama koruma ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor—**Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.
### <a name="add-a-second-account"></a>İkinci hesap ekleme
####  <a name="android"></a>Android
Android cihaz kullanıyorsanız, mevcut hesabı kaldırıp yenisini eklemeye ilişkin yönergeler bulunan bir engelleme iletisi görebilirsiniz.  Mevcut hesabı kaldırmak için **Ayarlar &gt;Genel &gt; Uygulama Yöneticisi &gt;Şirket Portalı**’na gidin. Ardından **Verileri Temizle**’yi seçin.

![Hata iletisi ve hesabı kaldırma yönergeleri ekran görüntüsü](./media/Android_SwitchUser.png)

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
[iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](end-user-mam-apps-ios.md)
