---
title: "Uygulamaları gruplara ekleme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune’a uygulama eklediğinizde, bu uygulamayı kullanıcı veya cihaz gruplarına atamak istersiniz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune’a uygulama eklediğinizde, bunu kullanıcılara ve cihazlara vermek istersiniz. Bunu, uygulamayı atayarak yaparsınız.

Uygulamalar, Intune tarafından yönetilip yönetilmediğine bakılmaksızın uygulamalara atanabilir. Uygulamaları kullanıcılara ve cihazlara atamaya yönelik çeşitli seçenekleri anlamanıza yardımcı olması için aşağıdaki tabloyu kullanın:

||||
|-|-|-|-|
|&nbsp;|Intune’a kayıtlı cihazlar|Intune’a kayıtlı olmayan cihazlar|
|Kullanıcılara atama|Evet|Evet|
|Cihazlara atama|Evet|Hayır|
|Sarmalanan uygulamaları veya Intune SDK’sında birleştirilmiş uygulamaları atama (uygulama koruma ilkeleri için)|Evet|Evet|
|Uygulamaları Kullanılabilir olarak atama|Evet|Evet|
|Uygulamalarını Gerekli olarak atama|Evet|Hayır|
|Uygulamaları kaldırma|Evet|Evet|
|Son kullanıcıların Şirket Portalı uygulamasından kullanılabilir uygulamaları yüklemesi|Evet|Hayır|
|Son kullanıcıların web tabanlı Şirket Portalı’ndan kullanılabilir uygulamaları yüklemesi|Evet|Evet|

> [!NOTE]
> Şu anda, iOS ve Android uygulamalarını (hem iş kolu uygulamaları hem de mağazadan satın uygulamalar), Intune’a kaydedilmeyen cihazlara atayabilirsiniz.

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Intune önizleme sürümünde uygulamaları gruplara atama konusundaki değişiklikler

Intune Azure Önizleme'de, artık grupları uygulamalara atamak için Intune yerine Azure Active Directory (Azure AD) güvenlik grupları kullanacaksınız. Bu nedenle, özellikle Intune alt gruplarına uygulama atadığınızda, uygulama atamalarının çalışma şeklinde yapılan bazı değişiklikleri öğrenmeniz gerekir.
Alt gruplar kavramının Azure AD'de mevcut olmaması bu konudaki en önemli husustur. Ancak, bazı gruplar aynı üyeleri içerebilir. Bu durumda, klasik Intune ile Intune Azure önizleme arasındaki davranış farklılık gösterir. Aşağıdaki tablo bunu göstermektedir:

||||||
|-|-|-|-|-|
|**Intune Klasik (kiracı geçişinden önce)**|-|**Intune Azure (Kiracı geçişi tamamlandıktan sonra)**|-|**Daha fazla bilgi**|
|**Üst grubu dağıtma hedefi**|**Alt grubu dağıtma hedefi**|**Önceki üst ve alt grup ortak üyeleri için ortaya çıkan atama hedefi**|**Üst grubun üyeleri için ortaya çıkan atama hedefi eylemi**|-|    
|Kullanılabilir|Gerekli|Gerekli ve Kullanılabilir|Kullanılabilir|Gerekli ve Kullanılabilir, gerekli olarak atanan uygulamaların Şirket Portalı uygulamasında da görülebildiği anlamına gelir.
|Uygulanamaz|Kullanılabilir|Uygulanamaz|Uygulanamaz|Geçici çözüm: 'Uygulanamaz' dağıtım hedefini Intune üst grubundan kaldırın.
|Gerekli|Kullanılabilir|Gerekli ve Kullanılabilir|Gerekli|-|
|Gerekli ve Kullanılabilir<sup>1</sup>|Kullanılabilir|Gerekli ve Kullanılabilir|Gerekli ve Kullanılabilir|-|    
|Gerekli|Uygulanamaz|Gerekli|Gerekli|-|    
|Gerekli ve Kullanılabilir|Uygulanamaz|Gerekli ve Kullanılabilir|Gerekli ve Kullanılabilir|-|    
|Gerekli|Kaldır|Gerekli|Gerekli|-|    
|Gerekli ve Kullanılabilir|Kaldır|Gerekli ve Kullanılabilir|Gerekli ve Kullanılabilir|-|
<sup>1</sup> Yalnızca yönetilen iOS mağazası uygulamaları söz konusu olduğunda, bunları Intune’a ekleyip Gerekli olarak dağıttığınızda, hem Gerekli, hem de Kullanılabilir hedefi ile otomatik olarak oluşturulurlar.

Dağıtım çakışmalarını önlemek için aşağıdaki eylemleri gerçekleştirebilirsiniz:

1.    İlgili Intune üst ve alt gruplarına daha önce uygulamalar dağıttıysanız, kiracı geçişiniz başlamadan önce bu dağıtımları kaldırmayı düşünün.
2.    Alt grupları üst gruplardan kaldırın ve eski alt grup üyelerini içeren yeni bir grup oluşturun. Daha sonra bu gruba yeni bir uygulama dağıtımı oluşturabilirsiniz.
Not: Önceki üst grup "Tüm Kullanıcılar" ise, alt grup üyelerini içermeyen yeni dinamik bir grup oluşturmanız gerekir.
Kullanıcı ve cihaz grupları için gruplarda yapacağınız tüm değişiklikleri [Azure Portalı](https://portal.azure.com/)’nda yapmanız gerekir. [Klasik Azure Portalı](https://manage.windowsazure.com/) yalnızca kullanıcı gruplarınızda değişiklik yapmanıza izin verir.


## <a name="how-to-assign-an-app"></a>Uygulama atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
1. **Uygulamaları Yönet** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde, atamak istediğiniz uygulamaya tıklayın.
3. <*uygulama adı*> - **Genel Bakış** dikey penceresinde **Yönet** > **Atamalar**’ı seçin.
4. **Grup Seç** öğesini seçin, ardından **Grupları seçin** dikey penceresinde uygulamayı atamak istediğiniz Azure AD gruplarını seçin.
5. Seçtiğiniz her uygulama için, **atama türü** olarak aşağıdakilerden birini seçin:
    - **Kullanılabilir** Kullanıcılar Şirket Portalı’ndan veya web sitesinden uygulamayı yükler.
    - **Uygulanamaz** - Uygulama yüklenmez veya Şirket Portalı’nda gösterilmez.
    - **Gerekli** - Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
    - **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. Yardım için yukarıdaki tabloya bakın.
6. İşiniz bittikten sonra **Kaydet**’i seçin.

Artık uygulama seçtiğiniz gruba atanır.

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](monitor-apps.md).

