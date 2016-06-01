---
# required metadata

title: Microsoft Intune’da yönetim hesapları, web siteleri ve izinler | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da yönetim hesapları, web siteleri ve izinler

Microsoft Intune’u ayarlamadan önce bu konuyu ve [Microsoft Intune’u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md) başlığı altında listelenen diğer gereksinimleri gözden geçirin.

Intune’u yönetmek için kullanacaklarınız:
- İki tür yönetici hesabı
- Ek izinleri olan kullanıcı hesapları
- Yöneticilerinize yönetmeleri gereken öğelere erişim vermek için, web tabanlı iki yönetim konsolu/portalı.

Aşağıdaki bölümlerde bu hesaplar ve portallar açıklamaktadır.

## Özel izinleri olan kullanıcı hesapları ve yönetici hesapları

Aşağıdakiler, Intune için kullanacağınız hesaplar ve izinlerdir.

### Kiracı yöneticisi
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Kiracı yöneticilerine, ilgili kullanıcı ve yönetebilecekleri görevler için yönetim kapsamını tanımlayan bir yönetici rolü atanır.<br /><br />Yönetici rolleri farklı Microsoft bulut hizmetleri arasında ortaktır, ancak bazı hizmetler bazı rolleri desteklemeyebilir.<br /><br /> Microsoft Intune aşağıdaki rolleri kullanır:<br /><br />- Genel yönetici<br />- Faturalama yöneticisi<br />- Parola yöneticisi<br />- Hizmet desteği yöneticisi<br />- Kullanıcı yönetimi yöneticisi|Varsayılan olarak, Microsoft Intune aboneliğinizi oluşturmak için kullandığınız hesap genel yönetici rolüne sahip bir kiracı yöneticisidir.<br /></br>  Kiracı yöneticisi olarak [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] hizmetini [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğinizi yönetmek ve kiracı yöneticilerini atamak için kullanırsınız.<br /><br />Birinci hizmet yöneticinizi atamak üzere [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] hizmetine erişmek için genel yönetim rolüne sahip bir kiracı yöneticisi kullanın. En iyi uygulama olarak, günlük yönetim görevleri için bir kiracı yöneticisi kullanmayın. Kiracı yöneticisinin erişim için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansına ihtiyacı yoktur.<br /><br />Kiracı yöneticisi, Microsoft bulut hizmetleri arasında ortak bir kavramıdır. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetine abone olduğunuzda, hizmetiniz bir Microsoft Azure AD kiracısıdır. [Azure AD dizini nedir?](http://technet.microsoft.com/library/jj573650.aspx) konusunun Azure AD kiracısı bölümüne bakın.|


### Hizmet yöneticisi
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Hizmet yöneticilerine aşağıdaki izinlerden biri atanır:<br /><br />**Tam erişim:** Herhangi bir kısıtlama olmadan tüm [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] alanlarına erişim hakkı verir. Ayrıca başka hizmet yöneticileri ekleyebilir ve yönetebilir.<br /><br />**Salt okunur erişim**: Tüm [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] alanlarına okuma izni verir. Salt okunur hizmet yöneticisi verileri değiştiremez, ancak raporları çalıştırabilir.<br /><br />**Yardım Masası - Gruplar Düğümü**: Hizmet yöneticisine, yalnızca yardım masası senaryolarıyla ilişkilendirilmiş bir dizi görevi gerçekleştirmesini sağlayan izinler verir. Bu izin kümesi hakkında bilgi için bkz. [Intune konsol görünümlerini yönetici rollerine göre özelleştirme](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)|Varsayılan olarak, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] bir hizmet yöneticisi atamaz. Bunun yerine, aboneliğinizin birinci hizmet yöneticisini atamak üzere genel yönetici rolüne sahip bir kiracı yöneticisi kullanmanız gerekir. </br></br> Hizmet yöneticisi olarak, gündelik görevleri yönetmek için [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] kullanırsınız.<br /><br />Hizmet yöneticilerini yönetim konsolundan atarsınız. Hizmet yöneticisi, hesabın yönetim konsoluna erişmesi için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı gerektirir.|



### Cihaz kaydı yöneticileri
|İzin düzeyleri|Daha fazla bilgi|
|--------------------------|-------------------------|
|Cihaz kaydı yöneticileri beşten fazla cihazı kaydetmek için ek izne sahip standart kullanıcı hesaplarıdır.|Varsayılan olarak, her bir [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] kullanıcısı en fazla beş cihaz kaydedebilir. Ancak, bir kullanıcı hesabına cihaz kayıt yöneticisi izni vererek söz konusu hesabı şirketin sahip olduğu cihazlardan oluşan büyük gruplar kaydetmek için kullanabilirsiniz. Bunun yapılması, cihazların kullanıcılara geçici olarak atanabildiği veya kullanıcı ile cihaz arasındaki ilişkinin zorunlu olmadığı bilgi noktası modunda hizmet verilebilen durumlarda faydalıdır.|


## Intune için yönetim web siteleri
 Farklı yönetim rolleri, [desteklenen bir web tarayıcısı](supported-web-browsers.md) kullanarak erişebileceğiniz aşağıdaki yönetim web sitelerinden birini kullanmanızı gerektirir.

- [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune yönetici konsolu](https://admin.manage.microsoft.com/)

### [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Kiracı yöneticisi olarak bu portalı**, yöneticiniz izin verdiğinde aşağıdaki görevler de dahil olmak üzere aboneliğinizi yönetmek için kullanın:

- Aboneliğin kullanıcı hesaplarını yönetme ve dizin eşitlemesini şirket içi Active Directory'den yapılandırma.
- Güvenlik grupları olarak anılan kullanıcı gruplarını yönetme.
- Kullanıcılara [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanma lisansları atama.
- Aboneliğiniz ile birlikte kullandığınız etki alanı adını yapılandırma. Etki alanı adı, kullanıcıların oturum açtığı hesabı tanımlar.
- Aboneliğiniz için sahip olduğunuz lisans sayısı veya kullanabileceğiniz bulut depolama alanı miktarı gibi faturalama ve satın alma ayrıntılarını yönetme.
- [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetinin durumunu görüntüleyen bağlantılar bulma.
- Kiracı yöneticisi olarak hesap portalında oturum açarak, hesabınıza Office 365 kullanmak için bir lisans atanmadığında bile aboneliğinizi yönetebilirsiniz.
- Intune lisansına sahip olan ancak yönetici olmayan tüm kullanıcılar bu portalı kullanarak hesap parolalarını sıfırlayabilir ve profillerini düzenleyebilir.
- Office 365 portalına erişmek için hesabınızın oturum açma durumu **İzin Verildi** olmalıdır. Bu durum, aboneliğin lisansına sahip olmaktan farklıdır. Varsayılan olarak, tüm kullanıcı hesapları **İzin Verildi** durumundadır.


### [Microsoft Intune yönetici konsolu](https://admin.manage.microsoft.com/)

**Hizmet yöneticisi olarak günlük işlemlerinizi yönetmek için bu portalı kullanın**, örneğin:

- Bilgisayarlar ve mobil cihazlar için ilkeler ayarlama.
- Yazılım güncelleştirmeleri ve uygulamalar gibi yazılımları karşıya yükleme ve dağıtma.
- Bilgisayarlarda [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection'ı yönetme.
- Cihaz durumunu görüntüleme ve raporları çalıştırma.
- Bu portalda oturum açın. Bu portalda oturum açabilmek için, hizmet yöneticisi izinlerine sahip olmanız veya genel yönetici rolüne sahip bir kiracı yöneticisi olmanız gerekir.


Yalnızca hizmet yöneticisi izinlerine sahip olan veya genel yönetici rolüne sahip bir kiracı yöneticisi olan kullanıcılar bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanma lisansına ve **İzin Verildi** oturum açma durumuna sahip olmalıdır.

[Aboneliğiniz için kullanıcı ekleme](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) ve [aboneliğiniz için lisans atama](start-with-a-paid-subscription-to-microsoft-intune-step-4.md) hakkında daha fazla bilgi edinin.

 ### Ayrıca bkz.
 [Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO2-->


