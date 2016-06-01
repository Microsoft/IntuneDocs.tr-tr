---
# required metadata

title: Microsoft Intune’da yönetilen mobil cihazlar için Exchange erişim kuralları | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobil cihazlar için Exchange Erişim kuralları
Mobil cihazlar için Exchange erişim kuralları, bu cihazların Exchange’e erişim düzeylerini belirler. Bu ayar, Microsoft Intune’a kaydedilmemiş cihazlar da dahil olmak üzere tüm mobil cihazları etkiler. Özel bir kural uygulanmayan tüm mobil cihazlar için geçerli olan bir **Varsayılan Kural** tanımlayarak başlayabilirsiniz. Aşağıdaki tablo, Exchange ActiveSync tarafından yönetilen erişim düzeylerini içerir:

|Erişim düzeyi|Açıklama|
|----------------|---------------|
|**Özel bir kuralda aksi belirtilmedikçe, tüm mobil cihazların Exchange'e erişmesine izin ver**|*Erişime izin verme* durumunda, mobil cihazlar Exchange ActiveSync üzerinden eşitlenebilir ve e-posta almak ve Takvimi, Kişileri, Görevleri ve Notları yönetmek için Exchange sunucusuna bağlanabilir. Bu, kullanıcı veya söz konusu mobil cihaz Exchange yöneticisi tarafından engellenmemişse, cihaz yapılandırdığınız **Intune Mobil Cihaz Güvenlik İlkesi**'yle uyumlu olduğu sürece devam eder.|
|**Özel bir kuralda aksi belirtilmedikçe, tüm mobil cihazların Exchange erişimini engelle**|*Erişimi engelleme* durumunda, mobil cihazlar engellenir ve Exchange sunucusuna bağlanmalarına izin verilmez. Aygıtlar HTTP 403 Yasak hatasını alır. Kullanıcı, Exchange sunucusundan mobil cihazın posta kutusuna erişiminin engellendiğini bildiren bir e-posta iletisi alır. Bu ileti, engellenen mobil cihazda olamaz. Cihazları engellenen kullanıcılara yönergeler sağlamak için **Kullanıcı Bildirimi Ayarla** görevini kullanarak bu iletiye özelleştirilmiş metin ekleyebilirsiniz.|
|**Özel bir kuralda aksi belirtilmedikçe, her bir mobil cihaz için sonradan karar vermem için tüm mobil cihazları karantinaya al**|Bir mobil cihaz karantinaya alındığında, mobil cihazın Exchange sunucusuna bağlanmasına izin verilir. Ancak, verilere yalnızca sınırlı erişimi vardır. Kullanıcı kendi Takvim, Kişiler, Görevler ve Notlar klasörlerine içerik ekleyebilir, ancak sunucu cihazın kullanıcının posta kutusundan içerik almasına izin vermez. Kullanıcı mobil cihazının karantinaya alındığını bildiren bir tek bir e-posta iletisi alır. Bu ileti cihazda ve kullanıcının posta kutusunda alınır. Cihazları karantinaya alınan kullanıcılara yönergeler sağlamak için **Kullanıcı Bildirimi Ayarla** görevini kullanarak bu iletiye özelleştirilmiş metin ekleyebilirsiniz.|

Erişim stratejisi, Exchange'e bağlanan tüm mobil cihazlar için geçerli olan **Varsayılan Kural** ve **Özel Kurallar** 'ın bir birleşimidir. Aşağıdaki tabloda bazı örnek erişim stratejileri listelenmektedir.

|Erişim stratejisi|Açıklama|
|-------------------|---------------|
|İzin verilenler listesi|Bir bilinen cihazlar listesine erişim verip geri kalan her şey için erişimi kısıtlamak üzere *izin verilenler listesini* kullanabilirsiniz. Bunu yapmak için, istediğiniz belirli cihazların kullanıcıların posta kutularına erişebilmeleri için özel kurallar oluşturmanız gerekir. Böyle bir kural oluşturur oluşturmaz varsayılan erişim kuralını diğer tüm cihazları engelleyecek veya karantinaya alacak şekilde ayarlamanız gerekir. İzin verilenler listesine yeni bir cihaz eklemek için, yeni bir özel kural oluşturun|
|Engellenenler listesi|Varsayılan olarak tüm cihazlara erişim vermek ancak kuruluşunuza erişmesini istemediğiniz belirli cihazlar için erişimi engellemek üzere bir *engellenenler listesi* kullanabilirsiniz. Kuruluşun posta kutularıyla eşitlenmesini istemediğiniz cihazları engellemek için özel kurallar oluşturarak bir engellenenler listesi oluşturun. Varsayılan kural, mevcut kurallar tarafından açıkça engellenmeyen tüm cihazlara erişim vermek üzere ayarlanmalıdır. Engellenenler listesine yeni bir cihaz veya cihaz kümesi eklemek için, yeni bir özel kural oluşturun.|
|Karma izin verme ve engelleme|İzin verme ve engelleme listeleri oluşturmaya ek olarak, kuruluşa katılan yeni mobil cihazları değerlendirmeye devam ederken karantinaya alabilirsiniz. Örneğin, kuruluşunuzda izin verilmeyen mobil cihazlar için bir engellenenler listeniz ve izin verilen mobil cihazlar için bir izin verilenler listeniz varsa, varsayılan kuralı karantina olarak ayarlayabilirsiniz. Diğer tüm cihazlar otomatik olarak karantinaya alınır. Böylece kuruluşa katılan yeni cihazları bulabilir ve izin verilenler listesine veya engellenenler listesine eklemeye karar verebilirsiniz.|
Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır.

## Varsayılan erişim kuralı oluşturma

1.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) &gt; **İlke** &gt; **Mobil Cihazlara Exchange Erişimi**’ne tıklayın.

2.   **Varsayılan Kural** listesinde, bir kural veya kişisel özel durum tarafından kapsanmayan tüm mobil cihazlara uygulanmasını istediğiniz Erişim Kuralını seçin. **Kaydet**’i seçin.

Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır.

## Özel erişim kuralı oluşturma

1. [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) &gt; **İlke** &gt; **Mobil Cihazlara Exchange Erişimi**’ne tıklayın.

2.  **Özel Kurallar** listesinde **Kural Ekle**'yi seçin ve özel bir kural oluşturun. **Kaydet**’i seçin.


<!--HONumber=May16_HO2-->


