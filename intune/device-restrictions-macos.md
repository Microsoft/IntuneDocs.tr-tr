---
title: "macOS için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "MacOS cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 716ca0a2041bdd2ecfadd180999a09f80373cb2a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da macOS cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu ayarları macOS cihazlarını bir cihaz kısıtlama profilinde yönetmek için kullanın.

## <a name="password"></a>Parola
-   **Parola gerekli** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Gerekli parola türü** - Parolanın yalnızca Sayısal olabileceğini ya da Alfasayısal (harfler ve sayılar içeren) olması gerektiğini belirtin. Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.
    -   **Paroladaki alfasayısal olmayan karakter sayısı** - Parolada bulunması gereken karmaşık karakterlerin sayısını belirtin (**0** ile **4** arasında).<br>Karmaşık bir karakter, **?** gibi bir simgedir
    -   **En az parola uzunluğu** - Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (**4** ile **16** karakter arasında).
    -   **Basit parolalar** - **0000** veya **1234** gibi basit parolaların kullanımına izin verin.
    -   **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı** - Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.
    -   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran kilitlenmeden önce bilgisayarın boşta bekleyeceği süreyi belirtin.
    -   **Parola kullanım süresi (gün)** - Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1** ile **255** gün arasında).
    -   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin (**1** ile **24** arasında).

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

**Yasak uygulamalar** listesi - Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.
**Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra tercih ettiğiniz bir adı (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın paket kimliğini (örneğin *com.apple.calculator*) belirtin.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

**E-posta Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, yapılandırdığınız etki alanı dışındaki bir etki alanından e-posta aldığında, bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

