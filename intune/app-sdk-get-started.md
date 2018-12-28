---
title: Microsoft Intune Uygulama SDK’sını kullanmaya başlayın
description: Mobil uygulamanızı Microsoft Intune ile mobil uygulama yönetimi (MAM) için hızlıca etkinleştirin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 03840b0a4a7ce3f4735e22a227f5d2856d532b11
ms.sourcegitcommit: 02f75d241b3cbb125cb235d16d447f8855b1806d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53657789"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Microsoft Intune Uygulama SDK’sını kullanmaya başlayın

Bu kılavuz, mobil uygulamanızı Microsoft Intune ile uygulama koruma ilkeleri için hızlıca etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz yararlı olabilir.

Intune Uygulama SDK'sı, iOS ve Android’de benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform sınırlamaları nedeniyle bazı özelliklerin desteklenmesinde küçük farklılıklar vardır.

## <a name="register-your-store-app-with-microsoft"></a>Mağaza uygulamanızı Microsoft’a kaydetme

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Uygulamanız kuruluşunuz içinde kullanılıyorsa ve herkese açık olmayacaksa:

Uygulamanızı kaydetmeniz *gerekmez*. BT yöneticisi, uygulamayı dahili iş kolu uygulamaları için içeriden dağıtır. Intune, uygulamanın SDK ile oluşturulduğunu algılar ve BT yöneticisinin buna uygulama koruma ilkesi uygulamasına izin verir. [iOS veya Android uygulamanızı uygulama koruma ilkesi için etkinleştirme](#enable-your-iOS-or-Android-app-for-app-protection-policy) bölümüne geçebilirsiniz.

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Uygulamanız Apple App Store veya Google Play gibi bir genel uygulama mağazasında yayınlanacaksa:

Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz _**gerekir**_. Bundan sonra BT yöneticileri, uygulama koruma ilkesini bir Intune uygulama iş ortağı olarak listelenen yönetilen uygulamaya uygulayabilir.

Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, Intune yöneticilerinin uygulamanızın ayrıntılı bağlantısına uygulama koruma ilkesi uygulama seçeneği olmaz. Microsoft ayrıca uygulamanızı kendi [Microsoft Intune İş Ortakları sayfasına](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) ekler. Sayfada Intune uygulama koruma ilkelerini desteklediğini göstermek üzere uygulamanın simgesi görüntülenir.

Henüz birlikte çalıştığınız bir Microsoft ilgili kişisi yoksa kayıt işlemine başlamak için [Microsoft Intune Uygulama İş Ortağı Anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)’ni doldurun.

Size ulaşmak ve kayıt işlemine devam etmek için anket yanıtlarınızda listelenen e-posta adresini (veya adreslerini) kullanacağız. Ayrıca, herhangi bir sorumuz olursa sizinle iletişim kurmak için kayıt e-posta adresinizi kullanırız.

> [!NOTE]
> Ankette ve Microsoft Intune ekibi ile yapılan e-posta yazışmaları aracılığıyla toplanan tüm bilgiler için [Microsoft Gizlilik Bildirimi](https://www.microsoft.com/privacystatement/default.aspx) geçerli olacaktır.

**Kayıt işleminde beklenmesi gerekenler**:

1. Siz anketi gönderdikten sonra, talebin başarıyla alındığını onaylamak veya kaydı tamamlamak amacıyla ek bilgi istemek için kayıt e-posta adresiniz üzerinden sizinle iletişim kurarız.

2. Gerekli tüm bilgileri sizden aldıktan sonra, imzalamanız için Microsoft Intune Uygulama İş Ortağı Sözleşmesi’ni size göndeririz. Bu sözleşmede, şirketinizin bir Microsoft Intune uygulama iş ortağı olmadan önce kabul etmesi gereken koşullar açıklanır.

3. Uygulamanız Microsoft Intune hizmetine başarıyla kaydedildiğinde ve [Microsoft Intune iş ortakları](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) sitesinde gösterildiğinde size bildirilir.

4. Son olarak, uygulamanızın ayrıntılı bağlantısı bir sonraki aylık Intune Hizmeti güncelleştirmesine eklenir. Örneğin kayıt bilgileri Temmuz'da tamamlanmışsa ayrıntılı bağlantı Ağustos ayının ortalarında desteklenecektir.

Uygulamanızın ayrıntılı bağlantısı gelecekte değişirse, uygulamanızı yeniden kaydetmeniz gerekir.

> [!NOTE]
> Uygulamanızı Intune Uygulama SDK'sının yeni bir sürümüyle güncelleştirirseniz bunu lütfen bize bildirin.

## <a name="download-the-sdk-files"></a>SDK dosyalarını indirme

Yerel iOS ve Android için Intune Uygulama SDK'ları bir Microsoft GitHub hesabında barındırılır. Bu genel depolar sırasıyla yerel iOS ve Android için SDK dosyalarını içerir:

* [iOS için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Uygulamanız bir Xamarin uygulaması ise lütfen şu SDK çeşidini kullanın:

* [Intune Uygulama SDK’sı Xamarin Bağlamaları](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)

Depolarımızdan çatallama ve çekme işlemleri yaparken kullanabileceğiniz bir GitHub hesabı oluşturmanız iyi olabilir. GitHub, geliştiricilerin ürün ekibimizle iletişim kurmasına, soru sorup hızlı yanıtlar almasına, sürüm notlarını görüntülemesine ve Microsoft'a geri bildirim sağlamasına olanak tanır. Intune Uygulama SDK’sı Github'ındaki sorular için şuraya başvurun: msintuneappsdk@microsoft.com.

## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>iOS veya Android uygulamanızı uygulama koruma ilkesi için etkinleştirme

Intune Uygulama SDK'sı ile uygulamanızı tümleştirmenize yardımcı olması için aşağıdaki geliştirici kılavuzlarından biri gerekir:

* **[İOS Geliştirici Kılavuzu için Intune uygulama SDK'sı](app-sdk-ios.md)**: Bu belgede, yerel iOS uygulamanızı Intune uygulama SDK'sı ile etkinleştirme adımları anlatılmaktadır.

* **[Android Geliştirici Kılavuzu için Intune uygulama SDK'sı](app-sdk-android.md)**: Bu belgede, yerel Android uygulamanızı Intune uygulama SDK'sı ile etkinleştirme adımları anlatılmaktadır.

* **[Intune uygulama SDK'sı Xamarin bağlamaları Kılavuzu](app-sdk-xamarin.md)**: Bu belge, iOS ve Xamarin için Intune uygulama koruma ilkeleri kullanarak Android uygulamaları oluşturmanıza yardımcı olur.



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>Uygulama tabanlı koşullu erişim için iOS veya Android uygulamanızı etkinleştirme
 
 Uygulama koruma ilkesi için uygulamanızı etkinleştirmenin yanı sıra, uygulamanızın Azure Active Directory (AAD) uygulama tabanlı koşullu erişim ile doğru şekilde yaşaması için aşağıdakiler gereklidir:
 
 * Uygulama, [Azure Active Directory Kimlik Doğrulama Kitaplığı](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) ile oluşturulur ve AAD aracısı kimlik doğrulaması için etkinleştirilir.
 
 * Uygulamanız için [AAD İstemci kimliği](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#optional-configure-a-native-client-application), farklı iOS ve Android platformlarında benzersiz olmalıdır.
 
## <a name="configure-telemetry-for-your-app"></a>Uygulamanızda Telemetriyi yapılandırma

Microsoft Intune, uygulamanızdaki kullanım istatistikleri hakkında veri toplar.

* **İOS için Intune uygulama SDK'sı**: SDK, kullanım olaylarına ilişkin SDK telemetri verilerini varsayılan olarak günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

    * Uygulamanızdan Microsoft Intune’a SDK telemetri verileri göndermek istemiyorsanız IntuneMAMSettings sözlüğündeki `MAMTelemetryDisabled` özelliğini “EVET” olarak ayarlayarak telemetri iletimini devre dışı bırakmanız gerekir.

* **Android için Intune uygulama SDK'sı**: Android için Intune Uygulama SDK’sı, uygulamanızdan veri toplanmasını denetlemez. Şirket Portalı uygulaması, varsayılan olarak telemetri verilerini günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir. Microsoft İlkesi uyarınca kişisel bilgileri toplamıyoruz. 

    * Son kullanıcılar bu verileri göndermemeyi tercih ederse, Şirket Portalı uygulamasının Ayarlar bölümünde telemetriyi kapatmaları gerekir. Daha fazla bilgi için bkz. [Microsoft kullanım verilerini toplamayı devre dışı bırakma](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="line-of-business-app-version-numbers"></a>İş kolu uygulaması sürüm numaraları

Intune’da iş kolu uygulamaları artık iOS ve Android uygulamaları için sürüm numarasını görüntüler. Numara, Azure portalındaki uygulama listesinde ve uygulama genel bakış dikey penceresinde görüntülenir. Son kullanıcılar, uygulama numarasını Şirket Portalı uygulamasında ve web portalında görebilir.

### <a name="full-version-number"></a>Tam sürüm numarası

Tam sürüm numarası uygulamanın belirli bir yayınını tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin 2.2(2.2.17560800). 

Tam sürüm numarası iki bileşenden oluşur:

 - **Sürüm**  
   Sürüm numarası uygulamanın insan tarafından okunabilir yayın numarasıdır. Bu, son kullanıcılar tarafından uygulamanın farklı yayınlarını tanımlamak için kullanılır.

 - **Derleme Numarası**  
    Derleme numarası, uygulama algılamada ve uygulamayı programlı olarak yönetmek için kullanılabilen dahili bir numaradır. Derleme numarası, uygulamanın koddaki değişikliklere başvuran bir yinelemesini ifade eder.

### <a name="version-and-build-number-in-android-and-ios"></a>Android ve iOS’te sürüm ve derleme numarası

Android ve iOS, uygulamalar için hem sürüm hem de derleme numaralarını kullanır. Ancak her iki işletim sisteminin de işletim sistemine özgü anlamları vardır. Aşağıdaki tabloda bu terimlerin arasındaki ilişkiler açıklanmaktadır.

Intune’da kullanmak üzere bir iş kolu uygulaması geliştirirken, sürüm ve derleme numarasını birlikte kullanmayı unutmayın. Intune Uygulama yönetimi özellikleri anlamlı bir **CFBundleVersion** (iOS için) ve **PackageVersionCode** (Android için) kullanır. Bu numaralar, uygulama bildirimine eklenir. 

Intune|iOS|Android|Açıklama|
|---|---|---|---|
Sürüm numarası|CFBundleShortVersionString|PackageVersionName |Bu numara, son kullanıcılara yönelik belirli bir uygulama yayınını gösterir.|
Yapı numarası|CFBundleVersion|PackageVersionCode |Bu numara, uygulama kodunda bir yinelemeyi gösterir.|

#### <a name="ios"></a>iOS

- **CFBundleShortVersionString**  
    Paket yayımlanma sürümü numarasını belirtir. Bu numara, uygulamanın yayımlanma sürümünü tanımlar. Numara, son kullanıcılar tarafından uygulamaya başvurmak için kullanılır.
- **CFBundleVersion**  
    Paketin bir yinelemesini tanımlayan paket derleme sürümü. Numara, yayımlanmış veya yayımlanmamış bir paketi tanımlayabilir. Numara, uygulama algılama için kullanılır.

#### <a name="android"></a>Android

 - **PackageVersionName**  
    Kullanıcılara gösterilen sürüm numarası. Bu öznitelik bir ham dize veya bir dize kaynağına başvuru olarak ayarlanabilir. Dizenin kullanıcılara görüntülenmekten başka bir amacı yoktur.
 - **PackageVersionCode**  
    Dahili sürüm numarası. Bu numara yalnızca bir sürümün diğerinden daha yeni olup olmadığını belirlemek için kullanılır; daha yüksek numaralar daha yeni sürümleri gösterir. Bu sürüm değildir 

## <a name="next-steps-after-integration"></a>Tümleştirmeden sonraki adımlar

### <a name="test-your-app"></a>Uygulamanızı test etme
iOS veya Android uygulamanızı Intune Uygulama SDK’sıyla tümleştirmek için gerekli adımları bitirdikten sonra, kullanıcı ile BT yöneticisi için tüm uygulama koruma ilkelerinin etkinleştirildiğinden ve çalıştığından emin olmanız gerekir. Tümleşik uygulamanızı sınamak için aşağıdakiler gerekir:

* **Microsoft Intune test hesabının**: Intune ile yönetilen uygulamanızı Intune uygulama koruma özelliklerine karşı sınamak için bir Microsoft Intune hesabınız olması gerekir.

    * iOS veya Android mağazası uygulamalarınızı Intune uygulama koruma ilkesi için etkinleştiren bir ISV iseniz Microsoft Intune kaydını, kayıt adımında belirtilen şekilde bitirdikten sonra bir promosyon kodu alırsınız. Promosyon kodu, bir yıllık uzatılmış kullanım sağlayan Microsoft Intune denemesine kaydolmanıza olanak tanır.

    * Mağazaya gönderilmeyecek bir iş kolu uygulaması geliştiriyorsanız kuruluşunuz aracılığıyla Microsoft Intune’a erişiminizin olması beklenir. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ile bir aylık ücretsiz deneme için de kaydolabilirsiniz.

* **Intune uygulama koruma ilkeleri**: Uygulamanızı tüm Intune uygulama koruma ilkelerine karşı sınamak için her ilke ayarı için beklenen davranış ne olduğunu bilmeniz. Açıklamalar için bkz. [iOS uygulama koruma ilkeleri](app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkeleri](app-protection-policy-settings-android.md).

* **Sorun giderme**: Uygulama yükleme kullanıcı deneyimini el ile sınarken herhangi bir sorunla karşılaşırsanız çalıştırırsanız, bkz. [uygulaması yükleme sorunlarını giderme](troubleshoot-app-install.md). 

### <a name="give-your-app-access-to-the-intune-app-protection-service-optional"></a>Uygulama erişimlerini Intune uygulama koruma hizmeti için (isteğe bağlı)

Kimlik doğrulaması için uygulamanızı kendi özel Azure Active Directory (AAD) ayarları kullanıyorsa, aşağıdaki adımları hem ortak mağaza uygulamaları, hem de için dahili LOB uygulamalarında gerçekleştirilmelidir. Adımları **uygulamanız Intune SDK'sı varsayılan istemci Kimliğini kullanıyorsanız alınması gerekmez**. 

Uygulamanızı bir Azure kiracısı içinde kaydettikten sonra altında bazılarındaki **tüm uygulamaları**, kendi uygulama erişimini Intune uygulama koruma Hizmeti'ne (daha önce MAM hizmeti olarak da bilinir) vermeniz gerekir. Azure portalında:

1.  **Azure Active Directory** dikey penceresine gidin.
2.  Uygulama için **Uygulama kaydı** ayarını seçin.
3.  **API Erişimi** başlığının altındaki **Ayarlar**’da **Gerekli İzin**’i seçin. 
4.  **+ Ekle**’ye tıklayın.
5.  **Bir API Seç**’e tıklayın. 
6.  Arama kutusuna **Microsoft Mobil Uygulama Yönetimi** yazın.
7.  API’ler listesinde **Microsoft Mobil Uygulama Yönetimi**’ni seçin ve seçime tıklayın.
8.  **Kullanıcının Uygulama Yönetim Verilerini Okuma ve Yazma**'yı seçin.
9.  **Bitti**’ye tıklayın.
10. **İzin ver**'e, ardından **Evet**'e tıklayın. 

### <a name="badge-your-app-optional"></a>Uygulamanıza rozet ekleyin (isteğe bağlı)

Intune uygulama koruma ilkelerinin uygulamanızda çalıştığını doğruladıktan sonra, uygulamanızın simgesine Intune uygulama koruma logosu ile rozet ekleyebilirsiniz.

Bu rozet BT yöneticilerine, son kullanıcılara ve potansiyel Intune müşterilerine uygulamanızın Intune uygulama koruma ilkeleriyle çalıştığını gösterir. Uygulamanızın Intune müşterileri tarafından kullanılmasını ve benimsenmesini teşvik eder.

Rozet bir evrak çantası simgesidir ve aşağıdaki örneklerde görülebilir:

![Intune uygulama koruma ilkeleri - rozet örneği 1](./media/badge-example-1.png) ![Intune uygulama koruma ilkeleri - rozet örneği 2](./media/badge-example-2.png)

**Uygulamanıza rozet eklemek için gerekenler**:

* **.eps** dosyalarını okuyabilen bir görüntü işleme uygulaması veya **.ai** dosyalarını okuyabilen bir Adobe uygulaması.

* Microsoft Intune GitHub’da [Intune uygulama rozet varlıkları ve yönergelerini](https://github.com/msintuneappsdk/intune-app-partner-badge) bulabilirsiniz.
