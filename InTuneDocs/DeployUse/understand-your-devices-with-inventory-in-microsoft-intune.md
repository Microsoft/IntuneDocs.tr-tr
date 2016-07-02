---
title: "Envanterle cihazlarınızı anlama | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: 55b99e326e4f22aee62b207eb2e976a8d52e70c3


---

# Microsoft Intune’da envanterle cihazlarınızı anlama
Microsoft Intune, kayıtlı cihazların ve Intune istemci yazılımını çalıştıran Windows bilgisayarlarının envanterini görüntülemenize olanak tanır.

## Kayıtlı cihazlardan ne toplanır?
Mobil cihazlar tarafından toplanan envanteri görüntülemek için, [Mobil Cihaz Envanter Raporları](understand-microsoft-intune-operations-by-using-reports.md)’nı çalıştırın. Intune, kayıtlı cihazlardan aşağıdaki envanteri toplar:

|Özellik|Toplayan|
|------------|-----------------------|
|**Ad**|Tüm cihazlar|
|**İşletim sistemi**|Tüm cihazlar|
|**Üretici**|Tüm cihazlar|
|**Model**|Tüm cihazlar|
|**Yönetim Kanalı**|Tüm cihazlar|
|**AAD Kayıtlı**|Mac OS X dışında tüm cihazlar|
|**Uyumlu**|Tüm cihazlar|
|**EAS Özellikli**|Mac OS X dışında tüm cihazlar|
|**EAS Etkinleştirme Kimliği**|Mac OS X dışında tüm cihazlar|
|**EAS Etkinleştirme Zamanı**|Mac OS X dışında tüm cihazlar|
|**Yönetim Durumu**|Tüm cihazlar|
|**E-posta Adresi**|Tüm cihazlar|
|**Exchange ActiveSync Kimliği**|Tüm cihazlar|
|**Yazılım Kilidi Kırılmış veya Kökü Belirtilen**|Yalnızca iOS ve Android cihazları|
|**Benzersiz Cihaz Kimliği**|Exchange ActiveSync dışında tüm cihazlar|
|**Seri numarası**|iOS, Mac OS X, Android, Windows 8.1, Windows 10 cihazları|
|**Toplam Depolama Alanı**|iOS, Mac OS X, Windows 8.1, Windows 10 cihazları|
|**Boş Depolama Alanı**|iOS, Mac OS X, Windows 8.1, Windows 10 cihazları|
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

## Windows bilgisayarlarından ne toplanır
> [!IMPORTANT]
> Bu bölüm yalnızca Intune Windows bilgisayarı istemci yazılımı çalıştıran Windows bilgisayarları için geçerlidir.

Windows bilgisayarları tarafından toplanan envanteri görüntülemek için, [Bilgisayar Envanter Raporları](understand-microsoft-intune-operations-by-using-reports.md)’nı çalıştırın. Intune, Windows bilgisayarlarından aşağıdaki envanteri toplar:

-   **Ad**

-   **Kasa Türü**

-   **Üretici**

-   **Model**

-   **İşletim sistemi**

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



<!--HONumber=Jun16_HO4-->


