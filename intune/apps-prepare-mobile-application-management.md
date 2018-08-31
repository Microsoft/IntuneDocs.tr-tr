---
title: Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme
description: Bu konu başlığı altındaki bilgiler, özel iş kolu uygulamalarınızın mobil uygulama yönetimi ilkelerini kullanabilmesini sağlamak için, Uygulama sarmalama aracını ve Uygulama SDK'sını ne zaman kullanmanız gerektiğine karar vermenize yardımcı olur.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 07/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d4dbdb3aa07020aa027dc1a4a1b2edcefefb4ca
ms.sourcegitcommit: 77ed48ab52b55e92ceaa89e9edf53b892fc62adb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2018
ms.locfileid: "40251505"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>İş kolu uygulamalarını uygulama koruma ilkelerine hazırlama

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune Uygulaması Sarmalama Aracı’nı veya Intune Uygulama SDK’sını kullanarak uygulamalarınızın uygulama koruma ilkeleri kullanmasını sağlayabilirsiniz. Bu iki yöntem ve ne zaman kullanılacakları hakkında bilgi edinmek için bu bilgileri kullanın.

## <a name="intune-app-wrapping-tool"></a>Intune Uygulaması Sarmalama Aracı
Uygulama Sarmalama Aracı öncelikle **iç** iş kolu (LOB) uygulamaları için kullanılır. Araç, uygulamanın çevresinde bir sarmalayıcı oluşturan ve sonra uygulamanın bir Intune uygulama koruma ilkesiyle yönetilmesine izin veren bir komut satırı uygulamasıdır. Bağımsız yazılım satıcısı (ISV) tarafından sağlanan bir uygulamayı korurken, ISV'nin sarmalanmış uygulamayı yine de destekleyip desteklemeyeceğini netleştirmek önemlidir.

