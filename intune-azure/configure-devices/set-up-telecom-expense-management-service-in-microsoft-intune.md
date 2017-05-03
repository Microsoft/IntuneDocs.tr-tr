---
title: "Telekom gider yönetimi hizmeti ayarlama"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Saaswedo telekom gider yönetimi hizmetini Intune ile tümleştirilecek şekilde yapılandırın."
keywords: Saaswedo
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a981b0253f56d66292ce77639faf4beba8832a9e
ms.openlocfilehash: b0d0ad102942c65ac3988ea4659b34b397289126
ms.lasthandoff: 04/19/2017

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Intune Azure önizlemesinde telekom gider yönetimi hizmetini ayarlama
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune, şirkete ait mobil cihazlarda veri kullanımından kaynaklanan telekom giderlerini yönetmenizi sağlar. Bu özelliği etkinleştirmek için Intune, üçüncü taraf yazılım geliştiricisi Saaswedo’nun Datalert telekom gider yönetimi çözümüyle tümleştirilmiştir. Datalert, telekom veri kullanımını yönetmenize ve Intune tarafından yönetilen cihazlarınızda veri ve dolaşımda yüksek maliyetli ve beklenmedik fazla kullanımları önlemenize olanak tanıyan gerçek zamanlı bir telekom gider yönetimi yazılımıdır.

Intune'un Datalert’le tümleştirilmesi, sınırlar önceden tanımlanmış eşikleri aştığında verilen otomatik uyarıları kullanarak, dolaşım ve yerel veri kullanım sınırlarını merkezi olarak ayarlamanıza, izlemenize ve zorunlu tutmanıza olanak tanır. Kullanıcıların eşiği aşması durumunda, tek tek son kullanıcılara veya son kullanıcı gruplarına dolaşımı devre dışı bırakma gibi farklı eylemler uygulanacak şekilde hizmeti yapılandırabilirsiniz. Datalert yönetim konsolundan veri kullanım ve izleme bilgilerini içeren raporlar sağlanır.

Aşağıdaki diyagramda, Intune’un Datalert ile nasıl tümleştirildiği gösterilmektedir.

  ![Intune ile Datalert’ün tümleştirme diyagramı](../media/tem-datalert-intune-solution-diagram.png)

Intune ile Datalert hizmetini kullanabilmeniz için, önce Datalert konsolunda ve Intune’da ayarları yapılandırmalısınız. Datalert hizmeti ve Intune için bağlantının açılması gerekir. Bağlantının Datalert tarafı etkinleştirilir ancak Intune tarafı etkinleştirilmezse, Intune iletişimi alır ancak yoksayar.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Samsung Knox
- iOS 8.0 ve üzeri

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Intune aboneliği ve şu anda genel önizlemedeki Azure portalına erişim.
- Datalert telekom gider yönetimi hizmeti için abonelik

## <a name="list-of-telecom-expense-management-providers"></a>Telekom gider yönetimi sağlayıcıları listesi

Intune şu anda aşağıdaki telekom gider yönetimi sağlayıcılarıyla tümleştirilmiştir:

