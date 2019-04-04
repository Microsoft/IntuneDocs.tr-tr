---
title: İş İçin Microsoft Mağazası’ndan uygulamaları yönetme
titleSuffix: Microsoft Intune
description: İş İçin Microsoft Store’daki uygulamaları Intune’a eşitlemeyi, sonra da bu uygulamaları atamayı ve izlemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 500fef4cf0edf7739bb1a4f0785f590e328dbbed
ms.sourcegitcommit: 219bbbfb44eba70ac2b751970d8b4b778cd28416
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920247"
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Microsoft Intune ile İş İçin Microsoft Mağazası'ndan satın aldığınız uygulamaları yönetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[İş İçin Microsoft Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayı Microsoft Intune’a bağlayarak toplu satın alınan uygulamaları Azure portalından yönetebilirsiniz. Örneğin:
* Intune’la mağazadan satın aldığınız uygulamalar listesini eşitleyebilirsiniz.
* Eşitlenen uygulamalar, Intune yönetim konsolunda gösterilir; bu uygulamaları herhangi bir uygulama gibi atayabilirsiniz.
* Kaç tane kullanılabilir lisans olduğunu ve bunlardan kaç tanesinin kullanıldığını Intune yönetim konsolunda izleyebilirsiniz.
* Kullanılabilir lisans sayısı yetersiz olduğunda Intune uygulamaların atanmasını ve yüklenmesini engeller.
* İş İçin Microsoft Store ile yönetilen uygulamalar, kullanıcı işletmeden ayrıldığında veya yönetici kullanıcıyı ve kullanıcı cihazlarını kaldırdığında, lisansları otomatik olarak iptal eder.

## <a name="before-you-start"></a>Başlamadan önce

İş İçin Microsoft Mağazası’ndan uygulamaları eşitlemeye ve atamaya başlamadan önce aşağıdaki bilgileri gözden geçirin:

- Intune'u kuruluşunuz için mobil cihaz yönetim yetkilisi olarak yapılandırın.
- İş İçin Microsoft Mağazası’ndan bir hesap almak isterseniz kaydolmanız gerekir.
- İş İçin Microsoft Store hesabını Intune’la ilişkilendirdikten sonra, gelecekte farklı bir hesaba geçemezsiniz.
- Mağazadan satın alınan uygulamalar Intune’a el ile eklenemez veya Intune’dan el ile silinemez. Bunlar yalnızca İş İçin Microsoft Mağazası’yla eşitlenebilir.
- İş İçin Microsoft Store'dan satın aldığınız hem çevrimiçi hem de çevrimdışı lisanslı uygulamalar Intune portalına eşitlenir. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. 
- Çevrimiçi uygulama yüklemeleri mağaza tarafından yönetilir.
- Ücretsiz çevrimdışı uygulamalar da Intune ile eşitlenebilir. Bu uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.
- Bu özelliğin kullanılabilmesi için cihazların Active Directory Etki Alanı Hizmetleri'ne veya çalışma alanına katılmış olması gerekir.
- Kaydedilen cihazlar Windows 10’un 1511 sürümünü veya sonraki bir sürümü kullanıyor olmalıdır.

