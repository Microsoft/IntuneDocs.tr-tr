---
title: Microsoft Intune - Azure’da İş İçin Windows Update’i yapılandırma | Microsoft Docs
description: Windows 10 cihazlarda Microsoft Intune kullanarak İş İçin Windows Update ayarlarında bir güncelleştirme halkası oluşturmak, uyumluluğu gözden geçirmek ve güncelleştirmeleri duraklatmak için bir profildeki Yazılım Güncelleştirme ayarlarını güncelleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7e144c91f91da998a868868880e9a12d2370e81
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "71302437"
---
# <a name="manage-software-updates-in-intune"></a>Intune’da yazılım güncelleştirmelerini yönetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows 10 cihazlarınızı bir hizmet olarak Windows 'un nasıl ve ne zaman güncelleştirçalıştığını belirten güncelleştirme halkalarını tanımlamak için Intune 'U kullanın. Güncelleştirme halkaları, cihaz gruplarına atadığınız ilkeleridir. Güncelleştirme kademelerini kullanarak işletmenizin ihtiyaçlarına uygun bir güncelleştirme stratejisi oluşturabilirsiniz. Daha fazla bilgi için bkz. [İşletmeler için Windows Update'i kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Windows 10 ile yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri kapsar. En son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.


İş İçin Windows Update kullanarak güncelleştirme yönetimi deneyimini basitleştirirsiniz. Cihaz grupları için ayrı ayrı güncelleştirmeleri onaylamanız gerekmez. Bir güncelleştirmeyi piyasaya sunma stratejisi yapılandırarak ortamlarınızda riskleri yönetebilirsiniz. Intune, cihazlarda [güncelleştirme ayarlarını yapılandırma](windows-update-settings.md) ve güncelleştirme yüklemesini erteleme olanağı sağlar. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. Windows 10 güncelleştirmelerinin yüklendiği zaman yapılandıran Bu ayar koleksiyonu, *Windows 10 güncelleştirme halkası*olarak adlandırılır.

Windows 10 güncelleştirme halkaları [kapsam etiketlerini](scope-tags.md)destekler. Kullandığınız yapılandırmaların kümelerini filtrelemenize ve yönetmenize yardımcı olması için kapsam etiketlerini güncelleştirme halkalarıyla birlikte kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar  

Intune 'da Windows 10 cihazları için Windows güncelleştirmelerini kullanmak üzere aşağıdaki önkoşulların karşılanması gerekir.  

