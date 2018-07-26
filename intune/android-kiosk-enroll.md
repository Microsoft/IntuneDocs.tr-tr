---
title: Android kurumsal bilgi noktası cihazlarını Intune’a kaydetme
titlesuffix: Microsoft Intune
description: Android kurumsal bilgi noktası cihazlarını Intune’a nasıl kaydedeceğinizi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5a223834eed1b0174c56b5e33ad2140203073d0
ms.sourcegitcommit: 5251a630fb2c7a2e6f86abd84ab887f8eabc1481
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39212044"
---
# <a name="set-up-enrollment-of-android-enterprise-kiosk-devices"></a>Android kurumsal bilgi noktası cihazlarının kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android; Şirkete Ait, Tek Kullanımlık çözüm kümesi ile bilgi noktası türü cihazlarını destekler. Bu tür cihazlar tek bir amaca hizmet eder; örneğin dijital işaretler, bilet yazdırma veya envanter yönetimi gibi. Yöneticiler bir cihazın kullanımını sınırlı sayıda uygulama ve web bağlantısına indirger. Ayrıca kullanıcılar başka uygulama ekleyemez veya farklı eylemler gerçekleştiremez.

Intune, Android bilgi noktası cihazlarına uygulama ve ayar dağıtmanıza yardımcı olur. Android kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Bu şekilde yönettiğiniz cihazlar, bir kullanıcı hesabı olmadan Intune’a kaydolur ve hiçbir son kullanıcı ile ilişkili değildir. Bu cihazlar, kullanıcıya özgü hesap verileri konusunda katı gereksinimleri olan Outlook veya Gmail gibi kişisel kullanım uygulamalarına uygun değildir.

## <a name="device-requirements"></a>Cihaz gereksinimleri

Cihazların Android kurumsal bilgi noktası cihazları olarak yönetilebilmesi için şu gereksinimleri karşılaması gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Cihazlar Android’in Google Mobile Services (GMS) bağlantısı olan bir dağıtımını çalıştırmalıdır. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

## <a name="set-up-android-kiosk-management"></a>Android bilgi noktası yönetimini ayarlama

