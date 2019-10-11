---
title: Microsoft Intune-Azure 'da Microsoft Defender ATP 'yi kullanma | Microsoft Docs
description: Kurulum ve yapılandırma dahil olmak üzere Intune ile Microsoft Defender Gelişmiş tehdit koruması 'nı (Microsoft Defender ATP) kullanın, Intune cihazlarınızı ATP ile ekleme ve ardından Intune cihaz uyumluluğuyla ve koşullu bir cihaz ATP risk değerlendirmesi kullanma ağ kaynaklarını korumak için erişim ilkeleri.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bea28afc39a693dc4d634a0ff92c8ce900ab5a22
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237175"
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
- Kullanıcı eki açar ve içeriği sunar.  
- Yükseltilmiş bir ayrıcalık saldırısı başlar ve uzak bir makineden bir saldırganın, kurban cihazında yönetici hakları vardır.  
- Saldırgan daha sonra kullanıcının diğer cihazlarına uzaktan erişir. Bu güvenlik ihlali, kuruluşun tamamını etkileyebilir.  

Microsoft Defender ATP, bu senaryo gibi güvenlik olaylarının çözümlenmesine yardımcı olabilir.  
- Örneğimizde, Microsoft Defender ATP cihazın anormal kod yürütüldüğünü, bir işlem ayrıcalık yükseltme yükseltmesi, eklenen kötü amaçlı kod ve şüpheli bir uzak kabuk vermiş olduğunu algılar.  
- Microsoft Defender ATP cihazdan bu eylemlere bağlı [olarak, cihazı yüksek riskli olarak sınıflandırır](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) ve Microsoft Defender Güvenlik Merkezi portalındaki şüpheli etkinlik hakkında ayrıntılı bir rapor içerir.  

Cihazları uyumlu olmayan bir *Orta* veya *yüksek* düzeyde riske göre sınıflandırmak için bir Intune cihaz uyumluluk ilkeniz olduğundan, güvenliği aşılmış bir cihaz uyumlu değil olarak sınıflandırılmıştır. Bu sınıflandırma, koşullu erişim ilkenizin, bu cihazdan kurumsal kaynaklarınıza erişimi başlatmanıza ve erişimini engellemeye olanak tanır.  

## <a name="prerequisites"></a>Prerequisites

Microsoft Defender ATP 'yi Intune ile birlikte kullanmak için, aşağıdakilerin yapılandırıldığından ve kullanıma hazırlandığınızdan emin olun:

