---
title: Hızlı Başlangıç - Windows 10 Masaüstü cihazınızı Microsoft Intune’a kaydetme
description: Hızlı Başlangıç - Windows 10 Masaüstü cihazınızı Microsoft Intune’a kaydetmek için Şirket Portalı’nı kullanın.
services: microsoft-intune
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 12/05/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 658a7655-a6df-4dbe-b56c-22c7fc60e706
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: c04dc3169fbf6a60d0c4d7db8358092909e90240
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841832"
---
# <a name="quickstart-enroll-your-windows-10-device"></a>Hızlı Başlangıç: Windows 10 cihazınızı kaydetme

Bu hızlı başlangıçta önce bir Intune kullanıcısı rolünü üstlenecek ve Windows 10 cihazınızı Microsoft Intune’a kaydedeceksiniz. Daha sonra Intune’a dönüp kaydettiğiniz cihazı onaylayacaksınız.

Windows 10 cihazlarınızı Microsoft Intune'a kaydederek e-postalar, dosyalar ve diğer kaynaklar gibi kuruluşunuzun güvenli verilerine erişebilirsiniz. Bu durum hem Windows 10 masaüstü hem de Windows 10 Mobile cihazlar için geçerlidir. Cihazlarınızı kaydetmeniz hem sizin hem de kuruluşunuz için güvenli erişim sağlamanıza ve iş verilerinizi kişisel verilerinizden ayırmanıza yardımcı olur.

> [!TIP]
> [Cihazınızı Intune'a kaydettiğinizde](/intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows) neler olacağını ve [cihazınızdaki bilgilerin](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) nasıl etkileneceğini öğrenin.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Intune aboneliği - [ücretsiz deneme hesabına kaydolun](free-trial-sign-up.md)
- Bu hızlı başlangıcı tamamlamak için [Intune’da otomatik kayıt kurulumu](quickstart-setup-auto-enrollment.md) adımlarını tamamlamanız gerekir.

## <a name="confirm-your-windows-10-desktop-version"></a>Windows 10 Masaüstü sürümünüzü onaylayın

Windows 10 Masaüstü cihazınızı kaydetmeden önce yüklü olan Windows sürümünü onaylamanız gerekir.

1. Windows Ayarları seçeneklerini görüntülemek için Windows’un **Başlat** simgesine sağ tıklayın ve **Ayarlar**’ı seçin.

   ![Windows Ayarları - Sistem ekran görüntüsü](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-01.png)

2. **Sistem** > **Hakkında**’yı seçin. 

   ![Sistem ayarlarınızın ekran görüntüsü](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-02.png)

    > [!TIP]
    > Ayrıca **arama çubuğuna** “Bilgisayarınız hakkında” yazıp **Bilgisayarınız hakkında**’yı seçebilirsiniz.

3. **Ayarlar** penceresinde bilgisayarınız için bir **Windows belirtimleri** listesi göreceksiniz. Bu listede **Sürüm**'ü bulun.

4. Windows 10’un **Sürüm** bölümünün **1607 veya üzeri** olduğunu onaylayın.

    > [!IMPORTANT]
    > Bu hızlı başlangıçta sunulan adımlar Windows 10 **1607 veya üzeri** sürümler içindir, **1511 veya daha düşük** sürüme sahipseniz [şu adımları](/intune-user-help/enroll-your-w10-device-your-account) izleyin.

## <a name="enroll-windows-10-desktop"></a>Windows 10 Masaüstü’nü kaydetme

1. Windows Ayarları’na dönün ve **Hesaplar**’ı seçin.

   ![Sistem ayarları - Hesaplar ekranınızın ekran görüntüsü](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-03.png)

2. **İş veya okula erişim** > **Bağlan**’ı seçin.

    ![İş veya okul hesabına erişimi seçme](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-04.png)

3. İş veya okul hesabınızla Intune’da oturum açın ve daha sonra **Sonraki**’ne tıklayın. [Kullanıcı oluşturma ve lisans atama] hızlı başlangıcını takip ettiyseniz orada oluşturduğunuz kullanıcı hesabıyla oturum açabilirsiniz.

    > [!NOTE]
    > Bir “.onmicrosoft.com” hesabı ayarlıyorsanız, kullanıcı hesabında adresin bir parçası olarak **.onmicrosoft.com** görünür. 

   ![İş veya okul hesabınızı girme](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-05.png)

    Şirketinizin veya okulunuzun cihazını kaydettiğini belirten bir mesaj görürsünüz.

4. **Tamamen hazırsınız!** ekranını görünce **Bitti**’yi seçin. İşlem tamamlandı.

5. Eklenen hesabı artık Windows Masaüstü cihazınızdaki **İş veya okula erişim** ayarlarında görebilirsiniz.

   ![Yeni eklenen hesabın ekran görüntüsü](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-06.png)

    Önceki adımları uygulamanıza rağmen iş veya okul e-posta hesabınıza ve dosyalarınıza erişemiyorsanız, [İşe veya okula erişim görüyorsanız izlenecek sorun giderme adımları](/intune-user-help/troubleshoot-your-windows-10-device-windows#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) bölümündeki adımları uygulayın.

## <a name="confirm-your-device-enrollment-in-intune"></a>Intune’da cihaz kaydınızı onaylama

1. [Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.
2. Intune’da kayıtlı cihazları görüntülemek için **Cihazlar**’ı seçin.
3. Intune’a kayıtlı bir ek cihazınız olduğunu doğrulayın.

   ![Intune’a kayıtlı cihazların ekran görüntüsü](media/quickstart-enroll-windows-device/quickstart-enroll-windows-device-07.png)

## <a name="clean-up-resources"></a>Kaynakları temizleme

Windows cihazınızın kaydını silmek için bkz. [Windows cihazınızı yönetimden kaldırma](/intune-user-help/unenroll-your-device-from-intune-windows).

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Windows 10 cihazları Intune’a kaydetmeyi öğrendiniz. Tüm platformlar genelinde cihaz kaydetmenin başka yolları hakkında bilgi edinebilirsiniz. Cihazları Intune ile kullanma hakkında daha fazla bilgi için bkz. [İşlerinizi tamamlamak için yönetilen cihazlar kullanma](/intune-user-help/use-managed-devices-to-get-work-done).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Gerekli parola uzunluğu Android cihazları için ayarlayın](quickstart-set-password-length-android.md)
