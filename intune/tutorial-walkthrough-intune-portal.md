---
title: Öğretici - Azure portalında Intune gözden geçirme
titleSuffix: Microsoft Intune
description: Bu öğreticide, görevlerin nasıl daha iyi anlamak için Intune turu.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 03/28/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c601af8c2b73ac68ec88f45d3684fcfd41f1c87f
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61516390"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Öğretici: Azure portalında Microsoft Intune gözden geçirme

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) bulut bilgi işlem senaryolarına ve olanaklar çeşitli yardımcı olması için 100'den fazla hizmet içeriyor. Microsoft Intune Azure'da kullanılabilen çeşitli hizmetler biridir. Intune, şirketinizin cihazları, uygulamaları ve verileri, şirketinizin güvenlik gereksinimlerini karşıladığından emin olun yardımcı olur. Sahip olduğunuz bir denetime gereksinimleri denetlenmesi gereken kümesi ve bu gereksinimleri karşılanmadığı ne olur. [Azure portalı](https://portal.azure.com), Microsoft Intune hizmetini bulabileceğiniz yerdir. Intune'da kullanılabilen özellikleri anlama çeşitli mobil cihaz Yönetimi (MDM) ve mobil uygulama yönetimi (MAM) görevleri gerçekleştirmenize yardımcı olur.

Bu öğreticide şunları yapacaksınız:
> [!div class="checklist"]
> * Tur Microsoft Intune
> * Azure Portalı'nı yapılandırma

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
Microsoft Intune'u kurmadan önce aşağıdaki gereksinimleri gözden geçirin:

   - [Desteklenen işletim sistemleri ve tarayıcılar](supported-devices-browsers.md) 
   - [Ağ yapılandırma gereksinimleri ve bant genişliği](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz denemesine kaydolma

Intune'u 30 gün boyunca ücretsiz deneyebilirsiniz. Zaten bir iş veya okul hesabınız varsa bu hesapla **oturum açın** ve aboneliklerinize Intune’u ekleyin. Aksi takdirde [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md) kuruluşunuz için Intune kullanmak istiyorsanız.

> [!IMPORTANT]
> Yeni bir hesap için kaydolduktan sonra mevcut bir iş veya okul hesabını birleştirmeniz mümkün olmayacaktır.

## <a name="tour-microsoft-intune"></a>Tur Microsoft Intune

Intune Azure portalında daha iyi anlamak için aşağıdaki adımları izleyin. Turu tamamladıktan sonra daha iyi bir ıntune önemli alanlardan bazıları'nın anlayış sahip olacaksınız.

1. Bir tarayıcı açın ve oturum [Intune portalı](https://aka.ms/intuneportal). Intune'a yeni başladıysanız, ücretsiz deneme aboneliğinizi kullanın.

    ![Microsoft Intune portalı ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Azure'da Intune veya diğer herhangi bir hizmeti açtığınızda, hizmet bir bölmede görüntülenir. Intune'da kullanabilir ilk iş yükleri dahil **cihazları**, **istemci uygulamaları**, **kullanıcılar**, ve **grupları**. Bir hizmetin yalnızca bir alt alanı bir iş yüküne sahiptir. İş yükünü seçtiğinizde bu bölme tam bir sayfa olarak açılır. Açmak ve kapatmak için önceki bölmeye Göster diğer bölmeler çıkış bölmesinde sağ taraftan kaydırın. Bir bölme bir dikey pencere adlandırılır. 

    Varsayılan olarak, Intune açtığınızda göreceğiniz **genel bakış** bölmesi. Bu bölme, uygulama yükleme durumu yanı sıra cihaz atama ve uyumluluk durumu genel görsel bir anlık görüntüsünü sağlar.

2. Gelen [Intune](https://aka.ms/intuneportal)seçin **cihaz kaydı** Intune kiracınızda kayıtlı cihazlar hakkındaki ayrıntıları görüntülemek için. Yeni bir Intune Kiracı ile başlıyorsanız, kayıtlı tüm cihazları henüz yoktur. 

    ![Cihaz kayıt bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Intune, iş gücünüzün cihazları ve uygulamaları, şirket verilerinizi nasıl erişim de dahil olmak üzere yönetmenize olanak tanır. Bu mobil cihaz Yönetimi (MDM) hizmetini kullanmak için cihazların Intune'a ilk kaydedilmesi gerekir. Bir cihaz kaydedildiğinde, ona bir MDM sertifikası verilir. Bu sertifika, Intune hizmeti ile iletişim kurmak için kullanılır. 

    İş gücünüzün cihazlarını Intune'a kaydetmeleri için çeşitli yöntemler vardır. Her bir yöntem cihazın sahipliği (kişisel veya şirket), cihaz türü (iOS, Windows, Android) ve yönetim gereksinimlerine (sıfırlama, benzeşim, kilitleme) bağlıdır. Ancak, cihaz kaydını etkinleştirmeden önce Intune altyapınızı ayarlamanız gerekir. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir. Intune ortamınızı (Kiracı) hazırlığı hakkında daha fazla bilgi için bkz. [Intune'u ayarlama](setup-steps.md). Intune kiracınız hazır olduktan sonra cihazları kaydedebilirsiniz. Cihaz kaydı hakkında daha fazla bilgi için bkz. [Cihaz kaydı nedir?](device-enrollment.md)

3. Gelen [Intune](https://aka.ms/intuneportal)seçin **cihaz uyumluluğu** Intune tarafından yönetilen cihazlar için Uyumluluk ilgili ayrıntıları görüntülemek için. Aşağıdaki görüntüye benzer ayrıntıları görürsünüz.

    ![Cihaz uyumluluk bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Uyumluluk gereksinimleri bir cihaz PIN'i veya cihaz şifrelemeyi gerektirme gibi temelde kurallardır. Cihaz uyumluluk ilkeleri, bir cihaz uyumlu olarak değerlendirilmesi için izlemeniz gereken ayarları ve kuralları tanımlar. Cihaz uyumluluğu kullanmak için şunlara sahip olmalısınız:
    - Intune ve Azure Active Directory (Azure AD) Premium aboneliği
    - Desteklenen bir platform çalıştıran cihazlar
    - Cihazları Intune'a kayıtlı olması gerekir
    - Bir kullanıcı veya birincil kullanıcı için kaydedilen cihazlar.
    
    Daha fazla bilgi için [ıntune cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

4. Gelen [Intune](https://aka.ms/intuneportal)seçin **cihaz Yapılandırması** Intune'da cihaz profilleri hakkında ayrıntılı bilgi görüntülemek için. 

    ![Cihaz yapılandırma bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve Özellikler "yapılandırma profillerini" eklenir. Farklı cihaz ve iOS, Android ve Windows gibi farklı platformlar için profiller oluşturabilirsiniz. Ardından, Intune profili, kuruluşunuzdaki cihazlara uygulamak için kullanabilirsiniz.   

    Cihaz yapılandırması hakkında daha fazla bilgi için bkz: [Intune cihaz profillerini kullanarak cihazlarınızda özellikleri ayarları uygulamak](device-profiles.md).

5. Gelen [Intune](https://aka.ms/intuneportal)seçin **cihazları** Intune hakkındaki ayrıntıları görüntülemek için Kiracı cihazlar kayıtlı. Yeni bir Intune kaydı ile başlıyorsanız, kayıtlı tüm cihazları henüz yoktur. 

    ![Cihaz kayıt bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)
    
    **Cihazları** bölmesi, kayıtlı cihazlar kiracınız hakkında ayrıntılar sağlar. Tıklayabilirsiniz **tüm cihazlar** Intune kiracınız için cihazların bir listesini görüntülemek için. 

6. Gelen [Intune](https://aka.ms/intuneportal)seçin **istemci uygulamaları** uygulama yükleme durumu görüntülemek için.

    ![İstemci uygulamaları bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)
    
    BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz. Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Ekleme ve uygulamaları atama hakkında daha fazla bilgi için bkz. [uygulamaları Microsoft Intune ekleme](apps-add.md) ve [Intune gruplara uygulama atama](apps-deploy.md).

7. Gelen [Intune](https://aka.ms/intuneportal)seçin **koşullu erişim** erişim ilkeleri hakkındaki ayrıntıları görüntülemek için.

    ![Koşullu erişim bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Koşullu erişim, e-postanıza ve şirket kaynaklarınıza bağlanmasına izin verilen cihazları ve uygulamaları denetlemek için kullanabileceğiniz yolları gösterir. Cihaz tabanlı ve uygulama tabanlı koşullu erişim hakkında bilgi edinin ve koşullu erişimi Intune'la kullanmaya yönelik yaygın senaryolar bulmak için bkz: [koşullu erişim nedir?](conditional-access.md)

8. Gelen [Intune](https://aka.ms/intuneportal)seçin **kullanıcılar** Intune'a eklediğiniz kullanıcı hakkındaki ayrıntıları görüntülemek için. Bu, şirketinizin iş gücü kullanıcılardır. 
 
    ![Kullanıcılar bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Doğrudan Intune'a kullanıcı ekleme ya da şirket içi Active Directory'den kullanıcıları eşitlemeye. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Bu gibi durumlarda, kullanıcılar ayrıca Intune'a erişmek için ek izinler verebilirsiniz. Daha fazla bilgi için [kullanıcı ekleme ve Intune'a yönetici izni verme](users-add.md).

9. Gelen [Intune](https://aka.ms/intuneportal)seçin **grupları** Intune'da bulunan Azure Active Directory (Azure AD) grupları hakkındaki ayrıntıları görüntülemek için. Bir Intune Yöneticisi, cihazları ve kullanıcıları yönetmek için grupları kullanın. 

    ![Grupları bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Grupları kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin, çok sayıda kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulama dağıtma. Grupları hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için gruplar ekleyin](groups-add.md).

10. Gelen [Intune](https://aka.ms/intuneportal)seçin **Yardım ve Destek** için yardım iste. BT yöneticisi, kullandığınız **Yardım ve Destek** aramak ve çözümleri yanı sıra Intune için çevrimiçi destek bileti görüntülemek için seçenek. 

    ![Yardım ve Destek bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Bir destek bileti oluşturmak için hesabınızı bir Azure Active Directory'de Yönetici rolü olarak atanması gerekir. Yönetici rollerini içeren **Intune yönetici**, **genel yönetici**, ve **Hizmet Yöneticisi**. Daha fazla bilgi için [Intune için destek alma](get-support.md).

11. Gelen [Intune](https://aka.ms/intuneportal)seçin **Kiracı durumu** , Intune kiracınıza ilgili ayrıntıları görüntülemek için.

    ![Kiracı durumu bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Bağlayıcı durumu, Intune hizmet durumu ve Intune haber Kiracı durumu ayrıntıları içerir. Kiracı veya Intune kendisi ile herhangi bir sorun varsa, Ayrıntılar bulabilirsiniz **Kiracı durumu** bölmesi. Daha fazla bilgi için [Intune Kiracı durumu](tenant-status.md).

12. Gelen [Intune](https://aka.ms/intuneportal)seçin **sorun giderme** sorun giderme ipuçları, destek istemeden veya Intune durumunu denetleme kısayol ulaşmak için. Bu bilgiler belirli seçtiğiniz Intune kullanıcı.

    ![Sorun giderme bölmesinin ekran görüntüsü](media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

İçinde Intune sorun giderme hakkında daha fazla bilgi için bkz. [şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Azure Portalı'nı yapılandırma

Azure, özelleştirme ve Portalı'nın görünümünü yapılandırmanıza olanak sağlar.

### <a name="change-the-sidebar"></a>Kenar çubuğunu değiştirme

Azure portalının sol tarafındaki **kenar çubuğu**, size kullanılabilir Azure hizmetlerinin bir listesini gösterir. Bu kapsamlı listenin varsayılan görüntüsünü değiştirerek sizin için önemli olan hizmetleri sürekli görüntüleyebilirsiniz. Aşağıdaki bilgilerde listenin başına eklenecek hizmet örneği olarak Intune kullanılır.

![‘Diğer hizmetler’ listesinde Microsoft Intune’u arayan bir kullanıcı.](./media/azure-add-intune1.png)

1. Sayfanın solundaki kenar çubuğundan **Tüm hizmetler**’i seçin.
2. Filtre kutusunda **Intune**’u arayın.
3. Intune’u sık kullanılan hizmetler listenizin altına eklemek için **yıldız** simgesini seçin.
4. Intune hizmetinin üzerine gelin. Hizmet adının sağ tarafındaki **üç dikey noktayı** kullanarak Intune’u seçin ve sürükleyin.

### <a name="change-the-dashboard"></a>Panoyu değiştirme

Varsayılan giriş sayfanız **panodur**. Bu sayfada, sizin için önem taşıyan bilgileri göstermek üzere kutucukları özelleştirirsiniz.

![Genel yeni panonun görüntüsü. Tüm hizmetleri soldaki kenar çubuğunda ve ana panoyu ortada görüntüler. Pano değiştirme düğmelerinin yanı sıra tüm kaynaklara, hızlı başlangıç eğiticilerine, hizmet durumuna ve Azure marketine erişim sağlayan kutucuklar da üsttedir.](./media/azure-default-dashboard.png)

Geçerli panonuzu değiştirmek için **Panoyu düzenle** düğmesini seçin. Varsayılan panonuzu değiştirmek istemiyorsanız **Yeni bir pano** da oluşturabilirsiniz. Yeni bir pano oluşturmak, size **Kutucuk Galerisi** olan boş, özel bir pano sağlar ve burada kutucuk ekleyebilir veya bunları yeniden düzenleyebilirsiniz. Kutucukları **Genel** kategorilerinden ve **Türlerinden**, **Arama** ile veya bir **Kaynak grubu** veya**Etiket** aracılığıyla bulabilirsiniz.

Ayrıca herhangi bir **üç nokta** düğmesine tıklayıp **Panoya sabitle**’yi seçerek kutucukları doğrudan panonuza ekleyebilirsiniz.

![Intune’da, bir grubun en sağında “Panoya sabitle” seçeneğini barındıran Kullanıcılar ve Gruplar > Tüm gruplar konumunun yakın görüntüsü.](./media/azure-pin-to-dashboard.png)

Bu özellik, Intune’a kullanıcı ve gruplar gibi daha fazla içerik eklediğinizde daha çok işinize yarayacaktır.

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Intune hızla çalıştırmaya başlamak için ücretsiz bir Intune hesabı ayarlayarak Intune hızlı başlangıç şablonları adım.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Microsoft Intune ücretsiz olarak deneyin](free-trial-sign-up.md)