- Windows 10 bilgisayarları, Windows yıldönümü güncelleştirmesi veya sonraki sürümüyle en az Windows 10 Pro çalıştırmalıdır (sürüm 1607 veya üzeri)
- Windows Update aşağıdaki Windows 10 sürümlerini destekler:
  - Windows 10
  - Windows 10 Team (Surface Hub cihazları için)
  - Windows 10 Holographic for Business  

    Windows holographic for Business, aşağıdakiler dahil olmak üzere Windows güncelleştirmeleri için bir ayar alt kümesini destekler:
    - **Otomatik güncelleştirme davranışı**
    - **Microsoft ürün güncelleştirmeleri**
    - **Bakım kanalı**: **Yarı yıllık kanal** ve **yarı yıllık kanal (hedefli)** seçeneklerini destekler. Daha fazla bilgi için bkz. [Windows holographic 'ı yönetme](windows-holographic-for-business.md).  

    > [!NOTE]  
    > **Desteklenmeyen sürümler ve sürümler**:
    > - Windows 10 Mobile  
    > - Windows 10 Enterprise LTSC. Windows Update for Business (WUfB) Şu anda *uzun süreli hizmet kanalı* sürümlerini desteklememektedir. WSUS veya Configuration Manager gibi alternatif düzeltme eki uygulama yöntemlerini kullanmayı planlayın.  

- Windows cihazlarında **geri bildirim & tanılama** > **tanılaması ve kullanım verilerinin** **temel**, **Gelişmiş**veya **tam**olarak ayarlanması gerekir.  

  Windows 10 cihazları için *Tanılama ve kullanım verileri* ayarını el ile yapılandırabilir veya Windows 10 ve üzeri Için bir Intune cihaz kısıtlama profili kullanabilirsiniz. Bir cihaz kısıtlama profili kullanıyorsanız, **kullanım verilerini paylaşma** [cihaz kısıtlama ayarını](device-restrictions-windows-10.md#reporting-and-telemetry) en az **temel**olarak ayarlayın. Bu ayar, Windows 10 veya üzeri için bir cihaz kısıtlama ilkesi yapılandırdığınızda **Raporlama ve telemetri** kategorisi altında bulunur.

  Cihaz profilleri hakkında daha fazla bilgi için bkz. [cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md).  

- Klasik Azure portalını kullanıyorsanız, [ayarlarınızı Azure Portal geçirin](#migrate-update-settings-to-the-azure-portal).  


## <a name="create-and-assign-update-rings"></a>Güncelleştirme halkaları oluşturma ve atama

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları** > **Oluştur**’u seçin.
4. Bir ad ve açıklama (isteğe bağlı) girin ve ardından **Yapılandır**’ı seçin.
5. **Ayarlar**' da, iş gereksinimleriniz için ayarları yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Windows Update ayarları](windows-update-settings.md).  
6. İşiniz bittiğinde **Tamam**’ı seçin. **Güncelleştirme Halkası Oluştur**’da **Oluştur**’u seçin. Yeni güncelleştirme kademesi, güncelleştirme kademeleri listesinde görünür.
7. Halka atamak için, güncelleştirme halkaları listesinde bir halka seçin ve sonra \<halka adı > sekmesinde **atamalar**' ı seçin.
8. Bu halkanın hangi gruplara atandığını tanımlamak için **dahil etme** ve **hariç tutma** sekmelerini kullanın ve ardından atamayı tamamlaması için **Kaydet** ' i seçin.

## <a name="manage-your-windows-10-update-rings"></a>Windows 10 güncelleştirme Halkalarınızı yönetin
Portalda, **genel bakış** bölmesini açmak Için bir Windows 10 güncelleştirme halkası seçebilirsiniz. Bu bölmeden halkalar atama durumunu görüntüleyebilir ve halkayı yönetmek için ek eylemler gerçekleştirebilirsiniz. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Bir güncelleştirme halkalarının genel bakış bölmesini görüntülemek için: 
1. Azure Portal’da oturum açın.
2. **Intune** > **yazılım**güncelleştirmeleriWindows > **10 güncelleştirme halkaları**' na gidin.
3. Görüntülemek veya yönetmek istediğiniz güncelleştirme halkasını seçin.  

Atama durumunu görüntülemenin yanı sıra, güncelleştirme halkasını yönetmek için genel bakış bölmesinin üst kısmından aşağıdaki işlemleri seçebilirsiniz:  
- [Silme](#delete)  
- [Tamazsınız](#pause)  
- [Bilmeniz](#resume)  
- [Genişletmeyi](#extend)  
- [Kaldırma](#uninstall)  

![Kullanılabilir eylemler](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Sil  
Seçili Windows 10 güncelleştirme halkası ayarlarının uygulanmasını durdurmak için **Sil** ' i seçin. Bir halkayı silmek, Intune 'un yapılandırmasını artık geçerli olmaması ve bu ayarları zorunlu kıldığı şekilde Intune 'dan kaldırır.  

Bir halkanın Intune 'dan silinmesi, güncelleştirme halkasının atandığı cihazlarda ayarları değiştirmez.  Bunun yerine, cihaz geçerli ayarlarını korur. Bunun nedeni, cihazların daha önce hangi ayarların yerinde olduğunu ve cihazın etkin kalan ek güncelleştirme halkalarından ayarları almasına yönelik bir geçmiş kaydını korumadığı bir şeydir.  

#### <a name="to-delete-a-ring"></a>Bir halkayı silmek için  
1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Sil**' i seçin.  
2. **Tamam**’ı seçin.  

### <a name="pause"></a>Duraklat  
Atanan cihazların, halyi duraklatışınızda 35 güne kadar bir özellik güncelleştirmesi veya kalite güncelleştirmeleri almasını engellemek için **Duraklat** ' ı seçin. En fazla gün sayısı geçtikten sonra duraklatma işlevi otomatik olarak sona erer ve cihaz, kullanılabilecek güncelleştirmeleri bulmak için Windows Güncelleştirmeleri’ni tarar. Bu taramanın ardından güncelleştirmeleri yeniden duraklatabilirsiniz. Duraklatılmış bir güncelleştirme halkasını devam ettirdikten sonra bu halkayı yeniden duraklatabilirsiniz, duraklatma süresi 35 güne sıfırlanır.  

#### <a name="to-pause-a-ring"></a>Bir halkayı duraklatmak için  
1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Duraklat**' ı seçin.  
2. Bu tür bir güncelleştirmeyi duraklatmak için **özellik** veya **kalite** ' yi seçin ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türünü durakladıktan sonra, diğer güncelleştirme türünü duraklatmak için yeniden Duraklat ' ı seçebilirsiniz.  

Bir güncelleştirme türü duraklatıldığında, bu halkaya ilişkin genel bakış bölmesi, bu güncelleştirme türünün devam edebilmesi için kaç gün kaldığını gösterir.

> [!IMPORTANT]  
> Bir duraklatma komutu verdikten sonra, cihazlar bu komutu hizmete bir dahaki sefer denetduklarında alır. Bu nedenle, hizmete giriş yapmadan önce, zamanlanmış bir güncelleştirmenin yüklenmesi mümkündür. Ayrıca, hedeflenen bir cihaz duraklatma komutunu verdiğiniz sırada kapalıysa bu cihaz açıldığında Intune’u denetlemeden önce, zamanlanmış güncelleştirmeleri indirip yükleyebilir.

### <a name="resume"></a>Sürdür  
Bir güncelleştirme halkası duraklatıldığında, bu halkaya yönelik özellik ve kalite güncelleştirmelerini etkin işleme geri yüklemek için **özgeçmişi** ' ı seçebilirsiniz. Bir güncelleştirme halkasını devam ettirdikten sonra, bu halkayı yeniden duraklatabilirsiniz.  

#### <a name="to-resume-a-ring"></a>Bir halkayı sürdürmesini sağlamak için  
1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken, yeniden Güncelleştir ' **i seçin.**  
2. **Özelliklerin** veya **kalite** güncelleştirmelerinin her birini sürdürmesini sağlamak için kullanılabilir seçenekler arasından seçim yapın ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türüne devam ettikten sonra, diğer güncelleştirme türünü sürdürmek için yeniden devam etmeyi seçebilirsiniz.  

### <a name="extend"></a>Genişletme  
Bir güncelleştirme halkası duraklatıldığında, bu güncelleştirme halkası için her iki özellik ve kalite güncelleştirmesi için de duraklatma süresini 35 gün olarak sıfırlamak için **Genişlet** ' i seçebilirsiniz.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Bir halka için duraklatma süresini uzatmak için  
1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken **Genişlet**' i seçin. 
2. **Özelliklerin** veya **kalite** güncelleştirmelerinin her birini sürdürmesini sağlamak için kullanılabilir seçenekler arasından seçim yapın ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türü için duraklama 'yı genişlettikten sonra, diğer güncelleştirme türünü genişletmek için yeniden Genişlet seçeneğini belirleyebilirsiniz.  

### <a name="uninstall"></a>Kaldır  
Bir Intune Yöneticisi, etkin veya duraklatılmış bir güncelleştirme halkası için en son *özellik* güncelleştirmesini veya en son *kalite* güncelleştirmesini kaldırmak (geri almak) için **kaldırmayı** kullanabilir. Bir tür kaldırıldıktan sonra, diğer türü kaldırabilirsiniz. Intune, kullanıcıların güncelleştirmeleri kaldırma yeteneğini desteklemez veya yönetemez.  

Kaldırma işleminin başarılı olabilmesi için:  
- Bir cihazın Windows 10 Nisan 2018 Güncelleştirmesi (sürüm 1803) veya üzerini çalıştırması gerekir.  

Bir cihazın en son güncelleştirmeyi yüklemiş olması gerekir. Güncelleştirmeler birikimli olduğundan, en son güncelleştirmeyi yükleyen cihazlar en son özellik ve kalite güncelleştirmesine sahip olacaktır. Bu seçeneği ne zaman kullanacağınızı bir örnek, Windows 10 makinelerinizde önemli bir sorun bulmalısınız.  

Kaldırma kullandığınızda aşağıdakileri göz önünde bulundurun:  
- Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir.  

- Özellik veya kalite güncelleştirmeleri için kaldırma özelliğinin kullanılması, Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemek için bir ilke tetikler.  

- Bir Windows 10 cihazında, bir kalite güncelleştirmesi başarıyla geri alındıktan sonra, son kullanıcılar **Windows ayarları** > **güncelleştirmeler** > **güncelleştirme geçmişi**' nde listelenen güncelleştirmeyi görmeye devam eder.  

- Özellikle özellik güncelleştirmeleri için, özellik güncelleştirmesini kaldırabilmeniz gereken süre 2-60 günden sınırlıdır ve güncelleştirme halkaları güncelleştirme ayarı, **özellik güncelleştirme kaldırma süresi (2 – 60 gün)** ile yapılandırılır. Özellik Güncelleştirmesi yapılandırılmış kaldırma süresinden daha uzun bir süre için yüklendikten sonra bir cihaza yüklenmiş bir özellik güncelleştirmesini geri alamazsınız.  

  Örneğin, özellik güncelleştirme kaldırma süresi 20 gün olan bir güncelleştirme halkasını düşünün. 25 gün sonra en son özellik güncelleştirmesini geri alma ve kaldırma seçeneğini kullanma kararı verirsiniz.  Özellik güncelleştirmesini 20 gün önce yükleyen cihazlar, bakımının bir parçası olarak gerekli bitleri kaldırdıklarından bu sürümü kaldıramıyor. Ancak, yalnızca 19 güne kadar olan özellik güncelleştirmesini yükleyen cihazlar, 20 günlük kaldırma süresini aşmadan önce kaldırma komutunu almak üzere iade ederseniz güncelleştirmeyi kaldırabilir.  

Windows Update ilkeleri hakkında daha fazla bilgi için bkz. Windows istemci yönetimi belgelerinde [CSP güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp) .  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>En son Windows 10 güncelleştirmesini kaldırmak için  
1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken **Kaldır**' ı seçin.  
2. **Özellik** veya **kalite** güncelleştirmelerini kaldırmak için kullanılabilir seçeneklerden birini belirleyin ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türü için kaldırmayı tetikledikten sonra, kalan güncelleştirme türünü kaldırmak için Kaldır ' ı tekrar seçebilirsiniz.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Güncelleştirme ayarlarını Azure portal geçirme  
Ayrıca Azure klasik portalındaki cihaz yapılandırma profilinde de sınırlı sayıda Windows 10 güncelleştirme ayarı bulunur. Azure portal geçiş yaparken bu ayarlardan herhangi birini yapılandırdıysanız, aşağıdaki eylemleri yapmanızı kesinlikle öneririz:  

1. Azure portalında ihtiyaç duyduğunuz ayarlara sahip Windows 10 güncelleştirme kademeleri oluşturun. **Yayın öncesi özelliklere izin ver** ayarı, en son Windows 10 derlemelerinde geçerli olmadığından Azure portal’da desteklenmez. Windows 10 güncelleştirme kademeleri oluştururken kalan üç ayarı ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.  

   > [!NOTE]  
   > Klasik portalda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portalında görüntülenmez. Ancak bu ayarlar uygulanır. Bu ayarlardan herhangi birini geçirir ve geçirilen ilkeyi Azure portalından düzenlerseniz söz konusu ayarlar ilkeden kaldırılır.  

2. Güncelleştirme ayarlarını klasik portaldan silin. Azure portalına geçiş yaptıktan ve aynı ayarları bir güncelleştirme halkasına ekledikten sonra, olası ilke çakışmalarını önlemek için ayarları klasik portalda silmeniz gerekir. Örneğin aynı ayar farklı değerlerle yapılandırılırsa bir çakışma olur. Klasik portalda yapılandırılan ayar Azure portal görüntülenmediğinden, bildiğiniz kolay bir yol yoktur.  

## <a name="next-steps"></a>Sonraki adımlar
[Intune tarafından desteklenen Windows Update ayarları](windows-update-settings.md)  

[Güncelleştirmeler için Intune uyumluluk raporları](windows-update-compliance-reports.md)

[Windows 10 güncelleştirme halkaları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

