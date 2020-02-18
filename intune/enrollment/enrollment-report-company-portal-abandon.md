---
title: Intune 'da tamamlanmamış Kullanıcı kayıtları raporu
titleSuffix: Microsoft Intune
description: Tamamlanmamış Kullanıcı kayıtları raporu hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7861d26650aaf74ea9c58608c33e72495244575
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414219"
---
# <a name="incomplete-user-enrollments-report"></a>Tamamlanmamış Kullanıcı kayıtları raporu

Bu rapor, Şirket Portalı kayıt işlemi kullanıcılarının kayıt işlemini tamamlamada nerede olduğunu söyler.

Raporu görmek için **ıntune** > **cihaz kaydı** > **tamamlanmamış Kullanıcı**kayıtları ' nı seçin.

Bu bilgileri kullanarak, kullanıcıların kaydı tamamlamasını sağlamak için ekleme belgelerinizi güncelleştirebilirsiniz. Örneğin çok sayıda kullanıcı Kullanım Koşulları ekranında kaydı bırakıyorsa bu alanı araştırıp kullanıcılar için kullanımı daha kolay bir hale getirebilirsiniz.

## <a name="what-is-an-incomplete-enrollment"></a>Tamamlanmamış kayıt nedir?

Tamamlanmamış bir kayıt, bir kullanıcı aşağıdakilerden birini yapar:

- Kaydı durdurmak için açıkça bir eylem seçmesi
- Kayıt sırasında Şirket Portalı’nı kapatması
- Kayıt bölümleri arasında 30 dakikadan fazla zaman harcaması

Bir kullanıcı kaydı durdurmayı ve birden çok kez yeniden başlatmayı seçerse, birden çok deneme ve birden çok tamamlanmamış kayıt olarak gösterilir. Kullanıcı farklı kayıt ekranları arasında 30 dakika bekliyorsa, bu birden fazla tamamlanmamış kayıt olarak kabul edilir.

## <a name="what-does-the-report-show"></a>Rapor neleri gösterir?

Raporlar iOS/ıpados ve Android cihazlara yönelik verileri içerir.

Raporlar, son iki haftanın verilerini gösterir ancak geçmiş 30 gün içerisindeki herhangi bir dönemi gösterecek şekilde filtrelenebilir.

**Filtre** seçeneği ile tarih aralığını, işletim sistemini ve kayıt bölümünü filtreleyebilirsiniz.

### <a name="number-and-percentage-tiles"></a>Sayı ve yüzde kutucukları

Raporun en üstünde, tamamlanmamış kayıtları tüm kayıtlar ' da olduğu gibi, eksik kayıtların sayısını ve yüzdesini görebilirsiniz.

- Başlatılan kayıtlar: Toplam kayıt denemesi sayısı.
- Tamamlanmamış kayıtlar: tam kayıtlı ve uyumlu bir cihazla sonuçlanmayan denenen kayıt sayısı.
- Tamamlanmamış hız: bırakılan kayıt denemelerinin yüzdesi (bırakılan kayıtlar/başlatılan kayıtlar).

### <a name="line-graph"></a>Çizgi grafik

Çizgi grafiğinde dört çekirdekli kayıt bölümlerinin her biri için günlük tamamlanmamış kayıtlar gösterilmektedir:

- Kurulum denetim listesi
- Platform ekranları
- Kullanım koşulları
- Uyumluluk/Etkinleştirme

### <a name="user-abandonment-actions"></a>Kullanıcı bırakma eylemleri

Aşağıdaki tablolarda, tamamlanmamış bir kayıt isteminde bulunarak nitelendiği Kullanıcı eylemlerinin listesi gösterilmektedir. Kayıt ekranı örnekleri görmek için [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) ve [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) kayıt videolarını izleyebilirsiniz. 


#### <a name="setup-checklist-section"></a>Kurulum denetim listesi bölümü

