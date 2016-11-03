---
experimental: true
experiment_id: kgremban_images_080416
title: "Microsoft Intune’a Giriş | Microsoft Intune"
description: "Intune’un nasıl Enterprise Mobility + Security çözümünün mobil cihaz yönetim bileşeni olduğunu hakkında bilgi edinin."
keywords: 
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3318201cd77ec16f72e65275eda0e65c0dd9e05c
ms.openlocfilehash: 256a1e7873a6603226843d2936e44c09424b8050


---

# Intune’a giriş
Microsoft Intune, Microsoft Enterprise Mobility + Security’nin (EMS, eski adı Enterprise Mobility Suite) yönetim koludur. Kurumsal mobil çalışma, çalışanlarınıza tüm cihazlarında daha üretken olma olanağı tanırken kuruluşunuzun bilgilerini de koruma altına almaya yöneliktir.  

EMS üretkenlik, kimlik, erişim denetimi, yönetim ve veri koruması özelliklerini içeren tam bir tümleşik kurumsal mobil çalışma paketidir. Kuruluşunuzda mobil çalışma çözümünü dağıtmak ve çalıştırmak için etkili bir yol sağlar.  

![Kurumsal mobil çalışma vizyonu resmi](..\media\em-vision.png)

Intune mobil cihazları ve mobil uygulamaları yönetmenize yardımcı olur. Kimlik ve erişim denetimi için Azure Active Directory (Azure AD) ve veri koruma için Azure Rights Management (Azure RMS) ile yakın bir tümleştirmede çalışır.  

Intune’un çözmenize yardımcı olduğu yaygın iş sorunları:

* Şirket içi e-postanızın ve işbirliği altyapınızın güvenliğini sağlayarak, İnternet üzerinden mobil cihazlar ve uygulamaların bunlara erişebilmesine olanak tanıma.
* Office 365 altyapınızın güvenliğini sağlayarak, İnternet üzerinden mobil cihazlar ve uygulamaların buna güvenle erişebilmesine olanak tanıma.
* Kuruluşunuzun çalışanlarına cep telefonu vermesini sağlama.
* Kuruluşunuzun görevlerde çalışanlara sınırlı kullanımı olan “paylaşılan cihazlar” vermesini sağlama.
* Kuruluşunuzun güvenli bir “kendi cihazını getir (KCG)” yöntemi veya kişisel cihaz stratejisi uygulamasını sağlama.
* Kuruluşunuzun çalışanları için, ticari fuarın lobisindeki bir bilgi noktası gibi üzerinde denetiminiz olmayan cihazlardan ve uygulamalardan Office 365’e erişimi destekleyebilmesini sağlama.

Intune’un sunduğu başlıca araçlar:
* **Mobil cihaz yönetimi (MDM)**: Cihazları Intune’a kaydederek bunları sağlamanıza, yapılandırmanıza, izlemenize ve bunlar üzerinde işlem yapmanıza (cihazları temizleme gibi) olanak tanıyan özellik.
* **Mobil uygulama yönetimi (MAM)**: Kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme özelliği.
* **Mobil uygulama güvenliği**: Mobil uygulamaları yönetme işlemi kapsamında, kişisel verileri şirket verilerinden yalıtarak ve şirket verilerinin seçmeli temizlenmesine izin vererek mobil uygulamaların güvenliğini sağlamaya yardımcı olabilme.

Bu araçlar, yukarıdaki yaygın iş senaryolarına olanak tanımak için farklı bileşimlerde kullanılır. Örneğin, paylaşılan cihaz senaryolarında MDM yoğun olarak kullanılır. KCG senaryoları normalde MAM’ye dayanır. Şirket telefonu senaryoları ise her ikisi üzerine yapılandırılır. Neredeyse tüm senaryolarda mobil uygulama güvenliği kullanılır.

Bu belge boyunca, iş senaryolarınızı desteklemek için Intune tarafından sağlanan araçları nasıl kullanacağınızı açıklayacağız.  Ayrıca, bu araçların Office 365, Azure AD, Azure RMS ve Microsoft mobil çalışma paketinin diğer parçalarıyla birlikte kullanılmasını da anlatacağız. Teknolojinin yaygın olarak hangi yollarla kullanıldığı ve sizin ortamınızda nasıl yararlı olabileceği konusuna kapsamlı bir genel bakış sağlayacak, ayrıca bunları uygulama yordamlarını da vereceğiz. Teknolojinin kendisi esnektir ve burada açıkladıklarımızın çok ötesinde, her türlü senaryoya uyarlanabilir.

### Sonraki adımlar
* [Intune’u kullanmanın yaygın yolları](common-ways-to-use-intune.md) hakkında yazılanları okuyun.
* [30 günlük Intune denemesini](get-started-with-a-30-day-trial-of-microsoft-intune.md) kullanarak ürünle tanışın.
* Intune’un [teknik gereksinimlerini ve özelliklerini](/intune/get-started/what-to-know-before-you-start-microsoft-intune) derinlemesine öğrenin.



<!--HONumber=Oct16_HO2-->


