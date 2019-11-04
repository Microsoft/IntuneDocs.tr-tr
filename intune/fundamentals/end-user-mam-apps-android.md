---
title: Uygulama koruma ilkelerine sahip Android uygulamaları
description: Bu konu başlığı altında, Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 946ce31c613ddb3c7dd2bf4dfde7561dd56e4ca0
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414052"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

Bu makale, uygulama koruma ilkeleri içeren uygulamalardaki kullanıcı deneyimini açıklar. Uygulama koruma ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: Örneğin kullanıcı, iş hesabı kullanarak uygulamalara veya şirketinizin OneDrive İş konumunda depolanan dosyalara eriştiğinde.

## <a name="access-apps"></a>Erişim uygulamaları

Şirket Portalı uygulaması, Android cihazlarda uygulama koruma ilkeleriyle ilişkili tüm uygulamalar için gereklidir.

Intune'a kayıtlı olmayan cihazlarda, Şirket Portalı uygulamasının cihaza yüklenmesi gerekir. Ancak kullanıcının uygulama koruma ilkeleri tarafından yönetilen uygulamaları kullanabilmesi için önce Şirket Portalı uygulamasını açması veya uygulamada oturum açması gerekmez.

Şirket Portalı uygulaması, Intune’un güvenli bir konumda veri paylaşmasının bir yoludur. Bu nedenle cihaz Intune'a kayıtlı olmasa bile, Şirket Portalı uygulaması uygulama koruma ilkeleri ile ilişkili olan tüm uygulamalar için gereklidir.

## <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

Uygulama koruma ilkeleri yalnızca iş bağlamında uygulanır. Bu nedenle uygulama, bağlamın iş veya kişisel olmasına göre farklı davranış gösterebilir.

Örneğin, kullanıcı iş verilerine erişirken kendisinden bir PIN istenir. **Outlook uygulamasında**, kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, kullanıcı iş hesabında yazdığında bir PIN istenir. Microsoft **Word**, **PowerPoint** ve **Excel** için kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde PIN istenir.

## <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Çoklu kimlik uygulamaları, kullanıcıların birden fazla hesap eklemelerine olanak tanır.  Intune uygulaması yalnızca bir yönetilen hesap destekler.  Intune uygulaması yönetilmeyen hesapların sayısını sınırlamaz.

Uygulamada bir yönetilen hesap olduğunda:

* Kullanıcı ikinci bir yönetilen hesap eklemeye çalışırsa kendisinden hangi yönetilen hesabın kullanılacağını seçmesi istenir.  Diğer hesap kaldırılır.
* BT yöneticisi ikinci bir mevcut hesaba ilke eklerse kullanıcıdan hangi yönetilen hesabın kullanılacağını seçmesi istenir.  Diğer hesap kaldırılır.

Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A,**Şirket X** ve **Şirket Y**olmak üzere iki şirket için geçerlidir. Kullanıcı A 'nın her şirket için bir iş hesabı vardır ve her ikisi de uygulama koruma ilkelerini dağıtmak için Intune 'u kullanır. **Şirket X** , **Şirket Y** **'den önce** uygulama koruma ilkeleri dağıtır. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak şirket Y ile ilişkili hesabı değildir. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, şirket X ile ilişkili kullanıcı hesabını kaldırmanız ve şirket Y ile ilişkili hesabı eklemeniz gerekir.

### <a name="add-a-second-account"></a>İkinci hesap ekleme

#### <a name="android"></a>Android

Android cihaz kullanıyorsanız, mevcut hesabı kaldırıp yenisini eklemeye ilişkin yönergeler bulunan bir engelleme iletisi görebilirsiniz.  Mevcut hesabı kaldırmak için **Ayarlar &gt;Genel &gt; Uygulama Yöneticisi &gt;Şirket Portalı**’na gidin. Ardından **Verileri Temizle**’yi seçin.

![Hata iletisi ve hesabı kaldırma yönergeleri ekran görüntüsü](./media/end-user-mam-apps-android/Android_SwitchUser.png)

## <a name="view-media-files-with-the-azure-information-protection-app"></a>Azure Information Protection uygulamasıyla medya dosyalarını görüntüleme

Şirket AV, PDF ve görüntü dosyalarını Android cihazlarda görüntülemek için [Azure Information Protection uygulamasını](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (önceden Rights Management özellikli paylaşım uygulaması olarak biliniyordu) kullanın.

Bu uygulamayı Google Play mağazasından indirin.  

Aşağıdaki dosya türleri desteklenir:

* **Ses:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (gelişmiş AAC+), AAC ELD (gelişmiş düşük gecikme AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Resim:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg
* **Belgeler:** PDF, PPDF

|**pfile**|
|----|
|Pfile, korumalı dosyalar için şifrelenmiş içerik ve Azure Information Protection lisanslarını kapsayan genel bir "sarmalayıcı" biçimidir. Herhangi bir dosya türünü korumak için kullanılabilir.|

## <a name="next-steps"></a>Sonraki adımlar
[iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](end-user-mam-apps-ios.md)
