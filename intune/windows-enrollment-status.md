---
title: Kayıt durum sayfası ayarlama
titleSuffix: Microsoft Intune
description: Windows 10 cihaz kaydeden kullanıcılarınızı selamlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5460db2d646d8bd417baa50d8188acbf69a251d
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48827998"
---
# <a name="set-up-an-enrollment-status-page"></a>Kayıt durum sayfası ayarlama
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Cihaz kurulumu sırasında, kayıt durumu sayfası cihazda yükleme bilgilerini görüntüler. Bir kullanıcı kaydedildiğinde bazı uygulamalar, profiller ve sertifikalar tamamen yüklenmemiş olabilir. Durum sayfası, kullanıcıların kayıt sırasında ve sonrasında cihazlarının durumunu anlamasına yardımcı olabilir. Durum sayfasını tüm kullanıcılarınız için etkinleştirebilir veya belirli kullanıcı gruplarını hedefleyen profiller oluşturabilirsiniz.  Yükleme ilerleme durumunu göstermek, yükleme tamamlanana kadar kullanımı engellemek ve sıfırlamalara izin vermek gibi işlemler için profiller ayarlayabilirsiniz.
 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Tüm kullanıcılar için varsayılan kayıt durumu sayfasını etkinleştirme

Tüm son kullanıcılarınız için kayıt durumu sayfasını açmak için aşağıdaki adımları izleyin.
 
1.  [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)**’yi seçin.
2.  **Kayıt Durumu Sayfası** dikey penceresinde, **Varsayılan** > **Ayarlar**’ı seçin.
3.  **Uygulama ve profil yükleme ilerleyişini göster** için **Evet**’i seçin.
4.  Açmak istediğiniz diğer ayarları seçin ve **Kaydet**’i seçin.

## <a name="create-enrollment-status-page-profile-to-target-specific-users"></a>Belirli kullanıcıları hedeflemek için kayıt durumu sayfası profili oluşturma

1.  [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)** > **Profil oluştur**’u seçin.
2. Bir **Ad** ve **Açıklama** sağlayın.
3. **Oluştur**’u seçin.
4. **Kayıt Durumu Sayfası** listesinde yeni profili seçin.
5. **Atamalar** > **Grup seçin** > bu profili benimsemesini istediğiniz grupları seçin > **Seç** > **Kaydet**’i seçin.
6. **Ayarlar** > bu profile uygulamak istediğiniz ayarları seçin > **Kaydet**’i seçin.


## <a name="enrollment-status-page-tracking-information"></a>Kayıt durumu sayfası izleme bilgileri

Durum sayfası; cihaz hazırlığı, cihaz kurulumu ve hesap kurulumu için bilgileri izler.

### <a name="device-preparation"></a>Cihaz hazırlığı

Cihaz hazırlığı için kayıt durumu sayfası, Güvenilir Platform Modülü (TPM) anahtar kanıtlamalarını (geçerli olduğunda), Azure Active Directory’ye katılma ilerleyişini ve Intune’a kaydolmayı izler.

### <a name="device-setup"></a>Cihaz kurulumu

Cihaz kurulumu için, kayıt durumu sayfası Tüm Cihazlar’a atandıysa şu öğeleri izler:
- Güvenlik ilkeleri
    - Tüm kayıtlar için tek bir yapılandırma hizmeti sağlayıcısı (CSP).
    - Intune tarafından yapılandırılan gerçek CSP’ler burada izlenmez.
- Uygulamalar
    - Makine başına iş kolu (LoB) MSI uygulamaları.
    - Yükleme bağlamı ile LoB mağaza uygulamaları = Cihaz.
    - Yükleme bağlamı ile çevrimdışı mağaza ve LoB mağaza uygulamaları = Cihaz.
- Bağlantı profilleri (VPN ve Wi-Fi) henüz izlenmiyor, bu nedenle bunlar her zaman "0/0" olarak belirtilir.
- Sertifikalar henüz izlenmiyor, bu nedenle bunlar her zaman "0/0" olarak belirtilir.

### <a name="account-setup"></a>Hesap kurulumu
Hesap kurulumu için kayıt durumu sayfası şu öğeleri izler:
- Güvenlik ilkeleri
    - Tüm kayıtlar için tek CSP.
    - Intune tarafından yapılandırılan gerçek CSP’ler burada izlenmez.
- Uygulamalar
    - Tüm Cihazlar, Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan kullanıcı başına LoB MSI uygulamaları.
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan makine başına LoB MSI uygulamaları.
    - Aşağıdakilerden birini atanan LoB mağaza uygulamaları, çevrimiçi mağaza uygulamaları ve çevrimdışı mağaza uygulamaları:
        - Tüm Cihazlar
        - Tüm Kullanıcılar
        - Cihazı kaydeden kullanıcının yükleme bağlamı Kullanıcı olarak ayarlanmış bir üye olduğu kullanıcı grubu.
- Bağlantı profilleri
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan VPN veya Wi-Fi profilleri.
- Sertifikalar
    - Tüm Kullanıcılar veya cihazı kaydeden kullanıcının üyesi olduğu bir kullanıcı grubuna atanan sertifika profilleri.

## <a name="next-steps"></a>Sonraki adımlar
Windows kayıt sayfalarını ayarladıktan sonra, Windows cihazlarını nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)