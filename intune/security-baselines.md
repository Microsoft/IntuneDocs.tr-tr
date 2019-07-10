---
title: Microsoft Intune - Azure güvenlik temellerini kullanın | Microsoft Docs
description: Ekleyebilir veya kullanıcı ve mobil cihaz yönetimi için Intune cihazlardaki verileri korumak için önerilen windows güvenlik ayarlarını yapılandırın. BitLocker'ı etkinleştirmek, Microsoft Defender Gelişmiş tehdit koruması yapılandırma, Internet Explorer denetim, Smart Screen kullanan, yerel güvenlik ilkelerini ayarlama, parola iste, Internet karşıdan yüklemeler ve daha fazlasını engelleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e4e1040913daef5418f0b4fa1e56f6ef827dd67
ms.sourcegitcommit: 63b55e81122e5c15893302b109ae137c30855b55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67713268"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Intune'da Windows 10 cihazları yapılandırmak için güvenlik temellerini kullanın

Güvenli ve kullanıcılarınızı ve cihazlarınızı korumaya yardımcı olmak için Intune'un güvenlik temellerini kullanın. Güvenlik temellerini yardımcı olan ayarlar bilinen bir Grup ayarlarını ve ilgili güvenlik ekipleri tarafından önerilen varsayılan değerleri uygulamak Windows önceden yapılandırılmış gruplarıdır. Intune'da bir güvenlik temel profilini oluşturduğunuzda, oluşturmakta olduğunuz bir *cihaz Yapılandırması* profili.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 sürüm 1809 ve üzeri

Intune cihaz veya kullanıcı gruplarına güvenlik temellerini dağıtma ve ayarlarını Windows 10 veya sonraki sürümleri çalıştıran cihazlar için geçerlidir. Örneğin, *MDM güvenlik temeli* BitLocker çıkarılabilir sürücüler için otomatik olarak etkinleştirir, otomatik olarak bir cihazın kilidini açmak için parola gerektirir, otomatik olarak ve temel kimlik doğrulaması devre dışı bırakır. Varsayılan değer, ortamınız için işe yaramazsa, gereksinim duyduğunuz ayarları uygulamak için taban çizgisini özelleştirin.  

Ayrı temel türleri, aynı ayarları içerir ancak bu ayarlar için farklı varsayılan değerleri kullanın. Taban çizgileri varsayılan değerleri anlamak için kullanılacak seçin ve ardından kuruluşunuzun uyacak şekilde her bir taban çizgisi değiştirmesi gereken önemlidir.  

> [!NOTE]
> Microsoft, güvenlik temellerini Önizleme sürümleri üretim ortamında kullanılması önerilir değil. Bir önizleme temelini ayarlar, Önizleme boyunca değişebilir. 

Güvenlik temellerini kullanma amacıyla bir uçtan uca güvenli iş akışını Microsoft 365 ile çalışırken sağlamaktır. Bazı avantajları şunlardır:

- Güvenlik temeli, en iyi yöntemler ve öneriler etkileyen güvenlik ayarlarını içerir. Grup İlkesi, güvenlik temellerini oluşturur Windows Güvenlik Ekibi ile Intune iş ortakları. Bu önerileri kılavuz ve kapsamlı deneyimi temel alır.
- Nereden başlayacağınızı ıntune'a yeni ve emin değil, ardından güvenlik temellerini size avantajlı. Hızlı bir şekilde oluşturabilir ve kuruluşunuzun kaynakları ve veri korumaya yardımcı oluyoruz bilmek bir güvenlik profili dağıtın.
- Şu anda Grup İlkesi kullanırsanız, Yönetim için Intune'a geçiş ile bu taban çizgisi çok daha kolaydır. Bu temelleri yerel olarak Intune'da yerleşiktir ve modern yönetim deneyimi içerir.



[Windows güvenlik temellerini](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) bu özellik hakkında daha fazla bilgi için harika bir kaynaktır. [Mobil cihaz Yönetimi](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) olan MDM ve Windows cihazlarda neler yapabileceğiniz hakkında harika bir kaynak.

## <a name="security-baseline-versions-and-instances"></a>Güvenlik temel sürümler ve örnekleri
Zaman zaman, temel bir yeni güncelleştirmeleri kullanılabilir hale gelir. Her yeni sürümü örneğini temel eklemek veya ayarları kaldırabilir veya diğer değişikliğine neden. Örneğin, yeni Windows 10 ayarları ile yeni Windows 10 sürümleri kullanılabilir oldukça, MDM güvenlik temeli en yeni ayarları içeren yeni bir sürümü örneği alabilirsiniz.  

