---
title: "Windows 10 için toplu kayıt"
titlesuffix: Azure portal
description: "Microsoft Intune için toplu kayıt paketi oluşturma"
keywords: 
author: Erikje
ms.author: erikje
manager: dougeby
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: 8b4c9f5685c12bb6c15d15d85c73d573dfcd66e8
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="bulk-enrollment-for-windows-devices"></a>Windows cihazlar için toplu kayıt

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir yönetici olarak çok sayıda yeni Windows cihazını Azure Active Directory ve Intune’a dahil edebilirsiniz. Azure AD kiracınıza cihazları toplu kaydetmek için Windows Yapılandırma Tasarımcısı (WCD) uygulaması ile bir sağlama paketi oluşturursunuz. Sağlama paketini şirkete ait cihazlara uygulamak, cihazları Azure AD kiracınıza dahil eder ve Intune yönetimine kaydeder. Paket uygulandıktan sonra, Azure AD kullanıcılarınızın oturum açması için hazır hale gelir.

Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan Intune ilkelerini ve gerekli uygulamaları alırlar. Self Servis ve Şirket Portalı senaryoları şu anda desteklenmiyor.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Windows cihazları toplu kaydetme önkoşulları

- Windows 10 Creator Update veya üzerini çalıştıran cihazlar
- [Windows otomatik kayıt](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Sağlama paketi oluşturma

1. Microsoft Mağazası'ndan [Windows Yapılandırma Tasarımcısı (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) uygulamasını indirin.
![Windows Yapılandırma Tasarımcısı uygulamasının Mağaza ekran görüntüleri ve açıklamasının ekran görüntüsü](media/bulk-enroll-store.png)

2. **Windows Yapılandırma Tasarımcısı** uygulamasını açın ve **Masaüstü cihazları sağla** seçeneğini belirleyin.
![Windows Yapılandırma Tasarımcısı uygulamasında Masaüstü cihazları sağla seçeneğini belirlemenin ekran görüntüsü](media/bulk-enroll-select.png)

3. Aşağıdaki bilgileri belirttiğiniz **Yeni proje** penceresi açılır:
  - **Ad** - Projenizin adı
  - **Proje klasörü** - Projenin kaydetme konumu
  - **Açıklama** - Proje için isteğe bağlı bir açıklama ![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-name.png)

4.  Cihazlarınız için benzersiz bir ad girin. Adlar bir seri numarası (%%SERIAL%%) veya rastgele bir karakter kümesi içerebilir. İsteğe bağlı olarak Windows sürümünü yükseltiyor, cihazı paylaşımlı kullanım için yapılandırıyor ve önceden yüklenmiş yazılımları kaldırıyorsanız bir ürün anahtarı girebilirsiniz.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-device.png)

5.  İsteğe bağlı olarak, cihazları ilk kez başlattığınızda bağlanacakları Wi-Fi ağını yapılandırabilirsiniz.  Ağ cihazları yapılandırılmadıysa, cihaz ilk başlatıldığında kablolu bir ağ bağlantısı gerekir.
![Windows Yapılandırma Tasarımcısı uygulamasında Ağ SSID’si ve Ağ türü seçeneklerini içeren Wi-Fi etkinleştirme ekran görüntüsü](media/bulk-enroll-network.png)

6.  **Azure AD'ye Kaydet**’i seçin, bir **Toplu Belirteç Süre Sonu** tarihi girin ve ardından **Toplu Belirteç Al**’ı seçin.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-account.png)

7. Bir toplu belirteç almak için Azure AD kimlik bilgilerinizi sağlayın.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-cred.png)

8.  **Toplu Belirteç** başarıyla alındığında **İleri**’ye tıklayın.

9. İsteğe bağlı olarak, **Uygulama ekleyebilir** ve **Sertifika ekleyebilirsiniz**. Bu uygulamalar ve sertifikalar cihazda sağlanır.

10. İsteğe bağlı olarak, sağlama paketinizi parola ile koruyabilirsiniz.  **Oluştur**'a tıklayın.
![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Cihaz sağlama

1. Uygulamada belirtilen **Proje klasörü** içinde belirtilen konumdaki sağlama paketine erişin.

2. Sağlama paketini cihaza nasıl uygulayacağınızı seçin.  Sağlama paketi bir cihaza aşağıdaki yollardan biriyle uygulanabilir:
 - Sağlama paketini bir USB sürücüsüne kaydedin, USB sürücüsünü toplu kaydetmek istediğiniz cihaza yerleştirin ve ilk kurulum sırasında uygulayın
 - Sağlama paketini bir ağ klasörüne yerleştirin ve ilk kurulum sonrasında toplu kaydetmek istediğiniz cihaza uygulayın

 Sağlama paketi uygulama ile ilgili adım adım yönergeler için bkz. [Sağlama paketi uygulama](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Paketi uyguladıktan sonra, cihaz bir dakika içinde otomatik olarak yeniden başlatılır.
 ![Windows Yapılandırma Tasarımcısı uygulamasında ad, proje klasörü ve açıklama belirtilen ekran görüntüsü](media/bulk-enroll-add.png)

4. Cihaz yeniden başlatıldığında, Azure Active Directory'ye bağlanır ve Microsoft Intune’a kaydedilir.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Windows toplu kayıt için sorun giderme

### <a name="provisioning-issues"></a>Sağlama sorunları
Sağlama, yeni Windows cihazlarda kullanılmak üzere tasarlanmıştır. Sağlama hataları cihazın fabrika ayarlarına sıfırlanmasını veya bir önyükleme görüntüsünden kurtarılmasını gerektirebilir. Bu örneklerde sağlama hatalarının bazı nedenleri açıklanır:

- Yerel bir hesap oluşturmayan bir Active Directory etki alanına veya Azure Active Directory kiracısına katılmayı deneyen bir sağlama paketinin, ağ bağlantısı olmaması nedeniyle etki alanına katılma işlemi başarısız olursa cihaza ulaşılamayabilir.
- Sağlama paketi tarafından çalıştırılan betikler, sistem bağlamında çalıştırılır. Betikler cihaz dosya sisteminde ve yapılandırmalarında rastgele değişiklikler yapabilir. Kötü amaçlı veya hatalı bir betik, cihazın yalnızca yeniden görüntü oluşturma veya fabrika ayarlarına sıfırlama yollarıyla kurtarılabilecek bir duruma gelmesine neden olabilir.

### <a name="problems-with-bulk-enrollment-and-company-portal"></a>Toplu kayıt ve Şirket Portalı ile ilgili sorunlar
Bir kullanıcı, daha önce Şirket Portalı kullanılarak toplu olarak kaydedilmiş bir cihazı kaydetmeye çalışırsa cihazının kurulum veya kayıt gibi ek eylemler gerektirdiğine dair uyarılar alır. Cihaz kaydedilir ancak kayıt, Şirket Portalı uygulaması veya web sitesi tarafından tanınmaz.

### <a name="bulk-enrollment-with-wi-fi"></a>Wi-Fi ile toplu kayıt 

Toplu kayıtlı cihazlar, kullanıcı hedefli sertifikaları ve Wi-Fi dağıtımını kullanamaz. Bu bağlantıları yönetmek için [cihaz düzeyinde sertifikalara](certificates-configure.md) ihtiyacınız vardır. 

### <a name="conditional-access"></a>Koşullu erişim
Koşullu erişim, toplu kayıt kullanılarak kaydedilen Windows cihazlar için kullanılamaz.