[Saaswedo Datalert telekom gider yönetimi hizmeti](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Tümleştirilmiş Intune ve Datalert çözümünü dağıtma

Başlamadan önce, bir Intune ve bir Datalert telekomünikasyon gider yönetimi hizmeti aboneliğine sahip olduğunuzdan emin olun.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>1. Adım: Datalert hizmetini Microsoft Intune’a bağlama

1. Datalert yönetim konsolunda yönetici kimlik bilgilerinizle oturum açın.

2. Datalert yönetim konsolunda **Ayarlar** sekmesine ve sonra **MDM yapılandırması**’na gidin.

3. Sayfada ayarları girebilmek için **Engellemeyi Kaldır**’ı seçin.

4. **Sunucu MDM** için **Microsoft Intune**’u seçin.

5. **Azure AD etki alanı** için Azure kiracı kimliğinizi girin ve ardından **Bağlantı** düğmesini seçin.

    **Bağlantı**’nın seçilmesi, önceden Intune ile Datalert bağlantılarının olmadığından emin olmak için Intune ile Datalert hizmetini denetler. Birkaç saniye sonra Microsoft oturum açma sayfası görüntülenir ve onun ardından Datalert Azure kimlik doğrulaması gelir.

6. Microsoft kimlik doğrulaması sayfasında **Kabul Et**’i seçin. Datalert “teşekkür ederiz” sayfasına yönlendirilirsiniz ve bu sayfa birkaç saniye sonra kapatılır. Datalert bağlantıyı doğrular ve doğrulanan öğe listesinin yanında yeşil onay işaretleri görüntülenir. Doğrulama başarısız olursa, kırmızı bir ileti görürsünüz. Böyle bir durum olursa, yardım için Datalert Desteği’ne başvurun.

    Aşağıdaki ekran görüntüsünde, bağlantı başarılı olduktan sonra görmeniz gereken yeşil onay işaretleri gösterilir.

  ![Bağlantının başarılı olduğunu gösteren Datalert sayfası](../media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>2. Adım: Telekomünikasyon gider yönetimi özelliğinin Intune’da etkin olup olmadığını denetleme

Yukarıdaki 1. Adımı tamamladıktan sonra, bağlantınızın otomatik olarak etkinleştirilmiş olması ve bağlantı durumunun Azure portalında **Etkin** olarak gösterilmesi gerekir. Aşağıdaki adımlar, **Etkin** durumunu nasıl denetleyebileceğinizi göstermektedir.

1. Azure portalında oturum açın.

2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.

4. **Cihaz Yapılandırması** dikey penceresinde **Kurulum** > **Telecom Gider Yönetimi**’ni seçin.

   Sayfanın en üstünde **Etkin** bağlantı durumu olup olmadığına bakın.

  ![Datalert bağlantı durumunu Etkin olarak gösteren Azure portalı](../media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>3. Adım: Datalert uygulamasını şirket için kaydedilmiş cihazlara dağıtma

Veri kullanımı bilgilerinin yalnızca şirkete ait hatlardan toplandığından emin olmak için, Intune’da cihaz kategorileri oluşturduktan sonra Datalert uygulamasını yalnızca şirkete ait telefonlara hedeflemeniz gerekir. Aşağıdaki alt bölümlerde yer alan adımları tamamlayın.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Cihaz kategorileri ve kategorilere eşlenen cihaz grupları tanımlama

Kuruluş gereksinimlerinize bağlı olarak, en az iki cihaz kategorisi (örneğin, Kurumsal ve Kişisel) oluşturmanız ve her kategori için dinamik cihaz grupları oluşturmanız gerekir. Gerektikçe kuruluşunuz için daha fazla kategori oluşturabilirsiniz.

Bu kategoriler, kayıt sırasında kullanıcılara gösterilir. Kullanıcıların hangi kategoriyi seçtiğine bağlı olarak, kaydedilen cihaz ilgili cihaz grubuna taşınır. Cihaz kategorileri oluşturma adımları için bkz. [Cihazları gruplara eşleme](https://docs.microsoft.com/intune-azure/enroll-devices/how-to-use-device-group-mapping).

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Intune'da Datalert uygulamasını oluşturma

Her platform için Intune'da Datalert uygulamasını oluşturmak üzere şu adımları izleyin. Aşağıdaki adımlarda örnek olarak iOS kullanılmaktadır.

1. Azure portalının **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.

2. **Uygulamaları Yönet** dikey penceresinde, **Yönet** > **Uygulamalar**’ı seçin.

3. Uygulama eklemek için **Ekle**’yi seçin.

4. Uygulama türünü seçin. Örneğin, iOS için **iOS Mağazası Uygulaması**’nı seçersiniz.

5. **App Store’da Ara** kısmında arama penceresine **Datalert** yazarak Datalert uygulamasını arayın.

6. **Datalert** uygulamasını ve sonra **Tamam**’ı seçin.

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/tem-select-app-from-apple-app-store.png)

7. iOS için uygulama oluşturmak üzere kalan adımları tamamlayın.

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Datalert uygulamasını kurumsal cihaz grubuna atama

1. Önceki adımda oluşturduğunuz iOS Datalert uygulamasını seçin.

2. **Uygulamalar** dikey penceresinde **Yönet** > **Atamalar**’a gidin.

3. **Grupları seçin**’i belirleyip şirket cihaz grubunu seçme adımlarını izleyin.

4. Bir grup için uygulama yüklemeyi, gerekli mi yoksa isteğe bağlı mı yapacağınızı seçin. Aşağıdaki örnek ekran görüntüsü, yüklemenin gerekli olduğu durumu gösterir; bu durumda kullanıcıların, cihazlarını kaydettikten sonra Datalert uygulamasını yüklemeleri gerekir.

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>4. Adım: Şirket tarafından ödenen telefon hatlarını Datalert konsoluna ekleme

Intune ve Datalert hizmetlerini birbiriyle iletişim kuracak şekilde yapılandırdınız. Şimdi şirket tarafından ödenen telefon hatlarınızı Datalert konsoluna eklemeniz ve şebeke kullanımı veya gezici kullanım ihlallerine yönelik eşikler ve eylemler tanımlamanız gerekir. Şirket tarafından ödenen telefon hatlarını Datalert konsoluna el ile ekleyebilir veya cihaz Intune’a kaydedildikten sonra hatların otomatik olarak eklenmesini sağlayabilirsiniz.

Bu öğeleri ayarlamak için [Microsoft Intune için Datalert kurulumu sayfasına](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup) giderek **Ayarlar** sekmesi altındaki kurulum sihirbazında sunulan adımları izleyin.

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/tem-add-phone-lines-to-datalert-console.png)


Datalert hizmeti artık etkindir; veri kullanımını izlemeye ve yapılandırılmış kullanım sınırlarını aşan cihazlarda hücresel ve dolaşım verilerini devre dışı bırakmaya başlar.

## <a name="client-enrollment-experience"></a>İstemci kayıt deneyimi
İstemci kayıt deneyimi için aşağıdakilere bakın:
-    [iOS cihazınızı telekom gider yönetimine kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-    [Android cihazınızı telekom gider yönetimine kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Datalert hizmetini kapatma

Azure portalında Datalert hizmetini devre dışı bırakırsanız:

- Geçmişte kullanım sınırlarının ihlal edilmesinden dolayı cihazlara uygulanmış olan tüm eylemler geri alınır.
- Artık kullanıcıların veri erişimi ve dolaşımı engellenmez.
- Intune hizmetten gelen sinyalleri almaya devam eder ancak bunları yoksayar.

**Hizmeti kapatmak için**

1. Azure portalının **Telekom Gider Yönetimi** dikey penceresinde **Devre Dışı Bırak**’ı seçin.

2. **Kaydet**’i seçin.

## <a name="viewing-data-usage-and-roaming-reports"></a>Veri kullanımı ve dolaşım raporlarını görüntüleme

Veri kullanım raporlaması şu anda yalnızca Saaswedo’nun Datalert yönetim konsolunda sağlanmaktadır.

Son kullanıcılarınızın Datalert uygulamasını yüklemek için izleyeceği yönergeler yakında eklenecektir.

