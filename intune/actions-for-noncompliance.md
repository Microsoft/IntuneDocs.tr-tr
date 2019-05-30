---
title: Microsoft Intune - Azure ile uyumsuzluk iletisi ve eylemleri | Microsoft Docs
description: Uyumlu olmayan cihazlara gönderilmek üzere bir bildirim e-postası oluşturun. Cihaz uyumlu değil olarak işaretlendikten sonraki eylemleri ekleyin. Örneğin uyumluluğu sağlamak için bir yetkisiz kullanım süresi ekleyebilir veya cihaz uyumlu duruma gelene kadar erişimi engellemek için bir zamanlama oluşturabilirsiniz. Bunu yapmak için Azure'da Microsoft Intune’u kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 72a9156ce9b7b1b43acf9b39d9186a52dd6c3e8d
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373702"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>E-postayı otomatikleştirme ve eylemleri uyumsuz cihazlar için Intune'da ekleme

Uyumluluk ilkeleri veya kuralları sağlamayan cihazlarda, eklediğiniz **uyumsuzluğa yönelik Eylemler**. Bu özellik son kullanıcı ile daha fazla e-postayla gönderme gibi eylemleri, zamana göre sıralı bir dizi yapılandırır.

## <a name="overview"></a>Genel Bakış

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Ardından Azure Active Directory (AD) [koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) cihazı engeller. Bir cihaz uyumlu değilse **uyumsuzluğa yönelik eylem** ayrıca esnekliği karar verir. Örneğin, cihazı hemen engellemeyebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

Çeşitli türlerde eylemler vardır:

- **Son kullanıcıya e-posta gönderme**: Son kullanıcıya göndermeden önce bir e-posta bildirimini özelleştirin. Şirket logosu da dahil olmak üzere alıcılar, konu ve ileti gövdesi ve kişi bilgilerini özelleştirebilirsiniz.

    Buna ek olarak Intune, uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

- **Uyumsuz bir cihazı uzaktan kilitleme**: Uyumlu olmayan cihazları uzaktan kilitleme verebilir. Bunun ardından cihazın kilidini açmak için kullanıcıdan PIN veya parola istenir. [Uzaktan Kilitleme](device-remote-lock.md) özelliğinde daha fazla bilgi bulabilirsiniz. 

- **Cihazı uyumsuz işaretle**: Bir zamanlama (gün cinsinden) oluşturun. sonra cihaz uyumsuz olarak işaretlenir. Hemen gerçekleştirilecek eylemi yapılandırabilir veya kullanıcıya uyumlu hale getirmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

Bu makale, şunları nasıl yapacağınızı gösterir:

- İleti bildirimi şablonu oluşturma
- Uyumsuzluk durumları için e-posta gönderme veya cihazı uzaktan kilitleme gibi bir eylem oluşturma


## <a name="before-you-begin"></a>Başlamadan önce

- Uyumsuzluk eylemlerini ayarlamak için, en az bir cihaz uyumluluk ilkesine ihtiyacınız vardır. Cihaz uyumluluk ilkesi oluşturmak için aşağıdaki platformlara bakın:

  - [Android](compliance-policy-create-android.md)
  - [Android iş profilleri](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Cihazların şirket kaynaklarına erişimini engellemek için cihaz uyumluluk ilkeleri kullanıldığında, Azure AD koşullu erişiminin ayarlanmış olması gerekir. Yönergeler için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) veya [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz uyumluluğu** > **Bildirimler**’i seçin.
3. **Bildirim oluştur**’u seçin. Aşağıdaki bilgileri girin:

   - **Ad**
   - **Konu**
   - **İleti**
   - **E-posta üst bilgisi – Şirket logosunu ekleyin**
   - **E-posta alt bilgisi – Şirket adını ekleyin**
   - **E-posta alt bilgisi – İletişim bilgilerini ekleyin**

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/actionsfornoncompliance-1.PNG)

4. Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır. Şirket portalı markası bir parçası olarak karşıya logo, e-posta şablonları için kullanılır. Şirket Portalı markası hakkında daha fazla bilgi için bkz. [Şirket kimliği marka özelleştirme](company-portal-app.md#company-identity-branding-customization).

> [!NOTE]
> Ayrıca, değiştirebilir veya daha önce oluşturulmuş mevcut bir bildirim şablonu güncelleştirin.

## <a name="add-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Bir cihaz cihazlardan birin uyumluluk ilkenize Bu eylem cihazı uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Bu eylem kaldırılamaz.

Ayrıca, uyumluluk ilkesi oluştururken veya mevcut ilkeyi güncelleştirirken başka bir eylem ekleyebilirsiniz. 

1. [Azure portalında](https://portal.azure.com) **Microsoft Intune** > **Cihaz uyumluluğu**'nu açın.
2. **İlkeler**'i seçin, ilkelerinizden birini seçin ve sonra da **Özellikler**'i seçin. 

    Henüz bir ilkeniz yok mu? [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) veya başka bir platform ilkesi oluşturun.
  
    > [!NOTE]
    > JAMF cihazlar ve cihaz grupları tarafından hedeflenen cihazlar, şu anda uyumluluk eylemleri alamaz.

3. **Uyumsuzluk eylemleri** > **Ekle**'yi seçin.
4. İstediğiniz **Eylem**’i seçin: 

    - **Son kullanıcılara e-posta Gönder**: Cihaz uyumsuz olduğunda, kullanıcının e-posta seçin. Ayrıca: 
    
         - Daha önce oluşturduğunuz **İleti şablonunu** seçin
         - Grupları seçerek **Ek alıcılar** girin
    
    - **Uyumsuz bir cihazı uzaktan kilitleme**: Cihaz uyumsuz olduğunda, cihazı kilitler. Bu eylem, kullanıcının bir PIN veya geçiş kodunu cihazın kilidini açmak için girmesini zorlar. 
    
5. Yapılandırma bir **zamanlama**: Kullanıcıların cihazlarında eylemi tetiklemesine uyumsuzluktan sonra (0 ila 365) gün sayısını girin. Bu yetkisiz kullanım süresinden sonra bir koşullu erişim ilkesini zorlayabilirsiniz. Girerseniz **0** gün sonra koşullu erişim (sıfır) sayısı etkinleşir **hemen**. Örneğin, cihaz uyumsuzsa şirket kaynaklarına erişimi hemen engelleyebilirsiniz.

6. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Ekle** > **Tamam**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).
