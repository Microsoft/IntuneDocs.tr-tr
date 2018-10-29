---
title: Hızlı Başlangıç - Android cihazlar için gerekli parola uzunluğu ayarlama
titlesuffix: Microsoft Intune
description: Bu hızlı başlangıçta Microsoft Intune kullanarak Android cihazlar için gerekli parola uzunluğunu ayarlayacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395304"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Hızlı Başlangıç: Android cihazlar için gerekli parola uzunluğu ayarlama

Bu hızlı başlangıçta Microsoft Intune kullanarak iş gücünüzdeki Android kullanıcılarının Android cihazlarındaki bilgilere erişim kazanmak için belirli uzunluğa sahip parolalar girmesini gerektireceksiniz. 

> [!IMPORTANT]
> İş gücünüzü korumak için parola ayarlarına ek olarak diğer sistem güvenlik ayarlarını da göz önünde bulundurmalısınız. Daha fazla bilgi için bkz. [Sistem güvenlik ayarları](compliance-policy-create-android-for-work.md#system-security-settings).

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın. Intune, Azure portalında **Tüm hizmetler** > **Intune** seçilerek bulunur. Intune, **İzleme + Yönetim** bölümünde bulunur.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma
1. **Microsoft Intune** dikey penceresini açtıktan sonra **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**’u seçin.
2. **Ad** olarak **Android uyumluluğu** yazın. Ayrıca bir **Açıklama** girin.
3. **Platform** olarak **Android**’i seçin. 
4. **Ayarlar** > **Sistem Güvenliği**’ni seçerek Android **Sistem Güvenliği** dikey penceresini görüntüleyin.
5. **Parola** bölümünde **Mobil cihazların kilidini açmak için parola gerektir**’i **Gerektir** olarak belirleyin.
6. **En düşük parola uzunluğu**’nu **6** olarak ayarlayın.  

    ![Microsoft Intune'da grup oluşturma işleminin ekran görüntüsü](./media/quickstart-set-password-length-android-01.png)

7. İşiniz bittiğinde **Tamam**’a tıklayarak **Sistem Güvenliği** dikey penceresini kapatın. 
8. **Tamam**’a tıklayın ve **Android uyumluluk ilkesi** dikey penceresini kapatın. 
9. **Oluştur**’a tıklayarak ilkeyi oluşturun.

İlkeyi başarıyla oluşturduktan sonra **Cihaz uyumluluğu - İlkeler** listesinde görebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Android cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için Intune’u kullanarak bir uyumluluk ilkesi oluşturdunuz.

> [!div class="nextstepaction"]
> [Intune'da otomatik kayıt kurma](quickstart-setup-auto-enrollment.md)
