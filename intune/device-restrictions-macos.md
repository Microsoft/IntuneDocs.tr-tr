---
title: "macOS için Microsoft Intune cihaz kısıtlama ayarları"
titlesuffix: 
description: "macOS çalıştıran cihazlarda cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 72c9036bd6062e719d55876d77f44123fe2af392
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-macos-device-restriction-settings"></a>Microsoft Intune macOS cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makalede, macOS çalıştıran cihazlar için yapılandırabileceğiniz Microsoft Intune cihaz kısıtlama ayarları gösterilir.

## <a name="password"></a>Parola
-   **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Gerekli parola türü** - Parolanın yalnızca Sayısal olabileceğini ya da Alfasayısal (harfler ve sayılar içeren) olması gerektiğini belirtin. Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.
    -   **Paroladaki alfasayısal olmayan karakter sayısı** - Parolada bulunması gereken karmaşık karakterlerin sayısını belirtin (**0** ile **4** arasında).<br>Karmaşık bir karakter, “**?**” gibi bir simgedir.
    -   **En az parola uzunluğu** - Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (**4** ile **16** karakter arasında).
    -   **Basit parolalar** - **0000** veya **1234** gibi basit parolaların kullanımına izin verin.
    -   **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı** - Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.
    -   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran kilitlenmeden önce bilgisayarın boşta bekleyeceği süreyi belirtin.
    -   **Parola kullanım süresi (gün)** - Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1** ile **255** gün arasında).
    -   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin (**1** ile **24** arasında).

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- **Yasak uygulamalar** listesi - Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin. Kullanıcıların izin verilmeyen uygulamaları yüklemesi engellenmez, ancak yüklemeleri durumunda bu size bildirilir.
- **Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların izin verilmeyen uygulamaları yüklemesi engellenmez, ancak yüklemeleri durumunda bu size bildirilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra tercih ettiğiniz bir adı (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın paket kimliğini (örneğin *com.apple.calculator*) belirtin.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

**E-posta Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Kullanıcılar, yapılandırdığınız etki alanı dışındaki bir etki alanından e-posta aldığında, bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

