---
title: Hızlı Başlangıç - Microsoft Intune'u ücretsiz deneyin
titlesuffix: ''
description: Bu hızlı başlangıçta ücretsiz bir deneme aboneliği oluşturacak, desteklenen yapılandırmaları ve ağ gereksinimlerini anlayacak ve isterseniz kendi etki alanı adınızı yapılandıracaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 827766d76a66ea7d69ebbd3ba77efe785689e7e2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189189"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Hızlı Başlangıç: Microsoft Intune'u ücretsiz deneyin 

Microsoft Intune, cihaz ve uygulamaları yöneterek iş gücünüzün şirket verilerini korumanıza yardımcı olur. Bu hızlı başlangıçta Intune'u bir test ortamında denemek için ücretsiz bir abonelik oluşturacaksınız.

Intune, Microsoft Azure portalıyla yönetilen güvenli bir bulut tabanlı hizmetten mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sağlar. Intune kullanarak işgücünüzün şirket kaynaklarının (veriler, cihazlar ve uygulamalar) yapılandırmasının, erişiminin ve güncelleştirmesinin şirketinizin uyumluluk ilke ve gereksinimlerini karşılayacak şekilde doğru olmasını sağlayabilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar
Microsoft Intune'u kurmadan önce aşağıdaki gereksinimleri gözden geçirin:

   - [Desteklenen işletim sistemleri ve tarayıcılar](supported-devices-browsers.md) 
   - [Ağ yapılandırma gereksinimleri ve bant genişliği](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz denemesine kaydolma

Intune'u 30 gün boyunca ücretsiz deneyebilirsiniz. Zaten bir iş veya okul hesabınız varsa bu hesapla **oturum açın** ve aboneliklerinize Intune’u ekleyin. Veya bunun yerine kuruluşunuz için Intune kullanmak üzere yeni bir hesaba **kaydolun**.

> [!IMPORTANT]
> Yeni bir hesap için kaydolduktan sonra mevcut bir iş veya okul hesabını birleştirmeniz mümkün olmayacaktır.

1. [Microsoft Intune Deneme](https://go.microsoft.com/fwlink/?linkid=2019088) sayfasına gidin ve formu doldurun.

    ![Microsoft Intune Deneme hesabına kaydolma web sayfasının ekran görüntüsü](./media/account-sign-up-site-full-browser.png)

    BT işlemlerinizin ve kullanıcılarınızın çoğu sizinkinden başka bir bölgedeyse, **Ülke veya bölge** altından bu konumu seçmeniz doğru olur. Azure doğru hizmetleri sunmak için bölgesel bilgilerinizi kullanır. Bu ayar daha sonra değiştirilemez.

2. Şirketinizin adını ve arından **. onmicrosoft.com** dizesini kullanarak bir hesap oluşturun. 

    ![Microsoft Intune Deneme hesabına kaydolma web sayfasının ekran görüntüsü](./media/account-sign-up-site-user-id.png)

    Kuruluşunuzun **.onmicrosoft.com** dizesi olmadan kullanmak istediğiniz kendi özel etki alanı varsa, bunu bu makalenin devamında anlatılan Office 365 Yönetim Portalı’nda değiştirebilirsiniz.

3. Kaydolma işleminin sonunda yeni hesap bilgilerinizi görüntüleyin.

    ![Hesap bilgilerinizin görüntüsü](./media/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Azure portalında oturum açma

1. Yeni bir tarayıcı penceresi açın ve adres çubuğuna **https://portal.azure.com** ifadesini girin. 
2. Oturum açmak için yukarıdaki adımlarda verilen kimlik bilgilerini kullanın.

    ![Azure portalı oturum açma sayfasının görüntüsü](./media/azure-portal-signin.png)

3. Azure portalında Microsoft Intune'u görüntülemek için sayfanın solundaki kenar çubuğundan **Tüm hizmetler**'i seçin.
4. Filtre kutusunda **Microsoft Intune**'u arayıp seçin.
5. Intune'u sık kullandığınız hizmetler listesinin altına eklemek için **yıldız** simgesini seçin ve Intune panosunu açın.

Deneme için kaydolduğunuzda, hesap bilgilerinizi ve kayıt işlemi sırasında verdiğiniz e-posta adresini içeren bir e-posta iletisi de alırsınız. Bu e-posta, denemenizin etkin olduğunu doğrular.

> [!TIP]
> Azure portalıyla çalışırken tarayıcınızda özel mod yerine normal modda çalışırsanız daha iyi sonuçlar elde edebilirsiniz.

## <a name="set-the-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

Azure portalında oturum açıp Intune’u seçtikten sonra henüz bir MDM yetkilisi ayarlamadığınızı gösteren turuncu bir başlık görebilirsiniz. Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetime cihaz kaydetmeleri için bir MDM yetkilisi ayarlanması gerekir.

MDM yetkilisini Intune'a ayarlamak için aşağıdaki adımları izleyin.

1. Yeni bir tarayıcı penceresi açın ve adres çubuğuna **https://portal.azure.com** ifadesini girin. 
2. **Tüm hizmetler** > **Microsoft Intune**'u seçin.
3. Cihaz yönetimini etkinleştirmediğinizi gösteren başlığı veya başlığı göremiyorsanız **Cihaz kaydı**’nı seçin. Cihaz yönetimini henüz etkinleştirmediyseniz **MDM Yetkilisi seçin** dikey penceresi görüntülenir.

    > [!NOTE]
    > Turuncu başlık, ancak henüz MDM yetkilisini ayarlamadıysanız görüntülenir.

    ![MDM Yetkilisi seçin dikey penceresinin görüntüsü](./media/choose-mdm-authority.png) 

4. **MDM Yetkilisi seçin** dikey penceresinin altında MDM yetkilinizi **Intune MDM Yetkilisi** olarak ayarlayın.

MDM yetkilisi hakkında daha fazla bilgi için bkz. [Mobil cihaz yönetimi yetkilisini ayarlama](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Özel etki alanı adınızı yapılandırma (İsteğe bağlı)

Yukarıda değinildiği gibi kuruluşunuzun **. onmicrosoft.com** olmadan kullanmak istediğiniz kendi özel etki alanı varsa, bunu Office 365 Yönetim Portalı'nda değiştirebilirsiniz. Özel etki alanınızın adını kendiniz ekler, doğrular ve yapılandırırsınız.  

> [!IMPORTANT]
> İlk **onmicrosoft.com** etki alanı adını yeniden adlandıramaz ve kaldıramazsınız. İş kimliğinizin açık ve anlaşılır olması adına Intune’da kullanılan özel etki alanı adlarında ekleme, doğrulama veya kaldırma işlemleri yapabilirsiniz.

1. [Office 365 yönetim portalına](https://portal.office.com/Admin/Default.aspx) gidin ve yönetici hesabınızı kullanarak oturum açın.

2. Gezinme bölmesinde, **Kurulum** > **Etki alanları** > **Etki alanı ekle**'yi seçin.

3. Özel etki alanı adınızı yazın. Ardından **İleri**'yi seçin.

   ![Office 365 Yönetim Merkezi’nde Ayarlar > Etki Alanları’nın seçili olduğu ve yeni bir etki alanının eklenmesini gösteren ekran görüntüsü](./media/domain-custom-add.png)

4. Önceki adımda girdiğiniz etki alanının sahibi olduğunuzu doğrulayın. 
    
    **Kodu e-posta yoluyla gönder** seçilirse, etki alanınızın kayıtlı iletişim sorumlusuna bir e-posta gönderilir. E-postayı aldıktan sonra kodu kopyalayın ve **Doğrulama kodunuzu buraya yazın** etiketli alana girin. Doğrulama kodu eşleşirse, etki alanı kiracınıza eklenir. Görüntülenen e-posta tanıdık görünmeyebilir. Bazı kaydediciler etki alanı kaydedilirken sağlanan gerçek e-posta adresini gizler.

   ![Office 365 Yönetim Merkezi'nin eklenen etki alanı adı doğrulanırken ekran görüntüsü](./media/domain-custom-verify.png)

   > [!NOTE]
   > TXT kaydı doğrulama ayrıntıları için bkz. [Office 365 için DNS barındırma sağlayıcılarında DNS kayıtları oluşturma](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Yönetici deneyimi

Kullanabileceğiniz iki portal vardır:
- [Intune'un özelliklerini](what-is-intune.md) Azure’daki ([portal.azure.com](https://portal.azure.com)) Intune panosunda bulabilirsiniz. Normalde, işlerinizi Intune panosunda yaparsınız.
- Kullanıcı eklemek ve yönetmek için Azure Active Directory'yi kullanmıyorsanız, bunları yapabileceğiniz yer Office 365 Yönetim merkezidir ([portal.office.com](https://portal.office.com)). Ayrıca hesabınızın faturalama ve destek gibi diğer yönlerini de yönetebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Intune’u bir test ortamında denemek için ücretsiz bir abonelik oluşturdunuz. Intune’u ayarlama hakkında daha fazla bilgi için bkz. [Intune’u ayarlama](setup-steps.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Kullanıcı oluşturun ve ona bir lisans atayın](quickstart-create-user.md)
