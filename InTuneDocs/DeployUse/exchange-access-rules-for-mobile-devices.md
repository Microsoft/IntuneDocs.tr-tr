---
title: "Mobil cihazlar için Exchange erişim kuralları | Microsoft Intune"
description: "EAS ile cihaz bağlantılarına izin vermek ya da bunları engellemek için Exchange ActiveSync erişim kuralları"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c49e19e8c478af252d7b59c380d5500a57b71db5
ms.openlocfilehash: 7714a338d02afedde2ac090964e4d18d4410a80e


---

# Mobil cihazlar için Exchange Erişim kuralları
Mobil cihazlar için Exchange erişim kuralları, bu cihazların Exchange ActiveSync’e erişim düzeylerini belirler. Bu ayar, Microsoft Intune’a kaydedilmemiş cihazlar da dahil olmak üzere tüm mobil cihazları etkiler. Özel bir kural uygulanmayan tüm mobil cihazlar için geçerli olan bir **Varsayılan Kural** tanımlayarak başlayabilirsiniz. Aşağıdaki tablo, Exchange ActiveSync tarafından yönetilen erişim düzeylerini içerir:

|Erişim düzeyi|Açıklama|
|----------------|---------------|
|**Cihazların Exchange'e erişmesine izin ver**|*Erişime izin verme* durumunda, mobil cihazlar Exchange ActiveSync üzerinden eşitlenebilir ve e-posta almak ve Takvimi, Kişileri, Görevleri ve Notları yönetmek için Exchange sunucusuna bağlanabilir. Kullanıcı veya söz konusu mobil cihaz Exchange yöneticisi tarafından engellenmemişse, cihaz yapılandırdığınız herhangi bir Exchange ActiveSync posta kutusu ilkesiyle uyumlu olduğu sürece bu devam eder.|
|**Cihazların Exchange'e erişimini engelle**|*Erişimi engelleme* durumunda, mobil cihazlar engellenir ve Exchange sunucusuna bağlanmalarına izin verilmez. Aygıtlar HTTP 403 Yasak hatasını alır. Kullanıcı, Exchange sunucusundan mobil cihazın posta kutusuna erişiminin engellendiğini bildiren bir e-posta iletisi alır. Bu ileti, engellenen mobil cihazda olamaz. Cihazları engellenen kullanıcılara yönergeler sağlamak için **Kullanıcı Bildirimi Ayarla** görevini kullanarak bu iletiye özelleştirilmiş metin ekleyebilirsiniz.|
|**Daha sonra izin vermek veya engellemek üzere cihazları karantinaya al**|Bir mobil cihaz karantinaya alındığında, mobil cihazın Exchange sunucusuna bağlanmasına izin verilir. Ancak, verilere yalnızca sınırlı erişimi vardır. Kullanıcı kendi Takvim, Kişiler, Görevler ve Notlar klasörlerine içerik ekleyebilir, ancak sunucu cihazın kullanıcının posta kutusundan içerik almasına izin vermez. Kullanıcı mobil cihazının karantinaya alındığını bildiren bir tek bir e-posta iletisi alır. Bu ileti cihazda ve kullanıcının posta kutusunda alınır. Cihazları karantinaya alınan kullanıcılara yönergeler sağlamak için **Kullanıcı Bildirimi Ayarla** görevini kullanarak bu iletiye özelleştirilmiş metin ekleyebilirsiniz.|

Erişim stratejisi, Exchange'e bağlanan tüm mobil cihazlar için geçerli olan **Varsayılan Kural** ve **Platform Özel Durumları**'nın bir birleşimidir. Aşağıdaki tabloda bazı örnek erişim stratejileri listelenmektedir.

|Erişim stratejisi|Açıklama|
|-------------------|---------------|
|İzin verilenler listesi|Bir bilinen cihazlar listesine erişim verip geri kalan her şey için erişimi kısıtlamak üzere *izin verilenler listesini* kullanabilirsiniz. Bunu yapmak için kullanıcıların posta kutularına erişmesine izin verilen cihaz platformları için özel kurallar oluşturmanız gerekir. Böyle bir kural oluşturur oluşturmaz varsayılan erişim kuralını diğer tüm cihazları engelleyecek veya karantinaya alacak şekilde ayarlamanız gerekir. İzin verilenler listesine yeni bir cihaz eklemek için, yeni bir özel kural oluşturun|
|Engellenenler listesi|Varsayılan olarak tüm cihazlara erişim vermek ancak kuruluşunuza erişmesini istemediğiniz belirli cihazlar için erişimi engellemek üzere bir *engellenenler listesi* kullanabilirsiniz. Kuruluşun posta kutularıyla eşitlenmesini istemediğiniz cihaz platformlarını engellemek için özel kurallar oluşturarak bir engellenenler listesi oluşturun. Varsayılan kural, mevcut kurallar tarafından açıkça engellenmeyen tüm cihazlara erişim vermek üzere ayarlanmalıdır. Engellenenler listesine yeni bir cihaz veya cihaz kümesi eklemek için, yeni bir özel kural oluşturun.|
|Karma izin verme ve engelleme|İzin verme ve engelleme listeleri oluşturmaya ek olarak, kuruluşa katılan yeni mobil cihazları değerlendirmeye devam ederken karantinaya alabilirsiniz. Örneğin, kuruluşunuzda izin verilmeyen mobil cihazlar için bir engellenenler listeniz ve izin verilen mobil cihazlar için bir izin verilenler listeniz varsa, varsayılan kuralı karantina olarak ayarlayabilirsiniz. Diğer tüm cihazlar otomatik olarak karantinaya alınır. Böylece kuruluşa katılan yeni cihazları bulabilir ve izin verilenler listesine veya engellenenler listesine eklemeye karar verebilirsiniz.|
Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır.

## Varsayılan erişim kuralı oluşturma

1.  [Microsoft Intune yönetim konsolu](http://manage.microsoft.com) &gt; **İlke** &gt; **Exchange ActiveSync** bölümünde.

2.   **Varsayılan Kural** listesinde, bir kural veya kişisel özel durum tarafından kapsanmayan tüm mobil cihazlara uygulanmasını istediğiniz Erişim Kuralını seçin. **Kaydet**’i seçin.

Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır.

## Özel erişim kuralı oluşturma

1. [Microsoft Intune yönetim konsolu](http://manage.microsoft.com) &gt; **İlke** &gt; **Exchange ActiveSync** bölümünde.

2.  **Platform Özel Durumları** listesinde **Kural Ekle**'yi seçin ve özel bir kural oluşturun. **Kaydet**’i seçin.



<!--HONumber=Aug16_HO1-->


