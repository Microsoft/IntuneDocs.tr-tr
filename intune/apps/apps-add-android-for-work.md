---
title: Yönetilen Google Play uygulamalarını Android Kurumsal cihazlarına atama
titleSuffix: Microsoft Intune
description: Yönetilen Google Play mağazasından Android Kurumsal cihazlarına uygulama eşitlemeyi ve atamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 126ea5a1798252f29e988553edfea462eff2fd7e
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256467"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Intune ile Yönetilen Google Play uygulamalarını Android Kurumsal cihazlarına ekleme

Yönetilen Google Play, Google 'ın kurumsal uygulama mağazası ve Android Enterprise uygulamalarının tek kaynağıdır. Intune 'u, herhangi bir Android kurumsal senaryosunda (iş profili, adanmış ve tam olarak yönetilen kayıtlar dahil) yönetilen Google Play aracılığıyla uygulama dağıtımını düzenlemek için kullanabilirsiniz. Intune 'a yönetilen Google Play uygulamalarını nasıl ekleyeceğiniz, Android uygulamalarının Android olmayan kurumsal için nasıl eklendiğine göre farklılık gösterir. Mağaza uygulamaları, iş kolu (LOB) uygulamaları ve Web uygulamaları, içinde onaylanır veya yönetilen Google Play eklenir ve ardından, Istemci uygulamaları listesinde gözükmek üzere Intune 'a eşitlenir. Istemci uygulamaları liste listesinde göründükleri Google Play her türlü uygulamayı başka bir uygulamayla aynı şekilde yönetebilirsiniz.

