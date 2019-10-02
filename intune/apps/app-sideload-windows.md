---
title: Windows ve Windows Phone uygulamalarını dışarıdan yükleme
titleSuffix: Microsoft Intune
description: Intune’u kullanarak iş kolu uygulamalarını dağıtmak için bunları nasıl imzalayacağınızı öğrenin.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 09/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c1d039d5be449d1c1b8cc13e69b84e1bd7f7dd2b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731289"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Intune ile Windows cihazlarına dağıtmak için iş kolu uygulamalarını imzalayın

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Bir Intune Yöneticisi olarak, Şirket Portalı uygulaması da dahil olmak üzere masaüstü veya Windows 10 Masaüstü & Mobil cihazlara Windows 8.1 iş kolu (LOB) Universal uygulamaları dağıtabilirsiniz. Windows 8.1. appx uygulamalarını masaüstü veya Windows 10 Masaüstü & Mobil cihazlara dağıtmak için, Windows cihazlarınız tarafından zaten güvenilen bir genel sertifika yetkilisinden kod imzalama sertifikası kullanabilir veya kendi sertifika yetkilinizi kullanabilirsiniz.

 > [!NOTE]
 > Windows 8.1 Masaüstü, dışarıdan yüklemeyi etkinleştirmek için bir kuruluş ilkesi veya dışarıdan Yükleme anahtarlarının (etki alanına katılmış cihazlar için otomatik olarak etkinleştirilir) kullanılmasını gerektirir. Daha fazla bilgi için bkz. [Windows 8 dışarıdan yükleme](https://blogs.technet.microsoft.com/scd-odtsp/2012/09/27/windows-8-sideloading-requirements-from-technet/).

## <a name="windows-10-sideloading"></a>Windows 10 dışarıdan yükleme

Windows 10 ' da, dışarıdan yükleme Windows 'un önceki sürümlerinden farklıdır:

- Kurumsal bir ilke kullanarak dışarıdan yükleme için bir cihazın kilidini açabilirsiniz. Intune, "güvenilir uygulama yüklemesi" adlı bir cihaz yapılandırma ilkesi sağlar. Bunun <allow> olarak ayarlanması, appx uygulamasını imzalamak için kullanılan sertifikaya zaten güvenecek olan cihazlar için gereklidir.

- Symantec telefon sertifikaları ve dışarıdan yükleme lisans anahtarları gerekli değildir. Ancak, şirket içi bir sertifika yetkilisi yoksa, bir genel sertifika yetkilisinden kod imzalama sertifikası edinmeniz gerekebilir. Daha fazla bilgi için bkz. [kod Imzalamaya giriş](https://docs.microsoft.com/windows/desktop/SecCrypto/cryptography-tools#introduction-to-code-signing).

### <a name="code-sign-your-app"></a>Uygulamanızı kodla imzalama

İlk adım, appx paketinizi yeniden kodlayabilirseniz. Ayrıntılar için bkz. [SignTool kullanarak uygulama paketini imzalama](https://docs.microsoft.com/windows/uwp/packaging/sign-app-package-using-signtool).

### <a name="upload-your-app"></a>Uygulamanızı karşıya yükleyin

Ardından, imzalanmış appx dosyasını karşıya yüklemeniz gerekir. Ayrıntılar için bkz. [Windows iş kolu uygulaması ekleme Microsoft Intune](lob-apps-windows.md).

Uygulamayı kullanıcılara veya cihazlara gereken şekilde dağıtırsanız, ınutne Şirket Portalı uygulamasına ihtiyacınız yoktur. Ancak, uygulamayı kullanıcılara kullanılabilir olarak dağıtırsanız, ortak Microsoft Store Şirket Portalı uygulamayı kullanabilir, Iş için özel Microsoft Store Şirket Portalı uygulamayı kullanabilir veya Intune şirketini imzalayıp el ile dağıtmanız gerekir Portal uygulaması.

### <a name="upload-the-code-signing-certificate"></a>Kod imzalama sertifikasını karşıya yükleme

Windows 10 cihazınız sertifika yetkilisine zaten güvenmezse, appx paketinizi imzaladıktan ve Intune hizmetine yükledikten sonra, kod imzalama sertifikasını Intune portalına yüklemeniz gerekir:
1. Istemci uygulamaları ' na tıklayın
2. Windows Kurumsal sertifikaları ' na tıklayın
3. Kod imzalama sertifikası altında ' Dosya Seç ' seçeneğini belirleyin
4. . Cer dosyanızı seçip karşıya yükle ' ye tıklayın.

Artık, Intune hizmeti tarafından bir appx dağıtımı olan Windows 10 Masaüstü & mobil cihaz, ilgili kurumsal sertifikayı otomatik olarak indirir ve uygulamanın yüklemeden sonra çalışmasına izin verilir.

Intune yalnızca karşıya yüklenen en son. cer dosyasını dağıtır. Kuruluşunuz ile ilişkilendirilmemiş farklı geliştiriciler tarafından oluşturulmuş birden çok appx dosyası varsa, bu kişilere sertifika imzalama için imzasız appx dosyaları sağlamanızı ya da bunları tarafından kullanılan kod imzalama sertifikasını sağlamanız gerekir. Kuruluşunuz.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Symantec kurumsal kod imzalama sertifikasını yenileme

Windows Phone 8,1 mobil uygulamaları dağıtmak için kullanılan sertifika, 28 2019 Şubat tarihinde kaldırılmıştır ve artık Symantec 'ten yenileme için kullanılamaz. WIndows 10 Mobile 'a dağıtıyorsanız, [Windows 10 dışarıdan yükleme](app-sideload-windows.md#windows-10-sideloading) yönergelerini Izleyerek Symantec masaüstü kurumsal kod imzalama sertifikaları kullanmaya devam edebilirsiniz.

## <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>İş kolu (LOB) uygulamaları için güncelleştirilmiş sertifika yükleme

WVPN profillerinidows Phone 8.1

Intune hizmeti, mevcut Symantec mobil kurumsal kod imzalama sertifikasının süresi dolduktan sonra bu platform için LOB uygulamalarını artık dağıtmaz. SD kart kullanılarak veya dosyayı cihaza indirerek imzasız XAP/APPX dosyalarını dışarıdan yüklemek yine de mümkün olacaktır. Daha fazla bilgi için bkz. [WINDOWS Phone XAP dosyalarını yüklemek](https://answers.microsoft.com/en-us/mobiledevices/forum/mdlumia-mdapps/how-to-install-xap-file-in-windows-phone-8/da09ee72-51ae-407c-9b85-bc148df89280).

Windows 8.1 Masaüstü/Windows 10 Masaüstü & Mobile

Sertifika döneminin süresi dolmuşsa, appx dosyaları başlatmayı durdurabilir. Yeni bir. cer dosyası edinmeniz ve dağıtılan her bir appx dosyasını kod imzalama ve tüm appx dosyalarını ve güncelleştirilmiş. cer dosyasını Intune portalının Windows Enterprise Certificates bölümüne yeniden yükleme yönergelerini izlemeniz gerekir.

## <a name="manually-deploy-windows-10-company-portal-app"></a>Windows 10 Şirket Portalı uygulamasını el ile dağıtma
Microsoft Store erişim sağlamak istemiyorsanız, Intune 'u Iş Microsoft Store (MSFB) ile tümleştirmemiş olsanız bile Windows 10 Şirket Portalı uygulamasını doğrudan Intune 'dan el ile dağıtabilirsiniz. Alternatif olarak, tümleştirdiyseniz, [MSFB kullanarak uygulama dağıtma](store-apps-windows.md)aracılığıyla şirket portalı uygulamasını dağıtabilirsiniz.

 > [!NOTE]
 > Bu seçeneğin kullanılması, her uygulama güncelleştirmesi yayımlandığında el ile güncelleştirme dağıtılmasını gerektirir.

1. [İş için Microsoft Store](https://www.microsoft.com/business-store) hesabınızda oturum açın ve şirket portalı uygulamasının **Çevrimdışı lisans** sürümünü edinin.  
2. Uygulamayı aldıktan sonra **Envanter** sayfasında uygulamayı seçin.  
3. **Platform** olarak **Windows 10 tüm cihazlar**’ı ve uygun **Mimari**’yi seçip sonra indirin. Bu uygulama için bir uygulama lisans dosyası gerekmez.
   Yükleme için Windows 10 x86 paket ayrıntılarının ![Görüntüsü @ no__t-1
4. "Gerekli Çerçeveler" başlığı altındaki tüm paketleri indirin. Bu işlem x86, x64 ve ARM mimarileri için gerçekleştirilmelidir. Böylece aşağıda gösterildiği gibi toplam 9 paket gerekir.

   ![İndirilecek bağımlılık dosyalarının görüntüsü ](./media/app-sideload-windows/Win10CP-dependent-files.png)
5. Şirket Portalı uygulamasını Intune’a yüklemeden önce, paketlerin aşağıdaki şekilde yapılandırıldığı bir klasör (ör. C:&#92;Company Portal) oluşturun:
   1. Şirket Portalı paketini C:\Company Portal adresine koyun. Bu konumda bir Dependencies alt klasörü oluşturun.  
      ![APPXBUN dosyasıyla kaydedilen Dependencies klasörünün görüntüsü](./media/app-sideload-windows/Win10CP-Dependencies-save.png)
   2. Dokuz bağımlılık paketini Dependencies klasörüne yerleştirin.  
      Bağımlılıklar, bu biçimde yerleştirilmezse Intune tarafından tanınamazlar ve paketin karşıya yüklenmesi sırasında karşıya yüklenemezler. Bu durumda, karşıya yükleme aşağıdaki hatayı vererek başarısız olur.  
      ![Hata iletisi-Windows uygulaması bağımlılığı sağlanmalıdır.](./media/app-sideload-windows/Win10CP-error-message.png)
6. Intune'a dönün ve Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. Uygulamayı, istenen hedef kullanıcı kümesine gerekli bir uygulama olarak dağıtın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı’nı nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Mağaza'dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak yeni sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Mağaza uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini denetlemelerini isteyin.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için dağıtım eylemini "Kaldır" şeklinde ayarlayarak dağıtımı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması yukarıdaki seçeneklerden herhangi biri kullanılarak dağıtılabilir.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan dağıttıysanız, yükseltmeyi tamamlamak için yukarıdaki Doğrudan Intune aracılığıyla dağıtma bölümünde sunulan adımları izleyin.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec kod imzalama sertifikası ile imzalayıp dağıttıysanız aşağıdaki bölümde sunulan adımları izleyin.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenmiş ve imzalı Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulaması için dağıtım eylemini "Kaldır" şeklinde ayarlayarak mevcut dağıtımı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması normal bir biçimde dağıtılabilir.  

Aksi takdirde, yükseltme yoluna uyulduğundan emin olmak için Windows 10 Şirket Portalı uygulamasının uygun şekilde güncelleştirilmesi ve imzalanması gerekir.  

Windows 10 Şirket Portalı uygulaması bu şekilde imzalanır ve dağıtılırsa, mağazada kullanıma sunulan her yeni uygulama güncelleştirmesi için bu işlemi tekrarlamanız gerekecektir. Mağaza güncelleştirildiğinde uygulama otomatik olarak güncelleştirilmez.  

Uygulamanın bu şekilde nasıl imzalanıp dağıtılacağı aşağıda açıklanmaktadır:

1. Microsoft Intune Windows 10 Şirket Portalı Uygulaması İmzalama Betiğini [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) adresinden indirin.  Bu betik, Windows 10 için Windows SDK’nın ana bilgisayara yüklenmiş olmasını gerektirir. Windows 10 için Windows SDK’sını indirmek için [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) adresini ziyaret edin.
2. Windows 10 Şirket Portalı uygulamasını yukarıda açıklandığı biçimde İş İçin Microsoft Mağazası'ndan indirin.  
3. Betik üst bilgisinde açıklanan giriş parametrelerini (ayıklanmış hali aşağıdadır) kullanıp betiği çalıştırarak Windows 10 Şirket Portalı uygulamasını imzalayın. Bağımlılıkların betiğe geçirilmesi gerekmez. Bunlar, yalnızca uygulama Intune Yönetici Konsolu’na yüklenirken gereklidir.

|       Parametre       |                                                                    Description                                                                    |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                             Kaynak appxbundle dosyasının bulunduğu yol.                                              |
| OutputWin10AppxBundle |                                                  İmzalı appxbundle dosyası için çıkış yolu.                                                  |
|       Win81Appx       |                          Windows 8.1 veya Windows Phone 8.1 Şirket Portalı (.APPX) dosyasının bulunduğu yol.                           |
|      PfxFilePath      |                                   Symantec Enterprise Mobil Kod İmza Sertifikası (.PFX) dosyasının yolu.                                    |
|      PfxPassword      |                                     Symantec Enterprise Mobil Kod İmza Sertifikası’nın parolası.                                      |
|      PublisherId      |      Kuruluşun Yayımcı Kimliği. Yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın 'Konu' alanı kullanılır.       |
|        SdkPath        | Windows 10 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\10 değerindedir. |

Betik, çalışması tamamlandığında Windows 10 Şirket Portalı uygulamasının imzalı sürümünü çıktı olarak sunar. Ardından Intune aracılığıyla uygulamanın imzalı sürümünü bir LOB uygulaması olarak dağıtabilirsiniz. Şu anda dağıtılmış durumdaki sürümler, bu yeni uygulamaya yükseltilir.  