Aracı kullanmak için kaynak kodu gerekli değildir, ancak imzalama kimlik bilgileri gereklidir. İmzalama kimlik bilgileri hakkında daha fazla bilgi için bkz. [Intune blogu](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Uygulama Sarmalama Aracı belgeleri için bkz. [Android Uygulaması Sarmalama Aracı](app-wrapper-prepare-android.md) ve [iOS Uygulaması Sarmalama Aracı](app-wrapper-prepare-ios.md).

Uygulama Sarmalama Aracı, Apple App Store veya Google Play Store'daki uygulamaları **desteklemez**. Ayrıca geliştirici tümleştirmesi gerektiren bazı özellikler için de destek sunmaz (aşağıdaki özellik karşılaştırma tablosuna bakın).

Intune’a kayıtlı olmayan cihazlarda uygulama koruma ilkeleri uygulamak için kullanılan Uygulama Sarmalama Aracı hakkında daha fazla bilgi için bkz. [Microsoft Intune’a kayıtlı olmayan cihazlarda iş kolu uygulamaları ve verilerini koruma](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracı kullanma nedenleri
* Uygulamanız yerleşik veri koruma özelliklerine sahip değil
* Uygulamanız basit
* Uygulamanız dahili olarak dağıtılmış
* Uygulamanın kaynak koduna erişiminiz yok
* Uygulamayı siz geliştirmediniz
* Uygulamanızda en düşük kullanıcı kimlik doğrulama deneyimleri bulunuyor

### <a name="supported-app-development-platforms"></a>Desteklenen uygulama geliştirme platformları

|**Uygulama Sarmalama Aracı** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Evet|Evet|
|**Android**|Hayır - [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Evet|

## <a name="intune-app-sdk"></a>Intune Uygulama SDK'sı
Uygulama SDK'sı temel olarak App Store veya Google Play Store’da uygulamaları olan ve uygulamaları Intune ile yönetebilmek isteyen müşteriler için tasarlanmıştır. Ancak, bir iş kolu uygulaması olsa bile SDK’yı tümleştirme özelliğinden her uygulama yararlanabilir.

SDK hakkında daha fazla bilgi edinmek için bkz. [Genel bakış](app-sdk.md). SDK’yı kullanmaya başlamak için bkz. [Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama](app-sdk-get-started.md).

### <a name="reasons-to-use-the-sdk"></a>SDK kullanma nedenleri
* Uygulamanız yerleşik veri koruma özelliklerine sahip değil
* Uygulamanız karmaşık ve birçok deneyim içeriyor
* Uygulamanız Google Play veya Apple App Store gibi genel bir uygulama mağazasında dağıtılmış
* Bir uygulama geliştiricisisiniz ve SDK kullanabilecek teknik bilgiye sahipsiniz
* Uygulamanız diğer SDK tümleştirmelerine sahip
* Uygulamanız sıklıkla güncelleştiriliyor

### <a name="supported-app-development-platforms"></a>Desteklenen uygulama geliştirme platformları

|**Intune Uygulama SDK'sı** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Evet – [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Hayır|
|**Android**| Evet - [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Hayır|

## <a name="feature-comparison"></a>Özellik karşılaştırması
Bu tabloda Uygulama SDK'si ve Uygulama Sarmalama Aracı için kullanabileceğiniz ayarlar listelenmektedir.

> [!NOTE]
> Uygulama Sarmalama Aracı, tek başına Intune veya Configuration Manager ile Intune ile kullanılabilir.

|Özellik|Uygulama SDK'sı|Uygulama Sarmalama Aracı|
|-----------|---------------------|-----------|
|Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın|X|X|
|Android, iTunes veya iCloud yedeklemelerini engelle|X|X|
|Uygulamanın diğer uygulamalara veri aktarmasına izin ver|X|X|
|Uygulamanın diğer uygulamalardan veri almasına izin ver|X|X|
|Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla|X|X|
|Erişim için basit PIN gerektir|X|X|
|Intune PIN ile yerleşik uygulama PIN kodunu değiştir|X||
|PIN sıfırlanmadan önceki deneme sayısını belirtin|X|X|
|PIN yerine parmak izine izin ver|X|X|
|PIN yerine yüz tanımaya izin ver (yalnızca iOS)|X|X|
|Erişim için kurumsal kimlik bilgileri gerektir|X|X|
|Yönetilen cihazların, jailbreak uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelle|X|X|
|Uygulama verilerini şifreleme|X|X|
|Belirtilen sayıda dakika sonrasında erişim gereksinimlerini yeniden denetle|X|X|
|Çevrimdışı kullanım süresini belirtin|X|X|
|Ekran yakalamayı engelle (yalnızca Android)|X|X|
|Cihaz kaydı olmadan MAM desteği|X|X|
|Tam Temizleme|X|X|
|Seçmeli Silme <br></br>**Not:** iOS için yönetim profili kaldırıldığında uygulama da kaldırılır.|X||
|“Farklı Kaydet”i önleme|X||
|Hedeflenen Uygulama Yapılandırması|X||
|Çoklu Kimlik Desteği|X||
|Özelleştirilebilir Stil |X|||
|Citrix mVPN ile isteğe bağlı uygulama VPN bağlantıları|X|X| 
|Kişilerin eşitlenmesini devre dışı bırak|X|X|
|Yazdırmayı devre dışı bırak|X|X|
|En düşük uygulama sürümünü zorunlu tut|X|X|
|En düşük işletim sistemini zorunlu tut (iOS ve Android)|X|X|
|En düşük Android güvenlik düzeltme eki sürümünü zorunlu tut (yalnızca Android)|X|X|
|iOS için en düşük Intune SDK’sını zorunlu tut (yalnızca iOS)|X|X|

## <a name="next-steps"></a>Sonraki adımlar

Uygulama koruma ilkeleri ve Intune hakkında daha fazla bilgi edinmek için aşağıdaki konulara bakın:

  - [Android uygulama sarmalama aracı](app-wrapper-prepare-android.md)</br>
  - [iOS uygulama sarmalama aracı](app-wrapper-prepare-ios.md)</br>
  - [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
