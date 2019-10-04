---
title: Hızlı Başlangıç-Microsoft Intune ücretsiz olarak deneyin
titleSuffix: ''
description: Bu hızlı başlangıçta ücretsiz bir deneme aboneliği oluşturacak, Desteklenen yapılandırmaların ve ağ gereksinimlerinin anlaşılması ve isteğe bağlı olarak etki alanı adınızı yapılandıracaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f1e19822aaf90761e6429b2e91194eacccf467a
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940499"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Hızlı başlangıç: Microsoft Intune ücretsiz deneyin

Microsoft Intune, cihazları ve uygulamaları yöneterek iş gücünüzün şirket verilerini korumanıza yardımcı olur. Bu hızlı başlangıçta, Intune 'U bir test ortamında denemek için ücretsiz bir abonelik oluşturacaksınız.

Intune, Microsoft Azure portal kullanılarak yönetilen güvenli bir bulut tabanlı hizmetten mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sağlar. Intune 'u kullanarak, iş gücünüzün kurumsal kaynaklarının (veriler, cihazlar ve uygulamalar) doğru yapılandırıldığından, erişildiği ve güncelleştirildiğinden, şirketinizin uyumluluk ilkelerine ve gereksinimlerine karşı emin olmanızı sağlayabilirsiniz.

