---
# required metadata

title: İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme
[İş İçin Windows Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayla Microsoft Intune arasında bağlantı kurarak, toplu uygulama alışverişlerini Intune konsolundan yönetebilirsiniz. Örneğin:
* Intune’la mağazadan satın aldığınız uygulamalar listesini eşitleyebilirsiniz.
* Eşitlenen uygulamalar Intune yönetim konsolunda gösterilir ve bunları aynı diğer uygulamalar gibi dağıtabilirsiniz.
* Kaç tane kullanılabilir lisans olduğunu ve bunlardan kaç tanesinin kullanıldığını Intune yönetim konsolunda izleyebilirsiniz.
* Kullanılabilir yeterli lisans olmadığında Intune uygulamaların dağıtılmasını ve yüklenmesini engeller

## Başlamadan önce
İş İçin Windows Mağazası’ndan uygulamaları eşitlemeye ve dağıtmaya başlamadan önce aşağıdaki bilgileri gözden geçirin:
* Intune’u kuruluşunuz için mobil cihaz yönetim yetkilisi olarak yapılandırmalısınız. Daha fazla bilgi için bkz. [Microsoft Intune’da cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md).
* İş İçin Windows Mağazası’ndan bir hesap almak için kaydolmalısınız
* İş İçin Windows Mağazası hesabını Intune’la ilişkilendirdikten sonra, gelecekte farklı bir hesaba geçemezsiniz.
* Mağazadan satın alınan uygulamalar Intune’a el ile eklenemez veya Intune’dan el ile silinemez. Bunlar yalnızca İş İçin Windows Mağazası’yla eşitlenebilir.
* Intune yalnızca İş İçin Windows Mağazası’ndan satın almış olduğunuz çevrimiçi lisanslı uygulamaları eşitler.

## İş İçin Windows Mağazası hesabınızı Intune’la ilişkilendirme
Intune konsolunda eşitlemeyi etkinleştirmek için, önce mağaza hesabınızı yönetim aracı olarak Intune’u kullanacak şekilde yapılandırmanız gerekir:
1. İş İçin Windows Mağazası’nda oturum açarken, Intune’da oturum açtığınız kiracı hesabının aynısını kullandığınızdan emin olun.
2. İş İçin Windows Mağazası’nda, **Ayarlar** > **Yönetim araçları**’nı seçin..
3. Yönetim araçları sayfasında, **Yönetim aracı ekle**’yi ve sonra da Microsoft Intune’u seçin.

Artık devam edebilir ve Intune konsolunda eşitlemeyi ayarlayabilirsiniz.

## Eşitlemeyi yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’ye tıklayın..
2. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve **İş İçin Mağaza**’ya tıklayın..
3. **İş İçin Windows Mağazası** sayfasında aşağıdakileri yapın:
* Henüz yapmadıysanız, İş İçin Windows Mağazası’na kaydolma bağlantısına tıklayın.
* Kaydolduktan sonra, **Eşitleme Yapılandır**’a tıklayın.
4. **İş İçin Windows Mağazası uygulamasının eşitlenmesini yapılandır** iletişim kutusunda **İş İçin Windows Mağazası eşitlemesini etkinleştirin** öğesini seçin..
5. **Dil** açılan listesinde, İş İçin Windows Mağazası’ndan gelen uygulamaların Intune konsolunda görüntüleneceği dili seçin. Görüntülendikleri dilinden bağımsız olarak, bunlar uygun olduğunda son kullanıcının dilinde yüklenir.
6. **Tamam**'a tıklayın..

## Uygulamaları eşitleme

1. Mağazadan satın aldığınız uygulamaları Intune’la eşitlemek için, **İş İçin Windows Mağazası** sayfasında **Şimdi eşitle**’ye tıklayın.
2. Kullanılabilir uygulamaları görmek ve satın aldığınız uygulamaların düzgün bir şekilde içeri aktarıldığını doğrulamak için, **Uygulamalar** çalışma alanında **Yönetilen Yazılım** > **Lisanslı Yazılım**’a tıklayın.
Bu düğümdeki uygulamalar, sahip olduğunuz toplam lisans sayısı ve kullanılabilir lisanslarınızın sayısıyla birlikte görüntülenir.

## Uygulama dağıtma

Mağazadan alınan uygulamaları, diğer tüm Intune uygulamalarıyla aynı şekilde dağıtırsınız. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md)..
İş İçin Windows Mağazası uygulamasını dağıttığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır. Dağıtılan uygulamanın tüm kullanılabilir lisanslarını kullandıysanız, artık başka kopya dağıtamazsınız ve aşağıdaki işlemlerden birini yapmanız gerekir:
* Uygulamayı bazı cihazlardan kaldırma
* Geçerli dağıtımın kapsamını, yalnızca lisanslarınızın yeterli olduğu kullanıcıları hedefleyecek şekilde daraltma
* İş İçin Windows Mağazası’ndan uygulamanın daha fazla kopyasını satın alma


### Ayrıca bkz.
[Microsoft Intune'da mobil cihazlara uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=May16_HO1-->


