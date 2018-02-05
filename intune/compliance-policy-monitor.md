---
title: Intune cihaz uyumluluk ilkelerini izleme
titlesuffix: Azure portal
description: "Cihaz uyumluluğu ilkelerini izlemeyi öğrenin.\""
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 999cb6a9ec37c42b216cda1f6963bbd61ec8fa66
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, yöneticilerin kuruluşlarındaki cihazların uyumluluk duruşunu analiz etmesine ve kuruluşlarındaki kullanıcıların karşılaştığı uyumluluk sorunlarını hızla gidermelerine yardımcı olur. Cihazların genel uyumluluk durumunu, tek bir ayar için uyumluluk durumunu ve tek bir ilke için uyumluluk durumunu görüntüleyebilir ve tek tek cihazların ayrıntılarına inerek söz konusu cihazı etkileyen belirli ayar ve ilkelere bakabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Azure portalında **Intune Cihaz uyumluluk panosu**’nu bulmak için aşağıdaki adımları izleyin:

1.  [Azure Portal](https://portal.azure.com)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3.  **Intune** &gt; **Cihaz uyumluluğu** &gt; **Genel bakış**’ı seçin. **Cihaz uyumluluk panosu** açılır.

> [!IMPORTANT] 
> Cihaz uyumluluk ilkelerini almak için, cihazların Intune'a kayıtlı olmaları gerekir.

## <a name="device-compliance-dashboard"></a>Cihaz uyumluluk panosu

**Cihaz uyumluluk panosu**‘nda Cihaz uyumluluk ilkesi durumlarını izleyebilirsiniz. Farklı kutucuklar içerisinde yer alan farklı raporlar kuruluşunuzdaki cihazların uyumluluk duruşlarını gösterir. Aşağıdaki raporları görüntüleyebilirsiniz:

-   Genel cihaz uyumluluk toplamı

-   İlkeye göre cihaz uyumluluğu

-   Ayara göre cihaz uyumluluğu

![Cihaz uyumluluk panosu](./media/idc-1.png)

Ayrıca, tek bir cihaz için geçerli olan uyumluluk ilkelerini ve ayarlarını, söz konusu ayarların cihazdaki son uyumluluk durumunu görüntüleyebilirsiniz.

### <a name="overall-device-compliance-aggregate-report"></a>Genel cihaz uyumluluk toplamı raporu

Intune’a kayıtlı tüm cihazlar için toplam uyumluluk durumunu gösteren bir halka grafiktir. Cihaz uyumluluk durumları iki farklı veritabanında (Intune ve Azure Active Directory) tutulur. Cihaz uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler aşağıdadır:

-   **Uyumlu**: Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını başarıyla uyguladı.

-   **Uyumlu değil:** Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamadı veya kullanıcı, yönetici tarafından hedeflenen ilkeler ile uyum sağlayamadı.

-   **Yetkisiz kullanım süresi içinde:** Cihaza yönetici tarafından bir veya daha fazla cihaz uyumluluk ilkesi ayarı hedeflendi ancak kullanıcı ilkeleri henüz uygulamadı. Bu nedenle cihaz uyumlu değil, ancak yönetici tarafından tanımlanan yetkisiz kullanım süresi içinde bulunuyor.

    -   Uyumlu olmayan cihazlara yönelik eylemler hakkında daha fazla bilgi edinin.

-   **Cihaz eşitlenmedi:** Cihaz, aşağıdaki nedenlerden biri sonucunda cihaz uyumluluk ilkesi durumunu bildiremedi:

    -   **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramadı.

    -   **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve bunun nedenini açıklayan bir hata iletisi aldı.

> [!IMPORTANT] 
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-option"></a>Detaya gitme seçeneği

**Cihaz uyumluluk panosu**‘nda Cihaz uyumluluğu kutucuğuna tıklarsanız, cihaz uyumluluk ilkeleri tarafından hedeflenen her bir cihaz için belirli bir **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** detayına gidebilirsiniz.

![Detaya gidilmiş cihaz uyumluluk panosu](./media/idc-2.png)

Belirli bir kullanıcı hakkında daha fazla ayrıntı gerekiyorsa kullanıcının e-posta diğer adını yazarak Cihaz uyumluluğu grafik raporunu filtreleyebilirsiniz.

![Belirli bir kullanıcı için cihaz uyumluluk panosu](./media/idc-3.png)

Ayrıca, Cihaz uyumluluk grafiğinde farklı uyumluluk durumlarına tıklayarak kullanıcıya ait cihazların uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler görebilirsiniz.

![Farklı durumlar için cihaz uyumluluk panosu](./media/idc-4.png)

#### <a name="filter"></a>Filtrele

**Filtre düğmesine** tıklarsanız aşağıdaki seçenekleri içeren filtre geçici açılır öğesi görünür:

-   Model

    -   Serbest biçimli arama dizesi kabul eden metin kutusu
<br></br>
-   Platform

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Durum

    -   Uyumlu

    -   Uyumlu Değil

    -   Yetkisiz Kullanım süresi içinde

    -   Bilinmiyor

    -   Hata

**Güncelleştir düğmesine** tıkladığınızda geçici açılır öğe kapatılır ve sonuçlar, seçilen filtre ölçütlerine göre güncelleştirilir.

##### <a name="device-details"></a>Cihaz ayrıntıları

Bir cihaza tıklandığında bu cihaz seçili bir halde **Cihazlar Dikey Penceresi** açılır. Burada, söz konusu cihaz için uygulanan cihaz uyumluluk ilkesi ayarı hakkında daha ayrıntılı bilgiler sunulur.

![Cihaz uyumluluk panosu](./media/idc-6.png)

Cihaz ilkesi ayarının kendisinin üzerine tıkladığınızda yönetici tarafından hedeflenen bu cihaz uyumluluk ayarının kaynağı olan cihaz uyumluluk ilkesinin adını görebilirsiniz.

![Cihaz uyumluluk ayarı adı](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>İlkeye göre cihaz uyumluluğu raporu

Bu raporda, uyumluluk ilkesine göre görünüm ve her bir uyumluluk durumundaki toplam cihaz sayısı sunulmaktadır. **İlke uyumluluğu** kutucuğuna **Cihaz uyumluluk panosu**‘ndan erişilebilir. Bu kutucuk, daha önce yönetici tarafından oluşturulan tüm ilkeleri, ilkenin uygulandığı platformları, uyumlu olan ve olmayan cihazların sayısını gösterir.

![İlkeye göre cihaz uyumluluğu raporu](./media/idc-8.png)

İlke uyumluluğu kutucuğuna ve sonra cihaz uyumluluk ilkelerinden birine tıkladığınızda, cihaz uyumluluk ilkesi tarafından hedeflenen her bir cihaz için **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

![İlke uyumluluğu kutucuğu](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>Ayara göre cihaz uyumluluğu raporu

Bu raporu kullanarak uyumluluk ayarına göre her bir uyumluluk durumundaki toplam cihaz sayısını görüntüleyebilirsiniz. **Ayar uyumluluğu** kutucuğuna **Cihaz uyumluluk panosu**‘ndan erişilebilir. Bu kutucuk, yönetici tarafından oluşturulan tüm cihaz uyumluluk ilkelerinin tüm cihaz uyumluluk ilkesi ayarlarını, ilke ayarlarının uygulandığı platformları, uyumlu olmayan cihazların sayısını gösterir.

![Ayara göre cihaz uyumluluğu raporu](./media/idc-10.png)

Ayar uyumluluğu kutucuğuna ve sonra cihaz uyumluluk ilkesi ayarlarından birine tıkladığınızda, cihaz uyumluluk ilkesi ayarı tarafından hedeflenen her bir cihaz için **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

![Ayar uyumluluğu kutucuğu](./media/idc-11.png)
