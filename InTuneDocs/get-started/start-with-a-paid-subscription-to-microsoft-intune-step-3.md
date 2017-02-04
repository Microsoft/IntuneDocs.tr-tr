---
title: "Kullanıcıları ekleme ve izin verme | Microsoft Docs"
description: "Şirket içindeki kullanıcıları Azure AD ile eşitleme ve Intune aboneliğiniz için yönetici izinleri verme"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: 02b6dd389c94d2b31bd96b2095ae48b685084370


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Kullanıcı ekleme ve Intune'a yönetici izni verme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Yönetici olarak, kullanıcıları doğrudan ekleyebilir veya şirket içi Active Directory'den eşitleyebilirsiniz. Eklendikten sonra, kullanıcılar cihazlarını kaydedebilir ve şirket kaynaklarına erişebilir. Kullanıcılara *kiracı yöneticisi*, *hizmet yöneticisi* ve *cihaz kayıt yöneticisi izinlerini* içeren ek izinler de verebilirsiniz.

Bu konuda aşağıdaki başlıklarla ilgili yardım sağlanır:

- [Intune’a kullanıcı ekleme](#add-users-to-intune)
- Aşağıdakileri içeren [ek Intune izinleri verme](#grant-intune-permissions):
  - [Kiracı yöneticisi](#tenant-administrator)
  - [Hizmet yöneticisi](#service-administrator)
  - [Cihaz kaydı yöneticileri](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Intune’a kullanıcı ekleme
Intune aboneliğinize [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854) aracılığıyla kullanıcıları el ile ekleyebilirsiniz; bu kullanıcılara otomatik olarak Intune lisansı atanmaz. Bunun yerine, daha sonra bir Intune kiracı yöneticisinin kullanıcı hesabını düzenleyerek Office 365 portalından kullanıcıya lisans ataması gerekir. Yönergeler için bkz. [Office 365 portalına kullanıcıları tek tek veya toplu ekleme](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme
Şirket içi Active Directory'nizden Microsoft Azure Active Directory’ye (Azure AD) kullanıcı hesaplarını aktarmak için dizin eşitlemeyi yapılandırabilirsiniz ve bu, Intune kullanıcılarını da içerir. Şirket içi Active Directory hizmetinizi tüm Azure Active Directory tabanlı hizmetlere bağlamak kullanıcı kimliği yönetimini daha kolay hale getirir. Kullanıcılarınız için kimlik doğrulaması deneyimini tanıdık ve kolay hale getirmek isterseniz, çoklu oturum açma özelliklerini de yapılandırabilirsiniz. Aynı [Azure AD kiracısını](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) birden çok hizmete bağlayarak, önceden eşitlediğiniz kullanıcı hesaplarını tüm bulut tabanlı hizmetler için kullanabilirsiniz.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcılarını Azure AD ile eşitleme
Kullanıcı hesaplarınızı Azure AD ile eşitlemek için ihtiyacınız olan tek araç [Azure AD Connect sihirbazıdır](https://www.microsoft.com/download/details.aspx?id=47594). Azure AD Connect sihirbazı, şirket içi kimlik altyapınızı buluta bağlamak için basitleştirilmiş ve kılavuzlu bir deneyim sağlar.  Topolojinizi ve ihtiyaçlarınızı (tek veya birden çok dizin, parola eşitleme ya da federasyon) seçtiğinizde, sihirbaz bağlantınızı çalışır hale getirmek için gereken tüm bileşenleri dağıtır ve yapılandırır. Bunlara eşitleme hizmetleri, Active Directory Federasyon Hizmetleri (AD FS) ve Azure AD PowerShell modülü de dahildir.

> [!TIP]
> Azure AD Connect, önceden Dirsync ve Azure AD Eşitleme olarak yayımlanan işlevselliği kapsar. [Dizin tümleştirmesi](http://technet.microsoft.com/library/jj573653.aspx) hakkında daha fazla bilgi edinebilirsiniz. Kullanıcı hesaplarını yerel dizininizden Azure AD'ye eşitlemenin avantajlarını öğrenmek için, bkz. [Active Directory ve Azure AD arasındaki benzerlikler](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Intune izinleri verme

Intune aboneliğinize kullanıcılar ekledikten sonra, birkaç kullanıcı hesabına yönetici izinleri vermenizi öneririz. Intune’u yönetmek için kullanıcılara üç tür Intune izni verebilirsiniz
-   **Kiracı yöneticisi**: Faturalandırma, bulut depolama ve Intune kullanabilecek kullanıcıları yönetme gibi, aboneliğinizin özelliklerini yönetmesi için bu tür yöneticiyi atamak amacıyla Office 365 portalını kullanın.
-   **Hizmet yöneticisi**: Cihaz veya bilgisayar yönetimi, ilke veya uygulama dağıtma ve raporları çalıştırma gibi günlük görevler için bu türde bir yönetici atamak üzere Microsoft Intune yönetici konsolunu kullanın.
-   **Cihaz kaydı yöneticisi**: Cihaz veya bilgisayar yönetimi, ilke veya uygulama dağıtma ve raporları çalıştırma gibi günlük görevler için bu türde bir yönetici atamak üzere Microsoft Intune yönetici konsolunu kullanın.


### <a name="tenant-administrator"></a>Kiracı yöneticisi


Kiracı yöneticilerine, ilgili kullanıcı ve yönetebilecekleri görevler için yönetim kapsamını tanımlayan bir yönetici rolü atanır. Yönetici rolleri farklı Microsoft bulut hizmetleri arasında ortaktır, ancak bazı hizmetler bazı rolleri desteklemeyebilir. Intune aşağıdaki rolleri kullanır:
- **Genel yönetici** - Intune'daki tüm yönetim özelliklerine erişim sağlar. Varsayılan olarak Intune için kaydolan kişi Genel yönetici olur. Diğer yönetici rollerini yalnızca genel yöneticiler atayabilir. Kuruluşunuzda birden fazla genel yönetici olabilir. İş riskinizi azaltmak için en iyi uygulama olarak şirketinizde yalnızca birkaç kişinin bu role sahip olmasını öneririz.
- **Faturalama yöneticisi** - Satın alma işlemleri yapar, abonelikleri ve destek biletlerini yönetir, hizmetin sistem durumunu izler.
- **Parola yöneticisi** - Parolaları sıfırlar, hizmet isteklerini yönetir ve hizmetin sistem durumunu izler. Parola yöneticileri yalnızca kullanıcıların parolalarını sıfırlayabilir.
- **Hizmet desteği yöneticisi** - Microsoft ile destek istekleri açar ve hizmet panosu ile ileti merkezini görüntüler. Destek biletleri açmak ve okumak dışında “yalnızca görüntüleme” izinlerine sahiptirler.
- **Kullanıcı yönetimi yöneticisi** - Parolaları sıfırlar, hizmetin sistem durumunu izler, kullanıcı hesaplarını ekler ve siler, hizmet isteklerini yönetir. Kullanıcı yönetimi yöneticisi bir genel yöneticiyi silemez, başka yönetici rolleri oluşturamaz veya faturalama, genel ve hizmet yöneticileri için parolaları sıfırlayamaz.

Varsayılan olarak, Microsoft Intune aboneliğinizi oluşturmak için kullandığınız hesap genel yönetici rolüne sahip bir kiracı yöneticisidir. Kiracı yöneticisi rolünde Intune yönetici konsolunu kullanarak Intune aboneliğinizi yönetir ve [Office 365 portalından](http://go.microsoft.com/fwlink/p/?LinkId=698854) kiracı yöneticilerini atarsınız. Birinci hizmet yöneticinizi atamak üzere portala erişmek için genel yönetim rolüne sahip bir kiracı yöneticisi kullanın. En iyi uygulama olarak, günlük yönetim görevleri için bir kiracı yöneticisi kullanmayın. Kiracı yöneticisi Intune yönetici konsoluna erişmek için bir Intune lisansı gerektirmez. Kiracı yöneticisi, Microsoft bulut hizmetleri arasında ortak bir kavramıdır. Intune hizmetine abone olduğunuzda, hizmetiniz bir Azure AD kiracısıdır. Daha fazla bilgi için [Azure AD dizini nedir?](http://technet.microsoft.com/library/jj573650.aspx) konusunun Azure AD kiracısı bölümüne bakın.

Kiracı yöneticisi olarak, yöneticiniz izin verdiğinde [Office 365 portalını](http://go.microsoft.com/fwlink/p/?LinkId=698854) aşağıdaki görevler de dahil olmak üzere aboneliğinizi yönetmek için kullanın:

- Kullanıcı hesaplarını yönetme ve şirket içi Active Directory'den dizin eşitlemesini yapılandırma
- Güvenlik grupları olarak anılan kullanıcı gruplarını yönetme
- Intune için kullanıcı lisansları atama
- Kullanıcılar oturum açtığında kullanılan aboneliğinizin etki alanı adını yapılandırma (örneğin contoso.com)
- Lisanslar ve bulut depolama alanını da içeren faturalama ve satın almayı yönetme
- Intune hizmetinin durumunu görüntüleyen bağlantılar bulma

Office 365 portalına erişmek için hesabınızın oturum açma durumu **İzin Verildi** olmalıdır. Bu durum, aboneliğin lisansına sahip olmaktan farklıdır. Varsayılan olarak, tüm kullanıcı hesapları **İzin Verildi** durumundadır. Yönetici izinleri olmayan kullanıcılar Intune parolalarını sıfırlamak için Office 365 portalını kullanabilir.

### <a name="service-administrator"></a>Hizmet yöneticisi

Varsayılan olarak, Intune bir hizmet yöneticisi atamaz. Bunun yerine, aboneliğinizin birinci hizmet yöneticisini atamak üzere genel yönetici rolüne sahip bir kiracı yöneticisi kullanmanız gerekir. Hizmet yöneticisi olarak [Intune yönetici konsolunu](https://manage.microsoft.com/) Intune için günlük görevleri yönetmek üzere kullanırsınız. Hizmet yöneticilerini yönetim konsolundan atarsınız. Bir hizmet yöneticisi, yönetim konsoluna erişmek için Intune lisansı gerektirir.

Hizmet yöneticilerine aşağıdaki izinlerden biri atanır:
- **Tam erişim**: Intune yönetici konsolunun tüm alanlarına sınırsız erişim, diğer hizmet yöneticilerini ekleme ve yönetme
- **Salt okunur erişim**: Intune yönetici konsolunun tüm alanlarında okuma izni, verilerde değişiklik yapamaz ancak raporları çalıştırabilir
- **Yardım Masası - Gruplar Düğümü**: Hizmet yöneticisinin yalnızca yardım masası senaryolarıyla ilişkili görevleri gerçekleştirmesine olanak tanır; bkz. [Intune konsol görünümlerini yönetici rollerine göre özelleştirme](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Hizmet yöneticisi olarak günlük işlemlerinizi yönetmek için bu portalı kullanın, örneğin:

- Bilgisayar ve mobil cihazlar için ilkeler oluşturma ve yönetme
- Yazılım güncelleştirmelerini ve uygulamaları karşıya yükleme ve dağıtma
- Bilgisayarlarda Endpoint Protection'ı yönetme
- Cihaz durumunu görüntüleme ve raporları çalıştırma

### <a name="device-enrollment-managers"></a>Cihaz kaydı yöneticileri

Cihaz kaydı yöneticileri daha birçok kullanıcısız cihazı kaydetmek için ek izne sahip standart kullanıcı hesaplarıdır. Varsayılan olarak, her bir Intune kullanıcısı en fazla on beş cihaz kaydedebilir. Yönetici olarak, bir kullanıcı hesabına cihaz kaydı yöneticisi izni verebilirsiniz. Bu hesap çok fazla sayıda şirkete ait cihazı kaydedebilir. Bunun yapılması, cihazların kullanıcılara geçici olarak atanabildiği veya kullanıcı ile cihaz arasındaki ilişkinin zorunlu olmadığı bilgi noktası modunda hizmet verilebilen durumlarda faydalıdır. Daha fazla bilgi için bkz. [Cihaz kaydı yöneticisi](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Etki alanı ayarları**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune lisanslarını yönetme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Jan17_HO2-->


