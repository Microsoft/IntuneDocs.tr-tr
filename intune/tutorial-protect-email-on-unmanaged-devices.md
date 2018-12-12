---
title: Öğretici - yönetilmeyen cihazlarda Exchange Online e-postaları koruma
titlesuffix: Microsoft Intune
description: Intune uygulama koruma ilkelerini ve Azure AD koşullu erişim ile Office 365 Exchange Online güvenli şekilde öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/11/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bcf66037995c6b5cb2b0c5b3f090d3af2e42cd6a
ms.sourcegitcommit: 8019bdd8117806c6a3a73a8c6d40af1a3def6d90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53263732"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Öğretici: Yönetilmeyen cihazlarda Exchange Online e-postaları koruma

Bile cihazları Intune gibi bir cihaz yönetim çözümüne kayıtlı olmayan, Exchange Online koruma için uygulama koruma ilkeleri ile koşullu erişim kullanma hakkında bilgi edinin. Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz: 

> [!div class="checklist"]
> * Outlook uygulaması için bir Intune uygulama koruma ilkesi oluşturun. Hangi kullanıcı "Farklı Kaydet" engelleyerek ile uygulama verilerini yapın ve kısıtlama sınırlamak kesme, kopyalama ve yapıştırma. 
> * Exchange Online'da şirket e-postalarına yalnızca Outlook uygulaması sağlayan Azure Active Directory (Azure AD) koşullu erişim ilkeleri oluşturun. Ayrıca, iOS için Outlook ve Android gibi Modern kimlik doğrulaması istemcileri için çok faktörlü kimlik doğrulaması (MFA) ihtiyacınız olacaktır.

## <a name="prerequisites"></a>Önkoşullar
  - Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:
    - Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Intune aboneliği ([ücretsiz deneme sürümü](free-trial-sign-up.md))
    - Exchange içeren Office 365 Business aboneliği ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune, Azure portalında **Tüm hizmetler** > **Intune** seçilerek bulunur.

## <a name="create-the-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
Bu öğretici için size bir uygulama düzeyinde koruma yararlanılmasını Outlook uygulaması için Intune uygulama koruma İlkesi ayarlarsınız. Biz, uygulamayı iş bağlamında açmak bir PIN ihtiyacınız olacaktır. Ayrıca uygulamalar arasında veri paylaşımı sınırlamak ve şirket verilerinin kişisel bir konuma kaydedilmesini engelleyen.

1.  Intune'da seçin **istemci uygulamaları** > **uygulama koruma ilkeleri** > **ilke Ekle**.
2.  İçinde **adı**, girin **Outlook uygulama ilkesi test**.
3.  İçinde **açıklama**, girin **Outlook uygulama ilkesi test**.
4.  Seçin **uygulamaları**. Uygulamalar listesinde **Outlook**ve ardından **seçin**.
5.  Seçin **ayarları**. 
6.  Altında **verileri yeniden konumlandırma**, bu öğreticide seçmek için bu ayarları:

    - İçin **uygulamanın diğer uygulamalara veri aktarmasına izin ver**seçin **hiçbiri**.
    - İçin **uygulamanın diğer uygulamalardan veri almasına izin ver**seçin **hiçbiri**.
    - İçin **engelle "Farklı Kaydet"** seçin **Evet**.
    - İçin **kısıtlama kesme, kopyalama ve yapıştırma diğer uygulamalarla**seçin **bloke**.
   
     ![Outlook uygulama koruma İlkesi veri yeniden konumlandırma ayarları seçin](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-data-relocation.png)
    
7.  Altında **erişim eylemleri**, bu öğreticide seçmek için bu ayarları:

    - İçin **erişim için PIN'i zorunlu kıl**seçin **Evet**.
    - İçin **erişim için Kurumsal kimlik bilgilerini gerektir**seçin **Evet**.
    - Diğer tüm ayarları varsayılan değerlerinde bırakın.
 
     ![Uygulama koruma İlkesi Outlook erişim eylemleri seçin](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-access-actions.png)

