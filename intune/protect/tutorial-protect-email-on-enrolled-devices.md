---
title: Öğretici-yönetilen cihazlarda Exchange Online e-postasını koruma
titleSuffix: Microsoft Intune
description: İOS Intune uyumluluk ilkeleriyle Exchange Online 'ı ve yönetilen cihazlar ve Outlook uygulaması gerektirmek için Azure AD koşullu erişim 'i güvenli hale getirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c20c0c1543cd8fcbf7345a02295486aaaa6ddcea
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306874"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Öğretici: Yönetilen cihazlarda Exchange Online e-postasını koruma
İOS cihazlarının Exchange Online e-postasına yalnızca Intune tarafından yönetilmiyorsa ve onaylanan bir e-posta uygulaması kullanılarak erişip erişemediğinden emin olmak için cihaz uyumluluk ilkelerini koşullu erişimle kullanma hakkında bilgi edinin. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz: 
> [!div class="checklist"]
> * Bir cihazın uyumlu kabul edilmesi için uyması gereken koşulları ayarlamak için bir Intune iOS cihaz uyumluluk ilkesi oluşturun.
> * İOS cihazlarının Intune 'a kaydolmasını gerektiren bir Azure Active Directory (Azure AD) koşullu erişim ilkesi oluşturun, Intune ilkeleriyle uyumlu yapın ve Exchange Online e-postasına erişmek için onaylanan Outlook Mobile uygulamasını kullanın.

Intune aboneliğiniz yoksa [ücretsiz deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- Bu öğretici için aşağıdaki aboneliklerle bir test kiracının olması gerekir:
  - Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Exchange ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938)) içeren Office 365 İş aboneliği
- Başlamadan önce, [hızlı başlangıç: iOS için bir e-posta cihaz profili oluşturma](../configuration/quickstart-email-profile.md)' daki adımları izleyerek iOS cihazları için bir test cihaz profili oluşturun.

## <a name="sign-in-to-intune"></a>Intune 'da oturum açma

