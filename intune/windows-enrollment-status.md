---
title: Kayıt durum sayfası ayarlama
titleSuffix: Microsoft Intune
description: Windows 10 cihazlarını kaydeden kullanıcılar için karşılama sayfası ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d19be73472aed6b6ede1cfdc3d14007c5222c43
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896621"
---
# <a name="set-up-an-enrollment-status-page"></a>Kayıt durum sayfası ayarlama
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Intune ile cihaz kurulumu sırasında, Kayıt Durumu Sayfası cihazdaki yükleme bilgilerini görüntüler. Bir kullanıcı ilk kaydı tamamlayıp cihazda oturum açtığında bazı uygulama, profil ve sertifikalar henüz yüklenmemiş olabilir. Kayıt durumu sayfası, kullanıcıların cihaz kurulumu sırasında cihazlarının durumunu anlamasına yardımcı olabilir. Kayıt durumu sayfası için birden çok profil oluşturabilir ve bunları farklı gruplara uygulayabilirsiniz. Profiller, şunları yapacak şekilde ayarlanabilir:
- Yüklemenin ilerleme durumunu görüntüleme.
- Yükleme tamamlanana kadar kullanımı engelleme.
- Cihaz kurulumu başarısız olursa kullanıcının ne yapabileceğini belirtme.

Aynı kullanıcı veya cihazdaki farklı profil atamaları arasında oluşabilecek çakışmaların önüne geçmek amacıyla her bir profil için öncelik sırasını da ayarlayabilirsiniz.

> [!NOTE]
> Yalnızca cihazın bir atanmış grupta olması halinde Kayıt durumu sayfası görüntülenmez. Kayıt durumu sayfasının görüntülenmesi için kullanıcının atanmış grupta olması gerekir.

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

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Belirli bir uygulama yüklenene kadar cihaz erişimini engelleme

Kullanıcının masaüstüne erişebilmesi için yüklenmesi gereken uygulamaları belirtebilirsiniz.

1. Intune'da **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)** yolunu izleyin.
2. Bir profil seçip **Ayarlar**'a tıklayın.
3. **Uygulama ve profil yükleme ilerleyişini göster** için **Evet**'i seçin.
4. **Tüm uygulamalar ve profiller yüklenene kadar cihaz kullanımını engelle** için **Evet**'i seçin.
5. **Bu gerekli uygulamalar kullanıcıya/cihaza atanmışsa uygulamalar yüklenene kadar cihaz kullanımını engelle** için **Seçili**'yi belirleyin.
 6. **Uygulama seç**'e tıklayın, uygulamaları seçin ve **Seç** > **Kaydet** yolunu izleyin.

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
