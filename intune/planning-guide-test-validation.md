---
title: "Intune’u sınama ve doğrulama"
titlesuffix: Microsoft Intune
description: "Çevrenizdeki Intune bulut çözümünüzde sınama ve doğrulama yapma."
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: 1346c0f5b0e1665e49e09fc566b9ff3da17fc17a
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="intune-testing-and-validation"></a>Intune’u sınama ve doğrulama

Microsoft Intune uygulamasını sınarken, işlevsel doğrulama ve kullanım örneği doğrulamasını dikkate alın. İşlevsel doğrulama, her bileşeni ve yapılandırmayı sınama ve düzgün çalışıp çalışmadığını belirleme aşamalarından oluşur. Kullanım örneği doğrulaması, bir dizi görev içeren senaryonun beklendiği gibi çalıştığını doğrulamak için sınama işlemi içerir. 

Destek belgelerinin oluşturulması ve BT destek ve yardım masası personelinin ürünü zorlanmadan destekleyebilmesi için, sınama aşamasına BT destek ve yardım masası personelini dahil etmenizi öneririz. Bir bileşen ya da senaryo kullanım örneklerine dayalı olarak çalışmıyorsa gerekli değişiklikleri belgelediğinizden ve değişikliğin nedenini eklediğinizden emin olun.

## <a name="before-you-begin"></a>Başlamadan önce

Şunları belgelemenizi öneririz:

-   **Sınama ölçütleri:** Karşılaştırılacak kıyaslama noktalarını tanımlayın.

-   **Tasarım bileşenleri:** En az bir sınama ölçütünde bulunmalıdır.

Bir tasarım bileşeni; bir gereksinim veya senaryoya uygun en az bir sınama ölçütünde mevcut değilse tasarım bileşeninin gerekli olup olmadığını göz önünde bulundurun. Ayrıca, aşağıdaki öğelere sahip olduğunuzdan emin olun:

-   **Hesaplar:** Tüm kullanım örneği senaryolarının sınanması için EMS ve Office 365 lisansına sahip sınama hesapları.

-   **Cihazlar:** Silinebilen veya fabrika ayarlarına sıfırlanabilen sınama cihazları.

-   **Tümleştirme bileşenleri:** Tüm tümleştirme bileşenleri (sertifika bağlayıcısı, barındırılan Exchange için Intune hizmetten hizmete bağlayıcısı ve Intune şirket içi Exchange bağlayıcısı) gerekirse yüklenmeli ve yapılandırılmalıdır.

Öngörülemeyen sorunları ele almak için tasarım değişikliklerine gerek duyabilirsiniz. Ayrıca tüm tasarım değişiklikleri, her değişikliğin nedeniyle birlikte tam olarak belgelenmelidir. Bir değişikliğin neler yapabileceğini gösteren bir örnek aşağıda verilmiştir:

<blockquote>Ağ Cihazı Kayıt Hizmeti (NDES) gereksinimlerini karşılamadığınızı fark edebilir ve ayrıca VPN ve Wi-Fi profillerinin NDES uygulaması olmadan aynı gereksinimleri karşılayan bir kök CA ile yapılandırılabileceğini öğrenebilirsiniz.</blockquote>

Sınama ve doğrulama aşamasında teknik rehberlik veya özel sorun giderme gerektiren zorluk veya sorunlarla karşılaşabilirsiniz. Microsoft destek kanallarında yardım aramanızı öneririz.

-   [Intune desteği almayı öğrenme](get-support.md)

-   [Microsoft Intune için yardımlı telefon desteği ile iletişim kurun](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>İşlevsel doğrulama sınaması

İşlevsel doğrulama, her bileşeni ve yapılandırmayı sınama ve düzgün çalışıp çalışmadığını belirleme aşamalarından oluşur. Bir doğrulama sınaması örneği aşağıdaki tabloda verilmiştir.

![Bölüm 9 tablo 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Kullanım örneği doğrulama sınaması

Senaryoların tam ve işlevsel olduğunu doğrulamak için kullanım örneği doğrulama sınaması gerçekleştirin. İki tür kullanım örneği senaryosu vardır: BT yöneticisi ve son kullanıcı.

### <a name="it-admin"></a>BT yöneticisi

Bir cihaz veya kullanıcıya uygulanan Yönetim eyleminin düzgün çalışıp çalışmadığını doğrulamak için BT Yöneticisi doğrulama sınaması gerçekleştirin. Aşağıda BT yöneticisi uçtan uca doğrulama senaryosu örneği verilmiştir.

![Bölüm 9 tablo 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Son kullanıcı

Son kullanıcı deneyiminin beklendiği gibi olduğu ve tüm kullanıcı iletişimlerinde düzgün biçimde sunulduğunu doğrulamak için son kullanıcı doğrulama sınaması gerçekleştirin. Son kullanıcı deneyiminin doğru olduğunu doğrulamak önemlidir. Doğrulama başarısız olursa benimseme oranı düşebilir ve yardım masası çağrıları artabilir.

![Bölüm 9 tablo 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Sonraki adımlar

Intune işlevsel ve kullanıcı örneği senaryolarınızı sınayıp doğrulamayı tamamladığınıza göre,[ Intune üretim dağıtımınız](planning-guide-rollout-plan.md) için hazırsınız.

Daha fazla plan şablonu ve bilgi için [ek kaynaklara](planning-guide-resources.md) bakın.
