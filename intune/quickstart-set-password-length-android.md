---
title: Hızlı Başlangıç - Android cihazları için parola uyumluluk ilkesi oluşturma
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta Android cihazlar için gerekli parola uzunluğunu ayarlamak için Microsoft Intune’u kullanacaksınız.
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
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4a16272f32b8546e7e9bb12a22f16235ab49aed
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799667"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Hızlı Başlangıç: Android cihazlar için parola uyumluluk ilkesi oluşturma

Bu hızlı başlangıçta Microsoft Intune kullanarak iş gücünüzdeki Android kullanıcılarının Android cihazlarındaki bilgilere erişim kazanmak için belirli uzunluğa sahip parolalar girmesini gerektireceksiniz. 

Intune cihaz uyumluluk ilkesi, cihazların uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları belirtir. Bu uyumluluk ilkelerini şirket kaynaklarına erişime izin vermek veya bunu engellemek için koşullu erişim ile birlikte kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz.

> [!IMPORTANT]
> İş gücünüzü korumak için parola ayarlarına ek olarak diğer sistem güvenlik ayarlarını da göz önünde bulundurmalısınız. Daha fazla bilgi için bkz. [Sistem güvenlik ayarları](compliance-policy-create-android-for-work.md#system-security-settings).

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. 

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

Bu hızlı başlangıçta iş gücünüzdeki Android kullanıcılarının Android cihazlarındaki bilgilere erişim kazanmak için belirli uzunluğa sahip parolalar girmesini gerekli kılmak amacıyla Intune’u kullanacaksınız.

1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. **Ad** olarak **Android uyumluluğu** yazın. Ayrıca bir **Açıklama** girin.
3. **Platform** olarak **Android**’i seçin. 
4. **Ayarlar** > **Sistem Güvenliği**’ni seçerek Android **Sistem Güvenliği** dikey penceresini görüntüleyin.
5. **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin.
6. Seçin **en az sayısal** yanındaki **gerekli parola türü**.
7. **En düşük parola uzunluğu** olarak **6** değerini girin. 

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. İşiniz bittiğinde **Tamam** > **Tamam** > **Oluştur**’a tıklayarak ilkeyi oluşturun.

İlkeyi başarıyla oluşturduktan sonra bunu cihaz uyumluluğu ilkeleri listenizde görebilirsiniz. 

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık gerekli olmadığında, ilkeyi silin. Bunu yapmak için uyumluluk ilkesini seçin ve **Sil**’e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Android cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için Intune’u kullanarak bir uyumluluk ilkesi oluşturdunuz. Uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Bildirimleri göndermek için uyumsuz cihazlar](quickstart-send-notification.md)
