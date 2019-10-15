---
title: Kişisel verileri denetleme, dışarı aktarma veya silme
titleSuffix: Microsoft Intune
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
ms.openlocfilehash: 74428abf8141c648b5b81bba3177cc89a3cb01d2
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306823"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Intune 'da kişisel verileri denetleme, dışarı aktarma veya silme

Intune yöneticileri, kişisel verileri çevreleyen etkinlikleri izlemek için Denetim günlüklerini kullanabilir. Yöneticiler kişisel verileri de dışarı aktarıp silebilir.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Kişisel verileri denetleme

Denetim günlükleri, Kiracı yöneticilerine Microsoft Intune değişiklik üreten etkinliklerin kaydını sağlar. Denetim günlükleri birçok yönetim etkinliği için kullanılabilir ve genellikle eylemleri oluşturma, güncelleştirme (düzenleme), silme ve atama. Denetim olayları üreten uzak görevler de incelenebilir. Bu denetim günlükleri, cihazları Intune 'A kayıtlı olan kullanıcılardan kişisel veriler içerebilir.  

Güvenlik nedeniyle Intune, bir yıllık dönem için Kullanıcı ve cihaz eylemleri için Denetim günlüklerini koruyabilir. Bu Günlükler, bir yıllık saklama süresinden sonra otomatik olarak silinir.

Denetim günlüklerini gözden geçirmek için bkz. [Intune etkinlikleri Için denetim günlükleri](../fundamentals/monitor-audit-logs.md). 

Yöneticiler denetim günlüklerini silemiyor.

