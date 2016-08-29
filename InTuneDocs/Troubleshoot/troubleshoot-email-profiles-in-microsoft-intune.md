---
title: "E-posta profilleriyle ilgili sorunları giderme | Microsoft Intune"
description: "E-posta profili sorunları, bu sorunları giderme ve çözme."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 08/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb0aeac2f94dfde50d9398b09c6b21c7ae40624
ms.openlocfilehash: 79076b65fe85adeaffd5435915cb5eca2a15413f


---

# Microsoft Intune’da e-posta profilleriyle ilgili sorunları giderme
Burada bazı e-posta profili sorunları listelenir, bunların nasıl giderileceği ve çözüleceği açıklanır.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).


## E-posta hesabından resim gönderilemedi
Otomatik olarak yapılandırılan e-posta hesaplarına sahip kullanıcılar, cihazlarından resim veya görüntü gönderemiyor.
**Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver** seçeneği etkinleştirilmediğinde bu durum ortaya çıkar.

### Intune çözümü

1.  Microsoft Intune Yönetim Konsolu’nu açın, **İlke** iş yükü &gt; **Yapılandırma İlkesi**’ni seçin.

2.  E-posta profilini seçin ve **Düzenle**’yi seçin.

3.  **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

### Intune ile tümleştirilmiş Configuration Manager çözümü

1.  Configuration Manager konsolu &gt; **Varlıklar ve Uyum**'u açın.

2.  **Genel Bakış** -&gt;**Uyumluluk Ayarları** -&gt; **Şirket Kaynağına Erişim**’i genişletin ve **E-posta Profilleri**’ni seçin.

3.  E-posta profiline sağ tıklayın ve **Özellikler**’i açın.

4.  **Eşitleme Ayarları** sekmesinde **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.


## Cihazda zaten yüklü bir e-posta profili var

Intune tarafından profil sağlanmadan önce kullanıcı bir e-posta profili yüklediyse, Intune e-posta profili dağıtımının sonucu cihaz platformuna bağlıdır:

-**iOS**: Intune, konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğunu algılar. Kullanıcı tarafından oluşturulmuş yinelenen e-posta profili, Intune yöneticisinin oluşturduğu bir profili engeller. Bu, iOS kullanıcıları genellikle bir e-posta profili oluşturduğundan, ardından kaydolduğundan, bu yaygın görülen bir sorundur. Şirket portalı, kullanıcıyı, el ile yapılandırılmış e-posta profilleri nedeniyle uyumlu olmadıkları konusunda bilgilendirir ve kullanıcıdan, o profili kaldırmasını ister. Kullanıcı, Intune profilinin dağıtılabilmesi için, e-posta profilini kaldırmalıdır. Bu sorunun önüne geçmek için, kullanıcılarınızdan bir e-posta profili yüklemeden önce kaydolmalarını ve Intune’un profili dağıtmasına izin vermelerini isteyin.

-**Windows**: Intune, konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğunu algılar. Intune kullanıcı tarafından oluşturulmuş var olan e-posta profilinin üzerine yazar.

-**Samsung KNOX**: Intune, e-posta adresini temel alan yinelenen bir e-posta hesabı olduğunu algılar ve Intune profilini bunun üzerine yazar. Kullanıcı bu hesabı yapılandırırsa, Intune profili tarafından hesabın yeniden üzerine yazılır. Hesap yapılandırmasının üzerine yazılan kullanıcı için bu durumun kafa karıştırıcı olabileceğini unutmayın.

Samsung KNOX’un profili algılamak için konak adını kullanmaması nedeniyle, farklı konaklarda aynı e-posta adresine dağıtmak üzere birden çok e-posta profili oluşturursanız bunlar birbirinin üzerine yazılacağından, bunu yapmamanızı öneririz.

## KNOX cihazı için 0x87D1FDE8 hatası
**Sorun**: Çeşitli Android cihazlarda Samsung KNOX için Exchange Active Sync e-posta profilini oluşturduktan ve dağıttıktan sonra, cihazların özellikler &gt; ilke sekmesinde **0x87D1FDE8** hatası veya **düzeltme başarısız** hatası bildirilir.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmez ve profilinizde bu seçenek belirtilmemelidir. Cihazların ilkeyi işlemesi için yeterli bir süre beklendiğinden (24 saate kadar) emin olun.

## Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Aug16_HO1-->


