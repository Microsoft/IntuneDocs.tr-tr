---
title: Öğretici-Microsoft Endpoint Manager 'da Intune 'da Izlenecek yol
titleSuffix: Microsoft Intune
description: Bu öğreticide, görevlerin nasıl gerçekleştirileceğini daha iyi anlamak için Microsoft Endpoint Manager Yönetim merkezinde Microsoft Intune turuna katılın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune from the Microsoft Endpoint Manager admin center.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 267f09c3dc16aab10fbe64f0e8662ee6f7c7ffa0
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2019
ms.locfileid: "74908227"
---
# <a name="tutorial-walkthrough-intune-in-microsoft-endpoint-manager"></a>Öğretici: Microsoft Endpoint Manager 'da Intune 'da Izlenecek yol

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) , çok sayıda bulut bilgi işlem senaryosu ve olasılıklarıyla size yardımcı olmak için 100 'den fazla hizmet içerir. Azure 'da bulunan çeşitli hizmetlerden biridir Microsoft Intune. Intune, şirketinizin cihazlarınızın, uygulamalarının ve verilerinin şirketinizin güvenlik gereksinimlerini karşıladığından emin olmanıza yardımcı olur. Hangi gereksinimlerin denetlenmesi gerektiğini ve bu gereksinimler karşılanmazsa ne olacağını ayarlamaya yönelik denetime sahipsiniz. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) , Microsoft Intune hizmetini ve cihaz yönetimiyle ilgili diğer ayarları bulabileceğiniz yerdir. Intune 'da kullanılabilen özellikleri anlamak çeşitli mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) görevlerini gerçekleştirmenize yardımcı olur.

> [!NOTE]
> Microsoft Uç Nokta Yöneticisi, tüm uç noktalarınızı yönetmek için tek ve tümleşik bir uç nokta yönetim platformudur. Bu Microsoft Endpoint Manager Yönetim Merkezi ConfigMgr ve Microsoft Intune tümleştirir.

