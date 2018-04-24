---
title: Mobil cihazlar için Exchange erişim kuralları
description: EAS ile cihaz bağlantılarına izin vermek ya da bunları engellemek için Exchange ActiveSync erişim kuralları
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93dece592ce5280b1650303484bd24169814465c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="exchange-access-rules-for-mobile-devices"></a>Mobil cihazlar için Exchange erişim kuralları

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Mobil cihazlar için Exchange erişim kuralları, bu cihazların Exchange ActiveSync’e erişim düzeylerini belirler. Bu ayarlar, Microsoft Intune’a kaydedilmemiş olanlar da dahil olmak üzere tüm mobil cihazları etkiler. Özel bir kural uygulanmayan tüm mobil cihazlar için geçerli olan bir **Varsayılan Kural** tanımlayarak başlayabilirsiniz.

Aşağıdaki tablo, Exchange ActiveSync tarafından yönetilen erişim düzeylerini içerir:

|Erişim düzeyi|Description|
|----------------|---------------|
|**Cihazların Exchange'e erişmesine izin verme**|*Erişime izin ver* durumunda, mobil cihazlar Exchange ActiveSync üzerinden eşitlenebilir; e-posta almak ve Takvimi, Kişileri, Görevleri ve Notları yönetmek için Exchange sunucusuna bağlanabilir. Kullanıcı veya söz konusu mobil cihaz Exchange yöneticisi tarafından engellenmemişse, cihaz yapılandırdığınız herhangi bir Exchange ActiveSync posta kutusu ilkesiyle uyumlu olduğu sürece bu devam eder.|
|**Cihazların Exchange'e erişimini engelleme**|*Erişimi engelle* durumunda, mobil cihazlar engellenir ve Exchange sunucusuna bağlanmalarına izin verilmez. Cihazlar bir HTTP 403 Yasak hatası alır. Kullanıcı, Exchange sunucusundan mobil cihazın posta kutusuna erişiminin engellendiğini bildiren bir e-posta iletisi alır. Bu ileti, engellenen mobil cihazda olamaz. **Kullanıcı Bildirimi Ayarla** görevini kullanarak, cihazları engellenen kullanıcılara yönergeler sağlamak için bu iletiye özel metin ekleyebilirsiniz. |
|**Daha sonra izin vermek veya engellemek üzere cihazları karantinaya alma**|Bir mobil cihaz karantinaya alındığında, mobil cihazın Exchange sunucusuna bağlanmasına izin verilir. Ancak, verilere yalnızca sınırlı erişimi vardır. Kullanıcı kendi Takvim, Kişiler, Görevler ve Notlar klasörlerine içerik ekleyebilir ancak sunucu, cihazın kullanıcının posta kutusundan içerik almasına izin vermez. Kullanıcı, mobil cihazının karantinaya alındığını bildiren tek bir e-posta iletisi alır. Bu ileti cihaza ve kullanıcının posta kutusuna gönderilir. **Kullanıcı Bildirimi Ayarla** görevini kullanarak, cihazları karantinaya alınan kullanıcılara yönergeler sağlamak için bu iletiye özel metin ekleyebilirsiniz.|

Erişim stratejisi, Exchange'e bağlanan tüm mobil cihazlar için geçerli olan **Varsayılan Kural**’ın ve **Platform Özel Durumları**'nın bir birleşimidir. Aşağıdaki tabloda bazı örnek erişim stratejileri listelenmektedir.


|    Erişim stratejisi    |                                                                                                                                                                                                                                                                                       Description                                                                                                                                                                                                                                                                                        |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      İzin verilenler listesi       |                                                                                  Bilinen cihazlar listesine erişim verip geri kalan tüm cihazlar için erişimi kısıtlamak üzere bir <em>izin verilenler listesi</em> kullanabilirsiniz. Bunu yapmak için kullanıcının posta kutusuna erişmesine izin verilen cihaz platformları için özel kurallar oluşturmanız gerekir. Böyle bir kural oluşturur oluşturmaz varsayılan erişim kuralını diğer tüm cihazları engelleyecek veya karantinaya alacak şekilde ayarlamanız gerekir. İzin verilenler listesine yeni bir cihaz eklemek için yeni bir özel kural oluşturun.                                                                                  |
|      Engellenenler listesi       |                              Varsayılan olarak tüm cihazlara erişim vermek ancak kuruluşunuza erişmesini istemediğiniz belirli cihazlar için erişimi engellemek üzere bir <em>engellenenler listesi</em> kullanabilirsiniz. Kuruluşun posta kutularıyla eşitlenmesini istemediğiniz cihaz platformlarını engellemek için özel kurallar oluşturarak bir engellenenler listesi oluşturun. Varsayılan kuralı, mevcut kurallar ile açıkça engellenmeyen tüm cihazlara izin verecek şekilde ayarlamanızı öneririz. Engellenenler listesine yeni bir cihaz veya cihaz kümesi eklemek için, yeni bir özel kural oluşturun.                               |
| Karma izin verme ve engelleme | İzin verme ve engelleme listeleri oluşturmaya ek olarak, kuruluşa katılan yeni mobil cihazları değerlendirmeye devam ederken karantinaya alabilirsiniz. Örneğin, kuruluşunuzda izin verilmeyen mobil cihazlar için bir engellenenler listeniz ve izin verilen mobil cihazlar için bir izin verilenler listeniz varsa, varsayılan kuralı karantina olarak ayarlayabilirsiniz. Diğer tüm cihazlar otomatik olarak karantinaya alınır. Böylece kuruluşa katılan yeni cihazları bulabilir ve bunları izin verilenler listesine mi, yoksa engellenenler listesine mi ekleyeceğinize karar verebilirsiniz. |

Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır.

## <a name="create-a-default-access-rule"></a>Varsayılan erişim kuralı oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Exchange ActiveSync**’i seçin.

2.  **Varsayılan Kural** listesinde, bir kural veya kişisel muafiyet kapsamında olmayan tüm mobil cihazlara uygulanmasını istediğiniz Erişim Kuralı’nı seçin. **Kaydet**’i seçin.

Aşağıdaki yordamda özel bir kuralın nasıl oluşturulacağı açıklanmaktadır:

## <a name="create-a-custom-access-rule"></a>Özel erişim kuralı oluşturma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Exchange ActiveSync**’i seçin.

2.  **Platform Özel Durumları** listesinde **Kural Ekle**'yi seçin ve sonra özel bir kural oluşturun. **Kaydet**’i seçin.
