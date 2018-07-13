---
title: Microsoft Intune - Azure ile uyumsuzluk iletisi ve eylemleri | Microsoft Docs
description: Uyumlu olmayan cihazlara gönderilmek üzere bir bildirim e-postası oluşturun. Cihaz uyumlu değil olarak işaretlendikten sonraki eylemleri ekleyin. Örneğin uyumluluğu sağlamak için bir yetkisiz kullanım süresi ekleyebilir veya cihaz uyumlu duruma gelene kadar erişimi engellemek için bir zamanlama oluşturabilirsiniz. Bunu yapmak için Azure'da Microsoft Intune’u kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3c8bc523f2796f8af7cb4801cdb13a60b7e2eb5d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905742"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme - Intune

Zamana göre sıralanmış bir eylem dizisi yapılandıran bir **Uyumsuzluk eylemleri** özelliği vardır. Bu eylemler, uyumluluk ilkenize uymayan cihazlara uygulanır. 

## <a name="overview"></a>Genel bakış
Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Ardından Azure Active Directory (AD) [koşullu erişimi](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) cihazı engeller. Cihaz uyumlu olmadığında, **uyumsuzluk eylemleri** size karar verme esnekliği de sağlar. Örneğin, cihazı hemen engellemeyebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

İki tür eylem vardır:

- **Son kullanıcıları e-posta ile bilgilendir**: Son kullanıcıya göndermeden önce e-posta bildirimini özelleştirin. Şirket logosu da dahil olmak üzere alıcılar, konu ve ileti gövdesi ve kişi bilgilerini özelleştirebilirsiniz.

    Buna ek olarak Intune, uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

- **Cihazı uyumsuz olarak işaretle**: Cihazın kaç gün sonra uyumsuz olarak işaretleneceğini gösteren bir zamanlama (gün sayısı cinsinden) oluşturun. Hemen gerçekleştirilecek eylemi yapılandırabilir veya kullanıcıya uyumlu hale getirmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

- Uyumsuzluk eylemlerini ayarlamak için, en az bir cihaz uyumluluk ilkesine ihtiyacınız vardır. Cihaz uyumluluk ilkesi oluşturmak için aşağıdaki platformlara bakın:

  - [Android](compliance-policy-create-android.md)
  - [Android iş profilleri](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Cihazların şirket kaynaklarına erişimini engellemek için cihaz uyumluluk ilkeleri kullanıldığında, Azure AD koşullu erişiminin ayarlanmış olması gerekir. Yönergeler için [Azure Active Directory'de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) konusuna bakın.

- Bildirim iletisi şablonu oluşturulmalıdır. Kullanıcılarınıza e-posta göndermek için, bu şablon kullanılarak uyumsuzluk eylemleri oluşturulur.

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın. 
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz uyumluluğu**'nu ve ardından **Bildirimler**'i seçin. 
4. **Bildirim oluştur**’u seçin ve ardından aşağıdaki bilgileri girin:

   - Ad
   - Konu
   - İleti
   - E-posta üst bilgisi – Şirket logosunu ekleyin
   - E-posta alt bilgisi – Şirket adını ekleyin
   - E-posta alt bilgisi – İletişim bilgilerini ekleyin

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/actionsfornoncompliance-1.PNG)

Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır.

> [!NOTE]
> Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

## <a name="add-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler ekleme

Varsayılan olarak, Intune uyumluluğa yönelik eylemi otomatik olarak oluşturur. Cihazlardan birin uyumluluk ilkenize uymadığında, bu eylem cihazı uyumsuz olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Bu eylem kaldırılamaz.

Yeni bir uyumluluk ilkesi oluştururken veya mevcut uyumluluk ilkesini düzenlerken eylem ekleyebilirsiniz. 

1. [Azure portalında](https://portal.azure.com) **Microsoft Intune**'u açın ve **Cihaz uyumluluğu**'nu seçin.
2. **İlkeler**'i seçin, ilkelerinizden birini seçin ve sonra da **Özellikler**'i seçin. 

  Henüz bir ilkeniz yok mu? [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) veya başka bir platform ilkesi oluşturun.
  
  > [!NOTE]
  > JAMF cihazlar ve cihaz grupları tarafından hedeflenen cihazlar, şu anda uyumluluk eylemleri alamaz.

3. **Uyumsuzluk eylemleri**'ni seçin ve ardından **Ekle**'yi seçerek eylem parametrelerini girin. Önceden oluşturulmuş ileti şablonunu seçebilir, ek alıcılar ekleyebilir ve yetkisiz kullanım süresi zaman çizelgesini güncelleştirebilirsiniz. Zaman çizelgesinde gün sayısını (0 - 365 arası) girebilir ve daha sonra koşullu erişim ilkelerini zorlayabilirsiniz. Gün sayısı olarak **0** girerseniz, koşullu erişim şirket kaynaklarına erişimi **hemen** engeller.

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Ekle** > **Tamam**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar
Raporları çalıştırarak cihaz uyumluluk etkinliğini izleyin. [Intune ile cihaz uyumluluğunu izleme](device-compliance-monitor.md) başlığı altında bazı yönergeler sağlanır.
