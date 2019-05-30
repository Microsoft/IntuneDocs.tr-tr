---
title: Microsoft Intune - Azure güvenlik temellerini kullanın | Microsoft Docs
description: Ekleyebilir veya kullanıcı ve mobil cihaz yönetimi için Microsoft Intune kullanarak cihazlardaki verileri korumak için önerilen grubu güvenlik ayarlarını yapılandırın. BitLocker'ı etkinleştirmek, Microsoft Defender Gelişmiş tehdit koruması yapılandırma, Internet Explorer denetim, Smart Screen kullanan, yerel güvenlik ilkelerini ayarlama, parola iste, Internet karşıdan yüklemeler ve daha fazlasını engelleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e4d5c23d598641256c196cd7217797f87f99d1c
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374126"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Intune'da Windows 10 Güvenlik taban çizgisi oluşturma

Güvenlik temellerini üzeri ve Windows 10 çalıştıran cihazlar için kullanılabilir bir önizleme özelliğidir. Bu özellik, kullanıcı ve cihazları koruyun ve güvenliğini sağlamaya yardımcı olmak için kullanabileceğiniz Intune tarafından desteklenen çok sayıda ayarları içerir. Güvenlik ekipleri tarafından önerilen değerleri için bu ayarları da otomatik olarak ayarlar. Örneğin, taban çizgisi BitLocker'ı otomatik olarak etkinleştirir, otomatik olarak bir cihazın kilidini açmak için parola gerektirir, otomatik olarak ve temel kimlik doğrulaması devre dışı bırakır.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 sürüm 1809 ve üzeri

> [!NOTE]
> Önizleme'de güvenlik temellerini olsa da Microsoft profilleri bir üretim ortamında, temel kullanarak, Önizleme boyunca değişebilir önerilir değil. Güvenlik temellerini genel kullanıma sunulmuştur, var olan profilleri için desteklenen en son profilleri dönüştürmez.

Güvenlik temellerini kullanma amacıyla bir uçtan uca güvenli iş akışını Microsoft 365 ile çalışırken sağlamaktır. Bazı avantajları şunlardır:

- Güvenlik temeli, en iyi yöntemler ve öneriler etkileyen güvenlik ayarlarını içerir. Grup İlkesi, güvenlik temellerini oluşturur Windows Güvenlik Ekibi ile Intune iş ortakları. Bu önerileri kılavuz ve kapsamlı deneyimi temel alır.
- Nereden başlayacağınızı ıntune'a yeni ve emin değil, ardından güvenlik temellerini size avantajlı. Hızlı bir şekilde oluşturabilir ve kuruluşunuzun kaynakları ve veri korumaya yardımcı oluyoruz bilmek bir güvenlik profili dağıtın.
- Şu anda Grup İlkesi kullanırsanız, Yönetim için Intune'a geçiş ile bu taban çizgisi çok daha kolaydır. Bu temelleri yerel olarak Intune'da yerleşiktir ve modern yönetim deneyimi içerir.

Güvenlik temelleri "yapılandırma profili" Intune oluşturma. Bu profili, tüm ayarlarını temelde içerir. Daha sonra uygulayın veya bu profil için kullanıcılar, gruplara ve cihazlara atayın.

Profil atadıktan sonra profili izleme ve temel izleyin. Örneğin, hangi aygıtların temel eşleşmiyor veya temel eşleşmeyen görebilirsiniz.

Bu makalede, profil oluşturma, profil atama ve izleme profili için güvenlik temellerini kullanmanıza yardımcı olabilir.

[Windows güvenlik temellerini](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) bu özellik hakkında daha fazla bilgi için harika bir kaynaktır. [Mobil cihaz Yönetimi](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) olan MDM ve Windows cihazlarda neler yapabileceğiniz hakkında harika bir kaynak.

## <a name="available-security-baselines"></a>Kullanılabilir güvenlik temelleri  

Aşağıdaki güvenlik temelleri Intune ile kullanılabilir.
- **Önizleme: Ekim 2018 için MDM güvenlik temeli**  
  [Ayarları görüntüleyin](security-baseline-settings-windows.md)

- **ÖNİZLEME: Windows Defender ATP temeli**  
  [Ayarları görüntüleyin](security-baseline-settings-defender-atp.md)  
  *(Ortamınız kullanmak için önkoşulları karşıladığı durumlarda bu temel kullanılabilir [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites))* .


## <a name="prerequisites"></a>Önkoşullar
Intune'da temellerini yönetmek için hesabınızın olması gerekir [ilke ve Profil Yöneticisi](role-based-access-control.md#built-in-roles) yerleşik rolü.


