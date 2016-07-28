---
title: "İlke sorunlarını giderme | Microsoft Intune"
description: "İlke yapılandırma sorunlarını giderin."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 64518fc58a97c0d5060d909b60df565c19498389


---

# Microsoft Intune’da ilke sorunlarını giderme

Burada, Microsoft Intune ilke yapılandırmanızdan kaynaklanabilecek bazı sorunlar ve bu sorunları gidermeye yönelik öneriler listelenir.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).


## İlke cihazınıza uygulandı mı?
**Sorun:** Belirli bir ilkenin cihaza uygulanıp uygulanmadığı net değil veya cihaz ilkede belirtilenin tersine bir davranış gösteriyor.

İlkenin belirli bir cihazı nasıl etkileyeceğini anlamak için, her cihaz için verilen ilke bilgilerini gözden geçirin.

Intune yönetim konsolunda, **Cihaz Özellikleri**’nin altında her cihazın bir ilke sekmesi vardır. Bu sekme yoksa, cihaz hala kayıt aşamasında olabilir ve ilkeler henüz uygulanmamıştır. Her ilkenin bir **Amaçlanan Değer** ‘i ve bir de **Durum**‘u vardır. Amaçlanan değer, ilkeyi atarken ne elde etmek istediğinizi belirtir. Durum, cihaza uygulanan tüm ilkeler ve donanım ve işletim sistemi kısıtlamaları ve gereksinimleri birlikte değerlendirildiğinde gerçekten elde edilen şeydir. Olası durumlar şunlardır:

-   **Uyumlu**: Cihaz ilkeyi almıştır ve ayarla uyumlu olduğunu hizmete bildirir.

-   **Uygulanamaz**: İlke ayarı uygulanabilir değildir. Örneğin, iOS cihazlarının e-posta ayarları bir Android cihazına uygulanamaz.

-   **Beklemede**: İlke cihaza gönderilmiştir ancak hizmete durum bildirilmemiştir. Örneğin Android’de şifreleme için son kullanıcının şifrelemeyi etkinleştirmesi gerektiğinden, askıya alınmış olabilir.

Aşağıdaki ekran görüntüsünde, iki anlaşılır örnek gösterilmektedir:

-   **Amaçlanan Değer** sütununda gösterildiği gibi **Basit parolalara izin ver**, **Evet** olarak ayarlanmış, ancak **Durum** ‘u **Uygulanamaz**‘dır. Bunu nedeni, Android cihazlar için basit parolaların desteklenmemesidir.

-   Benzer şekilde, bu cihaz bir Android cihaz olduğundan **iOS cihazlar için e-posta ayarları** genişletilmiş ilke öğesi bu cihaza uygulanmaz.

