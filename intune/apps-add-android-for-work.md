---
title: Kurumsal Android cihazlar için yönetilen Google Play uygulamaları atama
titleSuffix: Microsoft Intune
description: Uygulama eşitlemeyi ve kurumsal Android cihazlar için yönetilen Google Play Mağazası'ndan atamayı öğrenin.
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
ms.openlocfilehash: 1ad07252ccf10fefdd1c753ab103eb91a2789c39
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587357"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Yönetilen Google Play uygulamaları Intune ile Android kuruluş cihazlarının ekleyin

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Kurumsal Android iş profili cihazları, ayrılmış/bilgi noktası cihazları için bir program olan ve tam olarak yönetilen cihazlar. Android iş profili cihazları için Android kurumsal, kişisel uygulamaları ve verileri iş uygulama ve verilerinden ayıran bir özellik ve hizmet kümesidir. Android iş profili, kullanıcılar Android cihazlarını iş için kullandıklarında ek yönetim seçenekleri ve gizlilik sağlar. Intune, iş bilgileriyle kişisel bilgilerin ayrı olmasını sağlamak için Android iş profili cihazlarına uygulamalar ve ayarlar dağıtmanıza yardımcı olur. Android iş profili cihazları için yüklediğiniz tüm uygulamalar Yönetilen Google Play mağazasından gelir. Android iş profili cihazlarına uygulama atama işlemi, standart Android cihazlara uygulama atamaktan farklıdır. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız. Daha sonra uygulama, Azure portalının **Lisanslı uygulamalar** düğümünde görünür ve uygulamanın atamasını diğer uygulamalarda olduğu gibi yaparsınız.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, bunları aşağıdaki gibi atayabilirsiniz:
- Google Play Store'daki özel bir alanda uygulama yayımlamanıza olanak tanıyan bir Google Developer hesabı için kaydolun.
- Uygulamaları Intune ile eşitleyin.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android iş profillerini Azure portalın **Cihaz kaydı** iş yüküyle birlikte çalışacak şekilde yapılandırdığınızdan emin olun. Daha fazla bilgi için bkz. [Android cihazları kaydetme](android-work-profile-enroll.md).

>[!NOTE]
>Microsoft Intune ile çalışırken Microsoft Edge veya Google Chrome tarayıcılarını kullanmanızı öneririz.

