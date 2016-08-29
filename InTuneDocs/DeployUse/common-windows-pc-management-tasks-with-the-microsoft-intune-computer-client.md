---
title: "Genel Windows bilgisayarı yönetim görevleri | Microsoft Intune"
description: "Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlarınızı nasıl yöneteceğinizi öğrenmek için bu konu başlığı altındaki görevleri gözden geçirin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6ddb0fda0e818b09d274276076fd6310d29b99cb
ms.openlocfilehash: 8ce6b10478927177e5d6d8de0677cf06bed00f08


---

# Microsoft Intune bilgisayar istemcisi ile genel Windows bilgisayarı yönetim görevleri
Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlarınızı nasıl yöneteceğinizi öğrenmek için bu konu başlığı altındaki görevleri gözden geçirin. İstemciyi bilgisayarlarınıza henüz yüklemediyseniz, bkz. [Microsoft Intune ile Windows bilgisayarı istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).


## PC yönetimi basitleştirmek için ilkeleri kullanma
### Windows Güvenlik Duvarı'nı yönetme
İlkeler, yönetilen bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yönetmeyi kolay hale getirir. Ayrıntılar için bkz. [Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Microsoft Intune Center’ı yönetme
Microsoft Intune Center kullanıcıların şunları yapmasını sağlar:

-   Şirket portalı üzerinden uygulamaları alma.

-   Güncelleştirmeleri denetleme.

-   Microsoft Intune Endpoint Protection’ı yönetme

-  Uzaktan yardım isteyin.

Microsoft Intune Center, tüm yönetilen bilgisayarlarda yüklüdür. Intune ilkesinde aşağıdaki ayarları yapılandırabilirsiniz ve bunlar Microsoft Intune Center’da kullanıcılara gösterilir:

|İlke ayarı|Ayrıntılar|
|------------------|--------------------|
|**Ad**|Bilgisayarı yöneten yöneticinin adı.<br /><br />En fazla uzunluk: 40 karakter|
|**Telefon numarası**|Bilgisayarı yöneten yöneticinin telefon numarası.<br /><br />En fazla uzunluk: 20 karakter|
|**E-posta adresi**|Bilgisayarı yöneten yöneticinin e-posta adresi.<br /><br />En fazla uzunluk: 40 karakter|
|**Web sitesinin adı**|Kullanıcılar için destek web sitenizin adı.<br /><br />En fazla uzunluk: 40 karakter|
|**Web sitesi URL'si**|Destek web sitenizin URL'si.<br /><br />En fazla uzunluk: 150 karakter|
|**Notlar**|Kullanıcılara gösterilen bir not.<br /><br />En fazla uzunluk: 120 karakter|

### Yazılım güncelleştirmeleri ayarlarını yönetme
Yönetilen bilgisayarların Microsoft ve üçüncü taraflardan yazılım güncelleştirmelerini denetlemek ve indirmek için kullandığı ayarları yapılandırmak için ilkeleri kullanın. Daha fazla bilgi için bkz. [Microsoft Intune'da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Endpoint Protection ayarlarını yönetme
Endpoint Protection ayarlarını yapılandırmak için ilkeleri kullanın ve bunları yönetilen bilgisayarlara dağıtın. Bu tarama zamanlama, kötü amaçlı yazılım algıladığında yapılacak işlemler ve daha fazlasını içerir. Daha fazla bilgi için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Donanım ve yazılım envanterini görüntüleme
Intune yönetilen bilgisayarların donanım ve yazılımı hakkında ayrıntılı bilgiler toplar. Şunları oluşturmak için aşağıdaki yordamlardaki bilgileri kullanın:

-   Bilgisayarlarınızın donanım özellikleri hakkında bilgileri listeleyen bir rapor.

-   Her bir bilgisayarda yüklü olan yazılımı listeleyen bir rapor.

-   Rapordaki verilerin güncel olduğundan emin olmak için bilgisayar envanterini yenileme.

### Bilgisayarlarınız hakkındaki bilgileri görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Raporlar** &gt; **Bilgisayar Envanteri Raporları**’nı seçin.

2.   **Yeni Rapor Oluştur** sayfasında, varsayılan değerleri kabul edin veya raporun döndüreceği sonuçlara filtre uygulamak için değerleri özelleştirin. Örneğin, raporda yalnızca Windows 8.1 çalıştıran bilgisayarların görüntülenmesini seçebilirsiniz.

3.  **Bilgisayar Envanteri Raporu**'nu yeni bir pencerede açmak için **Raporu Görüntüle**'yi seçin.

    Her sütunun başlığını seçerek raporu **Ad**, **Kasa Türü** veya **Üretici** gibi sütunlara göre sıralayabilirsiniz.

### Bilgisayarlarda yüklü yazılımı görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Raporlar** &gt; **Algılanan Yazılım Raporları**’nı seçin.

2.   **Yeni Rapor Oluştur** sayfasında, varsayılan değerleri kabul edin veya raporun döndüreceği sonuçlara filtre uygulamak için değerleri özelleştirin. Örneğin, raporda yalnızca Microsoft tarafından yayınlanan yazılımı görüntülemeyi seçebilirsiniz.

3.  **Algılanan Yazılım Raporu**'nu yeni bir pencerede açmak için **Raporu Görüntüle**'yi seçin.

    Her sütunun başlığını seçerek raporu **Ad**, **Yayımcı** veya **Kategori** gibi sütunlara göre sıralayabilirsiniz. Liste öğesinin yanındaki yön okunu seçerek daha fazla ayrıntı (örneğin yüklü olduğu bilgisayarlar) göstermek için listedeki güncelleştirmeleri genişletebilirsiniz.

### Bilgisayar envanterinin güncel olduğundan emin olmak üzere yenilemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya envanterini yenilemek istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Bir bilgisayar seçin veya **Ctrl** tuşunu basılı tutarak birden çok bilgisayarı seçin.

3.  Görev çubuğunda **Uzak Görevler** &gt; **Envanteri Yenile**’yi seçin.

4.  Görev durumunu görüntülemek için, sayfanın sağ alt köşesinde **Uzak Görevler**'i seçin.

     **Görev Durumu** iletişim kutusu geçerli uzak görevler, görev durumu, cihaz adı ve bildirilen hataları gösterir ve sorun giderme bilgilerine bir bağlantı sağlar.


## Windows bilgisayarını uzaktan yeniden başlatma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya yeniden başlatmak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Bir veya birden çok bilgisayar seçin ve ardından **Uzak Görevler** &gt; **Bilgisayarı Yeniden Başlat**’ı seçin.

3.  Görev durumunu görüntülemek için, sayfanın sağ alt köşesinde **Uzak Görevler**'i seçin.

4.   **Görev Durumu** iletişim kutusunda, geçerli uzak görevler, görev durumu, cihaz adı ve bildirilen hataları gözden geçirin.

## Bilgisayarı devre dışı bırakma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya devre dışı bırakmak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Devre dışı bırakmak istediğiniz cihazları seçin ve ardından **Devre Dışı Bırak/Temizle**'yi seçin.

Bir bilgisayarı Intune’a yeniden kaydetmek için, [Microsoft Intune ile Windows bilgisayarı istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md) konusundaki bilgileri kullanarak istemci yazılımı bilgisayara yeniden yükleyin.

Bilgisayar Intune’a bağlanamıyorsa, **Pano** çalışma alanında bir ileti görüntülenir.

Bir bilgisayarı kullanımdan çıkardığınızda:

-   Intune envanterinden kaldırılır ve bilgisayarla ilişkili lisans yeniden kullanılabilir hale gelir.

-   Intune bilgisayarın durumunu artık görüntülemez.

-   Intune istemci yazılımı bilgisayardan kaldırır. Bilgisayar Intune hizmetine bağlı değilse, istemci yazılımı bir sonraki bağlanışında kaldırılır.

-   Microsoft Intune Endpoint Protection bilgisayardan kaldırılır. Bilgisayarda başka bir uç nokta uygulaması yüklüyse ve devre dışı bırakıldıysa, bilgisayarlarınızın korunduğundan emin olmak için Microsoft Intune Endpoint Protection kaldırıldıktan sonra bu uygulama yeniden etkinleştirilebilir.

-   Bilgisayardaki tüm ilkeler kaldırılır ve ilke tarafından ayarlanan değerler değiştirilir.

-   Bilgisayar artık Intune hizmetinden yazılım güncelleştirmeleri veya kötü amaçlı yazılım tanımı güncelleştirmeleri almaz.

-   Yapılandırmaya bağlı olarak, kullanımdan çıkarılan bilgisayarlar Windows Server Update Services, Windows Update veya Microsoft Update'i kullanarak güncelleştirmeleri almaya devam edebilir.

    > [!IMPORTANT]
    > İstemci yazılımı bir Grup İlkesi Nesnesi (GPO) kullanılarak yüklendiyse, yazılımın yeniden yüklenmesini önlemek için istemci yazılımı kaldırmadan önce Grup İlkesi Nesnesi'ni (GPO) kaldırmanız gerekir.

    İstemciyi kaldırma işlemi başarısız olursa daha fazla yardım için [Endpoint Protection’da sorun giderme](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) konusunu okuyun.

## Kullanıcı-cihaz bağlantısını yönetme
Bir kullanıcı için yazılım dağıtmadan önce kullanıcıyı bir bilgisayara bağlamanız gerekir. Bir kullanıcıyı birden çok bilgisayara bağlayabilirsiniz, ancak her bilgisayara yalnızca bir kullanıcı bağlanabilir. Kullanıcılar şirket portalını kullanarak Intune kaydını yaptıkları bilgisayarlara otomatik olarak bağlanır.

### Bir kullanıcıyı bir bilgisayara bağlamak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya bir kullanıcıya bağlamak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Kullanıcıya bağlamak istediğiniz bilgisayarı seçin ve ardından **Kullanıcı Bağla**'yı seçin.

     **Kullanıcı Bağla** iletişim kutusu mevcut kullanıcıların görünen adı, kullanıcı kimliği ve her kullanıcının bağlı olduğu bilgisayar sayısını içeren bir liste görüntüler. Bir kullanıcı seçili bilgisayara zaten bağlıysa, kullanıcının adı ve kullanıcı kimliği **Geçerli kullanıcı**altında gösterilir. Bilgisayar hiçbir kullanıcıya bağlanmamışsa, **Geçerli Kullanıcı** altında **Kullanıcı Yok**görüntülenir.

3.  Aşağıdakilerden birini yapın:

    -   Bilgisayarın bağlı olduğu bir kullanıcı varsa, bilgisayarı bu kullanıcıya bağlı olarak bırakmak için **İptal**'i seçin.

    -   Geçerli kullanıcının (varsa) bağlantısını kaldırmak için **Bağlantıyı Kaldır** &gt; **Tamam**'ı seçin.

    -   Bilgisayarı yeni bir kullanıcıya bağlamak için, **Tüm kullanıcılar** listesinde bir kullanıcı seçin. Kullanıcı verilerinin doğru olduğundan emin olun ve ardından **Tamam**'ı seçin.

> [!TIP]
> Son kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtlamak istiyorsanız, **Microsoft Intune Aracı Ayarları** ilkesinde **Kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtla** seçeneğini etkinleştirin.

## Intune istemci yazılımı çalıştıran Windows bilgisayarlara uzaktan yardım isteme ve yardım sağlama

Microsoft Intune, Intune istemci yazılımını çalıştıran bilgisayarların kullanıcılarına sizden uzaktan yardım alma olanağı tanımak için [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Kullanıcı Microsoft Intune Center’dan yardım isteğinde bulunduğunda, bu durum bir uyarıyla size bildirilir; siz bu isteği kabul edebilir ve yardım sağlarsınız.
Bu işlevsellik, Intune’da var olan Windows Uzaktan Yardım işlevselliğinin yerini alır.


### Başlamadan önce

Uzaktan yardım isteklerine hazırlanmaya ve bu istekleri yanıtlamaya başlayabilmeniz için önce aşağıdaki önkoşulların karşılandığından emin olmalısınız:

- TeamViewer web sitesinde oturum açmak için [bir TeamViewer hesabına kaydolmuş](https://login.teamviewer.com/LogOn#register) olmanız gerekir.
- Yönetmek istediğiniz Windows bilgisayarların [Windows bilgisayar istemcisiyle yönetiliyor](manage-windows-pcs-with-microsoft-intune.md) olması gerekir.
- Intune tarafından desteklenen tüm Windows bilgisayarı işletim sistemleri yönetilebilir.

### TeamViewer Bağlayıcısı'nı yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
2. **Yönetici** çalışma alanında **TeamViewer**’ı seçin.
3. **TeamViewer** sayfasındaki **TeamViewer Bağlayıcısı**’nın altında **Etkinleştir**’i seçin.
4. **TeamViewer’ı Etkinleştir** iletişim kutusunda lisans koşullarını görüntüleyin ve **Kabul Et**’i seçin. Zaten bir TeamViewer lisansınız yoksa, **TeamViewer lisansı satın alın** öğesini seçin.
5. TeamViewer tarayıcı penceresi açıldıktan sonra, TeamViewer kimlik bilgilerinizle sitede oturum açın.
6. TeamViewer sitesinde, Intune’un TeamViewer’a bağlanmasına izin verme seçeneklerini okuyun ve sonra da kabul edin.
7. Intune konsolunda, **TeamViewer Bağlayıcısı** öğesinin **Etkin** durumda gösterildiğinden emin olun.


### Uzaktan yardım isteği açma (son kullanıcı)

1. İstemci Windows bilgisayarında **Microsoft Intune Center**’ı açın.
2. **Uzaktan Yardım**’ın altında **Uzaktan Yardım İste**’yi seçin.
3. Siz isteği onayladıktan sonra (aşağıya bakın), istemcide TeamViewer açılır. Kullanıcı, web tarayıcısının TeamViewer uygulamasını açmaya çalıştığını bildiren tüm iletileri kabul etmelidir.
4. Kullanıcı, bilgisayarını denetleyip denetleyemeyeceğinizi soran bir ileti görür. Devam etmek için bu iletiyi kabul etmesi gerekir.
5. Uzaktan yardım oturumu boyunca, kullanıcı sizin bağlı olduğunuzu gösteren bir pencere görür. Bu pencereyi kapatırsa, uzak oturum sona erer.

### Uzaktan yardım isteğini yanıtlama

1. Kullanıcı bir uzaktan yardım isteği gönderdiğinde, bu isteği **Uyarılar** çalışma alanındaki **İzleme** > **Uzaktan Yardım**’ın altında görebilirsiniz. Örneğin:
> ![Uzaktan yardım isteğinin ekran görüntüsü](./media/team-viewer.png)

<br>İstek 4 saatten uzun süre yanıtlanmadan kalırsa, kaldırılır.
2. İsteği kabul etmek için, **İsteği onaylayın ve Uzaktan Yardım’ı başlatın** öğesini seçin.
3. **Yeni Bir Uzaktan Yardım İsteği Bekliyor** iletişim kutusunda **Uzaktan yardım isteğini kabul et**’i seçin. Zaten yüklü değilse, TeamViewer tüm gerekli uygulamaları bilgisayarınıza yükler.
4. Ardından TeamViewer, bilgisayarının denetimini almak istediğinizi son kullanıcıya bildirir. Kullanıcı isteği kabul ettikten sonra, TeamViewer penceresi açılır ve bilgisayarın denetimini alabilirsiniz.

Uzaktan yardım oturumu sırasında, uzak bilgisayarı denetlemek için tüm sağlanan TeamViewer komutlarını kullanabilirsiniz. Bu komutlar hakkında yardım için, TeamViewer web sitesinden [Uzaktan kontrol kılavuzu](http://www.teamviewer.com/en/support/documents/)’nu indirin.

### Uzaktan yardım oturumunu kapatma

**TeamViewer** penceresinin **Eylemler** penceresinde **Oturumu Sonlandır**’ı seçin.



<!--HONumber=Aug16_HO1-->