9.  **Tamam**’ı seçin.
10. **Oluştur**’u seçin.

Outlook için uygulama koruma ilkesi oluşturulur. Artık Outlook uygulaması kullanmasını gerektirmek için koşullu erişimi ayarlayabilirsiniz.

## <a name="create-conditional-access-policies"></a>Koşullu erişim ilkeleri oluşturun.
Tüm cihaz platformları kapsayacak şekilde iki koşullu erişim ilkeleri artık oluşturacağız. İlk ilke onaylı Outlook uygulaması ve mfa'yı kullanmak için iOS için Outlook ve Android için Outlook gibi Modern kimlik doğrulaması istemcileri gerektirir. İkinci ilkesi Exchange ActiveSync istemcileri, onaylanan Outlook uygulaması kullanmasını gerektirir. (Şu anda Exchange Active Sync cihaz platformu farklı koşullar desteklemez). Azure AD portalından veya Intune portalında koşullu erişim ilkelerini yapılandırabilirsiniz. Zaten Intune portalında olduğumuz için ilkeyi burada oluşturalım.
### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Modern kimlik doğrulaması istemcileri için MFA ilkesi oluşturma
1.  Intune’da **Koşullu erişim** > **İlkeler** > **Yeni ilke**’yi seçin.
1.  İçinde **adı**, girin **modern kimlik doğrulaması istemcileriniz için ilke Test**. 
3.  **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

4.  **Atamalar** altında **Bulut uygulamaları**’nı seçin. Office 365 Exchange Online e-postalarını korumak istediğimiz için şu adımları izleyeceğiz:
     
    1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.
    2. **Seç**’i seçin. 
    3. Uygulamalar listesinde **Office 365 Exchange Online**’a ve ardından **Seç**’e tıklayın. 
    4. **Done** (Bitti) öğesini seçin.
  
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5.  **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. Üzerinde **INCLUDE** sekmesinde **tüm platformlar (desteklenmeyen dahil olmak üzere)**. 
    3. **Done** (Bitti) öğesini seçin.
   
6.  Üzerinde **koşullar** bölmesinde **istemci uygulamaları**.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. Seçin **mobil uygulamalar ve masaüstü istemciler** ve **Modern kimlik doğrulaması istemcileri**.
    3. Bir onay kutularını temizleyin.
    4. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.
    
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7.  **Erişim denetimleri** altında **Ver**’i seçin. 
     
    1. **Ver** bölmesinde **Erişim ver**’i seçin.
    2. Seçin **çok faktörlü kimlik doğrulaması gerektiren**.
    4. **Onaylı istemci uygulaması gerektir**’e tıklayın.
    5. **Çoklu denetim için** altında **Tüm seçili denetimleri gerektir**’i seçin. Bu ayar, bir cihaz e-postaya erişmeye çalıştığında seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.
    6. **Seç**’i seçin.
     
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

8.  **İlkeyi etkinleştir** altında **Açık**’ı seçin.
     
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)

9.  **Oluştur**’u seçin.

Modern kimlik doğrulaması istemciler için koşullu erişim ilkesi oluşturulur. Şimdi, Exchange Active Sync istemciler için bir ilke oluşturabilirsiniz.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Exchange Active Sync istemciler için bir ilke oluşturun
1.  Intune’da **Koşullu erişim** > **İlkeler** > **Yeni ilke**’yi seçin.
2.  İçinde **adı**, girin **EAS istemciler için ilke Test**. 
3.  **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

4.  **Atamalar** altında **Bulut uygulamaları**’nı seçin. Bu adımda Office 365 Exchange Online e-posta seçin:
     
    1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.
    2. **Seç**’i seçin. 
    3. Uygulamalar listesinde **Office 365 Exchange Online**’a ve ardından **Seç**’e tıklayın. 
    4. **Done** (Bitti) öğesini seçin.