## <a name="managed-google-play-app-type"></a>Yönetilen Google Play uygulaması türü
**Yönetilen Google Play** uygulama türü, özellikle eklemenize olanak sağlayacaktır [yönetilen Google Play uygulamaları](https://play.google.com/work/search?q=microsoft&c=apps) ıntune. Intune Yöneticisi olarak, artık göz atabilir, arama, onaylama, eşitleme ve onaylı bir yönetilen Google Play uygulamaları Intune içerisindeki atayın.  Yönetilen Google Play konsolunu için ayrı olarak göz atmak artık ihtiyacınız ve yeniden kimlik doğrulamaya zorlayabilir artık yok.

> [!NOTE]
> Bir yönetilen Google Play uygulaması Intune ile eşitlemek tercih ediyorsanız, bkz [bir yönetilen Google Play uygulaması Intune ile eşitleyin](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## <a name="add-a-managed-google-play-app-using-intune"></a>Intune kullanarak bir yönetilen Google Play uygulaması ekleme

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. İçinde **Intune** bölmesinde **istemci uygulamaları** > **uygulamaları**.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. İçinde **uygulama türü** açılır kutusunda, select **yönetilen Google Play**.
7. Seçin **yönetilen Google Play - onaylama** yönetilen Google Play kataloğunu açmak için.
8. Dahil etmek istediğiniz uygulamaları aramak için arama kutusunu kullanın.
9. Tıklayın **Onayla** uygulamayı yönetilen Google play onaylamak ve **Onayla** uygulama izinlerini kabul etmek için.
10. Seçin **uygulama yeni izinler istediğinde onaylı durumda tut** onay Ayarları penceresi ve ardından **Kaydet**. Bu seçeneği seçmezseniz, uygulama geliştiricisi güncelleştirilmiş yayımlarsa yeni izinlerin el ile onaylamanız gerekir.  Bu yüklemeleri ve güncelleştirmeleri izinler onaylanana kadar durdurmak için uygulamanın neden olur. Bu nedenle, otomatik olarak yeni izinleri onaylamak için bir seçenek belirlemeniz önerilir. 
11. Tıklayın **Tamam** onayladığınız uygulamalarını içerecek şekilde.
12. Tıklayın **eşitleme** üzerinde **uygulama** bölmesinde yönetilen Google Play hizmeti ile eşitlenemedi.

## <a name="synchronize-a-managed-google-play-app-with-intune-alternative"></a>Yönetilen Google Play uygulaması (diğer) Intune ile eşitleme
Intune ile doğrudan Intune kullanarak eklemek yerine bir yönetilen Google Play uygulaması eşitlemek isterseniz, aşağıdaki adımları kullanın.

> [!IMPORTANT]
> Aşağıda sağlanan bilgiler, yukarıda açıklandığı gibi Intune kullanarak bir yönetilen Google Play uygulaması eklemek için alternatif bir yöntemdir.

### <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından uygulama eşitleme

1. [Yönetilen Google Play mağazası](https://play.google.com/work)’na gidin. Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
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

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesinde, **Kurulum** altında **Yönetilen Google Play**’i seçin.
5. **Yönetilen Google Play** bölmesinde **Yenile**’yi seçin.  
    Bu sayfa son eşitlemenin zamanını ve durumunu güncelleştirir.
6. **İstemci uygulamaları** iş yükü bölmesinde **Uygulamalar**’ı seçin.  
    Yeni eklenen Yönetilen Google Play uygulaması görüntülenir.

## <a name="assigning-the-managed-google-play-app"></a>Yönetilen Google Play uygulaması atama

Ne zaman uygulama görüntülenir **uygulama lisanslarını** düğümünün **istemci uygulamaları** yapabilecekleriniz iş yükü bölmesinde [yalnızca diğer herhangi bir uygulamayı atadığınız gibi atayabilirsiniz](/intune-azure/manage-apps/deploy-apps) atayarak uygulamaya Kullanıcı grupları.

Uygulama atandıktan sonra hedeflediğiniz cihazlara yüklenir. Cihazın kullanıcısından yüklemeyi onaylaması istenmez.

## <a name="manage-android-enterprise-app-permissions"></a>Android kurumsal uygulama izinlerini yönetme
Android kurumsal, uygulamaları Intune ile eşitlemeden ve kullanıcılarınıza atamadan önce, yönetilen Google Play web konsolunda onaylamanızı gerektirir. Android iş profili bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulama izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir. Kullanıcılar uygulamayı yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, sizin bu izinleri anlamanız önemlidir.

Bir uygulama geliştiricisi bir uygulamanın yeni bir sürümüyle izinleri güncelleştirdiğinde, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Önceki sürümü çalıştıran cihazlar, uygulamayı kullanmaya devam edebilir. Ancak uygulama, yeni izinler onaylanana kadar yükseltilmez. Yüklü olmadığı cihazlarda, uygulama, yeni izinler onaylanana kadar yüklenmez.

### <a name="update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret edin. Google Play’i onaylanmış bir uygulama için yeni izinler gerekli olduğunda, size veya başkalarına e-posta göndermesi için yapılandırabilirsiniz. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımları izleyerek yeni izinleri denetleyin:

1. [Google Play](https://play.google.com/work)’e gidin.
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. **Güncelleştirmeler** sekmesini seçin ve herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğine bakın.  
    Listelenen tüm uygulamalar yeni izinler gerektirir ve uygulama, yeni izinler uygulanana kadar atanmaz.

Alternatif olarak, Google Play’i uygulama izinlerini uygulama başına otomatik olarak yeniden onaylamak üzere yapılandırabilirsiniz.

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından bir iş kolu uygulaması ile çalışma

1. Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Google Play Developer Console](https://play.google.com/apps/publish)’da oturum açın.  
    İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
2. Konsolda **Yeni uygulama ekle**’yi seçin.
3. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.

    ![Uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirme](media/restrict.png)

    Bu işlem, uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirir. Uygulama, genel Google Play mağazasında kullanılabilir olmayacaktır.

    Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Developer Console Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
4. Uygulamanızı yayımladıktan sonra Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Yönetilen Google Play mağazası](https://play.google.com/work)’nda oturum açın.
5. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamanın görüntülendiğini onaylayın.  
    Uygulama, Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="delete-managed-google-play-apps"></a>Yönetilen Google Play uygulamaları silin
Gerektiğinde, yönetilen Google Play uygulamaları Microsoft Intune silebilirsiniz. Yönetilen Google Play uygulama silmek için Azure portal ve select Intune açın **istemci uygulamaları** > **uygulamaları**. Uygulama listesinden yönetilen Google Play uygulaması'nın sağındaki üç nokta (...) seçin ve ardından **Sil** görüntülenen listeden. Uygulama listesinden bir yönetilen Google Play uygulaması sildiğinizde, yönetilen Google Play uygulaması otomatik olarak onaylanmadı.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