Intune konsolunda kullanılabilir hangi güvenlik temellerini ve bunlarla ilgili bilgileri görüntüleyebilirsiniz. Bu temel kullanan sahip olduğunuz kaç profillerini yazın, temel türündeki kaç ayrı örnekleri kullanılabilir ve son son örneğini kullanılabilir veya yayımlanmış ne zaman yapıldığı kullanılabilir bilgileri içerir.  Aşağıdaki örnek için kullanılan iyi bir MDM güvenlik temeli kutucuk gösterilmektedir:  

![Taban çizgisi kutucuğu](./media/security-baselines/baseline-tile.png)

Temel sürümler kullanmak, bir taban çizgisini seçin ve ardından ilgili bilgileri görüntülemek için **sürümleri**. Intune, profillerinizi tarafından kullanımda sürümleri hakkında ayrıntıları görüntüler. Sürümleri bölmesinde, bu sürümü kullanmak profilleri hakkında daha ayrıntılı ayrıntılarını görüntülemek için tek bir sürüm seçebilirsiniz. Ayrıca iki farklı sürümlerini seçin ve ardından **karşılaştırma taban çizgileri** bu farklılıkları ayrıntılı bir CSV dosyasını indirmek için.  

![Taban çizgileri karşılaştırın](./media/security-baselines/compare-baselines.png)

Bir güvenlik taban çizgisi oluştururken *profili*, profil otomatik olarak en kısa süre önce yayımlanan güvenlik temeli örneği kullanır.  Önceki bir temel sürüm örneği önizleme sürümüyle oluşturulan taban çizgilerini dahil olmak üzere daha önce oluşturduğunuz profillerini kullanıp devam edebilirsiniz. 