Bu denetim olayları bir yıl boyunca tutulur. Kiracı yöneticileri, [Bu destek isteği formunu](https://privacy.microsoft.com/en-US/privacy-questions?)kullanarak denetim günlükleri isteyebilir.

## <a name="export-personal-data"></a>Kişisel verileri dışarı aktarma

Yöneticiler, veri konu hakları istekleriyle uyum sağlamak için hesaplar, hizmet verileri ve ilişkili Günlükler dahil olmak üzere Son Kullanıcı kişisel verilerini dışarı aktarabilir. Bu, siz ve kuruluşunuza, verileri kişisel verilerin bir kopyası ile mi sağlayacağınıza, yoksa bunu vermeyle ilgili yasal bir iş nedeniniz mi olduğunu belirlemek için de kullanabilirsiniz. Bu uygulamayı sağlamaya karar verirseniz, bunlara gerçek belgenin bir kopyasını, uygun bir şekilde redaksiyonu veya paylaşmak için uygun olduğunu kabul ettiğiniz bölümlerin ekran görüntüsünü sağlayabilirsiniz.

Bir kullanıcının kişisel verilerini dışarı aktarmak için şunu kullanabilirsiniz: 
- cihazların listesini dışarı aktarmak için Intune MDM cihaz dikey penceresi. Ayrıca, cihaz verilerini doğrudan kopyalayabilirsiniz.
- [Export-IntuneData. ps1 betiği](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Son Kullanıcı kişisel verilerini sil

Intune yönetiminden kişisel verileri kaldırmanın üç yolu vardır:
- Kullanıcıyı Azure Active Directory Sil
- Cihazı fabrika ayarlarına sıfırlayın
- Kullanıcı kendini kaldırma

### <a name="delete-a-user-from-intune"></a>Intune 'dan Kullanıcı silme

Son kullanıcının Intune 'daki kişisel verilerini silmek için bir yöneticinin [kullanıcıyı Azure Active Directory (AAD) ' dan silmesi](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user)gerekir. Kullanıcı AAD 'den (kalıcı olarak silindi) silindiğinde, Intune, AAD 'den silme sinyali alır ve bu kullanıcının tüm kişisel verilerini Intune hizmetinden temizlemeyi otomatik olarak başlatır. Kullanıcının bilgileri, kaldırma eyleminin 30 gün içinde Intune hizmetinden silinir.

### <a name="reset-device-to-factory-settings"></a>Cihazı fabrika ayarlarına sıfırlama
Fabrika ayarlarına sıfırlama, tüm şirket ve kişisel verileri ve ayarları özgün fabrika ayarlarına geri yükler. Bir sonraki çalışana bir cihaz sağlamak yararlıdır. Kullanıcı dosyaları, Kullanıcı tarafından yüklenen uygulamalar ve varsayılan olmayan ayarlar kaldırılır ve bu veriler, kaldırma eyleminin 30 gün içinde Intune hizmetinden silinir.

### <a name="user-self-removal-from-intune-management"></a>Intune yönetiminden Kullanıcı kendini kaldırma
Kullanıcılar, yönetim yardımı olmadan [Android, Apple veya Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android) kişisel cihazını Intune yönetiminden kaldırabilir.   

### <a name="retire"></a>Bırakmak
**Devre dışı bırakma** eylemi, Intune ile sağlanan Şirket uygulamaları, Intune 'un yönettiği uygulamalarla ilgili veriler, ilke ayarları ve e-posta profilleri gibi Intune tarafından sağlanan verileri kaldırır. Bu eylem, kullanıcının kişisel verilerini cihazda bırakır.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Microsoft Intune 'ten kiracı silme

Bir Intune kiracı müşterisi Intune hesabını iptal ederse, müşteri Intune hesabını kapattıktan sonra tüm kiracı verileri 180 gün içinde silinir. AAD kiracısı diğer Microsoft Enterprise abonelikleri (Azure, Office 365) ile ilişkiliyse, yalnızca Intune müşteri verileri silinir. AAD kiracı kaynağı diğer abonelikler tarafından kullanılmak üzere tutulur. Intune hesabı AAD kiracısı ile ilişkilendirilen tek abonelik ise, kiracı silinir ve tüm kaynaklar ve müşteri verileri de silinir.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Karma mobil cihaz yönetimi (MDM) ortamındaki bir kullanıcıyı silme
Karma MDM ortamınız varsa (Configuration Manager ile tümleşik Intune), bir kullanıcıyı tamamen silmek ve yerel Active Directory, Configuration Manager ve Intune 'dan tamamen kaldırmak için aşağıdaki eylemleri (sırasıyla) tamamlamalısınız.

1. Kullanıcıyı yerel Active Directory (AD) silin. Bu, kullanıcının Azure AD ile eşitlenmesini ve ayrıca Configuration Manager bulma tarafından bulunmasını durdurur. 
2. Kullanıcıyı ve Configuration Manager ilişkili verileri kaldırmak için Configuration Manager konsolundan kullanıcıyı silin. Konsolunda **varlık ve uyum** > **kullanıcıları**' na gidin, silinecek kullanıcıyı sağ tıklatın ve **Sil**' e tıklayın.
3. Kullanıcı ve ilişkili verileri aynı anda hem Azure Active Directory hem de Intune 'dan kaldıran [AAD 'den kullanıcıyı silin](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Kullanıcı AAD 'den (kalıcı olarak silindi) silindiğinde, Intune, AAD 'den silme sinyali alır ve bu kullanıcının tüm kişisel verilerini Intune hizmetinden temizlemeyi otomatik olarak başlatır. Kullanıcının bilgileri, kaldırma eyleminin 30 gün içinde Intune hizmetinden silinir.

> [!Important]
>Yeni hibrit MDM müşterilerinin eklenmesi kullanım dışı bırakılmıştır. Daha fazla bilgi için bkz. Azure blog gönderisine [karma mobil cihaz yönetiminden Intune 'A geçme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) .

## <a name="next-steps"></a>Sonraki adımlar

Intune 'da kişisel verileri [denetleme, dışarı aktarma veya silme](privacy-data-audit-export-delete.md) hakkında bilgi edinin.
