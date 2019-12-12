---
title: Apple Kullanıcı kaydıyla desteklenen Intune eylemleri ve seçenekleri
titleSuffix: Microsoft Intune
description: Apple Kullanıcı kaydıyla hangi Intune eylemlerinin ve seçeneklerinin desteklendiğini öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ffabcace189efd60e9d532172ecd1f2a048eec2c
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74562419"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Apple Kullanıcı kaydıyla desteklenen Intune eylemleri ve seçenekleri

Kullanıcı kaydı, cihaz yönetimi seçeneklerinin bir alt kümesini destekler. Önceden var olan bir yapılandırma profili bir kullanıcı kayıt cihazına uygulanmışsa, bu cihaza yalnızca Kullanıcı kaydı tarafından desteklenen ayarlar uygulanır.

> [!NOTE]
> Apple 'ın Intune 'da Kullanıcı kaydı desteği şu anda önizlemededir.

## <a name="password-settings"></a>Parola ayarları

Kullanıcı kayıt cihazlarında, herhangi bir parola ayarını yapılandırırsanız, **basit parolalar** ayarları otomatik olarak **engelleme**olarak ayarlanır ve 6 basamaklı bir PIN zorlanır.

Örneğin, **parola süre sonu** ayarını yapılandırır ve bu ilkeyi Kullanıcı tarafından kaydedilen cihazlara gönderirsiniz. Cihazlarda aşağıdakiler olur:
- **Parola süre sonu** ayarı yok sayılır.
- `1111` veya `1234`gibi basit parolalara izin verilmez.
- 6 basamaklı bir PIN zorlanır.

## <a name="administrator-remote-device-actions-and-options"></a>Yönetici uzak cihaz eylemleri ve seçenekleri
Yöneticiler, Kullanıcı kayıt cihazlarında aşağıdaki eylemleri ve seçenekleri gerçekleştirebilir:
- Devre dışı bırakma
- Sil
- Uzaktan Kilitleme
- Eşitle

Diğer tüm eylemler desteklenmez.

## <a name="end-user-actions"></a>Son Kullanıcı eylemleri
Kullanıcı kayıt cihazlarında, son kullanıcılar bu eylemleri cihazlarında Şirket Portalı uygulaması ve Web sitesinden gerçekleştirebilir:
- Yeniden Adlandır. Bu eylem yalnızca Şirket Portalı içindeki kullanıcıya yönelik ad için geçerlidir. Cihazı bu bağlamın dışında tamamen yeniden adlandırmaz.
- Kaldır
- Uzaktan Kilitleme
- Durumu Denetle

## <a name="app-deployment-options"></a>Uygulama dağıtım seçenekleri
Aşağıdaki uygulama türleri, Kullanıcı kayıt cihazlarına dağıtılabilir:
- Özel uygulamalar dahil Kullanıcı lisanslı birim satın alma planı (VPP) uygulamaları
- İş kolu (LOB) uygulamaları
- Web uygulamaları

## <a name="other-supported-options"></a>Desteklenen diğer seçenekler

Apple Kullanıcı kaydı kullanılarak kaydedilen cihazlar için Intune 'da aşağıdaki seçenekler desteklenir:
- Uygulama başına VPN. Bu destek, Kullanıcı kaydı Safari ayarlarını yapılandırmayı desteklemediğinden Safari etki alanlarını dışlar.
- WiFi 
- Kayıttan silme sonrasında kurumsal uygulama kaldırma
- Jailbreak algılama

Aşağıdaki kısıtlamalar desteklenir:
- Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme
- Kurumsal uygulamalarda kurumsal olmayan belgeleri görüntüleme
- Yönetilmeyen uygulamaların yönetilen kişiler hesaplarından okumasına izin ver
- Yönetilmeyen hedef olarak AirDrop
- Gerekli şifreli yedekleme
- Yönetilen uygulamalar buluta eşitlenir
- Cihaz kilitliyken denetim merkezi erişimi
- Cihaz kilitliyken bildirim merkezi erişimi
- Cihaz kilitliyken bugün görüntüleme
- Ekran görüntülerini engelle
- Kurumsal kitap yedeklemesini engelle
- Kurumsal kitap meta veri eşitlemesini engelle
- Şifreli yedekleme iste
- İzleme bilek algılama gerektir
- Siri engelle
- Cihaz kilitliyken Siri 'i engelle
- Safari sahtekarlık uyarılarını gerektir
- Apple 'a tanılama gönderimini engelle


