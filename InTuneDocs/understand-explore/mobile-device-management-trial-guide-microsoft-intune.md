---
title: "Microsoft Intune&quot;da mobil cihaz yönetimini değerlendirme | Microsoft Docs"
description: "Ücretsiz Intune deneme sürümünüzde MDM’yi değerlendirin."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Microsoft Intune'da mobil cihaz yönetimini değerlendirme
Bu değerlendirme kılavuzu, mobil cihazınızın Intune'da nasıl yönetildiğini gösterir. Şunları yapacaksınız:
- Intune tarafından yönetilecek bir cihazı kaydetme.
- Kullanıcıları ve cihazları düzenlemek için grup oluşturma.
- Bazı cihaz yönetimi ilkeleri oluşturma ve gruplarınıza dağıtma.
- Kayıtlı cihazları olan kullanıcıların cihazlarına yükleyebilmeleri için bir uygulama yayımlama.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Varsayımlar
Bu kılavuzda deneme sürümünü yalnızca değerlendirme amacıyla kullandığınız ve abone olduğunuzda temiz bir ortam ile başlamak istediğiniz varsayılmaktadır.

Deneme sürümüne başlamanızı kolaylaştırmak için yalnızca Intune kullanılan ve Intune’un mobil cihaz yönetimi yetkiliniz olacağını varsayan çok basit bir ortam ayarlıyoruz. Ancak kılavuz boyunca, daha fazlasını öğrenmek isterseniz sizi daha ayrıntılı içeriğe yönlendiririz.

Deneme sürümünde abonelik sürümünde yapabileceğiniz her şeyi yapabilirsiniz. Tek fark, deneme sürümünün 100 kullanıcı hesabı ile sınırlı olmasıdır.

