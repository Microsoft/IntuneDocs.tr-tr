---
title: Microsoft Intune-Azure 'da Microsoft Defender ATP 'yi kullanma | Microsoft Docs
description: Intune ve Microsoft Defender Güvenlik Merkezi 'nde Microsoft Defender ATP 'yi açma, Microsoft Defender ATP kullanarak cihazları ekleme dahil olmak üzere uçtan uca bir senaryoda Microsoft Defender Gelişmiş tehdit koruması 'nı (Microsoft Defender ATP) Etkinleştirme makalesine bakın. yapılandırma profili, bir Intune cihaz uyumluluk ilkesi oluşturun, bir Azure AD koşullu erişim ilkesi oluşturun ve cihaz uyumluluğunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ebde15eb39a61bbbafbe40020d90d9bebdce8cf
ms.sourcegitcommit: 7273100afc51fd808558dc05c651358145d4fa6b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68533170"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Intune 'da koşullu erişimle Microsoft Defender ATP için uyumluluğu zorlama  

Microsoft Defender Gelişmiş tehdit koruması 'nı (Microsoft Defender ATP) bir mobil tehdit savunması çözümü olarak Microsoft Intune tümleştirmenize yardımcı olmak için, güvenlik ihlallerinin önlenmesine ve bir kuruluşun içindeki ihlallerinin etkilerini sınırlamanıza yardımcı olabilirsiniz. Microsoft Defender ATP, Windows 10 veya üstünü çalıştıran cihazlarla çalışır.

Başarılı olmak için Concert 'de aşağıdaki konfigürasyonları kullanın:
- **Intune Ile Microsoft Defender ATP arasında hizmetten hizmete bağlantı kurun**. Bu bağlantı, Microsoft Defender ATP 'yi Intune ile yönettiğiniz Windows 10 cihazlarından makine riski hakkında veri toplamasına olanak sağlar.  
- **Microsoft Defender ATP ile cihazları eklemek için bir cihaz yapılandırma profili kullanın**. Cihazları, Microsoft Defender ATP ile iletişim kuracak şekilde yapılandırmak ve risk düzeylerini değerlendirmeye yardımcı olan verileri sağlamak için kullanabilirsiniz.  
 - **İzin vermek istediğiniz risk düzeyini ayarlamak için bir cihaz uyumluluk Ilkesi kullanın**. Risk düzeyleri Microsoft Defender ATP tarafından raporlanır.  İzin verilen risk düzeyini aşan cihazlar uyumlu değil olarak tanımlanır.  
- Kullanıcıların, uyumlu olmayan cihazlardan şirket kaynaklarına erişmesini engellemek için **koşullu erişim Ilkesi kullanın** .  