## <a name="options-not-supported"></a>Seçenekler desteklenmiyor
Kullanıcı kaydıyla kaydedilen cihazlarda aşağıdaki seçenekler desteklenmez. Bu seçeneklere ihtiyacınız varsa, kişisel cihazlar için cihaz kaydını veya şirket cihazları için otomatik cihaz kaydını inceleyin.
- Yönetilen APFS birimi dışındaki uygulamalar için uygulama envanteri toplayın.
- Yönetilen APFS birimi dışında sertifikaların ve sağlama profillerinin envanterini toplayın.
- UıDıD ve diğer kalıcı cihaz tanımlayıcılarını toplayın.
- Kullanıcı kaydı, kaydedilen her cihaz için benzersiz bir kayıt KIMLIĞINI destekler, ancak kayıt kaldırıldıktan sonra bu KIMLIK kalıcı olmaz.
- Bu sınırlama nedeniyle aşağıdaki Intune özellikleri desteklenmez:
- Seri numarasının konu adı biçimindeki SCEP Kullanıcı profilleri.
- Cihaz düzeyinde VPN.
- Cihaz lisanslı VPP uygulama dağıtımı.
- App Store uygulamalarını yönetilen uygulamalar olarak yükler.
- Yönetilen APFS birimi dışındaki uygulamaların MDM denetimi.
- Uygulama koruma Ilkeleri bu uygulamalar için uygulanmaya devam edecektir. Ancak, Kullanıcı bu uygulamaları cihazlarından silmedikleri takdirde yönetimi veya bu uygulamaların yönetilen bir sürümünü dağıtmanız mümkün olmayacaktır.
- İşlemler, konfigürasyonlar, ayarlar ve gözetimvision gerektiren komutlar. 

## <a name="options-not-supported-in-preview"></a>Önizlemede desteklenmeyen seçenekler
- Kişisel cihazlara izin verme/engelleme için kayıt cihazı tür kısıtlamaları 

## <a name="known-issues-in-preview"></a>Önizlemede bilinen sorunlar
- VPP lisansı iptali: lisansın iptal edildiğini belirten bir bildirim görüntülenir. Geçerli davranış, iptal işleminin başarılı olması ancak son kullanıcıya bildirilmemelidir. 
- VPP uygulama raporlaması: Istemci uygulamalarında bulunan > Uygulamalar > [uygulama adı] > cihaz yüklemesi durumu, Kullanıcı tarafından kaydedilen cihazlara dağıtılan VPP uygulamaları, uygulama başarıyla cihaza dağıtıldığında bile "başarısız" olarak raporlanır. 
- Uygulama raporlama: Kullanıcı kaydında desteklenmeyen uygulama türleri Için raporlar, ilgisiz hata iletileri sağlayabilir. 
- Uygulama deneyimi Şirket Portalı: kullanıcılar, bu uygulama türlerinin Kullanıcı tarafından kaydedilen cihazlarda desteklenip desteklenmediğini bağımsız olarak, onlara hedeflenen tüm uygulamaları görür. 
- Uygulama deneyimi Şirket Portalı: kullanıcılar, kuruluşların Kullanıcı ve cihaz kaydı için neleri görebileceğini ve göremeyeceğini belirten metni görürler.
- Bir kullanıcı kayıt sırasında "Kuruluşumun bu cihaza sahip olduğu" seçeneğini seçerse, Yönetici Konsolu 'nda veya Graph aracılığıyla değiştirilmedikleri sürece cihaz hala Intune 'da kişisel olarak tanımlanır. 
- Kayıt hedefleme: ıpados platform seçicisinde listelenmez. ıpados önizleme sürümünde desteklenir, ancak yönetici konsolu içinde açıkça belirtilmedi. 


## <a name="next-steps"></a>Sonraki adımlar

[İOS ve ıpados Kullanıcı kaydını ayarlama](ios-user-enrollment.md)
