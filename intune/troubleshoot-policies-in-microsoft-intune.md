---
title: Microsoft Intune - Azure’da ilke sorunlarını giderme | Microsoft Docs
description: Microsoft Intune’da ilke kullanırken yaygın olarak karşılaşılan problemler veya sorunlar ve bunların çözümleri
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d656dcc8c3abcf3a4b0a9c6aacbc42eb896289f
ms.sourcegitcommit: 7c70c3e0fcae7c4fa8c9e108aafb1cebb366332d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44096512"
---
# <a name="troubleshoot-policies-in-intune"></a>İlke sorunlarını giderme

Intune ilkelerini dağıtma ve yönetme konusunda sorun yaşıyorsanız buradan başlayın. Bu makale, karşılaşabileceğiniz bazı yaygın sorunları ve bunların olası çözümlerini açıklamaktadır.

## <a name="general-issues"></a>Genel Sorunlar

### <a name="was-a-deployed-policy-applied-to-the-device"></a>Dağıtılan bir ilke cihaza uygulandı mı?
**Sorun:** Bir ilkenin doğru uygulanıp uygulanmadığından emin değilsiniz.

Intune > **Cihazlar** > **Tüm cihazlar** > cihazı seçin > **Cihaz yapılandırması** bölümünde her cihaz kendi ilkelerini listeler. Her ilkenin bir **Durumu** vardır. Durum, işletim sistemi kısıtlamaları ve gereksinimleri dahil olmak üzere cihaz için geçerli olan tüm ilkeler ve donanım birlikte değerlendirildiğinde uygulanır. Olası durumlar şunlardır:

- **Uyumlu**: Cihaz ilkeyi almıştır ve ayarla uyumlu olduğunu hizmete bildirir.

- **Uygulanamaz**: İlke ayarı uygulanabilir değildir. Örneğin iOS cihazların e-posta ayarları bir Android cihazına uygulanamaz.

- **Beklemede**: İlke cihaza gönderilmiştir ancak hizmete durum bildirilmemiştir. Örneğin Android’de şifreleme, son kullanıcının şifrelemeyi etkinleştirmesi gerektirdiği için beklemede olarak görünebilir.

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, daha kısıtlayıcı olan ilke uygulanır.

## <a name="issues-with-enrolled-devices"></a>Kaydedilen cihazlar ile ilgili sorunlar

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Uyarı: Erişim Kuralları Exchange’e Kaydedilemedi
**Sorun**: Yönetici konsolunda **Erişim Kuralları Exchange’e Kaydedilemedi**  hatasını alıyorsunuz.

Yönetici Konsolu’nun altında, Şirket İçi Exchange İlkesi çalışma alanında ilkeler oluşturduysanız ancak O365 kullanıyorsanız, yapılandırılan ilke ayarları Intune tarafından zorlanmaz. Uyarıdaki ilke kaynağını not alın.  Exchange Şirket İçi İlke çalışma alanı altında eski kuralları silin. Eski kurallar, şirket içi Exchange için Intune’daki Genel Exchange kurallarıdır ve O365 ile bir ilgisi yoktur. Ardından, O365 için yeni ilke oluşturun.

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a>Çeşitli kayıtlı cihazlarda güvenlik ilkesi değiştirilemiyor
Windows Phone cihazlarda MDM veya EAS yoluyla ayarlamış olduğunuz güvenlik ilkelerinin azaltılmasına izin verilmez. Örneğin, **Parolanın karakter sayısı alt sınırı** olarak 8 ayarlayın ve sonra bunu 4’e indirmeyi deneyin. Cihaza zaten daha kısıtlayıcı bir ilke uygulanmıştır.

Cihaz platformuna bağlı olarak, ilkeyi daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.

Örneğin Windows’da, masaüstünde sağdan içeri doğru çekerek **Düğmeler** çubuğunu açın. **Ayarlar** > **Denetim Masası**’nı ve **Kullanıcı Hesapları**’nı seçin. Sol taraftaki **Güvenlik İlkelerini Sıfırla**’yı seçin ve **İlkeleri Sıfırla**’ya tıklayın.

Android, Windows Phone 8.1 ve üzeri ve iOS gibi diğer MDM cihazlarında daha az kısıtlayıcı bir ilke uygulamak için cihazın devre dışı bırakılması ve sonra hizmete yeniden kaydedilmesi gerekebilir.

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a>Intune yazılım istemcisi çalıştıran bilgisayarlar ile ilgili sorunlar

Klasik portalda geçerlidir.

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar
Intune yazılım istemcisi ile yönetilen Windows bilgisayarlarında, policyplatform.log dosyasındaki ilke hataları, cihazdaki Windows Kullanıcı Hesabı Denetimi’ndeki (UAC) varsayılan olmayan ayarların sonucunda oluşmuş olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

#### <a name="resolve-uac-issues"></a>UAC sorunlarını çözme

1. Bilgisayarı kullanımdan kaldırın. Bkz. [Cihaz kaldırma](devices-wipe.md).

2. İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3. Başlat menüsünde **UAC** yazarak Kullanıcı Hesabı Denetimi ayarlarını açın.

4. Bildirim kaydırıcısını varsayılan ayara getirin.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HATA: Bilgisayardan değer alınamadı, 0x80041013
Yerel sistemdeki saat beş dakika veya daha fazla farklı ise bu hata oluşur. Yerel bilgisayardaki saat eşitleme dışı ise zaman damgaları geçersiz olacağından güvenli işlemler başarısız olur.

Bu sorunu çözmek için yerel sistem saatini İnternet saatine veya ağ üzerindeki etki alanı denetleyicilerinde ayarlanan saate mümkün olduğunca yakın ayarlayın.

### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa [Microsoft Intune için destek alma](get-support.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.
