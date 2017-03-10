---
title: "İş İçin Windows Mağazası uygulamalarını yönetme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: İş İçin Windows Mağazası’ndaki uygulamaları Intune’a eşitlemeyi, sonra da bunları atamayı ve izlemeyi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d02d7c3367e18c96cc1d72de3a3a0ef581ef63ff
ms.lasthandoff: 02/18/2017

---

# <a name="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları Microsoft Intune ile yönetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


[İş İçin Windows Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayla Microsoft Intune arasında bağlantı kurarak, toplu satın alınan uygulamaları Intune portalından yönetebilirsiniz. Örneğin:
* Intune’la mağazadan satın aldığınız uygulamalar listesini eşitleyebilirsiniz.
* Eşitlenen uygulamalar Intune yönetim konsolunda gösterilir ve bunları aynı diğer uygulamalar gibi atayabilirsiniz.
* Kaç tane kullanılabilir lisans olduğunu ve bunlardan kaç tanesinin kullanıldığını Intune yönetim konsolunda izleyebilirsiniz.
* Kullanılabilir lisans sayısı yetersiz olduğunda Intune uygulamaların dağıtılmasını ve yüklenmesini engeller.

## <a name="before-you-start"></a>Başlamadan önce
İş İçin Windows Mağazası’ndan uygulamaları eşitlemeye ve dağıtmaya başlamadan önce aşağıdaki bilgileri gözden geçirin:
* Intune’u kuruluşunuz için mobil cihaz yönetim yetkilisi olarak yapılandırmalısınız.
* İş İçin Windows Mağazası’ndan bir hesap almak isterseniz kaydolmanız gerekir.
* İş İçin Windows Mağazası hesabını Intune’la ilişkilendirdikten sonra, gelecekte farklı bir hesaba geçemezsiniz.
* Mağazadan satın alınan uygulamalar Intune’a el ile eklenemez veya Intune’dan el ile silinemez. Bunlar yalnızca İş İçin Windows Mağazası’yla eşitlenebilir.
* Intune yalnızca İş İçin Windows Mağazası’ndan satın almış olduğunuz çevrimiçi lisanslı uygulamaları eşitler.
* Bu özelliğin kullanılabilmesi için cihazların Active Directory Etki Alanı Hizmetleri’ne veya çalışma alanına katılmış olması gerekir.
* Kaydedilen cihazlar Windows 10’un 1511 sürümünü veya sonraki bir sürümü kullanıyor olmalıdır.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>İş İçin Windows Mağazası hesabınızı Intune’la ilişkilendirme
Intune konsolunda eşitlemeyi etkinleştirmek için, önce mağaza hesabınızı yönetim aracı olarak Intune’u kullanacak şekilde yapılandırmanız gerekir:
1. İş İçin Windows Mağazası’nda oturum açarken, Intune’da oturum açtığınız kiracı hesabını kullandığınızdan emin olun.
2. İş İçin Windows Mağazası’nda, **Ayarlar** > **Yönetim araçları**’nı seçin.
3. Yönetim araçları sayfasında, **Yönetim aracı ekle**’yi ve sonra da **Microsoft Intune**’u seçin.

> [!NOTE]
> İş İçin Windows Mağazası uygulamalarını dağıtmak için birden fazla yönetim aracı kullanmanız durumunda önceden bunların yalnızca birini İş İçin Windows Mağazası ile ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz.

Artık devam edebilir ve Intune konsolunda eşitlemeyi ayarlayabilirsiniz.

## <a name="configure-synchronization"></a>Eşitlemeyi yapılandırma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
1. **Mobil Uygulamalar** dikey penceresinde **Kurulum** > **İş İçin Windows Mağazası**’nı seçin.
2. **Etkinleştir**'e tıklayın.
3. Henüz yapmadıysanız, İş İçin Windows Mağazası’na kaydolma bağlantısına tıklayın ve daha önce ayrıntılarıyla açıklandığı gibi hesabınızı ilişkilendirin.
5. **Dil** açılan listesinde, İş İçin Windows Mağazası’ndan gelen uygulamaların Intune portalında görüntüleneceği dili seçin. Görüntülendikleri dilinden bağımsız olarak, bunlar uygun olduğunda son kullanıcının dilinde yüklenir.
6. Windows Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="synchronize-apps"></a>Uygulamaları eşitleme

1. **Uygulamaları yönet** iş yükünde **Kurulum** > **İş İçin Windows Mağazası**’nı seçin.
2. Windows Mağazası’ndan satın aldığınız uygulamaları Intune’a almak için **Eşitle**’ye tıklayın.

## <a name="assign-apps"></a>Uygulamaları atama

Mağazadan alınan uygulamaları, diğer tüm Intune uygulamalarıyla aynı şekilde atarsınız. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](deploy-apps.md). Bununla birlikte, uygulamaları atama işlemini **Tüm Uygulamalar** sayfası yerine **Lisanslı Uygulamalar** sayfasından yaparsınız.

İş İçin Windows Mağazası uygulamasını atadığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır. Dağıtılan uygulamanın tüm kullanılabilir lisanslarını kullandıysanız, artık başka kopya dağıtamazsınız. Aşağıdaki işlemlerden birini yapmanız gerekir:
* Uygulamayı bazı cihazlardan kaldırın.
* Geçerli dağıtımın kapsamını, yalnızca lisanslarınızın yeterli olduğu kullanıcıları hedefleyecek şekilde daraltın.
* İş İçin Windows Mağazası’ndan uygulamanın daha fazla kopyasını satın alın.

> [!Important]
> Dağıtılan uygulamalar yalnızca cihazı ilk kaydeden kullanıcı tarafından kullanılabilir. Uygulamaya başka hiçbir kullanıcı erişemez.

