---
title: Microsoft Intune tasarımı oluşturma
titleSuffix: Microsoft Intune
description: Bu makale, Microsoft Intune yalnızca bulut tasarımı ve uygulaması için bir tasarım oluşturmanıza yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 3/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 007c84e3bfeac79d2223ea211cbb9f9c97e80475
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548386"
---
# <a name="create-a-design"></a>Tasarım oluşturma

Intune tasarımınız, [bu kılavuzun diğer bölümlerini](planning-guide.md) tamamlarken topladığınız bilgilere ve aldığınız kararlara dayanır. Şunları bir araya getirmenize yardımcı olur:

- Mevcut ortam

- Intune dağıtım seçenekleri

- Dış bağımlılıklar için kimlik gereksinimleri

- Cihaz platformunda dikkat edilecek noktalar

- Sağlanacak gereksinimler  

Şirket içi altyapı gereksinimleri minimal olsa da, hedeflerinizi, amaçlarınızı ve gereksinimlerinizi karşılayan doğru mobil cihaz yönetimi çözümüne sahip olduğunuzdan emin olmak için bir tasarım planı yine de yararlıdır.

Bu alanların her birini daha ayrıntılı bir şekilde gözden geçirelim. 

## <a name="record-your-current-environment"></a>Geçerli ortamınızı kaydetme
Ayrıca, uygulama ve test aşamaları sırasında tasarım değişiklikleri yaygın olarak gerçekleşir. Bu değişiklikleri ve gerekçelerini, değişiklikler gerçekleştikçe belgelemek için tasarım planınızı kullanın.

Mevcut ortamınız, tasarım kararlarını etkileyebilir ve diğer Intune tasarım kararlarını verdiğinizde mevcut ortam belgelenmeli ve buna başvurulmalıdır. Aşağıda mevcut ortamın nasıl kaydedileceğine ilişkin birkaç örnek verilmiştir:

- **Buluttaki kimlik**

    - DirSync veya Azure Active Directory (Azure AD) Connect kullanıyor musunuz?

    - Ortamınız federe mi?

    - Çok faktörlü kimlik doğrulaması (MFA) etkin mi?

- **E-posta ortamı**

    - Exchange kullanıyor musunuz? Şirket içinde mi, bulutta mı?

    - Exchange’i buluta geçirme projesinin ortasında mısınız?

- **Geçerli mobil cihaz yönetimi (MDM) çözümü**

    - Şu anda diğer MDM çözümlerini kullanıyor musunuz?

    - Şirket ve KCG kullanım örneği senaryoları için hangi MDM çözümlerini kullanıyorsunuz?

    - Hangi özellikleri kullanıyorsunuz (örneğin uygulama cihaz ayarları, Wi-Fi yapılandırmaları)?

    - Hangi cihaz platformları destekleniyor?

    - MDM çözümü hangi gruplar ve kaç kullanıcı tarafından kullanılıyor?

- **Sertifika çözümü**

    - Bir sertifika çözümü uyguladınız mı?

    - Hangi sertifika türlerini kullanıyorsunuz?

- **Sistem yönetimi**

    - PC ve sunucu ortamınızı nasıl yönetiyorsunuz?

    - System Center Configuration Manager’ı kullanıyor musunuz? Bir üçüncü taraf sistem yönetimi platformu kullanıyor musunuz?

- **VPN çözümü**

    - VPN çözümünüz nedir?

    - Hem şirket hem de KCG örneği senaryolarında kullanıyor musunuz?

Geçerli MDM ortamını kaydederken ortamınızı etkileyebilecek tüm projeleri ve planları not aldığınızdan emin olun. Intune tasarımınızı oluştururken mevcut ortamı kaydetme yoluna ilişkin bir örnek aşağıda verilmiştir:

