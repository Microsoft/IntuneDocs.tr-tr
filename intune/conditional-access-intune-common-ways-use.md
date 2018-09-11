---
title: Microsoft Intune ile koşullu erişim
titlesuffix: ''
description: Intune koşullu erişimin cihaz tabanlı ve uygulama tabanlı koşullu erişim için yaygın olarak nasıl kullanıldığını öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 59cba4ead614fe0b5deac535efb9bcb303d5810d
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253619"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Intune ile koşullu erişimi kullanmanın yaygın yolları nelerdir?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune ile kullanılan iki tür koşullu erişim vardır: Cihaz tabanlı koşullu erişim ve uygulama tabanlı koşullu erişim. Kuruluşunuzda koşullu erişim uyumluluğunu sağlamak için ilgili uyumluluk ilkelerini yapılandırmanız gerekir. Koşullu erişim, Exchange şirket içi erişimine izin verme veya erişimi engelleme, ağa erişimi denetleme veya Mobil Threat Defense çözümüyle tümleştirme gibi eylemlerde yaygın olarak kullanılır.

Aşağıdaki bilgiler, Intune mobil *cihaz* uyumluluk özelliklerini ve Intune mobil *uygulama* yönetimi (MAM) özelliklerini nasıl kullanacağınızı anlamanıza yardımcı olur. 

> [!NOTE]
> Koşullu erişim, Azure Active Directory Premium lisansına eklenmiş olan bir Azure Active Directory özelliğidir. Intune, çözüme mobil cihaz uyumluluğu ve mobil uygulama yönetimi ekleyerek bu özelliği geliştirir.

## <a name="device-based-conditional-access"></a>Cihaz tabanlı koşullu erişim

Intune ve Azure Active Directory; e-postaya, Office 365 hizmetlerine, Hizmet Olarak Yazılım (SaaS) uygulamalarına ve [şirket içi uygulamalara](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) erişim izninin yalnızca yönetilen ve uyumlu cihazlara verilmesini sağlamak için birlikte çalışır. Ayrıca, Office 365 hizmetlerine yalnızca etki alanına katılan bilgisayarların veya Intune'a kaydolan mobil cihazların erişebilmesi için, Azure Active Directory'de bir ilke belirleyebilirsiniz.

Intune, cihazların uyumluluk durumunu değerlendiren cihaz uyumluluk ilkesi özellikleri sunar. Uyumluluk durumu, bunu kullanıcı şirket kaynaklarına erişmeye çalıştığında Azure Active Directory'de oluşturulmuş koşullu erişim ilkesini zorlamak için kullanan Azure Active Directory'ye bildirilir.

Exchange Online ve diğer Office 365 ürünleri için cihaz tabanlı koşullu erişim ilkeleri, [Azure portalında](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) yapılandırılır.

