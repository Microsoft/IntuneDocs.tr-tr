---
title: Android Kurumsal ayrılmış cihazları için Intune kaydını ayarlama
titleSuffix: Microsoft Intune
description: Android Kurumsal ayrılmış cihazlarını Intune’a nasıl kaydedeceğinizi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83f0d980bc4fa1bfd0b48f87839fd6efa130aa70
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74563868"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Android Kurumsal ayrılmış cihazları için Intune kaydını ayarlama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Android Kurumsal ayrılmış cihazlar çözüm kümesiyle şirkete ait, tek kullanımlık, bilgi noktası türündeki cihazları destekler. Bu tür cihazlar tek bir amaca hizmet eder; örneğin dijital işaretler, bilet yazdırma veya envanter yönetimi gibi. Yöneticiler bir cihazın kullanımını sınırlı sayıda uygulama ve web bağlantısına indirger. Ayrıca kullanıcılar başka uygulama ekleyemez veya farklı eylemler gerçekleştiremez.

Intune, Android Kurumsal ayrılmış cihazlarına uygulama ve ayar dağıtmanıza yardımcı olur. Android Kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Bu şekilde yönettiğiniz cihazlar, bir kullanıcı hesabı olmadan Intune’a kaydolur ve hiçbir son kullanıcı ile ilişkili değildir. Bu cihazlar, kullanıcıya özgü hesap verileri konusunda katı gereksinimleri olan Outlook veya Gmail gibi kişisel kullanım uygulamalarına uygun değildir.

## <a name="device-requirements"></a>Cihaz gereksinimleri

Cihazların Android Kurumsal ayrılmış cihazları olarak yönetilebilmesi için şu gereksinimleri karşılaması gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Cihazlar Android’in Google Mobile Services (GMS) bağlantısı olan bir dağıtımını çalıştırmalıdır. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Android Kurumsal ayrılmış cihaz yönetimi ayarları

