---
title: Microsoft Intune Uygulama SDK’sını kullanmaya başlayın
description: Mobil uygulamanızı Microsoft Intune ile mobil uygulama yönetimi (MAM) için hızlıca etkinleştirin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b24387636408d2e28891aae13962c2febf9f329
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167198"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Microsoft Intune Uygulama SDK’sını kullanmaya başlayın

Bu kılavuz, mobil uygulamanızı Microsoft Intune ile uygulama koruma ilkelerini destekleyecek şekilde hızlı bir şekilde etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz yararlı olabilir.

Intune Uygulama SDK'sı, iOS ve Android’de benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform farkları ve sınırlamaları nedeniyle bazı özellikleri desteklemeye yönelik küçük farklılıklar vardır.

## <a name="register-your-store-app-with-microsoft"></a>Mağaza uygulamanızı Microsoft’a kaydetme

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Uygulamanız kuruluşunuz içinde kullanılıyorsa ve herkese açık olmayacaksa:

Uygulamanızı kaydetmeniz _**gerekmez**_ . Şirket tarafından veya şirketiniz tarafından yazılan iç [iş kolu (LOB) uygulamaları](apps-add.md#app-types-in-microsoft-intune) için BT Yöneticisi, uygulamayı dahili olarak dağıtır. Intune, uygulamanın SDK ile derlendiğinden emin olur ve BT yöneticisinin bu uygulamaya uygulama koruma ilkeleri uygulamasına izin verir. [iOS veya Android uygulamanızı uygulama koruma ilkesi için etkinleştirme](#enable-your-ios-or-android-app-for-app-protection-policy) bölümüne geçebilirsiniz.

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Uygulamanız Apple App Store veya Google Play gibi bir genel uygulama mağazasında yayınlanacaksa:

Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz _**gerekir**_ . BT yöneticileri daha sonra yönetilen uygulamaya bir [Intune korumalı iş ortağı uygulaması](apps-supported-intune-apps.md#partner-apps)olarak listelenen bir uygulama koruma ilkesi uygulayabilir.

Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, Intune yöneticilerinin uygulamanızın ayrıntılı bağlantısına uygulama koruma ilkesi uygulama seçeneği olmaz. Microsoft ayrıca uygulamanızı kendi [Microsoft Intune İş Ortakları sayfasına](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) ekler. Sayfada Intune uygulama koruma ilkelerini desteklediğini göstermek üzere uygulamanın simgesi görüntülenir.

### <a name="the-registration-process"></a>Kayıt işlemi
Henüz birlikte çalıştığınız bir Microsoft ilgili kişisi yoksa kayıt işlemine başlamak için [Microsoft Intune Uygulama İş Ortağı Anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR80SNPjnVA1KsGiZ89UxSdVUMEpZNUFEUzdENENOVEdRMjM5UEpWWjJFVi4u)’ni doldurun.

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

* **[İOS Için Intune uygulama SDK 'Sı Geliştirici Kılavuzu](app-sdk-ios.md)** : Bu belge, Intune uygulama SDK 'Sı ile Yerel iOS uygulamanızı etkinleştirmek için adım adım size kılavuzluk eder.

* **[Android Için Intune uygulama SDK 'Sı Geliştirici Kılavuzu](app-sdk-android.md)** : Bu belge, Intune uygulama SDK 'Sı ile yerel Android uygulamanızı etkinleştirmek için adım adım size kılavuzluk eder.

* **[Intune uygulama SDK 'Sı Xamarin bağlamaları Kılavuzu](app-sdk-xamarin.md)** : Bu belge, Intune uygulama koruma ilkeleri için Xamarin kullanarak iOS ve Android uygulamaları oluşturmanıza yardımcı olur.



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>İOS veya Android uygulamanızı uygulama tabanlı koşullu erişim için etkinleştirme

Uygulamanızı uygulama koruma ilkesi için etkinleştirmeye ek olarak, uygulamanızın Azure ActiveDirectory (AAD) uygulama tabanlı koşullu erişim ile düzgün çalışması için aşağıdakiler gereklidir:

* Uygulama, [Azure Active Directory Kimlik Doğrulama Kitaplığı](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) ile oluşturulur ve AAD aracısı kimlik doğrulaması için etkinleştirilir.

* Uygulamanız için [AAD İstemci kimliği](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#configure-a-native-client-application), farklı iOS ve Android platformlarında benzersiz olmalıdır.

## <a name="configure-telemetry-for-your-app"></a>Uygulamanızda Telemetriyi yapılandırma

Microsoft Intune, uygulamanızdaki kullanım istatistikleri hakkında veri toplar.

* **İOS Için Intune uygulama SDK 'sı**: SDK varsayılan olarak kullanım olaylarına ilişkin SDK telemetri verilerini günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

  * Uygulamanızdan Microsoft Intune’a SDK telemetri verileri göndermek istemiyorsanız IntuneMAMSettings sözlüğündeki `MAMTelemetryDisabled` özelliğini “EVET” olarak ayarlayarak telemetri iletimini devre dışı bırakmanız gerekir.

* **Android Için Intune uygulama SDK 'sı**: Android için Intune Uygulama SDK’sı, uygulamanızdan veri toplanmasını denetlemez. Şirket Portalı uygulaması, varsayılan olarak telemetri verilerini günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir. Microsoft İlkesi uyarınca kişisel bilgileri toplamıyoruz. 

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

* **Test hesabı Microsoft Intune**: Intune tarafından yönetilen uygulamanızı Intune uygulama koruma özelliklerine karşı sınamak için bir Microsoft Intune hesabınızın olması gerekir.

  * iOS veya Android mağazası uygulamalarınızı Intune uygulama koruma ilkesi için etkinleştiren bir ISV iseniz Microsoft Intune kaydını, kayıt adımında belirtilen şekilde bitirdikten sonra bir promosyon kodu alırsınız. Promosyon kodu, bir yıllık uzatılmış kullanım sağlayan Microsoft Intune denemesine kaydolmanıza olanak tanır.

  * Mağazaya gönderilmeyecek bir iş kolu uygulaması geliştiriyorsanız kuruluşunuz aracılığıyla Microsoft Intune’a erişiminizin olması beklenir. [Microsoft Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ile bir aylık ücretsiz deneme için de kaydolabilirsiniz.

  * Uygulamanızı Son Kullanıcı hesabı kullanarak bir mobil cihazda test ediyorsanız, bir yönetici hesabıyla oturum açtıktan sonra Microsoft 365 Yönetim Merkezi Web sitesinde bu hesaba bir Intune lisansı vermiş olduğunuzdan emin olun, bkz. [Microsoft Intune lisansı atama](licenses-assign.md).

* **Intune uygulama koruma ilkeleri**: Uygulamanızı tüm Intune uygulama koruma ilkelerine karşı test etmek için, her ilke ayarı için beklenen davranışın ne olduğunu bilmeniz gerekir. Açıklamalar için bkz. [iOS uygulama koruma ilkeleri](app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkeleri](app-protection-policy-settings-android.md). Uygulamanız Intune SDK 'sını tümleştirdiyse, ancak henüz hedeflenen bir uygulama olarak Azure portal listelenmiyorsa, "+ daha fazla uygulama" seçeneğini belirleyerek ve metin kutusuna paket KIMLIĞI (iOS) veya paket adı (Android) sağlayarak bunu bir ilkeyle hedefleyebilirsiniz.

* **Sorun giderme**: Uygulamanızın yükleme kullanıcı deneyimini el ile sınarken herhangi bir sorunla karşılaşırsanız, bkz. [uygulama yükleme sorunlarını giderme](troubleshoot-app-install.md). 

### <a name="give-your-app-access-to-the-intune-app-protection-service-optional"></a>Uygulamanızın Intune uygulama koruma hizmeti 'ne erişmesini sağlayın (isteğe bağlı)

Uygulamanız kimlik doğrulaması için kendi özel Azure Active Directory (AAD) ayarlarını kullanıyorsa, hem genel mağaza uygulamaları hem de iç LOB uygulamaları için aşağıdaki adımların alınması gerekir. **Uygulamanız ıNTUNE SDK varsayılan ISTEMCI kimliğini kullanıyorsa, adımların alınması gerekmez**. 

Uygulamanızı bir Azure kiracısında kaydettikten ve **tüm uygulamalar**altında gösteriyorsa, uygulamanızın Intune uygulama koruma hizmeti 'ne (ÖNCEKI adıyla mam hizmeti) erişmesini sağlamanız gerekir. Azure portalında:

1. **Azure Active Directory** dikey penceresine gidin.
2. **Uygulama kayıtları**altında, uygulama için ayarlanan listeye gidin.
3. **+ Izin Ekle**' ye tıklayın.
4. **Kuruluşumun kullandığı API 'lere**tıklayın. 
5. Arama kutusuna **Microsoft Mobil Uygulama Yönetimi** yazın.
6. **Temsilci izinleri**altında **devicemanagementmanagedapps. ReadWrite öğesini seçin: Kullanıcının uygulama yönetimi verileri*** onay kutusunu okuyun ve yazın.
7. **Izin Ekle**' ye tıklayın.

### <a name="badge-your-app-optional"></a>Uygulamanıza rozet ekleyin (isteğe bağlı)

Intune uygulama koruma ilkelerinin uygulamanızda çalıştığını doğruladıktan sonra, uygulamanızın simgesine Intune uygulama koruma logosu ile rozet ekleyebilirsiniz.

Bu rozet BT yöneticilerine, son kullanıcılara ve potansiyel Intune müşterilerine uygulamanızın Intune uygulama koruma ilkeleriyle çalıştığını gösterir. Uygulamanızın Intune müşterileri tarafından kullanılmasını ve benimsenmesini teşvik eder.

Rozet bir evrak çantası simgesidir ve aşağıdaki örneklerde görülebilir:

![Intune uygulama koruma ilkeleri-rozet örneği 1](./media/badge-example-1.png) ![Intune uygulama koruma ilkeleri-rozet örneği 2](./media/badge-example-2.png)

**Uygulamanıza rozet eklemek için gerekenler**:

* **.eps** dosyalarını okuyabilen bir görüntü işleme uygulaması veya **.ai** dosyalarını okuyabilen bir Adobe uygulaması.

* Microsoft Intune GitHub’da [Intune uygulama rozet varlıkları ve yönergelerini](https://github.com/msintuneappsdk/intune-app-partner-badge) bulabilirsiniz.
