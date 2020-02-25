---
title: Öğretici-yönetilen cihazlarda Exchange Online e-postasını koruma
titleSuffix: Microsoft Intune
description: İOS Intune uyumluluk ilkeleriyle Exchange Online 'ı ve yönetilen cihazlar ve Outlook uygulaması gerektirmek için Azure AD koşullu erişim 'i güvenli hale getirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c134eb1fc413a32f2a27034d8c3a993f18f8a9c9
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576279"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Öğretici: Yönetilen cihazlarda Exchange Online e-postalarını koruma

İOS cihazlarının Exchange Online e-postasına yalnızca Intune tarafından yönetilmiyorsa ve onaylanan bir e-posta uygulaması kullanılarak erişip erişemediğinden emin olmak için cihaz uyumluluk ilkelerini koşullu erişimle kullanma hakkında bilgi edinin.

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:

> [!div class="checklist"]
> * Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune iOS cihaz uyumluluk ilkesi oluşturma.
> * İOS cihazlarının Intune 'a kaydolmasını gerektiren bir Azure Active Directory (Azure AD) koşullu erişim ilkesi oluşturun, Intune ilkeleriyle uyumlu yapın ve Exchange Online e-postasına erişmek için onaylanan Outlook Mobile uygulamasını kullanın.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:

- Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))

- Exchange içeren Office 365 Business aboneliği ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938))

Başlamadan önce, [hızlı başlangıç: iOS için bir e-posta cihaz profili oluşturma/ıpados](../configuration/quickstart-email-profile.md)' daki adımları izleyerek iOS cihazları için bir test cihaz profili oluşturun.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) [genel yönetici](../fundamentals/users-add.md#types-of-administrators) veya Intune [Hizmet Yöneticisi](../fundamentals/users-add.md#types-of-administrators)olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-the-ios-device-compliance-policy"></a>iOS cihaz uyumluluğu ilkesini oluşturma

Bir cihazın uyumlu sayılması için karşılaması gereken şartları ayarlamak için bir Intune cihaz uyumluluk ilkesi ayarlayın. Bu öğreticide iOS cihazlar için bir cihaz uyumluluk ilkesi oluşturacağız. Uyumluluk ilkeleri platformlara özgüdür; değerlendirmek istediğiniz her bir platform için ayrı bir uyumluluk ilkesine ihtiyacınız vardır.

1. Intune 'da **cihaz** > **Uyumluluk Ilkeleri** > **ilke oluştur**' u seçin.

2. **Ad**için **iOS uyumluluk ilkesi sınaması**' nı girin.

3. **Açıklama**için **iOS uyumluluk ilkesi sınaması**' nı girin.

4. **Platform**için **IOS/ıpados**' ı seçin.

5. **Ayarlar** > **E-posta**’yı seçin.

   1. **Mobil cihazların yönetilen bir e-posta profiline sahip olmasını gerektir** ayarını **Gerektir** olarak belirleyin.

   2. **Tamam**’ı seçin.

   ![E-posta uyumluluk ilkesini yönetilen e-posta profili gerektirecek şekilde ayarlama](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)

6. **Cihaz Durumu**’nı seçin. **Jailbreak uygulanmış cihazlar** için **Engelle**’yi seçin ve daha sonra **Tamam**’a tıklayın.

