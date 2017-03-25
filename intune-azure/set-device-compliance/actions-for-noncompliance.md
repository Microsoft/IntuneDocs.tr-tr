---
title: "Uyumsuzluğa yönelik eylemler"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Uyumsuz cihazlara yönelik eylem oluşturmayı öğrenin"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Uyumsuzluğa yönelik eylem oluşturma

**Uyumsuzluğa yönelik eylemler**, uyumluluğu bozulan cihazlara uygulanacak zamana göre sıralı bir dizi eylem yapılandırmanıza olanak sağlar. Örneğin, uyumlu olmayan cihazların kullanıcılarını e-posta yoluyla bilgilendirebilir veya koşullu erişim aracılığıyla bu cihazların kurumsal kaynaklara erişimini engelleyebilirsiniz.

## <a name="use-case-scenario"></a>Kullanım örneği senaryosu

Varsayılan olarak, bir cihaz Intune cihaz uyumluluk ilkesi tarafından uyumsuz olarak bildirildiğinde koşullu erişim, cihazı hemen engeller ve kullanıcı uyumlu olunmasına yönelik yönergeler içeren bir e-posta alır. **Uyumsuzluğa yönelik eylemler**, uyumlu olmayan bir cihazla ilgili ne yapılması gerektiğine karar verirken daha fazla esneklik sağlar. Örneğin, cihazı hemen engellememeye karar verebilir ve kullanıcıya uyumlu hale gelmesi için bir yetkisiz kullanım süresi tanıyabilirsiniz.

İki tür eylem vardır:

-   Kullanıcıyı e-posta yoluyla bilgilendirme

-   Koşullu erişim aracılığıyla kurumsal kaynaklara erişimi engelleme

## <a name="notify-the-user-via-email"></a>Kullanıcıyı e-posta yoluyla bilgilendirme

Önceden oluşturulan varsayılan e-posta şablonları arasından seçim yapabilir veya tam olarak özelleştirilmiş bir e-posta bildirimi oluşturabilirsiniz. Konu, ileti gövdesi, şirket logosunun dahil edilmesi, iletişim bilgileri ve ek alıcılar ile ilgili özelleştirme yapılmasına olanak sağlanır.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Koşullu erişim aracılığıyla kurumsal kaynaklara erişimi engelleme

Cihazın kurumsal kaynaklara erişiminin engelleneceği, gün sayısı cinsinden bir zamanlama belirleyebilirsiniz. Bu engelleme anında olabilir, ancak kullanıcıya cihaz uyumluluk ilkeleri ile uyumlu hale gelmesi için bir yetkisiz kullanım süresi de tanıyabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Uyumsuzluğa yönelik eylem ayarlanabilmesi için en az bir adet cihaz uyumluluk ilkesi oluşturulmuş olmalıdır.

