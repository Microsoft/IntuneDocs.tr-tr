---
title: "Intune’u sınama ve doğrulama | Microsoft Docs"
description: "Bu makalede, Intune yalnızca bulut çözümünü ortamınızda sınarken ve doğrularken göz önünde bulundurmanız gereken tüm ayrıntılar sağlanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cacb542f5a5ecd8dab317fb165b6332ba376ee97
ms.openlocfilehash: ff56a664f8a604798c718a6b15e834da93a4be26


---

# <a name="intune-testing-and-validation"></a>Intune’u sınama ve doğrulama

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Sınama aşaması, uygulama sırasında ve sonrasında olmalıdır ve daha önce tanımlanan tüm gerekli BT (yönetici) ve son kullanıcı (kullanım örneği) senaryolarını sınamak için sınama hesapları, grupları ve cihazlarınızın olması gerekir.

Destek belgelerinin oluşturulması ve BT destek/yardım masası personelinin ürünü zorlanmadan destekleyebilmesi için sınama aşamasına BT destek/yardım masası personelini dahil etmeniz önerilir. Bir bileşen ya da senaryo kullanım örneklerine dayalı olarak çalışmıyorsa gerekli değişiklikleri belgelediğinizden ve değişikliğin nedenini eklediğinizden emin olun.

## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdakileri belgelemek önemlidir:

-   **Sınama ölçütleri:** Karşılaştırılacak kıyaslama noktalarını tanımlar.

-   **Tasarım bileşenleri:** En az 1 sınama ölçütünde bulunmalıdır.

Bir tasarım bileşeni, bir gereksinim veya senaryoya uygun en az 1 sınama ölçütünde mevcut değilse tasarım bileşeninin gerekli olup olmadığını göz önünde bulundurun. Ayrıca, aşağıdaki öğelere sahip olduğunuzdan emin olun:

-   **Hesaplar:** Sınama aşamasında kullanılan hesapların, tüm kullanım örneği senaryolarının sınanması için EMS ve Office 365 lisansına sahip sınama hesapları olması gerekir.

-   **Cihazlar:** Bu noktada kullanılan cihazlar, silinebilen veya fabrika ayarlarına getirilebilen sınama cihazları olmalıdır.

-   **Tümleştirme bileşenleri:** Tüm tümleştirme bileşenleri (Sertifika Bağlayıcısı, Barındırılan Exchange için Intune hizmetten hizmete bağlayıcısı ve Intune şirket içi Exchange bağlayıcısı) gerekirse yüklenmeli ve yapılandırılmalıdır.

Öngörülemeyen sorunları ele almak için tasarım değişiklikleri gerekebilir. Ayrıca tüm tasarım değişiklikleri, her değişikliğin nedeniyle birlikte tam olarak belgelenmelidir. Bir değişikliğin neler yapabileceğini gösteren bir örnek aşağıda verilmiştir:

-   Ağ Cihazı Kayıt Hizmeti (NDES) gereksinimlerini karşılamadığınızı fark edebilir ve ayrıca VPN ve Wi-Fi profillerinin NDES uygulaması olmadan aynı gereksinimleri karşılayan bir kök CA ile yapılandırılabileceğini öğrenebilirsiniz.

Sınama ve doğrulama aşamasında teknik rehberlik veya özel sorun giderme gerektiren zorluk veya sorunlarla karşılaşabilirsiniz. Microsoft destek kanalları üzerinden yardım aramanız önerilir.

-   [Intune desteği almayı öğrenme](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Microsoft Intune için genel sorun giderme ipuçları](https://docs.microsoft.com/intune/troubleshoot/general-troubleshooting-tips-for-microsoft-intune).

-   [Microsoft Intune için destek almayı öğrenme](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune)

-   [Microsoft Intune için yardımlı telefon desteği ile iletişim kurun](https://docs.microsoft.com/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>İşlevsel doğrulama sınaması

İşlevsel doğrulama, her bileşeni ve yapılandırmayı sınama ve düzgün çalışıp çalışmadığını belirleme aşamalarından oluşur. Bir doğrulama sınaması örneği aşağıdaki tabloda verilmiştir.

![Bölüm 9 tablo 1](../media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Kullanım örneği doğrulama sınaması

Kullanım örneği doğrulama sınaması, senaryoların tam ve işlevsel olduğunu doğrulamak için gerçekleştirilmelidir. İki tür kullanım örneği senaryosu vardır: BT yöneticisi ve son kullanıcı.

### <a name="it-admin"></a>BT Yöneticisi

BT Yöneticisi doğrulama sınaması, bir cihaz veya kullanıcıya uygulanan Yönetim eyleminin düzgün çalışıp çalışmadığını doğrulamak için gerçekleştirilmelidir. Aşağıda BT yöneticisi uçtan uca doğrulama senaryosu örneği verilmiştir.

![Bölüm 9 tablo 2](../media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Son kullanıcı

Son kullanıcı doğrulama sınaması, son kullanıcı deneyiminin beklendiği gibi olduğu ve tüm kullanıcı iletişimlerinde düzgün biçimde sunulduğunu doğrulamak için gerçekleştirilmelidir. Doğrulama hatası, daha düşük benimseme oranlarına ve daha fazla yardım masası çağrılarına neden olabileceğinden, son kullanıcı deneyiminin düzgün olduğunu doğrulamak önemlidir.

![Bölüm 9 tablo 3](../media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Sonraki Adımlar

Intune işlevsel ve kullanıcı örneği senaryolarınızı sınayıp doğrulamayı tamamladığınıza göre, Intune üretim dağıtımınız için hazırsınız. Daha fazla bilgi için bkz. [Ek kaynaklar](additional-resources.md).



<!--HONumber=Dec16_HO5-->


