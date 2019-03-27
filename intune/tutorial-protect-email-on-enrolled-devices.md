---
title: Öğretici - Intune ile yönetilen cihazlarda Exchange Online e-postalarını koruma
titlesuffix: Microsoft Intune
description: iOS Intune uyumluluk ilkeleri ve Azure Active Directory koşullu erişim ile yönetilen cihazlar ve Outlook uygulamasını gerektirerek Exchange Online’ın güvenliğini sağlamayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
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
ms.openlocfilehash: 0631c060833d7d68d96f6e78651da6de9420a5f5
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490630"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Öğretici: Yönetilen cihazlarda Exchange Online e-postaları koruma
iOS cihazların yalnızca Intune tarafından yönetildiğinde ve onaylı bir e-posta uygulaması kullandığında Exchange Online’a erişebilmesini sağlamak için koşullu erişim ile cihaz uyumluluk ilkelerini kullanma hakkında bilgi edinin. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz: 
> [!div class="checklist"]
> * Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune iOS cihaz uyumluluk ilkesi oluşturma.
> * iOS cihazların Exchange Online e-postalarına erişmek için Intune’a kaydolması, Intune ilkeleriyle uyumlu olması ve onaylı Outlook mobil uygulamasını kullanmasını gerektiren bir Azure Active Directory (AAD) koşullu erişim ilkesi oluşturma.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
  - Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:
    - Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Exchange içeren Office 365 Business aboneliği ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938))
  - Başlamadan önce içindeki adımları izleyerek iOS cihazları için cihaz profili oluşturma [hızlı başlangıç: İOS için bir e-posta cihaz profili oluşturma](quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-the-ios-device-compliance-policy"></a>iOS cihaz uyumluluğu ilkesini oluşturma
Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide iOS cihazlar için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platformlara özgüdür; değerlendirmek istediğiniz her bir platform için ayrı bir uyumluluk ilkesine ihtiyacınız vardır.

1.  Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2.  **Ad** olarak **iOS uyumluluk ilkesi testi**’ni seçin. 
3.  **Açıklama** olarak **iOS uyumluluk ilkesi testi**’ni seçin.
4.  **Platform** olarak **iOS**’u seçin. 
5.  **Ayarlar** > **E-posta**’yı seçin. 
     
    1.  **Mobil cihazların yönetilen bir e-posta profiline sahip olmasını gerektir** ayarını **Gerektir** olarak belirleyin.
    2. **Tamam**’ı seçin.

    ![E-posta uyumluluk ilkesini yönetilen e-posta profili gerektirecek şekilde ayarlama](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6.  **Cihaz Durumu**’nı seçin. **Jailbreak uygulanmış cihazlar** için **Engelle**’yi seçin ve daha sonra **Tamam**’a tıklayın.
7.  **Sistem Güvenliği**’ni seçin ve **Parola** ayarlarını girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:
     
    - **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerektir** olarak belirleyin.
    - **Basit parolalar** için **Engelle**’yi seçin.
    - **En düşük parola uzunluğu**’nu **4** olarak ayarlayın.
    - **Gerekli parola türü** için **Alfasayısal**’ı seçin.
    - **Ekran kilitlendiğinde parola istenmeden önce geçmesi gereken en yüksek dakika sayısı** için **Hemen**’i seçin.
    - **Parola zaman aşımı (gün)** için **41** değerini girin.
    - **Yeniden kullanımı önlemek için önceki parola sayısı** için **5** değerini girin.
 
    ![E-posta uyumluluk ilkesi için parola ayarlarını belirleme](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8.  **Tamam**’ı ve ardından tekrar **Tamam**’ı seçin.
9.  **Oluştur**’u seçin.

## <a name="create-the-conditional-access-policy"></a>Koşullu erişim ilkesini oluşturma
Şimdi Exchange Online’a erişmeden önce tüm cihaz platformlarının Intune uyumluluk ilkemizle uyumlu olmasını gerektiren bir koşullu erişim ilkesi oluşturacağız. Ayrıca e-posta erişimi için Outlook uygulamasını gerekli kılacağız. Koşullu erişim ilkeleri, Azure Active Directory portalında veya Intune portalında yapılandırılabilir. Zaten Intune portalında olduğumuz için ilkeyi burada oluşturalım.
1.  Intune’da **Koşullu erişim** > **İlkeler** > **Yeni ilke**’yi seçin.
1.  **Ad** olarak **Office 365 e-postaları için test ilkesi**’ni seçin. 
3.  **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

4.  **Atamalar** altında **Bulut uygulamaları**’nı seçin. Office 365 Exchange Online e-postalarını korumak istediğimiz için şu adımları izleyeceğiz:
     
    1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.
    2. **Seç**’i seçin. 
    3. Uygulamalar listesinde **Office 365 Exchange Online**’a ve ardından **Seç**’e tıklayın. 
    4. **Done** (Bitti) öğesini seçin.
  
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5.  **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. Üzerinde **INCLUDE** sekmesinde **herhangi bir CİHAZDAN**ve ardından **Bitti**. 
    3. Tekrar **Bitti**’yi seçin.
   
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6.  **Atamalar** altında **Koşullar** > **İstemci uygulamaları**’nı seçin.
     
    1. **Yapılandır** altında **Evet**’i seçin.
    2. Bu öğretici için **Mobil uygulamalar ve masaüstü istemciler**’i ve **Modern kimlik doğrulaması istemcileri**’ni (iOS için Outlook ve Android için Outlook gibi uygulamaları ifade eder) seçin. Diğer tüm onay kutularının işaretini kaldırın.
    3. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.
    
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7.  **Erişim denetimleri** altında **Ver**’i seçin. 
     
    1. **Ver** bölmesinde **Erişim ver**’i seçin.
    2. **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin. 
    3. **Onaylı istemci uygulaması gerektir**’e tıklayın.
    4. **Çoklu denetim için** altında **Tüm seçili denetimleri gerektir**’i seçin. Bu ayar, bir cihaz e-postaya erişmeye çalıştığında seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.
    5. **Seç**’i seçin.
     
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8.  **İlkeyi etkinleştir** altında **Açık**’ı seçin.
     
    ![Office 365 Exchange Online uygulamasını seçin](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9.  **Oluştur**’u seçin.

## <a name="try-it-out"></a>Deneyin
Oluşturduğunuz ilkelerle, Office 365’te oturum açmaya çalışan herhangi bir iOS cihazın Intune’a kaydolması ve iOS için Outlook mobil uygulamasını kullanması gerekecektir. Bu senaryoyu bir iOS cihazda test etmek için test kiracınızdaki kullanıcılardan birine ait kimlik bilgilerini kullanarak Exchange Online’da oturum açmayı deneyin. Cihazı kaydetmeniz ve Outlook mobil uygulamasını yüklemeniz istenecektir.
1. Bu testi bir iPhone’da yapmak için **Ayarlar** > **Parolalar ve Hesaplar** > **Hesap Ekle** > **Exchange**’i seçin.
2. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.
3. **Oturum Aç**’a basın.
4. Test kullanıcısının parolasını girin ve **Oturum aç**’a basın.
5. Kaynağa erişmek için cihazınızı kaydetmeniz gerektiğini belirten bir iletinin yanında kaydolma seçeneği görüntülenecektir. 

## <a name="clean-up-resources"></a>Kaynakları temizleme
Test ilkelerine artık ihtiyacınız kalmadığında bunları kaldırabilirsiniz.
1. [Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.
2. **Cihaz Uyumluluğu** > **İlkeler**’i seçin.
3. **İlke Adı** listesinde test ilkenizin açılır menüsünü (**...**) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Tamam**’ı seçin.
4. **Koşullu Erişim** > **İlkeler**’i seçin.
5. **İlke Adı** listesinde test ilkenizin açılır menüsünü (**...**) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Evet**’i seçin.

 ## <a name="next-steps"></a>Sonraki adımlar 
Bu öğreticide, iOS cihazların Exchange Online e-postalarına erişmek için Intune’a kaydolmasını ve Outlook uygulamasını kullanmasını gerektiren ilkeler oluşturdunuz. Office 365 Exchange Online için Exchange ActiveSync istemcileri dahil olmak üzere diğer uygulama ve hizmetleri korumak için koşullu erişim ile Intune’u kullanma hakkında daha fazla bilgi edinmek için bkz. [Koşullu erişimi ayarlama](conditional-access.md).