Bu öğreticide şunları yapacaksınız:
> [!div class="checklist"]
> * Microsoft Endpoint Manager Yönetim Merkezi turuna katılın
> * Microsoft Endpoint Manager Yönetim Merkezi görünümünüzü özelleştirin

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
Microsoft Intune'u kurmadan önce aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen işletim sistemleri ve tarayıcılar](../supported-devices-browsers.md) 
- [Ağ yapılandırma gereksinimleri ve bant genişliği](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz denemesine kaydolma

Intune'u 30 gün boyunca ücretsiz deneyebilirsiniz. Zaten bir iş veya okul hesabınız varsa bu hesapla **oturum açın** ve aboneliklerinize Intune’u ekleyin. Aksi takdirde, kuruluşunuz için Intune 'U kullanmak üzere [ücretsiz bir deneme hesabına kaydolabilirsiniz](free-trial-sign-up.md) .

> [!IMPORTANT]
> Yeni bir hesap için kaydolduktan sonra mevcut bir iş veya okul hesabını birleştirmeniz mümkün olmayacaktır.

## <a name="tour-microsoft-intune-in-the-microsoft-endpoint-manager-admin-center"></a>Microsoft Endpoint Manager Yönetim merkezinde Tur Microsoft Intune

Intune 'U Microsoft Endpoint Manager Yönetim Merkezi 'nde daha iyi anlamak için aşağıdaki adımları izleyin. Turu tamamladıktan sonra, Intune 'un bazı önemli alanlarından bazılarını daha iyi anlayacaksınız.

1. Bir tarayıcı açın ve [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın. Intune 'u yeni kullanmaya çalışıyorsanız, ücretsiz deneme aboneliğinizi kullanın.

    ![Microsoft Endpoint Manager Yönetim Merkezi-giriş sayfasının ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-01.png)

    Microsoft Uç Nokta Yöneticisi 'Ni veya Azure 'da başka bir hizmeti açtığınızda, hizmet bir bölmede görüntülenir. Intune 'da kullanabileceğiniz ilk iş yüklerinden bazıları **cihazları**, **uygulamaları**, **kullanıcıları**ve **grupları**içerir. Bir iş yükü, yalnızca bir hizmetin alt alanıdır. İş yükünü seçtiğinizde bu bölme tam sayfa olarak açılır. Diğer bölmeler, açıldığında bölmenin sağ tarafından çıkar ve önceki bölmeyi açığa çıkarmak için kapanır. 

    Varsayılan olarak, Microsoft Uç Nokta Yöneticisi 'Ni açtığınızda **giriş sayfası** bölmesini görürsünüz. Bu bölme, kiracı durumu ve uyumluluk durumunun genel bir görsel anlık görüntüsünü ve diğer yararlı ilgili bağlantıları sağlar.

2. Gezinti bölmesinden, Intune kiracınızdaki cihazlar ve istemci uygulamalarıyla ilgili genel ayrıntıları göstermek için **Pano** ' yı seçin. Yeni bir Intune kiracısıyla başladıysanız, henüz kayıtlı bir aygıtınız olmayacaktır. 

    ![Microsoft Endpoint Manager Yönetim Merkezi-Pano ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-02.png)
    
    Intune, iş gücünüzün cihazlarını ve uygulamalarını, şirket verilerinize nasıl eriştikleri gibi yönetmenize olanak sağlar. Bu mobil cihaz yönetimi (MDM) hizmetini kullanmak için önce cihazların Intune 'A kaydolması gerekir. Bir cihaz kaydedildiğinde, ona bir MDM sertifikası verilir. Bu sertifika, Intune hizmeti ile iletişim kurmak için kullanılır. 

    İş gücünüzün cihazlarını Intune 'a kaydetmek için çeşitli yöntemler vardır. Her bir yöntem cihazın sahipliği (kişisel veya şirket), cihaz türü (iOS, Windows, Android) ve yönetim gereksinimlerine (sıfırlama, benzeşim, kilitleme) bağlıdır. Ancak, cihaz kaydını etkinleştirebilmeniz için Intune altyapınızı ayarlamanız gerekir. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir. Intune ortamınızı (kiracı) hazırlayın hakkında daha fazla bilgi için bkz. [Intune 'U ayarlama](setup-steps.md). Intune kiracınızı kullanmaya başladıktan sonra cihazları kaydedebilirsiniz. Cihaz kaydı hakkında daha fazla bilgi için bkz. [Cihaz kaydı nedir?](../enrollment/device-enrollment.md)

3. Gezinti bölmesinden, Intune kiracınızda kayıtlı cihazların ayrıntılarını göstermek için **cihazlar** ' ı seçin. 

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **cihazlar**' ı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    **Cihazlar-genel bakış** bölmesinde, aşağıdaki durumların ve uyarıların özetini görüntülemenize olanak tanıyan birkaç sekme bulunur:
    - **Kayıt durumu** -Intune 'a kayıtlı cihazlar için platforma ve kayıt hatalarıyla ilgili ayrıntıları gözden geçirin.
    - **Kayıt uyarıları** -platforma göre atanmamış cihazlar hakkında daha fazla ayrıntı bulun. 
    - **Uyumluluk durumu** -cihaz, ilke, ayar, tehditler ve korumaya göre uyumluluk durumunu gözden geçirin. Ayrıca, bu bölme uyumluluk ilkesi olmayan cihazların bir listesini sağlar.
    - **Yapılandırma durumu** -cihaz profillerinin yapılandırma durumunu ve ayrıca profil dağıtımını gözden geçirin. 
    - **Yazılım güncelleştirme durumu** -tüm cihazlar ve tüm kullanıcılar için dağıtım durumunun görselini görüntüleyin.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-cihazlar](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-03.png)

