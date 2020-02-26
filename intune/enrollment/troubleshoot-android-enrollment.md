---
title: Microsoft Intune 'de Android kurumsal cihazlarda sorun giderme
description: Intune 'A Android cihazları kaydettiğinizde en yaygın sorunların giderilmesi için öneriler.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/25/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 312f8ee3acb6b8be767d6349b29932ab65ae75d8
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77611031"
---
# <a name="troubleshoot-android-device-enrollment-problems-in-microsoft-intune"></a>Microsoft Intune Android cihaz kaydı sorunlarını giderme

Bu makale, Intune yöneticilerinin Android cihazlarını Intune 'A kaydetme sırasında sorunları anlamalarına ve sorunlarını gidermenize yardımcı olur.

## <a name="apps-on-android-devices"></a>Android cihazlarda uygulamalar

### <a name="managed-google-play-apps-that-arent-deployed-through-intune-are-displayed-in-the-work-profile"></a>Intune aracılığıyla dağıtılmamış yönetilen Google Play uygulamaları iş profilinde görüntülenir
Sistem uygulamaları, iş profili oluşturulduğu sırada cihaz OEM tarafından iş profilinde etkinleştirilebilir. Bu, MDM sağlayıcısı tarafından denetlenmez.

Sorunu gidermek için şu adımları izleyin:

  1. Şirket Portalı günlüklerini toplayın.
  2. İş profilinde beklenmedik şekilde görünen uygulamaları unutmayın.
  3. Cihazın Intune kaydını kaldırıp Şirket Portalı kaldırın.
  4. Test için EMM olmadan bir iş profili oluşturulmasına izin veren [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) uygulamasını yükler.
  5. Cihazda bir iş profili oluşturmak için [Test DPC](https://play.google.com/store/apps/details?id=com.afwsamples.testdpc) içindeki yönergeleri izleyin.
  6. İş profilinde görünen uygulamaları gözden geçirin. 
  7. Test DPC uygulamasında aynı uygulamalar gösteriliyorsa, uygulamalar bu cihaz için OEM tarafından beklenir.

### <a name="unapproved-google-play-for-work-store-apps-arent-being-removed-from-the-mobile-apps-page-in-intune"></a>Iş Mağazası uygulamaları için onaylanmamış Google Play, Intune 'daki Mobile Apps sayfasından kaldırılmaz
Bu beklenen bir davranıştır.

### <a name="managed-google-play-apps-arent-being-reported-under-the-discovered-apps-blade-in-the-intune-portal"></a>Yönetilen Google Play uygulamalar, Intune portalındaki bulunan uygulamalar dikey penceresinde bildirilmiyor
Bu beklenen bir davranıştır.

### <a name="are-web-applications-supported-for-work-profile-enrolled-devices"></a>İş profili kayıtlı cihazlar için desteklenen Web uygulamaları var mı?
Şu anda değil.

## <a name="device-management"></a>Cihaz yönetimi

### <a name="file-path-internal-storageandroiddatacommicrosoftwindowsintunecompanyportalfiles-missing-on-work-profile-enrolled-devices"></a>Dosya yolu Iç depolama/Android/Data. com. Microsoft. windowsinayarla. CompanyPortal/dosyalar eksik iş profili kayıtlı cihazlarda yok

  **Cevap**: Bu beklenen davranıştır. Bu yol yalnızca Cihaz Yöneticisi (eski Android kayıt) senaryosu için oluşturulur.

  Şirket Portalı günlüklerini toplamak için aşağıdaki adımları izleyin:

  1. Rozet ile Şirket Portalı uygulamasında, **menü** ' > **Yardım** > **e-posta desteği**' ne tıklayın ve ardından **e-posta gönder & karşıya yükle**' ye dokunun. 
  2. **Yardım Isteği göndermek**isteyip istemediğiniz sorulduğunda, e-posta uygulamalarından birini seçin.
  3. BT yöneticinize, Microsoft ürün desteği 'ne sağlanacak bir olay KIMLIĞI ile bir e-posta oluşturulur.

### <a name="managed-google-play-last-sync-time--hasnt-been-updated-in-days"></a>Yönetilen Google Play son eşitleme saati, gün cinsinden güncelleştirilmedi
Bu beklenen bir davranıştır. Eşitleme yalnızca el ile yaptığınız zaman tetiklenir.

### <a name="is-system-center-configuration-manager-hybrid-supported"></a>System Center Configuration Manager karma destekleniyor mu?
Bu, iş profili yönetimi için Configuration Manager 1702 ve sonraki sürümlerde desteklenir. Adanmış cihazlar (COSU) karma bir senaryoda desteklenmez.

### <a name="encryption-is-required-when-a-device-is-enrolled-can-it-be-turned-off"></a>Bir cihaz kaydolduğunda şifreleme gereklidir. Kapatılabilir mi?
Hayır, iş profili için Google 'dan şifreleme gerekir. 

### <a name="samsung-devices-are-blocking-the-use-of-third-party-keyboards-like-swiftkey"></a>Samsung cihazlar, SwiftKey gibi üçüncü taraf klavyeleri kullanmayı engelliyor
Samsung, Android 8.0 + cihazlarında bu kısıtlamayı zorlamaya başladı. Microsoft şu anda bu sorun üzerinde Samsung ile çalışmaktadır ve kullanılabilir olduğunda yeni bilgiler göndermeyecektir.

## <a name="remote-actions"></a>Uzak eylemler

### <a name="wipe-factory-reset-option-isnt-available-for-work-profile-enrolled-device"></a>Sil (fabrika sıfırlaması) seçeneği, iş profili kayıtlı cihazı için kullanılamaz
Bu beklenen bir davranıştır. İş profili senaryosunda, MDM sağlayıcısı cihaz üzerinde tam denetime sahip değildir. Kullanılabilir tek seçenek, tüm iş profilini ve tüm içeriğini kaldıran (şirket verilerini Kaldır) devre dışı.

### <a name="is-device-passcode-reset-supported"></a>Cihaz geçiş kodu sıfırlaması destekleniyor mu?
İş profili kayıtlı cihazlar için, şu durumlarda yalnızca Android 8,0 veya üzeri cihazlarda iş profili geçiş kodunu sıfırlayabilirsiniz:
- iş profili geçiş kodu yönetiliyor
- Son Kullanıcı onu sıfırlamanıza izin verildi.

Adanmış cihazlar (COSU) için cihaz geçiş kodu sıfırlaması desteklenir.


## <a name="next-steps"></a>Sonraki adımlar

- [Intune’da cihaz kaydı sorunlarını giderme](../troubleshoot-device-enrollment-in-intune.md)
- [Intune forumundan soru sorun](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Microsoft Intune destek ekibi blogunu denetleyin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Microsoft Enterprise Mobility ve Security blogunu denetleyin](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)