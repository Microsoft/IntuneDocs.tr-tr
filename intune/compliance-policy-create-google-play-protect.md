---
title: Microsoft Intune ile Google Play Koruması uyumluluğunu etkinleştirme
titleSuffix: ''
description: Google Play Koruması'nı etkinleştirmek için Android cihazlarına uyumluluk ilkesi oluşturmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6c92115b3e5b5c0f13f60b7483905fef2f73c637
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230678"
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Google Play Koruması'nı etkinleştirmek için cihaz uyumluluk ilkesi oluşturma

Android platformu için yeni bir uyumluluk ilkesi oluşturarak Google Play Koruması (GPP) uyumluluğunu denetleyebilirsiniz.

Bu ayarları gerektiren uyumluluk ilkesi daha sonra bir grup Android kullanıcısı veya cihazını hedefleyebilir. Bu ayarların etkinleştirilmediği bir cihaz, uyumluluğun dışında kalır.

## <a name="create-a-compliance-policy"></a>Uyumluluk ilkesi oluşturma

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
2. **Yönet** grubunda **Cihaz uyumluluğu**'nu seçin. 
3. **İlkeler**'i ve **İlke oluştur**'u seçin.
4. İlke için **Ad** ve **Açıklama** yazın.
5. Platform olarak **Android**’i seçin.
6. **Ayarlar** > **Cihaz Durumu**'nu seçin.
7. **Google Play Koruması** ayarlarını yapılandırın.
8. Google Play Koruması ayarlarını yaptıktan sonra, **Sistem Güvenliği** ve **Cihaz Özellikleri** ayarlarını belirtin. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="configure-the-google-play-protect-settings"></a>Google Play Koruması ayarlarını yapılandırma

 - **Google Play Hizmetleri yapılandırıldı**  
   Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını gerektirir. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır.
 - **Güncel güvenlik sağlayıcısı**  
   Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını gerektirir.
 - **Uygulamalarda tehdit taraması**  
   Android **Uygulamaları Doğrula** özelliğinin etkinleştirilmesini gerektirir.
    > [!Note]  
    > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir. Android iş profilleri olan cihazlarda bu ayar, bir yapılandırma ilkesi ayarı olarak bulunabilir. Bu, yöneticilerin ayarı cihaz için etkinleştirmesine olanak tanır.

    Kuruluşunuzda Android iş profilleri kullanılıyorsa, kayıtlı cihazlarınız için **Uygulamalarda tehdit taraması**’nı etkinleştirebilirsiniz. Bir cihaz profili oluşturun ve sistem güvenlik ayarının gerekli olmasını sağlayın. Daha fazla bilgi için bkz. [Microsoft Intune’da Android iş profili cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

 - **SafetyNet cihaz kanıtı**  
   Uyulması gereken SafetyNet cihaz kanıtı bütünlük düzeyini ayarlayın. Düzeyler şunlardır: **Yapılandırılmadı**, **Temel bütünlüğü denetle** ve **Temel bütünlüğü ve sertifikalı cihazları denetle**.




## <a name="next-steps"></a>Sonraki adımlar

Intune cihaz uyumluluk ilkeleriyle çalışma hakkında daha fazla bilgi için bkz. [Intune cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).