- Enterprise Mobility + Security E3 ve Windows E5 (veya Microsoft 365 Kurumsal E5) için lisanslı kiracı
- Microsoft Intune ortamı, ayrıca Azure AD 'ye katılmış [Intune ile yönetilen](../enrollment/windows-enroll.md) Windows 10 cihazları
- Microsoft [Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ve Microsoft Defender güvenlik MERKEZI (ATP portalı) erişimi

## <a name="enable-microsoft-defender-atp-in-intune"></a>Intune 'da Microsoft Defender ATP 'yi etkinleştirme

İlk adım, Intune ile Microsoft Defender ATP arasında hizmetten hizmete bağlantı kurmak için kullanılır. Bu, hem Microsoft Defender Güvenlik Merkezi 'ne hem de Intune 'a yönetici erişimi gerektirir.  

### <a name="to-enable-defender-atp"></a>Defender ATP 'yi etkinleştirmek için  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluk** > **Microsoft Defender ATP**' yi seçin ve ardından *bağlayıcı ayarları*altında **Microsoft Defender Güvenlik Merkezi 'ni aç**' ı seçin.

    ![Microsoft Defender Güvenlik Merkezi 'ni açmak için seçin](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. **Microsoft Defender Güvenlik Merkezi**'nde:
    1. @No__t **ayarları**-1**Gelişmiş Özellikler**' i seçin.
    2. **Microsoft Intune bağlantı**için **Şu seçeneği belirleyin**:

        ![Intune bağlantısını etkinleştirme](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. **Tercihleri kaydet**' i seçin.

4. Intune, **cihaz uyumluluğu** > **Microsoft Defender ATP**'ye geri dönün. **Windows cihazları sürüm 10.0.15063 ve üstünü Microsoft Defender ATP** 'yi **Açık**olarak ayarlayın.
5. **Kaydet**' i seçin.

Bu görevi genellikle bir kez yapabilirsiniz. Intune kiracınız için Microsoft Defender ATP 'yi etkinleştirdikten sonra, bunu tekrar yapmanız gerekmez.

> [!TIP]  
> Yeni bir uygulamayı Intune mobil tehdit savunması ile tümleştirdiğinizde ve Intune bağlantısını etkinleştirdiğinizde, Intune Azure Active Directory içinde klasik bir koşullu erişim ilkesi oluşturur. [Defender ATP](advanced-threat-protection.md) veya ek [MTD iş ortaklarından](mobile-threat-defense.md#mobile-threat-defense-partners)herhangi biri dahil olmak üzere tümleştirilen her MTD uygulaması yeni bir klasik koşullu erişim ilkesi oluşturur. Bu ilkeler yoksayılabilir, ancak düzenlenmemelidir, silinmemelidir veya devre dışı bırakılmalıdır.
> 
> MTD uygulamaları için klasik koşullu erişim ilkeleri: 
> 
> - , Cihazların Azure AD 'ye kaydolmasını gerektirmek için, MTD iş ortaklarıyla iletişim kurmadan önce cihaz KIMLIĞI olması için Intune MTD tarafından kullanılır. KIMLIK, cihazların ve durumlarını Intune 'a başarıyla bildirebileceği şekilde gereklidir.  
> - Diğer bulut uygulamaları veya kaynakları üzerinde hiçbir etkisi yoktur.  
> - , MTD 'leri yönetmeye yardımcı olmak için oluşturabileceğiniz koşullu erişim ilkelerinden farklıdır.
> - Varsayılan olarak, değerlendirme için kullandığınız diğer koşullu erişim ilkeleriyle etkileşime geçin.  
> 
> Klasik koşullu erişim ilkelerini görüntülemek için [Azure](https://portal.azure.com/#home)'da **Azure Active Directory** > **koşullu erişim** > **Klasik ilke**' ye gidin.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Bir yapılandırma profili kullanarak cihazları ekleme

Intune ile Microsoft Defender ATP arasında hizmetten hizmete bağlantı kurduktan sonra, risk düzeyiyle ilgili verilerin toplanabilmesi ve kullanılabilmesi için Intune yönetilen cihazlarınızı ATP 'ye ekleyin. Cihazları eklemek için, Microsoft Defender ATP için bir cihaz yapılandırma profili kullanırsınız.  

Microsoft Defender ATP bağlantısı kurduktan sonra Intune, Microsoft Defender ATP 'den bir Microsoft Defender ATP ekleme yapılandırma paketi aldı. Bu paket cihaz yapılandırma profiliyle cihazlara dağıtılır. Yapılandırma paketi, cihazları taramak, tehditleri algılamak ve riski Microsoft Defender ATP 'ye bildirmek üzere [Microsoft Defender ATP hizmetleriyle](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) iletişim kuracak şekilde yapılandırır.  

Yapılandırma paketini kullanarak bir cihaz ekledikten sonra, bunu tekrar yapmanız gerekmez. Ayrıca, bir [Grup İlkesi veya System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)kullanarak da cihaz ekleyebilirsiniz.


### <a name="create-the-device-configuration-profile"></a>Cihaz yapılandırma profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. @No__t-3**Profil oluştur**@no__t **cihaz yapılandırması**' nı seçin.
3. Bir **ad** ve **Açıklama**girin.
4. **Platform**için **Windows 10 ve üzeri** ' i seçin
5. **Profil türü**Için **Microsoft Defender ATP (Windows 10 Masaüstü)** öğesini seçin.
6. Ayarları yapılandırın:

   - **Microsoft Defender ATP istemci yapılandırma paketi türü**: yapılandırma paketini profile **eklemek için Ekle** ' yi seçin. Yapılandırma paketini profilden kaldırmak için **kapalı Pano** ' yı seçin.
  
     > [!NOTE]  
     > Microsoft Defender ATP ile düzgün bir şekilde bağlantı oluşturduysanız, **Intune otomatik olarak yapılandırma profilini,** **Microsoft Defender ATP istemci yapılandırma paketi türü** ayarını de kullanıma sunulacaktır.
  
    - **Tüm dosyalar Için örnek paylaşımı**: **Etkinleştir** , örneklerin toplanmasına ve Microsoft Defender ATP ile paylaşılmasına olanak tanır. Örneğin, şüpheli bir dosya görürseniz, ayrıntılı analiz için Microsoft Defender ATP 'ye gönderebilirsiniz. **Yapılandırılmadı** , MICROSOFT Defender ATP 'ye herhangi bir örnek paylaşmaz.
    - **Telemetri raporlama sıklığını**hızlandırın: yüksek riskli olan cihazlar için bu ayarı **etkinleştirin** ve bu AYARı, Microsoft Defender ATP hizmetine daha sık telemetri rapor eder.

    [System Center Configuration Manager kullanarak Windows 10 makineler](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) eklemek, bu MICROSOFT Defender ATP ayarları hakkında daha fazla bilgi içerir.

7. **Tamam**' ı seçin ve oluşturduğunuz değişiklikleri kaydetmek için **Oluştur** ' u seçin.
8. [Cihaz yapılandırma profilini,](../configuration/device-profile-assign.md) MICROSOFT Defender ATP ile değerlendirmek Istediğiniz cihazlara atayın.  


## <a name="create-and-assign-the-compliance-policy"></a>Uyumluluk ilkesi oluşturma ve atama  

Uyumluluk ilkesi, bir cihaz için kabul edilebilir olarak düşünebileceğiniz risk düzeyini belirler.

### <a name="create-the-compliance-policy"></a>Uyumluluk ilkesini oluşturma  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. @No__t **cihaz uyumluluk** **@no__t-** 3**ilke oluştur**' u seçin.
3. Bir **ad** ve **Açıklama**girin.
4. **Platformda** **Windows 10 ve üzeri**' i seçin.
5. **Microsoft Defender ATP** ayarları ' nda, **cihazın makine risk puanı altında veya altında olmasını gerektir** ayarını tercih ettiğiniz düzeye ayarlayın. 
   
   Tehdit düzeyi sınıflandırmaları, [Microsoft Defender ATP tarafından belirlenir](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Temizle**: Bu düzey en güvenli seçenektir. Cihazda mevcut tehditler bulunamaz ve şirket kaynaklarına erişmeye devam edin. Herhangi bir tehdit bulunursa, cihaz uyumsuz olarak değerlendirilir. (Microsoft Defender ATP kullanıcıları değeri *güvenlidir*.)
   - **Düşük**: cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Orta veya yüksek tehdit düzeylerine sahip cihazlar uyumlu değildir.
   - **Orta**: cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Üst düzey tehditler algılanırsa, cihaz uyumsuz olarak belirlenir.
   - **Yüksek**: Bu düzey en az güvenlidir ve tüm tehdit düzeylerine izin verir. Yüksek, orta veya düşük tehdit düzeylerine sahip cihazlar uyumlu kabul edilir.

6. **Tamam**' ı seçin ve ardından **Oluştur** ' u seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).  
7. [Cihaz Uyumluluk ilkesini](create-compliance-policy.md#assign-the-policy) uygulanabilir gruplara atayın.



## <a name="create-a-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma  

Koşullu erişim ilkesi, uyumluluk ilkenizde ayarladığınız tehdit düzeyini aşan cihazlar için kaynaklara erişimi engeller. Cihazdan SharePoint veya Exchange Online gibi şirket kaynaklarına erişimi engelleyebilirsiniz.  

> [!TIP]  
> Koşullu erişim bir Azure Active Directory (Azure AD) teknolojisidir. *Intune* 'Dan erişilen koşullu erişim düğümü, *Azure AD*'den erişilen aynı düğümdür.  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **koşullu erişim** > **Yeni ilke**' yi seçin.
2. Bir ilke **adı**girin ve **Kullanıcılar ve gruplar**' ı seçin. İlke için gruplarınızı eklemek için dahil etme veya hariç tutma seçeneklerini kullanın ve **bitti**' yi seçin.
3. **Bulut uygulamaları**' nı seçin ve korunacak uygulamaları seçin. Örneğin, **Uygulama Seç**' i seçin ve **Office 365 SharePoint online** ve **Office 365 Exchange Online**' ı seçin.

    Değişikliklerinizi kaydetmek için **bitti** ' yi seçin.

4. İlkeyi uygulamalar ve tarayıcılara uygulamak için @no__t **Koşulları**-1**istemci uygulaması** ' nı seçin. Örneğin, **Evet**' i seçin ve ardından **tarayıcı** ve **mobil uygulamalar ve Masaüstü istemcileri**' ni etkinleştirin.

    Değişikliklerinizi kaydetmek için **bitti** ' yi seçin.

5. Cihaz uyumluluğuna göre koşullu erişim uygulamak için **Izin ver** ' i seçin. Örneğin, @no__t **erişim ver**' i seçin-1**cihazın uyumlu olarak işaretlenmesini gerektir**.

    Değişikliklerinizi kaydetmek için **Seç ' i** seçin.

6. **Ilkeyi etkinleştir**' i seçin ve sonra değişikliklerinizi kaydetmek için **Oluştur** ' u seçin.



## <a name="monitor-device-compliance"></a>Cihaz uyumluluğunu izleme  

Ardından, Microsoft Defender ATP Uyumluluk ilkesine sahip cihazların durumunu izleyin.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluk** > **ilke uyumluluğu**' nu seçin.
3. Listede Microsoft Defender ATP ilkenizi bulun ve hangi cihazların uyumlu veya uyumsuz olduğunu görün.

## <a name="view-onboarding-status"></a>Ekleme durumunu görüntüle
Tüm Intune ile yönetilen Windows 10 cihazlarının ekleme durumunu görüntülemek için **cihaz uyumluluğu** > **Microsoft Defender ATP**'ye gidebilirsiniz. Bu sayfadan, Microsoft Defender ATP 'ye daha fazla cihaz ekleme için bir cihaz yapılandırma profili oluşturmayı da başlatabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar  

[Microsoft Defender ATP koşullu erişim](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)   
[Microsoft Defender ATP risk panosu](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  
[Cihazların sorunlarını gidermek Için ATPs güvenlik açığı yönetimi ile güvenlik görevlerini kullanın](atp-manage-vulnerabilities.md).  
[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)  
 
