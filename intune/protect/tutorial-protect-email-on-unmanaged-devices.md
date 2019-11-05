---
title: Öğretici-yönetilmeyen cihazlarda Exchange Online e-postasını koruma
titleSuffix: Microsoft Intune
description: Intune uygulama koruma ilkeleriyle Office 365 Exchange Online 'ı ve Azure AD koşullu erişim 'i güvenli hale getirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/10/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d3b903c8d21b678bb86d9e6474dbe52a9caaaf74
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503599"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Öğretici: yönetilmeyen cihazlarda Exchange Online e-postasını koruma

Cihazlar, Intune gibi bir cihaz yönetimi çözümüne kayıtlı olmadığında bile Exchange Online 'ı korumak için koşullu erişimle birlikte uygulama koruma ilkelerini kullanma hakkında bilgi edinin. Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz: 

> [!div class="checklist"]
> * Outlook uygulaması için bir Intune uygulama koruma ilkesi oluşturun. "Farklı kaydet" i engellemek ve kesme, kopyalama ve yapıştırma eylemlerini kısıtlamak için kullanıcının uygulama verileriyle neler yapabileceğini sınırlayabilirsiniz. 
> * Exchange Online 'daki şirket e-postasına yalnızca Outlook uygulamasının erişmesine izin veren Azure Active Directory (Azure AD) koşullu erişim ilkeleri oluşturun. Ayrıca, iOS ve Android için Outlook gibi modern kimlik doğrulama istemcileri için çok faktörlü kimlik doğrulaması (MFA) gerekir.

## <a name="prerequisites"></a>Önkoşullar
- Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:
  - Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Intune aboneliği ([ücretsiz deneme](../fundamentals/free-trial-sign-up.md))
  - Exchange içeren Office 365 Business aboneliği ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune, Azure portalında **Tüm hizmetler** > **Intune** seçilerek bulunur.

## <a name="create-the-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
Bu öğretici için, uygulama düzeyinde koruma sağlamak üzere Outlook uygulaması için bir Intune uygulama koruma ilkesi ayarlayacağız. Uygulamayı bir iş bağlamında açmak için PIN gerekir. Ayrıca, uygulamalar arasında veri paylaşımını sınırlayacağız ve şirket verilerinin kişisel bir konuma kaydedilmesini engeller.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **istemci uygulamaları** > **Uygulama koruma Ilkeleri** > **ilke oluştur**' a gidin.  
2. Aşağıdaki ayarı yapılandırın:  
   - **Ad**: **Outlook uygulama ilkesi testini**girin.  
   - **Açıklama**: **Outlook uygulama ilkesi testini**girin.  
   - **Platform**: **iOS**' u seçin.  
   - **Tüm uygulama türlerine hedefle**: **Hayır**' ı seçin ve ardından **uygulama türleri**için, **yönetilmeyen cihazlardaki uygulamalar**onay kutusunu seçin.  
