---
title: Öğretici-Azure portal Intune 'da Izlenecek yol
titleSuffix: Microsoft Intune
description: Bu öğreticide, görevlerin nasıl gerçekleştirileceğini daha iyi anlamak için Microsoft Intune turuna katılın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 203d243df3e8ae496e7ff78f20222fd361417c3d
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514056"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Öğretici: Azure portal Microsoft Intune Izlenecek yol

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) , çok sayıda bulut bilgi işlem senaryosu ve olasılıklarıyla size yardımcı olmak için 100 'den fazla hizmet içerir. Azure 'da bulunan çeşitli hizmetlerden biridir Microsoft Intune. Intune, şirketinizin cihazlarınızın, uygulamalarının ve verilerinin şirketinizin güvenlik gereksinimlerini karşıladığından emin olmanıza yardımcı olur. Hangi gereksinimlerin denetlenmesi gerektiğini ve bu gereksinimler karşılanmazsa ne olacağını ayarlamaya yönelik denetime sahipsiniz. [Azure portalı](https://portal.azure.com), Microsoft Intune hizmetini bulabileceğiniz yerdir. Intune 'da kullanılabilen özellikleri anlamak çeşitli mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) görevlerini gerçekleştirmenize yardımcı olur.

Bu öğreticide şunları yapacaksınız:
> [!div class="checklist"]
> * Tur Microsoft Intune
> * Azure portal yapılandırma

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
Microsoft Intune'u kurmadan önce aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen işletim sistemleri ve tarayıcılar](../supported-devices-browsers.md) 
- [Ağ yapılandırma gereksinimleri ve bant genişliği](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz denemesine kaydolma

Intune'u 30 gün boyunca ücretsiz deneyebilirsiniz. Zaten bir iş veya okul hesabınız varsa bu hesapla **oturum açın** ve aboneliklerinize Intune’u ekleyin. Aksi takdirde, kuruluşunuz için Intune 'U kullanmak üzere [ücretsiz bir deneme hesabına kaydolabilirsiniz](free-trial-sign-up.md) .

> [!IMPORTANT]
> Yeni bir hesap için kaydolduktan sonra mevcut bir iş veya okul hesabını birleştirmeniz mümkün olmayacaktır.

## <a name="tour-microsoft-intune"></a>Tur Microsoft Intune

Azure portal Intune 'U daha iyi anlamak için aşağıdaki adımları izleyin. Turu tamamladıktan sonra, Intune 'un bazı önemli alanlarından bazılarını daha iyi anlayacaksınız.

1. Bir tarayıcı açın ve [Intune portalında](https://aka.ms/intuneportal)oturum açın. Intune 'u yeni kullanmaya çalışıyorsanız, ücretsiz deneme aboneliğinizi kullanın.

    ![Microsoft Intune portalının ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Intune 'u veya Azure 'da herhangi bir hizmeti açtığınızda, hizmet bir bölmede görüntülenir. Intune 'da kullanabileceğiniz ilk iş yüklerinden bazıları **cihazları**, **istemci uygulamalarını**, **kullanıcıları**ve **grupları**içerir. Bir iş yükü, yalnızca bir hizmetin alt alanıdır. İş yükünü seçtiğinizde bu bölme tam sayfa olarak açılır. Diğer bölmeler, açıldığında bölmenin sağ tarafından çıkar ve önceki bölmeyi açığa çıkarmak için kapanır. Bir bölme de dikey pencere olarak adlandırılır. 

    Varsayılan olarak, Intune 'U açtığınızda **genel bakış** bölmesini görürsünüz. Bu bölme, cihaz atamasının ve uyumluluk durumunun yanı sıra uygulama yükleme durumunun genel bir görsel anlık görüntüsünü sunar.

2. Intune ['da](https://aka.ms/intuneportal), Intune kiracınızda kayıtlı cihazların ayrıntılarını göstermek için **cihaz kaydı** ' nı seçin. Yeni bir Intune kiracısıyla başladıysanız, henüz kayıtlı bir aygıtınız olmayacaktır. 

    ![Cihaz kayıt bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Intune, iş gücünüzün cihazlarını ve uygulamalarını, şirket verilerinize nasıl eriştikleri gibi yönetmenize olanak sağlar. Bu mobil cihaz yönetimi (MDM) hizmetini kullanmak için önce cihazların Intune 'A kaydolması gerekir. Bir cihaz kaydedildiğinde, ona bir MDM sertifikası verilir. Bu sertifika, Intune hizmeti ile iletişim kurmak için kullanılır. 

    İş gücünüzün cihazlarını Intune 'a kaydetmek için çeşitli yöntemler vardır. Her yöntem cihazın sahipliğini (kişisel veya şirket), cihaz türü (iOS/ıpados, Windows, Android) ve yönetim gereksinimlerine (sıfırlamaları, benzeşim, kilitleme) bağlıdır. Ancak, cihaz kaydını etkinleştirebilmeniz için Intune altyapınızı ayarlamanız gerekir. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir. Intune ortamınızı (kiracı) hazırlayın hakkında daha fazla bilgi için bkz. [Intune 'U ayarlama](setup-steps.md). Intune kiracınızı kullanmaya başladıktan sonra cihazları kaydedebilirsiniz. Cihaz kaydı hakkında daha fazla bilgi için bkz. [Cihaz kaydı nedir?](../enrollment/device-enrollment.md)

3. Intune tarafından yönetilen cihazların uyumluluk ayrıntılarını göstermek için [Intune](https://aka.ms/intuneportal)'dan **cihaz uyumluluğu** ' nu seçin. Aşağıdaki görüntüye benzer Ayrıntılar görürsünüz.

    ![Cihaz uyumluluk bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Uyumluluk gereksinimleri, bir cihaz PIN 'ı gerektirme veya cihaz şifrelemesi gerektirme gibi temel kurallardır. Cihaz uyumluluk ilkeleri, bir cihazın uyumlu kabul edilmesi için izlenmesi gereken kuralları ve ayarları tanımlar. Cihaz uyumluluğunu kullanmak için şunları yapmanız gerekir:
    - Bir Intune ve Azure Active Directory (Azure AD) Premium aboneliği
    - Desteklenen bir platform çalıştıran cihazlar
    - Cihazların Intune 'A kayıtlı olması gerekir
    - Bir kullanıcıya veya birincil kullanıcıya kayıtlı olan cihazlar.
    
    Daha fazla bilgi için bkz. [Intune 'da cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

4. Intune ['da](https://aka.ms/intuneportal), Intune 'da cihaz profilleriyle ilgili ayrıntıları göstermek için **cihaz yapılandırması** ' nı seçin.

    ![Cihaz yapılandırma bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler "yapılandırma profillerine" eklenir. Farklı cihazlar ve iOS/ıpados, Android ve Windows dahil farklı platformlar için profiller oluşturabilirsiniz. Daha sonra, Intune 'u kuruluşunuzdaki cihazlara uygulamak için Intune ' u kullanabilirsiniz.   

    Cihaz yapılandırması hakkında daha fazla bilgi için bkz. [Microsoft Intune cihaz profillerini kullanarak cihazlarınızda özellik ayarlarını uygulama](../configuration/device-profiles.md).

5. Intune ['da,](https://aka.ms/intuneportal)Intune kiracınızın kayıtlı cihazlarınızla ilgili ayrıntıları göstermek için **cihazlar** ' ı seçin. Yeni bir Intune kaydı ile başlıyorsanız, henüz kayıtlı cihazlarınızın olmaması gerekir.

    ![Cihaz kayıt bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)

    **Cihazlar** bölmesi, kiracınızın kayıtlı cihazlarınızla ilgili ayrıntıları sağlar. Intune kiracınızın cihaz listesini göstermek için **tüm cihazlar** ' a tıklayabilirsiniz.

6. [Intune](https://aka.ms/intuneportal)'da, uygulama yükleme durumunu göstermek için **istemci uygulamalar** ' ı seçin.

    ![İstemci uygulamaları bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)

    BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz. Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Uygulama ekleme ve atama hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md) ve [Microsoft Intune olan gruplara uygulama atama](../apps/apps-deploy.md).

7. [Intune](https://aka.ms/intuneportal)'da, erişim ilkeleriyle ilgili ayrıntıları göstermek Için **koşullu erişim** ' i seçin.

    ![Koşullu erişim bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Koşullu erişim, e-postanıza ve şirket kaynaklarınıza bağlanmasına izin verilen cihazları ve uygulamaları denetleyebilmeniz için yollar anlamına gelir. Cihaz tabanlı ve uygulama tabanlı koşullu erişim hakkında bilgi edinmek ve Intune ile koşullu erişim kullanmak için sık karşılaşılan senaryolar bulmak için bkz. [koşullu erişim nedir?](../protect/conditional-access.md)

8. Intune ['da](https://aka.ms/intuneportal), Intune 'a dahil ettiğiniz kullanıcılarla ilgili ayrıntıları göstermek için **Kullanıcılar** ' ı seçin. Bu kullanıcılar, şirketinizin iş gücünüz.

    ![Kullanıcılar bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Kullanıcıları doğrudan Intune 'a ekleyebilir veya şirket içi Active Directory Kullanıcıları senkronize edebilirsiniz. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Kullanıcılara Intune 'a erişmek için ek izinler de verebilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı ekleme ve Intune 'a yönetici izni verme](users-add.md).

9. Intune 'da, Intune 'a dahil olan Azure Active Directory (Azure AD) gruplarıyla ilgili ayrıntıları göstermek için **gruplar** [' ı seçin](https://aka.ms/intuneportal). Bir Intune Yöneticisi olarak, cihazları ve kullanıcıları yönetmek için grupları kullanırsınız.

    ![Gruplar bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Grupları, Kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin, birçok kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulama dağıtabilirsiniz. Gruplar hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](../groups-add.md).

10. [Intune](https://aka.ms/intuneportal)'da yardım Istemek için **Yardım ve destek** ' i seçin. BT Yöneticisi olarak, çözümleri aramak ve görüntülemek için **Yardım ve destek** seçeneğini, ayrıca Intune için bir çevrimiçi destek bileti dosyasını da kullanabilirsiniz. 

    ![Yardım ve destek bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Bir destek bileti oluşturmak için, hesabınızın Azure Active Directory bir yönetici rolü olarak atanması gerekir. Yönetici rolleri, **Intune Yöneticisi**, **genel yönetici**ve **Hizmet Yöneticisi**içerir. Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](../get-support.md).

11. Intune ['da,](https://aka.ms/intuneportal)Intune kiracınızla ilgili ayrıntıları göstermek Için **kiracı durumu** ' nu seçin.

    ![Kiracı durumu bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Kiracı durumu ayrıntıları bağlayıcı durumu, Intune hizmet durumu ve Intune haberleri içerir. Kiracınızda veya Intune ile ilgili herhangi bir sorun varsa, bu bilgileri **kiracı durumu** bölmesinde bulabilirsiniz. Daha fazla bilgi için bkz. [Intune kiracı durumu](../tenant-status.md).

12. [Intune](https://aka.ms/intuneportal)'da sorun giderme ipuçlarında bir kısayola ulaşmak, destek Istemek veya Intune durumunu denetlemek Için **sorun gider** ' i seçin. Bu bilgiler, seçtiğiniz Intune kullanıcısına özeldir.

    ![Sorun giderme bölmesinin ekran görüntüsü](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Intune 'da sorun giderme hakkında daha fazla bilgi için bkz. [şirketinizde kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](../help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Azure portal yapılandırma

Azure, portalın görünümünü özelleştirmenize ve yapılandırmanıza olanak tanır.

### <a name="change-the-sidebar"></a>Kenar çubuğunu değiştirme

Azure portalının sol tarafındaki **kenar çubuğu**, size kullanılabilir Azure hizmetlerinin bir listesini gösterir. Bu kapsamlı listenin varsayılan görüntüsünü değiştirerek sizin için önemli olan hizmetleri sürekli görüntüleyebilirsiniz. Aşağıdaki bilgilerde listenin başına eklenecek hizmet örneği olarak Intune kullanılır.

![‘Diğer hizmetler’ listesinde Microsoft Intune’u arayan bir kullanıcı.](./media/tutorial-walkthrough-intune-portal/azure-add-intune1.png)

1. Sayfanın solundaki kenar çubuğundan **Tüm hizmetler**’i seçin.
2. Filtre kutusunda **Intune**’u arayın.
3. Intune’u sık kullanılan hizmetler listenizin altına eklemek için **yıldız** simgesini seçin.
4. Intune hizmetinin üzerine gelin. Hizmet adının sağ tarafındaki **üç dikey noktayı** kullanarak Intune’u seçin ve sürükleyin.

### <a name="change-the-dashboard"></a>Panoyu değiştirme

Varsayılan giriş sayfanız **panodur**. Bu sayfada, sizin için önem taşıyan bilgileri göstermek üzere kutucukları özelleştirirsiniz.

![Genel yeni panonun görüntüsü. Tüm hizmetleri soldaki kenar çubuğunda ve ana panoyu ortada görüntüler. Pano değiştirme düğmelerinin yanı sıra tüm kaynaklara, hızlı başlangıç eğiticilerine, hizmet durumuna ve Azure marketine erişim sağlayan kutucuklar da üsttedir.](./media/tutorial-walkthrough-intune-portal/azure-default-dashboard.png)

Geçerli panonuzu değiştirmek için **Panoyu düzenle** düğmesini seçin. Varsayılan panonuzu değiştirmek istemiyorsanız **Yeni bir pano** da oluşturabilirsiniz. Yeni bir pano oluşturmak, size **Kutucuk Galerisi** olan boş, özel bir pano sağlar ve burada kutucuk ekleyebilir veya bunları yeniden düzenleyebilirsiniz. Kutucukları **Genel** kategorilerinden ve **Türlerinden**, **Arama** ile veya bir **Kaynak grubu** veya**Etiket** aracılığıyla bulabilirsiniz.

Ayrıca herhangi bir **üç nokta** düğmesine tıklayıp **Panoya sabitle**’yi seçerek kutucukları doğrudan panonuza ekleyebilirsiniz.

![Intune’da, bir grubun en sağında “Panoya sabitle” seçeneğini barındıran Kullanıcılar ve Gruplar > Tüm gruplar konumunun yakın görüntüsü.](./media/tutorial-walkthrough-intune-portal/azure-pin-to-dashboard.png)

Bu özellik, Intune’a kullanıcı ve gruplar gibi daha fazla içerik eklediğinizde daha çok işinize yarayacaktır.

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Intune hızlı bir şekilde çalıştırmak için, önce ücretsiz bir Intune hesabı ayarlayarak Intune hızlı başlangıç adımlarını izleyin.

> [!div class="nextstepaction"]
> [Hızlı başlangıç: Microsoft Intune ücretsiz deneyin](free-trial-sign-up.md)
