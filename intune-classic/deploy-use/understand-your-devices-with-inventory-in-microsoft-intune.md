---
title: 'Envanterle cihazlarınızı anlama '
description: Yönettiğiniz cihazların donanımı hakkındaki bilgileri görüntülemek için Intune’u kullanın.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e50a7329512e6b57eb5486792669b7cd102eebdb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Microsoft Intune’da envanterle cihazlarınızı anlama

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, kayıtlı cihazların ve Intune istemci yazılımını çalıştıran Windows bilgisayarlarının envanterini görüntülemenize olanak tanır.
Intune yönetilen cihazların envanterini tipik olarak 7 günde bir toplar. Bu nedenle cihazda yakın zamanda yapılan değişikliklerin; örneğin, cihazın adının veya boş depolama alanı değişim sonuçlarının raporlarda görünmesinde bir gecikme olabilir.

## <a name="whats-collected-from-enrolled-devices"></a>Kayıtlı cihazlardan ne toplanır?
Mobil cihazlar tarafından toplanan envanteri görüntülemek için, [Mobil Cihaz Envanter Raporları](understand-microsoft-intune-operations-by-using-reports.md)’nı çalıştırın. Intune, kayıtlı cihazlardan aşağıdaki envanteri toplar:

|Özellik|Toplayan|
|------------|-----------------------|
|**Ad**|Tüm cihazlar|
|**İşletim Sistemi**|Tüm cihazlar|
|**Üretici**|Tüm cihazlar|
|**Model**|Tüm cihazlar|
|**Yönetim Kanalı**|Tüm cihazlar|
|**AAD Kayıtlı**|Mac OS X dışında tüm cihazlar|
|**Uyumlu**|Tüm cihazlar|
|**EAS Etkin**|Mac OS X dışında tüm cihazlar|
|**EAS Etkinleştirme Kimliği**|Mac OS X dışında tüm cihazlar|
|**EAS Etkinleştirme Zamanı**|Mac OS X dışında tüm cihazlar|
|**Yönetim Durumu**|Tüm cihazlar|
|**E-posta Adresi**|Tüm cihazlar|
|**Exchange ActiveSync Kimliği**|Tüm cihazlar|
|**İşletim Sistemi Kısıtlamaları Kaldırılmış veya Kök Erişim İzni Verilmiş**|Yalnızca iOS ve Android cihazları|
|**Benzersiz Cihaz Kimliği**|Exchange ActiveSync dışında tüm cihazlar|
|**Seri numarası**|iOS, Mac OS X, Android, Windows 8.1 ve Windows 10 masaüstü cihazları|
|**Toplam Depolama Alanı**|iOS, Mac OS X, Windows 8.1 ve Windows 10 masaüstü ve Mobile cihazları|
|**Boş Depolama Alanı**|iOS, Mac OS X, Windows 8.1 ve Windows 10 masaüstü cihazları|
|**Telefon Numarası**<br>Örneğin bir mobil cihaz envanter raporu çalıştırdığınızda, şirket olarak sınıflandırılmış telefonlar artık tam telefon numaralarıyla tanımlanır. KCG telefon numaraları, &#42; ile maskelenir ve yalnızca son 4 rakamları görüntülenir.|iOS, Android ve Windows Phone cihazları|
|**IMEI**|Exchange ActiveSync, iOS, Android ve Windows Phone cihazları|
|**MEID**<br>Mobil Donanım Kimliği|Yalnızca iOS cihazları|
|**Wi-Fi MAC**|Exchange ActiveSync dışında tüm cihazlar|
|**Abone Taşıyıcı**|Yalnızca iOS ve Android cihazları|
|**Cep Telefonu Teknolojisi**|Yalnızca iOS ve Android cihazları|
|**Denetimli**|Yalnızca iOS cihazları|
|**Etkinleştirme Kilidi Durumu**|Yalnızca iOS cihazları|
|**Kaydetme Tarihi**|Tüm cihazlar|
|**Son Güncelleştirme**|Tüm cihazlar|
|**Ethernet MAC**|Yalnızca Mac OS X cihazları|
|**Etkinleştirme Kilidi Etkin**|Yalnızca iOS cihazları|
|**Şifreleme Etkin**|Tüm cihazlar|

>[!NOTE]
>Cihazla kullandığınız operatöre bağlı olarak yukarıdaki öğelerden bazıları toplanmayabilir.

## <a name="whats-collected-from-windows-pcs"></a>Windows bilgisayarlarından ne toplanır?
> [!IMPORTANT]
> Bu bölüm yalnızca Intune Windows bilgisayarı istemci yazılımı çalıştıran Windows bilgisayarları için geçerlidir.

Windows bilgisayarları tarafından toplanan envanteri görüntülemek için, [Bilgisayar Envanter Raporları](understand-microsoft-intune-operations-by-using-reports.md)’nı çalıştırın. Intune, Windows bilgisayarlarından aşağıdaki envanteri toplar:

-   **Ad**

-   **Kasa Türü**

-   **Üretici**

-   **Model**

-   **İşletim Sistemi**

-   **TPM Sürümü**

-   **Toplam Disk Alanı**

-   **Kullanılan Disk Alanı**

-   **Boş Disk Alanı**

-   **İşletim Sistemi Diski Adı**

-   **İşletim Sistemi Diski Alanı**

-   **İşletim Sistemi Diski Boş Alanı**

-   **Fiziksel Bellek**

-   **İşlemci Adı**

-   **İşlemci Mimarisi**

-   **CPU Hızı**

-   **IP Adresi**

-   **Seri numarası**

-   **Oturum Açan Son Kullanıcı**

-   **Atanan Kullanıcı**

-   **Son Güncelleştirme**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