| Eylem adı | Ekran veya akış | Platfveyam | Eylem |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Sayfayı Şirket Portalı’nda açmaya yönelik istem | iOS/Android | **İptal** |
| EnrollmentWrapUp | **Şirket kaynakları yükleniyor** işlemi tamamlanana kadar gösterilen cihaz kaydetme ekranı | iOS/Android | 30 dakikadan fazla sürdü |
| DeviceCategory | **Bitti** düğmesine tıklanana kadar görüntülenen Cihaz Kategorisi seçimi (yönetici tarafından yapılandırılmışsa) | iOS/Android | 30 dakikadan fazla sürdü |
| PreEnrollmentWizard | Kaydı başlattıktan sonra Erişimi ayarlama ekranına dönüldüğünde gösterilen Erişimi ayarlama ekranı | iOS/Android| **Ertele** |
| PreEnrollmentWizard | **Sırada Ne Var** ekranında **Sonraki** düğmesine tıklanana kadar görüntülenen Erişimi ayarlama ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="platform-screens-section"></a>Platform ekranları bölümü

| Eylem adı | Ekran veya akış | Platfveyam | Eylem |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Bir yapılandırma profilini göstermeye yönelik istem | iOS/ıpados | **Yoksay** |
| iOSProfileLaunch | Profili yükleme ekranı | iOS/ıpados | **İptal** |
| iOSProfileLaunch | Profil kaynağının cihazı kaydetmesine güvenme istemi | iOS/ıpados | **İptal** |
| iOSProfileLaunch | Profil yüklenene kadar görüntülenen profil yükleme ekranı | iOS/ıpados | 30 dakikadan fazla sürdü |
| AndroidPermissions | Cihaz yöneticisi etkinleştirme ekranı | Android | **İptal** |
| AndroidPermissions | Cihaz yöneticisi için **Etkinleştir** düğmesine tıklanana kadar telefon çağrıları yapma ve bunları yönetmeye yönelik onay istemi | Android | 30 dakikadan fazla sürdü |
| KnoxActivation | KLMS aracısını etkinleştirme (yalnızca Samsung) | Android| **İptal** |
| KnoxActivation | **Onayla** düğmesine tıklanana kadar süren KLMS aracısını etkinleştirme işlemi | Android | 30 dakikadan fazla sürdü|

#### <a name="terms-of-use-section"></a>Kullanım koşulları bölümü

| Eylem adı | Ekran veya akış | Platfveyam | Eylem |
| ---- |---- |---- |---- |
| TermsofUse | Kullanım koşulları (yönetici yapılandırmışsa) | iOS/Android | **Tümünü Reddet** |
| TermsofUse | **Tümünü kabul et** seçeneği belirtilene kadar gösterilen Kullanım koşulları ekranı | iOS/Android | 30 dakikadan fazla sürdü |

#### <a name="complianceactivation-section"></a>Uyumluluk/Etkinleştirme bölümü

| Eylem adı | Ekran veya akış | Platfveyam | Eylem |
| ---- |---- |---- |---- |
| Uyumluluk | Cihaz uyumluluğu (yönetici yapılandırmışsa), kayıt sonrası erişim kurulumunda yeşil dışındaki bir renkte gösterilir| iOS/Android | **Ertele** |
| Uyumluluk | Cihaz uyumluluğu, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |
| Etkinleştirme | Kayıt etkinleştirme (yönetici yapılandırmışsa), erişim kurulumunda yeşil dışındaki bir renkte gösterilir | iOS/Android | **Ertele** |
| Uyumluluk | Cihaz etkinleştirme, yeşil görünecek şekilde güncelleştirilene kadar yeşil dışındaki bir renkte gösterilir | iOS/Android | 30 dakikadan fazla sürdü |

## <a name="next-steps"></a>Sonraki adımlar

Tamamlanmamış kayıt hızlarınızı denetledikten sonra, kaydı geliştirmek için herhangi bir değişiklik yapıp yapabileceğinizi görmek için [kayıt seçeneklerini](enrollment-options.md) gözden geçirebilirsiniz.
