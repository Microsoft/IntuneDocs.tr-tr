---
title: "Kullanıcı ekleme ve izinler verme"
description: "Şirket içindeki kullanıcıları Azure AD ile eşitleme ve Intune aboneliğiniz için yönetici izinleri verme"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8ce84f51dcfb61ec16c78a6216135c2a7639657f
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Kullanıcı ekleme ve Intune'a yönetici izni verme

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu konuda, yöneticilerin kullanıcıları Intune’a nasıl ekleyebilecekleri ve Intune hizmetinde ne tür yönetici izinlerinin bulunduğu açıklanır.

Yönetici olarak, kullanıcıları doğrudan ekleyebilir veya şirket içi Active Directory'den eşitleyebilirsiniz. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Ayrıca kullanıcılara *genel yönetici* ve *hizmet yöneticisi* izinleri gibi ek izinler verebilirsiniz.

## <a name="add-users-to-intune"></a>Intune’a kullanıcı ekleme
Intune aboneliğinize [Office 365 portalı](https://www.office.com/signin) veya [Azure portalı](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) aracılığıyla el ile kullanıcı ekleyebilirsiniz. Bir yönetici, Intune lisansları atamak için kullanıcı hesaplarını düzenleyebilir. Office 365 portalından veya Intune Azure portalından lisans atayabilirsiniz. Office 365 portalını kullanma konusunda daha fazla bilgi için bkz. [Office 365 portalına tek tek veya topluca kullanıcı ekleme](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Office 365 Yönetim Merkezi’nde Intune’a kullanıcı ekleme
1. Bir genel yönetici veya kullanıcı yönetimi yönetici hesabıyla [Office 365 portalında](https://www.office.com/signin) oturum açın.
2. Office 365 menüsünde **Yönetici**’yi seçin.
3. Yönetim merkezinde **Kullanıcı ekle**’yi seçin.

  ![Office 365 Yönetim ekran görüntüsü](media/office-add-user.png)

4. Kullanıcıya ait şu ayrıntıları belirtin:
  - **Adı**
  - **Soyadı**
  - **Görünen Ad**
  - **Kullanıcı adı** - Hizmete erişmek için kullanılan ve Azure Active Directory’de depolanan kullanıcı asıl adı (UPN)
  - **Konum**
  - **İletişim bilgileri** (isteğe bağlı)
  - **Parola** - Otomatik olarak oluşturun veya kendiniz belirtin

     ![Office 365 Yönetim ekran görüntüsü](media/office-add-user-details.png)

5. Bir Intune lisansı atayın. **Ürün lisansları**’nda ürün lisansını seçin. Intune’u barındıran bir lisans gereklidir.
6. Yeni kullanıcı oluşturmak için **Ekle**'yi seçin.

### <a name="add-intune-users-in-the-azure-portal"></a>Azure portalında Intune kullanıcıları ekleme
1. [Azure portalında](https://portal.azure.com) oturum açın ve **Diğer hizmetler** > **İzleme + Yönetim** > **Intune**’a gidin. Ayrıca **Intune** için *kaynak araması* da yapabilirsiniz.
2. **Kullanıcılar**’ı seçin.
3. Yönetim merkezinde **Yeni kullanıcı**’yı seçin.
  ![Office 365 Yönetim ekran görüntüsü](media/intune-add-user.png)
4. Kullanıcıya ait şu ayrıntıları belirtin:
  - **Ad**
  - **Kullanıcı adı** - Azure Active Directory portalındaki yeni ad ![Office 365 Yönetim ekran görüntüsü](media/intune-add-user-info.png) Devam etmek için **Tamam**’ı seçin.
5. İsteğe bağlı olarak, aşağıdaki kullanıcı özelliklerini de belirtebilirsiniz:
  - **Profil** - **İş unvanı** ve **Departman** dahil olmak üzere iş bilgileri
  -  **Gruplar** - Kullanıcı için eklenecek grupları seçin
  - **Dizin rolü** - Kullanıcıya, Intune hizmet yöneticisi rolü dahil olmak üzere yönetim izinleri verin.

  Yeni kullanıcıyı Intune’a eklemek için **Oluştur**’u seçin.
6. **Profil**’i seçin, daha sonra yeni kullanıcı için bir **Kullanım konumu** seçin. Yeni kullanıcıya bir Intune lisansı atayabilmeniz için kullanım konumu gerekir. Devam etmek için **Kaydet**’i seçin.
    ![Office 365 Yönetim ekran görüntüsü](media/intune-add-user-loc.png)
7. Bu kullanıcıya bir Intune lisansı atamak için **Lisanslar**’ı, ardından **Ata**’yı seçin. Cihazları kaydetmek veya şirket kaynaklarına erişmek için bir Intune lisansı gerekir. Sırasıyla **Ürünler**, lisans türü, **Seç** ve **Ata**’yı seçin.

## <a name="grant-admin-permissions"></a>Yönetim izinleri verme

Intune aboneliğinize kullanıcı ekledikten sonra, bazı kullanıcılara yönetici izinleri vermenizi öneririz.  Yönetici izinleri vermek için aşağıdaki adımları izleyin:

### <a name="give-admin-permissions-in-office-365"></a>Office 365’te yönetici izinleri verme
1. [Office 365 portalında](https://www.office.com/signin) bir genel yönetici hesabıyla oturum açın.
2. Office 365 menüsünde **Yönetici**’yi seçin.
3. Yönetim merkezinde **Etkin kullanıcılar**’ı ve ardından yönetici izinleri vereceğiniz kullanıcıyı seçin.
4. **Roller** sütununda **Düzenle**’yi seçin.
  ![Office 365 rol atama ekranının görüntüsü](./media/office-assign-roles-open.png)
5. Uygun roller listesinden vereceğiniz yönetici iznini seçin.
![Office 365 portalı Rol atama görüntüsü.](./media/office-assign-roles.png)
6. **Kaydet**’i seçin.

### <a name="give-admin-permissions-in-the-azure-portal"></a>Azure portalında yönetici izinleri verme
1. [Azure portalında](https://www.office.com/signin) bir genel yönetici hesabıyla oturum açın.
2. Azure portalında **Kullanıcı**’yı ve ardından yönetici izinleri vermek istediğiniz kullanıcıyı seçin.
3. **Dizin rolü**’nü ve ardından vereceğiniz izni seçin.
  ![Ekran görüntüsü](./media/add-intune-directory-role.png)
4. **Kaydet**’i seçin.

### <a name="types-of-administrators"></a>Yönetici türleri

Kullanıcılara bir veya daha fazla yönetici izni atayın. Bu izinler, kullanıcıların yönetim kapsamını ve yönetebilecekleri görevleri tanımlar. Yönetici izinleri, farklı Microsoft bulut hizmetlerinde ortak kullanılır ancak bazı hizmetler bazı izinleri desteklemeyebilir. Azure ve Office 365 portallarında Intune tarafından kullanılmayan sınırlı yönetici rolleri listelenir. Intune yönetici izinleri aşağıdaki seçenekleri içerir:

- **Genel yönetici** - (Office 365 ve Intune) Intune’daki tüm yönetim özelliklerine erişir. Varsayılan olarak Intune için kaydolan kişi Genel yönetici olur. Diğer yönetici rollerini yalnızca genel yöneticiler atayabilir. Kuruluşunuzda birden fazla genel yönetici olabilir. İş riskinizi azaltmak için, şirketinizde yalnızca birkaç kişinin bu role sahip olmasını öneririz.
- **Parola yöneticisi** - (Office 365 ve Intune) Parolaları sıfırlar, hizmet isteklerini yönetir ve hizmetin sistem durumunu izler. Parola yöneticileri yalnızca kullanıcıların parolalarını sıfırlayabilir.
- **Hizmet yöneticisi** - (Office 365 ve Intune) Microsoft’ta destek istekleri açar ve hizmet panosuyla ileti merkezini görüntüler. Destek biletleri açmak ve okumak dışında “yalnızca görüntüleme” izinlerine sahiptirler.
- **Faturalama yöneticisi** - (Office 365 ve Intune) Satın alma işlemleri yapar, aboneliklerle destek biletlerini yönetir ve hizmetin sistem durumunu izler.
- **Kullanıcı yöneticisi** - (Office 365 ve Intune) Parolaları sıfırlar, hizmetin sistem durumunu izler, kullanıcı hesapları ekleyip siler ve hizmet isteklerini yönetir. Kullanıcı yönetimi yöneticisi bir genel yöneticiyi silemez, başka yönetici rolleri oluşturamaz veya diğer yöneticilerin parolalarını sıfırlayamaz.
- **Intune Hizmet yöneticisi** - **Dizin Rolü** seçenekleriyle yönetici oluşturma izni hariç tüm Intune Genel yönetici izinlerine sahiptir.

Microsoft Intune aboneliğinizi oluşturmak için kullandığınız hesap bir genel yöneticidir. Günlük yönetim görevleri için bir genel yönetici kullanmamanız önerilir. Bir yöneticinin Azure portalında Intune’a erişmek için Intune lisansına ihtiyacı olmasa da, Exchance Hizmet Bağlayıcısını ayarlamak gibi belirli yönetim görevlerini yerine getirmek için bir Intune lisansı gereklidir. 

Office 365 portalına erişmek için hesabınızın **Oturum açmaya izinli** olması gerekir. Erişime izin vermek için Azure portalındaki **Profil**’in altında **Oturum açmayı engelle**’yi **Hayır** olarak ayarlayın. Bu durum, aboneliğin lisansına sahip olmaktan farklıdır. Varsayılan olarak, tüm kullanıcı hesapları **İzin Verildi** durumundadır. Yönetici izinleri olmayan kullanıcılar Intune parolalarını sıfırlamak için Office 365 portalını kullanabilir.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme
Şirket içi Active Directory'nizden Microsoft Azure Active Directory’ye (Azure AD) kullanıcı hesaplarını aktarmak için dizin eşitlemeyi yapılandırabilirsiniz ve bu, Intune kullanıcılarını da içerir. Şirket içi Active Directory hizmetinizi tüm Azure Active Directory tabanlı hizmetlere bağlamak kullanıcı kimliği yönetimini daha kolay hale getirir. Kullanıcılarınız için kimlik doğrulaması deneyimini tanıdık ve kolay hale getirmek isterseniz, çoklu oturum açma özelliklerini de yapılandırabilirsiniz. Aynı [Azure AD kiracısını](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) birden çok hizmete bağlayarak, önceden eşitlediğiniz kullanıcı hesaplarını tüm bulut tabanlı hizmetler için kullanabilirsiniz.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcılarını Azure AD ile eşitleme
Kullanıcı hesaplarınızı Azure AD ile eşitlemek için ihtiyacınız olan tek araç [Azure AD Connect sihirbazıdır](https://www.microsoft.com/download/details.aspx?id=47594). Azure AD Connect sihirbazı, şirket içi kimlik altyapınızı buluta bağlamak için basitleştirilmiş ve kılavuzlu bir deneyim sağlar.  Topolojinizi ve ihtiyaçlarınızı seçin (tek veya birden çok dizin, parola eşitleme veya federasyon). Sihirbaz, bağlantınızı çalışır hale getirmek için gereken tüm bileşenleri dağıtır ve yapılandırır. Bunlara eşitleme hizmetleri, Active Directory Federasyon Hizmetleri (AD FS) ve Azure AD PowerShell modülü de dahildir.

> [!TIP]
> Azure AD Connect, önceden Dirsync ve Azure AD Eşitleme olarak yayımlanan işlevselliği kapsar. [Dizin tümleştirmesi](http://technet.microsoft.com/library/jj573653.aspx) hakkında daha fazla bilgi edinebilirsiniz. Bir yerel dizindeki kullanıcı hesaplarını Azure AD’ye nasıl eşitleyeceğinizi öğrenmek için bkz. [Active Directory ve Azure AD arasındaki benzerlikler](http://technet.microsoft.com/library/dn518177.aspx).
