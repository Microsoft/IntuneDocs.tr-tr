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
ms.openlocfilehash: 96c802e76aab673aa6a9108dc0a14f553c26b96b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505407"
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
- Devre dışı bırakma
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
- Seri Numin. r için konu adı biçimindeki SCEP Kullanıcı profilleri
- Cihaz düzeyinde VPN.
- Cihaz lisanslı VPP uygulama dağıtımı.
- Yönetilen APFS birimi dışındaki uygulamaların MDM denetimi.
- Uygulama koruma Ilkeleri bu uygulamalar için uygulanmaya devam edecektir. Ancak, Kullanıcı bu uygulamaları cihazlarından silmedikleri takdirde yönetimi veya bu uygulamaların yönetilen bir sürümünü dağıtmanız mümkün olmayacaktır.
- İşlemler, konfigürasyonlar, ayarlar ve gözetimvision gerektiren komutlar. 

## <a name="next-steps"></a>Sonraki adımlar

[İOS ve ıpados Kullanıcı kaydını ayarlama](ios-user-enrollment.md)