| **Çözüm alanı** | **Mevcut ortam** | **Yorumlar** |
|---|---|---|
| **Kimlik** | Azure AD, Azure AD Connect, şirket dışında değil, MFA yok | Yıl sonundan itibaren MFA’yı etkinleştirme projesi geçerli |                 
| **E-posta ortamı** | Şirket İçi Exchange, Exchange Online | Şu anda Şirket İçi Exchange sürümünden Exchange Online sürümüne geçiriliyor. Posta kutularının % 75’i geçirildi. Kalan %25 Intune Pilot başlamadan önce geçirilecektir. |                
| **SharePoint** | Şirket İçi SharePoint | SharePoint Online sürümüne geçirme planı yok |  
| **Geçerli MDM** | Exchange ActiveSync |  |
| **Sertifika çözümü** | Microsoft Server 2012 R2, AD Sertifika Hizmetleri | Web Sitesi Sunucuları için yalnızca PKI kullanın |
| **Sistem Yönetimi** | System Center Configuration Manager CB 1606 | Intune karma çözümün araştırılması isteniyor |
| **VPN çözümü** | Cisco AnyConnect |  |


Intune tasarım planınızı geliştirmek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

## <a name="choose-an-intune-deployment-option"></a>Bir Intune dağıtım seçeneği belirleyin

Intune iki dağıtım seçeneği sunar: Tek başına ve karma. Tek başına bulut ortamında çalışan Intune hizmetine başvurur, karma, Intune'un System Center Configuration Manager ile ifade eder. Bu kılavuz öncelikle tek başına seçeneğinin kullanılmasına yönelik tasarlanmıştır. [İş gereksinimlerinize hangi seçeneğin uyduğuna karar verin](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

> [!Important]
>Yeni karma MDM müşterisi ekleme seçeneği kullanım dışı bırakılmıştır. Daha fazla bilgi için [Karma Mobil Cihaz Yönetiminden Azure’da Intune’a geçme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) başlıklı blog gönderisine bakın.


## <a name="intune-tenant-location"></a>Intune kiracı konumu

Kuruluşunuz küresel olarak faaliyet gösteriyorsa, hizmete abone olurken kiracınızın nerede duracağını planladığınızdan emin olun. Ülke, bir Intune aboneliğine ilk kez kaydolduğunuzda tanımlanır ve aşağıda listelenen dünya genelindeki bölgelerle eşlenir:

- Kuzey Amerika

- Avrupa, Orta Doğu ve Afrika

- Asya ve Pasifik

>[!IMPORTANT]
> Ülke ve kiracı konumunu sonradan değiştirmek mümkün değildir.

## <a name="external-dependencies"></a>Dış bağımlılıklar

Dış bağımlılıklar Intune'dan ayrı ancak aynı zamanda Intune gereksinimi olan veya Intune ile tümleşebilen hizmet ve ürünlerdir. Herhangi bir dış bağımlılığın gereksinimlerini ve nasıl yapılandırılacağını belirlemek önemlidir. Yaygın dış bağımlılıklara bazı örnekler:

- Kimlik

- Kullanıcı ve cihaz grupları

- Ortak anahtar altyapısı (PKI)

Aşağıda, bu yaygın dış bağımlılıkları daha ayrıntılı bir şekilde inceleyeceğiz.

### <a name="identity"></a>Kimlik

Kuruluşunuzda bulunan ve bir cihazı kaydeden kullanıcılar kimlik aracılığıyla tanımlanır. Intune, kullanıcı kimlik sağlayıcısı olarak Azure Active Directory (Azure AD) gerektirir. Bu hizmeti zaten kullanıyorsanız bulutta varolan kimliğinizi kullanabilirsiniz. Ayrıca Azure AD Connect, şirket içi kullanıcı kimliklerinizi Microsoft bulut hizmetleri ile eşitlemek için önerilen araçtır. Kuruluşunuzda zaten Office 365 kullanılıyorsa, Intune’un aynı Azure AD ortamını kullanması önemlidir.

Aşağıdaki Intune kimlik gereksinimleri hakkında daha fazla bilgi edinin:

