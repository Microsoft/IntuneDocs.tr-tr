---
title: Intune’da Şirket portalı kaydını bırakma
titlesuffix: Microsoft Intune
description: Şirket portalı bırakma raporu hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85a03718185de939612f5431a993f9f34c3048ba
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840663"
---
# <a name="company-portal-abandonment-report"></a>Şirket portalı bırakma raporu

Bu rapor, Şirket Portalı kaydının hangi aşamasında kullanıcıların kayıt sürecini bıraktığını gösterir.

Raporu görmek için **Intune** > **Cihaz kaydı** > **Şirket portalı bırakma** seçeneğini belirleyin.

Bu bırakma bilgilerini kullanarak, kullanıcıların kaydı tamamlamasına yardımcı olmak için ekleme belgelerinizi güncelleştirebilirsiniz. Örneğin çok sayıda kullanıcı Kullanım Koşulları ekranında kaydı bırakıyorsa bu alanı araştırıp kullanıcılar için kullanımı daha kolay bir hale getirebilirsiniz.

## <a name="what-is-abandonment"></a>Bırakma nedir?

Bırakma, kullanıcıların aşağıdakilerden birini yapmasıdır:

-   Kaydı durdurmak için açıkça bir eylem seçmesi
-   Kayıt sırasında Şirket Portalı’nı kapatması
-   Kayıt bölümleri arasında 30 dakikadan fazla zaman harcaması

Bir kullanıcı kaydı birçok kez durdurup yeniden başlatmayı seçerse bu, birden fazla girişim ve birden çok bırakma olarak görünür. Bir kullanıcı bir kayıt ekranında 30 dakika harcarsa bu, birden çok bırakma olarak kabul edilir.

## <a name="what-does-the-report-show"></a>Rapor neleri gösterir?

Kayıt raporları, iOS ve Android cihazlarına ait veriler içerir.

Raporlar, son iki haftanın verilerini gösterir ancak geçmiş 30 gün içerisindeki herhangi bir dönemi gösterecek şekilde filtrelenebilir.

**Filtre** seçeneği ile tarih aralığını, işletim sistemini ve kayıt bölümünü filtreleyebilirsiniz.

### <a name="number-and-percentage-tiles"></a>Sayı ve yüzde kutucukları

Raporun üst kısmında, tüm kayıtlar arasından bırakılan raporların sayısını ve yüzdesini görebilirsiniz.

-   Başlatılan kayıtları: Kayıtları denemesi sayısı.
-   Terk edilmiş kayıtları: İçinde tam olarak kayıtlı ve uyumlu bir cihaz dik denenen kayıtları sayısı.
-   Abandonment oranı: (Kayıtlar terk / kayıtları başlatılan) terk edilmiş kayıt girişimlerinin yüzdesi.

### <a name="line-graph"></a>Çizgi grafik

Çizgi grafik, dört temel kayıt bölümünün her biri için günlük bırakma sayısını gösterir:

-   Kurulum denetim listesi
-   Platform ekranları
-   Kullanım koşulları
-   Uyumluluk/Etkinleştirme

### <a name="user-abandonment-actions"></a>Kullanıcı bırakma eylemleri

Aşağıdaki tablolar, bırakma olarak değerlendirilen kullanıcı eylemlerini gösterir. Kayıt ekranı örnekleri görmek için [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) ve [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) kayıt videolarını izleyebilirsiniz. 


#### <a name="setup-checklist-section"></a>Kurulum denetim listesi bölümü

| Bırakma adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Sayfayı Şirket Portalı’nda açmaya yönelik istem | iOS/Android | **İptal** |
| EnrollmentWrapUp | **Şirket kaynakları yükleniyor** işlemi tamamlanana kadar gösterilen cihaz kaydetme ekranı | iOS/Android | 30 dakikadan fazla sürdü |
| DeviceCategory | **Bitti** düğmesine tıklanana kadar görüntülenen Cihaz Kategorisi seçimi (yönetici tarafından yapılandırılmışsa) | iOS/Android | 30 dakikadan fazla sürdü |
| PreEnrollmentWizard | Kaydı başlattıktan sonra Erişimi ayarlama ekranına dönüldüğünde gösterilen Erişimi ayarlama ekranı | iOS/Android| **Ertele** |
| PreEnrollmentWizard | **Sırada Ne Var** ekranında **Sonraki** düğmesine tıklanana kadar görüntülenen Erişimi ayarlama ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="platform-screens-section"></a>Platform ekranları bölümü

| Bırakma adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Bir yapılandırma profilini göstermeye yönelik istem | iOS | **Yoksay** |
| iOSProfileLaunch | Profili yükleme ekranı | iOS | **İptal** |
| iOSProfileLaunch | Profil kaynağının cihazı kaydetmesine güvenme istemi | iOS | **İptal** |
| iOSProfileLaunch | Profil yüklenene kadar görüntülenen profil yükleme ekranı | iOS | 30 dakikadan fazla sürdü |
| AndroidPermissions | Cihaz yöneticisi etkinleştirme ekranı | Android | **İptal** |
| AndroidPermissions | Cihaz yöneticisi için **Etkinleştir** düğmesine tıklanana kadar telefon çağrıları yapma ve bunları yönetmeye yönelik onay istemi | Android | 30 dakikadan fazla sürdü |
| KnoxActivation | KLMS aracısını etkinleştirme (yalnızca Samsung) | Android| **İptal** |
| KnoxActivation | **Onayla** düğmesine tıklanana kadar süren KLMS aracısını etkinleştirme işlemi | Android | 30 dakikadan fazla sürdü|

#### <a name="terms-of-use-section"></a>Kullanım koşulları bölümü

| Bırakma adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| TermsofUse | Kullanım koşulları (yönetici yapılandırmışsa) | iOS/Android | **Tümünü Reddet** |
| TermsofUse | **Tümünü kabul et** seçeneği belirtilene kadar gösterilen Kullanım koşulları ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="complianceactivation-section"></a>Uyumluluk/Etkinleştirme bölümü

| Bırakma adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| Uyumluluk | Cihaz uyumluluğu (yönetici yapılandırmışsa), kayıt sonrası erişim kurulumunda yeşil dışındaki bir renkte gösterilir| iOS/Android | **Ertele** |
| Uyumluluk | Cihaz uyumluluğu, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |
| Etkinleştirme | Kayıt etkinleştirme (yönetici yapılandırmışsa), erişim kurulumunda yeşil dışındaki bir renkte gösterilir | iOS/Android | **Ertele** |
| Uyumluluk | Cihaz etkinleştirme, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |

## <a name="next-steps"></a>Sonraki adımlar

Bırakma oranlarınızı denetledikten sonra kaydı geliştirmek için herhangi bir değişiklik yapıp yapamayacağınızı görmek için [kayıt seçeneklerine](enrollment-options.md) göz atabilirsiniz.
