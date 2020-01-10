---
title: Microsoft Intune - Azure ile uyumsuzluk iletisi ve eylemleri | Microsoft Docs
description: Uyumlu olmayan cihazlara gönderilmek üzere bir bildirim e-postası oluşturun. Cihaz uyumlu değil olarak işaretlendikten sonraki eylemleri ekleyin. Örneğin uyumluluğu sağlamak için bir yetkisiz kullanım süresi ekleyebilir veya cihaz uyumlu duruma gelene kadar erişimi engellemek için bir zamanlama oluşturabilirsiniz. Bunu yapmak için Azure'da Microsoft Intune’u kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/08/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50478ecb615cf39bba0a205cb06f83e47728e366
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827845"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>Intune 'da e-postayı otomatikleştirin ve uyumsuz cihazlara yönelik eylemler ekleyin

Uyumluluk ilkelerinizi veya kurallarınızı karşılamayan cihazlarda **uyumsuzluk Için eylemler**ekleyebilirsiniz. Bu özellik, son kullanıcıya e-posta gönderme ve daha fazlası gibi zaman sıralı bir eylem dizisi yapılandırır.

## <a name="overview"></a>İlke

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Azure Active Directory (AD) [koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) daha sonra cihazı engeller. Bir cihaz uyumlu olmadığında, **uyumsuzluğa yönelik eylem** , ne yapacaklarınız için esneklik de sağlar. Örneğin, cihazı hemen engellemeyebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

Çeşitli türlerde eylemler vardır:

- **Son kullanıcıya e-posta gönder**: Son kullanıcıya göndermeden önce e-posta bildirimini özelleştirin. Şirket logosu da dahil olmak üzere alıcılar, konu ve ileti gövdesi ve kişi bilgilerini özelleştirebilirsiniz.

    Buna ek olarak Intune, uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

- **Uyumsuz cihazları uzaktan kilitle**: Uyumsuz cihazlar için uzaktan kilitleme komutu gönderebilirsiniz. Bunun ardından cihazın kilidini açmak için kullanıcıdan PIN veya parola istenir. [Uzaktan Kilitleme](../remote-actions/device-remote-lock.md) özelliğinde daha fazla bilgi bulabilirsiniz.

- **Cihazı uyumsuz olarak işaretle**: Cihazın kaç gün sonra uyumsuz olarak işaretleneceğini gösteren bir zamanlama (gün sayısı cinsinden) oluşturun. Hemen gerçekleştirilecek eylemi yapılandırabilir veya kullanıcıya uyumlu hale getirmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

Bu makale, şunları nasıl yapacağınızı gösterir:

- İleti bildirimi şablonu oluşturma
- Uyumsuzluk durumları için e-posta gönderme veya cihazı uzaktan kilitleme gibi bir eylem oluşturma


## <a name="before-you-begin"></a>Başlamadan önce

