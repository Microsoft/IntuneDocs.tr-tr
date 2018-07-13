---
title: Microsoft Intune’da Android için bilgi noktası ayarları - Azure | Microsoft Docs
description: Android bilgi noktası cihazlarınızı tekli uygulama ve çoklu uygulama bilgi noktaları olarak yapılandırın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9158893b3ae2c2f70b08682a61cbba4d55b43710
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909159"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Intune’da Android cihazlar için bilgi noktası ayarları

Cihaz yapılandırma ayarlarını kullanarak bir cihazı tekli veya çoklu uygulama bilgi noktası moduna yapılandırabilirsiniz. Bir cihaz bilgi noktası modundayken cihazın kullanımı, kısıtlama profili tarafından belirlenen bir veya birkaç uygulama veya web bağlantısı ile sınırlıdır. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Android bilgi noktası cihazlarını tek uygulamayla kısıtlama

Bir bilgi noktası cihazının kısıtlama profili **Bilgi noktası modu** = **tekli uygulama bilgi noktası** olarak ayarlıysa, kullanıcılar yalnızca bir uygulamaya erişebilir. Bu modda yapılandırılmış cihazlar başlatıldığında, söz konusu uygulama başlar. Kullanıcılar yeni uygulamalar açamaz veya çalışan uygulamayı değiştiremez.

1. Bilgi noktası cihazında kullanılmasını istediğiniz uygulamanın [cihaza dağıtıldığından](apps-deploy.md) ve uygulamayı bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubuna atadığınızdan emin olun.
2. [Intune portalı](https://portal.azure.com)’na gidin ve **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. **Profil oluştur** dikey penceresinde aşağıdaki alanları ayarlayın:
     - **Ad**
     - **Platform**: Android kurumsal
     - **Profil türü**: Yalnızca Cihaz Sahibi > Cihaz kısıtlamaları
4. **Ayarlar** > **Bilgi noktası**’nı seçin.
5. **Bilgi noktası modu** olarak **Tekli uygulama bilgi noktası**’nı seçin.
6. **Yönetilen bir uygulama seçin**’i belirleyin ve daha sonra bu profili kullanan cihazlarda kullanılabilecek tek uygulama olmasını istediğiniz yönetilen Google Play uygulamasını seçin.
7. **Tamam** > **Tamam** > **Tamam** > **Oluştur**’u seçin.
8. Az önce oluşturduğunuz profili ve > **Atamalar**’ı seçin.
9. **Şuna ata** altında **Seçili gruplar**’ı seçin.
10. Sırasıyla şunları seçin: **Dahil edilecek cihazları seçin** > bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubunu seçin > **Seçin**.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Bilgi noktası cihazlarını bir uygulama veya web bağlantısı kümesiyle kısıtlama

Bir bilgi noktası cihazının kısıtlama profili **Bilgi noktası modu** = **çoklu uygulama bilgi noktası** olarak ayarlıysa, kullanıcılar yalnızca yapılandırdığınız sınırlı sayıda uygulamaya erişebilir. Ayrıca kullanıcıların ziyaret edebileceği bir dizi web bağlantısı da tanımlayabilirsiniz. İlke uygulandığında, kullanıcılar giriş ekranında izin verilen uygulamaların simgelerini görür.

Bir Android bilgi noktası cihazını çoklu uygulama olarak ayarlamak için şu ana adımları izleyin:

1. [Yönetilen Google Play’den Yönetilen Ana Ekran uygulamasını içeri aktarma ve dağıtma](#import-and -deploy-the-managed-home-screen-app)
2. [Bilgi noktası modunda kullanılabilecek uygulamalar ekleme ve atama](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (İsteğe bağlı) [Bilgi noktası modunda kullanılabilecek web bağlantıları ekleme](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deply-the-managed-home-screen-app"></a>Yönetilen Ana Ekran uygulamasını içeri aktarma ve dağıtma

1. [Google Play’den Yönetilen Ana Ekran sayfasına](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) gözatın ve diğer yönetilen Google Play uygulamaları için kullandığınız hesapla oturum açın.
2. **Onayla**’yı seçin.
3. [Intune portalı](https://portal.azure.com)’na gidin ve **Mobil uygulamalar** > **Yönetilen Google Play** > **Eşitle**’yi seçin.
4. **Uygulamalar** > **Yönetilen Ana Ekran** > **Atamalar** > **Grup ekle**’yi seçin.
5. **Atama türü** altında **Gerekli**’yi seçin.
6. Sırasıyla şunları seçin: **Dahil edilen cihazlar** > **Dahil edilecek cihazları seçin** > bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubunu seçin > **Seçin** > **Tamam** > **Tamam** > **Kaydet**.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>Bilgi noktası modunda kullanılabilecek uygulamalar ekleme ve atama

Bilgi noktası cihazlarında kullanılabilir olmasını istediğiniz her bir uygulama için şu adımları uygulayın:

1. [Uygulamayı Intune’a ekleyin](store-apps-android.md).
2. Sırasıyla şunları seçin: **Mobil uygulamalar** > **Uygulamalar** > uygulamayı seçin > **Atamalar** > **Grup ekle**.
3. **Atama türü** altında **Gerekli**’yi seçin.
4. Sırasıyla şunları seçin: **Dahil edilen cihazlar** > **Dahil edilecek cihazları seçin** > bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubunu seçin > **Seçin** > **Tamam** > **Tamam** > **Kaydet**.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>Bilgi noktası modunda kullanılabilecek web bağlantıları ekleme

1. [Intune portalı](https://portal.azure.com)’na gidin ve **Mobil uygulamalar** > **Uygulamalar** > **Ekle**’yi seçin.
2. **Uygulama türü** altında **Web bağlantısı**’nı seçin.
3. **Yapılandır**’ı seçin ve gerekli bilgileri sağlayın. Logo eklemenize gerek yok çünkü logo, sitenin favicon.ico’sundan otomatik olarak alınacaktır.
4. **Tamam** > **Ekle**’yi seçin.

Bilgi noktasına web tarayıcısı uygulamasını [Mobil Uygulamalar](apps-add.md)'ı kullanarak dağıttığınızdan emin olun.

### <a name="create-a-multi-app-kiosk-profile"></a>Çoklu uygulama bilgi noktası profili oluşturma

1. [Intune portalı](https://portal.azure.com)’na gidin ve **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. **Profil oluştur** dikey penceresinde aşağıdaki alanları ayarlayın:
     - **Ad**: Kullanımı kolay bir ad yazın
     - **Platform**: Android kurumsal
     - **Profil türü**: Yalnızca Cihaz Sahibi > Cihaz kısıtlamaları
4. **Ayarlar** > **Bilgi noktası**’nı seçin.
5. **Bilgi noktası modu** olarak **Çoklu uygulama bilgi noktası**’nı seçin.
6. **Ekle**’yi ve daha sonra bu profili kullanan cihazlar için kullanılabilir olmasını istediğiniz uygulama veya web bağlantılarını seçin.
7. **Tamam** > **Tamam** > **Tamam** > **Oluştur**’u seçin.
8. Az önce oluşturduğunuz profili ve > **Atamalar**’ı seçin.
9. **Şuna ata** altında **Seçili gruplar**’ı seçin.
10. Sırasıyla şunları seçin: **Dahil edilecek cihazları seçin** > bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubunu seçin > **Seçin** > **Kaydet**.

## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
