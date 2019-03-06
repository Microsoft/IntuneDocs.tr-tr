---
title: Jamf cihazları için cihaz uyumluluk İlkesi | Microsoft Intune
titlesuffix: Microsoft Intune
description: Jamf tarafından yönetilen cihazların güvenliğine yardımcı olmak için Microsoft Intune uyumluluk ilkelerini Azure Active Directory koşullu erişimiyle birlikte kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4c6e420134461ef5165255703b8cafa0bdb71d7
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393319"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Jamf Pro ile yönetilen Mac bilgisayarları üzerinde uyumluluğu zorla

Uygulama hedefi: Azure portalında Intune

Azure Active Directory'yi ve Microsoft Intune koşullu erişim ilkelerini son kullanıcılarınızın kuruluş gereksinimleriyle uyumlu olmasını sağladığından emin olmak için kullanabilirsin. Bu politikaları, [Jamf Pro](conditional-access-integrate-jamf.md) ile yönetilen Mac'lere uygulayabilirsiniz. Bu hem Intune hem de Jamf Pro konsollarına erişim gerektirir.

## <a name="set-up-device-compliance-policies-in-intune"></a>Intune'da cihaz uyumu politikaları oluşturma

1. Microsoft Azure'ı açın, ardından **Intune** > **Cihaz Uyumluluğu** > **İlkeleri**’ne gidin. Uyumsuz kullanıcılara ve gruplara bir dizi eylem (örneğin, uyarı e-postaları gönderme) de dahil olmak üzere, macOS için ilkeler oluşturabilirsiniz.
2. İstediğiniz grupları arayın, ardından ilkeleri onlara uygulayın.

> [!Note]
> Intune, uyumlu olmak için tam disk şifrelemesi gerektirir.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Jamf Pro'da macOS için Şirket Portalı uygulamasını dağıtma

Aşağıdaki yordamı izlemeli ve Jamf Pro'da macOS için Şirket Portalı uygulamasını arka plan yüklemesi olarak dağıtmalısınız:

1. macOS cihazda, [macOS için Şirket Portalı uygulamasının](https://go.microsoft.com/fwlink/?linkid=862280) güncel sürümünü indirin. Uygulamayı yüklemeyin; uygulamanın Jamf Pro'ya yüklenecek bir kopyasına ihtiyacınız vardır.
2. Jamf Pro açın ve **Bilgisayar Yönetimi** > **Paketleri**’ne gidin.
3. MacOS için Şirket Portalı uygulamasıyla yeni bir paket oluşturun, ardından **Kaydet**'e tıklayın.
4. **Bilgisayarlar** > **İlkeler** ve ardından **Yeni**’yi seçin.
5. **Genel** yükünü kullanarak ilkenin ayarlarını yapılandırın. Bu ayarlar şöyle olmalıdır:
   - Tetikleyici: **Kayıt Tamamlandı** ve **Yinelenen İade Etme**'yi seçin
   - Yürütme Sıklığı: **Bilgisayar başına bir kez**'i seçin
6. **Paketler** yükünü seçin ve **Yapılandır**'ı tıklayın.
7. Şirket Portalı uygulamasıyla paketi seçmek için **Ekle**'yi tıklayın.
8. **Eylem** açılır menüsünden **Yükle**'yi seçin.
9. Paket için ayarları yapılandırın.
10. Şirket Portalı uygulamasının hangi bilgisayarlara yükleneceğini belirlemek için **Kapsam** sekmesini tıklayın. **Kaydet**’e tıklayın. Politika, seçilen bilgisayarda tetiklemenin bir sonraki seferinde kapsamlı cihazları çalıştırır ve **Genel** yükündeki kriterleri karşılar.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Kullanıcıların cihazlarını Azure Active Directory'ye kaydetmesini sağlamak için Jamf Pro'da bir ilke oluşturma

> [!NOTE]
> Bir sonraki adımlara geçmeden önce MacOS için [Şirket Portalı’nı dağıtmanız](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) gerekir.  

Son kullanıcılar, cihazı Jamf Pro tarafından yönetilen bir cihaz olarak Azure AD'ye kaydettirmek için Jamf Self Service aracılığıyla Şirket Portalı uygulamasını başlatmaları gerekir. Bu, son kullanıcılarınızın işlem yapmasını gerektirir. Son kullanıcılarınıza Jamf Self Service'te düğmeye tıklamalarını bildirmek için e-postayla, Jamf Pro bildirimleriyle veya başka herhangi bir yöntemle [son kullanıcınızla iletişim kurmanızı](end-user-educate.md) öneririz.

> [!WARNING]
> Cihaz kaydını başlatmak için, Şirket Portalı uygulamasının Jamf Self Service'ten başlatılması gerekir. <br><br>Şirket Portalı uygulamasının el ile başlatılması (örneğin, Uygulamalar veya İndirilenler klasörlerinden), cihazı kaydetmez. Son kullanıcı Şirket Portalı'nı el ile başlatırsa, 'AccountNotOnboarded' uyarısını görür.

1. Jamf Pro'da **Bilgisayarlar** >  **İlkeler**'e gidin ve cihaz kaydı için yeni bir ilke oluşturun.
2. Tetikleyici ve yürütme sıklığı da dahil olmak üzere **Microsoft Intune Tümleştirmesi** yükünü yapılandırın.
3. **Kapsam** sekmesine tıklayın ve ilkeyi hedeflenen tüm cihazlara göre kapsamlaştırın.
4. İlkeyi Jamf Self Servis'te sunmak için **Self Servis** sekmesine tıklayın. İlkeyi **Cihaz Uyumluluğu** kategorisine ekleyin. **Kaydet**’e tıklayın.

## <a name="removing-a-jamf-managed-device-from-intune"></a>Jamf ile yönetilen bir cihazı Intune’dan kaldırma

**Tüm cihazlar** görünümünde **Sil**’i seçerek Jamf tarafından yönetilen bir cihazı Intune konsolundan kaldırabilirsiniz. Toplu cihaz silme işlemi birden çok cihaz seçip **Sil**’e tıklayarak etkinleştirilebilir.

[Jamf ile yönetilen bir cihazı nasıl kaldıracağınız hakkında, Jamf Pro belgelerinden](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information) bilgi edinebilirsiniz. Daha fazla yardım için [Jamf destek](https://www.jamf.com/support/) ekibine bir destek bileti de gönderebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Azure Active Directory'de koşullu erişimi başlatma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