5.  **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. **Dahil et** sekmesinde **Tüm platformlar (desteklenmeyenler dahil)** ve ardından **Bitti**’yi seçin. 
    3. Tekrar **Bitti**’yi seçin.

6.  Üzerinde **koşullar** bölmesinde **istemci uygulamaları**.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. Seçin **mobil uygulamalar ve masaüstü istemciler**.
    3. Seçin **Exchange ActiveSync istemcileri** ve **ilkeyi yalnızca desteklenen platformlara Uygula**. 
    4. Diğer tüm onay kutularının işaretini kaldırın.
    5. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.
    
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)

7.  **Erişim denetimleri** altında **Ver**’i seçin. 
     
    1. **Ver** bölmesinde **Erişim ver**’i seçin.
    4. **Onaylı istemci uygulaması gerektir**’e tıklayın. Diğer tüm onay kutularının işaretini kaldırın.
    6. **Seç**’i seçin.
     
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

8.  **İlkeyi etkinleştir** altında **Açık**’ı seçin.

9.  **Oluştur**’u seçin.

Uygulama koruma ilkeleri ve koşullu erişim artık yerinde olduğundan ve test için hazır. 

## <a name="try-it-out"></a>Deneyin
Oluşturduğunuz ilkeleri ile cihazlar, ıntune'a ve Office 365 e-postaya erişmek için Outlook mobil uygulaması gerekir. Bu senaryoyu bir iOS cihazda test etmek için test kiracınızdaki kullanıcılardan birine ait kimlik bilgilerini kullanarak Exchange Online’da oturum açmayı deneyin.
1. Bu testi bir iPhone’da yapmak için **Ayarlar** > **Parolalar ve Hesaplar** > **Hesap Ekle** > **Exchange**’i seçin.
2. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.
3. **Oturum Aç**’a basın.
4. Test kullanıcısının parolasını girin ve **Oturum aç**’a basın.
5. İleti **daha fazla bilgi gerekiyor** görünür istenirse mfa'yı ayarlamak için anlamına gelir. Devam edin ve bir ek doğrulama yöntemi ayarladığını.
6. Ardından, bu kaynağı BT departmanınızın onaylamadığı bir uygulamayla açmaya çalıştığınız belirten bir ileti görürsünüz. Bu, yerel posta uygulamasını kullanmaları engellenme anlamına gelir. Oturum açma iptal edin.
7.  Outlook uygulamasını açın ve seçin **ayarları** > **hesabı Ekle** > **e-posta hesabı Ekle**.
8. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.
9. Tuşuna **oturum Office 365 oturum**. Ek kimlik doğrulama ve kayıt için istenir. Oturumunuz açıldıktan sonra kesme, kopyalama, yapıştırma ve "Farklı Kaydet" gibi eylemler test edebilirsiniz.

## <a name="clean-up-resources"></a>Kaynakları temizleme
Test ilkelerine artık ihtiyacınız kalmadığında bunları kaldırabilirsiniz.
1. [Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.
2. **Cihaz Uyumluluğu** > **İlkeler**’i seçin.
3. **İlke Adı** listesinde test ilkenizin açılır menüsünü (**...**) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Tamam**’ı seçin.
4. **Koşullu Erişim** > **İlkeler**’i seçin.
5. İçinde **ilke adı** listesinde, bağlam menüsünü seçin (**...** ) her sınama ilkelerini ve ardından **Sil**. Onaylamak için **Evet**’i seçin.

 ## <a name="next-steps"></a>Sonraki adımlar 
Bu öğreticide, uygulama koruma ilkeleri, kullanıcının Outlook uygulaması ile neler yapabileceğinizi sınırlamak için oluşturduğunuz ve Outlook uygulaması gerektirebilir ve Modern kimlik doğrulaması istemcileri için MFA istemek için koşullu erişim ilkeleri oluşturdunuz. Diğer uygulama ve Hizmetleri korumak için Intune ile koşullu erişim kullanma hakkında bilgi edinmek için [koşullu erişimi ayarlama](conditional-access.md).
