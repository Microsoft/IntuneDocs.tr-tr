---
title: Microsoft Intune-Azure 'da güvenlik temellerini kullanma | Microsoft Docs
description: Mobil cihaz yönetimi için Microsoft Intune olan cihazlarda Kullanıcı ve verileri korumak için önerilen Windows güvenlik ayarlarını kullanın. Şifrelemeyi etkinleştirin, Microsoft Defender Gelişmiş tehdit korumasını yapılandırın, Internet Explorer 'ı denetleyin, yerel güvenlik ilkelerini ayarlayın, parola gerektir, Internet indirmelerini engelleyin ve daha fazlasını yapın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04436c38fc6c4100a8232ea1ad23585f350d6aae
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75548136"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Intune 'da Windows 10 cihazlarını yapılandırmak için güvenlik temellerini kullanma

Kullanıcılarınızın ve cihazlarınızın güvenliğini sağlamanıza ve korumanıza yardımcı olması için Intune 'un güvenlik temellerini kullanın. Güvenlik temelleri, bilinen bir ayar grubunu ve ilgili güvenlik ekipleri tarafından önerilen varsayılan değerleri uygulamanıza yardımcı olan önceden yapılandırılmış Windows ayarları gruplarıdır. Intune 'da bir güvenlik temeli profili oluşturduğunuzda, birden çok *cihaz yapılandırma* profilinden oluşan bir şablon oluşturursunuz.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 sürüm 1809 ve üzeri

Güvenlik temellerini Intune 'daki Kullanıcı veya cihaz gruplarına dağıtırsınız ve ayarlar Windows 10 veya üstünü çalıştıran cihazlara uygulanır. Örneğin, *MDM güvenlik temeli* çıkarılabilir sürücüler Için BitLocker 'ı otomatik olarak sağlar, otomatik olarak bir cihazın kilidini açmak için bir parola gerektirir, temel kimlik doğrulamasını otomatik olarak devre dışı bırakır ve daha fazlasını Ortamınız için varsayılan bir değer çalışmazsa, ihtiyacınız olan ayarları uygulamak için taban çizgisini özelleştirin.

Ayrı taban çizgisi türleri aynı ayarları içerebilir, ancak bu ayarlar için farklı varsayılan değerleri kullanır. Kullanmayı seçtiğiniz temellerin varsayılan değerlerini anlamanız ve sonra her bir taban çizgisini Kuruluş gereksinimlerinize uyacak şekilde değiştirmek önemlidir.

> [!NOTE]
> Microsoft, bir üretim ortamında güvenlik temellerinin önizleme sürümlerinin kullanılmasını önermez. Önizleme temelindeki ayarlar Önizleme kursu üzerinde değişebilir.

Güvenlik temelleri, Microsoft 365 çalışırken uçtan uca güvenli bir iş akışına sahip olmanıza yardımcı olabilir. Bazı avantajları şunlardır:

- Güvenlik temeli, güvenliği etkileyen ayarlarla ilgili en iyi uygulamaları ve önerileri içerir. Intune, Grup İlkesi güvenlik temelleri oluşturan aynı Windows güvenlik ekibine sahip iş ortakları. Bu öneriler, kılavuzluk ve kapsamlı deneyimi temel alır.
- Intune 'a yeni başladıysanız ve nereden başlayabileceğiniz konusunda emin değilseniz, güvenlik temelleri size bir avantaj sunar. Kuruluşunuzun kaynaklarını ve verilerini korumaya yardımcı olduğunuzu bilerek, güvenli bir profil oluşturup dağıtabilirsiniz.
- Şu anda Grup ilkesi kullanıyorsanız, yönetim için Intune 'a geçiş bu temellerle çok daha kolay olur. Bu taban çizgileri, Intune 'da yerel olarak yerleşik olarak bulunur ve modern bir yönetim deneyimi içerir.

[Windows güvenlik temelleri](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) , bu özellik hakkında daha fazla bilgi edinmek için harika bir kaynaktır. [Mobil cihaz yönetimi](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) MDM ile ilgili harika bir kaynaktır ve Windows cihazlarında neler yapabilirsiniz.

## <a name="about-baseline-versions-and-instances"></a>Temel sürümler ve örnekler hakkında

