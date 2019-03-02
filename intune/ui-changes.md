---
title: Azure'daki Intune özelliğim nereye gitti?
titleSuffix: Microsoft Intune
description: Azure portalında Microsoft Intune özelliklerini bulmanıza yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 1/4/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 442eca614f1f9bbdce0b88bb068bfc1dceb69c1c
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234939"
---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Azure'daki Intune özelliğim nereye gitti?
Intune'u Azure portalına taşırken bazı görevleri daha mantıklı bir şekilde organize ettik. Ancak her geliştirme sonrasında atlatılması gereken bir yeni düzene alışma süreci vardır. Bu başvuru kılavuzu, klasik portalda Intune’a aşina olanlar ve bir işlemi Azure portalında Intune’da nasıl gerçekleştireceğini merak edenler için hazırlanmıştır. Aradığınız özellik bu makalede yoksa , güncelleştirebilmemiz için makalenin sonuna yorumlarınızı yazın.
## <a name="quick-reference-guide"></a>Hızlı başvuru kılavuzu

|Özellik |Klasik portalda yol|Azure portalında Intune’da yol|
|------------|---------------|---------------|
|Aygıt Kayıt Programı (DEP) [yalnızca iOS]|Yönetici > Mobil Cihaz Yönetimi > iOS > Aygıt Kayıt Programı|[Cihaz kaydı > Apple Kaydı > Kayıt Programı Belirteci](#where-did-apple-dep-go) |
|Aygıt Kayıt Programı (DEP) [yalnızca iOS]| Yönetici > Mobil Cihaz Yönetimi > iOS ve Mac OS X > Aygıt Kayıt Programı |[Cihaz kaydı > Apple Kaydı > Kayıt Programı Seri Numaraları](#where-did-apple-dep-go) |
|Kayıt Kuralları |Yönetici > Mobil Cihaz Yönetimi > Kayıt Kuralları|[Cihaz kaydı > Kayıt Kısıtlamaları](#where-did-enrollment-rules-go) |
|iOS Seri Numarasına göre gruplar |Gruplar > Tüm Cihazlar > Ön Kayıtlı Şirket cihazları > iOS Seri Numarasına Göre|[Cihaz kaydı > Apple Kaydı > Kayıt Programı Seri Numaraları](#where-did-corporate-pre-enrolled-devices-go) |
|iOS Seri Numarasına göre gruplar |Gruplar > Tüm Cihazlar > Ön Kayıtlı Şirket cihazları > iOS Seri Numarasına Göre| [Cihaz kaydı > Apple Kaydı > AC Seri numaraları](#where-did-corporate-pre-enrolled-devices-go)|
|IMEI'ye göre gruplar (tüm platformlar)| Gruplar > Tüm Cihazlar > Ön Kayıtlı Şirket cihazları > IMEI'ye göre (Tüm platformlar) | [Cihaz kaydı > Şirket Cihaz Kaydı Tanımlayıcıları](#by-imei-all-platforms)|
| Şirket Cihaz Kaydı profili| İlke > Şirket Cihaz Kaydı | [Cihaz kaydı > Apple kaydı > Kayıt Programı Profilleri](#where-did-corporate-pre-enrolled-devices-go) |
| Şirket Cihaz Kaydı profili | İlke > Şirket Cihaz Kaydı | [Cihaz kaydı > Apple Kaydı > AC Profilleri](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Yönetici > Mobil Cihaz Yönetimi > Android for Work | Cihaz kaydı > Android kaydı |
| Hüküm ve Koşullar | İlke > Hüküm ve Koşullar | Cihaz kaydı > Hüküm ve Koşullar |
Şirket Portalı ayarları|Yönetici > Şirket Portalı|**Yönet** > Mobil uygulamalar<br> **Kurulum** > Şirket Portalı markalama


## <a name="where-do-i-manage-groups"></a>Grupları nereden yönetebilirim?
Azure portalında Intune’da grupları yönetmek için [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) kullanılır.

## <a name="where-did-enrollment-rules-go"></a>Kayıt kuralları nereye gitti?
Klasik portalda, mobil ve modern Windows ve macOS cihazlarının MDM kaydını yöneten kurallar belirleme imkanına sahiptiniz.

![Klasik mobil cihaz kayıt kuralları görüntüsü](./media/01-classic-rules.png)

Bu kurallar, özel durum olmadan Intune hesabınızdaki tüm kullanıcılar için geçerli oluyordu. Azure portalında bu kurallar iki farklı ilke türü artık görünür: Cihaz türü kısıtlamaları ve cihaz sınırı kısıtlamaları.

![Azure mobil cihaz kaydı kısıtlamalarının görüntüsü](./media/02-azure-enroll-restrictions.png)

Varsayılan Cihaz Sınırı Kısıtlaması, klasik portaldaki Cihaz Kaydı Sınırına karşılık gelmektedir.

![Azure cihaz sınırı kısıtlamalarının görüntüsü](./media/03-azure-device-limit.png)

Varsayılan Cihaz Türü Kısıtlaması, klasik portaldaki Platform Kısıtlamalarına karşılık gelmektedir.

![Azure cihaz türü kısıtlamalarının görüntüsü](./media/04-azure-platform-restrictions.png)

Kişisel cihazlara izin verme veya bu cihazları engelleme özelliği artık Cihaz Türü Kısıtlamasının Platform Yapılandırmaları bölümünde yönetilmektedir.

![Azure kişisel cihaz engelleme ayarlarının görüntüsü](./media/05-azure-personal-block.png)

Yeni kısıtlama özellikleri yalnızca Azure Portal'a eklenir.

## <a name="where-did-my-conditional-access-policies-go"></a>Koşullu erişim ilkelerim nereye gitti?
Kiracınız Azure portalına geçtikten sonra kiracınızın koşullu erişim ilkeleri uygulanmaya devam eder. Ancak bunları Azure portalında Intune’da görüntüleyemez veya değiştiremezsiniz.

Koşullu erişim ilkelerini görüntülemek ve ilkeler üzerinde değişiklik yapmak için Azure portalını kullanmak isterseniz klasik portaldan eski ilkeleri kaldırmanız gerekir. Daha sonra bunları Azure portalında yeniden oluşturmalısınız. Koşullu erişim ilkelerini geçirme hakkında daha fazla bilgi için bkz. [Azure Portal’da klasik ilkeleri geçirme](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration). 

## <a name="where-did-my-compliance-policies-go"></a>Uyumluluk ilkelerim nereye gitti?
Kiracınız Azure portalına geçtikten sonra kiracınızın uyumluluk ilkeleri uygulanmaya devam eder. Ancak bunları Azure portalında Intune’da görüntüleyemez veya değiştiremezsiniz.

Uyumluluk ilkelerini görüntülemek ve ilkeler üzerinde değişiklik yapmak için Azure portalını kullanmak isterseniz klasik portaldan eski ilkeleri kaldırmanız gerekir. Daha sonra bunları Azure portalında yeniden oluşturmalısınız. Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz. [Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama](https://docs.microsoft.com/intune/known-issues#compliance). 

## <a name="where-did-apple-dep-go"></a>Apple DEP nereye gitti?
Klasik portalda Intune’u Apple’ın Aygıt Kayıt Programı ile tümleştirebiliyor ve Apple’ın hizmetiyle el ile eşitleme isteğinde bulunuyordunuz:

![Klasik DEP belirtecinin görüntüsü](./media/06-classic-dep-token.png)

Azure portalında Apple Cihaz Kayıt Programı kurulumunu Intune klasik ile aynı adımları kullanarak gerçekleştirirsiniz:

![Azure DEP belirtecinin görüntüsü](./media/07-azure-dep-token.png)

Ancak klasik portaldaki **Eşitle** seçeneği, el ile yapılan eşitleme sonuçlarının görüneceği seri numarası yönetimi iş akışına taşındı:

![Azure DEP eşitleme görüntüsü](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Kurumsal ön kayıtlı cihazlar nereye gitti?
### <a name="by-ios-serial-number"></a>iOS seri numarasına göre
Klasik portalda Apple Aygıt Kayıt Programı (DEP) ve Apple Configurator aracıyla iOS cihazlarını kaydedebilirsiniz. İki yöntemde de cihazların seri numarasına göre ön kayıt yapıyor ve özel Kurumsal Cihaz Kayıt profilleri atıyordunuz. Kayıt işleminden önce kayıt profili atama işlemi **iOS Seri Numarasına Göre Kurumsal Ön Kayıtlı Cihazlar** cihaz grubundan yönetilebilir:

![Klasik Apple seri numaralarının görüntüsü](./media/09-classic-apple-serials.png)

Bu listede hem Apple DEP hem de Configurator kayıtları bir arada görüntülenir. Profil ataması uyuşmazlığını (DEP profili ile AC seri numarası arası) azaltmak için Azure portalında seri numaraları iki liste haline getirdik:

**DEP seri numaraları**
![Azure DEP seri numaralarının görüntüsü](./media/10-azure-dep-serials.png)

**Apple Configurator seri numaraları**
![Azure Apple Configurator seri numaralarının görüntüsü](./media/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>IMEI'ye göre (tüm platformlar)

Klasik portalda cihazların IMEI numaralarını önceden listeleyerek cihazlar Intune’a kaydolduklarında bunları kuruluş cihazı olarak işaretleyebilirsiniz:

![Klasik IMEI numarası listesinin görüntüsü](./media/12-classic-corp-imei.png)

Azure portalında aynı IMEI ile Kurumsal Cihaz Tanımlayıcıları listesini virgülle ayrılmış değerler (CSV) dosyası olarak yüklemeniz gerekir. Yeni portalda IMEI numaralarının el ile girişi desteklenmez:

![Azure IMEI numarası listesinin görüntüsü](./media/13-azure-corp-imei.png)

Azure portalındaki Intune, gelecekte ortaya çıkabilecek IMEI haricindeki tanımlayıcı türlerini destekleyecek şekilde tasarlanmıştır ancak şu an için yalnızca IMEI numaralarının listelenmesine izin verilmektedir.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Kurumsal Cihaz Kayıt profilleri nereye gitti?
iOS cihazlarını Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla kaydetmek için cihaza atanacak bir Kurumsal Cihaz Kayıt profili sağlamanız gerekir. Klasik portalda bu profillerin oluşturulması ve yönetilmesi tek bir listeden yapılıyordu:

![Klasik cihaz kayıt profillerinin görüntüsü](./media/14-classic-corp-profiles.png)

Bu listede Apple Cihaz Kayıt Programı (**DEP Açık**) ile kullanılabilecek profillerin yanı sıra yalnızca Apple Configurator aracıyla (**DEP Kapalı**) kullanılabilecek profiller gösterilmektedir.

İki profil türü arasındaki karışıklıkları ve olası yanlış eşlenmiş atamaları (DEP profili yerine Configurator cihazları ve tersi) azaltmak için Kayıt Programı profillerinin (hem Apple Cihaz Kayıt Programını hem de Apple Okul Yöneticisi'ni destekleyen) oluşturma ve yönetim adımlarıyla Apple Configurator profillerininkini ayırdık:

**DEP profilleri**
![Azure DEP profillerinin görüntüsü](./media/15-azure-dep-profiles.png)

**Apple Configurator profilleri**
![Azure Apple Configurator profillerinin görüntüsü](./media/16-azure-ac-profiles.png)
