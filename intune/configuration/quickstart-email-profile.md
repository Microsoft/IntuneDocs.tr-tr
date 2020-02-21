---
title: Hızlı başlangıç-iOS/ıpados cihazları için bir e-posta cihaz profili oluşturma
titleSuffix: Microsoft Intune
description: İOS/ıpados cihazlarının şirket e-postasına güvenli bir şekilde bağlanabilmesi için bir e-posta cihaz profili oluşturmak üzere Microsoft Intune nasıl kullanacağınızı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/18/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af2576c44e0486dbd859a56896db3b7d0ffc6cff
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511077"
---
# <a name="quickstart-create-an-email-device-profile-for-iosipados"></a>Hızlı başlangıç: iOS/ıpados için bir e-posta cihaz profili oluşturma

Bu hızlı başlangıçta iOS/ıpados cihazları için bir e-posta cihaz profili oluşturma hakkında bilgi edineceksiniz. Bu profil, şirket e-postasına bağlanmak için iOS/ıpados cihazında yerleşik e-posta uygulaması için gerekli olan ayarları belirtir. E-posta cihaz profilleri cihaz ayarlarını standartlaştırır ve son kullanıcıların kişisel cihazlarında şirket e-postasına bir kurulum yapmaları gerekmeden erişmelerini sağlar. E-postanızı daha fazla korumak için bir e-posta profili kullanarak cihazların uyumlu olup olmadığını belirleyebilir ve sonra yalnızca uyumlu cihazların e-postaya erişmesine izin vermek üzere koşullu erişim ayarlayabilirsiniz. E-posta profilleri hakkında bilgi için bkz. [Microsoft Intune'da e-posta ayarlarını yapılandırma](email-settings-configure.md)

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) genel yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-an-iosipados-email-profile"></a>İOS/ıpados e-posta profili oluşturma

1. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

   ![Intune 'da iOS/ıpados için bir e-posta profili oluşturma](./media/quickstart-email-profile/ios-create-profile.png)

2. **Ad**'ın altına yeni profil için açıklayıcı bir ad girin. Bu örnekte **iOS iş e-postası iste** girin.
3. Aşağıdaki profil bilgilerini girin:
    - **Açıklama**için, **iş e-postasını kullanmak üzere IOS/ıpados cihazları gerektir**yazın.
    - **Platform**için **IOS/ıpados**' ı seçin.
    - **Profil türü** için **E-posta**'yı seçin.

        ![Intune 'da iOS/ıpados cihazları ile kullanmak için bir e-posta profili oluşturma](./media/quickstart-email-profile/ios-email-profile-name.png)

4. **Ayarlar**'ı seçin ve aşağıdaki ayarları girin (diğer ayarlarda varsayılanları bırakın):
   - **E-posta sunucusu**: Bu hızlı başlangıç için **outlook.office365.com** girin. Bu ayar, iOS/ıpados posta uygulamasının e-postaya bağlanmak için kullanacağı e-posta sunucusunun Exchange konumunu (URL) belirtir.
   - **Hesap adı**: girin **şirket e-posta**.
   - **AAD'den kullanıcı adı özniteliği**: Bu ad, Intune'un Azure Active Directory'den (Azure AD) aldığı özniteliktir. Intune, bu profilin kullanıcı adını bu adı kullanarak dinamik olarak oluşturur. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nın profilin kullanıcı adı olarak kullanılmasını istediğimizi (örneğin user1@contoso.com) varsayacağız.
   - **AAD'den e-posta adresi özniteliği**: Bu ayar Exchange'de oturum açmak için kullanılacak Azure AD e-posta adresidir. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nı seçin.
   - **Kimlik doğrulama yöntemi**: Bu hızlı başlangıçta **Kullanıcı adı ve parola**'yı seçin. (Önceden Intune için bir sertifika ayarladıysanız **Sertifika**'yı da seçebilirsiniz.)

        ![İOS/ıpados kullanımı için bir e-posta profili oluşturma](./media/quickstart-email-profile/ios-email-profile.png)

5. **Oluştur** > **Tamam ' ı** seçin. Yeni profil, panonun iOS/ıpados cihazlarına ve iOS/ıpados kullanıcılarına nasıl atandığını izleyebilmeniz için, pano görüntülenirken profiller listesinde görüntülenir.
6. **Atamalar**’ı seçin.
7. **Dahil et** sekmesini, ardından **Tüm Kullanıcılar ve Tüm Cihazlar**'ı seçin. 
8. **Kaydet**’i seçin.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Oluşturulan profili ek öğreticiler veya testler için kullanmayı düşünmüyorsanız silebilirsiniz.

1. Intune'da **Cihaz yapılandırması**'nı, ardından **Profiller**'i seçin.
2. Oluşturduğunuz test profilini, **iOS/ıpados için iş e-postası gerektir**' i seçin.
3. Profilin yanındaki üç nokta simgesini ( **...** ) ve ardından **Sil**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iOS/ıpados cihazları için bir e-posta profili oluşturdunuz. Artık bu profili, bir iOS/ıpados cihazının profille eşleşmeyen tüm iOS/ıpados aygıtlarını işaret eden bir uyumluluk ilkesi oluşturarak uyumlu olup olmadığını anlamak için kullanabilirsiniz. Daha fazla koruma için, uyumsuz iOS/ıpados cihazlarının e-postaya erişimini engelleyen bir koşullu erişim ilkesi oluşturabilirsiniz. Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

> [!div class="nextstepaction"]
> [Öğretici: Yönetilen cihazlarda Exchange Online e-postalarını koruma](../tutorial-protect-email-on-enrolled-devices.md)
