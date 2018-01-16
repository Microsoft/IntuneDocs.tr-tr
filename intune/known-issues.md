---
title: "Azure portalında Microsoft Intune’da bilinen sorunlar"
titlesuffix: Azure portal
description: "Intune’da bilinen sorunlar hakkında okuyun\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5cdda6a34311bb7b70234ab046975e6ff5417878
ms.sourcegitcommit: cfe3607ba0b76a37a3c54f465754482d49a816a0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="known-issues-in-microsoft-intune"></a>Microsoft Intune’da bilinen sorunlar


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinmek için bu konuyu kullanın.

Burada listelenmeyen bir hatayı bildirmek istiyorsanız, [bir destek isteği açın](get-support.md).

Intune için yeni bir özellik talep etmek istiyorsanız, [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) sitemizde bir rapor doldurabilirsiniz.

## <a name="migration"></a>Geçiş

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Intune eski PC istemcisi özellikleri yalnızca Silverlight konsolunda bulunur

Azure Portal üzerinde Intune'da Windows 10'u yönetme özelliği, Windows MDM kaydıyla sağlanır. Daha fazla bilgi için bkz. [Azure konsolu ve eski Intune PC İstemcisi'ndeki Intune](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Geçiş sırasında Intune tarafından oluşturulan gruplar diğer Microsoft ürünlerinin işlevlerini etkileyebilir

Intune’dan Azure portalına geçiş yaptığınızda **Tüm Kullanıcılar - b0b08746-4dbe-4a37-9adf-9e7652c0b421** adlı yeni bir grup görebilirsiniz. Bu grupta yalnızca Intune lisanslı kullanıcılar değil Azure Active Directory'niz içindeki tüm kullanıcılar bulunur. Mevcut kullanıcılardan bazılarının veya yeni kullanıcıların herhangi bir gruba üye olmamasını bekliyorsanız bu kullanım diğer Microsoft ürünlerinde sorunlara neden olabilir.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Geçirilen ilkeler için durum dikey pencereleri çalışmıyor

Azure portalındaki klasik portaldan geçirilen ilkeler için durum bilgilerini görüntüleyemezsiniz. Ancak, bu ilkelerin raporlarını klasik portalda görüntülemeye devam edebilirsiniz. Geçirilen yapılandırma ilkelerinin durum bilgilerini görüntülemek için bunları Azure portalında yeniden oluşturun.

## <a name="apps"></a>Uygulamalar

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>iOS toplu satın alınan uygulamaları, yalnızca varsayılan Intune kiracı dilinde bulunuyor
iOS toplu satın alınan uygulamaları, yalnızca Intune hesabınız ile aynı ülke kodunda görüntülenir ve atanabilir. Intune yalnızca Intune kiracı hesabı ülke kodu ile aynı iTunes bölgesindeki uygulamaları eşitler. Örneğin, Intune hesabınız Almanca ise ve yalnızca ABD mağazasında bulunan bir uygulamayı satın alırsanız Intune bu uygulamayı göstermez.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Aynı iOS toplu satın alınan programının birden fazla kopyası karşıya yükleniyor
Aynı VPP belirteci için **Karşıya Yükle** düğmesine birden çok kez tıklamayın. Bu, yinelenen VPP belirteçlerinin karşıya yüklenmesine ve uygulamaların aynı VPP belirteci için birden çok kez eşitlenmesine neden olur.

### <a name="assigning-office-365-to-macos-devices"></a>macOS cihazlarına Office 365'i atama
Microsoft Intune'la macOS cihazlarına Office 365'i atama özelliği, kullanıcı arabirimi güncelleştirmemiz tamamlandıktan sonra kullanıma sunulacaktır.

<!-- ## Groups -->

## <a name="device-configuration"></a>Cihaz yapılandırması

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Bazı cihazlar için bir Windows Bilgi Koruması İlkesi kaydedilemiyor

Intune'a kayıtlı olmayan cihazlarda, bir Windows Bilgi Koruması ilkesi için ayarlardaki **Şirket Tanıma** alanında yalnızca birincil bir etki alanı belirtebilirsiniz.
Ek etki alanları eklerseniz (**Gelişmiş ayarlar** > **Ağ çevresi** > **Korumalı bir etki alanı ekle** kullanarak), ilkeyi kaydedemezsiniz. Gördüğünüz hata iletisi yakında daha doğru hale getirilecektir.

### <a name="cisco-anyconnect-vpn-client-support"></a>Cisco AnyConnect VPN istemci desteği

Cisco AnyConnect VPN istemcisinin en son sürümü (4.0.07072) şu anda Intune ile uyumlu değildir.
Intune'un gelecekteki bir güncelleştirmesi, bu VPN istemci sürümüyle uyumluluğu içerecektir. O zamana kadar Cisco AnyConnect VPN istemcinizi güncelleştirmemenizi ve mevcut sürümü kullanmaya devam etmenizi öneririz.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>macOS Sierra cihazlarda sayısal parola türü kullanma

Şu anda, macOS Sierra cihazlar için bir cihaz kısıtlama profilinde **Sayısal** **Gerekli parola türü**’nü seçerseniz, **Alfasayısal** olarak uygulanır. Bu aygıtlar ile sayısal bir parola kullanmak istiyorsanız, bu ayarı yapılandırmayın.
Bu sorun, macOS’un gelecek bir sürümünde düzeltilebilir.

Bu ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune’da macOS cihaz kısıtlama ayarları](device-restrictions-macos.md).

## <a name="compliance"></a>Uyumluluk

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Intune'daki uyumluluk ilkeleri yeni konsolda gösterilmez

Klasik portalda oluşturduğunuz uyumluluk ilkeleri geçirilir, ancak Azure portalındaki tasarım değişiklikleri nedeniyle Azure portalında görüntülenmez. Klasik Intune portalında oluşturduğunuz uyumluluk ilkeleri uygulanmaya devam eder ancak bunları klasik portalda görüntülemeniz ve düzenlemeniz gerekir.

Ayrıca Azure portalında oluşturduğunuz yeni uyumluluk ilkeleri klasik portalda görünmez.

Daha fazla bilgi için bkz. [Cihaz uyumluluğu nedir?](device-compliance.md)

<!-- ## Enrollment -->


## <a name="data-protection"></a>Veri koruma

### <a name="ios-app-protection-policies"></a>iOS uygulama koruma ilkeleri

Yönetilen cihazlardaki kullanıcılar için mevcut olan [iOS için uygulama koruma ilkelerini](app-protection-policy-settings-ios.md), kayıt gerekmeden mobil uygulama yönetimi (MAM) aracılığıyla tanımlayabilirsiniz. Geçici bir hata yüzünden bu ilkeleri birden çok değil, yalnızca tek ondalık ayırıcısı olan iOS sürümleri için tanımlayabilirsiniz. iOS’un en düşük sürümünü 10.3.1 olarak ayarlamak yerine iOS 10.3 şeklinde ayarlayabilirsiniz. Bu sorun, iOS SDK’sına yakında gelecek olan güncelleştirme ile çözülecektir.


## <a name="administration-and-accounts"></a>Yönetim ve hesaplar

Genel Yöneticiler (Kiracı Yöneticileri olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebilir. Ancak, kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterlerse bir Intune veya EMS lisansına ihtiyaçları olur.

<!-- ## Additional items -->