4. **Cihazlar-genel bakış** bölmesinden, Intune tarafından yönetilen cihazların uyumluluk ayrıntılarını göstermek için **uyumluluk ilkeleri** ' ni seçin. Aşağıdaki görüntüye benzer Ayrıntılar görürsünüz.

    ![Microsoft Endpoint Manager Yönetim Merkezi-uyumluluk ilkelerinin ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-04.png)
    
    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açıp **cihaz uyumluluğu**' nu seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Uyumluluk gereksinimleri, bir cihaz PIN 'ı gerektirme veya cihaz şifrelemesi gerektirme gibi temel kurallardır. Cihaz uyumluluk ilkeleri, bir cihazın uyumlu kabul edilmesi için izlenmesi gereken kuralları ve ayarları tanımlar. Cihaz uyumluluğunu kullanmak için şunları yapmanız gerekir:
    - Bir Intune ve Azure Active Directory (Azure AD) Premium aboneliği
    - Desteklenen bir platform çalıştıran cihazlar
    - Cihazların Intune 'A kayıtlı olması gerekir
    - Bir kullanıcıya veya birincil kullanıcıya kayıtlı olan cihazlar.
    
    Daha fazla bilgi için bkz. [Intune 'da cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

5. **Cihazlar-genel bakış** bölmesinden, erişim ilkeleriyle ilgili ayrıntıları göstermek Için **koşullu erişim** ' i seçin.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-koşullu erişim](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-05.png)

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **koşullu erişim**' i seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Koşullu erişim, e-postanıza ve şirket kaynaklarınıza bağlanmasına izin verilen cihazları ve uygulamaları denetleyebilmeniz için yollar anlamına gelir. Cihaz tabanlı ve uygulama tabanlı koşullu erişim hakkında bilgi edinmek ve Intune ile koşullu erişim kullanmak için sık karşılaşılan senaryolar bulmak için bkz. [koşullu erişim nedir?](../protect/conditional-access.md)

6. Gezinti bölmesinden, Intune 'da cihaz profilleriyle ilgili ayrıntıları göstermek için **cihazlar** > **yapılandırma profilleri** ' ni seçin.

    ![Microsoft Endpoint Manager yönetim merkezi-yapılandırma profillerinin ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-06.png)
    
    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açıp **cihaz yapılandırması**' nı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler "yapılandırma profillerine" eklenir. Farklı cihazlar ve iOS, Android, macOS ve Windows gibi farklı platformlar için profiller oluşturabilirsiniz. Daha sonra, Intune 'u kuruluşunuzdaki cihazlara uygulamak için Intune ' u kullanabilirsiniz.   

    Cihaz yapılandırması hakkında daha fazla bilgi için bkz. [Microsoft Intune cihaz profillerini kullanarak cihazlarınızda özellik ayarlarını uygulama](../configuration/device-profiles.md).

7. Gezinti bölmesinden, Intune kiracınızın kayıtlı cihazlarınızla ilgili ayrıntıları göstermek için **cihazlar** > **tüm cihazlar** ' ı seçin. Yeni bir Intune kaydı ile başlıyorsanız, henüz kayıtlı cihazlarınızın olmaması gerekir.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-tüm cihazlar](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-07.png)

    Bu cihaz listesi uyumluluk, işletim sistemi sürümü ve son iade etme tarihiyle ilgili önemli ayrıntıları gösterir.

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **tüm cihazlar** > **cihazlar** ' ı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.
 
8. Uygulama durumuna genel bir bakış göstermek için gezinti bölmesinden **uygulamalar** ' ı seçin. Bu bölme aşağıdaki sekmelere göre uygulama yükleme durumu sağlar:

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **istemci uygulamaları**' nı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    **Uygulamalar-genel bakış** bölmesinde aşağıdaki durumların özetini görüntülemenize olanak tanıyan iki sekme bulunur:
    - **Yükleme durumu** -cihaza göre en iyi yükleme başarısızlıklarını ve yükleme hatalarıyla birlikte uygulamaları görüntüleyin.  
    - **Uygulama koruma ilkesi durumu** -atanan kullanıcıların, uygulama koruma ilkelerine ve bayraklı kullanıcılara ilişkin ayrıntılarını bulun.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-uygulamalar](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-08.png)

    BT yöneticisi olarak Microsoft Intune'u şirketinizin iş gücünün kullandığı istemci uygulamaları yönetmek için kullanabilirsiniz. Bu işlev, cihazları yönetmeye ve verileri korumaya ek niteliğindedir. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. Buna ek olarak, Intune’a kaydolmamış cihazlarda uygulamaları atamak ve yönetmek isteyebilirsiniz. Intune, ihtiyacınız olan uygulamaları istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. 

    > [!NOTE]
    > **Uygulamalar-genel bakış** bölmesi, kiracı durumu ve hesap ayrıntıları da sağlar.

    Uygulama ekleme ve atama hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md) ve [Microsoft Intune olan gruplara uygulama atama](../apps/apps-deploy.md).

