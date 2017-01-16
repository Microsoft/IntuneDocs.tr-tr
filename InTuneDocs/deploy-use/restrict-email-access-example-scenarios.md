---
title: "E-postaya erişimi kısıtlama örnek senaryoları | Microsoft Docs"
description: "Birkaç örnek senaryo ve bunların koşullu erişimle nasıl gerçekleştirilebileceği konusunda bilgi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2d6ead1495a64e4e215c49b14064e390065a06de


---

# <a name="restrict-access-to-email-with-microsoft-intune-example-scenarios"></a>Microsoft Intune ile e-postaya erişimi kısıtlama: Örnek senaryolar

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>1. Senaryo: Kullanıcıların Exchange Online’a erişmek için uyumsuz cihazlar kullanmasını engelleyin
### <a name="scenario-requirements"></a>Senaryo gereksinimleri
- **Muhasebe** Azure Active Directory güvenlik grubundaki tüm kullanıcıların, cihazlarının dağıttığınız bir uyumluluk ilkesiyle uyumlu olmaması durumunda Exchange Online’a erişimi engellenmelidir.
- Bu grupta cihazları [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından desteklenmeyen kullanıcılar varsa, bu kullanıcıların da o cihazda Exchange Online’a erişimi engellenmelidir.
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
- Desteklenen diğer tüm cihazlar, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından yönetildikleri sürece Exchange’e erişebilir.

Bunu başarmak için, Şirket İçi Exchange için aşağıdaki ayarlarla bir koşullu erişim ilkesi yapılandırın:

-   **Cihaz uyumsuzsa veya Microsoft Intune'a kayıtlı değilse e-posta uygulamalarının Şirket İçi Exchange'e erişimini engelleyin** seçeneğini belirtin. Bu seçenek belirtildiğinde, tüm cihazların Intune’a kaydolmasını ve uyumluluk ilkesi kurallarına uymasını zorunlu tutmuş olursunuz.

- Gelişmiş Exchange Active Sync ayarları için şunları oluşturun:
  -   Android çalıştıran cihazların Exchange’e erişmesini engelleyen bir platform özel durumu. Bu kural, Exchange erişim için Android cihazlarının kullanılamamasını sağlar.

  -   Bir cihazın diğer kuralların kapsamında olmaması durumunda Exchange’e erişmesine izin verileceğini belirten bir varsayılan kural. Bu varsayılan kural, Android dışındaki platformları çalıştıran ama Microsoft Intune tarafından desteklenen cihazların Exchange’e erişmek için kullanılabilmesini sağlar. Öte yandan bunların Intune’a kaydolması ve uyumluluk ilkesi kurallarına uyması gerekir.

Hangi cihazların Exchange’e erişebileceğine karar vermek için aşağıdaki akışı kullanırsınız:

![Cihaz erişim akışı](./media/ConditionalAccess8-4.png)



<!--HONumber=Dec16_HO2-->


