---
title: "Windows mağaza uygulamalarını Intune’a ekleme"
titleSuffix: Intune on Azure
description: "Intune'a Windows mağazası uygulamaları ekleme hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 812bdf5bde724798289668937ed2502438c524e0
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde **Uygulama Bilgileri**’ni seçin.
7. **Uygulamayı Düzenle** dikey penceresinde aşağıdaki bilgileri yapılandırın. Bitirdiğinizde, **Ekle**’ye tıklayın. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Uygulama Adı** - Uygulamanın şirket portalında görüntülenecek olan adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Uygulama Açıklaması** - Uygulama için bir açıklama girin. Bu, şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Uygulama mağazası URL’si** - Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin.
    - **Minimum İşletim Sistemi** - Listeden uygulamanın yüklenebileceği minimum işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Simgeyi Karşıya Yükle** - Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.
8. İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Kaydet**’i seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>Windows 10 Şirket Portalı uygulamasını el ile atama
Son kullanıcılar cihazları yönetmek ve uygulama yüklemek için Intune Şirket Portalı uygulamasını Microsoft Mağazası'ndan yükleyebilir. Ancak şirketiniz, Intune Şirket Portalı uygulamasını sizin atamanızı gerektiriyorsa Intune ile İş İçin Microsoft Mağazası'nı tümleştirmiş olmasanız bile Windows 10 Şirket Portalı uygulamasını doğrudan Intune'dan atayabilirsiniz.

 > [!NOTE]
 > Bu seçeneğin kullanılması, her uygulama güncelleştirmesi yayımlandığında el ile güncelleştirme atanmasını gerektirir.

1. [İş İçin Microsoft Mağazası](https://www.microsoft.com/business-store)’ndaki hesabınızda oturum açın ve Intune Şirket Portalı uygulamasının **çevrimdışı lisanslı** sürümünü edinin.  
2. Uygulamayı aldıktan sonra **Envanter** sayfasında uygulamayı seçin.  
3. **Platform** olarak **Windows 10 tüm cihazlar**’ı ve uygun **Mimari**’yi seçip sonra indirin. Bu uygulama için bir uygulama lisans dosyası gerekmez.
![İndirme işlemi için Windows 10 tüm cihazlar ve Mimari X86 Paketi ayrıntılarının görüntüsü](./media/Win10CP-all-devices.png)
4. "Gerekli Çerçeveler" başlığı altındaki tüm paketleri indirin. Bu işlem x86, x64 ve ARM mimarileri için gerçekleştirilmelidir. Böylece aşağıda gösterildiği gibi toplam 9 paket gerekir.

![İndirilecek bağımlılık dosyalarının görüntüsü ](./media/Win10CP-dependent-files.png)
5. Şirket Portalı uygulamasını Intune’a yüklemeden önce, paketlerin aşağıdaki şekilde yapılandırıldığı bir klasör (ör. C:&#92;Company Portal) oluşturun:
  1. Şirket Portalı paketini C:\Company Portal adresine koyun. Bu konumda bir Dependencies alt klasörü oluşturun.  
  ![APPXBUN dosyasıyla kaydedilen Dependencies klasörünün görüntüsü](./media/Win10CP-Dependencies-save.png)
  2. Dokuz bağımlılık paketini Dependencies klasörüne yerleştirin.  
  Bağımlılıklar, bu biçimde yerleştirilmezse Intune tarafından tanınamazlar ve paketin karşıya yüklenmesi sırasında karşıya yüklenemezler. Bu durumda, karşıya yükleme aşağıdaki hatayı vererek başarısız olur.  
  ![Bu yazılım yükleyicisine ait Windows uygulama bağımlılığı, uygulama klasöründe bulunamadı. Bu uygulamayı oluşturmaya ve atamaya devam edebilirsiniz ancak uygulama, eksik Windows uygulama bağımlılığı sağlanmadıkça çalışmayacaktır.](./media/Win10CP-error-message.png)
6. Intune'a dönün ve Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. Uygulamayı, istenen hedef kullanıcı kümesine gerekli bir uygulama olarak atayın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı’nı nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Mağaza'dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak yeni sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Mağaza uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini denetlemelerini isteyin.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için atama eylemini "Kaldır" şeklinde ayarlayarak atamayı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması yukarıdaki seçeneklerden herhangi biri kullanılarak atanabilir.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan atadıysanız, yükseltmeyi tamamlamak için yukarıdaki Doğrudan Intune aracılığıyla atama bölümünde sunulan adımları izleyin.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec kod imzalama sertifikası ile imzalayıp atadıysanız aşağıdaki bölümde sunulan adımları izleyin.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenmiş ve imzalı Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulaması için atama eylemini "Kaldır" şeklinde ayarlayarak mevcut atamayı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması normal bir biçimde atanabilir.  

Aksi takdirde, yükseltme yoluna uyulduğundan emin olmak için Windows 10 Şirket Portalı uygulamasının uygun şekilde güncelleştirilmesi ve imzalanması gerekir.  

Windows 10 Şirket Portalı uygulaması bu şekilde imzalanır ve atanırsa, mağazada kullanıma sunulan her yeni uygulama güncelleştirmesi için bu işlemi tekrarlamanız gerekecektir. Mağaza güncelleştirildiğinde uygulama otomatik olarak güncelleştirilmez.  

Uygulamanın bu şekilde nasıl imzalanıp atanacağı aşağıda açıklanmaktadır:

1. Microsoft Intune Windows 10 Şirket Portalı Uygulamasını İmzalama Betiğini [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) adresinden indirin.  Bu betik, Windows 10 için Windows SDK’nın ana bilgisayara yüklenmiş olmasını gerektirir. Windows 10 için Windows SDK’yı indirmek için [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) adresini ziyaret edin.
2. Windows 10 Şirket Portalı uygulamasını yukarıda açıklandığı biçimde İş İçin Microsoft Mağazası'ndan indirin.  
3. Betik üst bilgisinde açıklanan giriş parametrelerini (ayıklanmış hali aşağıdadır) kullanıp betiği çalıştırarak Windows 10 Şirket Portalı uygulamasını imzalayın. Bağımlılıkların betiğe geçirilmesi gerekmez. Bunlar, yalnızca uygulama Intune Yönetici Konsolu’na yüklenirken gereklidir.

|Parametre | Açıklama|
| ------------- | ------------- |
|InputWin10AppxBundle |Kaynak appxbundle dosyasının bulunduğu konumun yolu |
|OutputWin10AppxBundle |İmzalı appxbundle dosyası için çıkış yolu.  Win81Appx Windows 8.1 veya Windows Phone 8.1 Şirket Portalı (. APPX) dosyasının bulunduğu konumun yolu.|
|PfxFilePath |Symantec Enterprise Mobil Kod İmza Sertifikası (.PFX) dosyasının yolu. |
|PfxPassword| Symantec Enterprise Mobil Kod İmza Sertifikası’nın parolası. |
|PublisherId |Kuruluşun Yayımcı Kimliği. Yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın 'Konu' alanı kullanılır.|
|SdkPath | Windows 10 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\10 değerindedir.|
Betik, çalışması tamamlandığında Windows 10 Şirket Portalı uygulamasının imzalı sürümünü çıktı olarak sunar. Ardından Intune aracılığıyla uygulamanın imzalı sürümünü bir LOB uygulaması olarak atayabilirsiniz. Şu anda atanmış durumdaki sürümler, bu yeni uygulamaya yükseltilir.  
