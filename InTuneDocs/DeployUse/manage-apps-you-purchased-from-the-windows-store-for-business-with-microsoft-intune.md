---
title: "İş İçin Windows Mağazası uygulamalarını yönetme | Microsoft Intune"
description: "Toplu satın alınan uygulamaları Intune konsolundan yönetmek ve dağıtmak istiyorsanız, Microsoft Intune’u İş İçin Windows Mağazası’na bağlayın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d40ec3b5b7c5c4ee2cfd48a95ada0dadcaa80be4
ms.openlocfilehash: 077029a962797a18fab27c3f1f5340eae6edfe04


---

# Microsoft Intune ile İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme
[İş İçin Windows Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayla Microsoft Intune arasında bağlantı kurarak, toplu uygulama alışverişlerini Intune konsolundan yönetebilirsiniz. Örneğin:
* Intune’la mağazadan satın aldığınız uygulamalar listesini eşitleyebilirsiniz.
* Eşitlenen uygulamalar Intune yönetim konsolunda gösterilir ve bunları aynı diğer uygulamalar gibi dağıtabilirsiniz.
* Kaç tane kullanılabilir lisans olduğunu ve bunlardan kaç tanesinin kullanıldığını Intune yönetim konsolunda izleyebilirsiniz.
* Kullanılabilir lisans sayısı yetersiz olduğunda Intune uygulamaların dağıtılmasını ve yüklenmesini engeller.

## Başlamadan önce
İş İçin Windows Mağazası’ndan uygulamaları eşitlemeye ve dağıtmaya başlamadan önce aşağıdaki bilgileri gözden geçirin:
* Intune’u kuruluşunuz için mobil cihaz yönetim yetkilisi olarak yapılandırmalısınız. Daha fazla bilgi için bkz. [Microsoft Intune’da cihazları kaydetmeye hazırlanın](get-ready-to-enroll-devices-in-microsoft-intune.md).
* İş İçin Windows Mağazası’ndan bir hesap almak isterseniz kaydolmanız gerekir.
* İş İçin Windows Mağazası hesabını Intune’la ilişkilendirdikten sonra, gelecekte farklı bir hesaba geçemezsiniz.
* Mağazadan satın alınan uygulamalar Intune’a el ile eklenemez veya Intune’dan el ile silinemez. Bunlar yalnızca İş İçin Windows Mağazası’yla eşitlenebilir.
* Intune yalnızca İş İçin Windows Mağazası’ndan satın almış olduğunuz çevrimiçi lisanslı uygulamaları eşitler.
* Bu özelliğin kullanılabilmesi için cihazların Active Directory Etki Alanı Hizmetleri’ne veya çalışma alanına katılmış olması gerekir.
* Kaydedilen cihazlar Windows 10’un 1511 sürümünü kullanıyor olmalıdır.

## İş İçin Windows Mağazası hesabınızı Intune’la ilişkilendirme
Intune konsolunda eşitlemeyi etkinleştirmek için, önce mağaza hesabınızı yönetim aracı olarak Intune’u kullanacak şekilde yapılandırmanız gerekir:
1. İş İçin Windows Mağazası’nda oturum açarken, Intune’da oturum açtığınız kiracı hesabını kullandığınızdan emin olun.
2. İş İçin Windows Mağazası’nda, **Ayarlar** > **Yönetim araçları**’nı seçin.
3. Yönetim araçları sayfasında, **Yönetim aracı ekle**’yi ve sonra da **Microsoft Intune**’u seçin.

Artık devam edebilir ve Intune konsolunda eşitlemeyi ayarlayabilirsiniz.

## Eşitlemeyi yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
2. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve **İş İçin Mağaza**’yı seçin.
3. **İş İçin Windows Mağazası** sayfasında aşağıdakileri yapın:
 * Henüz yapmadıysanız, İş İçin Windows Mağazası’na kaydolma bağlantısına tıklayın.
 * Kaydolduktan sonra, **Eşitleme Yapılandır**’ı seçin.
4. **İş İçin Windows Mağazası uygulamasının eşitlenmesini yapılandır** iletişim kutusunda **İş İçin Windows Mağazası eşitlemesini etkinleştirin** öğesini seçin.
5. **Dil** açılan listesinde, İş İçin Windows Mağazası’ndan gelen uygulamaların Intune konsolunda görüntüleneceği dili seçin. Görüntülendikleri dilinden bağımsız olarak, bunlar uygun olduğunda son kullanıcının dilinde yüklenir.
6. **Tamam**'ı tıklatın.

## Uygulamaları eşitleme

1. Mağazadan satın aldığınız uygulamaları Intune’la eşitlemek için **İş İçin Windows Mağazası** sayfasında **Şimdi eşitle**’yi seçin.
2. Kullanılabilir uygulamaları görmek ve satın aldığınız uygulamaların düzgün bir şekilde içeri aktarıldığını doğrulamak için, **Uygulamalar** çalışma alanında **Yönetilen Yazılım** > **Lisanslı Yazılım**’ı seçin. Bu düğümdeki uygulamalar, sahip olduğunuz toplam lisans sayısı ve kullanılabilir lisanslarınızın sayısıyla birlikte gösterilir.

## Uygulama dağıtma

Mağazadan alınan uygulamaları, diğer tüm Intune uygulamalarıyla aynı şekilde dağıtırsınız. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md).
İş İçin Windows Mağazası uygulamasını dağıttığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır. Dağıtılan uygulamanın tüm kullanılabilir lisanslarını kullandıysanız, artık başka kopya dağıtamazsınız. Aşağıdaki işlemlerden birini yapmanız gerekir:
* Uygulamayı bazı cihazlardan kaldırın.
* Geçerli dağıtımın kapsamını, yalnızca lisanslarınızın yeterli olduğu kullanıcıları hedefleyecek şekilde daraltın.
* İş İçin Windows Mağazası’ndan uygulamanın daha fazla kopyasını satın alın.

> [!Important]
> Dağıtılan uygulamalar yalnızca cihazı ilk kaydeden kullanıcı tarafından kullanılabilir. Uygulamaya başka hiçbir kullanıcı erişemez.


### Ayrıca bkz.
[Microsoft Intune'da mobil cihazlara uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


