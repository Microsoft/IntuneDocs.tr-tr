---
title: Microsoft Intune - Azure ile uyumsuzluk iletisi ve eylemleri | Microsoft Docs
description: Uyumlu olmayan cihazlara gönderilmek üzere bir bildirim e-postası oluşturun. Cihaz uyumlu değil olarak işaretlendikten sonraki eylemleri ekleyin. Örneğin uyumluluğu sağlamak için bir yetkisiz kullanım süresi ekleyebilir veya cihaz uyumlu duruma gelene kadar erişimi engellemek için bir zamanlama oluşturabilirsiniz. Bunu yapmak için Azure'da Microsoft Intune’u kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 953b468337d3317027344573d147b65d765e3db3
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236450"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme - Intune

Zamana göre sıralanmış bir eylem dizisi yapılandıran bir **Uyumsuzluk eylemleri** özelliği vardır. Bu eylemler, uyumluluk ilkenize uymayan cihazlara uygulanır. 

## <a name="overview"></a>Genel bakış
Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Ardından Azure Active Directory (AD) [koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) cihazı engeller. Cihaz uyumlu olmadığında, **uyumsuzluk eylemleri** size karar verme esnekliği de sağlar. Örneğin, cihazı hemen engellemeyebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

Çeşitli türlerde eylemler vardır:

- **Son kullanıcıya e-posta gönder**: Son kullanıcıya göndermeden önce e-posta bildirimini özelleştirin. Şirket logosu da dahil olmak üzere alıcılar, konu ve ileti gövdesi ve kişi bilgilerini özelleştirebilirsiniz.

    Buna ek olarak Intune, uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

- **Uyumsuz cihazları uzaktan kilitle**: Uyumsuz cihazlar için uzaktan kilitleme komutu gönderebilirsiniz. Bunun ardından cihazın kilidini açmak için kullanıcıdan PIN veya parola istenir. [Uzaktan Kilitleme](device-remote-lock.md) özelliğinde daha fazla bilgi bulabilirsiniz. 

- **Cihazı uyumsuz olarak işaretle**: Cihazın kaç gün sonra uyumsuz olarak işaretleneceğini gösteren bir zamanlama (gün sayısı cinsinden) oluşturun. Hemen gerçekleştirilecek eylemi yapılandırabilir veya kullanıcıya uyumlu hale getirmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

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

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz uyumluluğu** > **Bildirimler**’i seçin.
3. **Bildirim oluştur**’u seçin. Aşağıdaki bilgileri girin:

   - **Ad**
   - **Konu**
   - **İleti**
   - **E-posta üst bilgisi – Şirket logosunu ekleyin**
   - **E-posta alt bilgisi – Şirket adını ekleyin**
   - **E-posta alt bilgisi – İletişim bilgilerini ekleyin**

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/actionsfornoncompliance-1.PNG)

4. Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır. Şirket Portalı markasının bir parçası olarak yüklediğiniz logonun e-posta şablonlarında kullanılacağını unutmayın. Şirket Portalı markası hakkında daha fazla bilgi için bkz. [Şirket kimliği marka özelleştirme](company-portal-app.md#company-identity-branding-customization).  

> [!NOTE]
> Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

## <a name="add-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Cihazlardan birin uyumluluk ilkenize uymadığında, bu eylem cihazı uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Bu eylem kaldırılamaz.

Ayrıca, uyumluluk ilkesi oluştururken veya mevcut ilkeyi güncelleştirirken başka bir eylem ekleyebilirsiniz. 

1. [Azure portalında](https://portal.azure.com) **Microsoft Intune** > **Cihaz uyumluluğu**'nu açın.
2. **İlkeler**'i seçin, ilkelerinizden birini seçin ve sonra da **Özellikler**'i seçin. 

    Henüz bir ilkeniz yok mu? [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) veya başka bir platform ilkesi oluşturun.
  
    > [!NOTE]
    > JAMF cihazlar ve cihaz grupları tarafından hedeflenen cihazlar, şu anda uyumluluk eylemleri alamaz.

3. **Uyumsuzluk eylemleri** > **Ekle**'yi seçin.
4. İstediğiniz **Eylem**’i seçin: 

    - **Son kullanıcıya e-posta gönder**: Cihaz uyumsuz olduğunda kullanıcıya e-posta göndermek için bunu seçin. Ayrıca: 
    
         - Daha önce oluşturduğunuz **İleti şablonunu** seçin
         - Grupları seçerek **Ek alıcılar** girin
    
    - **Uyumsuz cihazları uzaktan kilitle**: Cihaz uyumsuz olduğunda cihazı kilitleyin. Bu seçenek cihazın kilidini açmak için kullanıcıyı PIN veya parola girmeye zorlar. 
    
    - **Zamanla**: Eylemi kullanıcının cihazında tetiklemek için uyumsuzluktan sonra geçecek gün sayısını (0 - 365) girin. Bu yetkisiz kullanım süresinden sonra bir koşullu erişim ilkesini zorlayabilirsiniz. Gün sayısı olarak **0** girerseniz, koşullu erişim **hemen** geçerlilik kazanır. Örneğin, cihaz uyumsuzsa şirket kaynaklarına erişimi hemen engelleyebilirsiniz.

5. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Ekle** > **Tamam**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Cihaz uyumluluk etkinliğini izleme](device-compliance-monitor.md).
