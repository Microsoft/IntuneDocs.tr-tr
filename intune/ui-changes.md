---
title: "Azure'daki Intune özelliğim nereye gitti?"
titlesuffix: Azure portal
description: "Azure portalında Intune özellikleri bulmanıza yardımcı olur.”"
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41b358f48412585ec40e369225b4263012bfd2f8
ms.sourcegitcommit: b8987b8dfb009ea55678d7f640ac5f18a6ab167e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2017
---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Azure'daki Intune özelliğim nereye gitti?
Intune'u Azure portalına taşırken bazı görevleri daha mantıklı bir şekilde organize ettik. Ancak her geliştirme sonrasında atlatılması gereken bir yeni düzene alışma süreci vardır. Bu nedenle klasik portalda Intune’a aşina olanlar ve bir işlemi Azure portalında Intune’da nasıl gerçekleştireceğini merak edenler için bu başvuru kılavuzunu hazırladık. Aradığınız özellik bu makalede yoksa ekleyebilmemiz için lütfen aşağıya yorum yazın.
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
| Android for Work | Yönetici > Mobil Cihaz Yönetimi > Android for Work | Cihaz kaydı > Android for Work Kaydı |
| Hüküm ve Koşullar | İlke > Hüküm ve Koşullar | Cihaz kaydı > Hüküm ve Koşullar |


## <a name="where-do-i-manage-groups"></a>Grupları nereden yönetebilirim?
Azure portalında Intune’da grupları yönetmek için [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) kullanılır.

## <a name="where-did-enrollment-rules-go"></a>Kayıt kuralları nereye gitti?
Klasik portalda mobil ve modern Windows ve macOS cihazlarının MDM kaydını yöneten kurallar belirleme imkanına sahiptiniz:

![Klasik mobil cihaz kayıt kuralları görüntüsü](./media/01-classic-rules.png)

Bu kurallar, özel durum olmadan Intune hesabınızdaki tüm kullanıcılar için geçerli oluyordu. Azure portalında bu kurallar iki farklı ilke türü altında listeleniyor: Cihaz Türü Kısıtlamaları ve Cihaz Sınırı Kısıtlamaları:

![Azure mobil cihaz kaydı kısıtlamalarının görüntüsü](./media/02-azure-enroll-restrictions.png)

Varsayılan Cihaz Sınırı Kısıtlaması, klasik portaldaki Cihaz Kaydı Sınırına karşılık gelmektedir:

![Azure cihaz sınırı kısıtlamalarının görüntüsü](./media/03-azure-device-limit.png)

Varsayılan Cihaz Türü Kısıtlaması, klasik portaldaki Platform Kısıtlamalarına karşılık gelmektedir:

![Azure cihaz türü kısıtlamalarının görüntüsü](./media/04-azure-platform-restrictions.png)

Kişisel cihazlara izin verme veya bu cihazları engelleme özelliği artık Cihaz Türü Kısıtlamasının Platform Yapılandırmaları bölümünde yönetilmektedir:

![Azure kişisel cihaz engelleme ayarlarının görüntüsü](./media/05-azure-personal-block.png)

Yeni kısıtlama özellikleri yalnızca Azure Portalına eklenecektir.

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
