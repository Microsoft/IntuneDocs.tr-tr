---
title: Microsoft Intune - Azure’da İş İçin Windows Update’i yapılandırma | Microsoft Docs
description: Windows 10 yazılım güncelleştirmelerini güncelleştirme halkalarını ve özellik güncelleştirmeleri ilkesini kullanarak yönetin. Uyumluluk ' i gözden geçirebilir ve Microsoft Intune kullanarak güncelleştirme yüklemesini Windows Update Iş ayarları ile duraklatabilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/14/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc9dd03714e24dae4b0c7afe9206c6a8d7d36c13
ms.sourcegitcommit: de663ef5f3e82e0d983899082a7f5b62c63f24ef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75956280"
---
# <a name="manage-windows-10-software-updates-in-intune"></a>Intune 'da Windows 10 yazılım güncelleştirmelerini yönetme

Windows Update for Business 'dan Windows 10 yazılım güncelleştirmelerinin yüklenmesini yönetmek için Intune 'U kullanın.

İş İçin Windows Update kullanarak güncelleştirme yönetimi deneyimini basitleştirirsiniz. Cihaz grupları için ayrı ayrı güncelleştirmeleri onaylamanız gerekmez. Bir güncelleştirmeyi piyasaya sunma stratejisi yapılandırarak ortamlarınızda riskleri yönetebilirsiniz. Intune, cihazlarda [güncelleştirme ayarlarını yapılandırma](windows-update-settings.md) ve güncelleştirme yüklemesini erteleme olanağı sağlar. Ayrıca, cihazların sürekli tutmaya yardımcı olmak için yeni Windows sürümlerinden Özellikler yüklemesini de engelleyebilirsiniz, bu da cihazların kalite ve güvenlik için güncelleştirmeleri yüklemeye devam etmesine izin verir.

Intune, güncelleştirmelerin kendileri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir.

Intune, güncelleştirmeleri yönetmek için aşağıdaki ilke türlerini sağlar:

- **Windows 10 güncelleştirme halkası**: Bu Ilke, Windows 10 güncelleştirmelerinin yüklendiği zaman yapılandıran ayarların bir koleksiyonudur.

- **Windows 10 özellik güncelleştirmeleri (Genel Önizleme)** : Bu ilke, cihazları belirttiğiniz Windows sürümüne getirir ve bunları daha sonraki bir Windows sürümü ile güncelleştirmeyi seçinceye kadar bu cihazlarda dondurur.  Özellik sürümü statik olmaya devam ederken, cihazlar Özellik sürümleri için kullanılabilen kalite ve güvenlik güncelleştirmelerini yüklemeye devam edebilir.

Cihaz gruplarına Windows 10 güncelleştirme halkaları ve Windows 10 özellik güncelleştirmeleri için ilkeler atarsınız. Windows 10 cihazlarınız için yazılım güncelleştirmelerini yönetmek ve iş gereksinimlerinizi yansıtan bir güncelleştirme stratejisi oluşturmak için aynı Intune ortamında her iki ilke türünü de kullanabilirsiniz.

