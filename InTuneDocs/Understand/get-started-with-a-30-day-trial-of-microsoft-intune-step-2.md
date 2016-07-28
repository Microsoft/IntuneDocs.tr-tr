---
title: "30 günlük Intune değerlendirmenize kullanıcıları ekleme | Microsoft Intune"
description: "Intune’un ücretsiz, 30 günlük değerlendirmesine kaydolduğunuzda, kullanıcılar tek tek veya toplu olarak nasıl eklenir"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: 5a5ebe474580b98a3696bbd970c889837283b6f0


---

# 30 günlük Microsoft Intune değerlendirmenize kullanıcılar ekleyin
Artık hesabınızı ayarladığınıza göre **Yeni kullanıcılar** sihirbazını kullanarak Intune hizmetine tek tek kullanıcı hesaplarını veya **Toplu olarak kullanıcı ekleme** sihirbazıyla toplu olarak kullanıcıları ekleyebilirsiniz (bu bölümdeki yönergelere bakın).  Başlamadan önce, Intune’un yönetici hesaplarını nasıl işlediğini anlamanız önemlidir.

Bir kiracı yöneticisi, Microsoft Intune **Kullanıcılar Grubu**’na kullanıcı eklemek için Office 365 yönetim merkezini kullanır. **Kullanıcılar Grubu** ’na kullanıcı eklemek hem Intune abonelik lisanslarını kullanıcılara atar hem de bu kullanıcıların Microsoft Intune yönetim konsolunda görünmesini sağlar.

Intune yönetici hesapları, normal kullanıcı hesaplarından farklı olarak, Office 365 yönetim merkezinde oluşturulmaz. Bunun yerine, **İdari Yönetim** altındaki **Yönetim** çalışma alanını kullanarak kullanıcılara salt okunur veya tam erişime sahip yönetici hakları atanır. Salt okunur erişim atanan hizmet yöneticileri Intune ayarlarını değiştiremez, ancak verileri görüntüleyebilir ve raporları çalıştırabilir. Tam erişimi olan hizmet yöneticileri mevcut tüm yönetim haklarına sahiptir.

Intune yönetim konsolunu kullanarak kiracı yöneticisi bilgilerini görüntüleyebilirsiniz, ancak buradan kiracı yöneticisi oluşturamazsınız. Varsayılan olarak, abonelik sahibi Microsoft Intune hizmetiniz için bir kiracı yöneticisi olur ve hem Office 365 yönetim merkezinde hem de Intune yönetim konsolunda tam erişime sahip olur. Görevler için temsilci seçimine yardımcı olması ve parolanızı unuttuğunuzda Intune hizmet yöneticisi hesabınıza tekrar erişebilmenizin sağlanması için Office 365 yönetim merkezini kullanarak bir en az bir ek kiracı yöneticisi hesabı daha oluşturmanızı öneririz.

## Bireysel kullanıcı hesapları ekleme
Değerlendirme kiracınızda ek kullanıcı hesapları oluşturmak için aşağıdaki adımları kullanın. Eklediğiniz her bir kullanıcı hesabının, Intune ücretsiz değerlendirmeniz kapsamında aldığınız 100 lisanstan düşüldüğünü unutmayın.