Bir taban çizgisinin her yeni sürüm örneği, ayarları ekleyebilir veya kaldırabilir veya diğer değişiklikleri getirebilir. Örneğin, yeni Windows 10 ayarları Windows 10 ' un yeni sürümleriyle kullanılabilir hale geldiğinde, MDM güvenlik temeli en yeni ayarları içeren yeni bir sürüm örneği alabilir.

Intune konsolunda her bir taban çizgisi için kutucuk, taban çizgisi şablon adını ve bu taban çizgisi hakkındaki temel bilgileri görüntüler. Bu bilgiler, bu taban çizgisi türünü kullanan profillerin sayısını, taban çizgisi türünün kaç farklı örneğine (sürümlerini) kullanılabildiğini ve temel şablonun kiracınıza ne zaman eklendiğini belirleyen *son Yayımlanma* tarihini içerir. Aşağıdaki örnek, iyi kullanılan bir MDM güvenlik temeli için kutucuğu göstermektedir:

![Taban çizgisi kutucuğu](./media/security-baselines/baseline-tile.png)

Kullandığınız temel sürümler hakkında daha fazla bilgi görüntülemek için bir temel kutucuk seçerek *genel bakış* bölmesini açın ve ardından **sürümler**' i seçin. Intune, profilleriniz tarafından kullanılan bu taban çizgisinin sürümleriyle ilgili ayrıntıları görüntüler. Sürümler bölmesinde, bu sürümü kullanan profillerle ilgili daha derin ayrıntıları görüntülemek için tek bir sürüm seçebilirsiniz. Ayrıca, iki farklı sürüm seçebilir ve bu farklılıkları ayrıntılarıyla bir CSV dosyası indirmek için **temelleri Karşılaştır** ' ı seçebilirsiniz.

![Temelleri Karşılaştır](./media/security-baselines/compare-baselines.png)

Bir güvenlik temeli *profili*oluşturduğunuzda, profil otomatik olarak en son yayınlanan güvenlik temeli örneğini kullanır.  Önizleme sürümü kullanılarak oluşturulan taban çizgileri dahil daha önce daha önce oluşturduğunuz profilleri kullanmaya ve düzenlemeye devam edebilirsiniz.

