---
title: "Uygulama koruma ilkelerine sahip Android uygulamaları"
titleSuffix: Intune on Azure
description: "Bu konu başlığı altında, Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d48725852e26b9e4b9c66a3d614bfc1c95dc58f
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konuda, uygulama koruma ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. Uygulama koruma ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: İş hesabınızı kullanarak uygulamalara veya şirketinizin OneDrive İş konumunda depolanan dosyalara erişmek gibi.
##  <a name="accessing-apps"></a>Uygulamalara erişme

Şirket Portalı uygulaması, Android cihazlarda uygulama koruma ilkeleriyle ilişkili tüm uygulamalar için gereklidir.

Intune'a kayıtlı olmayan cihazlarda, Şirket Portalı uygulamasının cihaza yüklenmesi gerekir. Öte yandan, kullanıcının uygulama koruması ilkeleri tarafından yönetilen uygulamaları kullanabilmek için önce Şirket Portalı uygulamasını açması veya bu uygulamada oturum açması gerekmez.
Şirket Portalı uygulaması, Intune’un güvenli bir konumda veri paylaşmasının bir yoludur; bu nedenle cihaz Intune'da kayıtlı olmasa bile bir zorunluluktur.


##  <a name="using-apps-with-multi-identity-support"></a>Birden çok kimlik destekli uygulamaları kullanma

Uygulama koruma ilkeleri uygulama kullanılırken yalnızca iş bağlamında uygulanır; bu nedenle bağlama (iş veya kişisel) bağlı olarak farklı uygulama davranışları görebilirsiniz.

Intune, birden çok kimliği destekleyen uygulamalarda uygulama koruma ilkelerini yalnızca son kullanıcı uygulamayı iş bağlamında kullandığında uygular.  Örneğin, son kullanıcı iş verilerine erişirken bir PIN istenir.  **Outlook uygulamasında**, son kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, bu durum son kullanıcı iş hesabını yazdığında gerçekleşir.  Microsoft **Word**, **PowerPoint* ve **Excel** için bu, son kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde gerçekleşir.
##  <a name="managing-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune yalnızca, uygulama koruma ilkelerinin cihaz başına tek bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir veya engellenmeyebilir. Ancak her durumda, yalnızca uygulama koruma ilkelerini alan ilk kullanıcı, ilkeden etkilenir.

  * **Microsoft Word**, **Excel** ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez ama ikinci kullanıcı uygulama koruma ilkelerinden etkilenmez.

  * **OneDrive ve Outlook uygulamaları** için, yalnızca bir iş hesabı kullanabilirsiniz.  Birden çok iş hesabının eklenmesi bu uygulamalarda engellenmiştir.  Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.


* Bir cihazda, uygulama koruma ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, uygulama koruma ilkelerinin ilk dağıtıldığı hedef hesap, Intune uygulama koruma ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor - **Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.
### <a name="adding-a-second-account"></a>İkinci hesap ekleme
####  <a name="android"></a>Android
Android cihaz kullanıyorsanız, mevcut hesabı kaldırıp yenisini eklemeye ilişkin yönergeler bulunan bir engelleme iletisi görebilirsiniz.  Mevcut hesabı kaldırmak için **Ayarlar &gt;Genel &gt;Uygulama Yöneticisi &gt;Şirket Portalı’na gidin ve "Verileri Temizle"’yi seçin**.

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
|**pfile**|**metin**|
|----|----|
|Pfile, korumalı dosyalar için şifrelenmiş içerik ve Azure Information Protection lisanslarını kapsayan genel bir "sarmalayıcı" biçimidir ve herhangi bir dosya türünü korumak üzere kullanılabilir.|XML, CSV, vb. gibi metin dosyaları, korumalı olduklarında dahi uygulamada görüntülenmek üzere açılabilir. Dosya türleri: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>Sonraki adımlar
[iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
