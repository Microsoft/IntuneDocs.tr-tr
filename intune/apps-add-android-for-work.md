---
title: Yönetilen Google Play uygulamalarını Android Kurumsal cihazlarına atama
titleSuffix: Microsoft Intune
description: Yönetilen Google Play mağazasından Android Kurumsal cihazlarına uygulama eşitlemeyi ve atamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b977d60c982a43e4465cd451cc2fc24b4e69f4cf
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898116"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Intune ile Yönetilen Google Play uygulamalarını Android Kurumsal cihazlarına ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Kurumsal, Android iş profili cihazları, ayrılmış/bilgi noktası cihazları ve tam olarak yönetilen cihazlara yönelik bir programdır. Android iş profili cihazları için Android Kurumsal, kişisel uygulamaları ve verileri iş uygulama ve verilerinden ayıran bir özellik ve hizmet kümesidir. Android Kurumsal, kullanıcılar Android cihazlarını iş için kullandıklarında ek yönetim seçenekleri ve gizlilik sağlar. Intune, iş bilgileriyle kişisel bilgilerin ayrı olmasını sağlamak için Android iş profili cihazlarına uygulamalar ve ayarlar dağıtmanıza yardımcı olur. Android iş profili cihazları için yüklediğiniz tüm uygulamalar Yönetilen Google Play mağazasından gelir. Android iş profili cihazlarına uygulama atama işlemi, standart Android cihazlara uygulama atamaktan farklıdır. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız. Daha sonra uygulama, Azure portalının **Lisanslı uygulamalar** düğümünde görünür ve uygulamanın atamasını diğer uygulamalarda olduğu gibi yaparsınız.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, bunları aşağıdaki gibi atayabilirsiniz:
- Google Play Store'daki özel bir alanda uygulama yayımlamanıza olanak tanıyan bir Google Developer hesabı için kaydolun.
- Uygulamaları Intune ile eşitleyin.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android iş profillerini Azure portalın **Cihaz kaydı** iş yüküyle birlikte çalışacak şekilde yapılandırdığınızdan emin olun. Daha fazla bilgi için bkz. [Android cihazları kaydetme](android-work-profile-enroll.md).

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

## <a name="managed-google-play-app-type"></a>Yönetilen Google Play uygulama türü
**Yönetilen Google Play** uygulama türü Intune'a özel olarak [Yönetilen Google Play uygulamalarını](https://play.google.com/work/search?q=microsoft&c=apps) eklemenize olanak tanır. Intune yöneticisi olarak şimdi Intune'un içinden onaylanmış yönetilen Google Play uygulamalarına göz atabilir, bunları arayabilir, onaylayabilir, eşitleyebilir ve atayabilirsiniz.  Artık ayrıca yönetilen Google Play konsoluna göz atmanız ve yeniden kimlik doğrulaması yapmanız gerekmez.

