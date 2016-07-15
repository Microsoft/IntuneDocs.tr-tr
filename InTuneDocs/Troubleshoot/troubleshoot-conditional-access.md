---
title: "Koşullu erişim sorunlarını giderme | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f79d2890c450a803bfb84ffa3c12b0de58a158c
ms.openlocfilehash: 373b9bf9794840f999d5e5b21fc411ff621a23e1


---

# Koşullu erişim sorunlarını giderme

Bu konuda, kullanıcıların, kaynaklara Intune koşullu erişim üzerinden erişemediklerinde ne yapacakları açıklanmaktadır. 

### Koşullu erişimde başarılı olmanın temel unsurları

İşe koşullu erişim sağlamak için, aşağıdaki koşullar gerekir:

-   Cihaz Intune tarafından yönetilmelidir.
-   Kullanıcı, Azure Active Directory’ye (AAD) kayıtlı olmalıdır
-   Cihaz, Intune'da yapılandırdığınız uyumluluk ilkeleri ile uyumlu olmalıdır. 
-   Kullanıcı, Outlook yerine cihazın yerel posta istemcisinden posta alıyorsa, cihazda EAS etkinleştirilmelidir.

Bu koşullar, Azure Yönetim Portalı’nda ve cihaz envanter raporunda her cihaz için görüntülenebilir.





Genellikle, bir kullanıcı e-posta veya SharePoint’a erişmeye çalışır ve kaydolmak için bir istem alır. Bu istem, kullanıcıyı şirket portalına götürür. Bu davranış için olası açıklamalar ve önerilen çözümler aşağıda verilmiştir:

## Modern kimlik doğrulama senaryoları

### Kayıt sorunları

 -  Cihaz kaydolmamıştır, böylelikle kayıt olunduğunda sorun çözümlenecektir.
 -  Kullanıcı cihazı kaydetmiştir, ancak çalışma alanına katılma başarısız olmuştur. Kullanıcı, şirket portalından kaydı güncelleştirmelidir. 
 
### Uyumluluk sorunları

 -  Cihaz Intune ilkesiyle uyumlu değildir. Şifreleme ve parola gereksinimleri yaygın görülen sorunlardır. Kullanıcı, şirket portalına yönlendirilir ve buradan, cihazını uyumlu olacak şekilde yapılandırabilir.
 -  iOS cihazları için, kullanıcı tarafından oluşturulmuş geçerli bir e-posta profili, Intune'dan uyumlu bir profil dağıtılmasını (Intune yöneticisi tarafından oluşturulan) engeller. Bu, iOS kullanıcıları genellikle bir e-posta profili oluşturduğundan, ardından kaydolduğundan, bu yaygın görülen bir sorundur. Şirket portalı, kullanıcıyı, el ile yapılandırılmış e-posta profilleri nedeniyle uyumlu olmadıkları konusunda bilgilendirir ve kullanıcıdan, o profili kaldırmasını ister. Kullanıcı, Intune profilinin dağıtılabilmesi için, e-posta profilini kaldırmalıdır. Sorunu önlemek için, kullanıcılarınızdan bir e-posta profili yüklemeden kayıt olmalarını ve Intune’un profili dağıtmasına izin vermelerini isteyin.  
 -  Uyumluluk bilgilerinin bir cihaz için kaydolması biraz zaman alabilir. Birkaç dakika bekleyin ve tekrar deneyin.

### İlke sorunları

Bir uyumluluk ilkesi oluşturduğunuzda ve onu bir e-posta ilkesine bağladığınızda, her iki ilkenin aynı kullanıcıya dağıtılması gerekir, bu nedenle, hangi ilkelerin hangi gruplara dağıtıldığını planlamada dikkatli olun. Yalnızca bir ilke uygulanmış kullanıcılar, olasılıkla, cihazların uyumlu olmadığını anlayacaktır.


## Exchange ActiveSync senaryoları


- Kayıtlı ve uyumlu bir Android cihaz, şirket kaynaklarına erişmeye çalışırken yine de karantina bildirimi alabilir. **Başlat** bağlantısını seçmeden önce, kullanıcı, kaynaklara erişmeye çalıştıklarında şirket portalının açık olmamasını sağlamalıdır. Kullanıcılar, şirket portalını kapatmalı, kaynaklara yeniden erişmeye çalışmalı ve ardından **Başlat** bağlantısını kapatmalıdır.

- Kullanımdan kaldırılmış bir cihaz, kullanımdan kaldırıldıktan sonra birkaç saat için erişime sahip olmaya devam edebilir. Bunun nedeni, Exchange’in, erişim haklarını 6 saat boyunca önbelleğe almasıdır. Bu senaryoda, kullanımdan kaldırılan cihazlardaki verileri korumanın başka yöntemlerini göz önünde bulundurun.
- Olası sorun, EASID, AAD’ye yamanamıyor. Bu sorunun temel nedeni azaltmadır, bu yüzden, birkaç dakika bekleyin ve yeniden deneyin. 

## OWA posta kutusu günlüklerini toplama

Dağıtımınızın sorunlarını giderdikten sonra Exchange bağlantısı sorunları devam ederse, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) kısmına açıklandığı şekilde, Microsoft Destek ile irtibat kurmadan önce, OWA posta kutusu günlüklerini toplayın.

1. OWA aracılığıyla oturum açın ve sağ üst köşedeki adınızın yanındaki ayarları (dişli) simgesini seçin. 
2. **Seçenekler**’i seçin
3. Sol taraftaki sütunda **Telefon** (**Mobil Cihazlar** olarak gözükebilir) seçin.
4. Üstteki menüden, **Mobil Cihazlar**’ı seçin. 
5. Listeden cihazınızı seçin ve ardından **Günlüğü Başlat**’ı seçin. 
6. İstendiğinde, açılan iletişimde **Evet**’i seçin. 
7. Soruna neden olan eylemi gerçekleştirin, böylelikle onu yeniden oluşturabilirsiniz. 
8. 1-2 dakika bekleyin, sonra OWA’da telefon listesinde dönün (listede telefonunuzun seçili olduğundan emin olun) ve üstteki menüden **Günlüğü Al**’ı seçin. 
9. Şimdi, kendinizden, eklentili bir e-posta gelmiş olmalıdır. Bir destek bileti açtığınızda, e-posta içeriğini Microsoft Destek’e sağlayın.


### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Jun16_HO4-->


