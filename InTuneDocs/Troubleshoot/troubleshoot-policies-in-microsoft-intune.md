---
title: "İlke sorunlarını giderme | Microsoft Intune"
description: "İlke yapılandırma sorunlarını giderin."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5256d4decfcd14de2d50a32a0906b6894639010
ms.openlocfilehash: 8b2f725dd71a9d5da5387c543261df8607be6d6f


---

# Microsoft Intune’da ilke sorunlarını giderme

Intune ile ilkelerinizi dağıtma ve yönetme konusunda sorun yaşıyorsanız buradan başlayın. Bu konuda, karşılaşabileceğiniz bazı yaygın sorunlar çözümleriyle birlikte sunulmuştur.

## Genel Sorunlar

### Dağıtılan bir ilke cihaza uygulandı mı?
**Sorun:** Bir ilkenin doğru olarak uygulanıp uygulanmadığından emin değilsiniz.

Intune yönetim konsolunda, **Cihaz Özellikleri**’nin altında her cihazın bir ilke sekmesi vardır. Her ilkenin bir **Amaçlanan Değer** ‘i ve bir de **Durum**‘u vardır. Amaçlanan değer, ilkeyi atarken ne elde etmek istediğinizi belirtir. Durum, cihaz için geçerli olan tüm ilkeler ve donanım ve işletim sistemi kısıtlamaları ve gereksinimleri birlikte değerlendirildiğinde gerçekten uygulanan şeydir. Olası durumlar şunlardır:

-   **Uyumlu**: Cihaz ilkeyi almıştır ve ayarla uyumlu olduğunu hizmete bildirir.

-   **Uygulanamaz**: İlke ayarı uygulanabilir değildir. Örneğin, iOS cihazlarının e-posta ayarları bir Android cihazına uygulanamaz.

-   **Beklemede**: İlke cihaza gönderilmiştir ancak hizmete durum bildirilmemiştir. Örneğin Android’de şifreleme için son kullanıcının şifrelemeyi etkinleştirmesi gerektiğinden, askıya alınmış olabilir.

Aşağıdaki ekran görüntüsünde, iki anlaşılır örnek gösterilmektedir:

-   **Amaçlanan Değer** sütununda gösterildiği gibi **Basit parolalara izin ver**, **Evet** olarak ayarlanmış, ancak **Durum** ‘u **Uygulanamaz**‘dır. Bunu nedeni, Android cihazlar için basit parolaların desteklenmemesidir.

-   Benzer şekilde, bu cihaz bir Android cihaz olduğundan **iOS cihazlar için e-posta ayarları** genişletilmiş ilke öğesi bu cihaza uygulanmaz.

![Intune cihaz ilkesi](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, gerçekte daha kısıtlayıcı olan ilkenin uygulanacağını unutmayın.


## Kaydedilen cihazlar ile ilgili sorunlar

### Uyarı: Erişim Kuralları Exchange’e Kaydedilemedi
**Sorun**: Yönetici konsolunda **Erişim Kuralları Exchange’e Kaydedilemedi**  hatasını alıyorsunuz.

Yönetici Konsolu’nun altında, Şirket İçi Exchange İlkesi çalışma alanında ilkeler oluşturduysanız ancak O365 kullanıyorsanız, yapılandırılan ilke ayarları Intune tarafından zorunlu tutulmaz. Uyarıdaki ilke kaynağını not alın.  Şirket İçi Exchange İlkesi çalışma alanındaki eski kuralları silin; çünkü bunlar şirket içi Exchange için Intune’daki Genel Exchange kurallarıdır ve O365’e uygun değildir. Ardından, O365 için yeni ilke oluşturun.

### Çeşitli kayıtlı cihazlarda güvenlik ilkesi değiştirilemiyor
Windows Phone ve Windows RT cihazlarında, MDM veya EAS yoluyla ayarlamış olduğunuz güvenlik ilkelerinin azaltılmasına izin verilmez. Örneğin, **Parolanın karakter sayısı alt sınırı** olarak 8 ayarlayın ve sonra bunu 4’e indirmeyi deneyin. Cihaza zaten daha kısıtlayıcı bir ilke uygulanmıştır.

Cihaz platformuna bağlı olarak, ilkeyi daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.
Örneğin Windows RT’de, masaüstünde sağdan içeri doğru çekerek **Düğmeler** çubuğunu açın ve **Ayarlar** &gt; **Denetim Masası**’nı seçin.   **Kullanıcı Hesapları** uygulamasını seçin.
Sol taraftaki gezinti menüsünde, en altta bir **Güvenlik İlkelerini Sıfırla** bağlantısı vardır. O bağlantıyı seçin ve ardından **İlkeleri Sıfırla** düğmesini seçin.
Android, Windows Phone 8.1 ve üstü ve iOS gibi diğer MDM cihazlarında, daha az kısıtlayıcı bir ilkeyi uygulayabilmeniz için cihazın devre dışı bırakılması ve sonra hizmete yeniden kaydedilmesi gerekebilir.

## Intune yazılım istemcisi çalıştıran bilgisayarlar ile ilgili sorunlar

### policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar
Intune yazılım istemcisi ile yönetilen Windows bilgisayarlarında, policyplatform.log dosyasındaki ilke hataları, cihazdaki Windows Kullanıcı Hesabı Denetimi’ndeki (UAC) varsayılan olmayan ayarların sonucunda oluşmuş olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

#### UAC sorunlarını çözmek için

1.  [Cihazları Microsoft Intune yönetiminde devre dışı bırakma](/intune/deploy-use/retire-devices-from-microsoft-intune-management) konusunda anlatıldığı gibi bilgisayarı devre dışı bırakın.

2.  İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3.  Başlat menüsünde **UAC** yazarak Kullanıcı Hesabı Denetimi ayarlarını açın.

4.  Bildirim kaydırıcısını varsayılan ayara getirin.

### HATA: Bilgisayardan değer alınamadı, 0x80041013
Yerel sistemdeki saat beş dakika veya daha fazla eşitleme dışı ise bu durum oluşabilir. Yerel bilgisayardaki saat eşitleme dışı ise zaman damgaları geçersiz olacağından güvenli işlemler başarısız olur.

Bu sorunu çözmek için yerel sistem saatini İnternet saatine veya ağ üzerindeki etki alanı denetleyicilerinde ayarlanan saate mümkün olduğunca yakın ayarlayın.








### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Sep16_HO1-->


