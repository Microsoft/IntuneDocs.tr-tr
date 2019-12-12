---
title: Android kurumsal adanmış cihazları veya tam olarak yönetilen cihazları Intune 'A kaydetme
titleSuffix: Microsoft Intune
description: Android kurumsal adanmış cihazları veya tam olarak yönetilen cihazları Intune 'a kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
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
ms.openlocfilehash: 2ad96c80a2cad71feec2afdfa87da767aa72fdb1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505619"
---
# <a name="enroll-your-android-enterprise-dedicated-devices-or-fully-managed-devices"></a>Android kurumsal adanmış cihazlarınızı veya tam olarak yönetilen cihazları kaydedin

[Android kurumsal adanmış cihazlarınızı](android-kiosk-enroll.md) veya [tam olarak yönetilen cihazları](android-fully-managed-enroll.md) Intune 'da ayarladıktan sonra, cihazları kaydedebilirsiniz. Hem adanmış hem de tam olarak yönetilen cihazların Intune kaydı, fabrika sıfırlaması ile başlar. Android kurumsal cihazlarınızı kaydetme, işletim sistemine bağlıdır.

| Kayıt yöntemi | Adanmış ve tam olarak yönetilen cihazlar için en düşük Android işletim sistemi sürümü |
| ----- | ----- |
| Yakın Alan İletişimi | 5.1 |
| Belirteç girişi | 6.0 |
| QR kodu | 7.0 |
| Zero Touch  | 8,0\* |

katılan üreticilerle \*.

## <a name="enroll-by-using-near-field-communication-nfc"></a>Yakın Alan İletişimi (NFC) kullanarak kaydetme

NFC 'yi destekleyen cihazlarda, özel olarak biçimlendirilmiş bir NFC etiketi oluşturarak cihazlarınızı sağlayabilirsiniz. Kendi uygulamanızı veya NFC etiketi oluşturan bir araç kullanabilirsiniz. Daha fazla bilgi için, bkz. Microsoft Intune ve [Google 'ın Android yönetim API 'si belgeleri](https://developers.google.com/android/management/provision-device#nfc_method) [Ile C tabanlı Android kurumsal cihaz kaydı](https://blogs.technet.microsoft.com/cbernier/2018/10/15/nfc-based-android-enterprise-device-enrollment-with-microsoft-intune/) .

## <a name="enroll-by-using-a-token"></a>Belirteç kullanarak kaydetme

Android 6 ve üzeri cihazlarda cihaz kaydı için belirteci kullanabilirsiniz. Ayrıca, **AFW # kurulum** kayıt yöntemi kullanılırken, Android 6,1 ve ÜZERI sürümler QR kod taramasını de kullanabilir.

1. Silinmiş cihazınızı açın.
2. **Hoş Geldiniz** ekranında dili seçin.
3. **Wi-Fi** ağınıza bağlanın ve **İLERİ**’yi seçin.
4. Google hüküm ve koşullarını kabul edin ve ardından **İLERİ**’yi seçin.
5. Google oturum açma ekranında bir Gmail hesabı yerine **afw#setup** girin ve **İLERİ**’yi seçin.
6. **Android Cihaz İlkesi** uygulaması için **YÜKLE**’yi seçin.
7. Bu ilkenin yüklemesine devam edin.  Bazı cihazlar ek koşulların kabul edilmesini gerektirebilir.
8. **Bu cihazı kaydet** ekranında cihazınızın QR kodunu taramasına izin verin veya belirteci el ile girmeyi seçin.
9. Kaydı tamamlamak için ekrandaki istemleri takip edin.

## <a name="enroll-by-using-a-qr-code"></a>QR kodu kullanarak kaydetme

Android 7 ve üzeri cihazları kaydetmek için kayıt profilinden QR kodunu tarayabilirsiniz.

> [!Note]
> Tarayıcı yakınlaştırma, cihazların QR kodunu tarayamamasına neden olabilir. Tarayıcı yakınlaştırmasının artırılması sorunu çözer.

1. Android cihazda QR okuması başlatmak için silme sonrası gördüğünüz ilk ekrana birkaç kez dokunun.
2. Android 7 ve 8 cihazlarda bir QR okuyucu yüklemeniz istenir. Android 9 ve üzeri cihazlarda bir QR okuyucu zaten yüklüdür.
3. Kayıt profili QR kodunu taramak için QR okuyucuyu kullanın ve kaydı tamamlamak için ekrandaki istemleri takip edin.

## <a name="enroll-by-using-google-zero-touch"></a>Google Zero Touch’ı kullanarak kaydetme

Google’ın Zero Touch sistemini kullanmak için cihazın bunu destekliyor olması ve hizmetin parçası olan bir sağlayıcıya bağlı olması gerekir.  Daha fazla bilgi için bkz. [Google’ın Zero Touch programı web sitesi](https://www.android.com/enterprise/management/zero-touch/).

1. Zero Touch konsolunda yeni bir Yapılandırma oluşturun.
2. EMM DPC açılan menüsünde **Microsoft Intune**’u seçin.
3. Google’ın Zero Touch konsolunda, aşağıdaki JSON’ı kopyalayıp DPC ek özellikler alanına yapıştırın. *YourEnrollmentToken* dizesini, kayıt profilinizin parçası olarak oluşturduğunuz kayıt belirteciyle değiştirin. Kayıt belirtecinin başına ve sonuna çift tırnak koymayı unutmayın.

    ```json
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


## <a name="next-steps"></a>Sonraki adımlar
- [Android uygulamalarını dağıtma](../apps/apps-deploy.md)
- [Android yapılandırma ilkelerini ekleme](../configuration/device-profiles.md)

