---
title: "Şirket Portalı uygulamasını yapılandırma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune Şirket Portalı uygulamasına şirkete özgü markayı uygulamayı öğrenin. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: f27eacc8a8282c9216f8983db32dc5e4e8bc7006

---

# <a name="how-to-configure-the-company-portal-app"></a>Şirket Portalı uygulamasını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.

> [!Tip]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, **Uygulamaları yönet** iş yükünde **Kurulum** > **Şirket Portalı Markalaması**’nı seçin ve gerekli ayarları yapılandırın.

## <a name="company-contact-information-and-privacy-statement"></a>Şirket iletişim bilgileri ve gizlilik bildirimi
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın **BT’ye Başvur** ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.


|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|-|-|-|
|**Şirket adı**|40|Bu ad Şirket Portalı’nın başlığı olarak gösterilir.|
|**BT departmanı ilgili kişi adı**|40|Bu ad **BT’ye Başvur**sayfasında gösterilir.|
|**BT departmanı telefon numarası**|20|Bu iletişim numarası **BT'ye Başvur** sayfasında gösterilir.|
|BT departmanı e-posta adresi|40|Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. **alias@domainname.com** biçiminde geçerli bir e-posta adresi girmeniz gerekir.|
|**Ek bilgiler**|120|**BT'ye Başvur** sayfasında gösterilir.|
|**Şirket gizlilik bildirimi URL'si**|79|Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. **Https://www.contoso.com** biçiminde geçerli bir URL girmelisiniz.|

## <a name="support-contacts"></a>Destek kişileri
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.



|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|-|-|-|
|**Destek web sitesi URL'si**|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. **URL, https://www.contoso.com biçiminde olmalıdır**. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|
|**Destek web sitesi adı**|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında BT web sitesine gidin ifadesi gösterilir.

## <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.



|Alan adı|Daha fazla bilgi|
|-|-|
|**Tema rengi**|Şirket Portalı’na uygulamak için bir tema rengi seçin.|
|**Şirket logosunu göster**|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.<br>Ayrıca, girdiğiniz şirket adını karşıya yüklenen logonun yanında görüntüleyebilirsiniz.|

Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için **Intune Web Portalı'nda ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz.



<!--HONumber=Feb17_HO1-->

