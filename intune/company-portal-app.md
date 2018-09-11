---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü marka uygulamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bd388131445715a4037cc0480c194d338212dbb0
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329982"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.        

> [!Tip]        
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.       

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, **İstemci uygulamaları** iş yükünde **Kurulum** > **Şirket Portalı Markalaması**’nı seçin ve gerekli ayarları yapılandırın.  

> [!Note]       
> Kullanıcı bir sorun hakkında yardım almak için iş akışı başlattığında Windows 10 için Şirket Portalı uygulaması artık uygulama günlüklerini doğrudan Microsoft’a gönderecek. Böylece Microsoft’a bildirilen sorunların giderilmesi ve çözülmesi daha kolay olacak.  

## <a name="company-information-and-privacy-statement"></a>Şirket bilgileri ve gizlilik bildirimi        
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

Yıldız işareti (*) ile işaretlenmiş alanlar zorunludur.       


| Alan adı | Uzunluk üst sınırı | Daha fazla bilgi |
|---|---|---|
|**Şirket adı**| 40 | Bu ad Şirket Portalı'nın başlığı olarak görüntülenir ve Intune kullanıcı deneyiminin her yerinde metin olarak gösterilir. |
| **Gizlilik bildirimi URL'si** |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz.  `<https://www.contoso.com>` biçiminde geçerli bir URL girmeniz gerekir. |

## <a name="support-information"></a>Destek bilgileri      
Çalışanınıza Intune'la ilgili sorularında bir başvuru noktası sağlamak için şirketinizin destek bilgilerini girin.       

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|---|---|---|
|**Kişi adı** | 40 | Bu ad **BT’ye Başvur**sayfasında gösterilir. |
|**Telefon numarası** | 20 | Çalışanların destek almak üzere size başvurabilmesini sağlamak için bu iletişim numarası **BT'ye Başvur** sayfasında görüntülenir. |
|**E-posta adresi**| 40 | Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. `alias@domainname.com` biçiminde geçerli bir e-posta adresi girmeniz gerekir. |
|**Web sitesinin adı**| 40 | Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında BT web sitesine gidin ifadesi gösterilir. |
|**Web sitesi URL'si**| 150 | Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, `https://www.contoso.com` biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez. |
| **Ek bilgiler**| 120 | **BT'ye Başvur** sayfasında gösterilir. |


## <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme       
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.     

### <a name="theme-color"></a>Tema rengi
Şirket Portalı’na bir tema rengi uygulayın. Standart renklerden birini seçin veya özel renk için alt basamaklı onaltılık kodu girin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Renk türü**| Şirket Portalı’na uygulamak için bir tema rengi seçin. Standart renk seçebilir veya belirli bir onaltılık kodu girebilirsiniz. |
|**Renk seçin** veya **Onaltılık renk kodu girin**| Şirket Portalı’na uygulamak için bir tema rengi seçin. Standart renk seçebilir veya belirli bir onaltılık kodu girebilirsiniz. Bu seçenekler, seçtiğiniz **Renk türü**'ne göre sağlanır.  |

### <a name="company-logo"></a>Şirket logosu
Intune kullanıcı deneyiminin her yerinde görünür olmasını sağlamak için şirket logonuzu karşıya yükleyin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Şirket logosunu göster**|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. |
|**Tema rengi arka planlarında kullanmak üzere karşıya logo yükle**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. Logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 400 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır. |
|**Açık renk arka planlarda kullanmak üzere karşıya logo yükle**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. Logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 400 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır. |
|**Logonun yanında şirket adını göster**| Girdiğiniz şirket adını karşıya yüklenen logonun yanında görüntülemek için bu seçeneği kullanın. |

Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için, dikey pencerenin üst kısmındaki **Intune Web Portalı'nda ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz.
