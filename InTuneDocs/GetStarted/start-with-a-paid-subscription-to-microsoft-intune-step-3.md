---
title: "Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme | Microsoft Intune"
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
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory’yi eşitleme ve Intune’a kullanıcı ekleme
Şirket içi Active Directory'nizden Microsoft Azure Active Directory’ye (Azure AD) kullanıcı hesaplarını aktarmak için dizin eşitlemeyi yapılandırabilirsiniz. Şirket içi Active Directory hizmetinizi tüm Azure Active Directory tabanlı hizmetlere bağlamak kullanıcı kimliği yönetimini daha kolay hale getirir. Kullanıcılarınız için kimlik doğrulaması deneyimini tanıdık ve kolay hale getirmek isterseniz, çoklu oturum açma özelliklerini de yapılandırabilirsiniz.

İşleri daha da kolaylaştırmak için, aynı [Azure AD kiracısıyla](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) birden çok hizmet kullandığınızda, daha önce eşitlemiş olduğunuz kullanıcı hesapları aynı Azure AD kiracı aboneliğini paylaşan tüm bulut tabanlı hizmetlerin kullanımına sunulur.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Şirket içi kullanıcılarını Azure AD ile eşitleme
Kullanıcı hesaplarınızı Azure AD ile eşitlemek için ihtiyacınız olan tek araç [Azure AD Connect sihirbazıdır](https://www.microsoft.com/download/details.aspx?id=47594). Azure AD Connect sihirbazı, şirket içi kimlik altyapınızı buluta bağlamak için basitleştirilmiş ve kılavuzlu bir deneyim sağlar.  Topolojinizi ve ihtiyaçlarınızı (tek veya birden çok dizin, parola eşitleme ya da federasyon) seçtiğinizde, sihirbaz bağlantınızı çalışır hale getirmek için gereken tüm bileşenleri dağıtır ve yapılandırır. Bunlara eşitleme hizmetleri, Active Directory Federasyon Hizmetleri (AD FS) ve Azure AD PowerShell modülü de dahildir.

> [!TIP]
> Azure AD Connect, önceden Dirsync ve Azure AD Eşitleme olarak yayımlanan işlevselliği kapsar. [Dizin tümleştirmesi](http://technet.microsoft.com/library/jj573653.aspx) hakkında daha fazla bilgi edinebilirsiniz. Kullanıcı hesaplarını yerel dizininizden Azure AD'ye eşitlemenin avantajlarını öğrenmek için, bkz. [Active Directory ve Azure AD arasındaki benzerlikler](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Yönetici izinleri verme

Intune’u yönetmek için kullanacaklarınız:
- İki tür yönetici hesabı
- Ek izinleri olan kullanıcı hesapları
- Yöneticilerinize yönetmeleri gereken öğelere erişim vermek için, web tabanlı iki yönetim konsolu/portalı.

Intune aboneliğinize kullanıcılar ekledikten sonra, birkaç kullanıcı hesabına yönetici kimlik bilgileri vermenizi öneririz. Yönetici kimlik bilgilerini atamak için kullandığınız konsol atamak istediğiniz yönetici türüne bağlıdır:

-   **Kiracı yöneticisi**: Faturalandırma, bulut depolama ve Intune kullanabilecek kullanıcıları yönetme gibi, aboneliğinizin özelliklerini yönetmesi için bu tür yöneticiyi atamak amacıyla **Microsoft Intune hesap portalını** kullanın.

-   **Hizmet yöneticisi**: Mobil cihaz veya bilgisayar yönetimi, ilke veya yazılım dağıtma ve raporları çalıştırma gibi günlük görevler için bir yönetici atamak için **Microsoft Intune yönetici konsolunu** kullanın.

Aşağıdaki bölümlerde bu hesaplar ve portallar açıklamaktadır.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Özel izinleri olan kullanıcı hesapları ve yönetici hesapları

Aşağıdakiler, Intune için kullanacağınız hesaplar ve izinlerdir.

### <a name="tenant-administrator"></a>Kiracı yöneticisi
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Kiracı yöneticilerine, ilgili kullanıcı ve yönetebilecekleri görevler için yönetim kapsamını tanımlayan bir yönetici rolü atanır.<br /><br />Yönetici rolleri farklı Microsoft bulut hizmetleri arasında ortaktır, ancak bazı hizmetler bazı rolleri desteklemeyebilir.<br /><br /> Microsoft Intune aşağıdaki rolleri kullanır:<br /><br />- Genel yönetici<br />- Faturalama yöneticisi<br />- Parola yöneticisi<br />- Hizmet desteği yöneticisi<br />- Kullanıcı yönetimi yöneticisi|Varsayılan olarak, Microsoft Intune aboneliğinizi oluşturmak için kullandığınız hesap genel yönetici rolüne sahip bir kiracı yöneticisidir.<br /></br>  Kiracı yöneticisi olarak [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] hizmetini Intune aboneliğinizi yönetmek ve [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] kiracı yöneticilerini atamak için kullanırsınız.<br /><br />Birinci hizmet yöneticinizi atamak üzere [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] hizmetine erişmek için genel yönetim rolüne sahip bir kiracı yöneticisi kullanın. En iyi uygulama olarak, günlük yönetim görevleri için bir kiracı yöneticisi kullanmayın. Kiracı yöneticisi [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] hizmetine erişmek için bir Intune lisansı gerektirmez.<br /><br />Kiracı yöneticisi, Microsoft bulut hizmetleri arasında ortak bir kavramıdır. Intune hizmetine abone olduğunuzda, hizmetiniz bir Microsoft Azure AD kiracısıdır. [Azure AD dizini nedir?](http://technet.microsoft.com/library/jj573650.aspx) konusunun Azure AD kiracısı bölümüne bakın.|


### <a name="service-administrator"></a>Hizmet yöneticisi
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Hizmet yöneticilerine aşağıdaki izinlerden biri atanır:<br /><br />**Tam erişim:** Herhangi bir kısıtlama olmadan tüm [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] alanlarına erişim hakkı verir. Ayrıca başka hizmet yöneticileri ekleyebilir ve yönetebilir.<br /><br />**Salt okunur erişim**: Tüm [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] alanlarına okuma izni verir. Salt okunur hizmet yöneticisi verileri değiştiremez, ancak raporları çalıştırabilir.<br /><br />**Yardım Masası - Gruplar Düğümü**: Hizmet yöneticisine, yalnızca yardım masası senaryolarıyla ilişkilendirilmiş bir dizi görevi gerçekleştirmesini sağlayan izinler verir. Bu izin kümesi hakkında bilgi için bkz. [Intune konsol görünümlerini yönetici rollerine göre özelleştirme](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Varsayılan olarak, Intune bir hizmet yöneticisi atamaz. Bunun yerine, aboneliğinizin birinci hizmet yöneticisini atamak üzere genel yönetici rolüne sahip bir kiracı yöneticisi kullanmanız gerekir. </br></br> Hizmet yöneticisi olarak [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] hizmetini Intune için günlük görevleri yönetmek üzere kullanırsınız.<br /><br />Hizmet yöneticilerini yönetim konsolundan atarsınız. Hizmet yöneticisi, hesabın yönetim konsoluna erişmesi için Intune lisansı gerektirir.|



### <a name="device-enrollment-managers"></a>Cihaz kaydı yöneticileri
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Cihaz kaydı yöneticileri beşten fazla cihazı kaydetmek için ek izne sahip standart kullanıcı hesaplarıdır.|Varsayılan olarak, her bir [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] kullanıcısı en fazla beş cihaz kaydedebilir. Ancak, bir kullanıcı hesabına cihaz kayıt yöneticisi izni vererek söz konusu hesabı şirketin sahip olduğu cihazlardan oluşan büyük gruplar kaydetmek için kullanabilirsiniz. Bunun yapılması, cihazların kullanıcılara geçici olarak atanabildiği veya kullanıcı ile cihaz arasındaki ilişkinin zorunlu olmadığı bilgi noktası modunda hizmet verilebilen durumlarda faydalıdır.|




>[!div class="step-by-step"]

>[&larr; **Etki alanı ayarları**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune lisanslarını yönetme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