Belirli bir profille kullanılan bir taban çizgisinin [sürümünün değiştirilmesini](#change-the-baseline-version-for-a-profile) seçebilirsiniz. Bu, yeni bir sürüm geldiğinde, bundan faydalanmak için yeni bir temel profil oluşturmanız gerekmediği anlamına gelir. Bunun yerine, hazır olduğunuzda bir temel profil seçebilir ve sonra bu profilin örnek sürümünü yeni bir profil olarak değiştirmek için yerleşik seçeneğini kullanabilirsiniz.

## <a name="available-security-baselines"></a>Kullanılabilir güvenlik temelleri

 Intune ortamınızda kullanılabilen bir veya daha fazla temeli aynı anda kullanabilirsiniz. Farklı Özelleştirmelerdeki aynı güvenlik temellerinin birden çok örneğini de kullanabilirsiniz.

Birden çok güvenlik temeli kullandığınızda, farklı temellerin aynı ayar için çakışan değerleri ne zaman tanıttığını belirlemek için her birindeki ayarları gözden geçirin. Farklı amaçlar için tasarlanan güvenlik temellerini dağıtabileceğiniz ve özelleştirilmiş ayarları içeren aynı taban çizgisinin birden çok örneğini dağıttığınız [için, araştırılması ve çözümlenmesi gereken cihazlar için yapılandırma çakışmaları](security-baselines-monitor.md#troubleshoot-using-per-setting-status)oluşturabilirsiniz.  Ayrıca, aynı ayarların birçoğunu güvenlik temellerine göre yapılandırabilen [cihaz yapılandırma profillerinizin](../configuration/device-profiles.md)farkında olun.

Aşağıdaki güvenlik temeli örnekleri Intune ile kullanılabilir. Her bir taban çizgisinin en son örneğine ilişkin ayarları görüntülemek için bağlantıları kullanın.

- **MDM güvenlik temeli**
  - [2019 Mayıs için MDM güvenlik temeli](security-baseline-settings-mdm-all.md?pivots=mdm-may-2019)
  - [Önizleme: 2018 Ekim için MDM güvenlik temeli](security-baseline-settings-mdm-all.md?pivots=mdm-preview)

- **Microsoft Defender ATP taban çizgisi**
   *(Bu temeli kullanmak Için ortamınız [Microsoft Defender Gelişmiş tehdit koruması](advanced-threat-protection.md#prerequisites)'nı kullanmaya yönelik önkoşulları karşılamalıdır)* .
  - [Microsoft Defender ATP temeli](security-baseline-settings-defender-atp.md)

  > [!NOTE]
  > Microsoft Defender ATP güvenlik temeli fiziksel cihazlar için iyileştirildi ve şu anda sanal makinelerde (VM) veya VDı uç noktalarında kullanılması önerilmez. Belirli taban çizgisi ayarları, sanallaştırılmış ortamlarda uzak etkileşimli oturumları etkileyebilir.  Daha fazla bilgi için bkz. Windows belgelerindeki [Microsoft Defender ATP güvenlik temeliyle uyumluluğu artırma](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) .

- **Microsoft Edge taban çizgisi**
  - [Önizleme: Microsoft Edge taban çizgisi](security-baseline-settings-edge.md)

Önizleme şablonu yeni profiller oluşturmak için artık kullanılabilir olmadığında bile, daha önce bir önizleme şablonunu temel alarak oluşturduğunuz profilleri kullanmaya ve düzenlemeye devam edebilirsiniz.

## <a name="manage-baselines"></a>Temelleri yönetme

Güvenlik temellerinde çalışırken ortak görevler şunları içerir:

- [Profil oluşturma](#create-the-profile) – kullanmak istediğiniz ayarları yapılandırın ve taban çizgisini gruplara atayın.
- [Sürümü değiştirme](#change-the-baseline-version-for-a-profile) – bir profil tarafından kullanılan temel sürümü değiştirin.
- [Taban çizgisi atamasını kaldırma](#remove-a-security-baseline-assignment) -ayarları güvenlik temeliyle yönetmeyi durdurduğunuzda ne olacağını öğrenin.


### <a name="prerequisites"></a>Prerequisites

- Intune 'da temelleri yönetmek için hesabınızın [ilke ve Profil Yöneticisi](../fundamentals/role-based-access-control.md#built-in-roles) yerleşik rolüne sahip olması gerekir.

- Bazı temellerin kullanımı, Microsoft Defender ATP gibi ek hizmetlere etkin bir aboneliğinizin olmasını gerektirebilir.

### <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. Kullanılabilir temeller listesini görüntülemek için **uç nokta güvenliği** > **güvenlik temellerini** seçin.

   ![Yapılandırmak için bir güvenlik temeli seçin](./media/security-baselines/available-baselines.png)

3. Kullanmak istediğiniz taban çizgisini seçin ve ardından **Profil oluştur**' u seçin.

4. **Temel bilgiler** sekmesinde, aşağıdaki özellikleri belirtin:

   - **Ad**: güvenlik temelleri profiliniz için bir ad girin. Örneğin, *Defender ATP Için standart profil*girin.

   - **Açıklama**: Bu temelin ne yaptığını açıklayan bir metin girin. Açıklama, istediğiniz herhangi bir metin girmenize yöneliktir. İsteğe bağlıdır, ancak önerilir.

   Sonraki sekmeye gitmek için **İleri ' yi** seçin. Yeni bir sekmeye gelişmiş bir sekmeye kadar, daha önce görüntülenen bir sekmeye geri dönmek için sekme adını seçebilirsiniz.

5. Yapılandırma ayarları sekmesinde, seçtiğiniz taban çizgisinde kullanılabilir olan **ayar** gruplarını görüntüleyin. Bu gruptaki ayarları görüntülemek için bir grubu genişletebilir ve bu ayarlar için taban çizgisinde varsayılan değerleri kullanabilirsiniz. Belirli ayarları bulmak için:
   - Genişletilecek bir grup seçin ve kullanılabilir ayarları gözden geçirin.
   - *Arama* çubuğunu kullanın ve yalnızca arama ölçütlerinizi içeren grupları görüntülemek için görünümü filtreleyen anahtar sözcükleri belirtin.

   Bir taban çizgisinin her bir ayarı, bu temel sürüm için varsayılan bir yapılandırmaya sahiptir. Varsayılan ayarları, iş gereksinimlerinizi karşılayacak şekilde yeniden yapılandırın. Farklı temeller aynı ayarı içerebilir ve taban çizgisinin amacına bağlı olarak ayar için farklı varsayılan değerleri kullanır.

   ![Bu grubun ayarlarını görüntülemek için bir grubu genişletin](./media/security-baselines/sample-list-of-settings.png)

6. **Kapsam Etiketleri sekmesini seçin** ' i seçerek kapsam etiketlerini profile atamak için kapsam *etiketleri Seç '* **i seçin.**

7. **Atamalar** sekmesinde, **dahil edilecek grupları seç** ' i seçin ve ardından temeli bir veya daha fazla gruba atayın. Atamanın ince ayar yapmak için, **hariç tutulacak grupları seçin ' i** kullanın.

   ![Profil atama](./media/security-baselines/assignments.png)

8. Temeli dağıtmaya hazırsanız, **gözden geçir + oluştur** sekmesine ilerleyin ve taban çizgisinin ayrıntılarını gözden geçirin. Profili kaydetmek ve dağıtmak için **Oluştur** ' u seçin.

   Profili oluşturur almaz, atanan gruba gönderilir ve hemen uygulanabilir.

   > [!TIP]
   > Bir profili önce gruplara atamadan kaydederseniz, daha sonra profili düzenleyerek bunu yapabilirsiniz.

   ![Taban çizgisini gözden geçirme](./media/security-baselines/review.png)

9. Bir profil oluşturduktan sonra **cihaz güvenliği** > **güvenlik temelleri**' ne giderek düzenleyin, yapılandırdığınız taban çizgisi türünü seçin ve ardından **profiller**' i seçin. Kullanılabilir profiller listesinden profili seçin ve ardından **Özellikler**' i seçin. Tüm kullanılabilir yapılandırma sekmelerinden ayarları düzenleyebilir ve değişikliklerinizi uygulamak için **gözden geçir + kaydet** ' i seçebilirsiniz.

### <a name="change-the-baseline-version-for-a-profile"></a>Bir profilin temel sürümünü değiştirme

Kullanılan temel örnek sürümünü bir profille değiştirebilirsiniz.  Sürümü değiştirdiğinizde, aynı taban çizgisinin kullanılabilir bir örneğini seçersiniz. Bir profili, MDM güvenlik temelini kullanarak Defender ATP için bir taban çizgisi kullanarak değiştirme gibi iki farklı taban çizgisi türü arasında geçiş yapamazsınız.

Taban çizgisi sürümünün bir değişikliğini yapılandırırken, dahil edilen iki temel sürüm arasındaki değişiklikleri listeleyen bir CSV dosyası indirebilirsiniz. Tüm özelleştirmelerinizi özgün temel sürümden tutma veya yeni sürümü varsayılan değerlerini kullanarak uygulama seçeneğiniz de vardır. Bir profil için bir taban çizgisinin sürümünü değiştirdiğinizde tek tek ayarlarda değişiklik yapma seçeneğiniz yoktur.

Kaydetme sırasında, dönüştürme işlemi tamamlandıktan sonra, taban çizgisi atanan gruplara hemen yeniden dağıtılır.

**Dönüştürme sırasında**:

- Kullanmakta olduğunuz Orijinal sürümde olmayan yeni ayarlar eklendi ve varsayılan değerleri kullanacak şekilde ayarlandı.

- Seçtiğiniz yeni temel sürümde olmayan ayarlar kaldırılır ve artık bu güvenlik temeli profili tarafından zorlanmaz.

  Bir ayar artık temel bir profil tarafından yönetilmediğinde, bu ayar cihazda sıfırlanmaz. Bunun yerine, başka bir işlem değişiklik ayarlarını yönetene kadar cihazdaki ayar en son yapılandırmaya ayarlanır. Yönetimi durdurduktan sonra bir ayarı değiştirebiliyor işlem örnekleri, farklı bir temel profil, bir Grup İlkesi ayarı veya cihazda yapılan el ile yapılandırma içerir.

#### <a name="to-change-the-baseline-version-for-a-profile"></a>Bir profilin temel sürümünü değiştirmek için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın. 

2. **Uç nokta güvenliği** > **güvenlik temelleri**' ni seçin ve ardından değiştirmek istediğiniz profilin bulunduğu temel türün kutucuğunu seçin.

3. Ardından, **profiller**' i seçin ve ardından düzenlemek istediğiniz profilin onay kutusunu seçin ve ardından **sürümü Değiştir**' i seçin.

   ![taban çizgisi seçin](./media/security-baselines/select-baseline.png)

4. **Sürümü Değiştir** bölmesinde, açılan menüyü **güncelleştirmek için bir güvenlik temeli Seç** ' i kullanın ve kullanmak istediğiniz sürüm örneğini seçin.

   ![Sürüm seçin](./media/security-baselines/select-instance.png)

5. Profiller geçerli örnek sürümü ve seçtiğiniz yeni sürüm arasındaki farkı gösteren bir CSV dosyası indirmek için **güncelleştirmeyi gözden geçir** ' i seçin. Hangi ayarların yeni veya kaldırılmış olduğunu ve bu ayarların varsayılan değerlerinin güncelleştirilmiş profilde ne olduğunu anlamak için bu dosyayı gözden geçirin.

   Hazırsanız, bir sonraki adımla devam edin.

6. **Profili güncelleştirmek için bir yöntem seçmek üzere**iki seçenekten birini belirleyin:
   - **Temel değişiklikleri kabul et ancak var olan ayar özelleştirmelerini tut** -Bu seçenek, taban çizgisi profilinde yaptığınız özelleştirmeleri korur ve bunları kullanmak üzere seçtiğiniz yeni sürüme uygular.
   - **Temel değişiklikleri kabul et ve var olan ayar özelleştirmelerini at** -Bu seçenek özgün profilinizi tamamen geçersiz kılar. Güncelleştirilmiş profil tüm ayarlar için varsayılan değerleri kullanır.

7. Seçin **gönderme**. Profil, seçili temel sürüme ve dönüştürme tamamlandıktan sonra güncelleştirilir ve taban çizgisi atanan gruplara hemen yeniden dağıtılır.

### <a name="remove-a-security-baseline-assignment"></a>Güvenlik temeli atamasını kaldırma

Bir güvenlik temeli ayarı bir cihaz için artık geçerli olmadığında veya bir taban çizgisinin ayarları *Yapılandırılmadı*olarak ayarlandığında, bir cihazdaki bu ayarlar önceden yönetilen bir yapılandırmaya dönmez. Bunun yerine, daha önce yönetilen ayarlar, bazı diğer işlemler cihazdaki bu ayarları güncelleştirene kadar son yapılandırmalarının taban çizgisinden alınmış olarak tutulmasını saklar.

Daha sonra cihazdaki ayarları değiştirebilecek diğer işlemlere, farklı veya yeni bir güvenlik taban çizgisi, cihaz yapılandırma profili, grup ilkesi yapılandırmaları veya cihazdaki ayarı el ile düzenleme sayılabilir.

## <a name="co-managed-devices"></a>Ortak yönetilen cihazlar

Intune tarafından yönetilen cihazlarda güvenlik temelleri, Configuration Manager ile birlikte yönetilen cihazlara benzerdir. Ortak yönetilen cihazlar Windows 10 cihazlarını eşzamanlı olarak yönetmek için Configuration Manager ve Microsoft Intune kullanır. Mevcut Configuration Manager yatırımınızın Intune avantajlarından faydalanmasına olanak tanır. [Ortak yönetime genel bakış](https://docs.microsoft.com/configmgr/comanage/overview) , Configuration Manager kullanırsanız ve ayrıca bulutun avantajlarından yararlanmak istiyorsanız harika bir kaynaktır.

Ortak yönetilen cihazlar kullanılırken **cihaz yapılandırma** iş yükünü (ayarlarını) Intune 'a geçmeniz gerekir. [Cihaz yapılandırma iş yükleri](https://docs.microsoft.com/configmgr/comanage/workloads#device-configuration) daha fazla bilgi sağlar.

## <a name="q--a"></a>Soru ve Cevap

### <a name="why-these-settings"></a>Bu ayarlar neden?

Microsoft Güvenlik ekibinin, bu önerileri oluşturmak için Windows geliştiricileriyle ve güvenlik topluluğuyla doğrudan çalışma deneyimi vardır. Bu taban çizgisinin ayarları, güvenlikle ilgili en ilgili yapılandırma seçenekleri olarak değerlendirilir. Her yeni Windows derlemesinde, takım önerilerini yeni yayınlanan özelliklere göre ayarlar.

### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Grup İlkesi ve Intune için Windows güvenlik temelleri önerilerinde bir farklılık var mı?

Aynı Microsoft Güvenlik ekibinin her bir taban çizgisi için ayarları seçtiği ve düzenleyen aynı. Intune, Intune güvenlik temelindeki tüm ilgili ayarları içerir. Grup İlkesi taban çizgisinde, şirket içi etki alanı denetleyicisine özgü bazı ayarlar vardır. Bu ayarlar Intune 'un önerilerinden çıkarılır. Diğer tüm ayarlar aynıdır.

### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Intune güvenlik temelleri CIS veya NSıT uyumlu mı?

Kesinlikle konuşuyor, hayır. Microsoft Güvenlik ekibi, bu kuruluşların önerilerini derlemek için CIS gibi danışmanları sağlar. Ancak, "CIS uyumlu" ve Microsoft taban çizgileri arasında bire bir eşleme yoktur.

### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Microsoft 'un güvenlik temelleri hangi sertifikaları kullanıyor? 

- Microsoft, birçok yıla sahip olduğu için Grup ilkeleri (GPO 'Lar) ve [Güvenlik uyumluluk araç seti](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10)için güvenlik temellerini yayımlamaya devam etmektedir. Bu taban çizgileri birçok kuruluş tarafından kullanılır. Bu temellerin önerileri, Microsoft Güvenlik ekibinin, Savunma Bakanlığı (DoD), ulusal standartlar ve Teknoloji Enstitüsü (NıST) ve daha fazlası dahil olmak üzere kurumsal müşteriler ve dış kurumlarla olan katılımından oluşur. Önerilerimizi ve temellerimizi bu kuruluşlarla paylaşıyoruz. Bu kuruluşların, Microsoft 'un önerilerini yakından yansıtan kendi önerileri de vardır. Mobil cihaz yönetimi (MDM) buluta büyümeye devam ettiğinden, Microsoft bu Grup İlkesi temellerinin eşdeğer MDM önerilerini oluşturmuştur. Bu ek taban çizgileri Microsoft Intune için yerleşiktir ve taban çizgisini izleyen (veya takip etmeyin) kullanıcılara, gruplara ve cihazlara uyumluluk raporları dahil edilir.

- Birçok müşteri, Intune temel önerilerini başlangıç noktası olarak kullanıyor ve ardından BT ve güvenlik taleplerini karşılayacak şekilde özelleştiriliyor. Microsoft 'un Windows 10 RS5 **MDM güvenlik temeli** , yayınlanacak ilk temeldir. Bu taban çizgisi, müşterilerin, en sonunda CIS, NıST ve diğer standartlara dayalı diğer güvenlik temellerini içeri aktarmasını sağlayan bir genel altyapı olarak oluşturulmuştur. Şu anda Windows için kullanılabilir ve sonunda iOS ve Android de bulunur.

- Şirket içi Active Directory Grup ilkelerinden Microsoft Intune ile Azure Active Directory (AD) kullanan saf bir bulut çözümüne geçiş bir yolculuğa sahip olur. Yardım için, karma AD ve Azure AD 'ye katılmış cihazları yönetmeye yardımcı olabilecek [Güvenlik uyumluluğu araç seti](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10) 'ne dahil edilen grup ilkesi şablonları vardır. Bu cihazlar, bulut (Intune) ve Grup İlkesi ayarlarından, gerektiğinde şirket içi etki alanı denetleyicilerinden MDM ayarları alabilir.

## <a name="next-steps"></a>Sonraki adımlar

- Kullanılabilir temellerin en son sürümlerindeki ayarları görüntüleyin:
  - [MDM güvenlik temeli](security-baseline-settings-mdm-all.md)
  - [Microsoft Defender ATP temeli](security-baseline-settings-defender-atp.md)

- Durumu denetleme ve [temeli ve profili](security-baselines-monitor.md) izleme
