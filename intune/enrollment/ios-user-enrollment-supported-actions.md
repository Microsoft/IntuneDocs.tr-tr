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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: acf1112f96b28b156b3c4857485de30d7ad553ef
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955436"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Apple Kullanıcı kaydıyla desteklenen Intune eylemleri ve seçenekleri

Kullanıcı kaydı, cihaz yönetimi seçeneklerinin bir alt kümesini destekler. Önceden var olan bir yapılandırma profili bir kullanıcı kayıt cihazına uygulanmışsa, bu cihaza yalnızca Kullanıcı kaydı tarafından desteklenen ayarlar uygulanır.

## <a name="password-settings"></a>Parola ayarları

Kullanıcı kayıt cihazlarında, herhangi bir parola ayarını yapılandırırsanız, **basit parolalar** ayarları otomatik olarak **engelleme**olarak ayarlanır ve 6 basamaklı bir PIN zorlanır.

Örneğin, **parola süre sonu** ayarını yapılandırır ve bu ilkeyi Kullanıcı tarafından kaydedilen cihazlara gönderirsiniz. Cihazlarda aşağıdakiler olur:
- **Parola süre sonu** ayarı yok sayılır.
- @No__t-0 veya `1234` gibi basit parolalara izin verilmez.
- 6 basamaklı bir PIN zorlanır.

## <a name="administrator-remote-device-actions-and-options"></a>Yönetici uzak cihaz eylemleri ve seçenekleri
Yöneticiler, Kullanıcı kayıt cihazlarında aşağıdaki eylemleri ve seçenekleri gerçekleştirebilir:
- Bırakmak
- Sil
- Uzaktan Kilitleme
- Eşitleme

Diğer tüm eylemler desteklenmez.

## <a name="end-user-actions"></a>Son Kullanıcı eylemleri
Kullanıcı kayıt cihazlarında, son kullanıcılar bu eylemleri cihazlarında Şirket Portalı uygulaması ve Web sitesinden gerçekleştirebilir:
- Yeniden Adlandır. Bu eylem yalnızca Şirket Portalı içindeki kullanıcıya yönelik ad için geçerlidir. Cihazı bu bağlamın dışında tamamen yeniden adlandırmaz.
- Kaldır
- Uzaktan Kilitleme
- Durumu Denetle

## <a name="other-supported-options"></a>Desteklenen diğer seçenekler

Apple Kullanıcı kaydı kullanılarak kaydedilen cihazlar için Intune 'da aşağıdaki seçenekler desteklenir:
- Uygulama başına VPN. Bu destek, Kullanıcı kaydı Safari ayarlarını yapılandırmayı desteklemediğinden Safari etki alanlarını dışlar.
- WiFi 
- Kayıttan silme sonrasında kurumsal uygulama kaldırma
- Kullanıcı lisanslı birim satın alma planı (VPP) aracılığıyla uygulama dağıtımı
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
- Şifrelenmiş yedekleme gerektir
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
- Seri Numin. r için konu adı biçimindeki SCEP Kullanıcı profilleri
- Cihaz düzeyinde VPN.
- Cihaz lisanslı VPP uygulama dağıtımı.
- Yönetilen APFS birimi dışındaki uygulamaların MDM denetimi.
- Uygulama koruma Ilkeleri bu uygulamalar için uygulanmaya devam edecektir. Ancak, Kullanıcı bu uygulamaları cihazlarından silmedikleri takdirde yönetimi veya bu uygulamaların yönetilen bir sürümünü dağıtmanız mümkün olmayacaktır.
- İşlemler, konfigürasyonlar, ayarlar ve gözetimvision gerektiren komutlar. 

## <a name="next-steps"></a>Sonraki adımlar

[İOS ve ıpados Kullanıcı kaydını ayarlama](ios-user-enrollment.md)