---
title: Quickstart - Password compliance policy for Android devices
titleSuffix: Microsoft Intune
description: In this quickstart, you will use Microsoft Intune to set the length of the password required for Android devices.
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
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 61fdf91d57ce5d187a0c43153f317b0b42c6b46c
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409772"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Hızlı Başlangıç: Android cihazları için parola uyumluluk ilkesi oluşturma

In this quickstart, you'll use Microsoft Intune to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices.

Intune cihaz uyumluluk ilkesi, cihazların uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları belirtir. You can use compliance policies with Conditional Access to allow or block access to company resources. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz.

> [!IMPORTANT]
> İş gücünüzü korumak için parola ayarlarına ek olarak diğer sistem güvenlik ayarlarını da göz önünde bulundurmalısınız. Daha fazla bilgi için bkz. [Sistem güvenlik ayarları](compliance-policy-create-android-for-work.md).

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators).

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

Create a device compliance policy to require your workforce's Android users to enter a password of a specific length before access is granted to information on their Android devices.

1. In Intune, select **Devices** > **Compliance Policies** > **Create Policy**.

2. **Ad** olarak **Android uyumluluğu** yazın. Ayrıca bir **Açıklama** girin.

3. **Platform** olarak **Android Kurumsal**’ı seçin.

4. For **Profile type**, select **Work profile**.

5. **Ayarlar** > **Sistem Güvenliği**’ni seçerek Android **Sistem Güvenliği** dikey penceresini görüntüleyin.

6. **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerektir** olarak belirleyin.

7. For **Required password type**, select **At least numeric**.

8. For **Minimum password length**, enter **6**.

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

9. When done, select **OK** > **OK** > **Create** to create the policy.

When you've successfully created the policy, it appears in your list of device complice policies.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık gerekli olmadığında, ilkeyi silin. Bunu yapmak için uyumluluk ilkesini seçin ve **Sil**’e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Android cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için Intune’u kullanarak bir uyumluluk ilkesi oluşturdunuz. Uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Uyumsuz cihazlara bildirim gönderme](../quickstart-send-notification.md)
