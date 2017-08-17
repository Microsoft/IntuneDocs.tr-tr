---
title: "İş İçin Microsoft Mağazası’ndan uygulamaları yönetme"
titleSuffix: Intune on Azure
description: "İş İçin Microsoft Mağazası’ndaki uygulamaları Intune’a eşitlemeyi, sonra da bunları atamayı ve izlemeyi öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f5f1b49d0785682f72d208287098466934ff0e1
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Microsoft Intune ile İş İçin Microsoft Mağazası'ndan satın aldığınız uygulamaları yönetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


[İş İçin Microsoft Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayla Microsoft Intune arasında bağlantı kurarak, toplu uygulama alışverişlerini Intune portalından yönetebilirsiniz. Örneğin:
* Intune’la mağazadan satın aldığınız uygulamalar listesini eşitleyebilirsiniz.
* Eşitlenen uygulamalar, Intune yönetim konsolunda gösterilir; bu uygulamaları herhangi bir uygulama gibi atayabilirsiniz.
* Kaç tane kullanılabilir lisans olduğunu ve bunlardan kaç tanesinin kullanıldığını Intune yönetim konsolunda izleyebilirsiniz.
* Kullanılabilir lisans sayısı yetersiz olduğunda Intune uygulamaların atanmasını ve yüklenmesini engeller.

## <a name="before-you-start"></a>Başlamadan önce

İş İçin Microsoft Mağazası’ndan uygulamaları eşitlemeye ve atamaya başlamadan önce aşağıdaki bilgileri gözden geçirin:

- Intune'u kuruluşunuz için mobil cihaz yönetim yetkilisi olarak yapılandırın.
- İş İçin Microsoft Mağazası’ndan bir hesap almak isterseniz kaydolmanız gerekir.
- İş İçin Windows Mağazası hesabını Intune’la ilişkilendirdikten sonra, gelecekte farklı bir hesaba geçemezsiniz.
- Mağazadan satın alınan uygulamalar Intune’a el ile eklenemez veya Intune’dan el ile silinemez. Bunlar yalnızca İş İçin Microsoft Mağazası’yla eşitlenebilir.
- Intune, İş İçin Microsoft Mağazası'ndan satın aldığınız hem çevrimiçi hem de çevrimdışı lisanslı uygulamaları eşitler.
- Yalnızca ücretsiz çevrimdışı uygulamalar Intune ile eşitlenebilir.
- Bu özelliğin kullanılabilmesi için cihazların Active Directory Etki Alanı Hizmetleri'ne veya çalışma alanına katılmış olması gerekir.
- Kaydedilen cihazlar Windows 10’un 1511 sürümünü veya sonraki bir sürümü kullanıyor olmalıdır.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>İş İçin Microsoft Mağazası hesabınızı Intune’la ilişkilendirme
Intune konsolunda eşitlemeyi etkinleştirmek için, önce mağaza hesabınızı yönetim aracı olarak Intune’u kullanacak şekilde yapılandırmanız gerekir:
1. İş İçin Windows Mağazası’nda oturum açarken, Intune’da oturum açtığınız kiracı hesabını kullandığınızdan emin olun.
2. İş İçin Windows Mağazası’nda, **Ayarlar** > **Yönetim araçları**’nı seçin.
3. Yönetim araçları sayfasında, **Yönetim aracı ekle**’yi ve sonra da **Microsoft Intune**’u seçin.

> [!NOTE]
> Daha önce İş İçin Microsoft Mağazası ile uygulama atamak üzere yalnızca bir yönetim aracı ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz.

Artık devam edebilir ve Intune konsolunda eşitlemeyi ayarlayabilirsiniz.

## <a name="configure-synchronization"></a>Eşitlemeyi yapılandırma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
1. **Mobil Uygulamalar** dikey penceresinde **Kurulum** > **İş İçin Microsoft Mağazası**’nı seçin.
2. **Etkinleştir**'e tıklayın.
3. Henüz yapmadıysanız İş İçin Microsoft Mağazası'na kaydolma bağlantısına tıklayın ve daha önce ayrıntı olarak açıklandığı gibi hesabınızı ilişkilendirin.
5. **Dil** açılan listesinden İş İçin Microsoft Mağazası'ndan alınan uygulamaların Intune portalında görüntülendiği dili seçin. Uygulamalar, görüntülendikleri dilden bağımsız olarak, mevcut olması durumunda son kullanıcının dilinde yüklenir.
6. Microsoft Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="synchronize-apps"></a>Uygulamaları eşitleme

1. **Mobil uygulamalar** iş yükünde **Kurulum** > **İş İçin Microsoft Mağazası**’nı seçin.
2. Microsoft Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="assign-apps"></a>Uygulamaları atama

Mağazadan alınan uygulamaları, diğer tüm Intune uygulamalarıyla aynı şekilde atarsınız. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md). Bununla birlikte, uygulamaları atama işlemini **Tüm Uygulamalar** sayfası yerine **Lisanslı Uygulamalar** sayfasından yaparsınız.

Çevrimdışı uygulamalar; kullanıcı gruplarını, cihaz gruplarını veya kullanıcı ve cihazları olan grupları hedefleyebilir.
Çevrimdışı uygulamalar, bir cihazdaki belirli bir kullanıcı veya bir cihazdaki tüm kullanıcılar için yüklenebilir. 


İş İçin Microsoft Mağazası uygulamasını atadığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır. Atanmış bir uygulamanın tüm lisanslarını kullanırsanız başka bir kopya atayamazsınız. Aşağıdaki eylemlerden birini uygulayın:
* Uygulamayı bazı cihazlardan kaldırın.
* Geçerli atamanın kapsamını, yalnızca yeteri kadar lisansa sahip olduğunuz kullanıcıları hedefleyerek daraltın.
* İş İçin Microsoft Mağazası’ndan uygulamanın daha fazla kopyasını satın alın.