Ayrıca, İş İçin Microsoft Store'dan eşitlenen ilgili kümeler ve Çevrimdışı Lisanslı uygulamalar artık kullanıcı arabiriminde tek bir uygulama girişinde birleştirilecektir. Tek paketlerden alınan tüm dağıtım ayrıntıları, tek girişe geçirilecektir. Azure portalında ilgili kümeleri görüntülemek için **İstemci uygulamaları** dikey penceresinden **Uygulama lisansları**’nı seçin.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>İş İçin Microsoft Mağazası hesabınızı Intune’la ilişkilendirme
Intune konsolunda eşitlemeyi etkinleştirmek için, önce mağaza hesabınızı yönetim aracı olarak Intune’u kullanacak şekilde yapılandırmanız gerekir:
1. İçine oturum olun [iş için Microsoft Store](https://www.microsoft.com/business-store) Intune'a oturum açmak için kullandığınız Kiracı hesabının aynısını kullandığınızdan.
2. İş Store içinde seçin **Yönet** sekmesinde **ayarları**ve **Dağıt** sekmesi.
3. Özellikle yoksa **Intune** kullanılabilir bir mobil cihaz yönetim aracı olarak seçin **Yönetim Aracı Ekle** eklemek için **Intune**. Öğeniz yoksa **Intune** , mobil cihaz yönetim aracı olarak etkinleştirilmiş tıklayın **etkinleştirme** yanındaki **Intune**. Etkinleştirilmesi gerektiğini unutmayın **Intune** yerine **Microsoft Intune kaydı**.

> [!NOTE]
> Daha önce İş İçin Microsoft Mağazası ile uygulama atamak üzere yalnızca bir yönetim aracı ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz. 

Artık devam edebilir ve Intune konsolunda eşitlemeyi ayarlayabilirsiniz.

## <a name="configure-synchronization"></a>Eşitlemeyi yapılandırma

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
1. **İstemci uygulamaları** bölmesinde **Kurulum** > **İş İçin Microsoft Store**’u seçin.
2. **Etkinleştir**'e tıklayın.
3. Henüz yapmadıysanız İş İçin Microsoft Mağazası'na kaydolma bağlantısına tıklayın ve daha önce ayrıntı olarak açıklandığı gibi hesabınızı ilişkilendirin.
5. **Dil** açılan listesinden İş için Microsoft Store’dan alınan uygulamaların Azure portalında görüntülendiği dili seçin. Uygulamalar, görüntülendikleri dilden bağımsız olarak, mevcut olması durumunda son kullanıcının dilinde yüklenir.
6. Microsoft Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="synchronize-apps"></a>Uygulamaları eşitleme

1. **İstemci uygulamaları** iş yükünde **Kurulum** > **İş İçin Microsoft Store**’u seçin.
2. Microsoft Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="assign-apps"></a>Uygulamaları atama

Mağazadan alınan uygulamaları, diğer tüm Intune uygulamalarıyla aynı şekilde atarsınız. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md). 

Çevrimdışı uygulamalar; kullanıcı gruplarını, cihaz gruplarını veya kullanıcı ve cihazları olan grupları hedefleyebilir.
Çevrimdışı uygulamalar, bir cihazdaki belirli bir kullanıcı veya bir cihazdaki tüm kullanıcılar için yüklenebilir. 


İş İçin Microsoft Mağazası uygulamasını atadığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır. Atanmış bir uygulamanın tüm lisanslarını kullanırsanız başka bir kopya atayamazsınız. Aşağıdaki eylemlerden birini uygulayın:
* Uygulamayı bazı cihazlardan kaldırın.
* Geçerli atamanın kapsamını, yalnızca yeteri kadar lisansa sahip olduğunuz kullanıcıları hedefleyerek daraltın.
* İş İçin Microsoft Mağazası’ndan uygulamanın daha fazla kopyasını satın alın.

## <a name="remove-apps"></a>Uygulamaları kaldırma

İş İçin Microsoft Store’dan eşitlenmiş bir uygulamayı kaldırmak için İş İçin Microsoft Store’da oturum açıp uygulamayı iade etmelisiniz. Uygulama boş olup olmadığını işlemi aynıdır. Ücretsiz bir uygulama için deponun 0 ABD Doları para iadesi. Aşağıdaki örnek, ücretsiz bir uygulama için para iadesi gösterir. 

![Uygulama kaldırma ayrıntılarının ekran görüntüsü](./media/microsoft-store-for-business-01.png)

> [!NOTE]
> Özel depoda bir uygulamanızın görünürlüğünü kaldırma, Intune uygulama eşitlenmesini tutulmaz. Uygulama uygulamasını tamamen kaldırmak için para iadesi gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- [Toplu satın alınan uygulama ve kitapları Microsoft Intune ile yönetme](vpp-apps.md)