7. **Sistem Güvenliği**’ni seçin ve **Parola** ayarlarını girin. Bu öğretici için aşağıdaki önerilen ayarları seçin:

   - **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerektir** olarak belirleyin.

   - **Basit parolalar** için **Engelle**’yi seçin.

   - **En düşük parola uzunluğu**’nu **4** olarak ayarlayın.

     > [!TIP]
     > Gri olan ve italik olan varsayılan değerler yalnızca önerilerdir. Bir ayarı yapılandırmak için öneriler olan değerleri değiştirmelisiniz.

   - **Gerekli parola türü** için **Alfasayısal**’ı seçin.

   - **Ekran kilitlendiğinde parola istenmeden önce geçmesi gereken en yüksek dakika sayısı** için **Hemen**’i seçin.

   - **Parola zaman aşımı (gün)** için **41** değerini girin.

   - **Yeniden kullanımı önlemek için önceki parola sayısı** için **5** değerini girin.
 
   ![E-posta uyumluluk ilkesi için parola ayarlarını belirleme](./media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. **Tamam**’ı ve ardından tekrar **Tamam**’ı seçin.

9. **Oluştur**’u seçin.

## <a name="create-the-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma

Şimdi, tüm cihaz platformlarının Intune 'a kaydolmasını ve Exchange Online 'a erişebilmesi için Intune uyumluluk ilkenize uymasını gerektiren bir koşullu erişim ilkesi oluşturacağız. Ayrıca e-posta erişimi için Outlook uygulamasını gerekli kılacağız. Koşullu erişim ilkeleri, Azure AD portalında veya Intune portalında yapılandırılabilir. Zaten Intune portalında olduğumuz için ilkeyi burada oluşturalım.

1. Intune 'da, **Yeni ilke** > **koşullu erişim** > **uç nokta güvenliği** ' ni seçin.

2. **Ad**Için, **Office 365 e-postası için test ilkesi**girin.

3. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

4. **Atamalar**' ın altında **bulut uygulamaları veya eylemler**' i seçin. Office 365 Exchange Online e-postalarını korumak istediğimiz için şu adımları izleyeceğiz:

   1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.

   2. **Seçin** öğesini belirleyin. 

   3. Uygulamalar listesinde **Office 365 Exchange Online**’a ve ardından **Seç**’e tıklayın. 

   4. **Bitti**’yi seçin.
  
   ![Office 365 Exchange Online uygulamasını seçin](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.

   1. **Yapılandır** altında **Evet**’i seçin.

   2. **Dahil et** sekmesinde **herhangi bir cihaz**seçin ve **bitti**' yi seçin. 

   3. Tekrar **Bitti**’yi seçin.

   ![Herhangi bir cihazı dahil et](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. **Atamalar** altında **Koşullar** > **İstemci uygulamaları**’nı seçin.

   1. **Yapılandır** altında **Evet**’i seçin.

   2. Bu öğretici için **Mobil uygulamalar ve masaüstü istemciler**’i ve **Modern kimlik doğrulaması istemcileri**’ni (iOS için Outlook ve Android için Outlook gibi uygulamaları ifade eder) seçin. Diğer tüm onay kutularının işaretini kaldırın.

   3. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.

   ![Uygulamaları ve istemcileri seçin](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. **Erişim denetimleri** altında **Ver**’i seçin.

   1. **Ver** bölmesinde **Erişim ver**’i seçin.

   2. **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin.

   3. **Onaylı istemci uygulaması gerektir**’e tıklayın.

   4. **Çoklu denetim için** altında **Tüm seçili denetimleri gerektir**’i seçin. Bu ayar, bir cihaz e-postaya erişmeye çalıştığında seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.

   5. **Seçin** öğesini belirleyin.

   ![Denetimleri Seç](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. **İlkeyi etkinleştir** altında **Açık**’ı seçin.

   ![İlkeyi etkinleştirme](./media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. **Oluştur**’u seçin.

## <a name="try-it-out"></a>Deneme

Oluşturduğunuz ilkelerle, Office 365 e-postasına oturum açmayı deneyen tüm iOS cihazlarının Intune 'a kaydolması ve iOS için Outlook Mobile App/ıpados kullanması gerekir. Bu senaryoyu bir iOS cihazda test etmek için test kiracınızdaki kullanıcılardan birine ait kimlik bilgilerini kullanarak Exchange Online’da oturum açmayı deneyin. Cihazı kaydetmeniz ve Outlook mobil uygulamasını yüklemeniz istenecektir.

1. Bu testi bir iPhone’da yapmak için **Ayarlar** > **Parolalar ve Hesaplar** > **Hesap Ekle** > **Exchange**’i seçin.

2. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.

3. **Oturum Aç**’a basın.

4. Test kullanıcısının parolasını girin ve **Oturum aç**’a basın.

5. Kaynağa erişmek için cihazınızı kaydetmeniz gerektiğini belirten bir iletinin yanında kaydolma seçeneği görüntülenecektir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Test ilkelerine artık ihtiyacınız kalmadığında bunları kaldırabilirsiniz.
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) genel yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.

2. **Uyumluluk ilkeleri** > **cihazları** seçin.

3. **İlke Adı** listesinde test ilkenizin açılır menüsünü (**...**) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Tamam**’ı seçin.

4. **Uç nokta güvenliği** > **koşullu erişim**' i seçin.

5. **İlke Adı** listesinde test ilkenizin açılır menüsünü (**...**) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Evet**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, iOS cihazların Exchange Online e-postalarına erişmek için Intune’a kaydolmasını ve Outlook uygulamasını kullanmasını gerektiren ilkeler oluşturdunuz. Intune 'u, Office 365 Exchange Online için Exchange ActiveSync istemcileri de dahil olmak üzere diğer uygulama ve hizmetleri korumak için koşullu erişimle kullanma hakkında bilgi edinmek için bkz. [koşullu erişimi ayarlama](conditional-access.md).
