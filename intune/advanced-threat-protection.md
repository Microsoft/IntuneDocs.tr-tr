---
title: Microsoft Intune-Azure 'da Microsoft Defender ATP 'yi kullanma | Microsoft Docs
description: Intune ve Microsoft Defender Güvenlik Merkezi 'nde Microsoft Defender ATP 'yi açma, Microsoft Defender ATP kullanarak cihazları ekleme dahil olmak üzere uçtan uca bir senaryoda Microsoft Defender Gelişmiş tehdit koruması 'nı (Microsoft Defender ATP) Etkinleştirme makalesine bakın. yapılandırma profili, bir Intune cihaz uyumluluk ilkesi oluşturun, bir Azure AD koşullu erişim ilkesi oluşturun ve cihaz uyumluluğunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af27a9b07434346a5425d0539759cb90ebf1ee6f
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427081"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Intune 'da koşullu erişimle Microsoft Defender ATP için uyumluluğu zorlama  

Microsoft Defender Gelişmiş tehdit koruması (Microsoft Defender ATP) ve Microsoft Intune, güvenlik ihlallerini önlemeye yardımcı olmak ve bir kuruluştaki ihlal etkilerini kısıtlamak için birlikte çalışır.

Bu özellik şu platformlarda geçerlidir: Windows 10 cihazlar

Örneğin biri, kuruluşunuzdaki bir kullanıcıya kötü amaçlı kod içeren bir Word eki gönderir. Kullanıcı eki açar ve içeriği etkinleştirir. Bir yükseltilmiş ayrıcalık saldırısı başlar ve uzak makinedeki saldırgan, kurbanın cihazında yönetici haklarına sahip olur. Daha sonra saldırgan, kullanıcının diğer cihazlarına uzaktan erişir.

Bu güvenlik ihlali tüm kuruluşu etkileyebilir.

Microsoft Defender ATP, bu senaryo gibi güvenlik olaylarını çözümleyebilir. Microsoft Defender Güvenlik Merkezi, cihazları "yüksek riskli" olarak raporlar ve şüpheli etkinlik hakkında ayrıntılı bir rapor içerir. Örneğimizde, Microsoft Defender ATP cihazın anormal kod yürütüldüğünü, bir işlem ayrıcalık yükseltme yükseltmesi, eklenen kötü amaçlı kod ve şüpheli bir uzak kabuk vermiş olduğunu algılar. Microsoft Defender ATP daha sonra tehdidi hafifletmek için size seçenekler sağlar.

Intune kullanarak kabul edilebilir risk düzeyi belirleyen bir uyumluluk ilkesi oluşturabilirsiniz. Bir cihaz bu riski aştığında uyumsuz hale gelir. Azure Active Directory (AD) Koşullu Erişim ile birlikte kullanıldığında, kullanıcının şirket kaynaklarına erişimi engellenir.

Bu makale, şunları nasıl yapacağınızı gösterir:

- Intune 'u Microsoft Defender Güvenlik Merkezi 'nde etkinleştirin ve Intune 'da Microsoft Defender ATP 'yi etkinleştirin. Bu görevler, Intune ile Microsoft Defender ATP arasında bir hizmetten hizmete bağlantı oluşturur. Bu bağlantı, Microsoft Defender ATP 'nin Intune cihazlarınız için makine riskini yazmasını sağlar.
- Intune’da uyumluluk ilkesi oluşturma.
- Cihazlarda tehdit düzeylerine göre Azure Active Directory (AD) koşullu erişimi etkinleştirin.

## <a name="prerequisites"></a>Önkoşullar

Microsoft Defender ATP 'yi Intune ile birlikte kullanmak için, aşağıdakilerin yapılandırıldığından ve kullanıma hazırlandığınızdan emin olun:

