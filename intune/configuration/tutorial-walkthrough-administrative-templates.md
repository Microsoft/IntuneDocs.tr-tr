---
title: İzlenecek yol-Microsoft Intune-Azure 'da yönetim şablonu oluşturma | Microsoft Docs
description: Bu öğretici veya İzlenecek yol, Windows 10 ve daha yeni cihazlarda Office, Windows ve Microsoft Edge ADMX şablonlarını yapılandırmak için Microsoft Intune kullanır.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/07/2020
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80f489bc91f6d2f51cf9ee378793043a49c4e949
ms.sourcegitcommit: e4602481a25a5e12379f673dfe801c611f51c35b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75735028"
---
# <a name="tutorial-use-the-cloud-to-configure-group-policy-on-windows-10-devices-with-admx-templates-and-microsoft-intune"></a>Öğretici: Windows 10 cihazlarında ADMX şablonları ve Microsoft Intune Grup İlkesi yapılandırmak için bulutu kullanın

> [!NOTE]
> Bu öğretici, Microsoft Ignite için teknik bir atölye olarak oluşturulmuştur. Intune 'da ve şirket içinde ADMX ilkelerini kullanarak ve yapılandırma ile karşılaştırıldığı için tipik öğreticilerden daha fazla önkoşul vardır.

ADMX şablonları olarak da bilinen Grup İlkesi Yönetim Şablonları, bilgisayarlar dahil olmak üzere Windows 10 cihazlarında yapılandırabileceğiniz ayarları içerir. ADMX şablon ayarları farklı hizmetler tarafından kullanılabilir. Bu ayarlar, Microsoft Intune dahil olmak üzere mobil cihaz yönetimi (MDM) sağlayıcıları tarafından kullanılır. Örneğin, PowerPoint 'te tasarım fikirlerini açabilir, Microsoft Edge 'de bir giriş sayfası ayarlayabilir, Internet Explorer 'da ActiveX denetimlerini engelleyebilir ve daha fazlasını yapabilirsiniz.

ADMX şablonları aşağıdaki hizmetler için kullanılabilir:

