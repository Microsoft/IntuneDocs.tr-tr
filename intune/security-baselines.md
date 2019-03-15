---
title: Microsoft Intune - Azure güvenlik temellerini kullanın | Microsoft Docs
description: Ekleyebilir veya kullanıcı ve mobil cihaz yönetimi için Microsoft Intune kullanarak cihazlardaki verileri korumak için önerilen grubu güvenlik ayarlarını yapılandırın. BitLocker'ı etkinleştirmek, Windows Defender Gelişmiş tehdit koruması yapılandırma, Internet Explorer denetim, Smart Screen kullanan, yerel güvenlik ilkelerini ayarlama, parola iste, Internet karşıdan yüklemeler ve daha fazlasını engelleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/01/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94fbd4b4f73dd24f83832af010a6350ae8a0aa25
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394666"
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

Bu makalede güvenlik temellerini profil oluşturma, profil atama ve profil izlemek için nasıl kullanılacağı gösterilmektedir.

[Windows güvenlik temellerini](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) bu özellik hakkında daha fazla bilgi için harika bir kaynaktır. [Mobil cihaz Yönetimi](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) olan MDM ve Windows cihazlarda neler yapabileceğiniz hakkında harika bir kaynak.

## <a name="co-managed-devices"></a>Ortak yönetilen cihazlar

Intune tarafından yönetilen cihazların temel güvenlik özelliklerinizin ortak yönetilen cihazlar Configuration Manager ile benzerdir. Ortak yönetilen cihazların, aynı anda Windows 10 cihazları yönetmek için System Center Configuration Manager ve Microsoft Intune kullanın. Mevcut Configuration Manager yatırımınızı avantajlara ıntune bulut ekleme olanak tanır. [Ortak yönetim genel bakış](https://docs.microsoft.com/sccm/comanage/overview) Yapılandırma Yöneticisi'ni, ve ayrıca bulutun avantajlarından istiyorsanız harika bir kaynaktır.

Ortak yönetilen cihazların kullanırken geçmelidir **cihaz Yapılandırması** Intune iş yüküne (ayarlarına). [Cihaz yapılandırması iş yükleri](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) daha fazla bilgi sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com/)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. Seçin **güvenlik temellerini (Önizleme)**. Kullanılabilir temelleri listesi kullanılabilir. Daha fazla temelleri eklendikçe bunları burada görürsünüz:

    ![Intune şu anda kullanılabilir güvenlik temelleri bakın](./media/security-baselines/available-baselines.png)

3. Kullanmak istediğiniz taban çizgisini seçin > **profili oluşturma**.
4. İçinde **Temelleri**, aşağıdaki özellikleri girin:

    - **Ad**: Güvenlik temelleri profiliniz için bir ad girin. Örneğin, şunu girin: `pilot Windows 10 MDM baseline - Oct 2018`.
    - **Açıklama**: Bu temel ne yaptığını açıklayan metin girin. Açıklama girin, istediğiniz herhangi bir metin için bağlıdır. Bu, isteğe bağlı, ancak kesinlikle önerilir.

5. Genişletin **ayarları**. Listede, bu güvenlik temeli ve ne otomatik olarak ayar tüm ayarlar bakın. Ayarları ve değerleri önerilir ve sizin tarafınızdan değiştirilebilir.

    ![Ayarı, bu güvenlik temeli ıntune'da tüm ayarları görmek için genişletin](./media/security-baselines/sample-list-of-settings.png)

    Bazı ayarlar değerleri denetlemek için genişletin. Örneğin, genişletme **Windows Defender**. Bazı ayarlar ve ne oldukları şey dikkat edin:

    ![Hangi ayarları Intune ile otomatik olarak ayarlanan Windows Defender'ın bazı bakın](./media/security-baselines/expand-windows-defender.png)

6. **Oluşturma** profili. 
7. Seçin **profilleri**. Profilinizi oluşturulur ve listede gösterilen. Ancak, herhangi bir şey henüz yapmıyor. Ardından, profil atayın.

## <a name="assign-the-profile"></a>Profil atama

Profil oluşturulduktan sonra kullanıcılar, cihazlar ve gruplar için atanmak üzere hazırdır. Kendilerine atandıktan sonra profil ve ayarları kullanıcıları, cihazları ve seçtiğiniz grupları için uygulanır.

1. Intune'da seçin **güvenlik temellerini** > bir temel seçin > **profilleri**.
2. Profilinizi seçin > **atamaları**.

    ![Intune'da güvenlik temel profilinizi seçin ve profilini dağıtmak için atamalar'a tıklayın](./media/security-baselines/assignments.png)

3. İçinde **INCLUDE** sekmesinde, kullanıcıları, grupları ekleyin veya cihazlar bu ilkenin uygulanmasını istediğiniz.

    > [!TIP]
    > Ayrıca uyarı **hariç** grupları. Bir ilkeyi uygularsanız **tüm kullanıcılar**, yönetici gruplarından dışlamayı göz önünde bulundurun. Bir şey olması durumunda, siz ve yöneticileriniz kilitli istemiyorum.

4. Yaptığınız değişiklikleri **kaydedin**.

Kaydettiğiniz hemen sonra Intune ile iade gönderilirken profili cihazlara gönderilir. Bu nedenle, bunu hemen oluşabilir.

## <a name="available-security-baselines"></a>Kullanılabilir güvenlik temelleri  

Aşağıdaki güvenlik temelleri, Intune ile kullanmak için kullanılabilir olan.
- **Önizleme: MDM güvenlik temeli**
  - Sürüm: [Ekim 2018](security-baseline-settings-windows.md)

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