Android Kurumsal ayrılmış cihaz yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. Mobil cihazların yönetimine hazırlık olarak, yönergeler için [**Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız](../fundamentals/mdm-authority-set.md) gerekir. Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Yönetilen Google Play hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Bir kayıt profili oluşturun.](#create-an-enrollment-profile)
4. [Bir cihaz grubu oluşturun](#create-a-device-group).
5. [Ayrılmış cihazları kaydedin](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Kayıt profili oluşturma

> [!NOTE]
> Belirtecin süresi dolmuşsa, onunla ilişkili profil, **şirkete ait adanmış cihazlarda** > **Android kaydı** > **cihaz kaydı** 'nda gösterilmez. Hem etkin hem de etkin olmayan belirteçlerle ilişkili tüm profilleri görmek için **filtre** ' ye tıklayın ve hem "etkin" hem de "etkin olmayan" ilke durumlarının onay kutularını işaretleyin. 

Ayrılmış cihazlarınızı kaydedebilmek için bir kayıt profili oluşturmalısınız. Profil oluşturulduktan sonra size bir kayıt belirteci (rastgele dize) ve QR kodu sağlar. Cihazın Android işletim sistemi ve cihazın sürümüne bağlı olarak [ayrılmış cihazı kaydetmek](#enroll-the-dedicated-devices) için belirteci veya QR kodunu kullanabilirsiniz.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' nde oturum açın ve **cihazlar** > **Android** > Android **kaydı** > **şirkete ait adanmış cihazlar**' ı seçin.
2. **Oluştur**’u seçin ve gerekli alanları doldurun.
    - **Ad**: Profili dinamik cihaz grubuna atarken kullanacağınız bir ad yazın.
    - **Belirteç sona erme tarihi**: Belirteç süresinin dolduğu tarih. Google, en fazla 90 günü kabul eder.
3. **Oluştur**’u seçerek profili kaydedin.

### <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma

Uygulama ve ilkeleri, atanmış veya dinamik cihaz gruplarına hedefleyebilirsiniz. Dinamik AAD cihaz gruplarını, belirli bir kayıt profili ile kaydedilmiş cihazları otomatik olarak dolduracak şekilde yapılandırmak için şu adımları izleyin:

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' nde oturum açın ve **gruplar** > **tüm gruplar** > **Yeni Grup**' a tıklayın.
2. **Grup** dikey penceresinde gerekli alanları aşağıdaki gibi doldurun:
    - **Grup türü**: Güvenlik
    - **Grup adı**: Kullanımı kolay bir ad yazın (Fabrika 1 cihazlar gibi)
    - **Üyelik türü**: Dinamik cihaz
3. **Dinamik sorgu ekle**’yi seçin.
4. **Dinamik üyelik kuralları** dikey penceresindeki alanları aşağıdaki gibi doldurun:
    - **Dinamik üyelik kuralı ekle**: Basit kural
    - **Cihaz eklenecek konum**: enrollmentProfileName
    - Ortadaki kutuda **eşittir**' i seçin.
    - Son alana ise daha önce oluşturduğunuz kayıt profili adını girin.
    Dinamik üyelik kuralları hakkında daha fazla bilgi için bkz: [AAD grupları için dinamik üyelik kuralları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. **Sorgu ekle** > **Oluştur**’u seçin.

### <a name="replace-or-remove-tokens"></a>Belirteçleri kaldırma veya değiştirme

- **Belirteci değiştir**: Belirteci Değiştir’i kullanarak süresi dolmak üzere olan belirteç/QR kodu yerine yenisini oluşturabilirsiniz.
- **Belirteci iptal et**: Belirtecin/QR kodunun süresinin hemen dolmasını sağlayabilirsiniz. Bu noktadan itibaren belirteç/QR kodu kullanılabilir olmaktan çıkar. Şu durumlarda bu seçeneği kullanmak isteyebilirsiniz:
  - belirteci/QR kodunu yanlışlıkla yetkisiz taraflarla paylaşırsanız
  - tüm kayıtları tamamlayıp belirtece/QR koduna artık ihtiyaç duymazsanız

Bir belirteci/QR kodunu değiştirmek veya iptal etmek, önceden kaydedilmiş cihazları etkilemez.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' nde oturum açın ve **cihazlar** > **Android** > **Android kayıt** > **ortak adanmış cihazlar**' ı seçin.
2. Çalışmak istediğiniz profili seçin.
3. **Belirteç**’i seçin.
4. Belirteci değiştirmek için **Belirteci değiştir**’i seçin.
5. Belirteci iptal etmek için **Belirteci iptal et**’i seçin.

## <a name="enroll-the-dedicated-devices"></a>Ayrılmış cihazları kaydetme

Artık [ayrılmış cihazlarınızı kaydedebilirsiniz](android-dedicated-devices-fully-managed-enroll.md).

> [!NOTE]
> **Microsoft Intune** uygulama adanmış bir cihazın kaydı sırasında otomatik olarak yüklenir.  Bu uygulama kayıt için gereklidir ve kaldırılamaz. 

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Android Kurumsal ayrılmış cihazlarındaki uygulamaları yönetme

Android Kurumsal ayrılmış cihazlarına yalnızca Atama türü [Gerekli](../apps/apps-deploy.md#assign-an-app) olarak ayarlanmış uygulamalar yüklenebilir. Uygulamalar, Android Kurumsal iş profili cihazlarında olduğu gibi Yönetilen Google Play mağazasından yüklenir.

Yönetilen cihazlarda uygulamalar, uygulama geliştiricisi Google Play’e bir güncelleştirme yayımladığında otomatik olarak güncelleştirilir.

Android Kurumsal ayrılmış cihazlarından bir uygulama kaldırmak için şunlardan birini yapabilirsiniz:
- Gerekli uygulama dağıtımını silin.
- Uygulama için bir kaldırma dağıtımı oluşturun.

## <a name="next-steps"></a>Sonraki adımlar
- [Android uygulamalarını dağıtma](../apps/apps-deploy.md)
- [Android yapılandırma ilkelerini ekleme](../configuration/device-profiles.md)