![Intune cihaz ilkesi](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, gerçekte daha kısıtlayıcı olan ilkenin uygulanacağını unutmayın.

## İlke yenileme ve güncelleştirme aralıkları
İlkelerin düzenli aralıklarla yenilendiğinden ve güncelleştirildiğinden emin olun. Genel olarak, ilkeler bir değişiklik yapmanızdan sonraki 15 dakika içinde kaydedilmelidir. İlke yenileme için düzenli aralıklar hakkında daha fazla ayrıntı aşağıda verilmiştir:

-   **MDM için kayıtlı Windows cihazı**: İlke, Windows 8.1 ve Windows 10 cihazları için 8 saatte bir ve Windows RT cihazları için 24 saatte bir güncelleştirilir.

-   **Windows Phone**: İlke her 8 saatte bir güncelleştirilir. Şirket Portalı’ndaki **Ayarlar** altında bir yenileme ile zorlanabilir.

-   **iOS**: İlke günde bir kez rastgele bir zaman aralığında güncelleştirilir. Bu da Şirket Portalı açılarak, cihaz seçilerek ve sonra da **Eşitle** seçilerek zorlanabilir.

-   **Android**: İlke günde bir kez rastgele bir zaman aralığında güncelleştirilir. Bu da Şirket Portalı açılarak, cihaz seçilerek ve sonra da **Eşitle** seçilerek zorlanabilir.

## policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar
MDM olmayan Windows cihazları için policyplatform.log dosyasındaki ilke hataları cihazdaki Windows Kullanıcı Hesabı Denetimi’nde (UAC) bulunan varsayılan olmayan ayarların sonucu olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

### UAC sorunlarını çözmek için

1.  [Cihazları Microsoft Intune yönetiminde devre dışı bırakma](/intune/deploy-use/retire-devices-from-microsoft-intune-management) konusunda anlatıldığı gibi bilgisayarı devre dışı bırakın.

2.  İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3.  Başlat menüsünde **UAC** yazarak Kullanıcı Hesabı Denetimi ayarlarını açın.

4.  Bildirim kaydırıcısını varsayılan ayara getirin.

## KNOX cihazı için 0x87D1FDE8 hatası
**Sorun**: Çeşitli Android cihazlarda Samsung KNOX için Exchange Active Sync e-posta profilini oluşturduktan ve dağıttıktan sonra, cihazların özellikler &gt; ilke sekmesinde **0x87D1FDE8** hatası veya **düzeltme başarısız** hatası bildirilir.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmez ve profilinizde bu seçenek belirtilmemelidir. Cihazların ilkeyi işlemesi için yeterli bir süre beklendiğinden (24 saate kadar) emin olun.

## Uyarı: Erişim Kuralları Exchange’e Kaydedilemedi
**Sorun**: Yönetici konsolunda **Erişim Kuralları Exchange’e Kaydedilemedi**  hatasını alıyorsunuz.

Yönetici Konsolu’nun altında, Şirket İçi Exchange İlkesi çalışma alanında ilkeler oluşturduysanız ancak O365 kullanıyorsanız, yapılandırılan ilke ayarları Intune tarafından zorunlu tutulmaz. Uyarıdaki ilke kaynağını not alın.  Şirket İçi Exchange İlkesi çalışma alanındaki eski kuralları silin; çünkü bunlar şirket içi Exchange için Intune’daki Genel Exchange kurallarıdır ve O365’e uygun değildir. Ardından, O365 için yeni ilke oluşturun.

## HATA: Bilgisayardan değer alınamadı, 0x80041013
Yerel sistemdeki saat beş dakika veya daha fazla eşitleme dışı ise bu durum oluşabilir. Yerel bilgisayardaki saat eşitleme dışı ise zaman damgaları geçersiz olacağından güvenli işlemler başarısız olur.

Bu sorunu çözmek için yerel sistem saatini İnternet saatine veya ağ üzerindeki etki alanı denetleyicilerinde ayarlanan saate mümkün olduğunca yakın ayarlayın.

## Çeşitli MDM cihazlarında güvenlik ilkesi değiştirilemez
Windows Phone ve Windows RT cihazlarında, MDM veya EAS yoluyla ayarlamış olduğunuz güvenlik ilkelerinin azaltılmasına izin verilmez. Örneğin, **Parolanın karakter sayısı alt sınırı** olarak 8 ayarlayın ve sonra bunu 4’e indirmeyi deneyin. Cihaza zaten daha kısıtlayıcı bir ilke uygulanmıştır.

Cihaz platformuna bağlı olarak, ilkeyi daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.
Örneğin Windows RT’de, masaüstünde sağdan içeri doğru çekerek **Düğmeler** çubuğunu açın ve **Ayarlar** &gt; **Denetim Masası**’nı seçin.   **Kullanıcı Hesapları** uygulamasını seçin.
Sol taraftaki gezinti menüsünde, en altta bir **Güvenlik İlkelerini Sıfırla** bağlantısı vardır. O bağlantıyı seçin ve ardından **İlkeleri Sıfırla** düğmesini seçin.
Android, Windows Phone 8.1 ve üstü ve iOS gibi diğer MDM cihazlarında, daha az kısıtlayıcı bir ilkeyi uygulayabilmeniz için cihazın devre dışı bırakılması ve sonra hizmete yeniden kaydedilmesi gerekebilir.

## Android cihazları son kullanıcı Kabul etmeden Güvenlik İlkesi Değişikliklerini zorunlu tutmaz
Android MDM, hizmetin cihazlarda ilke değişikliğini zorunlu tutmasına diğer platformlar gibi izin vermez. Bunun nedeni Android işlevselliğidir; Intune hizmetiyle ilgili değildir. Android cihazları, bildirim penceresi yoluyla ilgili ilke değişikliğini (Parola, Şifreleme, vb.) son kullanıcıya sorar.  Son kullanıcının soruyu yanıtlaması ve ilkenin uygulanmasını kabul etmesi gerekir.

## Şirket adı özel karakterler içeriyorsa ilke oluşturulamaz veya istemciler kaydedilemez.
**Sorun:** İlke oluşturamıyor veya istemcileri kaydedemiyorsunuz.

**Çözüm:** [Office 365 yönetim merkezinde](https://portal.office.com/), şirket adından özel karakterleri kaldırın ve şirket bilgilerini kaydedin.

### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Jul16_HO3-->