> [!NOTE]
> Yönetilen Google Play uygulamasını Intune'la eşitlemeyi tercih ediyorsanız, bkz. [Yönetilen Google Play uygulamasını Intune'la eşitleme](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## <a name="add-a-managed-google-play-app-using-intune"></a>Intune kullanarak Yönetilen Google Play uygulaması ekleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları** > **Uygulamalar**'ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama türü** açılan kutusunda **Yönetilen Google Play**'i seçin.
7. Yönetilen Google Play kataloğunu açmak için **Yönetilen Google Play - Onayla**'yı seçin.
8. Eklemek istediğiniz uygulamaları aramak için arama kutusunu kullanın.
9. Yönetilen Google Play'de uygulamayı onaylamak için **Onayla**'ya tıklayın ve ardından uygulama izinlerini kabul etmek için **Onayla**'ya tıklayın.
10. Onay Ayarları penceresinde **Uygulama yeni izinler istediğinde onaylı durumda tut** öğesini seçin ve **Kaydet**'e tıklayın. Bu seçeneği kullanmazsanız, uygulama geliştirici güncelleştirme yayımladığında tüm yeni izinleri el ile onaylamanız gerekecektir. Bu durum izinler onaylanana kadar uygulama yüklemelerinin ve güncelleştirmelerinin durdurulmasına neden olur. Dolayısıyla yeni izinlerin otomatik olarak onaylanması için bu seçeneğin kullanılması önerilir. 
11. Onayladığınız uygulamaların eklenmesi için **Tamam**'a tıklayın.
12. Yönetilen Google Play hizmetiyle eşitlemek için **Uygulama** bölmesinde **Eşitle**'ye tıklayın.

## <a name="synchronize-a-managed-google-play-app-with-intune-alternative"></a>Yönetilen Google Play uygulamalarını Intune ile eşitleme (Alternatif)
Yönetilen Google Play uygulamasını doğrudan Intune kullanarak eklemek yerine Intune'la eşitlemeyi tercih ediyorsanız aşağıdaki adımları kullanın.

> [!IMPORTANT]
> Aşağıda sağlanan bilgiler, yukarıda açıklanan Intune kullanarak Yönetilen Google Play uygulamasını ekleme işlemine alternatif bir yöntemdir.

### <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından uygulama eşitleme

1. [Yönetilen Google Play mağazası](https://play.google.com/work)’na gidin. Intune ve Android Kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak atamak istediğiniz uygulamayı mağazada arayın ve seçin.
3. Uygulamanın görüntülendiği sayfada **Onayla**’yı seçin.  
    Aşağıdaki örneklerde Microsoft Excel uygulaması seçilmiştir.

    ![Yönetilen Google Play mağazasında Onayla düğmesi](media/approve.png)

   Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister.

4. Uygulama izinlerini kabul edip devam etmek için **Onayla**’yı seçin.

    ![Uygulama izinleri için Onayla düğmesi](media/approve-app-permissions.png)

5. Yeni uygulama izin isteklerini işlemek için bir seçenek belirleyin ve daha sonra **Kaydet**’i seçin.

    ![Yeni uygulama izni isteklerini işleme seçenekleri](media/approve-app-settings.png)

    Uygulama onaylanır ve BT yönetici konsolunuzda görüntülenir. Ardından [Android iş profili uygulamasını Intune ile eşitleyebilirsiniz](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

### <a name="sync-a-managed-google-play-app-with-intune"></a>Yönetilen Google Play uygulamalarını Intune ile eşitleme

Mağazadan bir uygulamayı onayladıysanız ve **İstemci uygulamaları** iş yükünün **Lisanslı uygulamalar** düğümünde göremiyorsanız, aşağıdaki gibi bir anında eşitleme zorlayın:

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesinde, **Kurulum** altında **Yönetilen Google Play**’i seçin.
5. **Yönetilen Google Play** bölmesinde **Yenile**’yi seçin.  
    Bu sayfa son eşitlemenin zamanını ve durumunu güncelleştirir.
6. **İstemci uygulamaları** iş yükü bölmesinde **Uygulamalar**’ı seçin.  
    Yeni eklenen Yönetilen Google Play uygulaması görüntülenir.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Yönetilen Google Play uygulamasını Android Kurumsal iş profili cihazlarına atama

Uygulama, **İstemci uygulamaları** iş yükü bölmesinin **Uygulama lisansları** düğümünde görüntülendiğinde, bunu [diğer herhangi bir uygulamayı atadığınız gibi atayabilir](/intune-azure/manage-apps/deploy-apps), başka bir deyişle uygulamayı kullanıcı gruplarına atayabilirsiniz.

Uygulama atandıktan sonra hedeflediğiniz cihazlara yüklenir. Cihazın kullanıcısından yüklemeyi onaylaması istenmez. Android Kurulsal iş profili cihazları hakkında daha fazla bilgi için bkz. [Android Kurumsal iş profili cihazlarının kaydını ayarlama](android-work-profile-enroll.md).

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Yönetilen Google Play uygulamasını Android Kurumsal tam olarak yönetilen cihazlarına atama

[Android Kurumsal tam olarak yönetilen cihazları](android-fully-managed-enroll.md), tek kullanıcıyla ilişkilendirilmiş ve yalnızca iş için kullanılan (kişisel amaçlarla kullanılmayan) şirkete ait cihazlardır. Tam olarak yönetilen cihazların kullanıcıları kendilerine sağlanan şirket uygulamalarını yönetilen Google Play uygulamasından cihazlarına alabilirler.

Varsayılan olarak, Android Kurumsal tam olarak yönetilen cihazı çalışanların kuruluş tarafından onaylanmamış uygulamaları yüklemesine izin vermez. Ayrıca çalışanlar yüklü uygulamalardan hiçbirini ilkeye aykırı olarak kaldıramaz. Kullanıcıların yalnızca Yönetilen Google Play mağazasındaki onaylanmış uygulamalara erişmek yerine tüm Google Play mağazasına erişip uygulama yüklemesine izin vermek isterseniz, **Google Play Store'daki tüm uygulamalara izin ver** ayarını **İzin Ver** olarak belirleyebilirsiniz. Bu ayarla kullanıcı şirket hesabını kullanarak Google Play Store'daki tüm uygulamalara erişebilir ama satın alımlar sınırlanmış olabilir. Kullanıcıların cihaza yeni hesaplar eklemesine izin vererek sınırlı satın alma kısıtlamasını kaldırabilirsiniz. Bunu yaptığınızda son kullanıcılar kişisel hesaplarını kullanarak Google Play Store'dan uygulama satın alabilir, ayrıca uygulama için satın alımlar yapabilir. Daha fazla bilgi için bkz. [Intune kullanarak özelliklere izin vermek veya bunları kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md). 

> [!NOTE]
> Tam olarak yönetilen cihazların eklenmesi sırasında Microsoft Intune uygulamasıyla Microsoft Authenticator uygulaması bu cihazlara gerekli uygulamalar olarak yüklenecektir. Bu uygulamaların otomatik olarak yüklenmesi koşullu erişim desteği sağlar ve Microsoft Intune uygulaması kullanıcıları uyumluluk sorunlarını görebilir ve çözebilir. 

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

Android Kurumsal iş profili cihazlarına dağıtılan Yönetilen Google Play uygulamaları için, cihazda yüklü olan uygulamanın sürüm numarasını görüntüleyebilirsiniz. Bu yalnızca gerekli uygulamalar için geçerlidir. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından bir iş kolu uygulaması ile çalışma

1. Intune ile Android Kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Google Play Developer Console](https://play.google.com/apps/publish)’da oturum açın.  
    İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
2. Konsolda **Yeni uygulama ekle**’yi seçin.
3. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.

    ![Uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirme](media/restrict.png)

    Bu işlem, uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirir. Uygulama, genel Google Play mağazasında kullanılabilir olmayacaktır.

    Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Developer Console Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
4. Uygulamanızı yayımladıktan sonra Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Yönetilen Google Play mağazası](https://play.google.com/work)’nda oturum açın.
5. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamanın görüntülendiğini onaylayın.  
    Uygulama, Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="delete-managed-google-play-apps"></a>Yönetilen Google Play uygulamalarını silme
Gerektiğinde, yönetilen Google Play uygulamalarını Microsoft Intune'dan silebilirsiniz. Yönetilen Google Play uygulamasını silmek için Azure portalında Microsoft Intune'u açın ve **İstemci uygulamaları** > **Uygulamalar**'ı seçin. Uygulama listesinden, yönetilen Google Play uygulamasının sağ tarafındaki üç noktayı (...) seçin ve görüntülenen listeden **Sil**'i seçin. Uygulama listesinden yönetilen Google Play uygulamasını sildikten sonra, yönetilen Google Play uygulamasının onayı otomatik olarak kaldırılır.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
