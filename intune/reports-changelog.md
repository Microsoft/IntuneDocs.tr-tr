---
title: Intune Veri Ambarı Değişiklik günlüğü
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki değişikliklerin bir listesi.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dd9fb36bb1b8c5e66d104f530690c5d236ea25e4
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune Veri Ambarı API’si için değişiklik günlüğü

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune Veri Ambarı hakkında güncel bilgiler edinin.

## <a name="1805"></a>1805
_Yayımlanma Tarihi Mayıs 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>**Cihazlar** koleksiyonundaki cihaz sayısında düzeltme 

**Cihazlar** koleksiyonunda, `isDeleted` özniteliğine göre filtreleme yapan cihazların toplam sayısını azaltma ihtimali olan bir düzeltme yapıldı. Bu azalma, düzeltmenin sonucu olarak ortaya çıkar ve bir hata değildir. **Cihazlar** koleksiyonu hakkında daha fazla bilgi için bkz. [Cihaz varlıkları için başvuru](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Ocak 2018’de yayımlandı_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama <!-- 1867540 -->

Azure Active Directory (Azure AD) kullanarak bir uygulamayı ayarlayabilir ve Intune Veri Ambarı’nda kimlik doğrulayabilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri <!-- 2077525 -->

- Intune Veri Ambarı’na (API dahil) erişirken, bir Intune lisansının kullanıcıya atanması artık gerekli değildir.
- Intune rol adı, **Raporlar** yerine **Intune veri ambarı** olarak değiştirildi. 

    Daha fazla bilgi için bkz. [Azure AD ve Intune kimlik bilgisi gereksinimleri](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>OData sorgu seçenekleri <!-- 2077711 -->

<code>$select</code> öğesini OData sorgu parametresi olarak kullanabilirsiniz. Mevcut sürüm, aşağıdaki OData sorgu parametrelerini destekler: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> ve <code>$top</code>. Daha fazla bilgi için bkz. [OData sorgu seçenekleri](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Veri Ambarı veri modelinde yeni varlıklar <!-- 2077804 -->

 - [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md#mobileappdeviceuserinstallstatus) varlığı eklendi. **MobileAppDeviceUserInstallStatus** belirli bir cihaz ve kullanıcı için mobil uygulama yükleme durumunu gösterir.
 - [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate) varlığı eklendi. **MobileAppInstallState** varlığı, bir mobil uygulamanın cihazlar, kullanıcılar veya her ikisini de içeren bir gruba atandıktan sonra yükleme durumunu gösterir. 

## <a name="1710"></a>1710
_Yayımlanma tarihi: Kasım 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verisi ile sınırlıdır <!-- 1544273 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Yayınlanma tarihi: Ekim 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune Veri Ambarı veri modeline kullanıcı cihaz ilişkisi varlığı eklendi <!-- 1187917 -->

Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı Cihaz İlişkisi](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Veri Ambarı veri modelinde yeni varlıklar <!-- 1479526 --><!-- -->

 - [**UserDeviceAssociation**](reports-ref-user-device.md) varlığı eklendi. **UserDeviceAssociation**, kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir. Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz.  
 - [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) varlığı eklendi. **IntuneManagementExtension**, mobil cihazlar için sürüm veya yükleme durumu gibi bilgileri izleyen varlıklar barındırır.

## <a name="next-steps"></a>Sonraki adımlar
 - [Intune’daki haftalık yenilikleri](whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.
 - [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.
