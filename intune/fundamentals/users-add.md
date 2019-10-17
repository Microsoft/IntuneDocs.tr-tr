---
title: Kullanıcı ekleme ve izinler verme
titleSuffix: Microsoft Intune
description: Şirket içindeki kullanıcıları Azure AD ile eşitleyin ve Intune aboneliğiniz için yönetici izinleri verin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 90066bf55f50819ba77babee1e1d4230bdead613
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504872"
---
# <a name="add-users-and-grant-administrative-permission-to-intune"></a>Kullanıcı ekleme ve Intune'a yönetici izni verme

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Yönetici olarak, kullanıcıları doğrudan ekleyebilir veya şirket içi Active Directory'den eşitleyebilirsiniz. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Ayrıca kullanıcılara *genel yönetici* ve *hizmet yöneticisi* izinleri gibi ek izinler verebilirsiniz.

## <a name="add-users-to-intune"></a>Intune’a kullanıcı ekleme
Intune aboneliğinize [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) veya [Azure portalı](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) aracılığıyla el ile kullanıcı ekleyebilirsiniz. Bir yönetici, Intune lisansları atamak için kullanıcı hesaplarını düzenleyebilir. Microsoft 365 yönetim merkezinden veya Intune Azure portalından lisans atayabilirsiniz. Microsoft 365 yönetim merkezini kullanma konusunda daha fazla bilgi için bkz. [Microsoft 365 yönetim merkezine tek tek veya topluca kullanıcı ekleme](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezinde Intune kullanıcısı ekleme
1. Bir genel yönetici veya kullanıcı yönetimi yönetici hesabıyla [Microsoft 365 yönetim merkezinde](https://admin.microsoft.com) oturum açın.
2. Office 365 menüsünde **Yönetici**’yi seçin.
3. Yönetim merkezinde **Kullanıcı ekle**’yi seçin.

   ![Kullanıcı ekle bölümünün ekran görüntüsü](./media/users-add/office-add-user.png)

4. Kullanıcıya ait şu ayrıntıları belirtin:
   - **Adı**
   - **Soyadı**
   - **Görünen Ad**
   - **Kullanıcı adı** - Hizmete erişmek için kullanılan ve Azure Active Directory’de depolanan kullanıcı asıl adı (UPN)
   - **Konum**
   - **İletişim bilgileri** (isteğe bağlı)
   - **Parola** - Otomatik olarak oluşturun veya kendiniz belirtin

     ![Yeni kullanıcı bölümünün ekran görüntüsü](./media/users-add/office-add-user-details.png)

5. Bir Intune lisansı atayın. **Ürün lisansları**’nda ürün lisansını seçin. Intune’u barındıran bir lisans gereklidir.
6. Yeni kullanıcı oluşturmak için **Ekle**'yi seçin.

### <a name="add-intune-users-in-the-azure-portal"></a>Azure portalında Intune kullanıcıları ekleme
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Kullanıcılar** > **Tüm kullanıcılar**'ı seçin.
3. Yönetim merkezinde **Yeni kullanıcı**’yı seçin.
   ![Yeni Kullanıcı ekle için ekran görüntüsü](./media/users-add/intune-add-user.png)
4. Kullanıcıya ait şu ayrıntıları belirtin:
   - **Ad**
   - **Kullanıcı adı** - Azure Active Directory portalındaki yeni ad ![Ad ve kullanıcı adı ekleme için ekran görüntüsü](./media/users-add/intune-add-user-info.png) Devam etmek için **Tamam**’ı seçin.
5. İsteğe bağlı olarak, aşağıdaki kullanıcı özelliklerini de belirtebilirsiniz:
   - **Profil** - **İş unvanı** ve **Departman** dahil olmak üzere iş bilgileri
   - **Gruplar** - Kullanıcı için eklenecek grupları seçin
   - **Dizin rolü** - Kullanıcıya, Intune hizmet yöneticisi rolü dahil olmak üzere yönetim izinleri verin.

   Yeni kullanıcıyı Intune’a eklemek için **Oluştur**’u seçin.
6. **Profil**’i seçin, daha sonra yeni kullanıcı için bir **Kullanım konumu** seçin. Yeni kullanıcıya bir Intune lisansı atayabilmeniz için kullanım konumu gerekir. Devam etmek için **Kaydet**’i seçin.
    ![Kullanım konumunun ekran görüntüsü](./media/users-add/intune-add-user-loc.png)
7. Bu kullanıcıya bir Intune lisansı atamak için **Lisanslar**’ı, ardından **Ata**’yı seçin. Cihazları kaydetmek veya şirket kaynaklarına erişmek için bir Intune lisansı gerekir. Sırasıyla **Ürünler**, lisans türü, **Seç** ve **Ata**’yı seçin.

## <a name="grant-admin-permissions"></a>Yönetim izinleri verme

Intune aboneliğinize kullanıcı ekledikten sonra, bazı kullanıcılara yönetici izinleri vermenizi öneririz.  Yönetici izinleri vermek için aşağıdaki adımları izleyin:

### <a name="give-admin-permissions-in-office-365"></a>Office 365’te yönetici izinleri verme
1. [Microsoft 365 yönetim merkezinde](https://admin.microsoft.com) bir genel yönetici hesabıyla oturum açın.
2. Office 365 menüsünde **Yönetici**’yi seçin.
3. Yönetim merkezinde **Etkin kullanıcılar**’ı ve ardından yönetici izinleri vereceğiniz kullanıcıyı seçin.

4. **Roller** sütununda **Düzenle**’yi seçin.

    ![Yönetici kullanıcı ekran görüntüsü](./media/users-add/office-assign-roles-open.png)

5. Uygun roller listesinden vereceğiniz yönetici iznini seçin.
![Rol atama ekran görüntüsü](./media/users-add/office-assign-roles.png)
6. **Kaydet**’i seçin.

### <a name="give-admin-permissions-in-the-azure-portal"></a>Azure portalında yönetici izinleri verme
1. [Azure portalında](https://portal.azure.com) bir genel yönetici hesabıyla oturum açın.
2. Azure portalında **Kullanıcı**’yı ve ardından yönetici izinleri vermek istediğiniz kullanıcıyı seçin.
3. **Dizin rolü**’nü ve ardından vereceğiniz izni seçin.
  ![Dizin rolü ekran görüntüsü](./media/users-add/add-intune-directory-role.png)
4. **Kaydet**’i seçin.

### <a name="types-of-administrators"></a>Yönetici türleri

Kullanıcılara bir veya daha fazla yönetici izni atayın. Bu izinler, kullanıcıların yönetim kapsamını ve yönetebilecekleri görevleri tanımlar. Yönetici izinleri, farklı Microsoft bulut hizmetlerinde ortak kullanılır ancak bazı hizmetler bazı izinleri desteklemeyebilir. Azure portalında ve Microsoft 365 yönetim merkezinde Intune tarafından kullanılmayan sınırlı yönetici rolleri listelenir. Intune yönetici izinleri aşağıdaki seçenekleri içerir:

- **Genel yönetici** - (Office 365 ve Intune) Intune’daki tüm yönetim özelliklerine erişir. Varsayılan olarak, Intune 'A kaydolan kişi genel yönetici olur. Genel Yöneticiler, diğer yönetici rollerini atayabilen tek yöneticilerden yalnızca Yöneticiler vardır. Kuruluşunuzda birden fazla genel yönetici olabilir. İş riskinizi azaltmak için, şirketinizde yalnızca birkaç kişinin bu role sahip olmasını öneririz.
- **Parola yöneticisi** - (Office 365 ve Intune) Parolaları sıfırlar, hizmet isteklerini yönetir ve hizmetin sistem durumunu izler. Parola yöneticileri yalnızca kullanıcıların parolalarını sıfırlayabilir.
- **Hizmet yöneticisi** - (Office 365 ve Intune) Microsoft’ta destek istekleri açar ve hizmet panosuyla ileti merkezini görüntüler. Destek biletleri açmak ve okumak dışında “yalnızca görüntüleme” izinlerine sahiptirler.
- **Faturalama yöneticisi** - (Office 365 ve Intune) Satın alma işlemleri yapar, aboneliklerle destek biletlerini yönetir ve hizmetin sistem durumunu izler.
- **Kullanıcı yöneticisi** - (Office 365 ve Intune) Parolaları sıfırlar, hizmetin sistem durumunu izler, kullanıcı hesapları ekleyip siler ve hizmet isteklerini yönetir. Kullanıcı yönetimi yöneticisi bir genel yöneticiyi silemez, başka yönetici rolleri oluşturamaz veya diğer yöneticilerin parolalarını sıfırlayamaz.
- **Intune Hizmet yöneticisi** - **Dizin Rolü** seçenekleriyle yönetici oluşturma izni hariç tüm Intune Genel yönetici izinlerine sahiptir.

Microsoft Intune aboneliğinizi oluşturmak için kullandığınız hesap bir genel yöneticidir. Günlük yönetim görevleri için bir genel yönetici kullanmamanız önerilir. Bir yöneticinin Azure portalında Intune’a erişmek için Intune lisansına ihtiyacı olmasa da, Exchance Hizmet Bağlayıcısını ayarlamak gibi belirli yönetim görevlerini yerine getirmek için bir Intune lisansı gereklidir.

Microsoft 365 yönetim merkezine erişmek için hesabınızın **Oturum açmaya izinli** olması gerekir. Erişime izin vermek için Azure portalındaki **Profil**’in altında **Oturum açmayı engelle**’yi **Hayır** olarak ayarlayın. Bu durum, aboneliğin lisansına sahip olmaktan farklıdır. Varsayılan olarak, tüm kullanıcı hesapları **İzin Verildi** durumundadır. Yönetici izinleri olmayan kullanıcılar Intune parolalarını sıfırlamak için Microsoft 365 yönetim merkezini kullanabilir.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme
Şirket içi Active Directory'nizden Microsoft Azure Active Directory’ye (Azure AD) kullanıcı hesaplarını aktarmak için dizin eşitlemeyi yapılandırabilirsiniz ve bu, Intune kullanıcılarını da içerir. Şirket içi Active Directory hizmetinizi tüm Azure Active Directory tabanlı hizmetlere bağlamak kullanıcı kimliği yönetimini daha kolay hale getirir. Kullanıcılarınız için kimlik doğrulaması deneyimini tanıdık ve kolay hale getirmek isterseniz, çoklu oturum açma özelliklerini de yapılandırabilirsiniz. Aynı [Azure AD kiracısını](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) birden çok hizmete bağlayarak, önceden eşitlediğiniz kullanıcı hesaplarını tüm bulut tabanlı hizmetler için kullanabilirsiniz.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcılarını Azure AD ile eşitleme
Kullanıcı hesaplarınızı Azure AD ile eşitlemek için ihtiyacınız olan tek araç [Azure AD Connect sihirbazıdır](https://www.microsoft.com/download/details.aspx?id=47594). Azure AD Connect sihirbazı, şirket içi kimlik altyapınızı buluta bağlamak için basitleştirilmiş ve kılavuzlu bir deneyim sağlar. Topolojinizi ve ihtiyaçlarınızı (tekli veya çoklu dizinler, parola karma eşitlemesi, doğrudan kimlik doğrulama veya federasyon) seçin. Sihirbaz, bağlantınızı çalışır hale getirmek için gereken tüm bileşenleri dağıtır ve yapılandırır. Bunlara eşitleme hizmetleri, Active Directory Federasyon Hizmetleri (AD FS) ve Azure AD PowerShell modülü de dahildir.

> [!TIP]
> Azure AD Connect daha önce DirSync ve Azure AD Eşitleme olarak yayınlanan işlevselliği kapsar. [Dizin tümleştirmesi](https://technet.microsoft.com/library/jj573653.aspx)hakkında daha fazla bilgi edinin. Bir yerel dizindeki kullanıcı hesaplarını Azure AD’ye nasıl eşitleyeceğinizi öğrenmek için bkz. [Active Directory ve Azure AD arasındaki benzerlikler](https://technet.microsoft.com/library/dn518177.aspx).
