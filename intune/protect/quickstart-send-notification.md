---
title: Hızlı Başlangıç - Uyumsuz cihazlara bildirim gönderme
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta, uyumsuz cihazlara e-posta bildirimleri göndermek için Microsoft Intune kullanırsınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410227"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Hızlı Başlangıç: Uyumsuz cihazlara bildirim gönderme

Bu hızlı başlangıçta, uyumsuz cihazlara sahip olan iş gücünüzün üyelerine e-posta bildirimi göndermek için Microsoft Intune kullanacaksınız.

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Azure Active Directory (Azure AD) [koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) daha sonra cihazı engeller. Bir cihaz uyumlu olmadığında Intune, uyumsuzluk için Eylemler eklemenize olanak tanır. Bu, size ne yapacaklarınız için esneklik sağlar. Örneğin uyumsuz cihazları engellemeden önce kullanıcılara uyumlu olmaları için yetkisiz kullanım süresi sağlayabilirsiniz.

Bir cihaz uyumluluğu karşılamıyorsa gerçekleştirilecek bir eylem, cihazlar kullanıcısına e-posta göndermektir. Göndermeden önce bir e-posta bildirimi de özelleştirebilirsiniz. Özellikle şirket logosu ve kişi bilgileri dahil olmak üzere alıcılar, konu ve ileti gövdesini özelleştirebilirsiniz. Intune, e-posta bildiriminde uyumsuz cihaz hakkındaki ayrıntıları da içerir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

Cihazları kurumsal kaynaklardan engellemek için cihaz uyumluluk ilkelerini kullanırken, Azure AD koşullu erişiminin ayarlanması gerekir. [Cihaz uyumluluk Ilkesi oluşturma](quickstart-set-password-length-android.md) hızlı başlangıcı ' nı tamamladıysanız Azure Active Directory kullanıyorsunuz demektir. Azure AD hakkında daha fazla bilgi için bkz. [Azure Active Directory Koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ve [Intune ile koşullu erişim kullanmanın yaygın yolları](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) [genel yönetici](../fundamentals/users-add.md#types-of-administrators) veya Intune [Hizmet Yöneticisi](../fundamentals/users-add.md#types-of-administrators)olarak oturum açın. Bir Intune deneme aboneliği oluşturduysanız, aboneliği oluşturduğunuz hesap genel yöneticime sahip olur.

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. Intune 'da **cihaz** > **Uyumluluk Ilkeleri** > **Bildirimler** **Oluştur > bildirim oluştur**' u seçin.
2. Aşağıdaki bilgileri girin:

   - **Ad**: *Contoso Yöneticisi*
   - **Konu**: *Cihaz uyumluluğu*
   - **İleti**: *cihazınız şu anda kuruluşunuzun uyumluluk gereksinimlerini karşılamıyor.*
   - **E-posta üst bilgisi – Şirket logosunu ekle**: Kuruluşunuzun logosunu göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Şirket adını ekle**: Kuruluşunuzun adını göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Kişi bilgilerini ekle**: Kuruluşunuzdaki kişinin bilgilerini göstermek için **Etkin** olarak ayarlayın.

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. **İleri ' yi** seçin ve bildiriinizi gözden geçirin. **Oluştur** ' u seçin ve bildirim iletisi şablonu kullanıma hazırlanın.

   > [!NOTE]
   > Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

Şirketinizin adını, şirket iletişim bilgilerini ve Şirket logosunu ayarlama hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Şirket bilgileri ve gizlilik bildirimi](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Destek bilgileri](../apps/company-portal-app.md#support-information)
- [Şirket kimliği marka özelleştirmesi](../apps/company-portal-app.md#company-identity-branding-customization).

## <a name="add-a-noncompliance-policy"></a>Uyumsuzluk ilkesi ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Ardından Intune, uyumluluk ilkenize uyduklarında cihazları uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Ayrıca, uyumluluk ilkesi oluştururken veya mevcut uyumluluk ilkesini güncelleştirirken başka bir eylem ekleyebilirsiniz.

Aşağıdaki adımlar, Windows 10 cihazları için uyumluluk ilkesi oluşturmayı gösterir.

1. Intune 'da **cihaz** > **Uyumluluk Ilkeleri** > **ilke oluştur**' u seçin.

2. Aşağıdaki bilgileri girin:

   - **Ad**: *Windows 10 uyumluluk*
   - **Açıklama**: *Windows 10 uyumluluk ilkesi*
   - **Platform**: Windows 10 ve üzeri

3. **Ayarlar** > **Sistem Güvenliği**’ni seçerek cihazın güvenlikle ilgili ayarlarını görüntüleyin.

4. Aşağıdaki seçenekleri yapılandırın:

   - **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin. Bu ayar, kullanıcılara mobil cihazlarındaki bilgilere erişim verilmeden önce bu kullanıcılardan parola istenip istenmeyeceğini belirtir.

   - **En az parola uzunluğu**’nu **6** olarak ayarlayın. Bu ayar, parolada en az kaç rakam veya karakter bulunması gerektiğini belirtir.

   ![Yeni bir uyumluluk ilkesi için Sistem Güvenliği ayarları](./media/quickstart-send-notification/system-security-settings-01.png)

5. Uyumluluk ilkenizi oluşturmak için **tamam** ** > Tamam** > **Oluştur** ' u seçin.

6. **Özellikler** > **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi seçin.

7. Açılan **Eylem** kutusunda **Son kullanıcılara e-posta gönder** seçeneğinin belirlendiğini doğrulayın.

8. **İleti şablonu**' nu, bu makalede daha önce oluşturduğunuz şablonu seçin **ve ardından ileti şablonunu seçin.**

9. Değişikliklerinizi **kaydetmek için > ** **Ekle** ' > **Tamam ' ı** seçin.

## <a name="assign-the-policy"></a>İlke atama

Uyumluluk ilkesini belirli bir kullanıcı grubuna veya tüm kullanıcılara atayabilirsiniz. Intune bir cihazın uyumsuz olduğunu tanırsa, kullanıcıya Uyumluluk ilkesini karşılamak üzere cihazlarını güncelleştirmesi gerektiğini bildirilir. İlkeyi atamak için aşağıdaki adımları kullanın.

1. Intune ' da, **cihazlar** > **uyumluluk ilkeleri** ' ne gidin ve daha önce oluşturduğunuz **Windows 10 uyumluluk** ilkesini seçin.

2. **Atamalar**’ı seçin.

3. Açılan **Şuna ata** kutusunda **Tüm Kullanıcılar**’ı seçin. Bu eylem, tüm kullanıcıları seçer. **Windows 10 ve üzeri** cihaza sahip olan ve bu uyumluluk ilkesine uymayan tüm kullanıcılara bildirim gönderilir.

    > [!NOTE]
    > Uyumluluk ilkeleri atarken bazı grupları dahil edebilir veya dışlayabilirsiniz.

4. **Kaydet**'e tıklayın.

İlkeyi başarıyla oluşturup kaydettikten sonra, **uyumluluk ilkeleri**listesinde görünür. Listede **Atandı** ayarının **Evet** olarak belirlenmiş olduğuna dikkat edin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Windows 10 cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için bir uyumluluk ilkesi oluşturmak ve atamak amacıyla Intune’u kullandınız. Windows cihazları için uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da Windows cihazları için bir cihaz uyumluluk ilkesi ekleme](compliance-policy-create-windows.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: İstemci uygulaması ekleme ve atama](../apps/quickstart-add-assign-app.md)
