---
title: "Azure’da Microsoft Intune bilinen sorunları"
titleSuffix: Intune on Azure
description: "Intune’da bilinen sorunlar hakkında okuyun\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="known-issues-in-microsoft-intune"></a>Microsoft Intune’da bilinen sorunlar


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinmek için bu konuyu kullanın.

Burada listelenmeyen bir hatayı bildirmek istiyorsanız, [bir destek isteği açın](get-support.md).

Intune için yeni bir özellik talep etmek istiyorsanız, [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) sitemizde bir rapor doldurabilirsiniz.

## <a name="migration"></a>Geçiş

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Geçiş sırasında Intune tarafından oluşturulan gruplar diğer Microsoft ürünlerinin işlevlerini etkileyebilir

Klasik Intune'dan Azure’a geçiş yaptığınızda **Tüm Kullanıcılar - b0b08746-4dbe-4a37-9adf-9e7652c0b421** adlı yeni bir grup görebilirsiniz. Bu grupta yalnızca Intune lisanslı kullanıcılar değil Azure Active Directory'niz içindeki tüm kullanıcılar bulunur. Mevcut kullanıcılardan bazılarının veya yeni kullanıcıların herhangi bir gruba üye olmamasını bekliyorsanız bu kullanım diğer Microsoft ürünlerinde sorunlara neden olabilir.

### <a name="secondary-migration-required-for-select-capabilities"></a>Seçilen özellikler için gerekli ikincil geçiş

Ocak 2017’den önce oluşturulan Intune hesaplarının, bu özelliklerin Azure portalında kullanılabilmesi için geçişi yapılmalıdır:

- Şirket Cihaz Kayıt profilleri
- Apple Cihaz Kaydı Programı
- iOS seri numarası grubuna göre şirketin önceden kayıtlı cihazları
- Cihaz Kayıt Yöneticileri
- Apple Volume Purchase Program

Bu özellikler hem klasik Silverlight hem Azure konsolları tarafından yönetilemediğinden, geçiş işlemi:
- Bunları klasik konsolda devre dışı bırakır
- Azure konsolunda etkinleştirir.  

Artık Intune özelliklerini Azure portalında yönetiyorsanız aşağıdaki hususları göz önünde bulundurun:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Apple DEP’te varsayılan Kurumsal Cihaz Kaydı profillerini kaldırır
Azure Portalı, Apple Aygıt Kayıt Programı (DEP) cihazları için varsayılan bir Şirket Cihaz Kaydı profilini desteklemez. Klasik Silverlight Intune konsolunda sağlanan bu işlevsellik, profillerin yanlışlıkla atanmasını önlemek için kullanımdan kaldırılmıştır. Azure Portalı'nda DEP seri numaraları eşitlenirken, Şirket Cihaz Kaydı profili atanmaz. Cihaz kullanılmadan önce bir kayıt profili atanmalıdır.

#### <a name="apple-dep-token-restored-with-migration"></a>Apple DEP belirtecinin geçiş ile geri yüklenmesi

Intune klasik (Silverlight) portalında Apple Aygıt Kayıt Programı belirtecini sildiyseniz ve Azure portalına yeni bir belirteç yüklemezseniz geçiş yaptığınızda özgün belirteç Azure portalına geri yüklenir. Bu belirteci kaldırmak ve DEP kaydını önlemek için belirteci Azure portalından silin.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Geçirilen ilkeler için durum dikey pencereleri çalışmıyor

Azure portalındaki klasik portaldan geçirilen ilkeler için durum bilgilerini görüntüleyemezsiniz. Ancak, bu ilkeler için raporları Klasik portalda görüntülemeye devam edebilirsiniz.
Geçirilen yapılandırma ilkelerinin durum bilgilerini görüntülemek için bunları Azure portalında yeniden oluşturun.

## <a name="apps"></a>Uygulamalar

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>iOS toplu satın alınan uygulamaları, yalnızca varsayılan Intune kiracı dilinde bulunuyor
iOS toplu satın alınan uygulamaları, yalnızca Intune hesabınız ile aynı ülke kodunda görüntülenir ve atanabilir. Intune yalnızca Intune kiracı hesabı ülke kodu ile aynı iTunes bölgesindeki uygulamaları eşitler. Örneğin, yalnızca ABD mağazasında bulunan bir uygulamayı satın alırsanız ancak Intune hesabınız Almanca ise Intune bu uygulamayı göstermez.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Aynı iOS toplu satın alınan programının birden fazla kopyası karşıya yükleniyor
Aynı VPP belirteci için **Karşıya Yükle** düğmesine birden çok kez tıklamayın. Bu, yinelenen VPP belirteçlerinin karşıya yüklenmesine ve uygulamaların aynı VPP belirteci için birden çok kez eşitlenmesine neden olur. 

<!-- ## Groups -->

## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Bazı cihazlar için bir Windows Bilgi Koruması İlkesi kaydedilemiyor

Intune'a kayıtlı olmayan cihazlarda, bir Windows Bilgi Koruması ilkesi için ayarlardaki **Şirket Tanıma** alanında yalnızca birincil bir etki alanı belirtebilirsiniz.
Ek etki alanları eklerseniz (**Gelişmiş ayarlar** > **Ağ çevresi** > **Korumalı bir etki alanı ekle** kullanarak), ilkeyi kaydedemezsiniz. Gördüğünüz hata iletisi yakında daha doğru hale getirilecektir.

### <a name="cisco-anyconnect-vpn-client-support"></a>Cisco AnyConnect VPN istemci desteği
 
Cisco AnyConnect VPN istemcisinin en son sürümü (4.0.07072) şu anda Intune ile uyumlu değildir. Intune'un gelecekteki bir güncelleştirmesi, bu VPN istemci sürümüyle uyumluluğu içerecektir. O zamana kadar Cisco AnyConnect VPN istemcinizi güncelleştirmemenizi ve mevcut sürümü kullanmaya devam etmenizi öneririz.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>macOS Sierra cihazlarda sayısal parola türü kullanma

Şu anda, macOS Sierra cihazlar için bir cihaz kısıtlama profilinde **Sayısal** **Gerekli parola türü**’nü seçerseniz, **Alfasayısal** olarak uygulanır. Bu aygıtlar ile sayısal bir parola kullanmak istiyorsanız, bu ayarı yapılandırmayın.
Bu sorun, macOS’un gelecek bir sürümünde düzeltilebilir.

Bu ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune’da macOS cihaz kısıtlama ayarları](device-restrictions-macos.md).

## <a name="compliance"></a>Uyumluluk

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Intune'daki uyumluluk ilkeleri yeni konsolda gösterilmez

Klasik portalda oluşturduğunuz uyumluluk ilkeleri geçirilir, ancak Azure portalındaki tasarım değişiklikleri nedeniyle Azure portalında görüntülenmez. Klasik Intune portalında oluşturduğunuz uyumluluk ilkeleri uygulanmaya devam eder ancak bunları klasik Intune portalında görüntülemeniz ve düzenlemeniz gerekir.
Ayrıca Azure portalında oluşturduğunuz yeni uyumluluk ilkeleri klasik Intune portalında görünmez.

Daha fazla bilgi için bkz. [Cihaz uyumluluğu nedir?](device-compliance.md)

<!-- ## Enrollment -->


<!-- ## Data protection -->


## <a name="administration-and-accounts"></a>Yönetim ve hesaplar

Genel Yöneticiler (Kiracı Yöneticileri olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebilir. Ancak, kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterlerse bir Intune veya EMS lisansına ihtiyaçları olur.

<!-- ## Additional items -->












 
