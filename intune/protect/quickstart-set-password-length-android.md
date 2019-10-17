---
title: Hızlı başlangıç-Android cihazları için parola uyumluluk ilkesi
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta Android cihazlar için gerekli parola uzunluğunu ayarlamak için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
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
ms.openlocfilehash: f73bc84be46252cb99a47966b480e585545dde12
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504173"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Hızlı Başlangıç: Android cihazları için parola uyumluluk ilkesi oluşturma

Bu hızlı başlangıçta Microsoft Intune kullanarak iş gücünüzdeki Android kullanıcılarının Android cihazlarındaki bilgilere erişim kazanmak için belirli uzunluğa sahip parolalar girmesini gerektireceksiniz. 

Intune cihaz uyumluluk ilkesi, cihazların uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları belirtir. Şirket kaynaklarına erişim izni vermek veya erişimi engellemek için, koşullu erişimle uyumluluk ilkelerini kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz.

> [!IMPORTANT]
> İş gücünüzü korumak için parola ayarlarına ek olarak diğer sistem güvenlik ayarlarını da göz önünde bulundurmalısınız. Daha fazla bilgi için bkz. [Sistem güvenlik ayarları](compliance-policy-create-android-for-work.md).

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. 

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

Bu hızlı başlangıçta iş gücünüzdeki Android kullanıcılarının Android cihazlarındaki bilgilere erişim kazanmak için belirli uzunluğa sahip parolalar girmesini gerekli kılmak amacıyla Intune’u kullanacaksınız.

1. Intune’da **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. **Ad** olarak **Android uyumluluğu** yazın. Ayrıca bir **Açıklama** girin.
3. **Platform** olarak **Android**’i seçin. 
4. **Ayarlar** > **Sistem Güvenliği**’ni seçerek Android **Sistem Güvenliği** dikey penceresini görüntüleyin.
5. **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin.
6. **Gerekli parola türü**' nün yanında **en az sayısal** ' ı seçin.
7. **En düşük parola uzunluğu** olarak **6** değerini girin. 

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. İşiniz bittiğinde **Tamam** > **Tamam** > **Oluştur**’a tıklayarak ilkeyi oluşturun.

İlkeyi başarıyla oluşturduktan sonra bunu cihaz uyumluluğu ilkeleri listenizde görebilirsiniz. 

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık gerekli olmadığında, ilkeyi silin. Bunu yapmak için uyumluluk ilkesini seçin ve **Sil**’e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Android cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için Intune’u kullanarak bir uyumluluk ilkesi oluşturdunuz. Uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Uyumsuz cihazlara bildirim gönderme](../quickstart-send-notification.md)