- Uyumsuzluk eylemlerini ayarlamak için, en az bir cihaz uyumluluk ilkesine ihtiyacınız vardır. Cihaz uyumluluk ilkesi oluşturmak için aşağıdaki platformlara bakın:

  - [Outlook Web Access (OWA)](compliance-policy-create-android.md)
  - [Android iş profilleri](compliance-policy-create-android-for-work.md)
  - [Android](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Cihazları kurumsal kaynaklardan engellemek için cihaz uyumluluk ilkelerini kullanırken, Azure AD koşullu erişiminin ayarlanması gerekir. Rehberlik için [Intune Ile koşullu erişim kullanmanın Azure Active Directory veya genel yollarla](conditional-access-intune-common-ways-use.md) [koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) bölümüne bakın.

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Cihaz** > **Uyumluluk Ilkeleri** > **bildirim oluştur** > **bildirimleri** ' ni seçin.
3. *Temel bilgiler*altında, aşağıdaki bilgileri belirtin:

   - **Ad**
   - **Konu**
   - **İleti**

4. Ayrıca, *temel bilgiler*altında, tüm varsayılan olarak *etkinleştirilecek*olan bildirim için aşağıdaki seçenekleri yapılandırın:

   - **E-posta üst bilgisi – Şirket logosunu ekleyin**
   - **E-posta alt bilgisi – Şirket adını ekleyin**
   - **E-posta alt bilgisi – İletişim bilgilerini ekleyin**

   Şirket Portalı markasının bir parçası olarak karşıya yüklediğiniz logo, e-posta şablonları için kullanılır. Şirket Portalı markası hakkında daha fazla bilgi için bkz. [Şirket kimliği marka özelleştirme](../apps/company-portal-app.md#company-identity-branding-customization).

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/actions-for-noncompliance/actionsfornoncompliance-1.PNG)

   Devam etmek için **İleri** seçeneğini belirleyin.

5. **Gözden geçir + oluştur**altında, bildirim iletisi şablonunun kullanıma hazırsa emin olmak için yapılandırmalarınızı gözden geçirin. Bildirim oluşturmayı tamamladıktan sonra **Oluştur** ' u seçin.

> [!NOTE]
> Ayrıca, daha önce oluşturduğunuz mevcut bir bildirim şablonunu seçebilir ve şablonu güncelleştirmek için bilgilerini **düzenleyebilirsiniz** .

## <a name="add-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Bir cihaz uyumluluk ilkenizi karşımıyorsa, bu eylem cihazı uyumlu değil olarak işaretler. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Bu eylem kaldırılamaz.

Cihazları uyumsuz olarak işaretlemek için varsayılan eyleme ek olarak, bir uyumluluk ilkesi oluşturduğunuzda veya mevcut bir ilkeyi güncelleştirdiğinizde isteğe bağlı eylemler ekleyebilirsiniz.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihaz** > **uyumluluk ilkeleri** > **ilkeleri**' ni seçin, Ilkelerinizin birini seçin ve ardından **Özellikler**' i seçin.

   Henüz bir ilkeniz yok mu? [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) veya başka bir platform ilkesi oluşturun.

   > [!NOTE]
   > JAMF cihazlar ve cihaz grupları tarafından hedeflenen cihazlar, şu anda uyumluluk eylemleri alamaz.

3. **Uyumsuzluk eylemleri** > **Ekle**'yi seçin.

4. İstediğiniz **Eylem**’i seçin:

   - **Son kullanıcıya e-posta gönder**: Cihaz uyumsuz olduğunda kullanıcıya e-posta göndermek için bunu seçin. Ayrıca:
     - Daha önce oluşturduğunuz **İleti şablonunu** seçin
     - Grupları seçerek **Ek alıcılar** girin

   - **Uyumsuz cihazları uzaktan kilitle**: Cihaz uyumsuz olduğunda cihazı kilitleyin. Bu eylem, kullanıcının cihazın kilidini açmak için bir PIN veya geçiş kodu girmesini zorlar.

5. **Zamanlama**yapılandırma: kullanıcıların cihazlarında eylemi tetiklemek için uyumsuzluktan sonra geçen gün sayısını (0-365) girin. Bu yetkisiz kullanım süresinden sonra [koşullu erişim](conditional-access-intune-common-ways-use.md) ilkesini zorunlu kılabilirsiniz. **0** (sıfır) gün sayısı girerseniz, koşullu erişim **hemen**yürürlüğe girer. Örneğin, bir cihaz uyumsuzsa, e-posta, SharePoint ve diğer kuruluş kaynaklarına erişimi doğrudan engellemek için koşullu erişimi kullanın.

   Bir uyumluluk ilkesi oluşturduğunuzda, **cihaz uyumsuz olarak işaretle** eylemi otomatik olarak oluşturulur ve otomatik olarak **0** güne ayarlanır (hemen). Bu eylemle cihaz iade edildiğinde cihaz hemen uyumlu değil olarak değerlendirilir. Koşullu erişim de kullanılıyorsa, koşullu erişim hemen açılır. Yetkisiz kullanım süresine izin vermek istiyorsanız, **cihazı uyumsuz olarak işaretle** eyleminde **zamanlamayı** değiştirin.

   Uyumluluk ilkenizde, örneğin, kullanıcıya bildirme de isteyebilirsiniz. **Son kullanıcıya e-posta gönder** eylemini ekleyebilirsiniz. Bu **e-posta gönder** eyleminde **zamanlamayı** 2 güne ayarlarsınız. Cihaz veya son kullanıcı hala 2. gün uyumlu değil olarak değerlendiriliyorsa, e-postanız 2. gün gönderilir. Uyumsuzluğu 5. günde yeniden e-posta olarak gönderin ve sonra başka bir eylem ekleyin ve **zamanlamayı** 5 güne ayarlayın.

   Uyumluluk ve yerleşik eylemler hakkında daha fazla bilgi için bkz. [uyumluluğa genel bakış](device-compliance-get-started.md).

6. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Ekle** > **Tamam**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).