- [Kimlik gereksinimleri](https://docs.microsoft.com/azure/active-directory/understand-azure-identity-solutions).

- [Dizin eşitlemesi gereksinimleri](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

- [Çok faktörlü kimlik doğrulaması gereksinimleri](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).

### <a name="user-and-device-groups"></a>Kullanıcı ve cihaz grupları

Kullanıcı ve cihaz grupları, ilkeler, uygulamalar ve profiller de dahil olmak üzere bir dağıtımın hedefini belirler. Hangi kullanıcı ve cihaz gruplarının gerekli olacağını belirlemeniz gerekir.

Tüm grupları şirket içi Active Directory içinde oluşturup, ardından Azure AD ile eşitlemenizi öneririz. Kullanıcı ve cihaz gruplarını planlama hakkında daha fazla bilgi edinin:

- [Kullanıcı ve cihaz gruplarınızı planlayın](users-add.md).

- [Kullanıcı ve cihaz grupları oluşturun](groups-add.md).

### <a name="public-key-infrastructure-pki"></a>Ortak anahtar altyapısı (PKI)
Ortak anahtar altyapısı, bir hizmette güvenli kimlik doğrulaması yapabilmek için cihazlara veya kullanıcılara sertifika sağlar. Intune, Microsoft PKI altyapısını destekler. Sertifika tabanlı kimlik doğrulama gereksinimlerini karşılamak için cihaz ve kullanıcı sertifikaları bir mobil cihaza sağlanabilir. Sertifikaları kullanmadan önce, bunların gerekli olup olmadığını, ağ altyapısının sertifika tabanlı kimlik doğrulamasını destekleyip desteklemediğini ve sertifikaların şu anda mevcut ortamda kullanılıp kullanılmadığını belirlemeniz gerekir.

Sertifikaları VPN, Wi-Fi veya Intune ile e-posta profilleriyle kullanmayı planlıyorsanız sertifika ilkeleri oluşturmaya ve dağıtmaya hazır, desteklenen bir [PKI altyapısına sahip olduğunuzdan](certificates-configure.md) emin olun.

Ayrıca, SCEP sertifikaları sağlanacaksa hangi sunucunun Ağ Cihazı Kayıt Hizmeti (NDES) özelliğini barındıracağını ve iletişimin nasıl olacağını belirlemeniz gerekir.

Daha fazla bilgi:

- [Intune sertifika profillerini yapılandırma](certificates-configure.md)

- [SCEP için sertifika altyapısını yapılandırma](certificates-scep-configure.md)

- [PFX için sertifika altyapısını yapılandırma](certficates-pfx-configure.md)




## <a name="device-platform-considerations"></a>Cihaz platformunda dikkat edilecek noktalar

Cihazlarınızı nasıl doğru bir şekilde yöneteceğinizi anlamak için cihazların şu yönlerini yakından inceleyin.

- Desteklenen cihaz platformları

- Cihazlar

- Cihaz sahipliği

- Toplu kayıt

Bu alanları daha ayrıntılı bir şekilde gözden geçirelim.

### <a name="determine-supported-device-platforms"></a>Desteklenen cihaz platformlarını belirleme

Ortamda hangi cihazların olacağını bilmeniz ve tasarımınızı oluştururken bunların Intune tarafından desteklenip desteklenmediğini doğrulamanız gerekir. Intune; iOS, Android ve Windows platformlarını destekler.

[Intune desteklenen cihazların tam listesi](supported-devices-browsers.md).

### <a name="devices"></a>Cihazlar

Intune, kurumsal verilerin güvenliğini sağlamak ve son kullanıcılara daha fazla konumda çalışma olanağı sunmak için mobil cihazları yönetir. Intune birden çok cihaz platformunu desteklediğinden, kuruluşunuzun tasarımında desteklenecek cihazları, işletim sistemi platformlarını ve sürümlerini belgelemeniz önerilir. Örneğin:

| **Cihaz platformu** | **İşletim Sistemi Sürümleri** |
|:---:|:---:|
| iOS - iPhone | 10.0+ |                
| iOS - iPad | 10.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10 tablet | 10+ |


Cihaz listenizi geliştirmek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
### <a name="device-ownership"></a>Cihaz sahipliği

Intune, hem şirkete ait cihazları hem de kişisel cihazları destekler. Bir cihaz, cihaz kayıt yöneticisi tarafından veya cihaz kayıt programı ile kaydedilmişse şirkete ait olarak kabul edilir. Örneğin bir cihaz Apple Aygıt Kayıt Programı (DEP) aracılığıyla kaydedilmiş, şirkete ait olarak işaretlenmiş ve hedeflenen şirket ilkelerini ve uygulamalarını alan bir cihaz grubuna yerleştirilmiştir.

Başvurmak [3. Bölüm: Kullanım örneği senaryosu gereksinimlerini belirleme](planning-guide-requirements.md) daha fazla bilgi şirket ve KCG kullanım örnekleri.

### <a name="bulk-enrollment"></a>Toplu kayıt

 Platforma bağlı olarak cihazları farklı şekillerde toplu olarak kaydedebilirsiniz. Toplu kayıt gerekli olursa önce [toplu kayıt yöntemini belirleyin](device-enrollment.md) ve tasarımınıza dahil edin.

## <a name="feature-requirements"></a>Özellik gereksinimleri

Bu bölümlerde, kullanım örneği senaryo gereksinimlerinize uygun aşağıdaki özellikleri ve yetenekleri inceleyeceğiz:

- Hüküm ve koşullar ilkeleri

- Yapılandırma ilkeleri

- Kaynak profilleri

- Uygulamalar

- Uyumluluk ilkesi

- Koşullu Erişim

Bu alanların her birini daha ayrıntılı bir şekilde gözden geçirelim.

### <a name="terms-and-conditions-policies"></a>Hüküm ve koşullar ilkeleri

Bir son kullanıcının kayıt öncesi kabul etmesi gereken ilkeleri veya koşulları açıklamak için [hüküm ve koşullar](terms-and-conditions-create.md) kullanabilirsiniz. Intune, kullanıcı gruplarına birden çok hüküm ve koşullar ilkesi ekleme ve dağıtma yeteneğini destekler.

Hüküm ve koşul ilkelerinin gerekli olup olmadığını belirlemeniz gerekir. Gerekliyse kuruluşta bu bilgiyi sağlamaktan kimin sorumlu olacağını belirlemelisiniz. Hüküm ve koşullar ilkesinin nasıl belgeleneceğine ilişkin bir örnek aşağıda verilmiştir.

| **Hüküm ve Koşullar adı** | **Kullanım örneği** | **Hedeflenen grup** |
|:---:|:---:|:---:|
| Kurumsal Hüküm ve Koşullar | Kurumsal | Kurumsal kullanıcılar |                 
| KCG Hüküm ve Koşulları | KCG | KCG kullanıcıları |                


Hüküm ve koşullarınızı kullanıcı gruplarınıza eşlemek için [yukarıdaki tablonun şablonu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

### <a name="configuration-policies"></a>Yapılandırma ilkeleri

Bir cihazdaki güvenlik ayarlarını ve özelliklerini yönetmek için yapılandırma ilkeleri kullanın. Yapılandırma ilkelerinizi tasarlarken, Intune cihazları için gerekli yapılandırmaları belirlemek için kullanım örneği gereksinimleri bölümüne bakın. Ayarları ve nasıl yapılandırılmaları gerektiğini belgeleyin. Ayrıca bunların hangi kullanıcı veya cihaz gruplarına hedefleneceğini belgeleyin.

Platform başına en az bir yapılandırma ilkesi oluşturmanız gerekir. Gerekirse her platform için birden çok yapılandırma ilkesi oluşturabilirsiniz. Aşağıda farklı platformlar ve kullanım örneği senaryoları için dört farklı yapılandırma ilkesi tasarlamaya örnek verilmiştir.

| **İlke adı** | **Cihaz platformu** | **Ayarlar** | **Hedef grup** |   
|:---:|:---:|:---:|:---:|
| Kurumsal - iOS | iOS | PIN gereklidir, uzunluğu: 6, bulut yedeklemeyi kısıtla | Kurumsal Cihazlar |                                                           
| Kurumsal - Android | Android | PIN gereklidir, uzunluğu: 6, bulut yedeklemeyi kısıtla | Kurumsal Cihazlar |                                                           
| KCG – iOS  | iOS | PIN gereklidir, uzunluğu: 4 | KCG cihazlar |
| KCG – Android  | Android | PIN gereklidir, uzunluğu: 4 | KCG cihazlar |


Yapılandırma ilkesi ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

### <a name="profiles"></a>Profiller

Son kullanıcının şirket verilerine bağlanmasına yardımcı olmak için profiller kullanın. Intune birçok profil türünü destekler. Profillerin ne zaman yapılandırılacağını belirlemek için kullanım örneklerine ve gereksinimlerine başvurun. Tüm cihaz profilleri platform türüne göre kategorize edilir ve tasarım belgelerine eklenmelidir.

- Sertifika profilleri

- Wi-Fi profili

- VPN profili

- E-posta profili

Her profil türünü daha ayrıntılı bir şekilde inceleyelim.

#### <a name="certificate-profiles"></a>Sertifika profilleri

Sertifika profilleri Intune’un bir kullanıcı veya cihaza sertifika vermesine olanak tanır. Intune aşağıdakileri destekler:

- Basit Sertifika Kayıt Protokolü (SCEP)

- Güvenilen Kök Sertifika

- PFX sertifikası.

Hangi kullanıcı grubunun sertifikaya ihtiyacı olduğunu, kaç sertifika profili gerekeceğini ve bunların hangi kullanıcı gruplarına dağıtılacağını belgelemeniz önerilir.

>[!NOTE]
> Güvenilen kök sertifikanın SCEP sertifikası için gerekli olduğunu unutmayın ve SCEP sertifikası için hedeflenen tüm kullanıcıların aynı zamanda güvenilen kök sertifika alacağından emin olun. SCEP sertifikaları gerekiyorsa, hangi SCEP sertifika şablonlarına gerek duyduğunuzu tasarlayın ve belgeleyin.

Tasarım sırasında sertifikaları belgelemeye dair bir örnek aşağıda verilmiştir:

| **Tür** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Kök CA | Kurumsal Kök CA | Android, iOS, Windows mobile | Kurumsal, KCG  |                                                           
| SCEP | Kullanıcı Sertifikası | Android, iOS, Windows mobile | Kurumsal, KCG |                                                           


Sertifika profili ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

#### <a name="wi-fi-profile"></a>Wi-Fi profili

Wi-Fi profilleri, bir mobil cihazı otomatik olarak kablosuz ağa bağlamak için kullanılır. Intune, Wi-Fi profillerinin desteklenen tüm platformlara dağıtılmasını destekler. [Intune’un Wi-Fi profillerini nasıl desteklediği](wi-fi-settings-configure.md) hakkında daha fazla bilgi edinin.

Bir Wi-Fi profili için bir tasarım örneği aşağıda verilmiştir:

| **Türü** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Asya Wi-Fi profili | Android | Kurumsal, KCG Asya bölgesi|                                                           
| Wi-Fi | Kuzey Amerika Wi-Fi profili | Android, iOS, Windows 10 Mobile | Kurumsal, KCG Kuzey Amerika bölgesi |                                                           


Wi-Fi profili ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

#### <a name="vpn-profile"></a>VPN profili

VPN profilleri, kullanıcıların ağınıza uzak konumlardan güvenli bir şekilde erişmesini sağlar. Intune, yerel mobil VPN bağlantıları ve üçüncü taraf satıcılarından VPN profillerini destekler. [Intune tarafından desteklenen VPN profilleri ve satıcıları](vpn-settings-configure.md) hakkında daha fazla bilgi edinin.

Bir VPN profili tasarımının belgelenmesine ilişkin bir örnek aşağıda verilmiştir.

| **Türü** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco herhangi bir bağlantı Profili | Android, iOS, Windows 10 Mobile | Kurumsal, KCG Kuzey Amerika ve Almanya|                                                           
| VPN | Pulse Secure | Android | Kurumsal, KCG Asya bölgesi |                                                           


VPN profili ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
#### <a name="email-profile"></a>E-posta profili

E-posta profilleri, bir e-posta istemcisinin bağlantı bilgileriyle ve e-posta yapılandırması ile otomatik olarak ayarlamasına olanak tanır. Intune, bazı cihazlarda e-posta profillerini destekler. [E-posta profilleri ve hangi platformların desteklendiği](email-settings-configure.md) hakkında daha fazla bilgi edinin.

E-posta profillerinin tasarımının belgelenmesine dair bir örnek aşağıda verilmiştir:

| **Türü** | **Profil adı** | **Cihaz platformu** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| E-posta profili | iOS e-posta profili | iOS | Kurumsal – KCG bilgi çalışanı |                                                           
| E-posta profili | Android Knox e-posta profili | Android Knox | KCG |


E-posta profili ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
### <a name="apps"></a>Uygulamalar

Kullanıcılara veya cihazlara uygulamaları çeşitli yollarla sunmak için Intune kullanabilirsiniz. Uygulama türü yazılım yükleme uygulamalarını, genel uygulama mağazası uygulamalarını, dış bağlantıları veya yönetilen iOS uygulamalarını içerir. Tek tek uygulama dağıtımlarına ek olarak, iOS ve Windows için toplu satın alma programları aracılığıyla edinilen toplu satın alınan uygulamaları yönetilebilir ve dağıtılabilirsiniz. Aşağıdakiler hakkında daha fazla bilgi edinin:

- [Sağlayabileceğiniz uygulama türleri](app-management.md)

- [iOS İş için Toplu Satın Alma Programı (VPP)](vpp-apps-ios.md)

- [İş uygulamaları için Microsoft Mağazası](windows-store-for-business.md)

#### <a name="app-type-requirements"></a>Uygulama türü gereksinimleri

Uygulamalar kullanıcılara ve cihazlara dağıtılabildiği için hangi uygulamaların Intune tarafından yönetileceğine karar vermenizi öneririz. Listeyi oluştururken aşağıdaki soruları yanıtlamayı deneyin:

- Uygulamalar bulut hizmetleriyle tümleştirme gerektiriyor mu?

- KCG kullanıcılarına tüm uygulamalar sağlanacak mı?

- Bu uygulamalar için kullanılabilen dağıtım seçenekleri nelerdir?

- Şirketinizin, iş ortaklarına Hizmet olarak yazılım (SaaS) uygulama verilerine erişim sağlaması gerekiyor mu?

- Uygulamalar kullanıcının cihazlarından İnternet erişimini gerektiriyor mu?

- Uygulamalar bir uygulama mağazasında genel olarak kullanılabilir mi ya da özel iş kolu uygulamaları (LOB) mı?


#### <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

Uygulama koruma ilkeleri, uygulamanın kurumsal verileri nasıl yönettiğini tanımlayarak veri kaybını en aza indirir. Intune, mobil uygulama yönetimi ile çalışması için oluşturulan tüm uygulamalarda uygulama koruma ilkelerini destekler. Uygulama koruma ilkesi tasarlarken, belirli bir uygulamada şirket verilerine hangi kısıtlamaları getirmek istediğinizi belirlemeniz gerekir. [Uygulama koruma ilkelerinin](app-protection-policy.md) nasıl çalıştığını gözden geçirmenizi öneririz. Aşağıda mevcut uygulamaların nasıl belgeleneceği ve hangi korumanın gerektiğine ilişkin bir örnek verilmiştir.

| **Uygulama** | **Amaç** | **Platformlar** | **Kullanım örneği** | **Uygulama koruma ilkesi** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook mobile  | Kullanılabilir | iOS | Kurumsal - Yöneticiler | Jailbreak uygulanmış olamaz, dosyaları şifreleyin |                                                         
| Word | Kullanılabilir | iOS, Android - Samsung Knox, Knox harici, Windows 10 mobile | Kurumsal, KCG | Jailbreak uygulanmış olamaz, dosyaları şifreleyin |                                                         


Uygulama koruma ilkesi ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
#### <a name="compliance-policies"></a>Uyumluluk ilkeleri

Uyumluluk ilkeleri, bir cihazın belirli gereksinimlere uygun olup olmadığını belirler. Intune, bir cihazın uyumlu veya uyumsuz olarak kabul edileceğini belirlemek için uyumluluk ilkeleri kullanır. Bundan sonra, şirket kaynaklarına erişimi kısıtlamak veya erişime izin vermek için uyumluluk durumu kullanılabilir. Koşullu erişim gerekiyorsa, tasarlamanızı öneririz bir [cihaz uyumluluk İlkesi](device-compliance.md).

Kaç cihaz uyumluluk ilkesine gerek duyduğunuzu ve hangi kullanıcı gruplarının hedef kullanıcı grupları olduğunu belirlemek için gereksinimlere ve kullanım örneklerine başvurun. Ek olarak, bir cihazın uyumsuz olarak kabul edilmesi için oturum açmadan önce ne kadar süre çevrimdışı kalabileceğine de karar vermeniz gerekir.

Bir uyumluluk ilkesi tasarlamaya ilişkin bir örnek aşağıda verilmiştir:

| **İlke adı** | **Cihaz platformu** | **Ayarlar** | **Hedef grup** |   
|:---:|:---:|:---:|:---:|
| Uyumluluk ilkesi | iOS, Android - Samsung Knox, Knox harici, Windows 10 mobile | PIN - gerekli, jailbreak uygulanmış olamaz | Kurumsal, KCG |


Uyumluluk ilkesi ihtiyaçlarınızı belirlemek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).
#### <a name="conditional-access-policies"></a>Koşullu erişim ilkeleri

Koşullu erişim yalnızca uyumlu cihazların e-posta ve diğer şirket kaynaklarına erişmesine izin vermek için kullanılır. Intune şirket kaynaklarına erişimi denetlemek için Enterprise Mobility + Security (EMS) ile birlikte çalışır. Koşullu erişim gerektirip gerektirmediğini karar verin ve neyin korunması gerekir. [Koşullu Erişim](conditional-access.md) hakkında daha fazla bilgi edinin.

Çevrimiçi erişim için hangi platformlar ve kullanıcı gruplarının koşullu erişim ilkeleri tarafından hedef karar verin. Ayrıca, yükleme veya şirket içi Exchange için Intune bağlayıcısını yapılandırmak gerekli olup olmadığını belirleyin: 

- [Şirket İçi Exchange](exchange-connector-install.md)

Belge koşullu erişim ilkelerine ilişkin bir örnek aşağıda verilmiştir:

| **Hizmet** | **Modern Kimlik Doğrulaması Platformları** | **Temel Kimlik Doğrulaması** | **Kullanım örnekleri** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Intune’un desteklediği platformlarda uyumlu olmayan cihazları engelle | Kurumsal, KCG |
| SharePoint Online | iOS, Android |  | Kurumsal, KCG |

Yapabilecekleriniz [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) , koşullu erişim ilkesi ihtiyaçlarınızı belirlemek için.

## <a name="next-steps"></a>Sonraki adımlar

Sonraki bölümde [Intune uygulama süreci](planning-guide-onboarding.md) hakkında yönergeler sağlanır.
