---
title: Windows 10 Şirket Portalı uygulamasını el ile ekleme
titleSuffix: Microsoft Intune
description: Windows 10 Şirket Portalı uygulamasını el ile eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2c7e449e9931bccd5e736bd09c33e0b42c623e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Son kullanıcılar cihazları yönetmek ve uygulama yüklemek için Intune Şirket Portalı uygulamasını Microsoft Mağazası'ndan yükleyebilir. Ancak şirketiniz, Intune Şirket Portalı uygulamasını sizin atamanızı gerektiriyorsa Intune ile İş İçin Microsoft Mağazası'nı tümleştirmiş olmasanız bile Windows 10 Şirket Portalı uygulamasını doğrudan Intune'dan atayabilirsiniz.

 > [!NOTE]
 > Bu seçeneğin kullanılması, her uygulama güncelleştirmesi yayımlandığında el ile güncelleştirme atanmasını gerektirir.

## <a name="configure-settings-to-show-offline-apps"></a>Çevrimdışı uygulamaları göstermek için ayarları yapılandırma
1. [İş için Microsoft Store](https://www.microsoft.com/business-store)'a gidin ve yönetici hesabınızla oturum açtığınızdan emin olun.
2. Pencerenin üst kısmında **Yönet** sekmesini seçin.
3. Sol gezinti sütununda **Ayarlar**'ı seçin.
4. **Alışveriş deneyimi** bölümündeki **Çevrimdışı uygulamaları göster** seçeneğini **Açık** olarak ayarlayın. Bu, İş için Microsoft Store'daki çevrimdışı lisanslı uygulamaları gösterir.

## <a name="download-the-offline-company-portal-app"></a>Çevrimdışı Şirket Portalı uygulamasını indirme
1. **Şirket Portalı** uygulamasını arayın ve seçin.
2. **Lisans türü** olarak **Çevrimdışı** ayarlayın.
3. Çevrimdışı Şirket Portalı uygulamasını almak ve envanterinize eklemek için **Uygulamayı al**'a tıklayın.
4. **Şirket Portalı** uygulama sayfasında **Yönet**'e tıklayın.
5. **Platform** olarak **Windows 10 tüm cihazlar**'ı seçin ve ardından uygun **En düşük sürüm**, **Mimari** ve Uygulama indirme meta veri** değerlerini seçin. 
6. Dosyayı yerel makinenize kaydetmek için **İndir**'e tıklayın.

    ![İndirme işlemi için Windows 10 tüm cihazlar ve Mimari X86 paketi ayrıntılarının resmi](./media/Win10CP-all-devices.png)

7. "Gerekli Çerçeveler" başlığı altındaki tüm paketleri indirin. Bu işlem x86, x64 ve ARM mimarileri için gerçekleştirilmelidir. Böylece toplam 12 paket gerekir.
8. Şirket Portalı uygulamasını Intune’a yüklemeden önce, paketlerin aşağıdaki şekilde yapılandırıldığı bir klasör (ör: C:&#92;Şirket Portalı) oluşturun:
   - Şirket Portalı paketini C:\Company Portal adresine koyun. Bu konumda bir Dependencies alt klasörü oluşturun.  

     ![APPXBUN dosyasıyla kaydedilen Dependencies klasörünün görüntüsü](./media/Win10CP-Dependencies-save.png)

   - Bağımlılık paketlerini *Dependencies* klasörüne yerleştirin. 

     > [!NOTE]
     > Bağımlılıklar, doğru biçimde yerleştirilmezse, Intune dosyaları tanıyamaz ve paket karşıya yükleme işlemi sırasında bunları karşıya yükleyemez. Bu durumda, karşıya yükleme başarısız olur ve bir hata görüntülenir.

9. Azure portalında Microsoft Intune’a dönün.
10. Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. Uygulamayı, istenen hedef kullanıcı kümesine gerekli bir uygulama olarak atayın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı’nı nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Mağaza'dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak yeni sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Mağaza uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini denetlemelerini isteyin.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için atama eylemini "Kaldır" olarak ayarlayıp atamayı silmektir. Bu ayar yapıldıktan sonra Windows 10 Şirket Portalı uygulaması yukarıdaki seçeneklerden herhangi biri kullanılarak atanabilir.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan atadıysanız, yükseltmeyi tamamlamak için yukarıdaki Doğrudan Intune aracılığıyla atama bölümünde sunulan adımları izleyin.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec kod imzalama sertifikası ile imzalayıp atadıysanız aşağıdaki bölümde sunulan adımları izleyin.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenmiş ve imzalı Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulaması için atama eylemini "Kaldır" şeklinde ayarlayarak mevcut atamayı silmektir. Bu ayar yapıldıktan sonra Windows 10 Şirket Portalı uygulaması normal bir biçimde atanabilir.  

Aksi takdirde, yükseltme yoluna uyulduğundan emin olmak için Windows 10 Şirket Portalı uygulamasının uygun şekilde güncelleştirilmesi ve imzalanması gerekir.  

Windows 10 Şirket Portalı uygulaması bu şekilde imzalanır ve atanırsa, mağazada kullanıma sunulan her yeni uygulama güncelleştirmesi için bu işlemi tekrarlamanız gerekecektir. Mağaza güncelleştirildiğinde uygulama otomatik olarak güncelleştirilmez.  

Uygulamanın bu şekilde nasıl imzalanıp atanacağı aşağıda açıklanmaktadır:

1. Microsoft Intune Windows 10 Şirket Portalı Uygulaması İmzalama Betiğini [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) adresinden indirin.  Bu betik, Windows 10 için Windows SDK’nın ana bilgisayara yüklenmiş olmasını gerektirir. Windows 10 için Windows SDK’sını indirmek için [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) adresini ziyaret edin.
2. Windows 10 Şirket Portalı uygulamasını yukarıda açıklandığı biçimde İş İçin Microsoft Mağazası'ndan indirin.  
3. Betik üst bilgisinde açıklanan giriş parametrelerini (ayıklanmış hali aşağıdadır) kullanıp betiği çalıştırarak Windows 10 Şirket Portalı uygulamasını imzalayın. Bağımlılıkların betiğe geçirilmesi gerekmez. Bunlar, yalnızca uygulama Intune Yönetici Konsolu’na yüklenirken gereklidir.

|       Parametre       |                                                                        Description                                                                        |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                                  Kaynak appxbundle dosyasının bulunduğu konumun yolu                                                  |
| OutputWin10AppxBundle | İmzalı appxbundle dosyası için çıkış yolu.  Win81Appx Windows 8.1 veya Windows Phone 8.1 Şirket Portalı (. APPX) dosyasının bulunduğu konumun yolu. |
|      PfxFilePath      |                                       Symantec Enterprise Mobil Kod İmza Sertifikası (.PFX) dosyasının yolu.                                        |
|      PfxPassword      |                                         Symantec Enterprise Mobil Kod İmza Sertifikası’nın parolası.                                          |
|      PublisherId      |          Kuruluşun Yayımcı Kimliği. Yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın 'Konu' alanı kullanılır.           |
|        SdkPath        |     Windows 10 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\10 değerindedir.     |

Betik, çalışması tamamlandığında Windows 10 Şirket Portalı uygulamasının imzalı sürümünü çıktı olarak sunar. Ardından Intune aracılığıyla uygulamanın imzalı sürümünü bir LOB uygulaması olarak atayabilirsiniz. Şu anda atanmış durumdaki sürümler, bu yeni uygulamaya yükseltilir.  

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulamaları gruplara ekleme](apps-deploy.md)