Daha fazla bilgi için bkz. [İşletmeler için Windows Update'i kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="prerequisites"></a>Prerequisites

Intune 'da Windows 10 cihazları için Windows güncelleştirmelerini kullanmak üzere aşağıdaki önkoşulların karşılanması gerekir.

- Windows 10 bilgisayarları aşağıdaki Windows 10 sürümlerini çalıştırmalıdır:
  - **Windows 10 güncelleştirme halkaları**: sürüm 1607 veya üzeri
  - **Windows 10 özellik güncelleştirmeleri**: sürüm 1703 veya üzeri

- Windows Update aşağıdaki Windows 10 sürümlerini destekler:
  - Windows 10
  - Windows 10 Team-Surface Hub cihazları için ( *Windows 10 özellik güncelleştirmelerini*desteklemez)
  - Windows 10 Holographic for Business

    Windows holographic for Business, aşağıdakiler dahil olmak üzere Windows güncelleştirmeleri için bir ayar alt kümesini destekler:
    - **Otomatik güncelleştirme davranışı**
    - **Microsoft ürün güncelleştirmeleri**
    - **Bakım kanalı**: **yarı yıllık kanal** ve **yarı yıllık kanal (hedeflenen)** seçeneklerini destekler. Daha fazla bilgi için bkz. [Windows holographic 'ı yönetme](../fundamentals/windows-holographic-for-business.md).

  > [!NOTE]
  > **Desteklenmeyen sürümler ve sürümler**:
  > - Windows 10 Mobile  
  > - Windows 10 Enterprise LTSC. Windows Update for Business (WUfB) Şu anda *uzun süreli hizmet kanalı* sürümlerini desteklememektedir. WSUS veya Configuration Manager gibi alternatif düzeltme eki uygulama yöntemlerini kullanmayı planlayın.

- Windows cihazlarında **geri bildirim & tanılama** > **Tanılama ve kullanım verileri** **temel**, **Gelişmiş**veya **tam**olarak ayarlanmalıdır.

  Windows 10 cihazları için *Tanılama ve kullanım verileri* ayarını el ile yapılandırabilir veya Windows 10 ve üzeri Için bir Intune cihaz kısıtlama profili kullanabilirsiniz. Bir cihaz kısıtlama profili kullanıyorsanız, **kullanım verilerini paylaşma** [cihaz kısıtlama ayarını](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) en az **temel**olarak ayarlayın. Bu ayar, Windows 10 veya üzeri için bir cihaz kısıtlama ilkesi yapılandırdığınızda **Raporlama ve telemetri** kategorisi altında bulunur.

  Cihaz profilleri hakkında daha fazla bilgi için bkz. [cihaz kısıtlama ayarlarını yapılandırma](../configuration/device-restrictions-configure.md).

## <a name="windows-10-update-rings"></a>Windows 10 güncelleştirme halkaları

Windows 10 cihazlarınızı özellik ve kalite güncelleştirmeleriyle nasıl ve ne zaman güncelleştirmelerini belirten güncelleştirme halkaları oluşturun. Windows 10 ile yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri kapsar. En son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

Windows 10 güncelleştirme halkaları [kapsam etiketlerini](../fundamentals/scope-tags.md)destekler. Kullandığınız yapılandırmaların kümelerini filtrelemenize ve yönetmenize yardımcı olması için kapsam etiketlerini güncelleştirme halkalarıyla birlikte kullanabilirsiniz.

### <a name="create-and-assign-update-rings"></a>Güncelleştirme halkaları oluşturma ve atama

1. [Microsoft Endpoint Manager Yönetim merkezinde]( https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Windows > Windows** **10 güncelleştirme halkalarını** > **cihazları** seçin > **Oluştur**.

3. *Temel bilgiler*altında bir ad, açıklama (isteğe bağlı) belirtin ve ardından **İleri**' yi seçin.
  ![bir güncelleştirme halkası oluşturun]( ./media/windows-update-for-business-configure/basics-tab.png)
  
4. **Güncelleştirme halkası ayarları**altında, iş gereksinimlerinize göre ayarları yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. Windows Update ayarları. *Güncelleştirme ve Kullanıcı deneyimi* ayarlarını yapılandırdıktan sonra **İleri**' yi seçin.

5. **Kapsam etiketleri**altında **+ kapsam etiketlerini Seç** ' i seçerek bunları güncelleştirme halkalarına uygulamak istiyorsanız *etiketleri Seç* bölmesini açın. Bir veya daha fazla etiket seçin ve ardından **Seç** ' e tıklayarak güncelleştirme halkasını ekleyin ve *kapsam etiketi*s sayfasına dönün.

   Hazırlandığınızda, *atamalara*devam etmek için **İleri** ' yi seçin.

6. **Atamalar**' ın altında **+ dahil edilecek grupları seçin** ve ardından güncelleştirme halkasını bir veya daha fazla gruba atayın. Atamanın ince ayar yapmak için **+ Select grupları** kullanın. Devam etmek için **İleri** seçeneğini belirleyin.

7. **Gözden geçir + oluştur**bölümünde ayarları gözden geçirin ve ardından Windows 10 güncelleştirme halkasını kaydetmeye hazırsanız **Oluştur** ' u seçin. Yeni güncelleştirme halkalarınız, güncelleştirme halkaları listesinde görüntülenir.

### <a name="manage-your-windows-10-update-rings"></a>Windows 10 güncelleştirme Halkalarınızı yönetin

Portalda, **windows** > **Windows 10 güncelleştirme halkaları** > **cihazlar** ' a gidin ve yönetmek istediğiniz ilkeyi seçin.  İlke, **genel bakış** sayfasında açılır.

Bu sayfadan, halkalar atama durumunu görüntüleyebilir ve güncelleştirme halkasını yönetmek için genel bakış bölmesinin üst kısmından aşağıdaki eylemleri seçebilirsiniz:

- [Sil](#delete)
- [Tamazsınız](#pause)
- [Resume](#resume)
- [Genişletmeyi](#extend)
- [Kaldırma](#uninstall)

![Kullanılabilir eylemler](./media/windows-update-for-business-configure/overview-actions.png)

#### <a name="delete"></a>Sil

Seçili Windows 10 güncelleştirme halkası ayarlarının uygulanmasını durdurmak için **Sil** ' i seçin. Bir halkayı silmek, Intune 'un yapılandırmasını artık geçerli olmaması ve bu ayarları zorunlu kıldığı şekilde Intune 'dan kaldırır.

Bir halkanın Intune 'dan silinmesi, güncelleştirme halkasının atandığı cihazlarda ayarları değiştirmez.  Bunun yerine, cihaz geçerli ayarlarını korur. Cihazlar, daha önce tuttuğu ayarların geçmiş kaydını korumaz. Cihazlar, etkin kalan ek güncelleştirme halkalarının ayarlarını da alabilir.

##### <a name="to-delete-a-ring"></a>Bir halkayı silmek için

1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Sil**' i seçin.
2. **Tamam**’ı seçin.

#### <a name="pause"></a>Duraklat

Atanan cihazların, halyi duraklatışınızda 35 güne kadar bir özellik güncelleştirmesi veya kalite güncelleştirmeleri almasını engellemek için **Duraklat** ' ı seçin. En fazla gün sayısı geçtikten sonra duraklatma işlevi otomatik olarak sona erer ve cihaz, kullanılabilecek güncelleştirmeleri bulmak için Windows Güncelleştirmeleri’ni tarar. Bu taramanın ardından güncelleştirmeleri yeniden duraklatabilirsiniz.
Duraklatılmış bir güncelleştirme halkasını devam ettirdikten sonra bu halkayı yeniden duraklatabilirsiniz, duraklatma süresi 35 güne sıfırlanır.

##### <a name="to-pause-a-ring"></a>Bir halkayı duraklatmak için

1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Duraklat**' ı seçin.
2. Bu tür bir güncelleştirmeyi duraklatmak için **özellik** veya **kalite** ' yi seçin ve ardından **Tamam**' ı seçin.
3. Bir güncelleştirme türünü durakladıktan sonra, diğer güncelleştirme türünü duraklatmak için yeniden Duraklat ' ı seçebilirsiniz.

Bir güncelleştirme türü duraklatıldığında, bu halkaya ilişkin genel bakış bölmesi, bu güncelleştirme türünün devam edebilmesi için kaç gün kaldığını gösterir.

> [!IMPORTANT]
> Bir duraklatma komutu verdikten sonra, cihazlar bu komutu hizmete bir dahaki sefer denetduklarında alır. Bu nedenle, hizmete giriş yapmadan önce, zamanlanmış bir güncelleştirmenin yüklenmesi mümkündür. Ayrıca, hedeflenen bir cihaz duraklatma komutunu verdiğiniz sırada kapalıysa bu cihaz açıldığında Intune’u denetlemeden önce, zamanlanmış güncelleştirmeleri indirip yükleyebilir.

#### <a name="resume"></a>Sürdür

Bir güncelleştirme halkası duraklatıldığında, bu halkaya yönelik özellik ve kalite güncelleştirmelerini etkin işleme geri yüklemek için **özgeçmişi** ' ı seçebilirsiniz. Bir güncelleştirme halkasını devam ettirdikten sonra, bu halkayı yeniden duraklatabilirsiniz.

##### <a name="to-resume-a-ring"></a>Bir halkayı sürdürmesini sağlamak için

1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken, yeniden Güncelleştir ' **i seçin.**
2. **Özelliklerin** veya **kalite** güncelleştirmelerinin her birini sürdürmesini sağlamak için kullanılabilir seçenekler arasından seçim yapın ve ardından **Tamam**' ı seçin.
3. Bir güncelleştirme türüne devam ettikten sonra, diğer güncelleştirme türünü sürdürmek için yeniden devam etmeyi seçebilirsiniz.

#### <a name="extend"></a>Genişletme  

Bir güncelleştirme halkası duraklatıldığında, bu güncelleştirme halkası için her iki özellik ve kalite güncelleştirmesi için de duraklatma süresini 35 gün olarak sıfırlamak için **Genişlet** ' i seçebilirsiniz.

##### <a name="to-extend-the-pause-period-for-a-ring"></a>Bir halka için duraklatma süresini uzatmak için

1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken **Genişlet**' i seçin.
2. **Özelliklerin** veya **kalite** güncelleştirmelerinin her birini sürdürmesini sağlamak için kullanılabilir seçenekler arasından seçim yapın ve ardından **Tamam**' ı seçin.
3. Bir güncelleştirme türü için duraklama 'yı genişlettikten sonra, diğer güncelleştirme türünü genişletmek için yeniden Genişlet seçeneğini belirleyebilirsiniz.

#### <a name="uninstall"></a>Kaldır  

Bir Intune Yöneticisi, etkin veya duraklatılmış bir güncelleştirme halkası için en son *özellik* güncelleştirmesini veya en son *kalite* güncelleştirmesini kaldırmak (geri almak) için **kaldırmayı** kullanabilir. Bir tür kaldırıldıktan sonra, diğer türü kaldırabilirsiniz. Intune, kullanıcıların güncelleştirmeleri kaldırma yeteneğini desteklemez veya yönetemez.  

> [!IMPORTANT]
> *Kaldırma* seçeneğini kullandığınızda, Intune kaldırma isteğini cihazlara hemen geçirir.
>
> - Windows cihazları, Intune ilkesinde değişiklik aldıkları anda güncelleştirmelerin kaldırılmasına başlar. Güncelleştirme kaldırma, güncelleştirme halkasının parçası olarak yapılandırıldıklarında bile bakım zamanlamalarıyla sınırlı değildir.
> - Güncelleştirme kaldırma işlemi bir cihazın yeniden başlatılmasını gerektiriyorsa cihaz kullanıcılarına, gecikme süresi seçeneği sunulmadan cihaz yeniden başlatılır.

Kaldırma işleminin başarılı olabilmesi için:

- Bir cihazın Windows 10 Nisan 2018 Güncelleştirmesi (sürüm 1803) veya üzerini çalıştırması gerekir.

Bir cihazın en son güncelleştirmeyi yüklemiş olması gerekir. Güncelleştirmeler birikimli olduğundan, en son güncelleştirmeyi yükleyen cihazlar en son özellik ve kalite güncelleştirmesine sahip olacaktır. Bu seçeneği ne zaman kullanacağınızı bir örnek, Windows 10 makinelerinizde önemli bir sorun bulmalısınız.

Kaldırma kullandığınızda aşağıdakileri göz önünde bulundurun:

- Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir.

- Özellik veya kalite güncelleştirmeleri için kaldırma özelliğinin kullanılması, Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemek için bir ilke tetikler.

- Bir Windows 10 cihazında, kalite güncelleştirmesi başarıyla geri alındıktan sonra cihaz kullanıcıları **Windows ayarları** > **güncelleştirmeler** > **güncelleştirme geçmişi**' nde listelenen güncelleştirmeyi görmeye devam eder.

- Özellikle özellik güncelleştirmeleri için güncelleştirmeyi kaldırabilmeniz için zaman 2-60 gün sınırlı olur. Bu süre güncelleştirme halkaları güncelleştirme ayarı, **özellik güncelleştirme kaldırma süresi (2 – 60 gün)** tarafından yapılandırılır. Güncelleştirme, yapılandırılan kaldırma süresinden daha uzun bir süre için yüklendikten sonra bir cihaza yüklenmiş bir özellik güncelleştirmesini geri alamazsınız.

  Örneğin, özellik güncelleştirme kaldırma süresi 20 gün olan bir güncelleştirme halkasını düşünün. 25 gün sonra en son özellik güncelleştirmesini geri alma ve kaldırma seçeneğini kullanma kararı verirsiniz.  Özellik güncelleştirmesini 20 gün önce yükleyen cihazlar, bakımın bir parçası olarak gerekli bitleri kaldırdıklarından bu sürümü kaldıramıyor. Ancak, yalnızca 19 güne kadar olan özellik güncelleştirmesini yükleyen cihazlar, 20 günlük kaldırma dönemini aşmadan önce Uninstall komutunu almak üzere iade ederseniz güncelleştirmeyi kaldırabilir.

Windows Update ilkeleri hakkında daha fazla bilgi için bkz. Windows istemci yönetimi belgelerinde [CSP güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp) .

##### <a name="to-uninstall-the-latest-windows-10-update"></a>En son Windows 10 güncelleştirmesini kaldırmak için

1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken **Kaldır**' ı seçin.
2. **Özellik** veya **kalite** güncelleştirmelerini kaldırmak için kullanılabilir seçeneklerden birini belirleyin ve ardından **Tamam**' ı seçin.
3. Bir güncelleştirme türü için kaldırmayı tetikledikten sonra, kalan güncelleştirme türünü kaldırmak için Kaldır ' ı tekrar seçebilirsiniz.

## <a name="windows-10-feature-updates"></a>Windows 10 özellik güncelleştirmeleri

*Bu özellik genel önizlemede.*

*Windows 10 özellik güncelleştirmeleri*ile Windows 10 sürüm 1803 veya sürüm 1809 gibi cihazların üzerinde kalmasını istediğiniz Windows özellik sürümünü seçersiniz. 1803 veya üzeri bir özellik düzeyi belirleyebilirsiniz.

Bir cihaz Windows 10 özellik güncelleştirmeleri ilkesi aldığında:

- Cihaz, ilkede belirtilen Windows sürümüne güncelleşmeyecektir. Windows 'un daha sonraki bir sürümünü çalıştıran bir cihaz, geçerli sürümünde kalır. Sürümü dondurarak, cihazlar özellik kümesi ilke süresince kararlı kalır.

- Windows 'un yüklü sürümü ayarlanmış olsa da, cihazlar bu sürüme yönelik destek süresi boyunca Windows sürümleri için kalite ve güvenlik güncelleştirmeleri alabilir ve yükleyebilir, bu da cihazları güncel ve güvenli tutmanıza yardımcı olur.

- 35 gün sonra süresi dolan bir güncelleştirme halkasını *Duraklat* kullanmaktan farklı olarak, Windows 10 özellik güncelleştirmeleri ilkesi etkin kalır. Windows 10 özellik güncelleştirmeleri ilkesini değiştirip kaldırana kadar cihazlar yeni bir Windows sürümü yüklemez. İlkeyi daha yeni bir sürümü belirtmek üzere düzenlerseniz, cihazlar daha sonra bu Windows sürümünden özellikleri yükleyebilir.

### <a name="limitations-for-windows-10-feature-updates"></a>Windows 10 özellik güncelleştirmeleri için sınırlamalar

- Bir Windows 10 *özellik güncelleştirme* Ilkesini bir *Windows 10 güncelleştirme halkası* ilkesi de alan bir cihaza dağıttığınızda, aşağıdaki yapılandırmalarda güncelleştirme halkasını gözden geçirin:
  - **Özellik Güncelleştirmesi erteleme süresi (gün)** **0**olarak ayarlanmalıdır.
  - Güncelleştirme halkası için özellik güncelleştirmeleri *çalışıyor*olmalıdır. Bunların duraklamaları gerekir.

- Windows 10 özellik güncelleştirme ilkeleri, ilk çalıştırma deneyimi (OOBE) sırasında uygulanamıyor ve yalnızca bir cihazın sağlama işlemini tamamladıktan (genellikle bir gün) sonra ilk Windows Update taramaya uygulanır. Ayrıca, AutoPilot ile sağlanan cihazlar ilkeyi almaz.

  Gelecekte desteklenip desteklenmediğini öğrenmek için bu sınırlama incelenmekte.

> [!IMPORTANT]
> Özellik güncelleştirmeleri ilkesini Intune ile birlikte kullanmak için, cihazların en düşük bir ayarla [*temel*](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry)alarak telemetri açık olmalıdır. Telemetri, *Raporlama ve telemetri* altında [cihaz kısıtlama ilkesinin](../configuration/device-restrictions-configure.md)bir parçası olarak yapılandırılır.
>
> Özellik güncelleştirme ilkesi alan ve telemetri ayarlanmış *bir şekilde ayarlanmış olan cihazlar, devre*dışı olduğundan, özellik güncelleştirme ilkesinde tanımlananla Windows 'un daha yeni bir sürümünü yükleyebilirler. Telemetri gerektirmek için önkoşul, bu özellik genel kullanıma yönelik olarak taşındıkça gözden geçirme aşamasındadır.

### <a name="create-and-assign-windows-10-feature-updates"></a>Windows 10 özellik güncelleştirmelerini oluşturma ve atama

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2.  > **cihazları** seçin **Windows** > **Windows 10 özellik güncelleştirmeleri** > **Oluştur**.

3. **Temel bilgiler**altında bir ad, açıklama (isteğe bağlı) belirtin ve **dağıtılacak Özellik Güncelleştirmesi**için, istediğiniz özellik kümesiyle Windows sürümünü seçin ve ardından **İleri**' yi seçin.

4. **Atamalar**altında **+ dahil edilecek grupları seç** ' i seçin ve ardından özellik güncelleştirme dağıtımını bir veya daha fazla gruba atayın. Devam etmek için **İleri** seçeneğini belirleyin.

5. **Gözden geçir + oluştur**altında, ayarları gözden geçirin ve Windows 10 özellik güncelleştirmeleri ilkesini kaydetmeye hazırsanız **Oluştur** ' u seçin.  

### <a name="manage-windows-10-feature-updates"></a>Windows 10 özellik güncelleştirmelerini yönetme

Yönetim Merkezi 'nde **windows** > **Windows 10 özellik güncelleştirmeleri** > **cihazlar** ' a gidin ve yönetmek istediğiniz ilkeyi seçin. İlke, **genel bakış** bölmesi olarak açılır.

Bu bölmeden şunları yapabilirsiniz:

- İlkeyi Intune 'dan silmek ve cihazlardan kaldırmak için **Sil** ' i seçin.
- Dağıtımı değiştirmek için **Özellikler** ' i seçin.  *Özellikler* bölmesinde, dağıtım *ayarları veya atamalar*' ı açmak için **Düzenle** ' yi seçin, burada dağıtımı değiştirebilirsiniz.
- İlke hakkındaki bilgileri görüntülemek için **Son Kullanıcı güncelleştirme durumu** ' nu seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Intune tarafından desteklenen Windows Update ayarları](../windows-update-settings.md)

[Güncelleştirmeler için Intune uyumluluk raporları](../windows-update-compliance-reports.md)

[Windows 10 güncelleştirme halkaları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)