Güvenlik temeli destek profilleri bir [sürümünü değiştirmek](#change-the-baseline-instance-for-a-profile) temelinin kullanılıyor. Bunun anlamı, yeni bir sürüm sürümü çıktığında yararlanmak için yeni bir temel profilini oluşturmanız gerekmez. Bunun yerine, hazır olduğunuzda, bir temel profilini seçin ve ardından bu profil için örnek sürümü değiştirmek için yerleşik seçeneğini kullanın.  

## <a name="available-security-baselines"></a>Kullanılabilir güvenlik temelleri 

Aşağıdaki güvenlik temeli örnekleri, Intune ile kullanmak için kullanılabilir. En son örneğinin her bir taban çizgisi ayarlarını görüntülemek için bağlantıları kullanın. 

- **MDM güvenlik temeli**
  - [MDM güvenlik temeli Spring 2019 (19 saat 1)](security-baseline-settings-mdm.md)
  - [Önizleme: Ekim 2018 için MDM güvenlik temeli](security-baseline-settings-mdm-archive.md)

- **Windows Defender ATP temeli**  
  *(Bu temel kullanmak için ortamınız kullanmak için önkoşulları karşılamalıdır [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites))* .
  - [Önizleme: Windows Defender ATP temeli](security-baseline-settings-defender-atp.md)  

Bu önizleme şablonu artık yeni profilleri oluşturmak için kullanılabilir olsa bile, bir önizleme şablona göre daha önce oluşturduğunuz profillerini kullanıp devam edebilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar
- Intune'da temellerini yönetmek için hesabınızın olması gerekir [ilke ve Profil Yöneticisi](role-based-access-control.md#built-in-roles) yerleşik rolü.

- Bazı taban çizgileri kullanımını Microsoft Defender ATP gibi ek hizmetler etkin bir aboneliğiniz gerektirebilir.  

## <a name="co-managed-devices"></a>Ortak yönetilen cihazlar

Intune tarafından yönetilen cihazların temel güvenlik özelliklerinizin ortak yönetilen cihazlar Configuration Manager ile benzerdir. Ortak yönetilen cihazların, aynı anda Windows 10 cihazları yönetmek için System Center Configuration Manager ve Microsoft Intune kullanın. Mevcut Configuration Manager yatırımınızı avantajlara ıntune bulut ekleme olanak tanır. [Ortak yönetim genel bakış](https://docs.microsoft.com/sccm/comanage/overview) Yapılandırma Yöneticisi'ni, ve ayrıca bulutun avantajlarından istiyorsanız harika bir kaynaktır.

Ortak yönetilen cihazların kullanırken geçmelidir **cihaz Yapılandırması** Intune iş yüküne (ayarlarına). [Cihaz yapılandırması iş yükleri](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) daha fazla bilgi sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) seçip **cihaz güvenliği** > **güvenlik temellerini** kullanılabilir temellerinin listesini görüntülemek için.


    ![Yapılandırmak için bir güvenlik taban çizgisi seçin](./media/security-baselines/available-baselines.png)

2. Kullanın ve ardından istediğiniz taban çizgisini seçin **profili oluşturma**.  

3. Üzerinde **Temelleri** sekmesinde, aşağıdaki özellikleri belirtin:

    - **Ad**: Güvenlik temelleri profiliniz için bir ad girin. Örneğin, *Defender ATP için standart profili*.

    - **Açıklama**: Bu temel ne yaptığını açıklayan metin girin. Açıklama girin, istediğiniz herhangi bir metin için bağlıdır. Bu, isteğe bağlı ancak önerilen değerdir.  

   Seçin **sonraki** sonraki sekmesine gidin. Yeni bir sekmeye Gelişmiş sonra daha önce görüntülenen bir sekmesine geri dönmek için sekmesinde adı seçebilirsiniz.  

4. Yapılandırma ayarları sekmesinde gruplarını görüntülemek **ayarları** seçtiğiniz temeli kullanılabilir. Ayarları, Grup ve temelindeki bu ayarlar için varsayılan değerleri görüntülemek için bir grubu genişletebilirsiniz. Belirli ayarları bulmak için:
   - Genişletin ve kullanılabilir ayarlarını gözden geçirmek için bir grubu seçin.  
   - Kullanım *arama* çubuk ve arama ölçütlerinizi içeren gruplarını görüntülemek için görünüme filtre uygulamak anahtar belirtin.  
 
   Bu temel sürümü için varsayılan bir yapılandırma temelindeki her bir ayar vardır. İş ihtiyaçlarınızı karşılamak için varsayılan ayarlarını yeniden yapılandırın. Farklı taban çizgileri aynı ayarı içerir ve temel amacı bağlı olarak, ayar için farklı varsayılan değerleri kullanmak. 

    ![Bu grubun ayarlarını görüntülemek için bir grubu genişletin](./media/security-baselines/sample-list-of-settings.png)

5. Üzerinde **kapsam etiketleri** sekmesinde **kapsam etiketleri seçin** açmak için *etiketleri seçin* profil kapsam etiketleri atamak bölmesi. 

6. Üzerinde **atamaları** sekmesinde **dahil edilecek grupları seçin** ve temel bir veya daha fazla gruba atayın. Kullanım **dışlanacak Grupları Seç** atama ince ayar yapmak için.  

   ![Profil atama](./media/security-baselines/assignments.png)
  
7. Taban çizgisi dağıtmaya hazır olduğunuzda, ilerleyin **gözden + Oluştur** sekmesini ve temel ayrıntılarını gözden geçirin. Seçin **Oluştur** kaydedip profili dağıtın.  

   Profil oluşturma hemen sonra atanmış bir gruba gönderilir ve hemen uygulanabilir.

   > [!TIP]  
   > Bunu yapmak için profil, ilk gruplarına atayarak olmadan bir profili kaydedin, daha sonra düzenleyebilirsiniz.  

   ![Taban çizgisi gözden geçirin](./media/security-baselines/review.png) 

  
8. Bir profil oluşturduktan sonra şuraya giderek Düzenle **cihaz güvenliği** > **güvenlik temellerini**, yapılandırılmış ve ardından temel türünü seçin **profilleri**.  Profili kullanılabilir profiller listesinden seçin ve ardından **özellikleri**. Tüm kullanılabilir yapılandırma sekmelerindeki ayarlarını düzenleyin ve seçin **gözden geçir + Kaydet** değişiklikleri işlemek için.  

## <a name="change-the-baseline-instance-for-a-profile"></a>Bir profili temel örnek
Temel profiller profilini kullanan temel örnek, bir değişiklik destekler. Daha eski bir örneği veya genellikle aynı taban daha yeni bir örneğini seçebilirsiniz.  Bir profil MDM güvenlik taban çizgisi için kullanılacak bir taban çizgisi için Defender ATP kullanımından değiştirme gibi iki farklı temelleri arasında geçiş yapamazsınız. 

Temel sürüm değişikliği yapılandırılırken kullanılan iki temel sürümler arasındaki değişiklikleri listeleyen bir CSV dosyası yükleme seçeneği gerekir. Seçim temel sürümü tüm özelleştirmelerinizi tutun ve bunları yeni sürüme uygulamak için de sunulan veya tüm yeni temel sürüm, seçtiğiniz bulunan Varsayılanları uygulayın. 

Dönüştürme tamamlandıktan sonra kaydetmenizin ardından temel hemen atanan gruplar için yeniden.  

**Dönüştürme sırasında**:
- Kullanmakta olduğunuz'in özgün sürümünde olmayan yeni ayarlar eklenir ve varsayılan değerleri kullanmak için ayarlayın.  

- Seçtiğiniz yeni temel sürüm olmayan ayarlar kaldırılır ve artık bu güvenlik temel profilini tarafından zorunlu tutulur.  

  Bir ayarı artık temel profili tarafından yönetildiğinde bu ayarı cihazda sıfırlama değil. Bunun yerine, ayarı değiştirmek için başka bir işlem kadar son yapılandırmasını cihaz kalır kümesine ayarları yönetir. Farklı temel profilini, Grup İlkesi ayarı veya cihazda yapılan el ile yapılandırma yönetmeyi durdurduktan sonra bir ayarı değiştirebilir işlemleri örnekleridir. 

### <a name="to-change-the-instance-for-a-baseline"></a>Örnek bir taban çizgisi için değiştirmek için  

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) seçip **cihaz güvenliği** > **güvenlik temellerini**ve ardından istediğiniz profili olan temel türü için kutucuğu seçin değiştirilecek.  

