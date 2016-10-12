---
title: "Uygulamaları mobil uygulama yönetimi için hazırlama | Microsoft Intune"
description: "Bu konu başlığı altındaki bilgiler, özel iş kolu uygulamalarınızın mobil uygulama yönetimi ilkelerini kullanabilmesini sağlamak için, Uygulama sarmalama aracını ve Uygulama SDK’sını ne zaman kullanmanız gerektiğine karar vermenize yardımcı olur."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df1b58d5ce94c985e71f3afbe228dba9438040dc
ms.openlocfilehash: d79c498fd775ee9b3d59761fec2fe6ebba116d6d


---

# Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme
Intune Uygulaması Sarmalama Aracı’nı veya Intune Uygulama SDK’sını kullanarak uygulamalarınızın mobil uygulama yönetim (MAM) ilkelerini kullanmasını sağlayabilirsiniz. Bu iki yöntem ve ne zaman kullanılacakları hakkında bilgi edinmek için bu bilgileri kullanın.

## Intune Uygulaması Sarmalama Aracı
Uygulama Sarmalama Aracı öncelikle iç iş kolu (LOB) uygulamaları için kullanılır. Araç, uygulamanın çevresinde sarmalayıcı oluşturan ve sonra uygulamanın bir Intune mobil uygulama yönetimi ilkesiyle yönetilmesine izin veren bir komut satırı uygulamasıdır. 

Aracı kullanmak için kaynak kodu gerekli değildir, ancak imzalama kimlik bilgileri gereklidir.  İmzalama kimlik bilgileri hakkında daha fazla bilgi için bkz. [Intune blogu](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Uygulama Sarmalama Aracı belgeleri için bkz. [Android Uygulaması Sarmalama Aracı](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) ve [iOS Uygulaması Sarmalama Aracı](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Uygulama Sarmalama Aracı, Apple App Store veya Google Play Store’daki uygulamaları ya da geliştirme zamanı tümleştirmesi gerektiren belirli özellikleri **desteklemez** (aşağıdaki özellik karşılaştırma tablosuna bakın).

Uygulama daha önce yazılmışsa veya kaynak kodu yoksa SDK yerine Uygulama Sarmalama Aracı’nı kullanmanız gerekir.

**Intune’da kayıtlı olmayan cihazlarda MAM için Uygulama Sarmalama Aracı hakkında daha fazla bilgi edinmek üzere bkz. [Microsoft Intune’da kayıtlı olmayan cihazlarda iş kolu uygulamalarını ve verileri koruma](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)**.

### Desteklenen uygulama geliştirme platformları

|**Uygulama Sarmalama Aracı** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Evet|Evet|
|**Android**| Hayır |Evet|

## Intune Uygulama SDK'sı
Uygulama SDK'sı temel olarak App Store ve/veya Google Play Store’da uygulamaları olan ve uygulamaları Intune ile yönetebilmek isteyen müşteriler için tasarlanmıştır. Ancak, bir iş kolu uygulaması olsa bile SDK’yı tümleştirme özelliğinden her uygulama yararlanabilir.

SDK hakkında daha fazla bilgi edinmek için bkz. [Genel bakış](/intune/develop/intune-app-sdk). SDK’yı kullanmaya başlamak için bkz. [Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama](/intune/develop/intune-app-sdk-get-started).

### Desteklenen uygulama geliştirme platformları

|**Intune Uygulama SDK'sı** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Evet – Intune Uygulaması SDK Xamarin bileşenini kullan|Evet – Intune Uygulaması SDK Cordova eklentisini kullan|
|**Android**| Evet – Intune Uygulaması SDK Xamarin Bileşenini kullan|Evet – Intune Uygulaması SDK Cordova eklentisini kullan|

## Özellik karşılaştırması
Bu tabloda Uygulama SDK'si ve Uygulama Sarmalama Aracı için kullanabileceğiniz ayarlar listelenmektedir.

> [!NOTE]
> Uygulama Sarmalama Aracı, Tek Başına Intune veya Configuration Manager ile Intune ile kullanılabilir.

|Özellik|Uygulama SDK'sı|Uygulama Sarmalama Aracı|
|-----------|---------------------|-----------|
|Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın|X|X|
|Android, iTunes veya iCloud yedeklemelerini engelle|X|X|
|Uygulamanın diğer uygulamalara veri aktarmasına izin ver|X|X|
|Uygulamanın diğer uygulamalardan veri almasına izin ver|X|X|
|Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama|X|X|
|Erişim için basit PIN gerektir|X|X|
|Intune PIN ile yerleşik uygulama PIN kodunu değiştir|X||
|PIN sıfırlanmadan önceki deneme sayısını belirtin|X|X|
|PIN yerine parmak izi iste (yalnızca iOS)<br></br>**Not:** Yalnızca MAM ortamlarında kullanılabilir.|X||
|Erişim için kurumsal kimlik bilgileri gerektir|X|X|
|Yönetilen cihazların, jailbreak uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelle|X|X|
|Uygulama verilerini şifreleme|X|X|
|Belirtilen sayıda dakika sonrasında erişim gereksinimlerini yeniden denetle|X|X|
|Çevrimdışı kullanım süresini belirtin|X|X|
|Ekran yakalamayı engelle (yalnızca Android)|X|X|
|Tam Temizleme|X|X|
|Seçmeli Silme <br></br>**Not:** iOS için yönetim profili kaldırıldığında uygulama da kaldırılır.|X||
|“Farklı Kaydet”i önleme |X||
|Çoklu Kimlik Desteği|X||
|Cihaz kaydı olmadan MAM desteği|X|X|
### Ayrıca bkz.

[Android uygulama sarmalama aracı](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS uygulama sarmalama aracı](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO4-->


