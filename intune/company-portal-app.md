---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Intune Şirket Portalı uygulamasına şirkete özgü marka uygulamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aed2bec6e6fea40fdbd78bc487896d167d036f06
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.        

> [!Tip]        
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.       

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, **Mobil uygulamalar** iş yükünde **Kurulum** > **Şirket Portalı Markalaması**’nı seçin ve gerekli ayarları yapılandırın.      

## <a name="company-contact-information-and-privacy-statement"></a>Şirket iletişim bilgileri ve gizlilik bildirimi        
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın **BT’ye Başvur** ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.        


|                   Alan adı                   | Uzunluk üst sınırı |                                                                                                 Daha fazla bilgi                                                                                                 |
|------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <strong>Şirket adı</strong>          |     40     |                                                                            Bu ad Şirket Portalı’nın başlığı olarak gösterilir.                                                                            |
|  <strong>BT departmanı ilgili kişi adı</strong>   |     40     |                                                                         Bu ad <strong>BT’ye Başvur</strong>sayfasında gösterilir.                                                                          |
|  <strong>BT departmanı telefon numarası</strong>   |     20     |                                                                    Bu iletişim numarası <strong>BT'ye Başvur</strong> sayfasında gösterilir.                                                                     |
|  <strong>BT departmanı e-posta adresi</strong>  |     40     |                       Bu iletişim adresi <strong>BT'ye Başvur</strong> sayfasında gösterilir. <strong>alias@domainname.com</strong> biçiminde geçerli bir e-posta adresi girmeniz gerekir.                       |
|    <strong>Ek bilgiler</strong>     |    120     |                                                                                <strong>BT'ye Başvur</strong> sayfasında gösterilir.                                                                                |
| <strong>Şirket gizlilik bildirimi URL'si</strong> |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. <strong><https://www.contoso.com></strong> biçiminde geçerli bir URL girmeniz gerekir. |

## <a name="support-contacts"></a>Destek kişileri     
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.        



|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|        
|-|-|-|     
|**Destek web sitesi URL'si**|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, **https://www.contoso.com** biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|        
|**Destek web sitesi adı**|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında BT web sitesine gidin ifadesi gösterilir.       

## <a name="company-branding-customization"></a>Şirket markasıyla özelleştirme       
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.     



|Alan adı|Daha fazla bilgi|       
|-|-|       
|**Tema rengi**|Şirket Portalı’na uygulamak için bir tema rengi seçin. Renk seçiciden seçim yapabilir veya özel bir onaltılık kod girebilirsiniz.|      
|**Şirket logosunu göster**|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.<br>Ayrıca, girdiğiniz şirket adını karşıya yüklenen logonun yanında görüntüleyebilirsiniz.|      

Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için **Intune Web Portalı'nda ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz.
