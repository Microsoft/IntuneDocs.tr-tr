---
title: Telekom gider yönetimi hizmeti ayarlama
titleSuffix: Microsoft Intune
description: Intune'u Saaswedo telekom gider yönetimi hizmetiyle tümleştirin.
keywords: Saaswedo
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7514aef9ee94e774ff2e2fca1008966a92a24e0e
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842023"
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Intune'da telekom gider yönetimi hizmeti ayarlama
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, şirkete ait mobil cihazlarda veri kullanımından kaynaklanan telekom giderlerini yönetmenizi sağlar. Bu özelliği etkinleştirmek için Intune, üçüncü taraf yazılım geliştiricisi Saaswedo’nun [Datalert telekom gider yönetimi](http://datalert.biz/get-started) çözümüyle tümleştirilmiştir. Datalert, telekom veri kullanımını yönetmenize olanak tanıyan gerçek zamanlı bir telekom gider yönetimi yazılımıdır. Intune tarafından yönetilen cihazlarınızda pahalı ve beklenmedik düzeyde fazla veri ve dolaşım kullanımlarını önlemeye yardımcı olur.

Intune'un Datalert’le tümleştirilmesi, dolaşım ve yerel veri kullanım sınırlarını merkezi olarak ayarlamanıza, izlemenize ve zorunlu tutmanıza olanak tanır. Sınırlar önceden tanımlanmış eşikleri aştığında otomatik uyarılar tetiklenir. Tek tek son kullanıcılara veya son kullanıcı gruplarına farklı eylemler (dolaşımı devre dışı bırakma veya eşiği aşma gibi) uygulanacak şekilde hizmeti yapılandırabilirsiniz. Datalert yönetim konsolundan veri kullanım ve izleme bilgilerini içeren raporlar sağlanır.

Aşağıdaki diyagramda, Intune’un Datalert ile nasıl tümleştirildiği gösterilmektedir.

  ![Intune ile Datalert’ün tümleştirme diyagramı](./media/tem-datalert-intune-solution-diagram.png)

Intune ile Datalert hizmetini kullanabilmeniz için, önce Datalert konsolunda ve Intune’da ayarları yapılandırmalısınız. Datalert hizmeti ve Intune için bağlantının açılması gerekir. Bağlantının Datalert tarafı etkinleştirilir ancak Intune tarafı etkinleştirilmezse, Intune iletişimi alır ancak yoksayar.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Samsung Knox
- iOS 8.0 ve üzeri

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Intune'a abonelik ve Azure portalına erişim.
- Datalert telekom gider yönetimi hizmeti için abonelik

## <a name="list-of-telecom-expense-management-providers"></a>Telekom gider yönetimi sağlayıcıları listesi

Intune şu anda aşağıdaki telekom gider yönetimi sağlayıcılarıyla tümleştirilmiştir:

[Saaswedo Datalert telekom gider yönetimi hizmeti](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Tümleştirilmiş Intune ve Datalert çözümünü dağıtma

Başlamadan önce, bir Intune ve bir Datalert telekomünikasyon gider yönetimi hizmeti aboneliğine sahip olduğunuzdan emin olun.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>1. adım: Datalert hizmetini Microsoft Intune bağlama

1. Datalert yönetim konsolunda yönetici kimlik bilgilerinizle oturum açın.

2. Datalert yönetim konsolunda **Ayarlar** sekmesine ve sonra **MDM yapılandırması**’na gidin.

3. Sayfanın altında bulunan ve sayfadaki ayarları değiştirmenize yarayan **Engeli Kaldır**’ı seçin.

4. **Intune / Datalert Bağlantısı** bölümünde **Sunucu MDM** için **Microsoft Intune**’u seçin.    

5. **Azure Active Directory etki alanı** için Azure kiracı kimliğinizi girin ve ardından **Bağlantı**’yı seçin.

    **Bağlantı**’yı seçtiğinizde Datalert hizmeti, Intune ile Datalert arasında mevcut bir bağlantı olmadığından emin olmak için Intune’u denetler. Birkaç saniye sonra Microsoft oturum açma sayfası ve ardından Datalert Azure kimlik doğrulaması görüntülenir.

6. Microsoft kimlik doğrulaması sayfasında **Kabul Et**’i seçin. Datalert **teşekkür ederiz** sayfasına yönlendirilirsiniz ve bu sayfa birkaç saniye sonra kapatılır. Datalert bağlantıyı doğrular ve doğrulanan öğe listesinin yanında yeşil onay işaretleri görüntülenir. Doğrulama başarısız olursa, kırmızı renkli bir ileti görürsünüz ve yardım için Datalert Desteği'ne başvurmanız gerekir.

    Aşağıdaki ekran görüntüsünde, bağlantı başarılı olduktan sonra görmeniz gereken yeşil onay işaretleri gösterilir.

   ![Başarılı bağlantıyı gösteren Datalert sayfası](./media/tem-datalert-connection.png)

7. **Datalert App / ADAL Onayı** bölümünde, ayarı **Açık** olarak belirleyin. Microsoft kimlik doğrulaması sayfasında **Kabul Et**’i seçin. Datalert **teşekkür ederiz** sayfasına yönlendirilirsiniz ve bu sayfa birkaç saniye sonra kapatılır. Datalert bağlantıyı doğrular ve doğrulanan öğe listesinin yanında yeşil onay işaretleri görüntülenir. Doğrulama başarısız olursa, kırmızı renkli bir ileti görürsünüz ve yardım için Datalert Desteği'ne başvurmanız gerekir.    

    Aşağıdaki ekran görüntüsünde, bağlantı başarılı olduktan sonra görmeniz gereken yeşil onay işaretleri gösterilir.

   ![Başarılı bağlantıyı gösteren Datalert sayfası](./media/tem-datalert-adal-consent.png)

8. **MDM Profil yönetimi (isteğe bağlı)** bölümünde ayarı **Açık** olarak belirleyerek Datalert’in ilke ayarlamanıza yardımcı olması için Intune’daki kullanılabilir profilleri okumasına izin verin. Microsoft kimlik doğrulaması sayfasında **Kabul Et**’i seçin. Datalert **teşekkür ederiz** sayfasına yönlendirilirsiniz ve bu sayfa birkaç saniye sonra kapatılır. Datalert bağlantıyı doğrular ve doğrulanan öğe listesinin yanında yeşil onay işaretleri görüntülenir. Doğrulama başarısız olursa, kırmızı renkli bir ileti görürsünüz ve yardım için Datalert Desteği'ne başvurmanız gerekir.    

    Aşağıdaki ekran görüntüsünde, bağlantı başarılı olduktan sonra görmeniz gereken yeşil onay işaretleri gösterilir.

   ![Başarılı bağlantıyı gösteren Datalert sayfası](./media/tem-datalert-mdm-profiles.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>2. adım: Telekom Gider Yönetimi özelliğinin etkin olup olmadığını denetleme ıntune

Yukarıdaki 1. Adımı tamamladıktan sonra, bağlantınızın otomatik olarak etkinleştirilmiş olması ve bağlantı durumunun Azure portalında **Etkin** olarak gösterilmesi gerekir. Aşağıdaki adımlar, **Etkin** durumunu nasıl denetleyebileceğinizi göstermektedir.

1. [Azure portal](https://portal.azure.com) oturum açın.

2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.

3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.

4. **Cihaz yapılandırması** bölmesinde **Kurulum** > **Telecom Gider Yönetimi**’ni seçin.

   Sayfanın en üstünde **Etkin** bağlantı durumu olup olmadığına bakın.

   ![Datalert bağlantı durumunu Etkin olarak gösteren Intune sayfası](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>3. adım: Datalert uygulamasını şirket için kaydedilmiş cihazlara dağıtma

Yalnızca şirkete ait satırlardan veri kullanımının toplanmasını güvence altına almak için, iki işlem yapmalısınız:
- Intune'da cihaz kategorileri oluşturma
- yalnızca şirket telefonları için Datalert uygulamasını hedefleme.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Cihaz kategorileri ve kategorilere eşlenen cihaz grupları tanımlama

Kuruluş gereksinimlerinize bağlı olarak, en az iki cihaz kategorisi (örneğin, Kurumsal ve Kişisel) oluşturun. Ardından, her kategori için dinamik cihaz grupları oluşturun. Gerektikçe kuruluşunuz için daha fazla kategori oluşturabilirsiniz.

Bu kategoriler, kayıt sırasında kullanıcılara gösterilir. Kullanıcıların hangi kategoriyi seçtiğine bağlı olarak, kaydedilen cihaz ilgili cihaz grubuna taşınır. Cihaz kategorileri oluşturma adımları için bkz. [Cihazları gruplara eşleme](device-group-mapping.md).

  ![İlke ekle bölmesinin ekran görüntüsü](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>Intune'da Datalert uygulamasını oluşturma

Her platform için Intune'da Datalert uygulamasını oluşturmak üzere şu adımları izleyin. Aşağıdaki adımlarda örnek olarak iOS kullanılmaktadır.

1. [Azure portalının](https://portal.azure.com) **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.

2. **İstemci uygulamaları** bölmesinde **Yönet** > **Uygulamalar**’ı seçin.

3. Uygulama eklemek için **Ekle**’yi seçin.

4. Uygulama türünü seçin. Örneğin, iOS için **iOS Mağazası Uygulaması**’nı seçersiniz.

5. **App Store’da Ara** kısmında arama penceresine **Datalert** yazarak Datalert uygulamasını arayın.

6. **Datalert** uygulamasını ve sonra **Tamam**’ı seçin.

   ![İlke ekle bölmesinin ekran görüntüsü](./media/tem-select-app-from-apple-app-store.png)

7. iOS için uygulama oluşturmak üzere kalan adımları tamamlayın.

   ![İlke ekle bölmesinin ekran görüntüsü](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>Datalert uygulamasını kurumsal cihaz grubuna atama

1. **İstemci uygulamalar - Uygulamalar** bölmesinde, önceki adımda oluşturduğunuz iOS Datalert uygulamasını seçin.

2. **Uygulamalar** bölmesinde **Yönet** > **Atamalar**'ı seçin.

3. **Grup ekle**’yi seçin ve şirket cihaz grubunu seçme adımlarını izleyin.

4. Bir grup için uygulama yüklemeyi, gerekli mi yoksa isteğe bağlı mı yapacağınızı seçin. Aşağıdaki örnek ekran görüntüsü, yüklemenin gerekli olduğu durumu gösterir; bu durumda kullanıcıların, cihazlarını kaydettikten sonra Datalert uygulamasını yüklemeleri gerekir.

   ![İlke ekle bölmesinin ekran görüntüsü](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>4. adım: Şirket tarafından ödenen telefon hatlarını Datalert konsoluna ekleme

Intune ve Datalert hizmetlerini birbiriyle iletişim kuracak şekilde yapılandırdınız. Şimdi şirket tarafından ödenen telefon hatlarınızı Datalert konsoluna eklemeniz ve şebeke kullanımı veya gezici kullanım ihlallerine yönelik eşikler ve eylemler tanımlamanız gerekir. Şirket tarafından ödenen telefon hatlarını Datalert konsoluna el ile ekleyebileceğiniz gibi, cihaz Intune’a kaydedildikten sonra bunları otomatik olarak da ekleyebilirsiniz.

Bu öğeleri ayarlamak için [Microsoft Intune için Datalert kurulumu sayfasına](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup)) giderek **Ayarlar** sekmesi altındaki kurulum sihirbazında sunulan adımları izleyin.

  ![İlke ekle bölmesinin ekran görüntüsü](./media/tem-add-phone-lines-to-datalert-console.png)


Datalert hizmeti artık etkindir; veri kullanımını izlemeye ve yapılandırılmış kullanım sınırlarını aşan cihazlarda hücresel ve dolaşım verilerini devre dışı bırakmaya başlar.

## <a name="client-enrollment-experience"></a>İstemci kayıt deneyimi
İstemci kayıt deneyimi için aşağıdakilere bakın:
-   [iOS cihazınızı telekom gider yönetimine kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Android cihazınızı telekom gider yönetimine kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>Datalert hizmetini kapatma

Azure portalında Datalert hizmetini devre dışı bırakırsanız:

- Geçmişte kullanım sınırlarının ihlal edilmesinden dolayı cihazlara uygulanmış olan tüm eylemler geri alınır.
- Artık kullanıcıların veri erişimi ve dolaşımı engellenmez.
- Intune hizmetten gelen sinyalleri almaya devam eder ancak bunları yoksayar.

**Hizmeti kapatmak için**

1. Azure portalının **Telekom Gider Yönetimi** bölmesinde **Devre Dışı Bırak**’ı seçin.

2. **Kaydet**’i seçin.

## <a name="viewing-data-usage-and-roaming-reports"></a>Veri kullanımı ve dolaşım raporlarını görüntüleme

Veri kullanım raporlaması şu anda yalnızca Saaswedo’nun Datalert yönetim konsolunda sağlanmaktadır.

Son kullanıcılarınızın Datalert uygulamasını yüklemek için izleyeceği yönergeler yakında eklenecektir.