-   Aşağıdakiler için cihaz uyumluluk ilkesi oluşturmayı öğrenin:

    -   [Outlook Web Access (OWA)](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Cihaz uyumluluk ilkelerini kullanarak cihazların kurumsal kaynakları kullanmasını engellemeyi planlıyorsanız EMS koşullu erişiminin ayarlanıp hazır edilmiş olması gerekir.

- [EMS koşullu erişiminin kurulumunu yapmayı](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access) öğrenin.

Ek olarak, bir bildirim iletisi şablonu oluşturulmuş olmalıdır. Bildirim iletisi şablonu, uyumsuzluğa yönelik eylem oluşturma sürecinde kullanıcılarınıza e-posta göndermek için kullanılır.

### <a name="to-add-a-notification-message-template"></a>Bildirim iletisi şablonu eklemek için

**Cihaz uyumluluk ilkeleri** dikey penceresinde:

1.  **Yönet**’in altında **Bildirimler**’i seçin. Bildirim iletisi şablonları dikey penceresi açılır.

    ![Bildirim şablonu ekleme](../media/afnc-1.png)

2.  **Ekle**’yi seçin. Aşağıdakileri tanımlamanız gerekir:

    a.  Açıklama

    b.  Başlangıç

    c.  Konu

    d.  İleti

    e.  E-posta üst bilgisi – Şirket logosunu ekle

    f.  E-posta alt bilgisi – Şirket adını ekle

    g.  E-posta alt bilgisi – İletişim bilgilerini ekle

     ![Bildirim iletisi şablonu](../media/afnc-2.png)

Bilgi eklemeyi bitirdikten sonra **Oluştur**’a tıklayabilirsiniz. Bildirim iletisi şablonu kullanıma hazırdır.

> [!NOTE] 
> Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

## <a name="to-create-actions-for-non-compliance"></a>Uyumsuzluğa yönelik eylem oluşturmak için

Yeni bir cihaz uyumluluk ilkesi oluştururken veya mevcut bir cihaz uyumluluk ilkesini düzenleyerek bir eylem ekleyebilirsiniz.

1.  **Cihaz uyumluluk ilkeleri** dikey penceresinde **Yönet**’in altında **İlkeler**’i seçin.

2.  Üzerine tıklayarak bir cihaz uyumluluk ilkesini seçin.

    ![Uyumluluk ilkeleri](../media/afnc-3.png)

3.  **Cihaz uyumluluk ilkesi özellikleri** dikey penceresi açılır. **Uyumsuzluğa yönelik eylemler**’i seçin.

4.  Uyumsuzluğa yönelik eylemler dikey penceresi açılır. Eylem parametrelerini belirlemek için **Ekle**’yi seçin.

    ![Uyumsuzluğa yönelik eylemler dikey penceresi](../media/afnc-4.png)

Uyumsuzluğa yönelik eylemler şunlardır:

-   **Koşullu erişim ilkesini zorlama**

-   **Son kullanıcıya e-posta gönderme**

### <a name="enforce-conditional-access-policy"></a>Koşullu erişim ilkesini zorlama

Bu uyumsuzluğa yönelik eylemi eklemek için:

1.  **Uyumsuzluğa yönelik eylemler** dikey penceresinde **Ekle**’yi seçin.

2.  **Eylem parametreleri** dikey penceresindeki Eylem açılan listesinde **Koşullu erişim ilkesini zorla**’yı seçin.

3.  **Zamanlama** kısmında koşullu erişim ilkesinin kaç gün sonra (0-255) uygulanacağını belirtebilirsiniz. Gün sayısı olarak **0** belirtilmesi, cihaz uyumluluk ilkeleriyle uyumsuz hale gelen cihazların kurumsal kaynaklara erişiminin koşullu erişim tarafından **hemen** engelleneceği anlamına gelir.

    ![Uyumsuzluğa yönelik eylemleri zamanlama](../media/afnc-5.png)

4.  **Eylemler** dikey penceresinde **Ekle**’yi ve sonra **Tamam**’ı seçin.

5.  **Cihaz uyumluluk ilkesi özellikleri** dikey penceresinde **Kaydet**’i seçin.

### <a name="send-e-mail-to-end-user"></a>Son kullanıcıya e-posta gönderme

Uyumlu olmayan kullanıcılara bildirim göndermek üzere bir e-posta şablonu kullanabilirsiniz. Bu e-postalar, kuruluş genelinde cihaz uyumluluğu sağlamaya yardımcı olur.

Bu uyumsuzluğa yönelik eylemi eklemek için:

1.  **Uyumsuzluğa yönelik eylemler** dikey penceresinde **Ekle**’yi seçin.

2.  **Eylem parametreleri** dikey penceresindeki Eylem açılan listesinde **Son kullanıcıya e-posta gönder**’i seçin.

3.  **İleti şablonu**’na tıklayarak daha önce oluşturulmuş bir ileti şablonunu seçin. İleti şablonu içeriğini görüntüleyebilir ve ardından **Seç**’e tıklayabilirsiniz.

    ![İleti şablonu](../media/afnc-6.png)

> [!NOTE] 
> İleti şablonunu görüntüleyebilir ancak düzenleyemezsiniz. İleti şablonunu düzenlemek istiyorsanız **Bildirimler** dikey penceresine geri dönmeniz gerekir.

1.  **Zamanlama** kısmında e-postanın kullanıcılara uyumsuzluktan kaç gün sonra gönderileceğini girin. Gün sayısı olarak **0** belirtilmesi, e-postanın **hemen** gönderileceği anlamına gelir.

2.  **Eylemler** dikey penceresinde **Ekle**’yi ve sonra **Tamam**’ı seçin.

3.  **Cihaz uyumluluk ilkesi özellikleri** dikey penceresinde **Kaydet**’i seçin.