1.  [Office 365 yönetim merkezinde](http://go.microsoft.com/fwlink/?LinkID=787455), **Kullanıcı Ekle** &gt; **Yeni**&gt; **Kullanıcı**’yı seçerek **Yeni kullanıcılar** sihirbazını başlatın.

2.  **Ayrıntılar** sayfasında, gerekli alanları doldurun.

3.  **Ayarlar** sayfasında, kullanıcı için **konum** 'u ayarlayın.

4.  **Grup** sayfasında, varsayılanı kabul etmek için **İleri**'ye tıklayın ve kullanıcı hesabına bir Intune lisansı atayın.

5.  **E-posta** sayfasında, hesap için kullanıcı adını ve geçici parola bildirimi alacak en fazla beş e-posta adresini belirtin. Birden fazla e-posta adresini noktalı virgülle (;) ayırın. Bu işlemleri tamamladığınızda, kullanıcıyı aboneliğinize eklemek için **Oluştur**’u seçin.

6.  **Sonuçlar** sayfasında, yeni hesap adını ve geçici parolasını görüntüleyebilirsiniz. Intune geçici parolayı otomatik olarak oluşturur.

7.  Yeni kullanıcı, Office 365 yönetim merkezinde göründüğünde, yeni kullanıcının başarılı şekilde oluşturulduğunu doğrulayın:

    1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** &gt; **Şirket Portalı**’nı seçin ve ardından ekranın alt kısmına kaydırın. **Intune Şirket Portalı** altında gösterilen URL'yi kopyalayın.

    2.  “Gizlilik modunda” yeni bir tarayıcı penceresi açın (Internet Explorer'da **Araçlar** &gt; **InPrivate Gözatma**’yı seçin) veya farklı bir cihaz üzerinde yeni bir tarayıcı penceresi açın ve ardından önceki adımda kopyaladığınız URL'ye gidin. Kullanıcılar ilk kez oturum açtığında, hesap için yeni bir parola sağlamaları gerekir.

## Toplu olarak kullanıcı ekleme
Intune’a toplu olarak kullanıcı eklemek için, **Toplu olarak kullanıcı ekleme** sihirbazını kullanarak, kullanıcı verilerinizi içeren bir virgülle ayrılmış değerler (CSV) dosyasını karşıya yükleyin. Sihirbazdaki bağlantıları kullanarak boş bir şablon ve örnek CSV dosyası indirebilirsiniz. CSV dosyanızın ilk satırı, her bir kullanıcı veri sütunu etiketini doğru sırayla içermelidir. Ardından, CSV dosyasındaki her bir kullanıcı için **kullanıcı adı** (örneğin **bob@contoso.com**) ve bir **görünen ad** (örneğin **Bob Kelly**) eklemeniz gerekir.

1.  [Office 365 yönetim merkezinde](http://go.microsoft.com/fwlink/?LinkID=787455), **Kullanıcılar** &gt; **Yeni**’yi seçin.

2.  Toplu kullanıcı ekleme sihirbazını başlatmak için **Toplu ekle**'yi seçin.

3.  **Dosya seçin** sayfasında, mevcut bir CSV dosyasını belirtmek ve bilgisayarınızdan yüklemek için **Gözat**’ı seçin. Ayrıca, sihirbazdaki bağlantıları kullanarak örnek bir CSV dosyasını veya boş şablonu indirebilirsiniz.

4.  **Doğrulama** sayfasında, sonuçları inceleyin ve daha fazla ayrıntı için **Görüntüle**’yi seçin.

5.  **Ayarlar** sayfasında, oturum açma durumunun **İzin veriliyor** olduğundan emin olun ve **konum** ayarlayın. Bu ayarlar CSV dosyası tarafından eklenen tüm kullanıcı hesaplarına uygulanır.

6.  **Grup** sayfasında, varsayılanı kabul etmek ve CSV dosyasıyla eklenen tüm kullanıcı hesaplarına Intune lisansı atamak için **İleri**'yi seçin. Varsayılan olarak, onay kutusu işaretlidir ve her hesaba bir Intune lisansı atanır.

7.  **E-posta** sayfasında, Intune tarafından oluşturulan her hesap için kullanıcı adları ve geçici parolalar için bildirim alacak olan en fazla beş e-posta adresi belirtin. Birden fazla e-posta adresini noktalı virgülle (;) ayırın. Kullanıcıları aboneliğinize eklemek için **Oluştur**’u seçin.

8.  **Sonuçlar** sayfasında, her kullanıcı hesabı için kullanıcı adları ve geçici parolaları görüntüleyebilirsiniz.

İçeri aktararak eklediğiniz tüm kullanıcı hesapları artık Office 365 yönetim merkezinin **Kullanıcılar** düğümünde görünür. Yeni kullanıcılar ilk kez oturum açtığında, kullanıcı hesapları için yeni bir parola belirtmelidir.

### Sonraki adımlar
Tebrikler! *Microsoft Intune değerlendirme* gözden geçirmesinin 2. adımını tamamladınız.

>[!div class="step-by-step"]

>[&larr; **Değerlendirme için kaydolun**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Gruplar oluşturun** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO3-->