Intune kiracınızı yönetilen Google Play bağlama sırasında Android kurumsal yönetimini yapılandırıp kullanmanızı kolaylaştırmak için Intune, Intune yönetici konsoluna dört ortak Android kurumsal ilgili uygulamayı otomatik olarak ekler. Dört uygulama şunlardır:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** -Android kurumsal tam olarak yönetilen senaryolar için kullanılır. Bu uygulama, cihaz kayıt işlemi sırasında tam olarak yönetilen cihazlara otomatik olarak yüklenir.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** -iki öğeli doğrulama kullanırsanız hesaplarınızda oturum açmanıza yardımcı olur. Bu uygulama, cihaz kayıt işlemi sırasında tam olarak yönetilen cihazlara otomatik olarak yüklenir.
- **[Intune şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** -uygulama koruma ILKELERI (uygulama) ve Android kurumsal iş profili senaryoları için kullanılır.
- **[Yönetilen giriş ekranı](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise)** -Android kurumsal adanmış çok uygulama bilgi noktası senaryolarında kullanılır. BT yöneticileri, bu uygulamayı birden çok uygulama bilgi noktası senaryolarında kullanılacak adanmış cihazlara yüklemek için bir atama oluşturması gerekir.

>[!NOTE]
>Son Kullanıcı Android kurumsal tam olarak yönetilen cihazını kaydettiğinde, Intune Şirket Portalı uygulaması otomatik olarak yüklenir ve uygulama simgesi son kullanıcıya görünür olabilir. Son Kullanıcı Intune Şirket Portalı uygulamasını başlatmayı denerse, Son Kullanıcı Microsoft Intune uygulamasına yönlendirilir ve Şirket Portalı uygulama simgesi daha sonra gizlenir.

## <a name="before-you-start"></a>Başlamadan önce
- Intune kiracınızı yönetilen Google Play bağladığınızdan emin olun.  Daha fazla bilgi için bkz. [Intune hesabınızı yönetilen Google Play hesabınıza bağlama](../enrollment/connect-intune-android-enterprise.md).
- İş profili cihazlarını kaydetmek istiyorsanız, Intune ve Android iş profillerinin Azure portal **cihaz kayıt** iş yükünde birlikte çalışacak şekilde yapılandırdığınızdan emin olun. Daha fazla bilgi için bkz. [Android cihazları kaydetme](../enrollment/android-work-profile-enroll.md).

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

## <a name="managed-google-play-app-types"></a>Yönetilen Google Play uygulama türleri
Yönetilen Google Play kullanılabilecek üç tür uygulama vardır:

- **Yönetilen Google Play Mağazası uygulaması** -genel olarak, Play Store açık olan uygulamalar. Yönetmek istediğiniz uygulamalara göz atarak bu uygulamaları Intune 'da yönetin, bunları onaylama ve sonra Intune 'a eşitleme.
- **Yönetilen Google Play özel uygulama** -bu, Intune yöneticileri tarafından yönetilen Google Play yayımlanan lob uygulamalardır.  Bu uygulamalar özeldir ve yalnızca Intune kiracınız tarafından kullanılabilir. Bu, LOB uygulamalarının yönetilen Google Play ve Android Kurumsal ile yönetilmesi ve dağıtılması.
- **Yönetilen Google Play web bağlantısı** -Android kurumsal cihazlara DAĞITILABILIR ve BT Yöneticisi tarafından tanımlanan simgelerle Web bağlantıları. Bunlar, normal uygulamalar gibi cihazın uygulama listesindeki cihazlarda görünürler.

## <a name="managed-google-play-store-apps"></a>Yönetilen Google Play Mağazası uygulamaları
Intune ile yönetilen Google Play Mağazası uygulamalarını taramak ve onaylamak için iki yol vardır:

1. Doğrudan Intune konsolunda-Intune 'da barındırılan bir görünümde mağaza uygulamalarına gözatıp onaylayın. Bu, doğrudan Intune konsolunda açılır ve farklı bir hesapla yeniden kimlik doğrulaması yapmanız gerekmez.
1. Yönetilen Google Play konsolu 'nda, isteğe bağlı olarak, yönetilen Google Play konsolunu doğrudan açabilir ve uygulamayı burada onaylayabilirsiniz. Daha fazla bilgi için bkz. [Intune Ile yönetilen Google Play uygulamasını eşitleme](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune) .  Bu, Intune kiracınızı yönetilen Google Play bağlamak için kullandığınız hesabı kullanarak ayrı bir oturum açma gerektirir.

### <a name="add-a-managed-google-play-store-app-directly-in-the-intune-console"></a>Doğrudan Intune konsoluna yönetilen bir Google Play Mağazası uygulaması ekleme

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında, **yönetilen Google Play uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Yönetilen Google Play** App Store görüntülenir.

    > [!NOTE]
    > Yönetilen Google Play Mağazası uygulamalarına gözatagöstermek için Intune kiracı hesabınızın Android Kurumsal hesabınıza bağlı olması gerekir. Daha fazla bilgi için bkz. [Intune hesabınızı yönetilen Google Play hesabınıza bağlama](../enrollment/connect-intune-android-enterprise.md).

5. Uygulama ayrıntılarını görüntülemek için bir uygulama seçin.
6. Uygulamayı görüntüleyen sayfada **Onayla**' ya tıklayın. Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister.
7. Uygulama izinlerini kabul edip devam etmek için **Onayla**’yı seçin.
8. Uygulama **onay ayarları** sekmesinde **Yeni Izinler istediğinde onaylandı kalsın** ' ı seçin ve ardından **bitti**' ye tıklayın. 

    > [!IMPORTANT]
    > Bu seçeneği kullanmazsanız, uygulama geliştirici güncelleştirme yayımladığında tüm yeni izinleri el ile onaylamanız gerekecektir. Bu durum izinler onaylanana kadar uygulama yüklemelerinin ve güncelleştirmelerinin durdurulmasına neden olur. Dolayısıyla yeni izinlerin otomatik olarak onaylanması için bu seçeneğin kullanılması önerilir. 

9. Uygulamayı seçmek için **Seç** ' e tıklayın.
10. Uygulamayı yönetilen Google Play hizmetiyle eşitlemek için dikey pencerenin en üstündeki **Eşitle** ' ye tıklayın.
11. Uygulama listesini güncelleştirmek ve yeni eklenen uygulamayı göstermek için **Yenile** ' ye tıklayın.

### <a name="add-a-managed-google-play-store-app-in-the-managed-google-play-console-alternative"></a>Yönetilen Google Play konsoluna yönetilen bir Google Play Mağazası uygulaması ekleme (alternatif)
Yönetilen Google Play uygulamasını doğrudan Intune kullanarak eklemek yerine Intune'la eşitlemeyi tercih ediyorsanız aşağıdaki adımları kullanın.

> [!IMPORTANT]
> Aşağıda sağlanan bilgiler, yukarıda açıklanan Intune kullanarak Yönetilen Google Play uygulamasını ekleme işlemine alternatif bir yöntemdir.

1. [Yönetilen Google Play mağazası](https://play.google.com/work)’na gidin. Intune ve Android Kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak atamak istediğiniz uygulamayı mağazada arayın ve seçin.
3. Uygulamayı görüntüleyen sayfada **Onayla**' ya tıklayın.  
    Aşağıdaki örneklerde Microsoft Excel uygulaması seçilmiştir.

    ![Yönetilen Google Play mağazasında Onayla düğmesi](./media/apps-add-android-for-work/approve.png)

   Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister.

4. Uygulama izinlerini kabul edip devam etmek için **Onayla**’yı seçin.

    ![Uygulama izinleri için Onayla düğmesi](./media/apps-add-android-for-work/approve-app-permissions.png)

5. Yeni uygulama izin isteklerini işlemek için bir seçenek belirleyin ve daha sonra **Kaydet**’i seçin.

    ![Yeni uygulama izni isteklerini işleme seçenekleri](./media/apps-add-android-for-work/approve-app-settings.png)

    Uygulama onaylanır ve BT yönetici konsolunuzda görüntülenir. Daha sonra, [Android iş profili uygulamasını Intune Ile eşitleyebilirsiniz](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

## <a name="managed-google-play-private-lob-apps"></a>Yönetilen Google Play özel (LOB) uygulamaları

Yönetilen Google Play LOB uygulamaları eklemenin iki yolu vardır:

1. Doğrudan Intune konsolunda, doğrudan Intune içinde yalnızca uygulama APK ve bir başlığı göndererek LOB uygulamaları eklemenize olanak tanır. Bu yöntem, bir Google Geliştirici hesabınızın olmasını gerektirmez ve Google 'ı bir geliştirici olarak kaydetmek için ücret ödemenizi gerektirmez.  Bu yöntem daha basittir ve önemli ölçüde azaltılmış adımlara sahiptir ve LOB uygulamalarını on dakikadan kısa bir süre içinde yönetim için kullanılabilir hale getirir.
1. Google Play Geliştirici konsolunda-bir Google geliştirici hesabınız varsa veya yalnızca Google Play Geliştirici konsolunda kullanılabilir olan gelişmiş dağıtım özelliklerini yapılandırmak istiyorsanız (ek uygulama ekran görüntüleri ekleme gibi), [Google Play Geliştirici konsolunu](https://play.google.com/apps/publish)kullanabilirsiniz. 

### <a name="managed-google-play-private-lob-app-publishing-directly-in-the-intune-console"></a>Yönetilen Google Play özel (LOB) uygulaması doğrudan Intune konsolunda yayımlanıyor

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında, **yönetilen Google Play uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Yönetilen Google Play** App Store, Intune içinde görüntülenir.
5. Google Play penceresinde **özel uygulamalar** ( *kilit* simgesinin yanında) seçeneğini belirleyin. 
6. Yeni bir uygulama eklemek için sağ alt köşedeki **"+"** düğmesine tıklayın.
7. Bir uygulama **başlığı** ekleyin ve APK uygulama paketini Ekle **' ye tıklayın** .
8. **Oluştur**'a tıklayın.
9. Uygulama eklemeyi bitirdiğinizde, yönetilen Google Play bölmesini kapatın.
10. Yönetilen Google Play hizmetiyle eşitlemek için **Uygulama** bölmesinde **Eşitle**'ye tıklayın. 

    > [!NOTE]
    > Özel uygulamaların, eşitleme için kullanılabilir olması birkaç dakika sürebilir. Uygulama ilk kez eşitleme gerçekleştirirken görünmüyorsa, birkaç dakika bekleyip yeni bir eşitleme başlatın.

SSS dahil olmak üzere yönetilen Google Play özel uygulamalar hakkında daha fazla bilgi için bkz. Google 'ın Destek makalesi: https://support.google.com/googleplay/work/answer/9146439

>[!IMPORTANT]
>Bu yöntem kullanılarak eklenen özel uygulamalar hiçbir şekilde herkese açık hale getirilmez. Bu yayımlama seçeneğini yalnızca, bu uygulamanın kuruluşunuza her zaman özel olduğundan eminseniz kullanın.

### <a name="managed-google-play-private-lob-app-publishing-using-the-google-developer-console"></a>Google Geliştirici Konsolu kullanılarak yönetilen Google Play özel (LOB) uygulama yayımlama

1. Intune ile Android Kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Google Play Developer Console](https://play.google.com/apps/publish)’da oturum açın.  
    İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
2. Konsolda **Yeni uygulama ekle**’yi seçin.
3. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.

    ![Uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirme](./media/apps-add-android-for-work/restrict.png)

    Bu işlem, uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirir. Uygulama, genel Google Play mağazasında kullanılabilir olmayacaktır.

    Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Developer Console Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
4. Uygulamanızı yayımladıktan sonra Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Yönetilen Google Play mağazası](https://play.google.com/work)’nda oturum açın.
5. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamanın görüntülendiğini onaylayın.  
    Uygulama, Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="managed-google-play-web-links"></a>Yönetilen Google Play web bağlantıları

Yönetilen Google Play web bağlantıları, diğer Android uygulamalarıyla aynı şekilde yüklenebilir ve yönetilebilir. Bir cihaza yüklendiğinde, bu kullanıcılar, yüklemiş oldukları diğer uygulamaların yanı sıra kullanıcının uygulama listesinde görünür. Dokunulduğunda, cihazın tarayıcısında başlatılacaktır.

Web bağlantıları, Microsoft Edge veya dağıtmayı seçtiğiniz başka bir tarayıcı uygulamasıyla açılır. Web bağlantılarının düzgün şekilde açabilmek için en az bir tarayıcı uygulamasını cihazlara dağıttığınızdan emin olun. Ancak, Web bağlantıları için kullanılabilen tüm **görüntüleme** seçenekleri (tam ekran, tek başına ve en az kullanıcı arabirimi) yalnızca Chrome tarayıcısıyla çalışır. 

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında, **yönetilen Google Play uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Yönetilen Google Play** App Store, Intune içinde görüntülenir.
5. Google Play penceresinde **Web Apps** ( *Dünya* simgesinin yanında) seçeneğini belirleyin.
6. Yeni bir uygulama eklemek için sağ alt köşedeki **"+"** düğmesine tıklayın.
7. Uygulama **başlığı**, Web uygulaması **URL 'si**ekleyin, uygulamanın nasıl görüntüleneceğini seçin ve bir uygulama simgesi seçin.
8. **Oluştur**'a tıklayın.
9. Uygulama eklemeyi bitirdiğinizde, yönetilen Google Play bölmesini kapatın.
10. Yönetilen Google Play hizmetiyle eşitlemek için **Uygulama** bölmesinde **Eşitle**'ye tıklayın. 

    > [!NOTE]
    > Web uygulamalarının eşitleme için kullanılabilir olması birkaç dakika sürebilir. Uygulama ilk kez eşitleme gerçekleştirirken görünmüyorsa, birkaç dakika bekleyip yeni bir eşitleme başlatın.

## <a name="sync-a-managed-google-play-app-with-intune"></a>Yönetilen Google Play uygulamalarını Intune ile eşitleme

Mağazadan bir uygulamayı onayladıysanız ve **uygulamalar** iş yükünde görmüyorsanız, şu şekilde bir anında eşitleme zorlayın:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3.  > , **yönetilen Google Play** **bağlayıcı ve belirteçler** > **Kiracı Yönetimi** > **uygulamalar** ' ı seçin.
5. **Yönetilen Google Play** bölmesinde **Yenile**’yi seçin.  
    Bu sayfa son eşitlemenin zamanını ve durumunu güncelleştirir.
6. Microsoft Endpoint Manager Yönetim merkezinde **tüm uygulamalar** > **uygulamalar** ' ı seçin.  
    Yeni eklenen Yönetilen Google Play uygulaması görüntülenir.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Yönetilen Google Play uygulamasını Android Kurumsal iş profili cihazlarına atama

Uygulama, **uygulamalar** iş yükü bölmesinin **uygulama lisansları** düğümünde görüntülendiğinde, uygulamayı kullanıcı gruplarına atayarak [bunu başka bir uygulamayı atadığınız gibi atayabilirsiniz](/intune-azure/manage-apps/deploy-apps) .

Uygulamayı atadıktan sonra, hedeflediğiniz kullanıcıların cihazlarına yüklenir (veya yükleme için kullanılabilir). Cihazın kullanıcısından yüklemeyi onaylaması istenmez. Android Kurulsal iş profili cihazları hakkında daha fazla bilgi için bkz. [Android Kurumsal iş profili cihazlarının kaydını ayarlama](../enrollment/android-work-profile-enroll.md). 

> [!NOTE] 
> Yalnızca atanan uygulamalar, son kullanıcı için yönetilen Google Play deposunda görünür. Bu nedenle, yönetici tarafından yönetilen Google Play uygulamalar ayarlanırken gerçekleştirilecek önemli bir adımdır.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Yönetilen Google Play uygulamasını Android Kurumsal tam olarak yönetilen cihazlarına atama

[Android Kurumsal tam olarak yönetilen cihazları](../enrollment/android-fully-managed-enroll.md), tek kullanıcıyla ilişkilendirilmiş ve yalnızca iş için kullanılan (kişisel amaçlarla kullanılmayan) şirkete ait cihazlardır. Tam olarak yönetilen cihazların kullanıcıları kendilerine sağlanan şirket uygulamalarını yönetilen Google Play uygulamasından cihazlarına alabilirler.

Varsayılan olarak, Android Kurumsal tam olarak yönetilen cihazı çalışanların kuruluş tarafından onaylanmamış uygulamaları yüklemesine izin vermez. Ayrıca çalışanlar yüklü uygulamalardan hiçbirini ilkeye aykırı olarak kaldıramaz. Kullanıcıların yalnızca Yönetilen Google Play mağazasındaki onaylanmış uygulamalara erişmek yerine tüm Google Play mağazasına erişip uygulama yüklemesine izin vermek isterseniz, **Google Play Store'daki tüm uygulamalara izin ver** ayarını **İzin Ver** olarak belirleyebilirsiniz. Bu ayarla kullanıcı şirket hesabını kullanarak Google Play Store'daki tüm uygulamalara erişebilir ama satın alımlar sınırlanmış olabilir. Kullanıcıların cihaza yeni hesaplar eklemesine izin vererek sınırlı satın alma kısıtlamasını kaldırabilirsiniz. Bunu yaptığınızda son kullanıcılar kişisel hesaplarını kullanarak Google Play Store'dan uygulama satın alabilir, ayrıca uygulama için satın alımlar yapabilir. Daha fazla bilgi için bkz. [Intune kullanarak özelliklere izin vermek veya bunları kısıtlamak için Android Kurumsal cihaz ayarları](../configuration/device-restrictions-android-for-work.md). 

> [!NOTE]
> Tam olarak yönetilen cihazların eklenmesi sırasında Microsoft Intune uygulamasıyla Microsoft Authenticator uygulaması bu cihazlara gerekli uygulamalar olarak yüklenecektir. Bu uygulamaların otomatik olarak yüklenmesi, koşullu erişim desteği sağlar ve Microsoft Intune uygulama kullanıcıları uyumluluk sorunlarını görüp çözümleyebilir. 

## <a name="manage-android-enterprise-app-permissions"></a>Android Kurumsal uygulama izinlerini yönetme
Android Kurumsal, uygulamaları Intune ile eşitlemeden ve kullanıcılarınıza atamadan önce, yönetilen Google Play web konsolunda onaylamanızı gerektirir. Android Kurumsal bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulama izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir. Kullanıcılar uygulamayı yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, sizin bu izinleri anlamanız önemlidir.

Bir uygulama geliştiricisi bir uygulamanın yeni bir sürümüyle izinleri güncelleştirdiğinde, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Önceki sürümü çalıştıran cihazlar, uygulamayı kullanmaya devam edebilir. Ancak uygulama, yeni izinler onaylanana kadar yükseltilmez. Yüklü olmadığı cihazlarda, uygulama, yeni izinler onaylanana kadar yüklenmez. 

### <a name="update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret edin. Google Play’i onaylanmış bir uygulama için yeni izinler gerekli olduğunda, size veya başkalarına e-posta göndermesi için yapılandırabilirsiniz. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımları izleyerek yeni izinleri denetleyin:

1. [Google Play](https://play.google.com/work)’e gidin.
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. **Güncelleştirmeler** sekmesini seçin ve herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğine bakın.  
    Listelenen tüm uygulamalar yeni izinler gerektirir ve uygulama, yeni izinler uygulanana kadar atanmaz.

Alternatif olarak, Google Play’i uygulama izinlerini uygulama başına otomatik olarak yeniden onaylamak üzere yapılandırabilirsiniz.

## <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices"></a>Android Kurumsal iş profili cihazları için ek Yönetilen Google Play uygulaması raporlaması

Android kurumsal iş profili cihazlarına dağıtılan yönetilen Google Play uygulamaları için, Intune kullanarak bir cihazda yüklü olan uygulamanın durum ve sürüm numarasını görüntüleyebilirsiniz. 

## <a name="delete-managed-google-play-apps"></a>Yönetilen Google Play uygulamalarını silme
Gerektiğinde, yönetilen Google Play uygulamalarını Microsoft Intune'dan silebilirsiniz. Yönetilen bir Google Play uygulamasını silmek için, Azure portal Microsoft Intune açın ve **tüm uygulamalar** > **uygulamalar** ' ı seçin. Uygulama listesinden, yönetilen Google Play uygulamasının sağ tarafındaki üç noktayı (...) seçin ve görüntülenen listeden **Sil**'i seçin. Uygulama listesinden yönetilen Google Play uygulamasını sildikten sonra, yönetilen Google Play uygulamasının onayı otomatik olarak kaldırılır.

> [!NOTE]
> Bir uygulama onaylanmamış veya yönetilen Google Play deposundan silinirse, Intune istemci uygulamalar listesinden kaldırılmaz. Bu, uygulama onaylanmamış olsa bile bir kaldırma ilkesini kullanıcılara hedeflemesini sağlar.

## <a name="android-enterprise-system-apps"></a>Android Kurumsal sistem uygulamaları

Android kurumsal [ayrılmış cihazları](../enrollment/android-kiosk-enroll.md) veya [tam olarak yönetilen cihazlar](../enrollment/android-fully-managed-enroll.md)için bir Android kurumsal sistem uygulamasını etkinleştirebilirsiniz. Android kurumsal sistem uygulaması ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune Android kurumsal sistem uygulamaları ekleme](apps-ae-system.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
