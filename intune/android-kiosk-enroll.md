---
title: Kurulum için ayrılmış Android kuruluş cihazlarının Intune kaydı
titleSuffix: Microsoft Intune
description: Intune'da Android özel Kurumsal cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e980049797ffc3c727d89c197037c019b94326a
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798043"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Ayrılmış Android kuruluş cihazlarının Intune kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Kurumsal adanmış cihazlar çözüm kendine ait, tek kullanımlık bilgi noktası stili cihazları destekler. Bu tür cihazlar tek bir amaca hizmet eder; örneğin dijital işaretler, bilet yazdırma veya envanter yönetimi gibi. Yöneticiler bir cihazın kullanımını sınırlı sayıda uygulama ve web bağlantısına indirger. Ayrıca kullanıcılar başka uygulama ekleyemez veya farklı eylemler gerçekleştiremez.

Intune uygulama ve ayarları Android ayrılmış Kurumsal cihazlara dağıtmanıza yardımcı olur. Belirli Android Enterprise hakkında bilgi için [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Bu şekilde yönettiğiniz cihazlar, bir kullanıcı hesabı olmadan Intune’a kaydolur ve hiçbir son kullanıcı ile ilişkili değildir. Bu cihazlar, kullanıcıya özgü hesap verileri konusunda katı gereksinimleri olan Outlook veya Gmail gibi kişisel kullanım uygulamalarına uygun değildir.

## <a name="device-requirements"></a>Cihaz gereksinimleri

Cihazlar, Android Kurumsal adanmış cihaz yönetilmesini şu gereksinimleri karşılamanız gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Cihazlar Android’in Google Mobile Services (GMS) bağlantısı olan bir dağıtımını çalıştırmalıdır. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Ayrılmış Android Kurumsal cihaz yönetimini ayarlama

Ayrılmış Android Kurumsal cihaz Yönetimi ayarlamak için bu adımları izleyin:

1. Mobil cihazların yönetimine hazırlık olarak, yönergeler için [**Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız](mdm-authority-set.md) gerekir. Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune Kiracı hesabınız için yönetilen Google Play hesabınızı bağlayın](connect-intune-android-enterprise.md).
3. [Bir kayıt profili oluşturun.](#create-an-enrollment-profile)
4. [Bir cihaz grubu oluşturun](#create-a-device-group).
5. [Ayrılmış cihazları kaydetme](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Kayıt profili oluşturma

Böylece adanmış cihazları kaydedebilmeniz için bir kayıt profili oluşturmanız gerekir. Profil oluşturulduktan sonra size bir kayıt belirteci (rastgele dize) ve QR kodu sağlar. Android işletim sistemi ve sürümü cihazın bağlı olarak, belirteç veya QR kodunu kullanabilirsiniz [adanmış cihaz kaydı](#enroll-the-dedicated-devices).

1. Git [Intune portalı](https://portal.azure.com) ve **cihaz kaydı** > **Android kaydını** > **şirketin sahip olduğu adanmış cihazları**.
2. **Oluştur**’u seçin ve gerekli alanları doldurun.
    - **Ad**: Dinamik cihaz grubuna profili atamasını yaparken kullanacağınız bir ad yazın.
    - **Belirteç sona erme tarihi**: Belirtecin süresinin sona erdiği tarih. Google, en fazla 90 günü kabul eder.
3. **Oluştur**’u seçerek profili kaydedin.

### <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma

Uygulama ve ilkeleri, atanmış veya dinamik cihaz gruplarına hedefleyebilirsiniz. Dinamik AAD cihaz gruplarını, belirli bir kayıt profili ile kaydedilmiş cihazları otomatik olarak dolduracak şekilde yapılandırmak için şu adımları izleyin:

1. [Intune portalı](https://portal.azure.com)’na gidin ve **Gruplar** > **Tüm gruplar** > **Yeni grup**’u seçin.
2. **Grup** dikey penceresinde gerekli alanları aşağıdaki gibi doldurun:
    - **Grup türü**: Güvenlik
    - **Grup adı**: (Fabrika 1 cihaz gibi) kullanımı kolay bir ad yazın
    - **Üyelik türü**: Dinamik cihaz
3. **Dinamik sorgu ekle**’yi seçin.
4. **Dinamik üyelik kuralları** dikey penceresindeki alanları aşağıdaki gibi doldurun:
    - **Dinamik Üyelik Kuralı Ekle**: Basit kural
    - **Cihaz eklenecek konum**: enrollmentProfileName
    - Ortadaki kutudan **Eşleştir**’i seçin.
    - Son alana ise daha önce oluşturduğunuz kayıt profili adını girin.
    Dinamik üyelik kuralları hakkında daha fazla bilgi için bkz: [AAD grupları için dinamik üyelik kuralları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. **Sorgu ekle** > **Oluştur**’u seçin.

### <a name="replace-or-remove-tokens"></a>Belirteçleri kaldırma veya değiştirme

Belirteçleri veya QR kodlarını yenisiyle değiştirebilir ya da kaldırabilirsiniz.

- **Belirtecin yerini**: Bir belirteci Değiştir'i kullanarak süre sonu yaklaştığında, yeni bir belirteç/QR kodu oluşturabilirsiniz.
- **Belirteci iptal et**: Belirteç/QR kodunu hemen süresinin dolmasını sağlayabilir. Bu noktadan itibaren belirteç/QR kodu kullanılabilir olmaktan çıkar. Şu durumlarda bu seçeneği kullanmak isteyebilirsiniz:
    - belirteci/QR kodunu yanlışlıkla yetkisiz taraflarla paylaşırsanız
    - tüm kayıtları tamamlayıp belirtece/QR koduna artık ihtiyaç duymazsanız

Bir belirteci/QR kodunu değiştirmek veya iptal etmek, önceden kaydedilmiş cihazları etkilemez.

1. Git [Intune portalı](https://portal.azure.com) ve **cihaz kaydı** > **Android kaydını** > **Corporate sahip olduğu adanmış cihazları**.
2. Çalışmak istediğiniz profili seçin.
3. **Belirteç**’i seçin.
4. Belirteci değiştirmek için **Belirteci değiştir**’i seçin.
5. Belirteci iptal etmek için **Belirteci iptal et**’i seçin.

## <a name="enroll-the-dedicated-devices"></a>Ayrılmış cihazları kaydetme

Artık [ayrılmış cihazları kaydetme](android-dedicated-devices-fully-managed-enroll.md).

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Android ayrılmış Kurumsal cihazlarda uygulamaları yönetme

Atama türü olan uygulamaları [ayarlamak için gerekli](apps-deploy.md#assign-an-app) Android ayrılmış Kurumsal cihazlarda yüklenebilir. Yüklü uygulamalar aynı şekilde Android Kurumsal olarak yönetilen Google Play Mağazası'ndan profili cihazları çalışma.

Yönetilen cihazlarda uygulamalar, uygulama geliştiricisi Google Play’e bir güncelleştirme yayımladığında otomatik olarak güncelleştirilir.

Android ayrılmış Kurumsal cihazlardan bir uygulamayı kaldırmak için aşağıdakilerden birini yapabilirsiniz:
-   Gerekli uygulama dağıtımını silin.
-   Uygulama için bir kaldırma dağıtımı oluşturun.

## <a name="next-steps"></a>Sonraki adımlar
- [Android uygulamaları dağıtın](apps-deploy.md)
- [Android yapılandırma ilkeleri ekleme](device-profiles.md)
