---
title: Koşullu erişim senaryoları
titleSuffix: Microsoft Intune
description: Intune Koşullu erişimin cihaz tabanlı ve uygulama tabanlı koşullu erişim için yaygın olarak nasıl kullanıldığını öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fa4157d82ae63336503a9348851ad75f3b8243f9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729765"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Intune ile koşullu erişim kullanmanın yaygın yolları nelerdir?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]


Intune ile kullanılan iki tür koşullu erişim vardır: Cihaz tabanlı koşullu erişim ve uygulama tabanlı koşullu erişim. Kuruluşunuzda koşullu erişim uyumluluğunu sağlamak için ilgili uyumluluk ilkelerini yapılandırmanız gerekir. Koşullu erişim, Exchange 'e erişime izin verme veya erişimi engelleme, ağa erişimi denetleme veya bir mobil tehdit savunması çözümü ile tümleştirme gibi işlemleri yapmak için yaygın olarak kullanılır.
 
Bu makaledeki bilgiler, Intune mobil *cihaz* uyumluluk özelliklerini ve Intune mobil *uygulama* yönetimi (MAM) yeteneklerini nasıl kullanacağınızı anlamanıza yardımcı olabilir. 

> [!NOTE]
> Koşullu erişim, bir Azure Active Directory Premium lisansıyla birlikte sunulan bir Azure Active Directory özelliğidir. Intune, çözüme mobil cihaz uyumluluğu ve mobil uygulama yönetimi ekleyerek bu özelliği geliştirir. *Intune*’dan erişilen Koşullu Erişim düğümü *Azure AD*’den erişilen düğümle aynıdır.  

## <a name="device-based-conditional-access"></a>Cihaz tabanlı koşullu erişim

Intune ve Azure Active Directory, yalnızca yönetilen ve uyumlu cihazların e-postaya, Office 365 hizmetlerine, hizmet olarak yazılım (SaaS) uygulamalarına ve [Şirket içi uygulamalara](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)erişebileceğine emin olmak için birlikte çalışır. Ayrıca, Azure Active Directory ' de bir ilke, yalnızca Intune 'a kayıtlı olan etki alanına katılmış bilgisayarları veya mobil cihazları etkinleştirmek üzere Office 365 hizmetlerine erişmek için ayarlayabilirsiniz.

Intune, cihazların uyumluluk durumunu değerlendiren cihaz uyumluluk ilkesi özellikleri sunar. Uyumluluk durumu, Kullanıcı şirket kaynaklarına erişmeye çalıştığında Azure Active Directory oluşturulan koşullu erişim ilkesini zorlamak için onu kullanan Azure Active Directory bildirilir.

Exchange Online ve diğer Office 365 ürünlerine yönelik cihaz tabanlı koşullu erişim ilkeleri [Azure Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune)aracılığıyla yapılandırılır.  