-   [Azure Active Directory'de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) hakkında daha fazla bilgi edinin.

-   [Intune cihaz uyumluluğu](device-compliance.md) hakkında daha fazla bilgi edinin.

-   [E-postayı, Office 365'i ve diğer hizmetleri Intune ile koşullu erişim kullanarak koruma](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-for-exchange-on-premises"></a>Şirket içi Exchange için koşullu erişim

Koşullu erişim, cihaz uyumluluk ilkelerine ve kayıt durumuna bağlı olarak **şirket içi Exchange**'e erişim izin vermek veya erişim engellemek için kullanılabilir. Koşullu erişim bir cihaz uyumluluk ilkesiyle birlikte kullandığınızda, yalnızca uyumlu cihazların şirket içi Exchange'e erişmesine izin verilir.

Koşullu erişimdeki gelişmiş ayarları aşağıdaki gibi daha ayrıntılı denetim için yapılandırabilirsiniz:

-   Belirli platformlara izin verme veya bunları engelleme.

-   Intune tarafından yönetilmeyen cihazları hemen engelleme.

Cihaz uyumluluğu ve koşullu erişim ilkeleri uygulandığında, şirket için Exchange'e erişmek için kullanılan tüm cihazların uyumlu olup olmadığı denetlenir.

Cihazlar belirlenen koşullara uymadığında, son kullanıcı cihazı kaydetmeye ve cihazın uyumsuz olmasına neden olan sorunu düzeltmeye yönlendirilir.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Şirket içi Exchange için koşullu erişim nasıl çalışır

Intune Exchange bağlayıcısı; Intune'un Exchange Active Sync (EAS) kayıtlarını alıp bunları Intune cihaz kayıtlarına eşleyebilmesi için Exchange sunucusunda bulunan tüm EAS kayıtlarını çeker. Bu kayıtlar, Intune tarafından kaydedilmiş ve tanınan cihazlardır. Bu işlem, e-posta erişimine izin verir veya erişimi engeller.

EAS kaydı yeni bir kayıtsa ve Intune bu kaydı tanımıyorsa, Intune e-posta erişimini engelleyen bir command-let çalıştırır. Bu süreç hakkında daha fazla ayrıntı aşağıdadır:

![CA akış grafiği olan şirket içi Exchange](./media/ca-intune-common-ways-1.png)

1.  Kullanıcı, Exchange'de kurum içi 2010 SP1 veya sonraki bir sürümü üzerinde barındırılan kurumsal e-postalara erişmeye çalışır.

2.  Cihaz Intune tarafından yönetilmiyorsa, e-postaya erişimi engellenir. Intune, EAS istemcisine engelleme bildirimi gönderir.

3.  EAS engelleme bildirimini alır, cihazı karantinaya alır ve kullanıcıların cihazlarını kaydedebilmesi için bağlantılar içeren durum düzeltme adımlarının bulunduğu karantina e-postasını gönderir.

4.  Cihazın Intune tarafından yönetilmesi için ilk adım olan Çalışma alanına katılma işlemi gerçekleşir.

5.  Cihaz Intune'a kaydedilir.

6.  Intune, EAS kaydını bir cihaz kaydına eşler ve cihaz uyumluluk durumunu kaydeder.

7.  EAS istemci kimliği Azure AD Cihaz Kayıt işlemi tarafından kaydedilir. Bu işlem Intune cihaz kaydı ile EAS istemci kimliği arasında bir ilişki oluşturur.

8.  Azure AD Cihaz Kaydı, cihaz durum bilgilerini kaydeder.

9.  Kullanıcı koşullu erişim ilkelerini karşılıyorsa, Intune, Intune Exchange bağlayıcısı aracılığıyla posta kutusunun eşitlenmesine izin veren bir command-let çalıştırır.

10. Exchange sunucusu, kullanıcının e-postaya erişebilmesi için bildirimi EAS istemcisine gönderir.

#### <a name="whats-the-intune-role"></a>Intune'un rolü nedir?

Intune cihaz durumunu değerlendirir ve yönetir.

#### <a name="whats-the-exchange-server-role"></a>Exchange sunucusunun rolü nedir?

Exchange sunucusu, cihazları karantinaya taşımak için gerekli API'yi ve altyapıyı sağlar.

> [!IMPORTANT]
> Cihazın uyumluluk açısından değerlendirilebilmesi için, cihazı kullanan kullanıcıya atanmış bir uyumluluk profili olması gerektiğini unutmayın. Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

### <a name="conditional-access-based-on-network-access-control"></a>Ağ erişim denetimine bağlı koşullu erişim

Intune; Intune kaydını ve cihaz uyumluluk durumunu temel alan erişim denetimi sağlamak için Cisco ISE, Aruba Clear Pass ve Citrix NetScaler gibi iş ortaklarıyla tümleşme sağlamıştır.

Kullanıcı kurumsal Wi-Fi'ye veya VPN kaynaklarına erişmeye çalışırken, cihazın yönetilen ve Intune cihaz uyumluluk ilkeleriyle uyumlu olup olmadığına bağlı olarak erişime izin verilebilir veya erişim engellenebilir.

-   [Intune ile NAC tümleştirmesi](network-access-control-integrate.md) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-based-on-device-risk"></a>Cihaz riskine bağlı olarak koşullu erişim

Intune; mobil cihazlardaki kötü amaçlı yazılımı, Truva atlarını ve diğer tehditleri algılamak için güvenlik çözümleri sağlayan Mobil Tehdit Savunması satıcılarıyla iş ortaklıkları kurar.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Intune ve Mobil Tehdit Savunması Tümleştirmesi nasıl çalışır

Mobil cihazlar Mobil Tehdit Savunması aracısını yüklediklerinde, aracı, mobil cihazın kendisinde bir tehdit bulunduysa, Intune raporlamaya uyumluluk durumu iletileri gönderebilir.

Intune ve mobil tehdit savunması tümleştirmesi, cihaz riskine bağlı olarak alınan koşullu kararlarında rol oynar.

-   [Intune mobil tehdit savunması](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense) hakkında daha fazla bilgi edinin.

### <a name="conditional-access-for-windows-pcs"></a>Windows Bilgisayarlar için koşullu erişim

Bilgisayarlar için koşullu erişim, mobil cihazlarda bulunanlara benzer yetenekler sağlar. Bilgisayarları Intune ile yönetirken koşullu erişimi hangi biçimlerde kullanabileceğinizden söz edelim.

#### <a name="corporate-owned"></a>Şirkete ait olanlar

-   **Şirket içi AD etki alanına katılanlar:** Bu seçenek kendi bilgisayarlarını zaten AD grup ilkeleri ve/veya System Center Configuration Manager aracılığıyla yönettikleri için makul düzeyde kendinden emin olan kuruluşlar tarafından yaygın olarak kullanılır.

-   **Azure AD etki alanına katılan ve Intune yönetiminde olanlar:** Bu senaryo, tipik olarak cihazların kurumsal ağa ender olarak bağlandıkları Kendi Cihazını Seç (CYOD) ve dolaşım halinde dizüstü bilgisayar senaryolarına yöneliktir. Cihaz Azure AD'ye katılır ve Intune'a kaydolur; bu da şirket içi AD'ye ve etki alanı denetleyicisine olan tüm bağımlılıkları ortadan kaldırır. Bu seçenek, kurumsal kaynaklara erişirken bir koşullu erişim ölçütü olarak kullanılabilir.

-   **AD etki alanına katılmış ve System Center Configuration Manager:** System Center Configuration Manager, güncel dal itibariyle, etki alanına katılmış bir bilgisayar olmanın yanı sıra belirli uyumluluk ölçütlerini değerlendirebilen koşullu erişim yetenekleri sağlar:

    -   Bilgisayar şifrelenmiş mi?

    -   Kötü amaçlı yazılım yüklü mü? Güncel mi?

    -   Cihazın yazılım kilidi kırılmış mı veya kök dizinine erişilmiş mi?

#### <a name="bring-your-own-device-byod"></a>Kendi Cihazını Getir (KCG)

-   **Çalışma alanına katılma ve Intune yönetimi:** Burada kullanıcı kişisel cihazlarına ve kurumsal kaynak ve hizmetlere erişebilir. Koşullu erişim ölçütlerini değerlendirmenin bir başka seçeneği olan cihaz düzeyinde ilkeler almak için, Çalışma alanına katılmayı ve cihazları Intune'a kaydetmeyi kullanabilirsiniz.

## <a name="app-based-conditional-access"></a>Uygulamaya bağlı koşullu erişim

Intune ve Azure Active Directory, kurumsal e-postaya ve diğer Office 365 hizmetlerine yalnızca yönetilen uygulamaların erişmesi için birlikte çalışır.

-   [Intune ile uygulama tabanlı koşullu erişim hakkında](app-based-conditional-access-intune.md) daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

[Azure Active Directory’de koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Intune ile şirket Exchange bağlayıcısı nasıl yüklenir](https://docs.microsoft.com/intune/exchange-connector-install).

[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