## <a name="co-managed-devices"></a>Ortak yönetilen cihazlar

Intune tarafından yönetilen cihazların temel güvenlik özelliklerinizin ortak yönetilen cihazlar Configuration Manager ile benzerdir. Ortak yönetilen cihazların, aynı anda Windows 10 cihazları yönetmek için System Center Configuration Manager ve Microsoft Intune kullanın. Mevcut Configuration Manager yatırımınızı avantajlara ıntune bulut ekleme olanak tanır. [Ortak yönetim genel bakış](https://docs.microsoft.com/sccm/comanage/overview) Yapılandırma Yöneticisi'ni, ve ayrıca bulutun avantajlarından istiyorsanız harika bir kaynaktır.

Ortak yönetilen cihazların kullanırken geçmelidir **cihaz Yapılandırması** Intune iş yüküne (ayarlarına). [Cihaz yapılandırması iş yükleri](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) daha fazla bilgi sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=20909) seçip **cihaz güvenliği** > **güvenlik temellerini (Önizleme)** . Kullanılabilir temelleri listesi kullanılabilir. 

    ![Yapılandırmak için bir güvenlik taban çizgisi seçin](./media/security-baselines/available-baselines.png)

   >[!TIP]  
   > Windows Defender ATP temel ortamınızı kullanmak için önkoşulları karşıladığı durumlarda kullanılabilir [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites).
2. Kullanın ve ardından istediğiniz taban çizgisini seçin **profili oluşturma**.  

3. Üzerinde **Temelleri** sekmesinde, aşağıdaki özellikleri belirtin:

    - **Ad**: Güvenlik temelleri profiliniz için bir ad girin. Örneğin, *Defender ATP için standart profili*
    - **Açıklama**: Bu temel ne yaptığını açıklayan metin girin. Açıklama girin, istediğiniz herhangi bir metin için bağlıdır. Bu, isteğe bağlı, ancak kesinlikle önerilir.

4. Seçin **yapılandırma** kullanılabilir gruplarını görüntülemek için sekmesinde **ayarları** bu temelindeki. Genişletin ve içerdiği tek ayarlarını görüntülemek için bir grubu seçin. Ayarları, güvenlik temeli için varsayılan yapılandırmaları vardır. İş ihtiyaçlarınızı karşılamak için varsayılan ayarları yeniden yapılandırın.  

    ![Bu grubun ayarlarını görüntülemek için bir grubu genişletin](./media/security-baselines/sample-list-of-settings.png)

5. Seçin **atamaları** temel gruplarına atamak için sekmesinde. Taban çizgisini varolan bir gruba atayın veya yapılandırmayı tamamlamak için Intune konsolunda standart işlemini kullanarak yeni bir grup oluşturun.  

   ![Profil atama](./media/security-baselines/assignments.png)
  
6. Taban çizgisi dağıtmaya hazır olduğunuzda seçin **gözden + Oluştur** temel ayrıntılarını gözden geçirmek için sekmesinde. Ardından seçin **profili Kaydet** kaydetme ve profili dağıtın. 

   ![Taban çizgisi gözden geçirin](./media/security-baselines/review.png) 

   Kaydettiğiniz hemen sonra Intune ile iade gönderilirken profili cihazlara gönderilir. Bu nedenle, bunu hemen oluşabilir.

   > [!TIP]  
   > İlk gruplarına atayarak olmadan, bir profil kaydedebilirsiniz. Profil gruplar eklemek için daha sonraki bir zamanda düzenleyebilirsiniz. 

7. Profil oluşturduktan sonra şuraya giderek düzenleyebilirsiniz **cihaz güvenliği** > **güvenlik temellerini**, yapılandırılmış ve ardından taban çizgisini seçin **profilleri**.  Profili seçin ve ardından **özellikleri** ayarları düzenleyin ve **atamaları** bu temel alan gruplarını düzenlemek için. 

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

- Şirket içi Active Directory Grup İlkeleri ' Microsoft Intune Azure Active Directory (AD) kullanarak bir saf bulut çözümü geçiş bir yolculuktur. Yardımcı olmak için GPO'ları hibrit AD'ye ve Azure AD'ye katılmış cihazlar için yayımlanan Yardımcısı vardır. Bu cihazları buluttan (Intune) gelen MDM ayarları ve Grup İlkesi ayarları gerektiği gibi şirket içi etki alanı denetleyicilerinden elde edebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
- Görünüm [Windows Güvenlik taban çizgisi ayarlarını](security-baseline-settings-windows.md) Intune tarafından desteklenen.  
- Durum ve izleme denetimi [taban çizgisi ve profili](security-baselines-monitor.md).
