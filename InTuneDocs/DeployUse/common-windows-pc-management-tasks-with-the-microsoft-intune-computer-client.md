---
# required metadata

title: Genel Windows bilgisayarı yönetim görevleri | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune bilgisayar istemcisi ile genel Windows bilgisayarı yönetim görevleri
Intune istemcisi çalıştıran bilgisayarlarınızı nasıl yöneteceğinizi öğrenmek için bu konu başlığı altındaki görevleri gözden geçirin. İstemciyi bilgisayarlarınıza henüz yüklemediyseniz, bkz. [Microsoft Intune ile Windows bilgisayarı istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).


## PC yönetimi basitleştirmek için ilkeleri kullanma
### Windows Güvenlik Duvarı'nı yönetme
İlkeler, yönetilen bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yönetmeyi kolay hale getirir. Ayrıntılar için bkz. [Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)

### Microsoft Intune Center’ı yönetme
Microsoft Intune Center kullanıcıların şunları yapmasını sağlar:

-   Şirket portalı üzerinden uygulamaları alma.

-   Güncelleştirmeleri denetleme.

-   Microsoft Intune Endpoint Protection’ı yönetme

-   Uzaktan yardım isteyin.

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

    Her sütunun başlığını seçerek raporu **Ad**, **Yayımcı** veya **Kategori** gibi sütunlara göre sıralayabilirsiniz. Liste öğesinin yanındaki yön okuna tıklayarak daha fazla ayrıntı (örneğin yüklü olduğu bilgisayarlar) göstermek için listedeki güncelleştirmeleri genişletebilirsiniz.

### Bilgisayar envanterinin güncel olduğundan emin olmak üzere yenilemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya envanterini yenilemek istediğiniz bilgisayarı içeren farklı bir grubu) seçin.

2.  Bir bilgisayar seçin veya **Ctrl** tuşunu basılı tutarak birden çok bilgisayarı seçin.

3.  Görev çubuğunda, **Uzak Görevler** &gt; **Envanteri Yenile**’yi seçin.

4.  Görev durumunu görüntülemek için, sayfanın sağ alt köşesinde **Uzak Görevler**'i seçin.

     **Görev Durumu** iletişim kutusu geçerli uzak görevler, görev durumu, cihaz adı ve bildirilen hataları gösterir ve sorun giderme bilgilerine bir bağlantı sağlar.


## Windows bilgisayarını uzaktan yeniden başlatma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya yeniden başlatmak istediğiniz bilgisayarı içeren farklı bir grubu) seçin.

2.  Bir veya birden çok bilgisayar seçin ve ardından **Uzak Görevler** &gt; **Bilgisayarı Yeniden Başlat**’ı seçin.

3.  Görev durumunu görüntülemek için, sayfanın sağ alt köşesinde **Uzak Görevler**'i seçin.

4.   **Görev Durumu** iletişim kutusunda, geçerli uzak görevler, görev durumu, cihaz adı ve bildirilen hataları gözden geçirin.

## Bilgisayarı devre dışı bırakma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya devre dışı bırakmak istediğiniz bilgisayarı içeren farklı bir grubu) seçin.

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

    > İstemci yazılımı bir Grup İlkesi Nesnesi (GPO) kullanılarak yüklendiyse, yazılımın yeniden yüklenmesini önlemek için istemci yazılımı kaldırmadan önce Grup İlkesi Nesnesi'ni (GPO) kaldırmanız gerekir.

    İstemciyi kaldırma işlemi başarısız olursa daha fazla yardım için [Endpoint Protection’da sorun giderme](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) konusunu okuyun.

## Kullanıcı-cihaz bağlantısını yönetme
Bir kullanıcı için yazılım dağıtmadan önce kullanıcıyı bir bilgisayara bağlamanız gerekir. Bir kullanıcıyı birden çok bilgisayara bağlayabilirsiniz, ancak her bilgisayara yalnızca bir kullanıcı bağlanabilir. Kullanıcılar şirket portalını kullanarak Intune kaydını yaptıkları bilgisayarlara otomatik olarak bağlanır.

### Bir kullanıcıyı bir bilgisayara bağlamak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya bir kullanıcıya bağlamak istediğiniz bilgisayarı içeren farklı bir grubu) seçin.

