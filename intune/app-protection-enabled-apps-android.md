---
title: Uygulama koruma ilkelerine sahip Android uygulamaları
titlesuffix: Microsoft Intune
description: Koruma ilkelerine sahip bir Android uygulamasından neler bekleyebileceğinizi öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16cef0b3e72c2e7815aada1c45c0e312b84931ab
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31833026"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkelerine sahip Android uygulamalarından ne bekleyebileceğinizi öğrenin. Uygulama koruma ilkeleri, yalnızca uygulamalar çalışma bağlamında kullanıldığında uygulanır. Örneğin, bir iş hesabına sahip bir uygulamaya eriştiğinizde veya şirketinizin OneDrive konumunda kayıtlı dosyalara eriştiğinizde.
##  <a name="accessing-apps"></a>Uygulamalara erişme

Uygulama koruma ilkelerine sahip Android cihazlardaki tüm uygulamalar için Şirket Portalı uygulaması gereklidir.

Şirket Portalı'nı Intune'a kayıtlı olmayan tüm cihazlara yükleyin. Kullanıcıların uygulama koruma ilkeleri bulunan uygulamaları kullanmak için Şirket Portalı uygulamasında oturum açmaları gerekmez.
Şirket Portalı uygulaması, güvenli bir konumda veri paylaşmanıza olanak tanır. Bu nedenle kayıtlı olmayan cihazlar için bile gereklidir.


##  <a name="using-apps-with-multi-identity-support"></a>Birden çok kimlik destekli uygulamaları kullanma

Uygulama koruma ilkeleri, bir kullanıcı işle ilgili verilere erişmeye çalıştığında etkinleşir.  Kullanıcı kişisel kullanım için uygulamaya erişirse farklı davranışlar görebilirsiniz.

Bazı uygulamalar çoklu kimliği destekler. Bu durumda, Intune yalnızca bir kullanıcı iş verilerine eriştiğinde uygulama koruma ilkelerini uygular.  Örneğin, bir kullanıcı bir PIN istemi alabilir.  **Outlook uygulamasında**, kullanıcı uygulamayı başlattığında bir istem oluşur. **OneDrive uygulamasında**, kullanıcı iş hesabına yazdığında istem oluşur.  Microsoft **Word**, **PowerPoint** ve **Excel**’de, bir kullanıcı şirketin OneDrive belgelerine eriştiğinde bir istem oluşur.
##  <a name="managing-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune, uygulama koruma ilkelerinin cihaz başına tek bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir veya engellenmeyebilir. Ancak her durumda, yalnızca uygulama koruma ilkelerini alan ilk kullanıcı, ilkeden etkilenir.

  * **Microsoft Word**, **Excel** ve **PowerPoint** ek bir kullanıcı hesabına erişimi engellemez. Ancak, kullanıcı hesabı uygulama koruma ilkelerinden etkilenmez.

  * **OneDrive ve Outlook uygulamaları** için, yalnızca bir iş hesabı kullanabilirsiniz.  Birden çok iş hesabının eklenmesi bu uygulamalarda engellenmiştir.  Bununla birlikte, bir kullanıcıyı bir cihazdan kaldırabilir ve ardından cihaza farklı bir kullanıcı ekleyebilirsiniz.


* Bir cihazda, uygulama koruma ilkeleri dağıtılmadan önce birden fazla kullanıcı hesabı bulunabilir. Bu durumda, uygulama koruma ilkelerinin dağıtıldığı ilk hesap, Intune uygulama koruma ilkeleri tarafından yönetilir.


Intune’un çoklu kullanıcı hesaplarını nasıl işlediğini öğrenmek için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor: **Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini sağlamak için, Kullanıcı A’nın, Şirket X kullanıcı hesabını kaldırması gerekir.
### <a name="adding-a-second-account"></a>İkinci hesap ekleme
####  <a name="android"></a>Android
Mevcut hesabı kaldırmak ve yeni bir hesap eklemek için bir istem alabilirsiniz.  Mevcut hesabı kaldırmak için **Ayarlar &gt;Genel &gt; Uygulama Yöneticisi &gt;Şirket Portalı’na gidin. Ardından “Verileri temizle” seçeneğini belirleyin.**

![Hata iletisi ve hesabı kaldırma yönergeleri ekran görüntüsü](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Medya dosyalarını Azure Information Protection uygulaması ile (daha önce Rights Management paylaşım uygulaması olarak bilinirdi) görüntüleme
Şirket AV, PDF ve görüntü dosyalarını Android cihazlarda görüntülemek için [Azure Information Protection uygulamasını](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) kullanın.

Bu uygulamayı Google Play mağazasından indirin.  

Aşağıdaki dosya türleri desteklenir:

* **Ses:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (gelişmiş AAC+), AAC ELD (gelişmiş düşük gecikme AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Resim:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Belgeler:** PDF, PPDF

------------

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>metin</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pfile, korumalı dosyalar için bir genel “sarmalayıcı” biçimidir. Şifrelenmiş içeriği ve Azure Information Protection lisanslarını kapsüller. Herhangi bir dosya türünü korumak için kullanılabilir. | XML, CSV, vb. gibi metin dosyaları, korumalı olduklarında dahi uygulamada görüntülenmek üzere açılabilir. Dosya türleri: txt, ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>Sonraki adımlar
[iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