9. **Uygulamalar-genel bakış** bölmesinden, Intune 'a eklenmiş uygulamaların listesini görmek için **tüm uygulamalar** ' ı seçin.

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **Istemci uygulamaları** > **uygulamalar**' ı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Platforma, Intune 'a göre çeşitli farklı uygulama türleri ekleyebilirsiniz. Bir uygulama eklendikten sonra, Kullanıcı gruplarına atayabilirsiniz. 

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-tüm uygulamalar](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-09.png)

    Daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](~/apps/apps-add.md). 

10. Gezinti bölmesinden, Intune 'a dahil ettiğiniz kullanıcılarla ilgili ayrıntıları göstermek için **Kullanıcılar** ' ı seçin. Bu kullanıcılar, şirketinizin iş gücünüz.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-kullanıcılar](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-10.png)

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **Kullanıcılar**' ı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Kullanıcıları doğrudan Intune 'a ekleyebilir veya şirket içi Active Directory Kullanıcıları senkronize edebilirsiniz. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Kullanıcılara Intune 'a erişmek için ek izinler de verebilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı ekleme ve Intune 'a yönetici izni verme](users-add.md).

11. Gezinti bölmesinden, Intune 'a dahil olan Azure Active Directory (Azure AD) gruplarıyla ilgili ayrıntıları göstermek için **gruplar** ' ı seçin. Bir Intune Yöneticisi olarak, cihazları ve kullanıcıları yönetmek için grupları kullanırsınız.

    ![Microsoft Endpoint Manager Yönetim Merkezi-gruplarının ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-11.png)

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açıp **gruplar**' ı seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Grupları, Kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin, birçok kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulama dağıtabilirsiniz. Gruplar hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](../groups-add.md).

12. Intune kiracınızın ayrıntılarını göstermek için gezinti bölmesinden **Kiracı Yönetimi** ' ni seçin.

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açıp **kiracı durumu**' nu seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    Kiracı **Yöneticisi-kiracı durumu** bölmesi, **kiracı ayrıntıları**, **bağlayıcı durumu**ve **hizmet durumu panosu**için sekmeler sağlar. Kiracınızda veya Intune ile ilgili herhangi bir sorun varsa, bu bölmeden kullanılabilen ayrıntıları bulabilirsiniz. 

    ![Microsoft Endpoint Manager Yönetim Merkezi-kiracı durumunun ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-12.png)

    Daha fazla bilgi için bkz. [Intune kiracı durumu](../tenant-status.md).

13. Gezinti bölmesinden, belirli bir kullanıcının durum ayrıntılarını denetlemek için **sorun giderme + destek > sorun** **giderme '** yi seçin. 

    > [!TIP]
    > Daha önce Azure portal Intune kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **sorun giderme**' yi seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    **Atamalar** açılan listesinden, istemci uygulamaları, ilkeler, güncelleştirme halkaları ve kayıt kısıtlamaları için hedeflenen atamaları görüntülemeyi seçebilirsiniz. Ayrıca, bu bölme belirli bir kullanıcı için cihaz ayrıntıları, uygulama koruma durumu ve kayıt sorunları sağlar.

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-sorun giderme](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-13.png)

    Intune 'da sorun giderme hakkında daha fazla bilgi için bkz. [şirketinizde kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](../help-desk-operators.md).