- Enterprise Mobility + Security E3 ve Windows E5 (veya Microsoft 365 Kurumsal E5) için lisanslı kiracı
- Azure AD’ye katılmış [Intune tarafından yönetilen](windows-enroll.md) Windows 10 cihazların olduğu Microsoft Intune ortamı
- Microsoft [Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ve Microsoft Defender güvenlik MERKEZI (ATP portalı) erişimi

## <a name="enable-microsoft-defender-atp-in-intune"></a>Intune 'da Microsoft Defender ATP 'yi etkinleştirme

Yeni bir uygulamayı Intune mobil tehdit savunması ile tümleştirdiğinizde ve bağlantıyı etkinleştirdiğinizde, Intune Azure Active Directory içinde klasik bir koşullu erişim ilkesi oluşturur. Her MTD uygulaması, [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri gibi, yeni bir klasik koşullu erişim ilkesi oluşturur.  Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinmemelidir veya devre dışı bırakılmalıdır.

MTD uygulamaları için klasik koşullu erişim ilkeleri: 

- , Cihazların bir cihaz KIMLIĞI olması için Azure AD 'ye kaydolmasını gerektirmek üzere Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.  
- , MTD 'leri yönetmeye yardımcı olmak için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır.
- Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.  

Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilkeleri**' ne gidin.

### <a name="to-enable-defender-atp"></a>Defender ATP 'yi etkinleştirmek için
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu** > **Microsoft Defender ATP**' yi seçin ve ardından *bağlayıcı ayarları*altında **Microsoft Defender Güvenlik Merkezi 'ni aç**' ı seçin.

    ![Microsoft Defender Güvenlik Merkezi 'ni açmak için seçin](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. **Microsoft Defender Güvenlik Merkezi**'nde:
    1. **Ayarlar** > **Gelişmiş özellikler**’i seçin.
    2. **Microsoft Intune bağlantısı** için **Açık** seçeneğini belirleyin:

        ![Intune bağlantısını etkinleştirme](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. **Tercihleri kaydet**’i seçin.

4. Intune, **cihaz uyumluluğu** > **Microsoft Defender ATP**'ye geri dönün. **Windows cihazları sürüm 10.0.15063 ve üstünü Microsoft Defender ATP** 'yi **Açık**olarak ayarlayın.
5. **Kaydet**’i seçin.

Bu görevi genellikle bir kez yaparsınız. Bu nedenle, Intune kaynağında Microsoft Defender ATP zaten etkinse, bunu tekrar yapmanız gerekmez.

## <a name="onboard-devices-using-a-configuration-profile"></a>Bir yapılandırma profili kullanarak cihaz ekleme

Son kullanıcılar Intune’a kaydolduğunda bir yapılandırma profili kullanarak cihazlara farklı ayarlar gönderebilirsiniz. Bu, Microsoft Defender ATP için de geçerlidir.

Microsoft Defender ATP, [Microsoft Defender ATP hizmetleriyle](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) , dosyaları taramak, tehditleri algılamak ve riski MICROSOFT Defender ATP 'ye bildirmek için iletişim kuran bir ekleme yapılandırma paketi içerir.

Eklediğinizde, Intune Microsoft Defender ATP 'den otomatik olarak oluşturulan bir yapılandırma paketini alır. Intune, yapılandırma profilini cihaza gönderdiğinde yapılandırma paketini cihaza gönderir. Bu, Microsoft Defender ATP 'nin cihazı tehditler için izlemesine olanak sağlar.

Yapılandırma paketini kullanarak bir cihaz ekledikten sonra bunu tekrar yapmanız gerekmez. [Bir grup ilkesi veya System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) kullanarak da cihaz ekleyebilirsiniz.

### <a name="create-the-configuration-profile"></a>Yapılandırma profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzeri**’ni seçin
5. **Profil türü**Için **Microsoft Defender ATP (Windows 10 Masaüstü)** öğesini seçin.
6. Şu ayarları yapılandırın:

    - **Microsoft Defender ATP istemci yapılandırma paketi türü**: Yapılandırma  paketini Profile eklemek için Ekle ' yi seçin. Yapılandırma paketini profilden çıkarmak için **Çıkar**’ı seçin.
  
    > [!NOTE]  
    > Microsoft Defender ATP ile düzgün bir şekilde bağlantı oluşturduysanız, Intune otomatik olarak yapılandırma profilini  , **Microsoft Defender ATP istemci yapılandırma paketi türü** ayarını de kullanıma sunulacaktır.
  
    - **Tüm dosyalar Için örnek paylaşımı**: **Etkinleştir** ayarı, örneklerin toplanmasına ve MICROSOFT Defender ATP ile paylaşılmasına olanak tanır. Örneğin, şüpheli bir dosya görürseniz, ayrıntılı analiz için Microsoft Defender ATP 'ye gönderebilirsiniz. **Yapılandırılmadı** , MICROSOFT Defender ATP 'ye herhangi bir örnek paylaşmaz.
    - **Telemetri raporlama sıklığını**hızlandırın: Yüksek riskli cihazlarda, bu ayarı **etkinleştirin** ve bu ayarı, MICROSOFT Defender ATP hizmetine daha sık telemetri rapor eder.

    [System Center Configuration Manager kullanarak Windows 10 makineler](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) eklemek, bu MICROSOFT Defender ATP ayarları hakkında daha fazla bilgi içerir.

7. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin, böylece profil oluşturulur.

## <a name="create-the-compliance-policy"></a>Uyumluluk ilkesini oluşturma
Uyumluluk ilkesi, cihazda kabul edilebilir bir risk düzeyi belirler.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzerini** seçin.
5. **Microsoft Defender ATP** ayarları ' nda, **cihazın makine risk puanı altında veya altında olmasını gerektir** ayarını tercih ettiğiniz düzeye ayarlayın. Tehdit düzeyi sınıflandırmaları, [Microsoft Defender ATP tarafından belirlenir](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Temizle**: Bu düzey en güvenli seçenektir. Cihazda mevcut tehditler bulunamaz ve şirket kaynaklarına erişmeye devam edin. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir. (Microsoft Defender ATP kullanıcıları değeri *güvenlidir*.)
   - **Düşük**: Yalnızca düşük düzeydeki tehditler mevcutsa cihaz uyumludur. Orta veya yüksek tehdit düzeylerine sahip cihazlar uyumlu değildir.
   - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
   - **Yüksek**: Bu düzey en az güvenlidir ve tüm tehdit düzeylerine izin verir. Yüksek, orta veya düşük tehdit düzeylerine sahip cihazlar uyumlu kabul edilir.

6. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).

## <a name="assign-the-policy"></a>İlke atama

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluk** > **ilkeleri**' ni seçin > Microsoft Defender ATP uyumluluk ilkenizi seçin.
3. **Atamalar**’ı seçin.
4. Azure AD gruplarınıza ilkeyi atamak için grupları dahil edin veya hariç tutun.
5. İlkeyi gruplara dağıtmak için **Kaydet**’i seçin. İlkenin hedeflediği kullanıcı cihazlarında uyumluluk denetlenir.

## <a name="create-a-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma
Cihaz uyumsuzsa, koşullu erişim ilkesi kaynaklara  erişimi engeller. Yani bir cihaz, tehdit düzeyini aşarsa SharePoint veya Exchange Online gibi şirket kaynaklarına erişimi engelleyebilirsiniz.  

> [!TIP]  
> Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. *Intune*’dan erişilen Koşullu Erişim düğümü *Azure AD*’den erişilen düğümle aynıdır.  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **koşullu erişim** > **Yeni ilke**' yi seçin.
2. İlke için bir **Ad** girin ve **Kullanıcılar ve gruplar**’ı seçin. İlke için grupları eklemek üzere Dahil Et veya Hariç Tut seçeneklerini kullanın ve **Bitti**’yi seçin.
3. **Bulut uygulamaları**’nı ve ardından hangi uygulamaların korunacağını seçin. Örneğin **Uygulama seçin**’e tıklayın, **Office 365 SharePoint Online** ve **Office 365 Exchange Online**’ı seçin.

    Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

4. **Koşullar** > **İstemci uygulamaları**’nı seçerek ilkeyi uygulamalara ve tarayıcılara uygulayın. Örneğin **Evet**’i seçin ve ardından **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i etkinleştirin.

    Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

5. Cihaz uyumluluğuna göre koşullu erişim uygulamak için **Izin ver** ' i seçin. Örneğin **Erişim ver** > **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin.

    Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.

6. **İlkeyi etkinleştir**’i ve **Oluştur**’u seçerek değişikliklerinizi kaydedin.

[Koşullu erişim nedir?](conditional-access.md) iyi bir kaynaktır.

## <a name="monitor-device-compliance"></a>Cihaz uyumluluğunu izleme
Ardından, Microsoft Defender ATP Uyumluluk ilkesine sahip cihazların durumunu izleyin.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu** > **İlke uyumluluğu**’nu seçin.
3. Listede Microsoft Defender ATP ilkenizi bulun ve hangi cihazların uyumlu veya uyumsuz olduğunu görün.

## <a name="more-good-stuff"></a>Daha fazla iyi hizmet
[Microsoft Defender ATP koşullu erişimi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)  
[Microsoft Defender ATP risk panosu](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  

[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)  
[Azure AD 'de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)