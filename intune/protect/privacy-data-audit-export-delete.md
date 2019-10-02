---
title: Kişisel verileri denetleme, dışarı aktarma veya silme
description: Kişisel verileri denetleme, dışarı aktarma veya silme hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1fb30e8e07d71b72e337a8c2b27b3ed751c9d03e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729545"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Intune’da kişisel verileri denetleme, dışarı aktarma veya silme

Intune yöneticileri, denetim günlükleriyle ilgili kişisel verileri etkinlik izlemek için kullanabilir. Yöneticiler ayrıca kişisel verileri dışarı aktarabilir ve silebilir.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Kişisel verileri denetleme

Denetim günlükleri, kiracı yöneticilerine Microsoft Intune’da değişiklik yaratan etkinliklerin kaydını sağlar. Denetim günlükleri, birçok yönetim etkinliği için mevcuttur ve genellikle eylem oluşturur, güncelleştirir (düzenler), siler ve atar. Denetim olayları oluşturan kaldırma görevleri de gözden geçirilebilir. Bu denetim günlükleri, cihazları Intune’da kayıtlı olan kullanıcıların kişisel verilerini içerebilir.  

Intune, güvenlik nedeniyle kullanıcı ve cihaz eylemleri için denetim günlüklerini bir yıllık bir süre boyunca tutabilir. Bu günlükler, bir yıllık saklama döneminden sonra otomatik olarak silinir.

Denetim günlüklerini gözden geçirmek için bkz. [Intune etkinlikleri için denetim günlükleri](../fundamentals/monitor-audit-logs.md). 

Yöneticiler denetim günlüklerini silemez.