14. Gezinti bölmesinden, yardım istemek için **sorun giderme + destek** > **Yardım ve destek** ' i seçin. 

    > [!TIP]
    > Intune 'u Azure portal daha önce kullandıysanız, [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açarak ve **Yardım ve destek '** i seçerek yukarıdaki ayrıntıları Azure Portal bulabilirsiniz.

    BT Yöneticisi olarak, çözümleri aramak ve görüntülemek için **Yardım ve destek** seçeneğini, ayrıca Intune için bir çevrimiçi destek bileti dosyasını da kullanabilirsiniz. 

    ![Microsoft Endpoint Manager Yönetim Merkezi 'nin ekran görüntüsü-yardım ve destek](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-14.png)

    Bir destek bileti oluşturmak için, hesabınızın Azure Active Directory bir yönetici rolü olarak atanması gerekir. Yönetici rolleri, **Intune Yöneticisi**, **genel yönetici**ve **Hizmet Yöneticisi**içerir. 

    Daha fazla bilgi için bkz. [Microsoft Intune için destek alma](../get-support.md).

15. Gezinti bölmesinden, kullanılabilir Intune destekli senaryoları göstermek için **sorun giderme + destek** > **Kılavuzlu senaryolar** ' ı seçin. 

    Kılavuzlu senaryo, bir uçtan uca kullanım örneği etrafında ortalanan özelleştirilmiş bir adım serisidir. Yaygın senaryolar, bir yönetici, Kullanıcı veya cihazın kuruluşunuzda oynadığı role dayalıdır. Bu roller genellikle en iyi kullanıcı deneyimini ve güvenliğini sağlamak için dikkatle düzenlenmiş profiller, ayarlar, uygulamalar ve güvenlik denetimleri koleksiyonu gerektirir.

    Belirli bir Intune senaryosunu uygulamak için gereken tüm adımlar ve kaynaklarla ilgili bilgi sahibi değilseniz, Kılavuzlu senaryolar başlangıç noktası olarak kullanılabilir. 

    ![Microsoft Endpoint Manager Yönetim Merkezi-Kılavuzlu senaryoların ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-15.png)

    Kılavuzlu senaryolar hakkında daha fazla bilgi için bkz. [Kılavuzlu senaryolara genel bakış](~/fundamentals/guided-scenarios-overview.md).

## <a name="configure-the-microsoft-endpoint-manager-admin-center"></a>Microsoft Endpoint Manager yönetim merkezini yapılandırma

Azure, portalın görünümünü özelleştirmenize ve yapılandırmanıza olanak tanır.

### <a name="change-the-dashboard"></a>Panoyu değiştirme

Intune kiracınızdaki cihazların ve istemci uygulamalarının genel ayrıntılarını görüntüleyen **Pano** . Panolar, Microsoft Endpoint Manager Yönetim merkezinde odaklanmış ve düzenlenmiş bir görünüm oluşturmanız için bir yol sağlar. Panoları günlük işlemler için hızlı bir şekilde başlatabileceğiniz ve kaynakları izleyebileceğiniz bir çalışma alanı olarak panoları kullanın. Örneğin, projeler, görevler veya Kullanıcı rollerine dayalı özel panolar oluşturun. Microsoft Endpoint Manager Yönetim Merkezi, başlangıç noktası olarak varsayılan bir pano sağlar. Varsayılan panoyu düzenleyebilir, ek panolar oluşturabilir ve özelleştirebilir, diğer kullanıcıların kullanımına sunmak için panoları yayımlayabilir ve paylaşabilirsiniz. 

   ![Microsoft Endpoint Manager Yönetim Merkezi-Pano ekran görüntüsü](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-16.png)

Geçerli panonuzu değiştirmek için **Düzenle**' yi seçin. Varsayılan panonuzu değiştirmek istemiyorsanız **Yeni bir pano** da oluşturabilirsiniz. Yeni bir pano oluşturmak, size **Kutucuk Galerisi** olan boş, özel bir pano sağlar ve burada kutucuk ekleyebilir veya bunları yeniden düzenleyebilirsiniz. Bölmeleri kategoriye veya kaynak türüne göre bulabilirsiniz. Ayrıca, belirli kutucukları arayabilirsiniz. Mevcut özel Panolarınızın birini seçmek için **Panom** ' ı seçin.

### <a name="change-the-portal-settings"></a>Portal ayarlarını değiştirme

Varsayılan görünümü, temayı, kimlik bilgileri zaman aşımı süresini ve dil ve bölge ayarlarını seçerek Microsoft Endpoint Manager yönetim merkezini özelleştirebilirsiniz.

   <img alt="Screenshot of the Microsoft Endpoint Manager admin center - Portal settings" src="./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-17.png" width="250">

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Intune hızlı bir şekilde çalıştırmak için, önce ücretsiz bir Intune hesabı ayarlayarak Intune hızlı başlangıç adımlarını izleyin.

> [!div class="nextstepaction"]
> [Hızlı başlangıç: Microsoft Intune ücretsiz deneyin](free-trial-sign-up.md)
