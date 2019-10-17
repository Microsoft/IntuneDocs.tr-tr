---
title: Microsoft Intune - Azure’da eSIM veri bağlantılarını etkinleştirme | Microsoft Docs
description: Farklı mobil İnternet tarifeleri kullanarak İnternete ve verilere erişim sağlamak için eSIM ekleyin veya kullanın. Intune’da etkinleştirme kodlarını ekleyin veya içeri aktarın ve bir yapılandırma profili kullanarak bu etkinleştirme kodlarını atayın. Ayrıca eSIM profillerini izleyebilir ve eSIM etkinleştirilmiş cihazların durumunu denetleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 84103c6264431773ab5928f1da22c37a80cc9036
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492718"
---
# <a name="configure-esim-cellular-profiles-in-intune---public-preview"></a>Intune - Genel önizleme’de eSIM hücresel profilleri yapılandırma

eSIM, katıştırılmış bir SIM yongasıdır ve [Surface LTE Pro](https://www.microsoft.com/surface/business/surface-pro) gibi eSIM özellikli bir cihazdaki hücresel veri bağlantısı üzerinden İnternete bağlanmanızı sağlar. eSIM ile mobil operatörünüzden SIM kart almanız gerekmez. Genel gezgin olarak mobil operatörler ve veri planları arasında geçiş yaparak sürekli bağlantı sağlayabilirsiniz.

Örneğin işiniz için bir mobil İnternet tarifeniz ve farklı bir cep telefonu operatöründe kişisel kullanım için başka bir mobil İnternet tarifeniz olduğunu varsayalım. Seyahat ederken o alandaki cep telefonu operatörlerini ve mobil İnternet tarifelerini bulup İnternete erişebilirsiniz.

Intune’da cep telefonu operatörünüz tarafından sağlanan tek kullanımlık etkinleştirme kodlarını içeri aktarabilirsiniz. eSIM modülünde hücresel mobil İnternet tarifeleri yapılandırmak için etkinleştirme kodlarını eSIM özellikli cihazlarınıza dağıtın. Intune etkinleştirme kodunu yüklediğinde eSIM donanım modülü cep telefonu operatörüyle iletişim kurmak için etkinleştirme kodundaki verileri kullanır. İşlem tamamlandığında eSIM profili cihaza indirilir ve hücresel etkinleştirme için yapılandırılır.

Intune kullanarak cihazlarınıza eSIM dağıtmak için aşağıdakiler gereklidir:

- Surface LTE gibi **eSIM özellikli cihazlar** için: Bkz.[Cihazınız eSIM’i destekliyorsa](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data). İsterseniz, [bilinen bazı eSIM özellikli cihazlar](#esim-capable-devices) (bu makalede) listesine de bakabilirsiniz.
- Intune'da kayıtlı ve MDM tarafından yönetilen **Windows 10 Fall Creators Update bilgisayarı** (1709 veya üzeri)
- Cep telefonu operatörünüz tarafından sağlanan **etkinleştirme kodları**. Bu tek kullanımlık etkinleştirme kodları Intune’a eklenir ve eSIM özellikli cihazlarınıza dağıtılır. eSIM etkinleştirme kodları almak için cep telefonu operatörünüze başvurun.

## <a name="deploy-esim-to-devices---overview"></a>eSIM’i cihazlara dağıtma - genel bakış

eSIM’i cihazlara dağıtmak için Yönetici aşağıdaki görevleri tamamlar:

1. Cep telefonu operatörünüz tarafından sağlanan etkinleştirme kodlarını içeri aktarma
2. eSIM özellikli cihazlarınızı içeren bir Azure Active Directory (Azure AD) cihaz grubu oluşturma
3. Azure AD grubunuzu içeri aktarılan abonelik havuzunuza atama
4. Dağıtımı izleme

Bu makale bu adımlarda size yol gösterir.

## <a name="esim-capable-devices"></a>eSIM özellikli cihazlar

Aşağıdaki cihazların eSIM özellikli olduğu bildirilmiştir ve bugün satılmaktadır. Ayrıca [cihazınızın eSIM’i destekleyip desteklemediğini](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data) kontrol edin.

- Acer Swift 7
- Asus NovoGo TP370QL
- Asus TP401
- Asus Transformer Mini T103
- HP Elitebook G5
- HP Envy x2
- HP Probook G5
- Lenovo Miix 630
- Lenovo T480
- Samsung Galaxy Book
- Surface Pro LTE
- HP Spectre Folio 13
- Lenovo Yoga C630

## <a name="step-1-add-cellular-activation-codes"></a>1\. Adım: Hücresel etkinleştirme kodlarını ekleme

Hücresel etkinleştirme kodları cep telefonu operatörünüz tarafından virgülle ayrılmış bir dosyada (csv) sağlanır. Bu dosyayı aldığınızda aşağıdaki adımları izleyerek Intune’a ekleyin:

1. [Azure portalı](https://portal.azure.com/)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **eSIM hücresel profilleri** > **Ekle**’yi seçin.
4. Etkinleştirme kodlarınızı içeren CSV dosyasını seçin.
5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="csv-file-requirements"></a>CSV dosyası gereksinimleri

Etkinleştirme kodlarını içeren csv dosyasıyla çalışırken cep telefonu operatörünüzün aşağıdaki gereksinimleri karşıladığından emin olun:

- Dosya csv biçiminde (dosyaadı.csv) olmalıdır.
- Dosya yapısı, kesim bir biçime uymalıdır. Aksi takdirde, içeri aktarma başarısız olur. Intune, içeri aktarırken dosyaları denetler ve hata bulunması durumunda içeri aktarma başarısız olur.
- Etkinleştirme kodları tek bir kez kullanılır. Önceden kullandığınız etkinleştirme kodlarını içeri aktarmanız önerilmez çünkü aynı ya da başka cihaza dağıtılırken soruna neden olabilir.
- Her dosya tek bir cep telefonu operatörüne ve tüm etkinleştirme kodları aynı faturalama planına özel olmalıdır. Intune etkinleştirme kodlarını hedef cihazlara rastgele dağıtır. Belirli bir etkinleştirme kodunu hangi cihazın alacağı garanti edilemez.
- Tek bir csv dosyasında en fazla 1000 etkinleştirme kodu içeri aktarılabilir.

### <a name="csv-file-example"></a>CSV dosyası örneği

1. CSV dosyasının ilk satırı ve ilk hücresi cep telefonu operatörü eSIM etkinleştirme hizmetinin URL’sidir. SM-DP+ (Abonelik Yöneticisi Veri Hazırlama sunucusu) olarak adlandırılır. URL, virgül içermeyen bir tam etki alanı adı (FQDN) olmalıdır.
2. İkinci satır ve onun altındaki tüm satırlar iki değer içeren benzersiz tek kullanımlık etkinleştirme kodlarıdır:

    1. İlk sütun benzersiz ICCID’dir (SIM yongasının tanımlayıcısı)
    2. İkinci sütun yalnızca virgülle ayrılmış (sonda virgül bulunmaz) Eşleşen Kimliktir. Aşağıdaki örneğe bakın:

        ![Cep telefonu operatörü etkinleştirme kodunun örnek csv dosyası](./media/esim-device-configuration/url-activation-code-examples.png)

3. CSV dosyasının adı Azure portalında hücresel abonelik havuzunun adı olur. Önceki görüntüde dosya adı `UnlimitedDataSkynet.csv`‘dir. Bu nedenle Intune `UnlimitedDataSkynet.csv` abonelik havuzunu adlandırır:

    ![Hücresel abonelik havuzu, etkinleştirme kodu örneği csv dosya adını alır](./media/esim-device-configuration/subscription-pool-name-csv-file.png)

## <a name="step-2-create-an-azure-ad-device-group"></a>2\. Adım: Azure AD cihazı grubunu oluşturma

eSIM özellikli cihazları içeren bir Cihaz grubu oluşturun. [Grup ekleme](../fundamentals/groups-add.md) altında adımlar listelenir.

> [!NOTE]
> - Yalnızca cihazlar hedeflenir: kullanıcılar hedeflenmez.
> - eSIM cihazlarınızı içeren bir statik Azure AD cihazı grubu oluşturmanızı öneririz. Grup kullanarak, yalnızca eSIM cihazlarını hedefleyebilirsiniz.

## <a name="step-3-assign-esim-activation-codes-to-devices"></a>3\. Adım: Cihazlara eSIM etkinleştirme kodları atama

eSIM cihazlarınızı içeren Azure AD grubuna profili atayın.

1. [Azure portalında](https://portal.azure.com/) **Tüm Hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **eSIM hücresel** > **Profiller**’i seçin.
3. Profil listesinde, atamak istediğiniz eSIM hücresel abonelik havuzunu ve ardından **Atamalar**’ı seçin.
4. Grupları **Dahil Etmeyi** veya **Dışlamayı** seçin ve sonra da grupları belirtin.

    ![Profili atamak için cihaz grubunu dahil etme](./media/esim-device-configuration/include-exclude-groups.png)

5. Gruplarınızı seçtiğinizde, bir Azure AD grubu seçersiniz. Birden çok grup seçmek için **Ctrl** tuşunu kullanın ve grupları seçin.
6. İşiniz bittiğinde, değişikliklerinizi **Kaydedin**.

eSIM etkinleştirme kodları tek bir kez kullanılır. Intune bir cihaza etkinleştirme kodu yüklerse eSIM modülü hücresel profili indirmek için cep telefonu operatörüyle iletişim kurar. Bu iletişimle, cihazı cep telefonu operatörü ağına kaydetme işlemi tamamlanır.

## <a name="step-4-monitor-deployment"></a>4\. Adım: Dağıtımı izleme

### <a name="review-the-deployment-status"></a>Dağıtım durumunu gözden geçirme

Profili atadıktan sonra abonelik havuzunun dağıtım durumunu izleyebilirsiniz.

1. [Azure portalı](https://portal.azure.com/)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırma** > **eSIM hücresel profilleri**’ni seçin. Mevcut tüm eSIM hücresel abonelik havuzlarınız listelenir.
4. Abonelik seçin ve **Dağıtım Durumu**’nu gözden geçirin.

### <a name="check-the-profile-status"></a>Profil durumunu denetleme
Cihaz profilinizi oluşturduktan sonra, Intune grafikler sağlar. Bu grafikler profilin durumunu, örneğin cihazlara başarıyla atandığını veya çakışma gösterip göstermediğini görüntüler.

1. **Cihaz yapılandırma** > **eSIM hücresel profilleri**'ni ve mevcut aboneliği seçin.
2. **Genel Bakış** sekmesinde, en üstteki grafikte belirli bir eSIM hücresel abonelik havuzu dağıtımına atanan cihazların sayısı gösterilir.

    Ayrıca ayrı cihaz profiline atanmış olan diğer platformlardaki cihazların sayısını da gösterir.

    Intune, cihazları hedefleyen etkinleştirme kodu için teslim ve yükleme durumunu görüntüler.

    - **Cihaz eşitlenmedi**: Hedeflenen cihaz eSIM dağıtım ilkesinin oluşturulmasından bu yana Intune'la iletişim kurmadı
    - **Etkinleştirme bekliyor**: Intune'un cihaza etkin bir şekilde etkinleştirme kodunu kurması sırasında geçici bir durum
    - **Etkin**: Etkinleştirme kodu yüklemesi başarılı
    - **Etkinleştirme başarısız**: Etkinleştirme kodu yüklemesi başarısız oldu. Sorun giderme kılavuzuna bakın.

#### <a name="view-the-detailed-device-status"></a>Ayrıntılı cihaz durumunu görüntüleme

Cihaz Durumu'nda görebildiğiniz cihazların ayrıntılı bir listesini izleyebilir ve görüntüleyebilirsiniz.**

1. **Cihaz yapılandırma** > **eSIM hücresel profilleri**'ni ve mevcut aboneliği seçin.
2. **Cihaz Durumu**’nu seçin. Intune cihaz hakkında ek ayrıntılar gösterir:

    - **Cihaz Adı**: Hedeflenen cihazın adı
    - **Kullanıcı**: Kaydedilen cihazın kullanıcısı
    - **ICCID**: Cihaza yüklenen etkinleştirme kodu içinde cep telefonu operatörü tarafından sağlanan benzersiz kod
    - **Etkinleştirme Durumu**: Cihazdaki etkinleştirme kodunun Intune teslim ve yükleme durumu
    - **Şebeke durumu**: Cep telefonu operatörü tarafından sağlanan durum. Sorunları gidermek için cep telefonu operatörüyle iletişim kurun.
    - **Son İade Etme**: Cihazın Intune'la son iletişim kurma tarihi

### <a name="monitor-esim-profile-details-on-the-actual-device"></a>Gerçek cihazda eSIM profil ayrıntılarını izleme

1. Cihazınızda **Ayarlar**'ı açın > **Ağ ve İnternet**'e gidin.
2. **Hücresel** > **eSIM profillerini yönet**'i seçin
3. eSIM profilleri listelenir:

    ![Cihaz ayarlarınızda eSIM profillerini görüntüleme](./media/esim-device-configuration/device-settings-cellular-profiles.png)

## <a name="remove-the-esim-profile-from-device"></a>eSIM profilini cihazdan kaldırma

Cihazı Azure AD grubundan kaldırdığınızda eSIM profili de kaldırılır. Şunları yaptığınızdan emin olun:

1. eSIM cihazları Azure AD grubunu kullanmakta olduğunuzu onaylayın.
2. Azure AD grubuna gidin ve cihazı gruptan kaldırın.
3. Kaldırılan cihaz Intune'la iletişim kurduğunda, güncelleştirilen ilke değerlendirilir ve eSIM profili kaldırılır.

Ayrıca cihaz [kullanımdan kaldırıldığında](../remote-actions/devices-wipe.md#retire) veya cihazda [cihazı sıfırlama uzak eylemi](../remote-actions/devices-wipe.md#wipe) gerçekleştirildiğinde eSIM profili de kaldırılır.

> [!NOTE]
> Profilin kaldırılması faturalamayı durdurmaz. Cihazınızın faturalama durumunu denetlemek için cep telefonu operatörünüzle bağlantı kurun.

## <a name="best-practices--troubleshooting"></a>En iyi yöntemler ve sorun giderme

- CSV dosyanızın düzgün biçimlendirildiğinden emin olun. Dosyanın yinelenen kodlar, birden çok cep telefonu operatörü veya farklı mobil İnternet tarifeleri içermediğini onaylayın. Unutmayın; cep telefonu operatörü ve mobil İnternet tarifesi için her dosya benzersiz olmalıdır.
- Yalnızca hedeflenen eSIM cihazlarını içeren statik bir cihaz Azure AD grubu oluşturun.
- Dağıtım durumunda bir sorun olursa aşağıdakileri denetleyin:
  - **Dosya biçimi doğru değil**: Dosyanızı düzgün biçimlendirme hakkında bilgi için bkz. **1. Adım: Hücresel etkinleştirme kodları ekleme** (bu makalede).
  - **Hücresel etkinleştirme hatası, cep telefonu operatörüne başvurun**: Etkinleştirme kodu kendi ağı içinde etkinleştirilemiyor olabilir. Belki de profil indirme ve hücresel etkinleştirme başarısız olmuştur.

## <a name="next-steps"></a>Sonraki adımlar
[Cihaz profillerini yapılandırma](../device-profiles.md)
