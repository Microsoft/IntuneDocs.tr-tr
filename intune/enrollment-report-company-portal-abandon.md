---
title: Intune'da tamamlanmamış kullanıcı kayıtları raporu
titlesuffix: Microsoft Intune
description: Eksik kullanıcı kayıtları raporu hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0202fba7e31b7be1d325617867be9a43d4f2064a
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57400237"
---
# <a name="incomplete-user-enrollments-report"></a>Eksik kullanıcı kayıtları raporu

Bu rapor, burada şirket Portalı'nda kayıt işlemini kullanıcılar kayıt işlemini tamamlıyorsanız değil bildirir.

Raporu görmek için seçin **Intune** > **cihaz kaydı** > **eksik kullanıcı kayıtları**.

Bu bilgileri kullanarak, kullanıcı kaydı tamamlamak amacıyla ekleme belgelerinizi güncelleştirebilirsiniz. Örneğin çok sayıda kullanıcı Kullanım Koşulları ekranında kaydı bırakıyorsa bu alanı araştırıp kullanıcılar için kullanımı daha kolay bir hale getirebilirsiniz.

## <a name="what-is-an-incomplete-enrollment"></a>Tamamlanmamış bir kaydı nedir?

Bir kullanıcı aşağıdakilerden herhangi birini yaptığında, eksik bir kayıt şöyledir:

-   Kaydı durdurmak için açıkça bir eylem seçmesi
-   Kayıt sırasında Şirket Portalı’nı kapatması
-   Kayıt bölümleri arasında 30 dakikadan fazla zaman harcaması

Bir kullanıcı kaydı durdurmak ve birden çok kez yeniden başlatılması seçerse, birden fazla girişimde ve birden fazla tamamlanmamış kayıtları gösterilir. Bir kullanıcı farklı kayıt ekranlar arasında 30 dakika bekler, birden fazla tamamlanmamış kayıtları olarak kabul edilir.

## <a name="what-does-the-report-show"></a>Rapor neleri gösterir?

Raporlar, iOS ve Android cihazlar için veri içerir.

Raporlar, son iki haftanın verilerini gösterir ancak geçmiş 30 gün içerisindeki herhangi bir dönemi gösterecek şekilde filtrelenebilir.

**Filtre** seçeneği ile tarih aralığını, işletim sistemini ve kayıt bölümünü filtreleyebilirsiniz.

### <a name="number-and-percentage-tiles"></a>Sayı ve yüzde kutucukları

Raporun üstündeki sayısı ve yüzdesi ile ilgili olarak tüm kayıtları tamamlanmamış kayıtları görebilirsiniz.

-   Başlatılan kayıtları: Kayıtları denemesi sayısı.
-   Tamamlanmamış kayıtları: İçinde tam olarak kayıtlı ve uyumlu bir cihaz dik denenen kayıtları sayısı.
-   Tamamlanmamış oranı: (Kayıtlar terk / kayıtları başlatılan) terk edilmiş kayıt girişimlerinin yüzdesi.

### <a name="line-graph"></a>Çizgi grafik

Çizgi grafiği için dört temel kayıt bölümlerin her birinde günlük tamamlanmamış kayıtları gösterir:

-   Kurulum denetim listesi
-   Platform ekranları
-   Kullanım koşulları
-   Uyumluluk/Etkinleştirme

### <a name="user-abandonment-actions"></a>Kullanıcı bırakma eylemleri

Aşağıdaki tablolar, bir eksik kayıt istemi olarak uygun kullanıcı eylemlerinin listesini gösterir. Kayıt ekranı örnekleri görmek için [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) ve [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) kayıt videolarını izleyebilirsiniz. 


#### <a name="setup-checklist-section"></a>Kurulum denetim listesi bölümü

| Eylem adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Sayfayı Şirket Portalı’nda açmaya yönelik istem | iOS/Android | **İptal** |
| EnrollmentWrapUp | **Şirket kaynakları yükleniyor** işlemi tamamlanana kadar gösterilen cihaz kaydetme ekranı | iOS/Android | 30 dakikadan fazla sürdü |
| DeviceCategory | **Bitti** düğmesine tıklanana kadar görüntülenen Cihaz Kategorisi seçimi (yönetici tarafından yapılandırılmışsa) | iOS/Android | 30 dakikadan fazla sürdü |
| PreEnrollmentWizard | Kaydı başlattıktan sonra Erişimi ayarlama ekranına dönüldüğünde gösterilen Erişimi ayarlama ekranı | iOS/Android| **Ertele** |
| PreEnrollmentWizard | **Sırada Ne Var** ekranında **Sonraki** düğmesine tıklanana kadar görüntülenen Erişimi ayarlama ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="platform-screens-section"></a>Platform ekranları bölümü

| Eylem adı | Ekran veya akış | Platform | Eylem |
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

| Eylem adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| TermsofUse | Kullanım koşulları (yönetici yapılandırmışsa) | iOS/Android | **Tümünü Reddet** |
| TermsofUse | **Tümünü kabul et** seçeneği belirtilene kadar gösterilen Kullanım koşulları ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="complianceactivation-section"></a>Uyumluluk/Etkinleştirme bölümü

| Eylem adı | Ekran veya akış | Platform | Eylem |
| ---- |---- |---- |---- |
| Uyumluluk | Cihaz uyumluluğu (yönetici yapılandırmışsa), kayıt sonrası erişim kurulumunda yeşil dışındaki bir renkte gösterilir| iOS/Android | **Ertele** |
| Uyumluluk | Cihaz uyumluluğu, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |
| Etkinleştirme | Kayıt etkinleştirme (yönetici yapılandırmışsa), erişim kurulumunda yeşil dışındaki bir renkte gösterilir | iOS/Android | **Ertele** |
| Uyumluluk | Cihaz etkinleştirme, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |

## <a name="next-steps"></a>Sonraki adımlar

Eksik kayıt ücretlerinizi denetledikten sonra gözden geçirebileceğiniz [kayıt seçenekleri](enrollment-options.md) kayıt geliştirmek için herhangi bir değişiklik yapmadan, görmek için.