- [Azure Active Directory 'de koşullu erişim ile yönetilen cihazlar gerektirme](https://docs.microsoft.com/azure/active-directory/conditional-access/require-managed-devices)hakkında daha fazla bilgi edinin.

- [Intune cihaz uyumluluğu](device-compliance-get-started.md) hakkında daha fazla bilgi edinin.

- [Azure Active Directory 'de koşullu erişim Ile desteklenen tarayıcılar](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#supported-browsers)hakkında daha fazla bilgi edinin.

> [!NOTE]
> Android cihazlarda, SharePoint Online 'a cihaz tabanlı erişimi veya Exchange Online 'a tarayıcı tabanlı erişim 'i etkinleştirdiğinizde, kullanıcılar kayıtlı cihazda **tarayıcı erişimini etkinleştir** seçeneğini şu şekilde etkinleştirmelidir:
> 1. **Şirket Portal uygulamasını** başlatın.
> 2. Üç nokta (...) veya donanım menüsü düğmesinden **Ayarlar** sayfasına gidin.
> 3. **Tarayıcı Erişimi Etkinleştir** düğmesine basın. 
> 4. Chrome tarayıcıda, Office 365 oturumunu kapatın ve Chrome’u yeniden başlatın.

### <a name="conditional-access-based-on-network-access-control"></a>Ağ erişim denetimine bağlı koşullu erişim

Intune, Intune kaydına ve cihaz uyumluluk durumuna göre erişim denetimleri sağlamak için Cisco ıSE, Aruba Clear Pass ve Citrix NetScaler gibi iş ortaklarıyla tümleştirilir.

Kullanıcılar, kullandıkları cihazın Intune cihaz uyumluluk ilkeleriyle yönetilip yönetilmediğine bağlı olarak şirket Wi-Fi veya VPN kaynaklarına erişim izni verebilir veya erişimi reddedilebilir.

- [Intune ile NAC tümleştirmesi](network-access-control-integrate.md) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-based-on-device-risk"></a>Cihaz riskine bağlı olarak koşullu erişim

Intune; mobil cihazlardaki kötü amaçlı yazılımı, Truva atlarını ve diğer tehditleri algılamak için güvenlik çözümleri sağlayan Mobil Tehdit Savunması satıcılarıyla iş ortaklıkları kurar.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Intune ve Mobil Tehdit Savunması Tümleştirmesi nasıl çalışır

Mobil cihazlarda Mobile Threat Defense Aracısı yüklüyse, mobil cihazın kendisinde bir tehdit bulunduğunda Aracı, uyumluluk durumu iletilerini Intune bildirimine geri gönderir.

Intune ve mobil tehdit savunması tümleştirmesi, cihaz riskine bağlı olarak koşullu erişim kararlarında bir faktör oynar.

- [Intune mobil tehdit savunması](mobile-threat-defense.md) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-for-windows-pcs"></a>Windows Bilgisayarlar için koşullu erişim

Bilgisayarlar için koşullu erişim, mobil cihazlarda bulunanlara benzer yetenekler sağlar. Bilgisayarları Intune ile yönetirken koşullu erişimi hangi biçimlerde kullanabileceğinizden söz edelim.

#### <a name="corporate-owned"></a>Şirkete ait olanlar

- **Şirket ıçı ad etki alanına katılmış:** Bu seçenek genellikle bilgisayarlarını zaten AD Grup ilkeleri veya System Center Configuration Manager ile yönetme konusunda makul ölçüde rahat olan kuruluşlar tarafından kullanılır.

- **Azure AD etki alanına katılmış ve Intune yönetimi:** Bu senaryo, bulutu ilk kez yapmak isteyen kuruluşlar içindir (yani, birincil olarak bulut hizmetleri 'ni kullanarak, şirket içi bir altyapının kullanımını azaltmaya yönelik bir hedefle birlikte) veya salt bulut (Şirket içi altyapı olmadan). Azure AD JOIN, karma bir ortamda çalışarak hem buluta hem de şirket içi uygulamalara ve kaynaklara erişimi etkinleştirir. Cihaz Azure AD 'ye katılır ve şirket kaynaklarına erişirken koşullu erişim ölçütü olarak kullanılabilecek Intune 'a kaydedilir.

- **Ad etki alanına katılmış ve System Center Configuration Manager:** Güncel daldan itibaren, System Center Configuration Manager, etki alanına katılmış bir BILGISAYAR olmanın yanı sıra belirli uyumluluk ölçütlerini değerlendirebilecek koşullu erişim özellikleri sağlar:

  - Bilgisayar şifrelenmiş mi?

  - Kötü amaçlı yazılımdan koruma yüklendi mi? Güncel mi?

  - Cihazın yazılım kilidi kırılmış mı veya kök dizinine erişilmiş mi?

#### <a name="bring-your-own-device-byod"></a>Kendi cihazını getir (KCG)

- **Çalışma alanına katılma ve Intune yönetimi:** Burada kullanıcı kişisel cihazlarına ve kurumsal kaynak ve hizmetlere erişebilir. Koşullu erişim ölçütlerini değerlendirmek için başka bir seçenek olan cihaz düzeyinde ilkeler almak üzere çalışma alanına katılma ve cihazları Intune MDM 'ye kaydetme kullanabilirsiniz.

[Azure Active Directory 'de cihaz yönetimi](https://docs.microsoft.com/azure/active-directory/devices/overview)hakkında daha fazla bilgi edinin.

## <a name="app-based-conditional-access"></a>Uygulamaya bağlı koşullu erişim

Intune ve Azure Active Directory, kurumsal e-postaya ve diğer Office 365 hizmetlerine yalnızca yönetilen uygulamaların erişmesi için birlikte çalışır.

- [Intune ile uygulama tabanlı koşullu erişim hakkında](app-based-conditional-access-intune.md) daha fazla bilgi edinin.

### <a name="intune-conditional-access-for-exchange-on-premises"></a>Şirket içi Exchange için Intune koşullu erişimi

Koşullu erişim, cihaz uyumluluk ilkelerine ve kayıt durumuna bağlı olarak **şirket içi Exchange**'e erişim izin vermek veya erişim engellemek için kullanılabilir. Koşullu erişim bir cihaz uyumluluk ilkesiyle birlikte kullandığınızda, yalnızca uyumlu cihazların şirket içi Exchange'e erişmesine izin verilir.

Koşullu erişimdeki gelişmiş ayarları aşağıdaki gibi daha ayrıntılı denetim için yapılandırabilirsiniz:

- Belirli platformlara izin verme veya bunları engelleme.

- Intune tarafından yönetilmeyen cihazları hemen engelleyin.

Cihaz uyumluluğu ve koşullu erişim ilkeleri uygulandığında, şirket için Exchange'e erişmek için kullanılan tüm cihazların uyumlu olup olmadığı denetlenir.

Cihazlar koşullar kümesini karşılamıyorsa, Son Kullanıcı cihazı kaydetme işlemi boyunca aygıtı uyumsuz hale getiren sorunu düzeltir.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Şirket içi Exchange için koşullu erişim nasıl çalışır

Şirket içi Exchange için koşullu erişim, Azure koşullu erişim tabanlı ilkelerden farklı şekilde çalışır. Exchange Server 'a doğrudan etkileşimde bulunmak için Intune Exchange şirket içi bağlayıcısını yüklersiniz. Intune Exchange bağlayıcısı; Intune'un Exchange Active Sync (EAS) kayıtlarını alıp bunları Intune cihaz kayıtlarına eşleyebilmesi için Exchange sunucusunda bulunan tüm EAS kayıtlarını çeker. Bu kayıtlar, Intune tarafından kaydedilmiş ve tanınan cihazlardır. Bu işlem, e-posta erişimine izin verir veya erişimi engeller.

EAS kaydı yenidir ve Intune bunun farkında olmazsa, Intune, Exchange Server 'ı e-postaya erişimi engelleyecek şekilde yönlendiren bir cmdlet ("Command-Let") yayınlar. Bu işlemin nasıl çalıştığı hakkında daha fazla ayrıntı aşağıda verilmiştir:

![CA akış grafiği olan şirket içi Exchange](./media/conditional-access-intune-common-ways-use/ca-intune-common-ways-1.png)

1. Kullanıcı, Exchange'de kurum içi 2010 SP1 veya sonraki bir sürümü üzerinde barındırılan kurumsal e-postalara erişmeye çalışır.

2. Cihaz Intune tarafından yönetilmiyorsa, e-postaya erişim engellenir. Intune, EAS istemcisine bir blok bildirimi gönderir.

3. EAS blok bildirimini alır, cihazı karantinaya alır ve kullanıcıların cihazlarını kaydedebilmesi için bağlantılar içeren düzeltme adımlarını içeren karantina e-postasını gönderir.

4. Cihazın Intune tarafından yönetilmesi için ilk adım olan Çalışma alanına katılma işlemi gerçekleşir.

5. Cihaz Intune'a kaydedilir.

6. Intune, EAS kaydını bir cihaz kaydına eşler ve cihaz uyumluluk durumunu kaydeder.

7. EAS istemci kimliği Azure AD Cihaz Kayıt işlemi tarafından kaydedilir. Bu işlem Intune cihaz kaydı ile EAS istemci kimliği arasında bir ilişki oluşturur.

8. Azure AD Cihaz Kaydı, cihaz durum bilgilerini kaydeder.

9. Kullanıcı koşullu erişim ilkelerini karşılıyorsa, Intune, Intune Exchange Bağlayıcısı aracılığıyla posta kutusunun eşitlenmesine izin veren bir cmdlet 'i yayınlar.

10. Exchange sunucusu, kullanıcının e-postaya erişebilmesi için bildirimi EAS istemcisine gönderir.


#### <a name="whats-the-intune-role"></a>Intune'un rolü nedir?

Intune cihaz durumunu değerlendirir ve yönetir.

#### <a name="whats-the-exchange-server-role"></a>Exchange sunucusunun rolü nedir?

Exchange Server, cihazları karantinaya almak için API ve altyapı sağlar.

> [!IMPORTANT]
> Cihazın uyumluluk açısından değerlendirilebilmesi için, cihazı kullanan kullanıcıya bir uyumluluk profili ve Intune lisansı atanmış olması gerektiğini aklınızda bulundurun. Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

## <a name="next-steps"></a>Sonraki adımlar

[Azure Active Directory 'de koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Uygulama tabanlı koşullu erişim ilkeleri ayarlama](app-based-conditional-access-intune-create.md)

[Intune ile şirket Exchange bağlayıcısı nasıl yüklenir](exchange-connector-install.md).

[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