## <a name="prerequisites"></a>Prerequisites
Microsoft Intune ayarlamadan önce, aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen işletim sistemleri ve tarayıcılar](supported-devices-browsers.md)
- [Ağ yapılandırma gereksinimleri ve bant genişliği](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz deneme sürümü için kaydolun

Intune 'un denemesi 30 gün boyunca ücretsizdir. Zaten bir iş veya okul hesabınız varsa, bu hesapla **oturum açın** ve aboneliğinize Intune ekleyin. Aksi takdirde, kuruluşunuz için Intune 'U kullanmak üzere yeni bir hesap için **kaydolabilirsiniz** .

> [!IMPORTANT]
> Yeni bir hesaba kaydolduktan sonra mevcut bir iş veya okul hesabını birleştiremezsiniz.

1. [Microsoft Intune deneme](https://go.microsoft.com/fwlink/?linkid=2019088) sayfasına gidin ve formu doldurun.

    ![Microsoft Intune deneme hesabı kaydolma Web sayfasının ekran görüntüsü](./media/free-trial-sign-up/account-sign-up-site-full-browser.png)

    BT işlemlerinizin ve kullanıcılarınızın birçoğu sizin için farklı bir yerel ayarda yer alıyorsa, **ülke veya bölge**altında bu yerel ayarı seçmek isteyebilirsiniz. Azure, doğru hizmetleri sağlamak için bölgesel bilgilerinizi kullanır. Bu ayar daha sonra değiştirilemez.

2. Şirket adınızı ve ardından **. onmicrosoft.com**kullanarak bir hesap oluşturun. 

    ![Intune deneme hesabı yeni kimlik bilgileri işleminin ekran görüntüsü](./media/free-trial-sign-up/account-sign-up-site-user-id.png)

    Kuruluşunuzun, **. onmicrosoft.com**olmadan kullanmak istediğiniz kendi özel etki alanı varsa, bu makalede daha sonra açıklanan Microsoft 365 Yönetim Merkezi ' nde bunu değiştirebilirsiniz.

3. Kaydolma işleminin sonunda yeni hesap bilgilerinizi görüntüleyin.

    ![Hesap bilgilerinizin görüntüsü](./media/free-trial-sign-up/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Azure portal oturum açın

1. Yeni bir tarayıcı penceresi açın ve adres çubuğuna **https://portal.azure.com** girin. 
2. Oturum açmak için yukarıdaki adımlarda verilen kimlik bilgilerini kullanın.

    ![Azure portal oturum açma sayfasının görüntüsü](./media/free-trial-sign-up/azure-portal-signin.png)

3. Azure portal Microsoft Intune görüntülemek için sayfanın sol tarafındaki kenar çubuğundan **tüm hizmetler** ' i seçin.
4. Filtre kutusunda **Microsoft Intune** arayın ve seçin.
5. Intune 'U en sevdiğiniz hizmetler listesinin altına eklemek ve Intune panosunu açmak için **yıldızı** seçin.

Bir denemeye kaydolduğunuzda, hesap bilgilerinizi içeren bir e-posta iletisi ve kaydolma işlemi sırasında belirttiğiniz e-posta adresini de alırsınız. Bu e-posta, denemenizin etkin olduğunu onaylar.

> [!TIP]
> Azure portal ile çalışırken, özel mod yerine düzenli modda bir tarayıcıyla çalışan daha iyi sonuçlara sahip olabilirsiniz.

## <a name="set-the-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

Azure portal oturum açtıktan ve Intune ' u seçtikten sonra, MDM yetkilisini henüz belirtmeyeceğinizi belirten turuncu bir başlık görebilirsiniz. Mobil cihaz yönetimi (MDM) yetkilisi ayarı, cihazlarınızı nasıl yöneteceğinizi belirler. Kullanıcıların yönetim için cihazları kaydedebilmesi için MDM yetkilisi ayarlanmalıdır.

MDM yetkilisini Intune olarak ayarlamak için aşağıdaki adımları izleyin.

1. Yeni bir tarayıcı penceresi açın ve adres çubuğuna **https://portal.azure.com** girin. 
2. **Tüm hizmetler** > **Microsoft Intune**seçin.
3. Cihaz yönetimini etkinleştirmemiş olduğunuzu belirten başlığı seçin veya başlığı hemen görmüyorsanız **cihaz kaydı**' nı seçin. Henüz cihaz yönetimini etkinleştirmediyseniz **MDM yetkilisi Seç** dikey penceresi görüntülenir.

    > [!NOTE]
    > MDM yetkilisini ayarladıysanız, **cihaz kaydı** DIKEY penceresinde MDM yetkilisi değerini görürsünüz. Turuncu başlık yalnızca MDM yetkilisini henüz ayarlamadıysanız görüntülenir. 

    ![MDM yetkilisi Seç dikey penceresinin görüntüsü](./media/free-trial-sign-up/choose-mdm-authority.png) 

4. MDM yetkiliniz ayarlanmamışsa, **MDM yetkilisi seçin**altında MDM yetkilinizi **Intune MDM yetkilisi**olarak ayarlayın.

MDM yetkilisi hakkında daha fazla bilgi için bkz. [mobil cihaz yönetim yetkilisini ayarlama](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Özel etki alanı adınızı yapılandırma (Isteğe bağlı)

Yukarıda belirtildiği gibi, kuruluşunuzun, **. onmicrosoft.com**olmadan kullanmak istediğiniz kendi özel etki alanı varsa, Microsoft 365 Yönetim merkezinde bunu değiştirebilirsiniz. Aşağıdaki adımları kullanarak özel etki alanı adınızı ekleyebilir, doğrulayabilirsiniz ve yapılandırabilirsiniz.  

> [!IMPORTANT]
> Etki alanı adının *ilk* **onmicrosoft.com** bölümünü yeniden adlandıramaz veya kaldıramazsınız. Ancak, iş kimliğinizi açık tutmak için Intune ile kullanılan *özel* etki alanı adlarını ekleyebilir, doğrulayabilirsiniz veya kaldırabilirsiniz. Daha fazla bilgi için bkz. [özel bir etki alanı adı yapılandırma](custom-domain-name-configure.md).

1. [Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com) ' ne gidin ve yönetici hesabınızı kullanarak oturum açın.

2. Gezinti bölmesinde  >  etki**alanlarını** **Ayarla** > **etki alanı Ekle**' yi seçin.

3. Özel etki alanı adınızı yazın. Ardından **İleri**' yi seçin.

   ![Yönetim Merkezi Microsoft 365 ekran görüntüsü-etki alanı Ekle](./media/free-trial-sign-up/domain-custom-add.png)

4. Önceki adımda girdiğiniz etki alanının sahibi olduğunuzdan emin olun. 
    
    **Kodu e-postayla gönder** ' i seçtiğinizde, etki alanınız için kayıtlı kişiye bir e-posta gönderilir. E-postayı aldıktan sonra kodu kopyalayın ve **doğrulama kodunuzu buraya yazın**etiketli alana girin. Doğrulama kodu eşleşiyorsa, etki alanı kiracınıza eklenecektir. Görüntülenmekte olan e-posta tanıdık görünmeyebilir. Bazı kayıt şirketlerinde gerçek e-posta adresini gizler. Ayrıca, e-posta adresi farklı olabilir ve bu, etki alanı kaydedildiğinde sağlanmıştı.

   ![Yönetim Merkezi Microsoft 365 ekran görüntüsü-etki alanını doğrula](./media/free-trial-sign-up/domain-custom-verify.png)

   > [!NOTE]
   > TXT kaydı doğrulama ayrıntıları için bkz. [Office 365 için herhangi BIR DNS barındırma SAĞLAYıCıSıNDA DNS kayıtları oluşturma](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Yönetici deneyimleri

Kullanabileceğiniz iki Portal vardır:
- Azure 'daki Intune panosu ([Portal.Azure.com](https://portal.azure.com)), [Intune 'un yeteneklerini](what-is-intune.md)keşfedebileceğiniz yerdir. Normalde, işinizi Intune panosunda gerçekleştirirsiniz.
- Microsoft 365 Yönetim Merkezi ([admin.Microsoft.com](https://admin.microsoft.com)), bu kullanıcı için Azure Active Directory kullanmıyorsanız kullanıcıları ekleyebileceğiniz ve yönetebileceğiniz yerdir. Ayrıca, hesabınızın faturalama ve destek gibi diğer yönlerini de yönetebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta, Intune 'U bir test ortamında denemek için ücretsiz bir abonelik oluşturdunuz. Intune 'u ayarlama hakkında daha fazla bilgi için bkz. [Intune 'U ayarlama](setup-steps.md).

Bu Intune hızlı başlangıç serisini takip etmek için sonraki hızlı başlangıca geçin.

> [!div class="nextstepaction"]
> [Hızlı başlangıç: bir kullanıcı oluşturun ve buna bir lisans atayın](quickstart-create-user.md)