2. Ardından, **profilleri**ve ardından onay kutusunu düzenleyin ve ardından istediğiniz profili seçin **sürümünü Değiştir**.  

   ![bir taban çizgisi seçin](./media/security-baselines/select-baseline.png)  

3. Üzerinde **sürümünü Değiştir** bölmesinde, kullanım **güncelleştirmek için bir güvenlik taban çizgisi seçin** açılır listesinde, kullanmak istediğiniz sürüm örneği seçin.  

   ![bir sürüm seçin](./media/security-baselines/select-instance.png)  
   
4. Seçin **İnceleme güncelleştirmeniz** profilleri geçerli örneği için başka bir sürümü ve seçtiğiniz yeni sürümü arasındaki farkı görüntüler bir CSV dosyası indirilemedi. Hangi ayarların eklenen anlamanız kaldırıldıysa, bu dosyayı gözden geçirmesine ve güncelleştirilmiş profilinde bu ayarları için varsayılan değerleri nelerdir.  

   Hazır olduğunuzda bir sonraki adıma devam edin.  

5. İçin iki seçenekten birini **profilini güncelleştirmek için bir yöntem Seç**: 
   - **Temel değişiklikleri kabul etmek, ancak mevcut özelleştirmeleri ayarı tutmak** -bu seçenek için temel profilini yaptığınız özelleştirmeleri tutar ve bunları kullanmak için seçtiğiniz yeni sürümü için geçerlidir.
   - **Temel değişiklikleri kabul etmek ve özelleştirmeler ayarı mevcut atmak** -bu seçenek, özgün profilinizi tamamen üzerine yazar. Güncelleştirilmiş profil, tüm ayarlar için varsayılan değerleri kullanır.  

6. Seçin **gönderme**. Profil seçili temel sürümü ve güncelleştirmeleri dönüştürme işlemi tamamlandıktan sonra taban çizgisi için atanan gruplar hemen yeniden dağıtır.

## <a name="remove-a-security-baseline-assignment"></a>Güvenlik temeli atamasını Kaldır
Ne zaman bir güvenlik taban çizgisi ayarı artık bir cihaz için geçerli veya temel ayarlarında ayarlandığında *yapılandırılmadı*, bir cihazda bu ayarları önceden yönetilen bir yapılandırmaya geri yok. Bunun yerine, daha önce yönetilen cihaz ayarları, başka bir işlem güncelleştirmeleri bu ayarları cihaza kadar taban çizgisinden alındı olarak son yapılandırmalarına tutun.  

