---
title: "Windows 10 için toplu kayıt | Microsoft Docs"
description: "Microsoft Intune için toplu kayıt paketi oluşturma"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0053e37a-f26e-452f-9524-5039a635b52e
ms.reviewer: damionw
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: dfe63ba7e1825db8d8b6b1e74c442b125ccafd46
ms.lasthandoff: 04/19/2017

---
# <a name="bulk-enrollment-for-windows-devices"></a>Windows cihazlar için toplu kayıt

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir yönetici olarak çok sayıda yeni Windows cihazını Azure Active Directory ve Intune’a dahil edebilirsiniz. Azure AD kiracınıza cihazları toplu kaydetmek için Windows Yapılandırma Tasarımcısı (WCD) uygulaması ile bir sağlama paketi oluşturursunuz. Sağlama paketini şirkete ait cihazlara uygulamak, cihazları Azure AD kiracınıza dahil eder ve Intune yönetimine kaydeder. Paket uygulandıktan sonra, Azure AD kullanıcılarınızın oturum açması için hazırdır.

Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan Intune ilkelerini ve gerekli uygulamaları alırlar. Self Servis ve Şirket Portalı senaryoları şu anda desteklenmiyor.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Windows cihazları toplu kayıt için önkoşullar

Windows cihazları toplu kaydetmek için aşağıdakiler gereklidir:

- Windows 10 Creator Update veya üzerini çalıştıran cihazlar
- [Windows otomatik kayıt](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Sağlama paketi oluşturma

1. Windows Mağazası'ndan [Windows Yapılandırma Tasarımcısı (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) uygulamasını indirin.
![Windows Yapılandırma Tasarımcısı uygulamasının Mağaza ekran görüntüleri ve açıklamasının ekran görüntüsü](../media/bulk-enroll-store.png)

2. **Windows Yapılandırma Tasarımcısı** uygulamasını açın ve **Masaüstü cihazları sağla** seçeneğini belirleyin.
![Windows Yapılandırma Tasarımcısı uygulamasında Masaüstü cihazları sağla seçeneğini belirlemenin ekran görüntüsü](../media/bulk-enroll-select.png)

3. Aşağıdakileri belirttiğiniz **Yeni proje** penceresi açılır:
  - **Ad** - Projenizin adı
  - **Proje klasörü** - Yeni projenizin kaydedileceği yer
  - **Açıklama** - Proje için isteğe bağlı bir açıklama ![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-name.png)

4.    Cihazlarınız için benzersiz bir ad girin. Adlar bir seri numarası (%%SERIAL%%) veya rastgele bir karakter kümesi içerebilir. İsteğe bağlı olarak Windows sürümünü yükseltiyor, cihazı paylaşımlı kullanım için yapılandırıyor ve önceden yüklenmiş yazılımları kaldırıyorsanız bir ürün anahtarı girebilirsiniz.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-device.png)

5.    İsteğe bağlı olarak, cihazları ilk kez başlattığınızda bağlanacakları Wi-Fi ağını yapılandırabilirsiniz.  Yapılandırılmadıysa, cihaz ilk başlatıldığında kablolu bir ağ bağlantısı gerekir.
![Windows Yapılandırma Tasarımcısı uygulamasında Ağ SSID’si ve Ağ türü seçeneklerini içeren Wi-Fi etkinleştirme ekran görüntüsü](../media/bulk-enroll-network.png)

6.    **Azure AD'ye Kaydet**’i seçin, bir **Toplu Belirteç Süre Sonu** tarihi girin ve ardından **Toplu Belirteç Al**’ı seçin.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-account.png)

7. Bir toplu belirteç almak için Azure AD kimlik bilgilerinizi sağlayın.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-cred.png)

8.    **Toplu Belirteç** başarıyla alındığında **İleri**’ye tıklayın.

9. İsteğe bağlı olarak, **Uygulama ekleyebilir** ve **Sertifika ekleyebilirsiniz**. Bu uygulamalar ve sertifikalar cihazda sağlanır.

10. İsteğe bağlı olarak, sağlama paketinizi parola ile koruyabilirsiniz.  **Oluştur**'a tıklayın.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Cihaz sağlama

1. Uygulamada belirtilen **Proje klasörü** içinde belirtilen konumdaki sağlama paketine erişin.

2. Sağlama paketini cihaza nasıl uygulayacağınızı seçin.  Sağlama paketi bir cihaza aşağıdaki yollardan biriyle uygulanabilir:
 - Sağlama paketini bir USB sürücüsüne kaydedin, USB sürücüsünü toplu kaydetmek istediğiniz cihaza yerleştirin ve ilk kurulum sırasında uygulayın
 - Sağlama paketini bir ağ klasörüne yerleştirin ve ilk kurulum sonrasında toplu kaydetmek istediğiniz cihaza yerleştirmek üzere uygulayın

 Sağlama paketi uygulama ile ilgili adım adım yönergeler için bkz. [Sağlama paketi uygulama](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Paketi uyguladıktan sonra, cihaz 1 dakika içinde otomatik olarak yeniden başlatılır.
 ![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](../media/bulk-enroll-add.png)

4. Cihaz yeniden başlatıldığında, Azure Active Directory'ye bağlanır ve Microsoft Intune’a kaydedilir.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Windows toplu kayıt için sorun giderme

Sağlama, yeni Windows cihazlarda kullanılmak üzere tasarlanmıştır. Sağlama hataları cihazın fabrika ayarlarına sıfırlanmasını veya bir önyükleme görüntüsünden kurtarılmasını gerektirebilir. Bu örneklerde sağlama hatalarının bazı nedenleri açıklanır:

- Yerel bir hesap oluşturmayan bir Active Directory etki alanına veya Azure Active Directory kiracısına katılmayı deneyen bir sağlama paketinin, ağ bağlantısı olmaması nedeniyle etki alanına katılma işlemi başarısız olursa cihaza ulaşılamayabilir.
- Sağlama paketi tarafından çalıştırılan betikler sistem bağlamında çalışır ve cihazın dosya sistemi ve yapılandırmalarında rastgele değişiklikler yapabilir. Kötü amaçlı veya hatalı bir betik, cihazın yalnızca yeniden görüntü oluşturma veya fabrika ayarlarına sıfırlama yollarıyla kurtarılabilecek bir duruma gelmesine neden olabilir.