Bu denetim olayları, bir yıl boyunca saklanır. Kiracı yöneticileri, [bu destek isteği formunu](https://privacy.microsoft.com/en-US/privacy-questions?) kullanarak denetim günlüklerini isteyebilir.

## <a name="export-personal-data"></a>Kişisel verileri dışarı aktarma

Yöneticiler; hesaplar, hizmet verileri ve ilişkili günlükler dahil olmak üzere son kullanıcı kişisel verilerini Veri Sahibi Hakları istekleri doğrultusunda dışarı aktarabilir. Kişisel verileri gizli tutmak için geçerli bir yasal sebebiniz varsa veri sahibine bu verilerin bir kopyasını sağlayıp sağlamamak size ve kuruluşunuza kalmıştır. Verileri sağlamaya karar verirseniz asıl belgenin bir kopyasını, uygun şekilde redakte edilmiş halini veya paylaşmaya uygun gördüğünüz kısımların ekran görüntüsünü veri sahibiyle paylaşabilirsiniz.

Bir kullanıcının kişisel verilerini dışarı aktarmak için şunları kullanabilirsiniz: 
- Cihazlar listesini dışarı aktarmak için Intune MDM Cihaz dikey penceresi. Cihaz verilerini doğrudan da kopyalayabilirsiniz.
- [Export-IntuneData.ps1 betiği](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Son kullanıcı kişisel verilerini silme

Kişisel verileri Intune yönetiminden kaldırmanın üç yolu vardır:
- Cihazı Azure Active Directory’den silmek
- Cihazı fabrika ayarlarına sıfırlamak
- Kullanıcının kendisini kaldırması

### <a name="delete-a-user-from-intune"></a>Intune’dan kullanıcı silmek

Bir son kullanıcının kişisel verilerini Intune’dan silmek için yöneticinin [kullanıcıyı Azure Active Directory’den (AAD) silmesi](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user) gerekir. Kullanıcı AAD’den silindiğinde (kalıcı olarak silindiğinde) Intune, AAD’den silme sinyalini alır ve kullanıcının kişisel verilerinin tamamını otomatik olarak Intune hizmetinden temizlemeye başlar. Kaldırma eylemini takip eden 30 gün içerisinde kullanıcı bilgileri Intune hizmetinden silinir.

### <a name="reset-device-to-factory-settings"></a>Cihazı fabrika ayarlarına sıfırlama
Fabrika ayarlarına sıfırlama, tüm şirkete ait ve kişisel veri ve ayarlar yerine orijinal fabrika ayarlarını geri yükler. Bu, cihazı yeni bir çalışana vermek için kullanışlıdır. Kullanıcı dosyaları, kullanıcının yüklediği uygulamalar ve varsayılan olmayan ayarlar kaldırılır ve bu veriler kaldırma eylemini izleyen 30 gün içerisinde Intune hizmetinden silinir.

### <a name="user-self-removal-from-intune-management"></a>Kullanıcının kendisini Intune yönetiminden kaldırması
Kullanıcılar, yönetici yardımı olmadan kendi [Android, Apple veya Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android) cihazlarını Intune’dan kaldırabilir.   

### <a name="retire"></a>Devre dışı bırakma
**Kullanımdan kaldırma** eylemi; şirket uygulamaları, Intune'un yönettiği uygulamalara ilişkin veriler, ilke ayarları ve Intune yoluyla sağlanan e-posta profilleri gibi Intune tarafından sağlanan verileri kaldırır. Bu eylem, kullanıcının kişisel verilerini cihazda bırakır.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Microsoft Intune’dan kiracı silme

Bir Intune kiracısı Intune hesabını iptal ederse, Intune hesabının kapatılmasını izleyen 180 gün içerisinde tüm kiracı verileri silinir. AAD kiracısı diğer Microsoft kuruluş abonelikleri (Azure, Office 365) ile ilişkiliyse yalnızca Intune Müşteri Verileri silinir. AAD kiracı kaynağı, diğer abonelikler tarafından kullanılmak üzere saklanır. AAD kiracısıyla ilişkili tek abonelik Intune hesabıysa Intune Müşteri Verilerinin yanında kiracı ve tüm kaynaklar da silinir.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Karma bir Mobil Cihaz Yönetimi (MDM) ortamında kullanıcı silme
Karma bir MDM ortamınız (Configuration Manager ile tümleştirilmiş Intune) varsa bir kullanıcıyı tamamen silmek ve yerel Active Directory’nizden, Configuration Manager’dan ve Intune’dan tamamen kaldırmak için aşağıdaki eylemleri gerçekleştirmeniz gerekir.

1. Kullanıcıyı yerel Active Directory’nizden (AD) silin. Böylece kullanıcı Azure AD ile eşitlenme durdurulur ve Configuration Manager bulma tarafından bulunur. 
2. Kullanıcıyı ve ilişkili verileri Configuration Manager’dan kaldırmak için kullanıcıyı Configuration Manager’dan silin. Konsolda **Varlık ve Uyumluluk** > **Kullanıcılar**’a gidin, silinecek kullanıcıya sağ tıklayın ve **Sil**’e tıklayın.
3. [Kullanıcıyı AAD’den silin](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user), böylece kullanıcı ve ilişkili veriler Azure Active Directory ve Intune’dan aynı anda silinir. Kullanıcı AAD’den silindiğinde (kalıcı olarak silindiğinde) Intune, AAD’den silme sinyalini alır ve kullanıcının kişisel verilerinin tamamını otomatik olarak Intune hizmetinden temizlemeye başlar. Kaldırma eylemini takip eden 30 gün içerisinde kullanıcı bilgileri Intune hizmetinden silinir.

> [!Important]
>Yeni karma MDM müşterisi ekleme seçeneği kullanım dışı bırakılmıştır. Daha fazla bilgi için [Karma Mobil Cihaz Yönetiminden Azure’da Intune’a geçme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) başlıklı blog gönderisine bakın.

## <a name="next-steps"></a>Sonraki adımlar

Intune’da kişisel verileri [denetleme, dışarı aktarma ve silme](privacy-data-audit-export-delete.md) hakkında bilgi edinin.
