---
title: Hızlı Başlangıç - Uyumsuz cihazlara bildirim gönderme
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta uyumsuz cihazlara e-posta bildirimleri göndermek için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba835eb76dae19a13985a6175b4eceee0bae7f12
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871442"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Hızlı Başlangıç: Bildirimleri uyumsuz cihazlara gönderme

Bu hızlı başlangıçta iş gücünüzün uyumsuz cihazlara sahip üyelerine e-posta bildirimi göndermek için Microsoft Intune’u kullanacaksınız.

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Daha sonra Azure Active Directory (AAD) [koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) cihazı engeller. Bir cihaz uyumlu olmadığında Intune, uyumsuzluk eylemleri eklemenize imkan vererek size karar verme esnekliği sağlar. Örneğin uyumsuz cihazları engellemeden önce kullanıcılara uyumlu olmaları için yetkisiz kullanım süresi sağlayabilirsiniz.

Cihazlar uyumluluk gereksinimlerini karşılamadığında yapabileceğiniz eylemlerden biri, bu son kullanıcılara e-posta göndermektir. Son kullanıcılara göndermeden önce e-posta bildirimini özelleştirebilirsiniz. Özellikle şirket logosu ve kişi bilgileri dahil olmak üzere alıcılar, konu ve ileti gövdesini özelleştirebilirsiniz. Intune ayrıca uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- Cihazların şirket kaynaklarına erişimini engellemek için cihaz uyumluluk ilkeleri kullanıldığında, AAD koşullu erişiminin ayarlanmış olması gerekir. [Cihaz uyumluluk ilkesi oluşturma](quickstart-set-password-length-android.md) hızlı başlangıcını tamamladıysanız Azure Active Directory kullanıyorsunuzdur. AAD hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ve [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal) portalında [Genel yönetici](users-add.md#types-of-administrators) veya Intune [Hizmet yöneticisi](users-add.md#types-of-administrators) olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. Intune’da **Cihaz uyumluluğu** > **Bildirimler** > **Bildirim oluştur**’u seçin. 
2. Aşağıdaki bilgileri girin:

   - **Ad**: *Contoso Yöneticisi*
   - **Konu**: *Cihaz uyumluluğu*
   - **İleti**: *Cihazınız şu anda bizim kuruluşun uyumluluk gereksinimlerini karşılamıyor.*
   - **E-posta üst bilgisi – şirket logosunu Ekle**: Kümesine **etkin** kuruluşunuzun logosu gösterilecek.
   - **Alt bilgisi – şirket adını ekleyin e-posta**: Kümesine **etkin** kuruluşunuzun adını göstermek için.
   - **Alt Bilgisi – iletişim bilgilerini ekleyin e-posta**: Kümesine **etkin** kuruluşunuzun bilgilerini göstermek için.

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/quickstart-send-notification-01.png)

3. Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır.

    > [!NOTE]
    > Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

Şirketinizin adını, şirketinizdeki kişinin bilgilerini ve şirket logosunu ayarlama hakkında ayrıntılar için bkz. [Şirket bilgileri ve gizlilik bildirimi](company-portal-app.md#company-information-and-privacy-statement), [Destek bilgileri](company-portal-app.md#support-information) ve [Şirket kimliği markalama özelleştirmesi](company-portal-app.md#company-identity-branding-customization). 

## <a name="add-a-noncompliance-policy"></a>Uyumsuzluk ilkesi ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Bir cihaz uyumluluk ilkenize uymadığında Intune, bu cihazı otomatik olarak uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Ayrıca, uyumluluk ilkesi oluştururken veya mevcut uyumluluk ilkesini güncelleştirirken başka bir eylem ekleyebilirsiniz. 

Aşağıdaki adımlar, Windows 10 cihazları için uyumluluk ilkesi oluşturmayı gösterir.

1. Intune’da **Cihaz uyumluluğu**’nu seçin.
2. **İlkeler** > **İlke Oluştur**’u seçin.
3. Aşağıdaki bilgileri girin:

   - **Ad**: *Windows 10 uyumluluk*
   - **Açıklama**: *Windows 10 uyumluluk İlkesi*
   - **Platform**: Windows 10 ve üzeri

4. **Ayarlar** > **Sistem Güvenliği**’ni seçerek cihazın güvenlikle ilgili ayarlarını görüntüleyin.
5. **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin. Bu ayar, kullanıcılara mobil cihazlarındaki bilgilere erişim verilmeden önce bu kullanıcılardan parola istenip istenmeyeceğini belirtir. 
6. **En az parola uzunluğu**’nu **6** olarak ayarlayın. Bu ayar, parolada en az kaç rakam veya karakter bulunması gerektiğini belirtir.

    <img alt="System Security settings for a new compliance policy" src="./media/quickstart-send-notification-02.png" width="600">

7. Uyumluluk ilkenizi oluşturmak için **Tamam**, **Tamam** ve **Oluştur**’a tıklayın.
8. **Özellikler** > **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi seçin.
9. Açılan **Eylem** kutusunda **Son kullanıcılara e-posta gönder** seçeneğinin belirlendiğini doğrulayın.
10. Bu konunun öncesinde oluşturduğunuz ileti şablonunu seçmek için **İleti şablonu** > **Contoso Yöneticisi** > **Seçin**’i belirleyin.
11. Seçin **ekleme** > **Tamam** > **Kaydet** yaptığınız değişiklikleri kaydedin.

## <a name="assign-the-policy"></a>İlke atama

Uyumluluk ilkesini belirli bir kullanıcı grubuna veya tüm kullanıcılara atayabilirsiniz. Intune bir cihazın uyumsuz olduğunu algıladığında kullanıcıya uyumluluk ilkesine uyum sağlamak için cihazını güncelleştirmesi gerektiğine dair bir bildirim gider. Aşağıdaki adımlar, ilkeyi atamanızı sağlar.

1. Daha önce oluşturduğunuz **Windows 10 uyumluluk** ilkesini seçin.
2. **Atamalar**’ı seçin.
3. Açılan **Şuna ata** kutusunda **Tüm Kullanıcılar**’ı seçin. Bu eylem, tüm kullanıcıları seçer. **Windows 10 ve üzeri** cihaza sahip olan ve bu uyumluluk ilkesine uymayan tüm kullanıcılara bildirim gönderilir.

    > [!NOTE]
    > Uyumluluk ilkeleri atarken bazı grupları dahil edebilir veya dışlayabilirsiniz.

4. **Kaydet**’e tıklayın.

İlkeyi başarıyla oluşturduktan ve kaydettikten sonra **Cihaz uyumluluğu - İlkeler** listesinde görebilirsiniz. Listede **Atandı** ayarının **Evet** olarak belirlenmiş olduğuna dikkat edin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Windows 10 cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için bir uyumluluk ilkesi oluşturmak ve atamak amacıyla Intune’u kullandınız. Windows cihazları için uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da Windows cihazları için bir cihaz uyumluluk ilkesi ekleme](compliance-policy-create-windows.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Ekleme ve bir istemci uygulama atama](quickstart-add-assign-app.md)
