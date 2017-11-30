---
title: "Jamf tarafından yönetilen cihazlar için uyumluluk ilkelerini uygula"
titlesuffix: Azure portal
description: "Jamf tarafından yönetilen cihazların güvenliğini sağlamak için uyumluluk kullanın."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Jamf Pro ile yönetilen Mac bilgisayarları üzerinde uyumluluğu zorla

|Uygulama hedefi: Azure portalında Intune |
|--|
|Klasik portalda Intune hakkında belgeler mi arıyorsunuz? [Buraya gidin](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Şu anda özel olarak incelenmektedir|
|--|
|Bu konuda açıklanan özellikler, yalnızca şu anda önizlemede olan müşteriler tarafından kullanılabilir. Özellikler tüm müşterilerin kullanımına sunulduğunda bu ileti kaldırılacaktır.|
| |

Azure Active Directory'yi ve Microsoft Intune koşullu erişim ilkelerini son kullanıcılarınızın kuruluş gereksinimleriyle uyumlu olmasını sağladığından emin olmak için kullanabilirsin. Bu politikaları, [Jamf Pro](conditional-access-integrate-jamf.md) ile yönetilen Mac'lere uygulayabilirsiniz. Bu hem Intune hem de Jamf Pro konsollarına erişim gerektirir.

## <a name="set-up-device-compliance-policies-in-intune"></a>Intune'da cihaz uyumu politikaları oluşturma

1. Microsoft Azure'ı açın, ardından **Intune** > **Cihaz Uyumluluğu** > **İlkeleri**’ne gidin. Uyumsuz kullanıcılara ve gruplara bir dizi eylem (ör., uyarı e-postası gönderme) de dahil olmak üzere, macOS için ilkeler oluşturabilirsiniz.
2. İstediğiniz grupları arayın, ardından ilkeleri onlara uygulayın.

## <a name="require-the-company-portal-app-for-macos"></a>MacOS için Şirket Portalı uygulamasını gerektirir

1. MacOS aygıtta macOS için Şirket Portalı uygulaması geçerli sürümünü indirmek için https://aka.ms/macoscompanyportal adresine gidin.
2. Jamf Pro açın ve **Bilgisayar Yönetimi** > **Paketleri**’ne gidin.
3. MacOS için Şirket Portalı uygulamasıyla yeni bir paket oluşturun, ardından  **Kaydet** 'e tıklayın.
4. **Bilgisayarlar** > **İlkeler** ve ardından **Yeni**’yi seçin.
5. Tetikleme ve yürütme sıklığı da dahil olmak üzere ilke ayarlarını yapılandırmak için **Genel** yükünü kullanın.
6. **Paketler** yükünü seçin ve **Yapılandır**'ı tıklayın.
7. Şirket Portalı uygulamasıyla paketi seçmek için **Ekle**'yi tıklayın.
8. **Eylem** açılır menüsünden **Yükle**'yi seçin.
9. Paket için ayarları yapılandırın.
10. Şirket Portalı uygulamasının hangi bilgisayarlara yükleneceğini belirlemek için **Kapsam** sekmesini tıklayın. **Kaydet**'e tıklayın. Politika, seçilen bilgisayarda tetiklemenin bir sonraki seferinde kapsamlı cihazları çalıştırır ve **Genel** yükündeki kriterleri karşılar.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Kullanıcılarınızı Azure Active Directory ile Jamf Pro tarafından yönetilen cihazları kaydettirmeye yönlendirin

> [!NOTE]
> Bir sonraki adımlara geçmeden önce MacOS için [Şirket Portalı’nı dağıtmanız](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) gerekir.  

Son kullanıcılar, cihazı Jamf Pro tarafından yönetilen bir cihaz olarak Azure AD'ye kaydettirmek için Jamf Self Service aracılığıyla Şirket Portalı uygulamasını başlatmaları gerekir.

1. Jamf Pro'da **Bilgisayarlar** >  **İlkeler**'e gidin ve cihaz kaydı için yeni bir ilke oluşturun.
2. Tetikleyici ve uygulama frekansı da dahil olmak üzere **Koşullu Erişim** yükünü yapılandırın. Önceliği **Sonra** olarak belirleyin.
3. **Kapsam** sekmesine tıklayın ve ilkeyi hedeflenen tüm cihazlara göre kapsamlaştırın.
4. İlkeyi Jamf Self Servis'te sunmak için **Self Servis** sekmesine tıklayın. İlkeyi **Cihaz Uyumluluğu** kategorisine ekleyin. **Kaydet**'e tıklayın.
