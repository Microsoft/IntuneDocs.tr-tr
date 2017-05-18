---
title: "E-posta senaryolarını koruma | Microsoft Docs"
description: "Birkaç örnek senaryo ve bunların koşullu erişimle nasıl gerçekleştirilebileceği konusunda bilgi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 7d0b9cee72e8810b4f39bd81bd8f49d0818618c4
ms.contentlocale: tr-tr
ms.lasthandoff: 05/04/2017


---

# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a>Microsoft Intune ile e-postaya erişimi koruma: Örnek senaryolar

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>1. Senaryo: Kullanıcıların Exchange Online’a erişmek için uyumsuz cihazlar kullanmasını engelleyin
### <a name="scenario-requirements"></a>Senaryo gereksinimleri
- **Muhasebe** Azure Active Directory güvenlik grubundaki tüm kullanıcıların, cihazlarının dağıttığınız bir uyumluluk ilkesiyle uyumlu olmaması durumunda Exchange Online’a erişimi engellenmelidir.
- Bu grupta cihazları Intune tarafından desteklenmeyen kullanıcılar varsa, bu kullanıcıların da o cihazda Exchange Online’a erişimi engellenmelidir.
- **Finans** Azure Active Directory güvenlik grubundaki tüm kullanıcılar, **Muhasebe** güvenlik grubunda da olsalar ilkeden muaf tutulmalıdır.

Bunu başarmak için, Exchange Online için aşağıdaki ayarlarla bir koşullu erişim ilkesi yapılandırın:

- **Koşullu erişimi etkinleştir ilkesini** seçin.

- Modern kimlik doğrulaması kullanan uygulamalardan erişime izin vermek istediğiniz platformları seçin.
- Exchange ActiveSync uygulamaları için, **Microsoft Intune tarafından desteklenmeyen platformlardaki uyumsuz cihazları engelle**’yi ve **Microsoft Intune tarafından desteklenmeyen platformlardaki tüm diğer cihazları engelle**’yi seçin.
-   **Hedeflenen grup** bölümündeki **Seçilen güvenlik grupları** altında **Muhasebe** kullanıcı grubunu seçin.

-   **Muaf tutulan grup** bölümündeki **Seçilen güvenlik grupları** altında **Finans** kullanıcı grubunu seçin.


Hangi cihazların Exchange Online’a erişebileceğine karar vermek için senaryoda aşağıdaki akış kullanılır:

![Cihaz erişim akışı](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>2. Senaryo: Şirket İçi Exchange’e erişen tüm iOS cihazları, Intune tarafından yönetilmelidir
### <a name="scenario-requirements"></a>Senaryo gereksinimleri
- Yalnızca iOS çalıştıran cihazların Şirket İçi Exchange’e erişmesine izin verilmelidir.
- Cihazların Exchange’e erişim için kullanılabilmeleri için önce Intune’a kaydolmaları ve uyumluluk ilkesi kurallarına uymaları da gerekir.

Bunu başarmak için, Şirket İçi Exchange için aşağıdaki ayarlarla bir koşullu erişim ilkesi yapılandırın:

-   **Cihaz uyumsuzsa veya Microsoft Intune'a kayıtlı değilse e-posta uygulamalarının Şirket İçi Exchange'e erişimini engelleyin** seçeneğini belirtin. Bu seçenek belirtildiğinde koşullu erişim ilkesini etkinleştirirsiniz. Bu ilke, tüm cihazların Exchange’e erişebilmeleri için önce Microsoft Intune’a kaydolmalarını ve uyumluluk ilkesi kurallarına uymalarını zorunlu tutar.

-   Gelişmiş Exchange Active Sync ayarları için şunları oluşturun:

  -   iOS çalıştıran cihazların Exchange’e erişmesine izin veren bir platform özel durumu.   

  -   Platform özel durum kuralının kapsamına girmeyen cihazın Exchange’e erişiminin engellenmesi gerektiğini belirten, varsayılan bir kural. Bu kural, iOS çalıştırmayan cihazların Exchange’e erişiminin engellenmesini sağlar.

Hangi cihazların Exchange’e erişebileceğine karar vermek için aşağıdaki akışı kullanırsınız:

![Cihaz erişim akışı](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>3. Senaryo: Hiçbir Android cihazı Şirket İçi Exchange’e erişemez
### <a name="scenario-requirements"></a>Senaryo gereksinimleri
- Tüm Android cihazlarının Exchange’e erişimi engellenmelidir.
- Desteklenen diğer tüm cihazlar, Intune tarafından yönetildikleri sürece Exchange’e erişebilir.

Bunu başarmak için, Şirket İçi Exchange için aşağıdaki ayarlarla bir koşullu erişim ilkesi yapılandırın:

-   **Cihaz uyumsuzsa veya Microsoft Intune'a kayıtlı değilse e-posta uygulamalarının Şirket İçi Exchange'e erişimini engelleyin** seçeneğini belirtin. Bu seçenek belirtildiğinde, tüm cihazların Intune’a kaydolmasını ve uyumluluk ilkesi kurallarına uymasını zorunlu tutmuş olursunuz.

- Gelişmiş Exchange Active Sync ayarları için şunları oluşturun:
  -   Android çalıştıran cihazların Exchange’e erişmesini engelleyen bir platform özel durumu. Bu kural, Exchange erişim için Android cihazlarının kullanılamamasını sağlar.

  -   Bir cihazın diğer kuralların kapsamında olmaması durumunda Exchange’e erişmesine izin verileceğini belirten bir varsayılan kural. Bu varsayılan kural, Android dışındaki platformları çalıştıran ama Microsoft Intune tarafından desteklenen cihazların Exchange’e erişmek için kullanılabilmesini sağlar. Öte yandan bunların Intune’a kaydolması ve uyumluluk ilkesi kurallarına uyması gerekir.

Hangi cihazların Exchange’e erişebileceğine karar vermek için aşağıdaki akışı kullanırsınız:

![Cihaz erişim akışı](./media/ConditionalAccess8-4.png)

