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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b252c9d3d719847c8c0911b6cbce06c83bb4bf0e
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799291"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Hızlı Başlangıç: İOS için bir e-posta cihaz profili oluşturma

Bu hızlı başlangıçta iOS cihazları için e-posta cihaz profili oluşturmayı göreceksiniz. Bu profil, iOS cihazındaki yerleşik e-posta uygulamasının şirket e-postasına bağlanması için gerekli olan ayarları belirler. E-posta cihaz profilleri cihaz ayarlarını standartlaştırır ve son kullanıcıların kişisel cihazlarında şirket e-postasına bir kurulum yapmaları gerekmeden erişmelerini sağlar. E-postanızın güvenliğini daha da artırmak için cihazların uyumlu olup olmadığını belirlemek için bir e-posta profili kullanabilir, ondan sonra da e-postaya yalnızca uyumlu cihazların erişmesine izin vermek için koşullu erişim ayarlayabilirsiniz. E-posta profilleri hakkında bilgi için bkz. [Microsoft Intune'da e-posta ayarlarını yapılandırma](email-settings-configure.md)

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-an-ios-email-profile"></a>iOS e-posta profili oluşturma
1. Intune'da **Cihaz yapılandırması**'nı, ardından **Profiller**'i seçin.
2. **Profil Oluştur**'u seçin.
   
   ![iOS için e-posta profili oluşturma](media/quickstart-email-profile/ios-create-profile.png)

3. **Ad**'ın altına yeni profil için açıklayıcı bir ad girin. Bu örnekte **iOS iş e-postası iste** girin.
4. Aşağıdaki profil bilgilerini girin:
   - **Açıklama** için **iOS cihazlarından iş e-postasını kullanmalarını iste** girin.
   - **Platform** olarak **iOS**’u seçin.
   - **Profil türü** için **E-posta**'yı seçin.
    
     ![İOS ile kullanmak için bir e-posta profili oluşturma](media/quickstart-email-profile/ios-email-profile-name.png)

5. **Ayarlar**'ı seçin ve aşağıdaki ayarları girin (diğer ayarlarda varsayılanları bırakın):
   - **E-posta sunucusu**: Bu hızlı başlangıçta girin **outlook.office365.com**. Bu ayar, iOS mail uygulamasında e-postaya bağlanmak için kullanılacak e-posta sunucusunun Exchange konumunu (URL) belirtir.
   - **Hesap adı**: Girin **şirket e-posta**.
   - **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory'den (Azure AD) Intune alır özniteliğidir. Intune, bu profilin kullanıcı adını bu adı kullanarak dinamik olarak oluşturur. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nın profilin kullanıcı adı olarak kullanılmasını istediğimizi (örneğin user1@contoso.com) varsayacağız.
   - **Aad'den e-posta adresi özniteliği**: Bu ayar, Exchange'de oturum açmak için kullanılan Azure ad e-posta adresidir. Bu hızlı başlangıçta **Kullanıcı Asıl Adı**'nı seçin.
   - **Kimlik doğrulama yöntemi**: Bu hızlı başlangıçta seçin **kullanıcı adı ve parola**. (Önceden Intune için bir sertifika ayarladıysanız **Sertifika**'yı da seçebilirsiniz.)
    
     ![İOS kullanmak için bir e-posta profili oluşturma](media/quickstart-email-profile/ios-email-profile.png)

6. **Tamam**’ı seçin.
7. **Oluştur**’u seçin. Yeni profil, iOS cihazlarına ve kullanıcılarına nasıl atandığını izleyebilmeniz için görüntülenen panodaki profil listesinde görünür.
8. **Atamalar**’ı seçin.
9. **Dahil et** sekmesini, ardından **Tüm Kullanıcılar ve Tüm Cihazlar**'ı seçin. 
10. **Kaydet**’i seçin.

## <a name="clean-up-resources"></a>Kaynakları temizleme
Oluşturulan profili ek öğreticiler veya testler için kullanmayı düşünmüyorsanız silebilirsiniz.
1. Intune'da **Cihaz yapılandırması**'nı, ardından **Profiller**'i seçin.
2. Oluşturduğunuz **iOS iş e-postası iste** adlı test profilini seçin.
3. Profilin yanındaki üç nokta simgesini (**...**) ve ardından **Sil**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iOS cihazları için bir e-posta profili oluşturdunuz. Artık bu profili, profile uymayan tüm iOS cihazlarını uyumsuz olarak işaretleyen bir uyumluluk ilkesi oluşturarak bir iOS cihazının uyumlu olup olmadığını belirlemek için kullanabilirsiniz. Daha fazla koruma için uyumlu olmayan iOS cihazlarının e-posta erişimini engelleyen bir koşullu erişim ilkesi oluşturabilirsiniz. Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

> [!div class="nextstepaction"]
> [Öğretici: Yönetilen cihazlarda Exchange Online e-postaları koruma](tutorial-protect-email-on-enrolled-devices.md)