Yeni veya farklı güvenlik temeli, cihaz yapılandırma profili, Grup İlkesi yapılandırmalarını veya cihazdaki ayarı el ile düzenleme cihazdaki ayarları daha sonra değişebilir diğer işlemleri içerir.  





## <a name="q--a"></a>Soru - Yanıt

#### <a name="why-these-settings"></a>Neden bu ayarları?

Microsoft Güvenlik takımı, doğrudan Windows geliştiricileri ve güvenlik topluluğu bu önerileri oluşturmak için çalışma deneyim vardır. Bu temel ayarlarda, en uygun güvenlik ile ilgili yapılandırma seçenekleri olarak kabul edilir. Windows bulunan her yeni yapı takım önerilerini, yeni yayımlanmış özelliklere göre ayarlar.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Windows Grup İlkesi vs güvenlik taban çizgileri için öneriler bir fark yoktur. Intune?

Aynı Microsoft Güvenlik takımı, seçtiğiniz ve her bir taban çizgisi ayarlarını düzenlenir. Intune Intune güvenlik taban çizgisi testlerinde ilgili ayarları içerir. Bir şirket içi etki alanı denetleyicisine özgü bazı ayarlar Grup İlkesi temelindeki vardır. Bu ayarlar, Intune'un önerileri bırakılır. Tüm ayarlar aynıdır.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Intune güvenlik temelleri CI veya NSIT uyumlu misiniz?

Kesinlikle, Hayır konuşma. Microsoft Güvenlik takımı, kuruluş, öneriler derlemeye CIS'deki gibi danışır. Ancak, "CIS uyumlu" ve Microsoft taban çizgileri arasında bire bir eşleme yoktur.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Microsoft'un güvenlik temellerini hangi sertifikaları var mı? 

- Microsoft güvenlik temellerini grup ilkeleri (GPO'lar) için yayımlama devam eder ve [güvenlik Uyumluluk Araç Seti](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10)yıllardır sahip gibi. Bu taban çizgisi pek çok kuruluş tarafından kullanılır. Kurumsal müşteriler ve dış kurumları, Savunma Bakanlığı (DoD), Ulusal Standartlar ve teknoloji kurumu (NIST) ve daha fazla dahil olmak üzere Microsoft Güvenlik ekibinin engagement bu taban çizgisi önerileri arasındadır. Biz bu kuruluşlarla bizim öneriler ve taban çizgileri paylaşın. Bu kuruluşlar Microsoft'un önerileri yakından yansıtan kendi önerilerini de vardır. Mobil cihaz Yönetimi (MDM) buluta büyümeye devam ettikçe, Microsoft, bu Grup İlkesi temellerinin eşdeğer MDM öneriler oluşturmuştur. Bu ek temelleri Microsoft Intune yerleşiktir ve kullanıcıları, grupları ve temel izleyin (veya izlemeyin) cihazlar uyumluluk raporları içerir.

- Birçok müşteri Intune taban çizgisi önerileri bir başlangıç noktası olarak kullanarak ve BT karşılayacak şekilde özelleştirmek ve güvenlik talepleri. Microsoft'un Windows 10 RS5 **MDM güvenlik temeli** serbest bırakmak için ilk temel. Bu temeli, müşterileriniz sonunda CIS, NIST ve diğer standartlara dayalı diğer güvenlik temellerini içeri aktarmak genel bir altyapı olarak oluşturulmuştur. Şu anda Windows için kullanılabilir ve sonunda, iOS ve Android dahil edilir.

- Şirket içi Active Directory Grup İlkeleri ' Microsoft Intune Azure Active Directory (AD) kullanarak bir saf bulut çözümü geçiş bir yolculuktur. Yardımcı olmak için vardır Grup İlkesi Şablonları dahil [güvenlik Uyumluluk Araç Seti](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10) , hibrit AD'ye ve Azure AD'ye katılmış cihazları yönetmeye yardımcı olabilir. Bu cihazları buluttan (Intune) gelen MDM ayarları ve Grup İlkesi ayarları gerektiği gibi şirket içi etki alanı denetleyicilerinden elde edebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
- En son sürümlerini kullanılabilir temelleri ayarları görüntüleyin:  
  - [MDM güvenlik temeli](security-baseline-settings-mdm.md)  
  - [Windows Defender ATP temeli](security-baseline-settings-defender-atp.md)  

- Durum ve izleme denetimi [taban çizgisi ve profili](security-baselines-monitor.md).