2.  Kullanıcıya bağlamak istediğiniz bilgisayarı seçin ve ardından **Kullanıcı Bağla**'yı seçin.

     **Kullanıcı Bağla** iletişim kutusu mevcut kullanıcıların görünen adı, kullanıcı kimliği ve her kullanıcının bağlı olduğu bilgisayar sayısını içeren bir liste görüntüler. Bir kullanıcı seçili bilgisayara zaten bağlıysa, kullanıcının adı ve kullanıcı kimliği **Geçerli kullanıcı**altında gösterilir. Bilgisayar hiçbir kullanıcıya bağlanmamışsa, **Geçerli Kullanıcı** altında **Kullanıcı Yok** görüntülenir.

3.  Aşağıdakilerden birini yapın:

    -   Bilgisayarın bağlı olduğu bir kullanıcı varsa, bilgisayarı bu kullanıcıya bağlı olarak bırakmak için **İptal**'i seçin.

    -   Geçerli kullanıcının (varsa) bağlantısını kaldırmak için **Bağlantıyı Kaldır**&gt;**Tamam**'ı seçin.

    -   Bilgisayarı yeni bir kullanıcıya bağlamak için, **Tüm kullanıcılar** listesinde bir kullanıcı seçin. Kullanıcı verilerinin doğru olduğundan emin olun ve ardından **Tamam**'ı seçin.

> Son kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtlamak istiyorsanız, **Microsoft Intune Aracı Ayarları** ilkesinde **Kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtla** seçeneğini etkinleştirin.

## Uzaktan Yardım isteğini yanıtlama
Kullanıcılar yönetilen bilgisayarlara otomatik olarak yüklenen Microsoft Easy Assist aracılığıyla Uzaktan Yardım'ı kullanarak uzaktan yardım isteyebilirler. Bir istekte bulunulduğunda Intune konsolunda bir uyarı görüntülenir.

> Uzaktan Yardım Windows 8 veya üzerini çalıştıran bilgisayarlarda desteklenmez.
>
> Microsoft Easy Assist yüklü olmayan bir bilgisayardan Uzaktan Yardım isteği kabul ederseniz, kullanıcıdan yüklemesi istenir. Yükleme sonrasında bilgisayarın yeniden başlatılması gerekir. Bu yeniden başlatmayı önlemek için Microsoft Easy Assist'i kullanıcılarınızın bilgisayarlarına ön yüklemeyi göz önünde bulundurun.

### Bir Uzaktan Yardım isteğini yönetmek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Uyarılar** &gt; **Uzaktan Yardım**’ı seçin.

2.  İsteğin özellikler sayfasını açmak için **Uyarılar** listesinde bir Uzaktan Yardım isteğini seçin.

3.  Uyarıyı çözmek için seçenekler sunan bir iletişim kutusu açmak için **İsteği onayla ve Uzaktan Yardım'ı başlat**’ı seçin.

4.  Aşağıdakilerden birini yapın:

    -   **İsteği kabul et** - Uzak oturuma katılmak için **Uzaktan Yardım isteğini kabul et**'i seçin.

        Kullanıcı şu iletiyi görür: **İsteğiniz kabul edildi. Sistem yöneticinizle bir programı veya masaüstünüzü paylaşmak için Easy Assist'teki yönergeleri izleyin**.

        > Intune yönetici konsolunu çalıştıran bir Mac bilgisayarda uzaktan yardım isteğini kabul edemezsiniz.

    -   **İsteği reddet** - **Sorun Giderme Bilgilerini Görüntüle** penceresini kapatın ve ardından uyarı özellikleri penceresinde **Bu Uyarıyı Kapat**'ı seçin.

        İstek kapatılır ve kullanıcı isteğin reddedildiğini bildiren bir ileti görür. Kullanıcı yeniden Uzaktan Yardım istemek için yeni bir Uzaktan Yardım isteği göndermelidir. Uzaktan Yardım uyarısını yanlışlıkla kapatırsanız, Uzaktan Yardım isteği gönderen kullanıcıyla iletişime geçin ve kullanıcıdan yeni bir istek göndermesini isteyin.


<!--HONumber=May16_HO2-->


