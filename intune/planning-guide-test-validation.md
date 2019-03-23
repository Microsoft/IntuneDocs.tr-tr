---
title: Intune’u sınama ve doğrulama
titlesuffix: Microsoft Intune
description: Çevrenizdeki Intune bulut çözümünüzde sınama ve doğrulama yapma.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f63d396f51254f4aec99ac630b812a54ceeb405
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394942"
---
# <a name="intune-testing-and-validation"></a>Intune’u sınama ve doğrulama

Microsoft Intune uygulamasını sınarken, işlevsel doğrulama ve kullanım örneği doğrulamasını dikkate alın. İşlevsel doğrulama, her bileşeni ve yapılandırmayı sınama ve düzgün çalışıp çalışmadığını belirleme aşamalarından oluşur. Kullanım örneği doğrulaması, bir dizi görev içeren senaryonun beklendiği gibi çalıştığını doğrulamak için sınama işlemi içerir. 

Destek belgelerinin oluşturulması ve BT destek ve yardım masası personelinin ürünü zorlanmadan destekleyebilmesi için, sınama aşamasına BT destek ve yardım masası personelini dahil etmenizi öneririz. Bir bileşen ya da senaryo kullanım örneklerine dayalı olarak çalışmıyorsa gerekli değişiklikleri belgelediğinizden ve değişikliğin nedenini eklediğinizden emin olun.

## <a name="before-you-begin"></a>Başlamadan önce

Şunları belgelemenizi öneririz:

-   **Sınama ölçütleri:** Karşılaştırılacak Kıyaslama noktalarını tanımlayın.

-   **Tasarım bileşenleri:** En az birinde bulunmalıdır sınama ölçütünde.

Bir tasarım bileşeni; bir gereksinim veya senaryoya uygun en az bir sınama ölçütünde mevcut değilse tasarım bileşeninin gerekli olup olmadığını göz önünde bulundurun. Ayrıca, aşağıdaki öğelere sahip olduğunuzdan emin olun:

-   **Hesaplar:** EMS ve Office 365'in tüm kullanım örneği senaryolarını test etmek için lisanslı hesapları test edin.

-   **Cihazlar:** Silinebilen veya fabrika ayarlarına sıfırlanabilen sınama cihazlar.

-   **Tümleştirme Bileşenleri:** Tüm Tümleştirme Bileşenleri (sertifika Bağlayıcısı ve Intune Exchange şirket içi Bağlayıcısı) yüklü ve gerekirse yapılandırılmış.

Öngörülemeyen sorunları ele almak için tasarım değişikliklerine gerek duyabilirsiniz. Ayrıca tüm tasarım değişiklikleri, her değişikliğin nedeniyle birlikte tam olarak belgelenmelidir. Bir değişikliğin neler yapabileceğini gösteren bir örnek aşağıda verilmiştir:

<blockquote>Ağ Cihazı Kayıt Hizmeti (NDES) gereksinimlerini karşılamadığınızı fark edebilir ve ayrıca VPN ve Wi-Fi profillerinin NDES uygulaması olmadan aynı gereksinimleri karşılayan bir kök CA ile yapılandırılabileceğini öğrenebilirsiniz.</blockquote>

Sınama ve doğrulama aşamasında teknik rehberlik veya özel sorun giderme gerektiren zorluk veya sorunlarla karşılaşabilirsiniz. Microsoft destek kanallarında yardım aramanızı öneririz.

-   [Intune desteği almayı öğrenme](get-support.md)

-   [Microsoft Intune için yardımlı telefon desteği ile iletişim kurun](get-support.md)

## <a name="functional-validation-testing"></a>İşlevsel doğrulama sınaması

İşlevsel doğrulama, her bileşeni ve yapılandırmayı sınama ve düzgün çalışıp çalışmadığını belirleme aşamalarından oluşur. Bir doğrulama sınaması örneği aşağıdaki tabloda verilmiştir.

![Bölüm 9 tablo 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Kullanım örneği doğrulama sınaması

Senaryoların tam ve işlevsel olduğunu doğrulamak için kullanım örneği doğrulama sınaması gerçekleştirin. İki tür kullanım örneği senaryoları şunlardır: BT yöneticisi ve son kullanıcı.

### <a name="it-admin"></a>BT yöneticisi

Bir cihaz veya kullanıcıya uygulanan Yönetim eyleminin düzgün çalışıp çalışmadığını doğrulamak için BT Yöneticisi doğrulama sınaması gerçekleştirin. Aşağıda BT yöneticisi uçtan uca doğrulama senaryosu örneği verilmiştir.

![Bölüm 9 tablo 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Son kullanıcı

Son kullanıcı deneyiminin beklendiği gibi olduğu ve tüm kullanıcı iletişimlerinde düzgün biçimde sunulduğunu doğrulamak için son kullanıcı doğrulama sınaması gerçekleştirin. Son kullanıcı deneyiminin doğru olduğunu doğrulamak önemlidir. Doğrulama başarısız olursa benimseme oranı düşebilir ve yardım masası çağrıları artabilir.

![Bölüm 9 tablo 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Sonraki adımlar

Intune işlevsel ve kullanıcı örneği senaryolarınızı sınayıp doğrulamayı tamamladığınıza göre,[ Intune üretim dağıtımınız](planning-guide-rollout-plan.md) için hazırsınız.

Daha fazla plan şablonu ve bilgi için [ek kaynaklara](planning-guide-resources.md) bakın.
