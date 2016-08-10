---
title: "Toplu satın alınan iOS uygulamalarını yönetme | Microsoft Intune"
description: "Apple’dan toplu satın aldığınız uygulamaları Intune kullanarak yönetebilirsiniz. Lisans bilgilerini uygulama deposundan içeri aktarabilirsiniz, kaç lisans kullandığınızı izleyebilirsiniz ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önlenir."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c64fb33893027d0000cae4cc3d9c3ed28cc38901
ms.openlocfilehash: 5db23913601973630a4d013aae86cf26af337c4b


---

# Microsoft Intune ile toplu satın alma programından satın aldığınız iOS uygulamalarını yönetme
iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Bu durum, satın alınan uygulamaların birden fazla kopyasın izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

Microsoft Intune lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önleyerek, bu program aracılığıyla satın aldığınız uygulamaları yönetmenize yardımcı olur.

> [!Important]
> Şu anda, Intune iOS VPP uygulama lisanslarını cihazlara değil kullanıcılara atamaktadır. Bu nedenle, son kullanıcıların uygulamayı yüklemek için Apple Kimliği parolalarını girmeleri gerekir.

## iOS cihazları için toplu satın alınan uygulamaları yönetme
[Apple İş için Toplu Satın Alma Programı (VPP)](http://www.apple.com/business/vpp/) ile iOS için birden çok lisans satın alırsınız. Buna Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

## Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve bunu Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdakileri anlamanız gerekir:

* Her kuruluş yalnızca bir VPP hesabına ve belirtecine sahip olabilir.
* Bir Apple VPP hesabını Intune ile ilişkilendirdikten sonra farklı bir hesabı ilişkilendiremezsiniz. Bu nedenle, birden çok kişinin kullandığınız hesaba ilişkin ayrıntıları bilmesi çok önemlidir.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Ancak, dilediğiniz zaman elle eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'a içe aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS VPP kullanmaya başlamadan önce diğer MDM satıcıları ile oluşturulan tüm var olan VPP kullanıcı hesaplarını kaldırın. Intune bu kullanıcı hesaplarını bir güvenlik önlemi olarak Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmetinden verileri eşitler. 
* iOS VPP uygulamalarını Cihaz Kayıt Protokolü (DEP) kullanarak kaydedilen cihazlara dağıtamazsınız.

## Apple VPP belirtecini almak ve karşıya yüklemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Yönetim** &gt; **iOS ve Mac OS X** &gt; **Volume Purchase Program**’ı seçin.

2.  **Apple VPP Hesabı** bağlantısını seçin ve henüz kaydolmadıysanız Volume Purchase Program for Business’a kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin.

3.  Intune konsolunun **Apple Volume Purchase Program (VPP) Yönetimi** sayfasında **VPP belirtecini karşıya yükle**’yi seçin.

4.  **VPP belirtecini karşıya yükle** iletişim kutusunda, VPP belirteç adını ve Apple Kimliğinizi girin veya yapıştırın, sonra **Karşıya Yükle**’yi seçin.

5.  Uyarı iletişim kutusunda, ileride başka bir VPP hesabına geçemeyeceğinizi anladığınızı gösteren onay kutusunu işaretleyin, sonra **Evet**’i seçin.

**Toplu Satın Alma Programı** sayfasında bundan böyle Apple VPP hakkında en son ne zaman güncelleştirildiği, ne zaman sona ereceği ve Intune ile en son ne zaman eşitlendiği gibi bilgileri görüntüleyebilirsiniz.

İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## Toplu satın alınmış bir uygulamayı dağıtmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Uygulamalar** &gt; **Yönetilen Yazılım** &gt; **Toplu Satın Alınmış uygulamalar**’ı seçin. Bu listede, Apple VPP hizmetinden eşitlenmiş olan tüm uygulamalar gösterilir.

2.  Dağıtmak istediğiniz uygulamayı seçin, **Dağıtımı Yönet**’i seçin, sonra uygulamayı karşıya yüklemeyi, oluşturmayı ve dağıtmayı tamamlamak için [Microsoft Intune’da uygulama dağıt](deploy-apps-in-microsoft-intune.md) konusundaki yönergeleri kullanın.

> [!TIP]
> **Gerekli** şeklinde bir dağıtım eylemi seçmeniz gerekir. Kullanılabilir yüklemeler şu anda desteklenmiyor.

Uygulamayı **Gerekli** yükleme olarak dağıttığınızda uygulamayı yükleyen her kullanıcı tarafından bir lisans kullanılır.

Bir lisansı geri kazanmak için dağıtım eylemini **Kaldır** olarak değiştirmeniz gerekir. Uygulama kaldırıldıktan sonra lisans geri kazanılır.

Uygun cihaza sahip bir kullanıcı ilk olarak bir VPP uygulaması yüklemeye çalıştığında kullanıcıdan Apple Toplu Satın Alma programına katılması istenir. Uygulama yüklemesi devam etmeden önce bunu yapmaları gerekir.

> [!TIP]
> Uygulamanın dağıtıldığı her kullanıcının kabul durumunu görmek için **VPP Koşulları Durumu** sütununa bakın.

Başka bir lisans yoksa dağıtım başarısız olur.

## Apple VPP uygulamalarını izlemek için
Hangi VPP uygulamalarının dağıtıldığını ve kaç tane lisansın kullanıldığını **Yönetilen Yazılım** &gt; **Toplu Satın Alma Uygulamaları** düğümündeki **Uygulamalar** çalışma alanından izleyebilirsiniz.

> [!TIP]
> Her bir uygulama yüklemesinin durumunu incelemek için uygulama **Filtreleri**’ni de kullanabilirsiniz.

### Ayrıca bkz.
[Microsoft Intune'da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md)




<!--HONumber=Jul16_HO5-->