[Intune](https://aka.ms/intuneportal) 'Da genel yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Bir Intune deneme aboneliği oluşturduysanız, aboneliği oluşturduğunuz hesap genel yöneticime sahip olur.

## <a name="create-the-ios-device-compliance-policy"></a>İOS cihaz Uyumluluk ilkesini oluşturma
Bir cihazın uyumlu kabul edilmesi için uyması gereken koşulları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide iOS cihazları için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platforma özgüdür, bu nedenle değerlendirmek istediğiniz her cihaz platformu için ayrı bir Uyumluluk ilkesine ihtiyacınız vardır.

1. Intune 'da **cihaz uyumluluk** > **ilkeler** > **ilke oluştur**' u seçin.
2. **Ad**alanına **iOS uyumluluk ilkesi testi**girin. 
3. **Açıklama**' da **iOS uyumluluk ilkesi sınaması**' nı girin.
4. **Platform**altında **iOS**' u seçin. 
5. @No__t-1**e-posta** **ayarlarını**seçin. 
     
    1. **Mobil cihazların yönetilen bir e-posta profiline sahip olmasını gerektir**seçeneğinin yanında **gerektir**' i seçin.
    2. **Tamam**’ı seçin.

    ![E-posta Uyumluluk ilkesini yönetilen bir e-posta profili gerektirecek şekilde ayarlama](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6. **Cihaz durumu**seçin. **Jailbreak uygulanmış cihazlar**' ın yanındaki **Engelle**' yi seçin ve ardından **Tamam**' ı seçin.
7. **Sistem güvenliği** ' ni seçin ve **parola** ayarlarını girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:
     
    - **Mobil cihazların kilidini açmak için parola gerektir**için **gerektir**' i seçin.
    - **Basit parolalar**için **Engelle**' yi seçin.
    - **Minimum parola uzunluğu**için **4**girin.
    - **Gerekli parola türü**için **alfasayısal**' i seçin.
    - **Parola istenmeden önce ekran kilitlenmesinden sonra geçen en uzun dakika**için **hemen**öğesini seçin.
    - **Parola kullanım süresi (gün)** için **41**girin.
    - **Yeniden kullanılmasını önleyen önceki parolaların sayısı**için **5**girin.
 
    ![E-posta uyumluluk ilkesi için parola ayarlarını ayarla](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. **Tamam**' ı ve ardından yeniden **Tamam** ' ı seçin.
9. **Oluştur**'u seçin.

## <a name="create-the-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma
Şimdi, tüm cihaz platformlarının Intune 'a kaydolmasını ve Exchange Online 'a erişebilmesi için Intune uyumluluk ilkenize uymasını gerektiren bir koşullu erişim ilkesi oluşturacağız. E-posta erişimi için de Outlook uygulaması gerekir. Koşullu erişim ilkeleri, Azure AD portalında veya Intune portalında yapılandırılabilir. Intune portalında zaten yaptığımız için ilkeyi burada oluşturacağız.
1. Intune 'da, **koşullu erişim** > **ilkeler** > **Yeni ilke**' yi seçin.
1. **Ad**alanına **Office 365 e-postası için test ilkesi**girin. 
3. **Atamalar**' ın altında **Kullanıcılar ve gruplar**' ı seçin. **Dahil et** sekmesinde, **tüm kullanıcılar**' ı seçin ve **bitti**' yi seçin.

4. **Atamalar**' ın altında **bulut uygulamaları**' nı seçin. Office 365 Exchange Online e-postasını korumak istiyoruz, bu adımları izleyerek seçeceğiz:
     
    1. **Dahil et** sekmesinde, **Uygulama Seç**' i seçin.
    2. **Seç**’i seçin. 
    3. Uygulamalar listesinde **Office 365 Exchange Online**' ı seçin ve ardından **Seç**' i seçin. 
    4. **Done** (Bitti) öğesini seçin.
  
    ![Office 365 Exchange Online uygulamasını seçin](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. **Atamalar**' ın altında, @no__t **Koşulları**-2**cihaz platformları**' nı seçin.
     
    1. **Yapılandır**altında **Evet**' i seçin.
    2. **Dahil et** sekmesinde **herhangi bir cihaz**seçin ve **bitti**' yi seçin. 
    3. Yeniden **bitti** ' yi seçin.
   
    ![Herhangi bir cihazı dahil et](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. **Atamalar**' ın altında, **koşullar** > **istemci uygulaması**' nı seçin.
     
    1. **Yapılandır**altında **Evet**' i seçin.
    2. Bu öğretici için **mobil uygulamalar ve Masaüstü istemcileri** ve **modern kimlik doğrulama istemcileri** (IOS için Outlook ve Android için Outlook gibi uygulamalara başvurur) seçeneğini belirleyin. Diğer tüm onay kutularını temizleyin.
    3. **Bitti**' yi seçin ve sonra yeniden **bitti** ' yi seçin.
    
    ![Uygulamaları ve istemcileri seçin](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. **Erişim denetimleri**altında **izin ver**' i seçin. 
     
    1. **İzin** bölmesinde, **erişim ver**' i seçin.
    2. **Cihazın uyumlu olarak Işaretlenmesini gerektir**' i seçin. 
    3. **Onaylanan istemci uygulaması gerektir**' i seçin.
    4. **Birden çok denetim için**, **Seçilen tüm denetimleri gerektir**' i seçin. Bu ayar, bir cihaz e-postaya erişmeyi denediğinde seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.
    5. **Seç**’i seçin.
     
    ![Conrols seçin](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. **İlkeyi etkinleştir** bölümünde **Açık** seçeneğini belirleyin.
     
    ![İlkeyi etkinleştir](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. **Oluştur**'u seçin.

## <a name="try-it-out"></a>Deneyin
Oluşturduğunuz ilkelerle, Office 365 e-postasına oturum açmayı deneyen tüm iOS cihazlarının Intune 'a kaydolması ve iOS için Outlook Mobile uygulamasını kullanması gerekir. Bu senaryoyu bir iOS cihazında test etmek için test kiracınızdaki bir kullanıcının kimlik bilgilerini kullanarak Exchange Online 'da oturum açmayı deneyin. Cihazı kaydetmek ve Outlook Mobile uygulamasını yüklemek isteyip istemediğiniz sorulur.
1. İPhone 'u test etmek için **ayarlar** > **parola & hesaplar** > **Hesap Ekle** > **Exchange**' e gidin.
2. Test kiracınızdaki bir kullanıcının e-posta adresini girin ve ardından **İleri**' ye basın.
3. **Oturum aç '** a basın.
4. Test kullanıcısının parolasını girin ve **oturum aç**' a basın.
5. Cihazınızın kaynağa erişmek için yönetilmesi gerektiğini belirten bir ileti görünür ve kayıt için bir seçeneğe sahip olur. 

## <a name="clean-up-resources"></a>Kaynakları temizleme
Test ilkelerine artık ihtiyaç duyulmadığında, bunları kaldırabilirsiniz.
1. [Intune](https://aka.ms/intuneportal) 'Da genel yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.
2. **Cihaz uyumluluk** > **ilkeleri**' ni seçin.
3. **Ilke adı** listesinde, test ilkeniz için bağlam menüsünü ( **...** ) seçin ve **Sil**' i seçin. Onaylamak için **Tamam ' ı** seçin.
4. **Koşullu erişim** > **ilkeleri**' ni seçin.
5. **Ilke adı** listesinde, test ilkeniz için bağlam menüsünü ( **...** ) seçin ve **Sil**' i seçin. Onaylamak için **Evet**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar 
Bu öğreticide, iOS cihazlarının Intune 'a kaydolmasını gerektiren ve Exchange Online e-postasına erişmek için Outlook uygulamasını kullanan ilkeler oluşturdunuz. Intune 'u, Office 365 Exchange Online için Exchange ActiveSync istemcileri de dahil olmak üzere diğer uygulama ve hizmetleri korumak için koşullu erişimle kullanma hakkında bilgi edinmek için bkz. [koşullu erişimi ayarlama](conditional-access.md).
