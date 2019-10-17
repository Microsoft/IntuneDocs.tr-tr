---
title: Hızlı Başlangıç - iOS için bir e-posta cihaz profili oluşturma
titleSuffix: Microsoft Intune
description: iOS cihazlarının şirket e-postasına güvenli bir şekilde bağlanabilmesi için bir e-posta cihaz profili oluşturmak üzere Microsoft Intune kullanmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: b4890410f5948cdc9bd1c6e3d85125d8e0713d9b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492321"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Hızlı Başlangıç: iOS için bir e-posta cihaz profili oluşturma

Bu hızlı başlangıçta iOS cihazları için e-posta cihaz profili oluşturmayı göreceksiniz. Bu profil, iOS cihazındaki yerleşik e-posta uygulamasının şirket e-postasına bağlanması için gerekli olan ayarları belirler. E-posta cihaz profilleri cihaz ayarlarını standartlaştırır ve son kullanıcıların kişisel cihazlarında şirket e-postasına bir kurulum yapmaları gerekmeden erişmelerini sağlar. E-postanızı daha fazla korumak için bir e-posta profili kullanarak cihazların uyumlu olup olmadığını belirleyebilir ve sonra yalnızca uyumlu cihazların e-postaya erişmesine izin vermek üzere koşullu erişim ayarlayabilirsiniz. E-posta profilleri hakkında bilgi için bkz. [Microsoft Intune'da e-posta ayarlarını yapılandırma](email-settings-configure.md)

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-an-ios-email-profile"></a>iOS e-posta profili oluşturma
1. Intune'da **Cihaz yapılandırması**'nı, ardından **Profiller**'i seçin.
2. **Profil Oluştur**'u seçin.
   
   ![iOS için e-posta profili oluşturma](./media/quickstart-email-profile/ios-create-profile.png)

3. **Ad**'ın altına yeni profil için açıklayıcı bir ad girin. Bu örnekte **iOS iş e-postası iste** girin.
4. Aşağıdaki profil bilgilerini girin:
   - **Açıklama** için **iOS cihazlarından iş e-postasını kullanmalarını iste** girin.
   - **Platform** olarak **iOS**’u seçin.
   - **Profil türü** için **E-posta**'yı seçin.
    
     ![İOS ile kullanmak için bir e-posta profili oluşturma](./media/quickstart-email-profile/ios-email-profile-name.png)

5. **Ayarlar**'ı seçin ve aşağıdaki ayarları girin (diğer ayarlarda varsayılanları bırakın):
   - **E-posta sunucusu**: Bu hızlı başlangıç için **outlook.office365.com** girin. Bu ayar, iOS mail uygulamasında e-postaya bağlanmak için kullanılacak e-posta sunucusunun Exchange konumunu (URL) belirtir.
   - **Hesap adı**: girin **şirket e-posta**.
   - **AAD'den kullanıcı adı özniteliği**: Bu ad, Intune'un Azure Active Directory'den (Azure AD) aldığı özniteliktir. Intune, bu profilin kullanıcı adını bu adı kullanarak dinamik olarak oluşturur. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nın profilin kullanıcı adı olarak kullanılmasını istediğimizi (örneğin user1@contoso.com) varsayacağız.
   - **AAD'den e-posta adresi özniteliği**: Bu ayar Exchange'de oturum açmak için kullanılacak Azure AD e-posta adresidir. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nı seçin.
   - **Kimlik doğrulama yöntemi**: Bu hızlı başlangıçta **Kullanıcı adı ve parola**'yı seçin. (Önceden Intune için bir sertifika ayarladıysanız **Sertifika**'yı da seçebilirsiniz.)
    
     ![İOS kullanımı için bir e-posta profili oluşturma](./media/quickstart-email-profile/ios-email-profile.png)

6. **Tamam**’ı seçin.
7. **Oluştur**’u seçin. Yeni profil, iOS cihazlarına ve kullanıcılarına nasıl atandığını izleyebilmeniz için görüntülenen panodaki profil listesinde görünür.
8. **Atamalar**’ı seçin.
9. **Dahil et** sekmesini, ardından **Tüm Kullanıcılar ve Tüm Cihazlar**'ı seçin. 
10. **Kaydet**’i seçin.

## <a name="clean-up-resources"></a>Kaynakları temizleme
Oluşturulan profili ek öğreticiler veya testler için kullanmayı düşünmüyorsanız silebilirsiniz.
1. Intune'da **Cihaz yapılandırması**'nı, ardından **Profiller**'i seçin.
2. Oluşturduğunuz **iOS iş e-postası iste** adlı test profilini seçin.
3. Profilin yanındaki üç nokta simgesini ( **...** ) ve ardından **Sil**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iOS cihazları için bir e-posta profili oluşturdunuz. Artık bu profili, profile uymayan tüm iOS cihazlarını uyumsuz olarak işaretleyen bir uyumluluk ilkesi oluşturarak bir iOS cihazının uyumlu olup olmadığını belirlemek için kullanabilirsiniz. Daha fazla koruma için, uyumsuz iOS cihazlarının e-postaya erişimini engelleyen bir koşullu erişim ilkesi oluşturabilirsiniz. Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

> [!div class="nextstepaction"]
> [Öğretici: Yönetilen cihazlarda Exchange Online e-postalarını koruma](../tutorial-protect-email-on-enrolled-devices.md)