Android bilgi noktası yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. Mobil cihazların yönetimine hazırlık olarak, yönergeler için [**Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız](mdm-authority-set.md) gerekir. Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Android kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Bir kayıt profili oluşturun.](#create-an-enrollment-profile)
4. [Bir cihaz grubu oluşturun](#create-a-device-group).
5. [Bilgi noktası cihazlarını kaydedin](#enroll-the-kiosk-devices).

### <a name="create-an-enrollment-profile"></a>Kayıt profili oluşturma

Bilgi noktası cihazlarınızı kaydedebilmek için bir kayıt profili oluşturmalısınız. Profil oluşturulduktan sonra size bir kayıt belirteci (rastgele dize) ve QR kodu sağlar. Cihazın Android işletim sistemi ve cihazın sürümüne bağlı olarak [bilgi noktası cihazını kaydetmek](#enroll-the-kiosk-devices) için belirteci veya QR kodunu kullanabilirsiniz.

1. [Intune portalı](https://portal.azure.com)’na gidip **Cihaz kaydı** > **Android kaydı** > **Bilgi noktası ve görev cihazı kayıtları**’nı seçin.
2. **Oluştur**’u seçin ve gerekli alanları doldurun.
    - **Ad**: Profili dinamik cihaz grubuna atarken kullanacağınız bir ad yazın.
    - **Belirteç sona erme tarihi**: Belirteç süresinin dolduğu tarih. Google, en fazla 30 günü kabul eder.
3. **Oluştur**’u seçerek profili kaydedin.

### <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma

Uygulama ve ilkeleri, atanmış veya dinamik cihaz gruplarına hedefleyebilirsiniz. Dinamik AAD cihaz gruplarını, belirli bir kayıt profili ile kaydedilmiş cihazları otomatik olarak dolduracak şekilde yapılandırmak için şu adımları izleyin:

1. [Intune portalı](https://portal.azure.com)’na gidin ve **Gruplar** > **Tüm gruplar** > **Yeni grup**’u seçin.
2. **Grup** dikey penceresinde gerekli alanları aşağıdaki gibi doldurun:
    - **Grup türü**: Güvenlik
    - **Grup adı**: Kullanımı kolay bir ad yazın (Fabrika 1 cihazlar gibi)
    - **Üyelik türü**: Dinamik cihaz
3. **Dinamik sorgu ekle**’yi seçin.
4. **Dinamik üyelik kuralları** dikey penceresindeki alanları aşağıdaki gibi doldurun:
    - **Dinamik üyelik kuralı ekle**: Basit kural
    - **Cihaz eklenecek konum**: enrollmentProfileName
    - Ortadaki kutudan **Eşleştir**’i seçin.
    - Son alana ise daha önce oluşturduğunuz kayıt profili adını girin.
5. **Sorgu ekle** > **Oluştur**’u seçin.

### <a name="replace-or-remove-tokens"></a>Belirteçleri kaldırma veya değiştirme

Belirteçleri veya QR kodlarını yenisiyle değiştirebilir ya da kaldırabilirsiniz.

- **Belirteci değiştir**: Belirteci Değiştir’i kullanarak süresi dolmak üzere olan belirteç/QR kodu yerine yenisini oluşturabilirsiniz.
- **Belirteci iptal et**: Belirtecin/QR kodunun süresinin hemen dolmasını sağlayabilirsiniz. Bu noktadan itibaren belirteç/QR kodu kullanılabilir olmaktan çıkar. Şu durumlarda bu seçeneği kullanmak isteyebilirsiniz:
    - belirteci/QR kodunu yanlışlıkla yetkisiz taraflarla paylaşırsanız
    - tüm kayıtları tamamlayıp belirtece/QR koduna artık ihtiyaç duymazsanız

Bir belirteci/QR kodunu değiştirmek veya iptal etmek, önceden kaydedilmiş cihazları etkilemez.

1. [Intune portalı](https://portal.azure.com)’na gidip **Cihaz kaydı** > **Android kaydı** > **Bilgi noktası ve görev cihazı kayıtları**’nı seçin.
2. Çalışmak istediğiniz profili seçin.
3. **Belirteç**’i seçin.
4. Belirteci değiştirmek için **Belirteci değiştir**’i seçin.
5. Belirteci iptal etmek için **Belirteci iptal et**’i seçin.

## <a name="enroll-the-kiosk-devices"></a>Bilgi noktası cihazlarını kaydetme

Kayıt profilini ve dinamik cihaz grubunu oluşturduktan sonra bilgi noktası cihazlarınızı kaydedebilirsiniz. Android cihazları kaydetme biçiminiz, işletim sisteminize bağlıdır.

| Kayıt yöntemi | Desteklenen en düşük Android işletim sistemi sürümü |
| ----- | ----- |
| Yakın Alan İletişimi | 5.1 |
| Belirteç girişi | 6.0 |
| QR kodu | 7.0 |
| Zero Touch | 8.0, katılımcı üreticilerde |

### <a name="enroll-by-using-near-field-communication-nfc"></a>Yakın Alan İletişimi (NFC) kullanarak kaydetme

NFC destekleyen Android 5.1 ve üzeri cihazlarda özel olarak biçimlendirilmiş NFC etiketleri oluşturarak cihaz sağlayabilirsiniz. Kendi uygulamanızı veya NFC etiketi oluşturan bir araç kullanabilirsiniz. Daha fazla bilgi için [Google’ın Android Yönetim API’si belgelerine](https://developers.google.com/android/management/provision-device#nfc_method) bakın.

### <a name="enroll-by-using-a-token"></a>Belirteç kullanarak kaydetme

Android 6 ve üzeri cihazlarda cihaz kaydı için belirteci kullanabilirsiniz.

1. Fabrika ayarlarına sıfırlanmış cihazınızı açın.
2. **Hoş Geldiniz** ekranında dili seçin.
3. **Wi-Fi** ağınıza bağlanın ve **İLERİ**’yi seçin.
4. Google hüküm ve koşullarını kabul edin ve ardından **İLERİ**’yi seçin.
5. Google oturum açma ekranında bir Gmail hesabı yerine **afw#setup** girin ve **İLERİ**’yi seçin.
6. **Android Cihaz İlkesi** uygulaması için **YÜKLE**’yi seçin.
7. Bu ilkenin yüklemesine devam edin.  Bazı cihazlar ek koşulların kabul edilmesini gerektirebilir. 
8. **Bu cihazı kaydet** ekranında cihazınızın QR kodunu taramasına izin verin veya belirteci el ile girmeyi seçin.
9. Kaydı tamamlamak için ekrandaki istemleri takip edin. 

### <a name="enroll-by-using-a-qr-code"></a>QR kodu kullanarak kaydetme

Android 7 ve üzeri cihazları kaydetmek için kayıt profilinden QR kodunu tarayabilirsiniz.

1. Android cihazda QR okuması başlatmak için fabrika sıfırlaması sonrası gördüğünüz ilk ekrana birkaç kez dokunun.
2. Android 7 ve 8 cihazlarda bir QR okuyucu yüklemeniz istenir. Android 9 ve üzeri cihazlarda bir QR okuyucu zaten yüklüdür.
3. Kayıt profili QR kodunu taramak için QR okuyucuyu kullanın ve kaydı tamamlamak için ekrandaki istemleri takip edin.

### <a name="enroll-by-using-google-zero-touch"></a>Google Zero Touch’ı kullanarak kaydetme

Google’ın Zero Touch sistemini kullanmak için cihazın bunu destekliyor olması ve hizmetin parçası olan bir sağlayıcıya bağlı olması gerekir.  Daha fazla bilgi için bkz. [Google’ın Zero Touch programı web sitesi](https://www.android.com/enterprise/management/zero-touch/). 


1. Zero Touch konsolunda yeni bir Yapılandırma oluşturun.
2. EMM DPC açılan menüsünde **Microsoft Intune**’u seçin.
3. Google’ın Zero Touch konsolunda, aşağıdaki JSON’ı kopyalayıp DPC ek özellikler alanına yapıştırın. *YourEnrollmentToken* dizesini, kayıt profilinizin parçası olarak oluşturduğunuz kayıt belirteciyle değiştirin. Kayıt belirtecinin başına ve sonuna çift tırnak koymayı unutmayın.

```
{ 
    "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "com.google.android.apps.work.clouddpc/.receivers.CloudDeviceAdminReceiver", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "I5YvS0O5hXY46mb01BlRjq4oJJGs2kuUcHvVkAPEXlg", 

    "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://play.google.com/managed/downloadManagingApp?identifier=setup", 

    "android.app.extra.PROVISIONING_ADMIN_EXTRAS_BUNDLE": { 
        "com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "YourEnrollmentToken" 
    } 
} 
```
4. **Uygula**'yı seçin.

## <a name="managing-apps-on-android-kiosk-devices"></a>Android bilgi noktası cihazlarında uygulamaları yönetme

Android bilgi noktası cihazlarına yalnızca Atama türü [Gerekli](apps-deploy.md#to-assign-an-app) olarak ayarlanmış uygulamalar yüklenebilir. Uygulamalar, Android iş profili cihazlarında olduğu gibi yönetilen Google Play mağazasından yüklenir.

Yönetilen cihazlarda uygulamalar, uygulama geliştiricisi Google Play’e bir güncelleştirme yayımladığında otomatik olarak güncelleştirilir.

Android bilgi noktası cihazlarından bir uygulama kaldırmak için şunlardan birini yapabilirsiniz:
-   Gerekli uygulama dağıtımını silin.
-   Uygulama için bir kaldırma dağıtımı oluşturun.


## <a name="next-steps"></a>Sonraki adımlar
- [Android bilgi noktası uygulamalarını dağıtma](apps-deploy.md)
- [Android bilgi noktası yapılandırma ilkeleri ekleme](device-profiles.md)