## <a name="whats-not-covered"></a>Kapsanmayan konular
|İlgileniyorsanız |Bunu okuyun |
|------------------------|----------|
|Sınama ortamı olmayan bir ortamda MDM | [Başlarken](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|Intune ve System Center Configuration Manager ile MDM | [Karma mobil cihaz yönetimi](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Yukarıdaki kılavuzlar Intune'u üretim ortamlarında ayarlamanıza yardımcı olduğundan daha uzundurlar ve değerlendirme kılavuzunda yapmanız gerekenlere göre çok daha fazla karar noktası içerirler.

Intune’u hızlı bir şekilde tanımak için değerlendirme kılavuzu ile başlamanız ve ardından diğer kılavuzlara devam etmeniz önerilir.

## <a name="prerequisites-for-this-evaluation"></a>Bu değerlendirmenin önkoşulları
- Internet Explorer 10 veya üstü
- Intune kullanıcılarının Şirket Portalı’nı kullanarak cihazlarını nasıl kaydedeceğini ve yöneteceğini sınamak için kullanacağınız bir cihaz. Bu kılavuzda bir iPad ve Android telefon kullanılmaktadır.
- iPad veya başka bir iOS cihazını yönetmek için bir [Apple Anında İletilen Bildirim servisi sertifikasına](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) ihtiyacınız olacak.
- Bir [Intune deneme aboneliği](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>MDM yetkilinizi ayarlama
Intune ile mobil cihazları yönetmek için gereken ilk adım **mobil cihaz yönetimi (MDM) yetkilinizi** ayarlamaktır.

Bu deneme sürümünün varsaydığı gibi Intune’u tek başına kullanıyorsanız veya Intune’u bir Enterprise Mobility + Security (EMS) aboneliğinin parçası olarak kullanıyorsanız, Intune’u mobil cihaz yönetimi yetkiliniz olarak ayarlamanız gerekir. Diğer bir deyişle, Intune’u kuruluşunuzdaki mobil cihazları yönetmek için kullandığınız hizmet olarak belirlersiniz.

Mobil cihazları yönetmek için Intune’u System Center Configuration Manager ile kullanmak isteyen müşterilerin, mobil cihaz yönetim yetkilisi olarak Intune veya Configuration Manager’dan birini kullanmaya karar vermeleri gerekir. Bir üretim ortamında bu önemli bir karardır çünkü bu kararı verdikten sonra ayarı değiştirmek şu anda çok zordur ve bu kılavuzunun kapsamı dışında bir konudur. MDM yetkiliniz olarak Intune veya Configuration Manager’ı ayarlamanın etkileri hakkında daha fazlasını öğrenmek için bkz. [Tek başına Intune ve karma mobil cihaz yönetimi arasında seçim yapma](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

Deneme sürümünde MDM yetkilisi olarak Intune’u ayarlayacağız; deneme sürümünüzü üretim ortamınızda kullanmaya karar vermediğiniz sürece üretim ortamınızı etkilemez.

1. [Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** &gt; **Mobil Cihaz Yönetimi**’ni seçin.
2. **Görevler** listesinde, **MDM Yetkilisini Ayarla**’yı seçin. **MDM Yetkilisini Ayarla** iletişim kutusu açılır. <!---screen shot--->
3. Intune, Intune’u MDM yetkiliniz olarak isteyip istemediğinizi onaylamanızı ister. Mobil cihazları yönetmek için Intune kullanmak istiyorsanız onay kutusunu işaretleyin ve ardından **Evet**'i seçin.

## <a name="enroll-your-test-devices-into-intune"></a>Sınama cihazlarınızı Intune'a kaydetme

Bu kılavuzda bir Android telefonla bir Apple iPad kaydedeceğiz ve bu bölümün sonunda [Intune'da cihaz kaydı hakkında daha fazla bilgi](#Learn-more-about-device-enrollment) konusuna bağlantılar sağlayacağız.
### <a name="android"></a>Android
**Google Play**’den erişilebilen Microsoft Corporation’ın [Intune Şirket Portalı](http://go.microsoft.com/fwlink/p/?LinkId=386612) uygulamasını yükleyin ve ücretsiz deneme sürümüne kaydolduğunuzda [oluşturduğunuz Intune kullanıcı kimlik bilgileriyle](sign-up-for-30-day-trial-microsoft-intune.md#add-users) oturum açın.

### <a name="ios"></a>iOS
Kullanıcılar iOS cihazlarını kaydetmeden önce, Intune'u bu cihazları yönetmek üzere ayarlamanız gerekir.

1. **Sertifika imzalama isteği alma**<br/>
Yönetici hesabınızla Intune’da oturum açın ve **Yönetim** > **Mobil Cihaz Yönetimi** > **iOS ve Mac OS X** > **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifika isteğini indir**’i seçin. Sertifika imzalama isteği (.csr) dosyasını yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır. <!--- screen shot--->
2.  **Bir Apple Anında İletilen Bildirim Servisi sertifikası alma**<BR/>
[Apple Anında İletilen Bildirim Sertifikaları Portalı](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2)'na gidin ve .csr dosyasını kullanarak APNs sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. **Apple’ın Anında İletilen Sertifika Portalı’nda Karşıya Yükle**’yi seçtikten sonra, APNs için kullanılamayan bir .json dosyası alırsınız. İndirme işlemini tamamlayın, Üçüncü Taraf Sunucular için Sertifikalar için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’i seçin.

 APNs (.pem) sertifikasını indirin ve dosyayı yerel olarak kaydedin. Bu Apple kimliği daha sonra APNs sertifikanızı yenilemek için kullanılır.
3.  **APNs sertifikasını Intune'a ekleme**<BR/>
Microsoft Intune yönetim konsolunda **Yönetim** > **Mobil Cihaz Yönetimi** > **iOS ve Mac OS X** > **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifikasını karşıya yükle**’yi seçin. Sertifika (.pem) dosyasına gidin, **Aç**’ı seçin ve Apple kimliğinizi girin. APNs sertifikası ile. Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.
4.  **Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın.**<br/>
Son kullanıcı kayıt talimatları için bkz. [iOS cihazınızı Intune'a kaydetme](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) veya [Mac OS X cihazınızı Intune'a kaydetme](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x). Kayıt işlemi kullanıcıları neler bekleyebilecekleri ve BT yöneticilerinin görebileceği ve göremeyeceği cihaz içeriği hakkında bilgilendirir.


### <a name="learn-more-about-device-enrollment"></a>Cihaz kaydı hakkında daha fazla bilgi edinin

Intune aşağıdaki cihaz platformlarını destekler:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Cihaz yönetimini etkinleştirme gereksinimleri, yönetmek istediğiniz platformlarda bağlıdır.
- **Android** mobil cihazlar kullanıcıların Google Play’den erişilebilen [Şirket Portalı uygulamasını kullanarak kaydolmalarına](/intune/deploy-use/set-up-android-management-with-microsoft-intune) imkan tanır. Intune’da ek yapılandırma gerekmez.
- [**iOS ve Mac OS X için kurulum gereksinimleri**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [**Windows Phone için kurulum gereksinimleri**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcıları ve cihazları düzenlemek için grup oluşturma](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)



<!--HONumber=Jan17_HO1-->


