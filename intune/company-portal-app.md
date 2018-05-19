---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü marka uygulamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5d7a825f70694e9888cf80d96eff12b9169e9ae
ms.sourcegitcommit: b0ad42fe5b5627e5555b2f9e5bb81bb44dbff078
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/09/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.        

> [!Tip]        
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.       

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, **Mobil uygulamalar** iş yükünde **Kurulum** > **Şirket Portalı Markalaması**’nı seçin ve gerekli ayarları yapılandırın.  

> [!Note]       
> Kullanıcı bir sorun hakkında yardım almak için iş akışı başlattığında Windows 10 için Şirket Portalı uygulaması artık uygulama günlüklerini doğrudan Microsoft’a gönderecek. Böylece Microsoft’a bildirilen sorunların giderilmesi ve çözülmesi daha kolay olacak.  

## <a name="company-contact-information-and-privacy-statement"></a>Şirket iletişim bilgileri ve gizlilik bildirimi        
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın **BT’ye Başvur** ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

Yıldız işareti (*) ile işaretlenmiş alanlar zorunludur.       


| Alan adı | Uzunluk üst sınırı | Daha fazla bilgi |
|---|---|---|
|**Şirket adı**| 40 | Bu ad Şirket Portalı’nın başlığı olarak gösterilir. |
|**BT departmanı ilgili kişi adı** | 40 | Bu ad **BT’ye Başvur**sayfasında gösterilir. |
|**BT departmanı telefon numarası** | 20 | Bu iletişim numarası **BT'ye Başvur** sayfasında gösterilir. |
|**BT departmanı e-posta adresi**| 40 | Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. `alias@domainname.com` biçiminde geçerli bir e-posta adresi girmeniz gerekir. |
| **Ek bilgiler**|    120     | **BT'ye Başvur** sayfasında gösterilir. |
| **Şirket gizlilik bildirimi URL'si** |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. `<https://www.contoso.com>` biçiminde geçerli bir URL girmeniz gerekir. |

## <a name="support-contacts"></a>Destek kişileri     
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.        

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|---|---|---|
|**Destek web sitesi URL'si**|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, **https://www.contoso.com** biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|
|**Destek web sitesi adı**|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında BT web sitesine gidin ifadesi gösterilir.

## <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme       
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.     

|Alan adı|Daha fazla bilgi|
|---|---|
|**Tema rengi**|Şirket Portalı’na uygulamak için bir tema rengi seçin. Renk seçiciden seçim yapabilir veya özel bir onaltılık kod girebilirsiniz.|
|**Şirket logosunu göster**|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.<br>Ayrıca, girdiğiniz şirket adını karşıya yüklenen logonun yanında görüntüleyebilirsiniz.|

Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için **Intune Web Portalı'nda ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz.