- **Microsoft Edge**: [Microsoft Edge ilke dosyasında](https://www.microsoftedgeinsider.com/en-us/enterprise)indirin.
- **Office**: [Office 365 ProPlus, Office 2019 ve Office 2016](https://www.microsoft.com/download/details.aspx?id=49030)' de indirin.
- **Windows**: Windows 10 işletim sisteminde yerleşik olarak.

ADMX ilkeleri hakkında daha fazla bilgi için bkz. [ADMX ile desteklenen Ilkeleri anlama](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies).

Microsoft Intune, bu şablonlar Intune hizmetinde yerleşiktir ve **Yönetim Şablonları** profilleri olarak kullanılabilir. Bu profilde, dahil etmek istediğiniz ayarları yapılandırıp daha sonra bu profili cihazlarınıza "atamalısınız".

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * [Microsoft Endpoint Manager yönetim merkezine](https://go.microsoft.com/fwlink/?linkid=2109431)gidin.
> * Kullanıcı grupları oluşturun ve cihaz grupları oluşturun.
> * Intune 'daki ayarları şirket içi ADMX ayarlarıyla karşılaştırın.
> * Farklı yönetim şablonları oluşturun ve farklı grupları hedefleyen ayarları yapılandırın.

Bu laboratuvarın sonuna kadar, Intune 'u kullanmaya başlama becerileri ve kullanıcılarınızı yönetmek için Microsoft 365 ve Yönetim Şablonları dağıtmanız gerekir.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 sürüm 1703 ve üzeri

## <a name="prerequisites"></a>Prerequisites

- Intune ve Azure Active Directory (AD) Premium içeren bir Microsoft 365 E3 veya E5 aboneliği. E3 veya E5 aboneliğiniz yoksa [ücretsiz olarak deneyin](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365?view=o365-worldwide).

  Farklı Microsoft 365 lisanslarıyla neler alacağınız hakkında daha fazla bilgi için bkz. [kuruluşunuzu Microsoft 365 dönüştürme](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

- Microsoft Intune, **ıNTUNE MDM yetkilisi**olarak yapılandırılır. Daha fazla bilgi için bkz. [mobil cihaz yönetimi yetkilisini ayarlama](../fundamentals/mdm-authority-set.md).

  > [!div class="mx-imgBorder"]
  > ![MDM yetkilisini kiracı durumunuz Microsoft Intune olarak ayarlayın](./media/tutorial-walkthrough-administrative-templates/tenant-status.png)

- Şirket içi Active Directory etki alanı denetleyicisinde (DC):

  1. Aşağıdaki Office ve Microsoft Edge şablonlarını [Merkezi depoya (SYSVOL klasörü)](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)kopyalayın:

      - [Office Yönetim Şablonları](https://www.microsoft.com/download/details.aspx?id=49030)
      - [Microsoft Edge Yönetim Şablonları > Ilke dosyası](https://www.microsoftedgeinsider.com/en-us/enterprise)

  2. Bu şablonları DC ile aynı etki alanında bulunan bir Windows 10 Kurumsal Yönetici bilgisayara göndermek için bir grup ilkesi oluşturun. Bu öğreticide:

      - Bu şablonlarla oluşturduğumuz Grup ilkesi, **Officeandedge**olarak adlandırılır. Bu adı görüntülerde görürsünüz.
      - Kullandığımız Windows 10 kuruluş yöneticisi bilgisayar, **yönetici bilgisayar**olarak adlandırılır.

      Bazı kuruluşlarda, bir etki alanı yöneticisinin iki hesabı vardır-tipik bir etki alanı iş hesabıdır ve yalnızca Grup İlkesi gibi etki alanı yönetici görevlerinde kullanılan farklı bir etki alanı yönetici hesabı vardır.

      Bu **Yönetici bilgisayarın** amacı, yöneticilerin etki alanı yönetici hesabıyla oturum açmasını ve Grup İlkesi 'ni yönetmek için tasarlanan araçlara erişmelerini sağlamaktır.

- Bu **yönetici bilgisayarda**:

  - Bir etki alanı yönetici hesabıyla oturum açın.

  - **Rsat: Grup İlkesi Yönetim Araçları**'nı yükler:

    1. **Ayarlar** uygulama > **uygulamalar** > , **Özellik Ekle** > **isteğe bağlı özellikler** ' i açın.
    2. **Rsat: Grup ilkesi yönetim araçları** > **yüklemeyi**seçin.

        Windows özelliği yüklerken bekleyin. Bu tamamlandığında, sonunda **Windows Yönetim Araçları** uygulamasında gösterilir.

        > [!div class="mx-imgBorder"]
        > grup ilkesi yönetimi uygulaması da dahil olmak üzere Windows Yönetim Araçları uygulamalarını ![](./media/tutorial-walkthrough-administrative-templates/windows-administrative-tools-app.png)

  - Endpoint Manager yönetim merkezini içeren Microsoft 365 aboneliğine internet erişimi ve yönetici haklarına sahip olduğunuzdan emin olun.

## <a name="open-the-endpoint-manager-admin-center"></a>Endpoint Manager yönetim merkezini açın

1. Microsoft Edge sürüm 77 ve üzeri gibi bir kmıum Web tarayıcısı açın.
2. [Microsoft Endpoint Manager yönetim merkezine](https://go.microsoft.com/fwlink/?linkid=2109431) gidin (https://devicemanagement.microsoft.com). Şu hesapla oturum açın:

    **Kullanıcı**: Microsoft 365 Kiracı aboneliğinizin yönetici hesabını girin.  
    **Parola**: parolasını girin.

Bu Yönetim Merkezi cihaz yönetimine odaklanır ve Azure AD ve Intune gibi Azure hizmetlerini içerir. **Azure Active Directory** ve **Intune** markasını görmeyebilirsiniz, ancak bunları kullanıyorsunuz.

Ayrıca, [Microsoft 365 Yönetim merkezinden](https://admin.microsoft.com)Endpoint Manager yönetim merkezini açabilirsiniz:

1. [https://admin.microsoft.com](https://admin.microsoft.com) kısmına gidin.
2. Microsoft 365 Kiracı aboneliğinizin Yönetici hesabınızla oturum açın.
3. **Yönetim Merkezleri**altında, **uç nokta yönetimi** > **tüm yönetici merkezleri** ' ı seçin. Endpoint Manager Yönetim Merkezi açılır.

    > [!div class="mx-imgBorder"]
    > ![, Microsoft 365 Yönetim Merkezi 'ndeki tüm yönetim merkezlerini görüntüleyin](./media/tutorial-walkthrough-administrative-templates/microsoft365-admin-centers.png)

## <a name="create-groups-and-add-users"></a>Grup oluşturma ve Kullanıcı ekleme

Şirket içi ilkeler, LSDOU sıralaması-yerel, site, etki alanı ve kuruluş birimine (OU) uygulanır. Bu hiyerarşide, OU ilkeleri yerel ilkelerin üzerine yazılır, etki alanı ilkeleri site ilkelerinin üzerine yazar ve bu şekilde devam eder.

Intune 'da, ilkeler oluşturduğunuz kullanıcılara ve gruplara uygulanır. Hiyerarşi yok. İki ilke aynı ayarı güncelleştiriyorsa, ayar çakışma olarak gösterilir. İki uyumluluk ilkesi çakışırsa, en kısıtlayıcı ilke uygulanır. İki yapılandırma profili çakışırsa, ayar uygulanmaz. Daha fazla bilgi için bkz. [cihaz ilkeleri ve profillerle Ilgili yaygın sorular, sorunlar ve çözümler](device-profile-troubleshoot.md#if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied).

Bu sonraki adımlarda güvenlik grupları oluşturacak ve gruplara kullanıcılar ekleyeceğiz. Bir kullanıcıyı birden çok gruba ekleyebilirsiniz. Örneğin, bir kullanıcının Surface for Work gibi birden çok cihazı ve kişisel için bir Android mobil cihazını olması normaldir. Ayrıca, bir kişinin bu birden fazla cihazdan kuruluş kaynaklarına erişmesi normaldir.

1. Endpoint Manager Yönetim merkezinde **gruplar** > **Yeni Grup**' u seçin.

2. Aşağıdaki ayarları girin:

    - **Grup türü**: **güvenlik**' i seçin.
    - **Grup adı**: **tüm Windows 10 öğrenci cihazlarını**girin.
    - **Üyelik türü**: **atanan**' ı seçin.

3. **Üyeler**' i seçin ve bazı cihazlar ekleyin.

    Cihazları eklemek isteğe bağlıdır. Amaç, Grup oluşturma ve cihazların nasıl ekleneceğini bilme alışkanlıktır. Bu öğreticiyi bir üretim ortamında kullanıyorsanız, ne yaptığınızı unutmayın.

4. Değişikliklerinizi kaydetmek için > **Oluştur** ' u **seçin** .

    Grubunuzu göremiyor musunuz? **Yenile**' yi seçin.

5. **Yeni Grup**' u seçin ve aşağıdaki ayarları girin:

    - **Grup türü**: **güvenlik**' i seçin.
    - **Grup adı**: **tüm Windows cihazlarını**girin.
    - **Üyelik türü**: **dinamik cihaz**seçin.
    - **Dinamik cihaz üyeleri**: sorgunuzu yapılandırın:

        - **Özellik**: **deviceostype**öğesini seçin.
        - **İşleç**: **eşittir**' i seçin.
        - **Değer**: **Windows**girin.

        1. **Ifade Ekle**' yi seçin. İfadeniz **kural sözdiziminde**gösterilmektedir:

            > [!div class="mx-imgBorder"]
            > ![dinamik sorgu oluşturma ve Microsoft Intune yönetim şablonuna ifade ekleme](./media/tutorial-walkthrough-administrative-templates/dynamic-group-query.png)

            Kullanıcılar veya cihazlar girdiğiniz ölçütlere uyduklarında, bunlar otomatik olarak dinamik gruplara eklenir. Bu örnekte, işletim sistemi Windows olduğunda cihazlar bu gruba otomatik olarak eklenir. Bu öğreticiyi bir üretim ortamında kullanıyorsanız dikkatli olun. Amaç, dinamik gruplar oluşturma alıştırması sağlamaktır.

        2. Değişikliklerinizi **kaydetmek için > ** **oluşturun** .

6. Aşağıdaki ayarlarla **Tüm öğretmenler** grubunu oluşturun:

    - **Grup türü**: **güvenlik**' i seçin.
    - **Grup adı**: **Tüm öğretmenler**' i girin.
    - **Üyelik türü**: **Dinamik Kullanıcı**' yı seçin.
    - **Dinamik Kullanıcı üyeleri**: sorgunuzu yapılandırın:

      - **Özellik**: **departmanı**seçin.
      - **İşleç**: **eşittir**' i seçin.
      - **Değer**: **öğretmen**girin.

        1. **Ifade Ekle**' yi seçin. İfadeniz **kural sözdiziminde**gösterilmiştir.

            Kullanıcılar veya cihazlar girdiğiniz ölçütlere uyduklarında, bunlar otomatik olarak dinamik gruplara eklenir. Bu örnekte, bölümleri öğretmenler olduğunda kullanıcılar bu gruba otomatik olarak eklenir. Kullanıcılar kuruluşunuza eklendiğinde departmanı ve diğer özellikleri girebilirsiniz. Bu öğreticiyi bir üretim ortamında kullanıyorsanız dikkatli olun. Amaç, dinamik gruplar oluşturma alıştırması sağlamaktır.

        2. Değişikliklerinizi **kaydetmek için > ** **oluşturun** .

### <a name="talking-points"></a>Konuşma noktaları

- Dinamik Gruplar Azure AD Premium bir özelliktir. Azure AD Premium yoksa, yalnızca atanan gruplar oluşturmaya lisanslanır. Dinamik Gruplar hakkında daha fazla bilgi için bkz.

  - [Azure Active Directory dinamik grup üyeliği (Bölüm 1)](https://blogs.technet.microsoft.com/pauljones/2017/08/28/dynamic-group-membership-in-azure-active-directory-part-1/)
  - [Azure Active Directory dinamik grup üyeliği (2. bölüm)](https://blogs.technet.microsoft.com/pauljones/2017/08/29/dynamic-group-membership-in-azure-active-directory-part-2/)

- Azure AD Premium, [çok faktörlü kimlik doğrulaması (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) ve [koşullu erişim](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)de dahil olmak üzere uygulama ve cihazları yönetirken yaygın olarak kullanılan diğer hizmetleri içerir.

- Birçok yönetici, Kullanıcı gruplarını ne zaman kullanacağınızı ve cihaz gruplarının ne zaman kullanılacağını sorar. Bazı rehberlik için bkz. [Kullanıcı grupları ve cihaz grupları karşılaştırması](device-profile-assign.md#user-groups-vs-device-groups).

- Bir kullanıcının birden çok gruba ait olabileceğini unutmayın. Oluşturabileceğiniz bazı dinamik Kullanıcı ve cihaz gruplarından bazılarını göz önünde bulundurun, örneğin:

  - Tüm öğrenciler
  - Tüm Android cihazlar
  - Tüm iOS cihazları
  - Pazarlama
  - İnsan Kaynakları
  - Tüm Charlotte çalışanları
  - Tüm Redmond çalışanları
  - Batı Yakası IT yöneticileri
  - Doğu Yakası BT yöneticileri

Oluşturulan kullanıcılar ve gruplar ayrıca [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com), Azure Portal Azure AD 'de ve [Azure Portal Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2090973)da görülür. Kiracı aboneliğiniz için tüm bu alanlarda gruplar oluşturabilir ve yönetebilirsiniz. **Amacınız cihaz yönetimi ise, [Microsoft Endpoint Manager yönetim merkezini](https://go.microsoft.com/fwlink/?linkid=2109431)kullanın**.

### <a name="review-group-membership"></a>Grup üyeliğini gözden geçirme

1. Endpoint Manager Yönetim merkezinde, **kullanıcılar** > mevcut bir kullanıcının adını seçin.

    > [!div class="mx-imgBorder"]
    > Endpoint Manager Yönetim Merkezi 'Nde ![kullanıcılar ' ı seçin](./media/tutorial-walkthrough-administrative-templates/select-users-endpoint-manager-admin-center.png)

2. Ekleyebileceğiniz veya değiştirebilmeniz gereken bazı bilgileri gözden geçirin. Örneğin, Iş unvanı, departman, şehir, ofis konumu ve daha fazlası gibi yapılandırabileceğiniz özelliklere göz atın. Dinamik grupları oluştururken dinamik sorgularınızda bu özellikleri kullanabilirsiniz.
3. Bu kullanıcının üyeliğini görmek için **grupları** seçin. Kullanıcıyı bir gruptan da kaldırabilirsiniz.
4. Daha fazla bilgi ve yapabileceklerinizi görmek için diğer seçeneklerden bazılarını seçin. Örneğin, atanan lisansa, kullanıcının cihazlarına ve daha fazlasına göz atın.

### <a name="what-did-i-just-do"></a>Ne yapmam gerekiyor?

Endpoint Manager Yönetim merkezinde yeni güvenlik grupları oluşturdunuz ve var olan kullanıcıları ve cihazları bu gruplara eklediniz. Bu öğreticinin sonraki adımlarında bu grupları kullanacağız.

## <a name="create-a-template-in-intune"></a>Intune 'da şablon oluşturma

Bu bölümde, Intune 'da bir yönetim şablonu oluşturacağız, **Grup İlkesi yönetiminde**bazı ayarlara baktık ve Intune 'daki aynı ayarı karşılaştırıyoruz. Amaç, Grup İlkesi 'nde bir ayarı göstermek ve Intune 'da aynı ayarı göstermek için kullanılır.

1. Endpoint Manager Yönetim Merkezi 'nde, **cihaz** > **yapılandırma profilleri** > **Profil oluştur**' u seçin.
2. Aşağıdaki özellikleri girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, **yönetici şablonu-Windows 10 öğrenci cihazları**girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **Yönetim Şablonları**' nı seçin.

3. **Oluştur**’u seçin. **Kategori Seç** aşağı açılan listesinde **Tüm ürünler**' i seçin. Tüm ayarlar gösterilir. Bu ayarlarda aşağıdaki özelliklere dikkat edin:

    - İlke **yolu** Grup İlkesi Management veya gpedit ile aynıdır.
    - Ayar, kullanıcılar veya cihazlar için geçerlidir.

### <a name="open-group-policy-management"></a>grup ilkesi yönetimi 'ni açın

Bu bölümde, Intune 'da ve Grup İlkesi Yönetimi Düzenleyicisi eşleşen ilkesiyle bir ilke gösteririz.

#### <a name="compare-a-device-policy"></a>Bir cihaz ilkesini karşılaştırma

1. **Yönetici bilgisayarda** **Grup İlkesi Management** uygulamasını açın.

    Bu uygulama, Windows 'a yüklediğiniz isteğe bağlı bir özellik olan **rsat: Grup İlkesi Yönetim Araçları**ile birlikte yüklenir. [Önkoşullar](#prerequisites) (Bu makalede), yüklemek için gereken adımları listeler.

2. Etki **alanlarını** genişletin > etki alanınızı seçin. Örneğin, **contoso.net**öğesini seçin.
3. **Officeandedge** Policy > **Düzenle**' ye sağ tıklayın. Bu, Grup İlkesi Yönetimi Düzenleyicisi uygulamasını açar.

    > [!div class="mx-imgBorder"]
    > ![Office ve Edge ADMX Grup İlkesi ' ne sağ tıklayın ve Düzenle ' yi seçin](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management.png)

    **Officeandedge** , Office ve MICROSOFT Edge ADMX şablonlarını içeren bir grup ilkesidir. Bu ilke, [Önkoşullar](#prerequisites) (Bu makalede) bölümünde açıklanmaktadır.

4. **Bilgisayar yapılandırma** > **ilkeleri** > **Yönetim Şablonları** > **Denetim Masası** > **Kişiselleştirme**' yi genişletin. Kullanılabilir ayarlara dikkat edin.

    > [!div class="mx-imgBorder"]
    > Grup İlkesi Yönetimi Düzenleyicisi ![bilgisayar yapılandırmasını genişlettikten sonra kişiselleştirme](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management-editor-admx-policy.png) git

    **Kilit ekranı kamerayı etkinleştirmeyi engelle**' ye çift tıklayın ve kullanılabilir seçenekleri görüntüleyin:

    > [!div class="mx-imgBorder"]
    > ![Grup İlkesi 'nde bilgisayar yapılandırma ayarı seçeneklerini görmek](./media/tutorial-walkthrough-administrative-templates/prevent-enabling-lock-screen-camera-admx-policy.png)

5. Cihaz Yönetimi yönetim merkezinde, **yönetici şablonunuz-Windows 10 öğrenci cihazları** şablonuna gidin.
6. Açılan listeden **Tüm ürünler** ' i seçin ve **Kişiselleştirme**için arama yapın:

    > [!div class="mx-imgBorder"]
    > Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/search-personalization-administrative-template.png) yönetim şablonunda kişiselleştirme için arama ![

    Kullanılabilir ayarlara dikkat edin.

    Ayar türü **cihaz**ve yol **\Denetim masası \ kişiselleştirme**şeklindedir. Bu yol, Grup İlkesi Yönetimi Düzenleyicisi az önce gördüğünüzle benzerdir. Ayarı açarsanız, Grup İlkesi Yönetimi Düzenleyicisi aynı **yapılandırılmamış**, **etkin**ve **devre dışı** seçeneklerinin aynısını görürsünüz.

#### <a name="compare-a-user-policy"></a>Kullanıcı ilkesini karşılaştırma

1. Yönetici şablonunuzda, **InPrivate Gözatma**için arama yapın. Yoluna ve ayarın kullanıcılar ve cihazlar için geçerli olduğuna dikkat edin.

2. **Grup İlkesi Yönetimi Düzenleyicisi**, eşleşen kullanıcı ve cihaz ayarlarını bulun:

    - Cihaz: **bilgisayar yapılandırma** > **ilkeleri** > **Yönetim Şablonları** > **Windows bileşenleri** > **Internet Explorer** > **Gizlilik** > **InPrivate taramayı kapat**' ı genişletin.
    - Kullanıcı: **Kullanıcı yapılandırma** > **ilkeleri** > **Yönetim Şablonları** > **Windows bileşenleri** > **Internet Explorer** > **Gizlilik** > **InPrivate taramayı kapat**' ı genişletin.

    > [!div class="mx-imgBorder"]
    > ![ADMX şablonunu kullanarak Internet Explorer 'da InPrivate taramayı devre dışı bırakın](./media/tutorial-walkthrough-administrative-templates/group-policy-turn-off-inprivate-browsing.png)

> [!TIP]
> Yerleşik Windows ilkelerini görmek için GPEdit (**Grup İlkesi uygulamasını Düzenle** ) seçeneğini de kullanabilirsiniz.

#### <a name="compare-an-edge-policy"></a>Kenar ilkesini karşılaştırın

1. Cihaz Yönetimi yönetim merkezinde, **yönetici şablonunuz-Windows 10 öğrenci cihazları** şablonuna gidin.
2. Aşağı açılan listeden **Microsoft Edge sürüm 77 ve üstünü** seçin.
3. **Başlangıç**için arama yapın. Kullanılabilir ayarlara dikkat edin.
4. Grup İlkesi Yönetimi Düzenleyicisi, şu ayarları bulun:

    - Cihaz: **Microsoft Edge** > **Başlangıç, giriş sayfası ve yeni sekme sayfası** **Yönetim Şablonları** > **bilgisayar yapılandırma** > **ilkeleri** > genişletin.
    - Kullanıcı: **Kullanıcı yapılandırma** > **ilkeleri** > **Yönetim Şablonları** > **Microsoft Edge** > **Başlangıç, giriş sayfası ve yeni sekme sayfası '** nı genişletin

### <a name="what-did-i-just-do"></a>Ne yapmam gerekiyor?

Intune 'da bir yönetim şablonu oluşturdunuz. Bu şablonda bazı ADMX ayarlarına bakıyoruz ve grup ilkesi yönetiminde aynı ADMX ayarlarına baktık.

## <a name="add-settings-to-the-students-admin-template"></a>Öğrenciler yönetici şablonuna ayarlar ekleme

Bu şablonda, bazı Internet Explorer ayarlarını birden çok öğrenci tarafından paylaşılan cihazları kilitleyecek şekilde yapılandıracağız.

1. **Yönetici şablonunuzda-Windows 10 öğrenci cihazlarında**, **InPrivate taramayı**Kapat ' ı arayın ve cihaz ilkesini seçin:

    > [!div class="mx-imgBorder"]
    > Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/turn-off-inprivate-browsing-administrative-template.png) yönetim şablonunda InPrivate Gözatma cihaz ilkesini kapatma ![

2. Bu pencerede, ayarlayabileceğiniz açıklama ve değerlere dikkat edin. Bu seçenekler, Grup İlkesi 'nde gördüklerinize benzerdir.
3. Değişikliklerinizi kaydetmek için **etkin** > **Tamam ' ı** seçin.
4. Ayrıca, aşağıdaki Internet Explorer ayarlarını yapılandırın. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçtiğinizden emin olun.

    - **Dosyaları sürükle ve bırak veya Kopyala ve Yapıştır 'a izin ver**
      - **Tür**: cihaz
      - **Yol**: \Windows Internet Explorer\ınternet Control Panel\security Page\ınternet Zone
      - **Değer**: devre dışı

    - **Sertifika hatalarını yoksaymayı engelle**
      - **Tür**: cihaz
      - **Yol**: \Windows Internet Explorer\ınternet Denetim Masası
      - **Değer**: etkin

    - **Giriş sayfası ayarlarını değiştirmeyi devre dışı bırak**
      - **Tür**: Kullanıcı
      - **Yol**: \Windows Internet Explorer
      - **Değer**: etkin
      - **Giriş sayfası**: `contoso.com`gıbı bir URL girin.

5. Arama filtrenizi temizleyin. Yapılandırdığınız ayarların en üstte listelendiğini unutmayın:

    > [!div class="mx-imgBorder"]
    > ![yapılandırılan ayarlar, Microsoft Intune üst kısmında listelenir](./media/tutorial-walkthrough-administrative-templates/configured-settings-administrative-template.png)

### <a name="assign-your-template"></a>Şablonunuzu atama

1. Şablonunuzda, **atamalar**' ı seçin. Şablonunuzu kapatmanız ve ardından **cihazlar-yapılandırma profilleri** listesinden seçmeniz gerekebilir:

    > [!div class="mx-imgBorder"]
    > ![Microsoft Intune cihaz yapılandırma profilleri listesinden yönetim şablonu profilinizi seçin](./media/tutorial-walkthrough-administrative-templates/filter-administrative-template-device-configuration-profiles-list.png)

2. **Dahil edilecek grupları seçin**öğesini seçin. Mevcut kullanıcılar ve grupların listesi gösterilir.
3. Daha önce oluşturduğunuz **tüm Windows 10 öğrenci cihazları** grubunu seçin > **seçin**.

    Bu öğreticiyi bir üretim ortamında kullanıyorsanız boş olan grupları eklemeyi göz önünde bulundurun. Amaç, şablonunuzu atamaya yönelik bir uygulamadır.

4. Yaptığınız değişiklikleri **kaydedin**.

Profil kaydedildiği anda, Intune ile iade edildiğinde cihazlara uygulanır. Cihazlar internet 'e bağlıysa hemen gerçekleşebilir. İlke yenileme zamanları hakkında daha fazla bilgi için, [cihazların atanma sonrasında ilke, profil veya uygulama alma süresi ne kadar sürer](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Katı veya kısıtlayıcı ilkeler ve profiller atarken, kendinizi kilitlemeyin. İlkelerinizi ve profilinizden dışlanan bir grup oluşturmayı düşünün. Fikrin giderilmesi için erişim sahibi olmanız gerekir. Bu grubu, istenen şekilde kullanıldığını onaylamak için izleyin.

### <a name="what-did-i-just-do"></a>Ne yapmam gerekiyor?

Endpoint Manager Yönetim merkezinde bir yönetim şablonu cihaz yapılandırma profili oluşturdunuz ve bu profili oluşturduğunuz bir gruba atamış olursunuz.

## <a name="create-a-onedrive-template"></a>OneDrive şablonu oluşturma

Bu bölümde, bazı ayarları denetlemek için Intune 'Da bir OneDrive yönetici şablonu oluşturacaksınız. Bu özel ayarlar, kuruluşlar tarafından yaygın olarak kullanıldıkları için seçilir.

1. Başka bir profil (**cihaz** > **yapılandırma profilleri** > **Profil oluştur**) oluşturun.

2. Aşağıdaki özellikleri girin:

    - **Ad**: **yönetici şablonunu girin-tüm Windows 10 kullanıcılarına uygulanan OneDrive ilkeleri**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **Yönetim Şablonları**' nı seçin.

3. **Oluştur**’u seçin.
4. Açılan listeden **Office** ' i seçin.
5. Aşağıdaki ayarları **etkinleştirin** . Değişikliklerinizi kaydetmek için **Tamam ' ı** seçtiğinizden emin olun.

    - **Kullanıcıları Windows kimlik bilgileriyle OneDrive eşitleme istemcisine sessizce oturum açın**
    - **OneDrive dosyalarını Isteğe bağlı olarak kullanın**
    - **Kullanıcıların kişisel OneDrive hesaplarını eşitlemesini engelleyin**

Ayarlarınız aşağıdaki ayarlara benzer şekilde görünür:

> [!div class="mx-imgBorder"]
> Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/one-drive-administrative-template.png) ![OneDrive yönetim şablonu oluşturma

OneDrive istemci ayarları hakkında daha fazla bilgi için bkz. [OneDrive Sync istemci ayarlarını denetlemek için Grup İlkesi kullanma](https://docs.microsoft.com/onedrive/use-group-policy).

### <a name="assign-your-template"></a>Şablonunuzu atama

1. Şablonunuzda, **atamalar**' ı seçin.
2. **Dahil edilecek grupları seçin**öğesini seçin. Mevcut kullanıcılar ve grupların listesi gösterilir.
3. Daha önce oluşturduğunuz **tüm Windows cihazları** grubunu seçin > **seçin**.

    Bu öğreticiyi bir üretim ortamında kullanıyorsanız boş olan grupları eklemeyi göz önünde bulundurun. Amaç, şablonunuzu atamaya yönelik bir uygulamadır.

4. Yaptığınız değişiklikleri **kaydedin**.

Bu noktada, bazı yönetim şablonları oluşturdunuz ve bunları oluşturduğunuz gruplara atamış olursunuz. Sonraki adım, Windows PowerShell ve Intune için Microsoft Graph API kullanarak bir yönetim şablonu oluşturmaktır.

## <a name="optional-create-a-policy-using-powershell-and-graph-api"></a>İsteğe bağlı: PowerShell ve Graph API kullanarak ilke oluşturma

Bu bölüm aşağıdaki kaynakları kullanır. Bu kaynakları bu bölüme yükleyeceğiz.

- [Intune PowerShell SDK 'Sı](https://github.com/microsoft/Intune-PowerShell-SDK)
- [Intune için Microsoft Graph API 'SI](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)

1. Yönetici **bilgisayarda**, **Windows PowerShell** 'i yönetici olarak açın:

    1. Arama çubuğunuza **PowerShell**yazın.
    2. **Windows PowerShell** > **yönetici olarak çalıştır**' a sağ tıklayın.

    > [!div class="mx-imgBorder"]
    > Windows PowerShell 'i yönetici olarak çalıştırmak ![](./media/tutorial-walkthrough-administrative-templates/run-windows-powershell-administrator.png)

2. Yürütme ilkesini alın ve ayarlayın.

    1. Şunu girin: `get-ExecutionPolicy`

        ' Ne ayarlanmış olduğunu, **sınırlı**olabilecek şekilde yazın. Öğreticiyle işiniz bittiğinde, özgün değerine geri ayarlayın.

    2. Şunu girin: `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`

    3. Değiştirmek için `Y` girin.

    PowerShell 'in yürütme ilkesi kötü amaçlı betiklerin yürütülmesini önlemeye yardımcı olur. Daha fazla bilgi için bkz. [yürütme Ilkeleri hakkında](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).

3. Şunu girin: `Install-Module -Name Microsoft.Graph.Intune`

    `Y` şunu girin:

    - NuGet sağlayıcısı 'nı yüklemek isteyip istemediğiniz
    - Modülleri güvenilmeyen depolardan yüklemek isteyip istemediğiniz sorulur

    Tamamlanması birkaç dakika sürebilir. İşiniz bittiğinde, aşağıdaki komut istemine benzer bir istem gösterilir:

    > [!div class="mx-imgBorder"]
    > Modül yüklendikten sonra Windows PowerShell istemi ![](./media/tutorial-walkthrough-administrative-templates/powershell-prompt.png)

4. Web tarayıcınızda [https://github.com/Microsoft/Intune-PowerShell-SDK/releases](https://github.com/Microsoft/Intune-PowerShell-SDK/releases)' a gidin ve **Intune-PowerShell-SDK_v6.1907.00921.0001. zip** dosyasını seçin.

    1. **Farklı kaydet**' i seçin ve anımsayabileceğiniz bir klasör seçin. `c:\psscripts` iyi bir seçenektir.
    2. Klasörünüzü açın, tüm > **ayıklamayı** **ayıklamak** >. zip dosyasına sağ tıklayın. Klasör yapınız aşağıdaki klasöre benzer şekilde görünür:

        > [!div class="mx-imgBorder"]
        > ayıklandıktan sonra Intune PowerShell SDK klasör yapısını ![](./media/tutorial-walkthrough-administrative-templates/psscripts-directory.png)

5. **Görünüm** sekmesinde **dosya adı uzantıları**' nı işaretleyin:

    > [!div class="mx-imgBorder"]
    > Gezgin 'deki Görünüm sekmesinde dosya adı uzantılarını ![seçin](./media/tutorial-walkthrough-administrative-templates/file-names-extension.png)

6. Klasörünüze gidin ve `c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471`. Her. dll > **özellikler** > **Engellemeyi kaldır**' a sağ tıklayın.

    > [!div class="mx-imgBorder"]
    > Dll 'Leri engellemeyi kaldırmak ![](./media/tutorial-walkthrough-administrative-templates/unblock-dll.png)

7. **Windows PowerShell** uygulamanızda şunu girin:

    ```powershell
    Import-Module c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471\Microsoft.Graph.Intune.psd1
    ```

    Güvenilmeyen yayımcıdan çalıştırmanız istenirse `R` girin.

8. Intune Yönetim Şablonları, Graf beta sürümünü kullanır:

    1. Şunu girin: `Update-MSGraphEnvironment -SchemaVersion 'beta'`

    2. Şunu girin: `Connect-MSGraph -AdminConsent`

    3. İstendiğinde, aynı Microsoft 365 yönetici hesabıyla oturum açın. Bu cmdlet 'ler, ilkeyi kiracı kuruluşunuzda oluşturur.

        **Kullanıcı**: Microsoft 365 Kiracı aboneliğinizin yönetici hesabını girin.  
        **Parola**: parolasını girin.

    4. **Kabul Et**’i seçin.

9. **Test yapılandırması** yapılandırma profilini oluşturun. Girin:

    ```powershell
    $configuration = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations -Content '{"displayName":"Test Configuration","description":"A test configuration created through PS"}' -HttpMethod POST
    ```

    Bu cmdlet 'ler başarılı olduğunda profil oluşturulur. Doğrulamak için, Endpoint Manager Yönetim Merkezi > **yapılandırma profilleri**' ne gidin. **Test yapılandırması** profiliniz listelenmelidir.

10. Tüm SettingDefinitions 'ı alın. Girin:

    ```powershell
    $settingDefinitions = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions -HttpMethod GET
    ```

11. Görünen ad ayarını kullanarak tanım KIMLIĞINI bulun. Girin:

    ```powershell
    $desiredSettingDefinition = $settingDefinitions.value | ? {$_.DisplayName -Match "Silently sign in users to the OneDrive sync client with their Windows credentials"}
    ```

12. Bir ayar yapılandırın. Girin:

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues" -Content ("{""enabled"":""true"",""configurationType"":""policy"",""definition@odata.bind"":""https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions('$($desiredSettingDefinition.id)')""}") -HttpMethod POST
    ```

    ```powershell
    Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -Content ("{""enabled"":""false""}") -HttpMethod PATCH
    ```

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -HttpMethod GET
    ```

### <a name="see-your-policy"></a>İlkenize bakın

1. Endpoint Manager Yönetim merkezinde > **yapılandırma profilleri** > **yenileyin**.
2. **Test yapılandırma** profilinizi > **ayarları**' nı seçin.
3. Açılan listede, **Tüm ürünler**' i seçin.

**Kullanıcılar, Windows kimlik bilgileri ayarıyla birlikte OneDrive eşitleme istemcisine kullanıcıların sessizce oturum açmasını** görürsünüz.

## <a name="policy-best-practices"></a>İlke en iyi uygulamaları

Intune 'da ilke ve profil oluştururken dikkate almanız gereken bazı öneriler ve en iyi uygulamalar vardır. Daha fazla bilgi için bkz. [ilke ve profil en iyi uygulamaları](device-profile-create.md#recommendations).

## <a name="clean-up-resources"></a>Kaynakları temizleme

Artık gerekli değilse şunları yapabilirsiniz:

- Oluşturduğunuz grupları silin:

  - **Tüm Windows 10 öğrenci cihazları**
  - **Tüm Windows cihazları**
  - **Tüm öğretmenler**

- Oluşturduğunuz yönetici şablonlarını silin:

  - **Yönetici şablonu-Windows 10 öğrenci cihazları**
  - **Yönetici şablonu-tüm Windows 10 kullanıcılarına uygulanan OneDrive ilkeleri**
  - **Test yapılandırması**

- Windows PowerShell yürütme ilkesini özgün değerine geri ayarlayın. Aşağıdaki örnek, yürütme ilkesini kısıtlı olarak ayarlar:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Restricted
  ```

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, [Microsoft Endpoint Manager yönetim merkezine](https://go.microsoft.com/fwlink/?linkid=2109431)daha fazla bilgi sahibisiniz, dinamik gruplar oluşturmak için sorgu oluşturucuyu kullandınız ve [ADMX ayarlarını](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies)yapılandırmak için Intune 'da Yönetim Şablonları oluşturdunuz. Ayrıca, şirket içinde ve Intune ile bulutta ADMX şablonları kullanmayı da karşılaştırdığınızda. Bir ek olarak, PowerShell cmdlet 'lerini bir yönetim şablonu oluşturmak için kullandınız.

Intune 'daki Yönetim Şablonları hakkında daha fazla bilgi için bkz.:

> [!div class="nextstepaction"]
> [Intune 'da Grup İlkesi ayarlarını yapılandırmak için Windows 10 şablonlarını kullanma](administrative-templates-windows.md)
