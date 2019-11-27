---
title: Uygulamaları Microsoft Intune ile mobil uygulama yönetimi için hazırlama
description: Bu konu başlığı altındaki bilgiler, özel iş kolu uygulamalarınızın mobil uygulama yönetimi ilkelerini kullanabilmesini sağlamak için, Uygulama sarmalama aracını ve Uygulama SDK'sını ne zaman kullanmanız gerektiğine karar vermenize yardımcı olur.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 901eaafb24cda185540ffc4b1a56484042af74c1
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547697"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>İş kolu uygulamalarını uygulama koruma ilkelerine hazırlama

Intune Uygulaması Sarmalama Aracı’nı veya Intune Uygulama SDK’sını kullanarak uygulamalarınızın uygulama koruma ilkeleri kullanmasını sağlayabilirsiniz. Bu iki yöntem ve ne zaman kullanılacakları hakkında bilgi edinmek için bu bilgileri kullanın.

## <a name="intune-app-wrapping-tool"></a>Intune Uygulaması Sarmalama Aracı

Uygulama Sarmalama Aracı öncelikle **iç** iş kolu (LOB) uygulamaları için kullanılır. Araç, uygulamanın çevresinde bir sarmalayıcı oluşturan ve sonra uygulamanın bir Intune uygulama koruma ilkesiyle yönetilmesine izin veren bir komut satırı uygulamasıdır. Bağımsız yazılım satıcısı (ISV) tarafından sağlanan bir uygulamayı korurken, ISV'nin sarmalanmış uygulamayı yine de destekleyip desteklemeyeceğini netleştirmek önemlidir.

Aracı kullanmak için kaynak kodu gerekli değildir, ancak imzalama kimlik bilgileri gereklidir. İmzalama kimlik bilgileri hakkında daha fazla bilgi için bkz. [Intune blogu](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Uygulama sarmalama aracı belgeleri için bkz. [Android uygulama sarmalama aracı](app-wrapper-prepare-android.md) ve [IOS uygulaması sarmalama aracı](app-wrapper-prepare-ios.md).

Uygulama Sarmalama Aracı, Apple App Store veya Google Play Store'daki uygulamaları **desteklemez**. Ayrıca geliştirici tümleştirmesi gerektiren bazı özellikler için de destek sunmaz (aşağıdaki özellik karşılaştırma tablosuna bakın).

Intune’a kayıtlı olmayan cihazlarda uygulama koruma ilkeleri uygulamak için kullanılan Uygulama Sarmalama Aracı hakkında daha fazla bilgi için bkz. [Microsoft Intune’a kayıtlı olmayan cihazlarda iş kolu uygulamaları ve verilerini koruma](../apps/apps-add.md).

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
|**Android** |Evet|Evet|
|**Outlook Web Access (OWA)**|Hayır - [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Evet|

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
|**Android**|Evet – [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Hayır|
|**Outlook Web Access (OWA)**| Evet - [Intune Uygulaması SDK Xamarin Bağlamalarını](app-sdk-xamarin.md) kullan.|Hayır|

### <a name="not-using-an-app-development-platform-listed-above"></a>Yukarıda listelenen bir uygulama geliştirme platformu kullanmıyor musunuz?

Intune SDK geliştirme ekibi etkin bir şekilde sınar ve yerel Android, iOS (obj-C, Swift), Xamarin, Xamarin. Forms ve Cordova platformlarıyla oluşturulmuş uygulamalar için destek sağlar. Bazı müşteriler, bir Kullanıcı ve NativeScript gibi diğer platformlarla Intune SDK tümleştirmesi ile başarılı olmuş olsa da, desteklenen platformlarımızdan başka herhangi bir şeyi kullanarak uygulama geliştiricileri için açık rehberlik veya eklentiler sağlamayız. 

## <a name="feature-comparison"></a>Özellik karşılaştırması

Bu tabloda Uygulama SDK'si ve Uygulama Sarmalama Aracı için kullanabileceğiniz ayarlar listelenmektedir.

|Özellik|Uygulama SDK'sı|Uygulama Sarmalama Aracı|
|-----------|---------------------|-----------|
|Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın|X|X|
|Android, iTunes veya iCloud yedeklemelerini engelle|X|X|
|Uygulamanın diğer uygulamalara veri aktarmasına izin ver|X|X|
|Uygulamanın diğer uygulamalardan veri almasına izin ver|X|X|
|Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla|X|X|
|Yönetilen bir uygulamadan kesilebilir veya kopyalanabilecek karakter sayısını belirtin|X|X|
|Erişim için basit PIN gerektir|X|X|
|PIN sıfırlanmadan önceki deneme sayısını belirtin|X|X|
|PIN yerine parmak izine izin ver|X|X|
|PIN yerine yüz tanımaya izin ver (yalnızca iOS)|X|X|
|Erişim için kurumsal kimlik bilgileri gerektir|X|X|
|PIN süre sonu ayarlama|X|X|
|Yönetilen cihazların, jailbreak uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelle|X|X|
|Uygulama verilerini şifreleme|X|X|
|Belirtilen sayıda dakika sonrasında erişim gereksinimlerini yeniden denetle|X|X|
|Çevrimdışı kullanım süresini belirtin|X|X|
|Ekran yakalamayı engelle (yalnızca Android)|X|X|
|Cihaz kaydı olmadan MAM desteği|X|X|
|Uygulama verilerini tam Temizleme|X|X|
|Çoklu kimlik senaryolarında iş ve okul verilerinin seçmeli silme <br><br>**Not:** iOS için yönetim profili kaldırıldığında uygulama da kaldırılır.|X||
|“Farklı Kaydet”i önleme|X||
|Hedeflenen uygulama yapılandırması (veya "MAM Channel" aracılığıyla uygulama yapılandırması)|X||
|Çoklu Kimlik Desteği|X||
|Özelleştirilebilir Stil |X|||
|Citrix mVPN ile isteğe bağlı uygulama VPN bağlantıları|X|X| 
|Kişilerin eşitlenmesini devre dışı bırak|X|X|
|Yazdırmayı devre dışı bırak|X|X|
|En düşük uygulama sürümünü zorunlu tut|X|X|
|En düşük işletim sistemi gerektir|X|X|
|En düşük Android güvenlik düzeltme eki sürümünü zorunlu tut (yalnızca Android)|X|X|
|iOS için en düşük Intune SDK’sını zorunlu tut (yalnızca iOS)|X|X|
|SafetyNet cihaz kanıtlama (yalnızca Android)|X|X|
|Uygulamalarda tehdit taraması (yalnızca Android)|X|X|

## <a name="next-steps"></a>Sonraki adımlar

Uygulama koruma ilkeleri ve Intune hakkında daha fazla bilgi edinmek için aşağıdaki konulara bakın:

- [Android uygulama sarmalama aracı](app-wrapper-prepare-android.md)<br>
- [iOS uygulama sarmalama aracı](app-wrapper-prepare-ios.md)<br>
- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](app-sdk.md)