3. **Uygulamalar**' ı seçin. Uygulamalar listesinde **Outlook**' u ve ardından **Seç**' i seçin.
4. Ayarlar bölmesini açmak için **Ayarlar** ' ı seçin. 
5. Ayarlar bölmesinde **veri koruma**' yı seçin. Veri koruma bölmesinde *veri aktarımı*altında, bu öğretici için aşağıdaki ayarları yapılandırın:

   - **Diğer uygulamalara kuruluş verileri göndermek**için **hiçbiri**' ni seçin.  
   - **Diğer uygulamalardan gelen verileri almak**için **hiçbiri**' ni seçin.  
   - **Kuruluş verilerinin kopyalarını kaydetmek**için **Engelle**' yi seçin.  
   - **Diğer uygulamalar arasında kesme, kopyalama ve yapıştırma Işlemlerini kısıtlamak**için **engellendi**öğesini seçin. 
   - Tüm diğer ayarları varsayılan değerlerinde bırakın. 
   
   ![Outlook uygulama koruma ilkesi verilerini değiştirme ayarlarını seçin](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Ayarlar bölmesine dönmek için **Tamam ' ı** seçin.  

6. **Erişim gereksinimleri** ' ni seçin ve ardından aşağıdaki ayarları yapılandırın:  

   - **Erişim Için PIN**için **gerektir**' i seçin.
   - **Erişim Için iş veya okul hesabı kimlik bilgileri**için **gerektir**' i seçin.
   - Tüm diğer ayarları varsayılan değerlerinde bırakın.
 
    ![Outlook uygulama koruma ilkesi erişim eylemlerini seçin](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

    Ayarlar bölmesine dönmek için **Tamam ' ı** seçin.  

7. Ayarlar bölmesinde **Tamam**' ı seçin ve ardından ilke oluştur bölmesinde **Oluştur**' u seçin.

Outlook için uygulama koruma ilkesi oluşturulur. Daha sonra, cihazların Outlook uygulamasını kullanmasını gerektirmek için koşullu erişim ayarlayacaksınız.

## <a name="create-conditional-access-policies"></a>Koşullu erişim ilkeleri oluşturma
Artık tüm cihaz platformlarını kapsayan iki koşullu erişim ilkesi oluşturacağız.  

- İlk ilke, modern kimlik doğrulama istemcilerinin onaylanan Outlook uygulamasını ve Multi-Factor Authentication 'ı (MFA) kullanmasını gerektirir. Modern kimlik doğrulama istemcileri iOS için Outlook ve Android için Outlook içerir.  

- İkinci ilke, Exchange ActiveSync istemcilerinin onaylanan Outlook uygulamasını kullanmasını gerektirir. (Şu anda Exchange Active Sync cihaz platformu dışındaki koşulları desteklemez). Koşullu erişim ilkelerini Azure AD portalında veya Intune portalında yapılandırabilirsiniz. Zaten Intune portalında olduğumuz için ilkeyi burada oluşturalım.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Modern kimlik doğrulama istemcileri için MFA ilkesi oluşturma  

1. Intune 'da, **koşullu erişim** > **ilkeler** > **Yeni ilke**' yi seçin.  

2. **Ad**için, **modern kimlik doğrulama istemcileri için test ilkesi**girin.  

3. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

4. **Atamalar**' ın altında **bulut uygulamaları veya eylemler**' i seçin. Office 365 Exchange Online e-postalarını korumak istediğimiz için şu adımları izleyeceğiz:  
     
   1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.  
   2. **Seçin** öğesini belirleyin.  
   3. Uygulamalar listesinde **Office 365 Exchange Online**' ı seçin ve ardından **Seç**' i seçin.  
   4. Yeni ilke bölmesine dönmek için **bitti** ' yi seçin.  
  
   ![Office 365 Exchange Online uygulamasını seçin](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5. **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.  
   1. **Yapılandır** altında **Evet**’i seçin.  
   2. **Dahil et** sekmesinde **herhangi bir cihaz**seçin.  
   3. **Bitti**’yi seçin.  
   
6. **Koşullar** bölmesinde, **istemci uygulamaları**' nı seçin.  
   1. **Yapılandır** altında **Evet**’i seçin.  
   2. **Mobil uygulamalar ve Masaüstü istemcileri** ve **modern kimlik doğrulama istemcileri**' ni seçin.  
   3. Diğer onay kutularını temizleyin.  
   4. Yeni ilke bölmesine dönmek için **bitti**@no__t **-1 ' i seçin** .  

   ![Mobil Uygulamaları ve istemcileri seçin](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7. **Erişim denetimleri** altında **Ver**’i seçin. 
     
   1. **Ver** bölmesinde **Erişim ver**’i seçin.
   2. **Multi-Factor Authentication gerektir**' i seçin.
   3. **Onaylı istemci uygulaması gerektir**’e tıklayın.
   4. **Çoklu denetim için** altında **Tüm seçili denetimleri gerektir**’i seçin. Bu ayar, bir cihaz e-postaya erişmeye çalıştığında seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.
   5. **Seçin** öğesini belirleyin.
     
   ![Denetimleri Seç](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

7. **Ilkeyi etkinleştir**altında **Açık**' ı seçin ve ardından **Oluştur**' u seçin.  
     
    ![İlke oluştur](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

Modern kimlik doğrulama istemcileri için koşullu erişim ilkesi oluşturulur. Artık Exchange Active Sync istemcileri için bir ilke oluşturabilirsiniz.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Exchange Active Sync istemcileri için ilke oluşturma  
1. Intune 'da, **koşullu erişim** > **ilkeler** > **Yeni ilke**' yi seçin.  
2. **Ad**için **EAS istemcileri için test ilkesi**girin.  
3. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin.  
4. *Dahil et* sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.  

5. **Atamalar**' ın altında **bulut uygulamaları veya eylemler**' i seçin. Şu adımlarla Office 365 Exchange Online e-postası ' nı seçin:  
   1. *Dahil et* sekmesinde **Uygulama seç**’i seçin.  
   2. **Seçin** öğesini belirleyin.  
   3. *Uygulamalar*listesinden **Office 365 Exchange Online**' ı seçin ve ardından **Seç**' i ve ardından **Tamam**' ı seçin.  
  
6. **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.  
   1. **Yapılandır** altında **Evet**’i seçin.  
   2. **Dahil et** sekmesinde **herhangi bir cihaz**seçin ve **bitti**' yi seçin.  

7. **Koşullar** bölmesinde, **istemci uygulamaları**' nı seçin.  
   1. **Yapılandır** altında **Evet**’i seçin.  
   2. **Mobil uygulamalar ve Masaüstü istemcileri '** ni seçin.  
   3. **Exchange ActiveSync istemcileri** ' ni seçin ve **ilkeyi yalnızca desteklenen platformlar için uygulayın**.  
   4. Diğer tüm onay kutularının işaretini kaldırın.  
   5. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.  
    
   ![Desteklenen platformlara Uygula](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

7. **Erişim denetimleri** altında **Ver**’i seçin.  
   1. **Ver** bölmesinde **Erişim ver**’i seçin.  
   2. **Onaylı istemci uygulaması gerektir**’e tıklayın. Diğer tüm onay kutularının işaretini kaldırın.  
   3. **Seçin** öğesini belirleyin.  
     
   ![Onaylanan istemci uygulaması gerektir](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)  

8. **İlkeyi etkinleştir** altında **Açık**’ı seçin.  

9. **Oluştur**’u seçin.  

Uygulama koruma ilkeleriniz ve koşullu erişim artık yerinde ve test etmeye hazır.  

## <a name="try-it-out"></a>Deneme  
Oluşturduğunuz ilkelerle birlikte cihazların Intune 'a kaydolması ve Office 365 e-postasına erişmek için Outlook Mobile uygulamasını kullanması gerekir. Bu senaryoyu bir iOS cihazda test etmek için test kiracınızdaki kullanıcılardan birine ait kimlik bilgilerini kullanarak Exchange Online’da oturum açmayı deneyin.  
1. Bu testi bir iPhone’da yapmak için **Ayarlar** > **Parolalar ve Hesaplar** > **Hesap Ekle** > **Exchange**’i seçin.  
2. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.  
3. **Oturum Aç**’a basın.  
4. Test kullanıcısının parolasını girin ve **Oturum aç**’a basın.  
5. İleti **daha fazla bilgi gerekir** , bu da MFA 'yı ayarlamanız istenmekte olduğunuz anlamına gelir. Devam edin ve ek bir doğrulama yöntemi ayarlayın.  
6. Daha sonra, bu kaynağı BT departmanınız tarafından onaylanmamış bir uygulamayla açmaya çalıştığın bir ileti görürsünüz. İleti, yerel posta uygulamasını kullanmaktan engellediğiniz anlamına gelir. Oturum açma işlemini iptal edin.  
7. Outlook uygulamasını açın ve **ayarlar** > **Hesap Ekle** > **e-posta hesabı ekle**' yi seçin.  
8. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.  
9. **Office 365 Ile oturum aç '** a basın. Sizden ek kimlik doğrulaması ve kayıt istenir. Oturum açtıktan sonra kesme, kopyalama, yapıştırma ve "farklı kaydet" gibi eylemleri test edebilirsiniz.  

## <a name="clean-up-resources"></a>Kaynakları temizleme  
Test ilkelerine artık ihtiyacınız kalmadığında bunları kaldırabilirsiniz.  
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.  
2. **Cihaz Uyumluluğu** > **İlkeler**’i seçin.  
3. **İlke Adı** listesinde test ilkenizin açılır menüsünü ( **...** ) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Tamam**’ı seçin.  
4. **Koşullu Erişim** > **İlkeler**’i seçin.  
5. **Ilke adı** listesinde, test ilkelerinizin her biri için bağlam menüsünü ( **...** ) seçin ve **Sil**' i seçin. Onaylamak için **Evet** ' i seçin.  

## <a name="next-steps"></a>Sonraki adımlar  
Bu öğreticide, kullanıcının Outlook uygulamasıyla neler yapabileceğini sınırlamak için uygulama koruma ilkeleri oluşturdunuz ve Outlook uygulamasını gerektirecek ve modern kimlik doğrulama istemcileri için MFA gerektirirken koşullu erişim ilkeleri oluşturdunuz. Diğer uygulama ve hizmetleri korumak için Intune 'U koşullu erişimle kullanma hakkında bilgi edinmek için bkz. [koşullu erişimi ayarlama](conditional-access.md).