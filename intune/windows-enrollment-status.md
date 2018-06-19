---
title: Kayıt durum sayfası ayarlama
titleSuffix: Microsoft Intune
description: Windows 10 cihaz kaydeden kullanıcılarınızı selamlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235637"
---
# <a name="set-up-an-enrollment-status-page"></a>Kayıt durum sayfası ayarlama
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Cihaz kurulumu sırasında, kayıt durumu sayfası son kullanıcının cihazında yükleme durumunu görüntüler. Bir kullanıcı kaydedildiğinde bazı uygulamalar, profiller ve sertifikalar tamamen yüklenmemiş olabilir. Durum sayfası, kullanıcıların kayıt sırasında ve sonrasında cihazlarının durumunu anlamasına yardımcı olabilir. Tüm kullanıcılarınız için durum sayfasını açabilir ve kullanıcıların tüm atanan uygulamalar ve profiller yüklenene kadar cihazı kullanmasını engelleyebilirsiniz.
 
Tüm son kullanıcılarınız için kayıt durumu sayfasını açmak için aşağıdaki adımları izleyin.
 
1.  [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)**’yi seçin.
2.  **Kayıt Durumu Sayfası** dikey penceresinde, **Varsayılan** > **Ayarlar**’ı seçin.
3.  **Uygulama ve profil yükleme ilerleyişini göster** için **Evet**’i seçin.
4.  Açmak istediğiniz diğer ayarları seçin ve **Kaydet**’i seçin.
 
## <a name="enrollment-status-page-tracking-information"></a>Kayıt durumu sayfası izleme bilgileri

Durum sayfası; cihaz hazırlığı, cihaz kurulumu ve hesap kurulumu için bilgileri izler.

### <a name="device-preparation"></a>Cihaz hazırlığı

Cihaz hazırlığı için kayıt durumu sayfası, Güvenilir Platform Modülü (TPM) anahtar kanıtlamalarını (geçerli olduğunda), Azure Active Directory’ye katılma ilerleyişini ve Intune’a kaydolmayı izler.

### <a name="device-setup"></a>Cihaz kurulumu

Cihaz kurulumu için kayıt durumu sayfası, Tüm Cihazlar’a atandıysa şu öğeleri izler:
- Güvenlik ilkeleri
    - Tüm kayıtlar için tek bir yapılandırma hizmeti sağlayıcısı (CSP).
    - Intune tarafından yapılandırılan gerçek CSP’ler burada izlenmez.
- Uygulamalar
    - Makine başına iş kolu (LoB) MSI uygulamaları.
    - Yükleme bağlamı ile LoB mağaza uygulamaları = Cihaz.
    - Yükleme bağlamı ile çevrimdışı mağaza ve LoB mağaza uygulamaları = Cihaz.
- Bağlantı profilleri (VPN ve Wi-Fi) henüz izlenmiyor, bu nedenle bunlar her zaman "0/ 0" olarak belirtilir.
- Sertifikalar henüz izlenmiyor, bu nedenle bunlar her zaman “0/0” olarak belirtilir.

### <a name="account-setup"></a>Hesap kurulumu
Hesap kurulumu için kayıt durumu sayfası şu öğeleri izler:
- Güvenlik ilkeleri
    - Tüm kayıtlar için tek CSP.
    - Intune tarafından yapılandırılan gerçek CSP’ler burada izlenmez.
- Uygulamalar
    - Tüm Cihazlar, Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan kullanıcı başına LoB MSI uygulamaları.
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan makine başına LoB MSI uygulamaları.
    - Tüm Cihazlar, Tüm Kullanıcılar veya cihazı kaydeden kullanıcının yükleme bağlamı ile üyesi olduğu bir kullanıcı grubuna atanan LoB mağaza uygulamaları = Kullanıcı.
    - Tüm Cihazlar, Tüm Kullanıcılar veya cihazı kaydeden kullanıcının yükleme bağlamı ile üyesi olduğu bir kullanıcı grubuna atanan çevrimiçi mağaza uygulamaları = Kullanıcı.
    - Tüm Cihazlar, Tüm Kullanıcılar veya cihazı kaydeden kullanıcının yükleme bağlamı ile üyesi olduğu bir kullanıcı grubuna atanan çevrimdışı mağaza uygulamaları = Kullanıcı.
- Bağlantı profilleri
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan VPN veya Wi-Fi profilleri.
- Sertifikalar
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan sertifika profilleri.

## <a name="next-steps"></a>Sonraki adımlar
Windows kayıt sayfalarını ayarladıktan sonra, Windows cihazlarını nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)