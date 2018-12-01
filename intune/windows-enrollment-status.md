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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b953ea281ad785d8a0ce7bee4b0f6d420b785dd9
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52729050"
---
# <a name="set-up-an-enrollment-status-page"></a>Kayıt durum sayfası ayarlama
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Cihaz kurulumu sırasında, Kayıt Durumu Sayfası cihazdaki yükleme bilgilerini görüntüler. Bir kullanıcı ilk kaydı tamamlayıp cihazda oturum açtığında bazı uygulama, profil ve sertifikalar henüz yüklenmemiş olabilir. Kayıt durumu sayfası, kullanıcıların cihaz kurulumu sırasında cihazlarının durumunu anlamasına yardımcı olabilir. Kayıt durumu sayfası için birden çok profil oluşturabilir ve bunları farklı gruplara uygulayabilirsiniz. Profiller, şunları yapacak şekilde ayarlanabilir:
- Yüklemenin ilerleme durumunu görüntüleme.
- Yükleme tamamlanana kadar kullanımı engelleme.
- Cihaz kurulumu başarısız olursa kullanıcının ne yapabileceğini belirtme.

Aynı kullanıcı veya cihazdaki farklı profil atamaları arasında oluşabilecek çakışmaların önüne geçmek amacıyla her bir profil için öncelik sırasını da ayarlayabilirsiniz.

 
## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>Tüm kullanıcılar için varsayılan kayıt durumu sayfasını etkinleştirme

Kayıt durumu sayfasını açmak için aşağıdaki adımları izleyin.
 
1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)**’yi seçin.
2. **Kayıt Durumu Sayfası** dikey penceresinde, **Varsayılan** > **Ayarlar**’ı seçin.
3. **Uygulama ve profil yükleme ilerleyişini göster** için **Evet**’i seçin.
4. Açmak istediğiniz diğer ayarları seçin ve **Kaydet**’i seçin.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Kayıt durumu sayfası profili oluşturma ve bunu bir gruba atama

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)** > **Profil oluştur**’u seçin.
2. Bir **Ad** ve **Açıklama** sağlayın.
3. **Oluştur**’u seçin.
4. **Kayıt Durumu Sayfası** listesinde yeni profili seçin.
5. **Atamalar** > **Grup seçin** > bu profili benimsemesini istediğiniz grupları seçin > **Seç** > **Kaydet**’i seçin.
6. **Ayarlar** > bu profile uygulamak istediğiniz ayarları seçin > **Kaydet**’i seçin.

## <a name="set-the-enrollment-status-page-priority"></a>Kayıt durumu sayfası önceliğini ayarlama

Bir cihaz veya kullanıcı, birden fazla grupta bulunabilir ve birden fazla kayıt durumu sayfası profiline sahip olabilir. Bu gibi çakışmaları ele almak için her bir profile yönelik öncelikleri ayarlayabilirsiniz. Bir kişi birden çok kayıt durumu sayfa profiline sahipse yalnızca en yüksek önceliğe sahip profil uygulanır.

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)**’yi seçin.
2. Listede profilin üzerine gelin.
3. Üç dikey noktayı kullanarak, profili listede dilediğiniz konuma sürükleyin.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Belirli bir uygulama bir cihaza erişimi engelleme yüklenir

Hangi uygulamaların kullanıcının masaüstü erişebilmeniz için önce yüklenmesi gereken belirtebilirsiniz.

1. Intune'da, **cihaz kaydı** > **Windows kayıt** > **kayıt durumu sayfası (Önizleme)**.
2. Bir profili seçin > **ayarları**.
3. Seçin **Evet** için **Göster uygulama ve profil yükleme ilerleme durumu**.
4. Seçin **Evet** için **tüm uygulamalar ve Profiller yüklenene kadar cihaz kullanımını engelle**.
5. Seçin **seçili** için **bu uygulamaları yüklü kullanıcı/cihaz atanmışsa gerekli kadar cihaz kullanımını engelle**.
 6. Seçin **uygulamaları Seç** > uygulamalar'ı seçin > **seçin** > **Kaydet**.

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
- Bağlantı profilleri
    - **Tüm Cihazlar**’a atanmış VPN veya Wi-Fi profilleri veya kaydedilen cihazın üyesi olduğu bir cihaz grubu (yalnızca Autopilot cihazları için)
- **Tüm Cihazlar**’a atanmış sertifika profilleri veya kaydedilen cihazın üyesi olduğu bir cihaz grubu (yalnızca Autopilot cihazları için)

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
