---
title: "Intune ile uyumsuzluğa yönelik eylemler"
titleSuffix: Intune on Azure
description: "Intune ile uyumsuzluğa yönelik eylemler oluşturmayı öğrenin"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573a8b000e63576f3dd3bae1b6e8e8c47733f6bf
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="automate-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemleri otomatikleştirme

**Uyumsuzluğa yönelik eylemler**, uyumluluk ilkesi ölçütlerini sağlamayan cihazlara uygulanacak zamana göre sıralı bir dizi eylem yapılandırmanıza olanak sağlar. Bir cihazın uyumluluk ilkesi ölçütlerini sağlamadığı algılandığında, Intune varsayılan olarak bu cihazı derhal uyumsuz olarak işaretler ve Azure AD Koşullu Erişim de cihazı engeller. **Uyumsuzluğa yönelik eylemler**, uyumlu olmayan bir cihazla ilgili ne yapılması gerektiğine karar verirken daha fazla esneklik sağlar. Örneğin, cihazı hemen engellememeye karar verebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

İki tür eylem vardır:

-   **Son kullanıcıları e-posta ile bilgilendir**: Son kullanıcıya göndermeden önce e-posta bildiriminizi özelleştirebilirsiniz. Intune, şirket logosu da dahil olmak üzere alıcılar, konu ve ileti gövdesi ve kişi bilgilerini özelleştirmenize olanak sağlar.

    Buna ek olarak Intune, uyumsuz cihaz hakkındaki ayrıntıları da e-posta bildiriminde gösterir.

-   **Cihazı uyumsuz olarak işaretle**: Cihazın uyumsuz olarak işaretleneceği gün sayısını belirleyebilirsiniz. Hemen gerçekleştirilecek eylemi yapılandırabilir veya kullanıcıya cihazını uyumluluk ilkelerinizle uyumlu hale getirmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Uyumsuzluğa yönelik eylem ayarlanabilmesi için en az bir adet cihaz uyumluluk ilkesi oluşturulmuş olmalıdır. 

- Aşağıdaki platformlar için cihaz uyumluluk ilkesi oluşturmayı öğrenin:

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [Android](compliance-policy-create-ios.md)
    -   [macOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

Cihaz uyumluluk ilkelerini kullanarak cihazların kurumsal kaynakları kullanmasını engellemeyi planlıyorsanız Azure AD koşullu erişiminin ayarlanıp hazırlanmış olması gerekir. 

- [EMS koşullu erişiminin kurulumunu yapmayı](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access) öğrenin.

Ek olarak, bir bildirim iletisi şablonu oluşturulmuş olmalıdır. Bildirim iletisi şablonu, uyumsuzluğa yönelik eylem oluşturma sürecinde kullanıcılarınıza e-posta göndermek için kullanılır.

### <a name="to-create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturmak için

1. [Azure portalında Intune](https://portal.azure.com)’a gidin ve Intune kimlik bilgilerinizle oturum açın.
2. Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.
3. **Intune**’u seçin
4. **Cihaz uyumluluğu**’nu ve daha sonra **Yönet** bölümü altında **Bildirimler**‘i seçin.
5. **Bildirim oluştur**’u seçin ve aşağıdaki bilgileri girin:
    - Ad
    - Konu
    - İleti
    - E-posta üst bilgisi – Şirket logosunu ekle
    - E-posta alt bilgisi – Şirket adını ekle
    - E-posta alt bilgisi – İletişim bilgilerini ekle

5. **Bildirim oluştur**’u seçin ve aşağıdaki bilgileri girin:

    a. Ad

    b. Konu

    c.  İleti

    d. e-posta üst bilgisi – Şirket logosunu ekleyin

    e. e-posta alt bilgisi – Şirket adını ekleyin

    f. e-posta alt bilgisi – İletişim bilgilerini ekleyin

![bildirim iletisi şablonu örneği](./media/actionsfornoncompliance-1.PNG)

Bilgileri ekledikten sonra **Oluştur**’u seçin. Bildirim iletisi şablonu kullanıma hazırdır.

> [!NOTE]
> Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

## <a name="to-create-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylem oluşturmak için

> [!TIP]
> Intune, varsayılan olarak uyumsuzluk eylemleri bölümünde önceden tanımlı bir eylem sağlar. Bu eylem, cihaz uyumluluk ilkesi ölçütlerinize uymadığı algılanan cihazı uyumsuz olarak işaretler. Algılamanın ardından cihazın ne kadar bir süre sonra uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Eylem kaldırılamaz.

Yeni bir cihaz uyumluluk ilkesi oluştururken veya mevcut cihaz uyumluluk ilkesini düzenleyerek bir eylem ekleyebilirsiniz.

1.  Intune iş yükünde **Cihaz uyumluluk ilkeleri** dikey penceresinden **Yönet** bölümünün altındaki **İlkeler**’i seçin.

2.  Bir cihaz uyumluluk ilkesine tıklayıp seçin, daha sonra **Yönet** bölümünün altındaki **Özellikler**’i seçin.

3.  **Cihaz uyumluluk ilkesi özellikleri** dikey penceresi açılır. **Uyumsuzluğa yönelik eylemler**’i seçin.

4.  **Uyumsuzluğa yönelik eylemler** dikey penceresi açılır. Eylem parametrelerini belirlemek için **Ekle**’yi seçin. Önceden oluşturulmuş ileti şablonunu, ek alıcıları ve mehil süresi zaman çizelgesini seçebilirsiniz. Zaman çizelgesinde gün sayısını (0 ila 365) belirtebilir ve daha sonra koşullu erişim ilkelerini zorlayabilirsiniz. Gün sayısı olarak **0** belirtilmesi, cihaz uyumluluk ilkeleriyle uyumsuz hale gelen cihazların kurumsal kaynaklara erişiminin koşullu erişim tarafından **hemen** engelleneceği anlamına gelir.

5.  Bilgileri ekledikten sonra **Ekle** ve ardından **Tamam**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar
Cihaz uyumluluğu dikey penceresinde bulunan raporları çalıştırarak cihaz uyumluluğu etkinliğini izleyebilirsiniz. Ayrıntılar için bkz. [Intune ile cihaz uyumluluğunu izleme](device-compliance-monitor.md).