Ayrıca, Intune 'u Microsoft Defender ATP ile tümleştirdiğinizde, ATPs tehdidi & güvenlik açığı yönetimi 'nden (TVM) yararlanabilir ve [TVM tarafından tanımlanan uç nokta zayıflılığını düzeltmek Için Intune 'u kullanabilirsiniz](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Intune ile Microsoft Defender ATP kullanma örneği  

Aşağıdaki örnek, kuruluşunuzun korunmasına yardımcı olmak için bu çözümlerin birlikte nasıl çalıştığını açıklamanıza yardımcı olur. Bu örnek için, Microsoft Defender ATP ve Intune zaten tümleşiktir.  

Birisinin kuruluşunuzdaki bir kullanıcıya katıştırılmış kötü amaçlı kod içeren bir sözcük eki gönderdiği bir olay düşünün.  
- Kullanıcı eki açar ve içeriği etkinleştirir.  
- Bir yükseltilmiş ayrıcalık saldırısı başlar ve uzak makinedeki saldırgan, kurbanın cihazında yönetici haklarına sahip olur.  
- Daha sonra saldırgan, kullanıcının diğer cihazlarına uzaktan erişir. Bu güvenlik ihlali tüm kuruluşu etkileyebilir.  

Microsoft Defender ATP, bu senaryo gibi güvenlik olaylarının çözümlenmesine yardımcı olabilir.  
- Örneğimizde, Microsoft Defender ATP cihazın anormal kod yürütüldüğünü, bir işlem ayrıcalık yükseltme yükseltmesi, eklenen kötü amaçlı kod ve şüpheli bir uzak kabuk vermiş olduğunu algılar.  
- Microsoft Defender ATP cihazdan bu eylemlere bağlı [olarak, cihazı yüksek riskli olarak sınıflandırır](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) ve Microsoft Defender Güvenlik Merkezi portalındaki şüpheli etkinlik hakkında ayrıntılı bir rapor içerir.  

Cihazları uyumlu olmayan bir *Orta* veya *yüksek* düzeyde riske göre sınıflandırmak için bir Intune cihaz uyumluluk ilkeniz olduğundan, güvenliği aşılmış bir cihaz uyumlu değil olarak sınıflandırılmıştır. Bu sınıflandırma, koşullu erişim ilkenizin, bu cihazdan kurumsal kaynaklarınıza erişimi başlatmanıza ve erişimini engellemeye olanak tanır.  

## <a name="prerequisites"></a>Önkoşullar

Microsoft Defender ATP 'yi Intune ile birlikte kullanmak için, aşağıdakilerin yapılandırıldığından ve kullanıma hazırlandığınızdan emin olun:

- Enterprise Mobility + Security E3 ve Windows E5 (veya Microsoft 365 Kurumsal E5) için lisanslı kiracı
- Azure AD’ye katılmış [Intune tarafından yönetilen](windows-enroll.md) Windows 10 cihazların olduğu Microsoft Intune ortamı
- Microsoft [Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ve Microsoft Defender güvenlik MERKEZI (ATP portalı) erişimi

## <a name="enable-microsoft-defender-atp-in-intune"></a>Intune 'da Microsoft Defender ATP 'yi etkinleştirme

İlk adım, Intune ile Microsoft Defender ATP arasında hizmetten hizmete bağlantı kurmak için kullanılır. Bu, hem Microsoft Defender Güvenlik Merkezi 'ne hem de Intune 'a yönetici erişimi gerektirir.  

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

Bu görevi genellikle bir kez yaparsınız. Intune kiracınız için Microsoft Defender ATP 'yi etkinleştirdikten sonra, bunu tekrar yapmanız gerekmez.

> [!TIP]  
> Yeni bir uygulamayı Intune mobil tehdit savunması ile tümleştirdiğinizde ve bağlantıyı etkinleştirdiğinizde, Intune Azure Active Directory içinde klasik bir koşullu erişim ilkesi oluşturur. Her MTD uygulaması, [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri gibi, yeni bir klasik koşullu erişim ilkesi oluşturur.  Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinmemelidir veya devre dışı bırakılmalıdır.
> 
> MTD uygulamaları için klasik koşullu erişim ilkeleri: 
> 
> - , Cihazların bir cihaz KIMLIĞI olması için Azure AD 'ye kaydolmasını gerektirmek üzere Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.  
> - , MTD 'leri yönetmeye yardımcı olmak için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır.
> - Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.  
> 
> Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilkeleri**' ne gidin.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Bir yapılandırma profili kullanarak cihazları ekleme

Intune ile Microsoft Defender ATP arasında hizmetten hizmete bağlantı kurduktan sonra, risk düzeyiyle ilgili verilerin toplanabilmesi ve kullanılabilmesi için Intune yönetilen cihazlarınızı ATP 'ye ekleyin. Cihazları eklemek için, Microsoft Defender ATP için bir cihaz yapılandırma profili kullanırsınız.  

Microsoft Defender ATP bağlantısı kurduktan sonra Intune, Microsoft Defender ATP 'den bir Microsoft Defender ATP ekleme yapılandırma paketi aldı. Bu paket cihaz yapılandırma profiliyle cihazlara dağıtılır. Yapılandırma paketi, cihazları taramak, tehditleri algılamak ve riski Microsoft Defender ATP 'ye bildirmek üzere [Microsoft Defender ATP hizmetleriyle](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) iletişim kuracak şekilde yapılandırır.  

Yapılandırma paketini kullanarak bir cihaz ekledikten sonra, bunu tekrar yapmanız gerekmez. [Bir grup ilkesi veya System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) kullanarak da cihaz ekleyebilirsiniz.

### <a name="create-the-device-configuration-profile"></a>Cihaz yapılandırma profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzeri**’ni seçin
5. **Profil türü**Için **Microsoft Defender ATP (Windows 10 Masaüstü)** öğesini seçin.
6. Şu ayarları yapılandırın:

   - **Microsoft Defender ATP istemci yapılandırma paketi türü**: Yapılandırma paketini profile **eklemek için Ekle** ' yi seçin. Yapılandırma paketini profilden çıkarmak için **Çıkar**’ı seçin.
  
     > [!NOTE]  
     > Microsoft Defender ATP ile düzgün bir şekilde bağlantı oluşturduysanız, **Intune otomatik olarak** yapılandırma profilini, **Microsoft Defender ATP istemci yapılandırma paketi türü** ayarını de kullanıma sunulacaktır.
  
    - **Tüm dosyalar Için örnek paylaşımı**: **Etkinleştir** ayarı, örneklerin toplanmasına ve MICROSOFT Defender ATP ile paylaşılmasına olanak tanır. Örneğin, şüpheli bir dosya görürseniz, ayrıntılı analiz için Microsoft Defender ATP 'ye gönderebilirsiniz. **Yapılandırılmadı** , MICROSOFT Defender ATP 'ye herhangi bir örnek paylaşmaz.
    - **Telemetri raporlama sıklığını**hızlandırın: Yüksek riskli cihazlarda, bu ayarı **etkinleştirin** ve bu ayarı, MICROSOFT Defender ATP hizmetine daha sık telemetri rapor eder.

    [System Center Configuration Manager kullanarak Windows 10 makineler](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) eklemek, bu MICROSOFT Defender ATP ayarları hakkında daha fazla bilgi içerir.

7. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin, böylece profil oluşturulur.
8. [Cihaz yapılandırma profilini,](device-profile-assign.md) MICROSOFT Defender ATP ile değerlendirmek Istediğiniz cihazlara atayın.  

## <a name="create-and-assign-the-compliance-policy"></a>Uyumluluk ilkesi oluşturma ve atama  

Uyumluluk ilkesi, bir cihaz için kabul edilebilir olarak düşünebileceğiniz risk düzeyini belirler.

### <a name="create-the-compliance-policy"></a>Uyumluluk ilkesini oluşturma  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzerini** seçin.
5. **Microsoft Defender ATP** ayarları ' nda, **cihazın makine risk puanı altında veya altında olmasını gerektir** ayarını tercih ettiğiniz düzeye ayarlayın. 
   
   Tehdit düzeyi sınıflandırmaları, [Microsoft Defender ATP tarafından belirlenir](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Temizle**: Bu düzey en güvenli seçenektir. Cihazda mevcut tehditler bulunamaz ve şirket kaynaklarına erişmeye devam edin. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir. (Microsoft Defender ATP kullanıcıları değeri *güvenlidir*.)
   - **Düşük**: Yalnızca düşük düzeydeki tehditler mevcutsa cihaz uyumludur. Orta veya yüksek tehdit düzeylerine sahip cihazlar uyumlu değildir.
   - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
   - **Yüksek**: Bu düzey en az güvenlidir ve tüm tehdit düzeylerine izin verir. Yüksek, orta veya düşük tehdit düzeylerine sahip cihazlar uyumlu kabul edilir.

6. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).  
7. [Cihaz Uyumluluk ilkesini](create-compliance-policy.md#assign-user-groups) uygulanabilir gruplara atayın.



## <a name="create-a-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma  

Koşullu erişim ilkesi, uyumluluk ilkenizde ayarladığınız tehdit düzeyini aşan cihazlar için kaynaklara erişimi engeller. Cihazdan SharePoint veya Exchange Online gibi şirket kaynaklarına erişimi engelleyebilirsiniz.  

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



## <a name="monitor-device-compliance"></a>Cihaz uyumluluğunu izleme  

Ardından, Microsoft Defender ATP Uyumluluk ilkesine sahip cihazların durumunu izleyin.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu** > **İlke uyumluluğu**’nu seçin.
3. Listede Microsoft Defender ATP ilkenizi bulun ve hangi cihazların uyumlu veya uyumsuz olduğunu görün.

## <a name="next-steps"></a>Sonraki adımlar  

[Microsoft Defender ATP koşullu erişimi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)   
[Microsoft Defender ATP risk panosu](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  
[Cihazların sorunlarını gidermek Için ATPs güvenlik açığı yönetimi ile güvenlik görevlerini kullanın](atp-manage-vulnerabilities.md).  
[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)  
 
