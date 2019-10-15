---
title: Microsoft Intune-Azure 'da Windows Update Iş için yapılandırma | Microsoft Docs
description: Bir profildeki yazılım güncelleştirme ayarlarını güncelleştirme halkası oluşturmak, uyumluluğu gözden geçirmek ve Windows 10 cihazlarda Microsoft Intune kullanarak Iş ayarları için Windows Update güncelleştirmeleri duraklatmak için güncelleştirin.
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
ms.openlocfilehash: aa8cc396c05150006799c1e9b86ecb63351cdb36
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314707"
---
# <a name="manage-software-updates-in-intune"></a>Intune 'da yazılım güncelleştirmelerini yönetme

Windows 10 cihazlarınızı bir hizmet olarak Windows 'un nasıl ve ne zaman güncelleştirçalıştığını belirten güncelleştirme halkalarını tanımlamak için Intune 'U kullanın. Güncelleştirme halkaları, cihaz gruplarına atadığınız ilkeleridir. Güncelleştirme halkalarını kullanarak, iş gereksinimlerinizi yansıtan bir güncelleştirme stratejisi oluşturabilirsiniz. Daha fazla bilgi için bkz. [iş için Windows Update kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Windows 10 ile yeni özellik güncelleştirmeleri ve kalite güncelleştirmeleri, önceki tüm güncelleştirmelerin içeriğini içerir. En son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğunu bilirsiniz. Önceki Windows sürümlerinden farklı olarak, bir güncelleştirmenin parçası yerine artık tüm güncelleştirmeyi yüklemelisiniz.


Iş için Windows Update kullanarak güncelleştirme yönetimi deneyimini basitleştirirsiniz. Cihaz grupları için tek tek güncelleştirmeleri onaylamanız gerekmez. Bir güncelleştirme dağıtım stratejisi yapılandırarak ortamlarınızdaki riski yönetebilirsiniz. Intune, cihazlarda [güncelleştirme ayarlarını yapılandırma](../windows-update-settings.md) ve güncelleştirme yüklemesini erteleme olanağı sağlar. Intune güncelleştirmeleri depolamaz, ancak yalnızca güncelleştirme ilkesi atamasını depolar. Cihazlar Windows Update doğrudan güncelleştirmeler için erişim. Windows 10 güncelleştirmelerinin yüklendiği zaman yapılandıran Bu ayar koleksiyonu, *Windows 10 güncelleştirme halkası*olarak adlandırılır.

Windows 10 güncelleştirme halkaları [kapsam etiketlerini](../fundamentals/scope-tags.md)destekler. Kullandığınız yapılandırmaların kümelerini filtrelemenize ve yönetmenize yardımcı olması için kapsam etiketlerini güncelleştirme halkalarıyla birlikte kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar  

Intune 'da Windows 10 cihazları için Windows güncelleştirmelerini kullanmak üzere aşağıdaki önkoşulların karşılanması gerekir.  

- Windows 10 bilgisayarları, Windows yıldönümü güncelleştirmesi veya sonraki sürümüyle en az Windows 10 Pro çalıştırmalıdır (sürüm 1607 veya üzeri)
- Windows Update aşağıdaki Windows 10 sürümlerini destekler:
  - Windows 10
  - Windows 10 Team (Surface Hub cihazları için)
  - Windows holographic for Business  

    Windows holographic for Business, aşağıdakiler dahil olmak üzere Windows güncelleştirmeleri için bir ayar alt kümesini destekler:
    - **Otomatik Güncelleştirme davranışı**
    - **Microsoft ürün güncelleştirmeleri**
    - **Bakım kanalı**: **yarı yıllık kanal** ve **yarı yıllık kanal (hedeflenen)** seçeneklerini destekler. Daha fazla bilgi için bkz. [Windows holographic 'ı yönetme](../fundamentals/windows-holographic-for-business.md).  

    > [!NOTE]  
    > **Desteklenmeyen sürümler ve sürümler**:
    > - Windows 10 Mobile  
    > - Windows 10 Enterprise LTSC. Windows Update for Business (WUfB) Şu anda *uzun süreli hizmet kanalı* sürümlerini desteklememektedir. WSUS veya Configuration Manager gibi alternatif düzeltme eki uygulama yöntemlerini kullanmayı planlayın.  

- Windows cihazlarında **geri bildirim & tanılama** > **Tanılama ve kullanım verileri** **temel**, **Gelişmiş**veya **tam**olarak ayarlanmalıdır.  

  Windows 10 cihazları için *Tanılama ve kullanım verileri* ayarını el ile yapılandırabilir veya Windows 10 ve üzeri Için bir Intune cihaz kısıtlama profili kullanabilirsiniz. Bir cihaz kısıtlama profili kullanıyorsanız, **kullanım verilerini paylaşma** [cihaz kısıtlama ayarını](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) en az **temel**olarak ayarlayın. Bu ayar, Windows 10 veya üzeri için bir cihaz kısıtlama ilkesi yapılandırdığınızda **Raporlama ve telemetri** kategorisi altında bulunur.

  Cihaz profilleri hakkında daha fazla bilgi için bkz. [cihaz kısıtlama ayarlarını yapılandırma](../configuration/device-restrictions-configure.md).  

- Klasik Azure portalını kullanıyorsanız, [ayarlarınızı Azure Portal geçirin](#migrate-update-settings-to-the-azure-portal).  


## <a name="create-and-assign-update-rings"></a>Güncelleştirme halkaları oluşturma ve atama

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. @No__t **yazılım güncelleştirmelerini**seçin-1**Windows 10 güncelleştirme halkaları** > **Oluştur**.
4. Bir ad, açıklama (isteğe bağlı) girin ve ardından **Yapılandır**' ı seçin.
5. **Ayarlar**' da, iş gereksinimleriniz için ayarları yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Windows Update ayarları](../windows-update-settings.md).  
6. İşiniz bittiğinde **Tamam**’ı seçin. **Güncelleştirme Halkası Oluştur** menüsünde **Oluştur**’u seçin. Yeni güncelleştirme halkası, güncelleştirme halkaları listesinde görüntülenir.
7. Halka atamak için, güncelleştirme halkaları listesinde bir halka seçin ve sonra \<halka adı > sekmesinde **atamalar**' ı seçin.
8. Bu halkanın hangi gruplara atandığını tanımlamak için **dahil etme** ve **hariç tutma** sekmelerini kullanın ve ardından atamayı tamamlaması için **Kaydet** ' i seçin.

## <a name="manage-your-windows-10-update-rings"></a>Windows 10 güncelleştirme Halkalarınızı yönetin
Portalda, **genel bakış** bölmesini açmak Için bir Windows 10 güncelleştirme halkası seçebilirsiniz. Bu bölmeden, halkalar atama durumunu görüntüleyebilir ve halkayı yönetmek için ek eylemler gerçekleştirebilirsiniz. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Bir güncelleştirme halkalarının genel bakış bölmesini görüntülemek için: 
1. Azure Portal’da oturum açın.
2. **Intune** > **yazılım güncelleştirmeleri** > **Windows 10 güncelleştirme halkaları**' na gidin.
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

Bir halkanın Intune 'dan silinmesi, güncelleştirme halkasının atandığı cihazlarda ayarları değiştirmez.  Bunun yerine, cihaz geçerli ayarlarını korur. Cihazlar, daha önce tuttuğu ayarların geçmiş kaydını korumaz. Cihazlar, etkin kalan ek güncelleştirme halkalarının ayarlarını da alabilir.  

#### <a name="to-delete-a-ring"></a>Bir halkayı silmek için  
1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Sil**' i seçin.  
2. **Tamam**’ı seçin.  

### <a name="pause"></a>Duraklat  
Atanan cihazların, halyi duraklatışınızda 35 güne kadar bir özellik güncelleştirmesi veya kalite güncelleştirmeleri almasını engellemek için **Duraklat** ' ı seçin. En fazla gün geçtikten sonra, duraklatma işlevi otomatik olarak sona erer ve cihaz, geçerli güncelleştirmeler için Windows güncelleştirmelerini tarar. Bu taramayı izleyerek güncelleştirmeleri yeniden duraklatabilirsiniz. Duraklatılmış bir güncelleştirme halkasını devam ettirdikten sonra bu halkayı yeniden duraklatabilirsiniz, duraklatma süresi 35 güne sıfırlanır.  

#### <a name="to-pause-a-ring"></a>Bir halkayı duraklatmak için  
1. Bir güncelleştirme halkasının genel bakış sayfasını görüntülerken **Duraklat**' ı seçin.  
2. Bu tür bir güncelleştirmeyi duraklatmak için **özellik** veya **kalite** ' yi seçin ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türünü durakladıktan sonra, diğer güncelleştirme türünü duraklatmak için yeniden Duraklat ' ı seçebilirsiniz.  

Bir güncelleştirme türü duraklatıldığında, bu halkaya ilişkin genel bakış bölmesi, bu güncelleştirme türünün devam edebilmesi için kaç gün kaldığını gösterir.

> [!IMPORTANT]  
> Bir duraklatma komutu verdikten sonra, cihazlar bu komutu hizmete bir dahaki sefer denetduklarında alır. İade etmeden önce, zamanlanmış bir güncelleştirme yükleyebilecekleri için bu durum mümkündür. Ayrıca, duraklatma komutunu verdiğinizde hedeflenen bir cihaz kapatılmışsa, bu açık olduğunda, Intune 'a iade etmeden önce zamanlanan güncelleştirmeleri indirebilir ve yükleyebilir.

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

### <a name="uninstall"></a>Kaldırma  
Bir Intune Yöneticisi, etkin veya duraklatılmış bir güncelleştirme halkası için en son *özellik* güncelleştirmesini veya en son *kalite* güncelleştirmesini kaldırmak (geri almak) için **kaldırmayı** kullanabilir. Bir tür kaldırıldıktan sonra, diğer türü kaldırabilirsiniz. Intune, kullanıcıların güncelleştirmeleri kaldırma yeteneğini desteklemez veya yönetemez.  

> [!IMPORTANT] 
> *Kaldırma* seçeneğini kullandığınızda, Intune kaldırma isteğini cihazlara hemen geçirir. 
> - Windows cihazları, Intune ilkesinde değişiklik aldıkları anda güncelleştirmelerin kaldırılmasına başlar. Güncelleştirme kaldırma, güncelleştirme halkasının parçası olarak yapılandırıldıklarında bile bakım zamanlamalarıyla sınırlı değildir. 
> - Güncelleştirme kaldırma işlemi bir cihazın yeniden başlatılmasını gerektiriyorsa cihaz kullanıcılarına, gecikme süresi seçeneği sunulmadan cihaz yeniden başlatılır.


Kaldırma işleminin başarılı olabilmesi için:  
- Bir cihazın Windows 10 Nisan 2018 Güncelleştirmesi (sürüm 1803) veya üzerini çalıştırması gerekir.  

Bir cihazın en son güncelleştirmeyi yüklemiş olması gerekir. Güncelleştirmeler birikimli olduğundan, en son güncelleştirmeyi yükleyen cihazlar en son özellik ve kalite güncelleştirmesine sahip olacaktır. Bu seçeneği ne zaman kullanacağınızı bir örnek, Windows 10 makinelerinizde önemli bir sorun bulmalısınız.  

Kaldırma kullandığınızda aşağıdakileri göz önünde bulundurun:  
- Bir özellik veya kalite güncelleştirmesini kaldırmak yalnızca cihazın açık olduğu hizmet kanalı için kullanılabilir.  

- Özellik veya kalite güncelleştirmeleri için kaldırma özelliğinin kullanılması, Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemek için bir ilke tetikler.  

- Bir Windows 10 cihazında, bir kalite güncelleştirmesi başarıyla geri alındıktan sonra, son kullanıcılar **Windows ayarları**@no__t,-3**güncelleştirme geçmişi** **@no__t listelenen**güncelleştirmeyi görmeye devam eder.  

- Özellikle özellik güncelleştirmeleri için, özellik güncelleştirmesini kaldırabilmeniz gereken süre 2-60 günden sınırlıdır ve güncelleştirme halkaları güncelleştirme ayarı, **özellik güncelleştirme kaldırma süresi (2 – 60 gün)** ile yapılandırılır. Özellik Güncelleştirmesi yapılandırılmış kaldırma süresinden daha uzun bir süre için yüklendikten sonra bir cihaza yüklenmiş bir özellik güncelleştirmesini geri alamazsınız.  

  Örneğin, özellik güncelleştirme kaldırma süresi 20 gün olan bir güncelleştirme halkasını düşünün. 25 gün sonra en son özellik güncelleştirmesini geri alma ve kaldırma seçeneğini kullanma kararı verirsiniz.  Özellik güncelleştirmesini 20 gün önce yükleyen cihazlar, bakımının bir parçası olarak gerekli bitleri kaldırdıklarından bu sürümü kaldıramıyor. Ancak, yalnızca 19 güne kadar olan özellik güncelleştirmesini yükleyen cihazlar, 20 günlük kaldırma süresini aşmadan önce kaldırma komutunu almak üzere iade ederseniz güncelleştirmeyi kaldırabilir.  

Windows Update ilkeleri hakkında daha fazla bilgi için bkz. Windows istemci yönetimi belgelerinde [CSP güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp) .  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>En son Windows 10 güncelleştirmesini kaldırmak için  
1. Duraklatılmış bir güncelleştirme halkası için genel bakış sayfasını görüntülerken **Kaldır**' ı seçin.  
2. **Özellik** veya **kalite** güncelleştirmelerini kaldırmak için kullanılabilir seçeneklerden birini belirleyin ve ardından **Tamam**' ı seçin.  
3. Bir güncelleştirme türü için kaldırmayı tetikledikten sonra, kalan güncelleştirme türünü kaldırmak için Kaldır ' ı tekrar seçebilirsiniz.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Güncelleştirme ayarlarını Azure portal geçirme  
Klasik Azure portalında Ayrıca cihaz yapılandırma profilinde sınırlı sayıda Windows 10 güncelleştirme ayarı vardır. Azure portal geçiş yaparken bu ayarlardan herhangi birini yapılandırdıysanız, aşağıdaki eylemleri yapmanızı kesinlikle öneririz:  

1. Azure portal, ihtiyacınız olan ayarlarla Windows 10 güncelleştirme halkaları oluşturun. **Yayın öncesi sürüm özelliklerine Izin ver** ayarı, artık en son Windows 10 yapılarına uygun olmadığından Azure Portal desteklenmez. Güncelleştirme halkaları oluştururken diğer üç ayarı ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.  

   > [!NOTE]  
   > Klasik portalda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portal gösterilmez. Ancak, bu ayarlar uygulanır. Bu ayarlardan herhangi birini geçirirseniz ve geçirilen ilkeyi Azure portal düzenlediğinizde, bu ayarlar ilkeden kaldırılır.  

2. Klasik portalda güncelleştirme ayarlarını silin. Azure portal taşıdıktan ve aynı ayarları bir güncelleştirme halkasını ekledikten sonra, olası İlke çakışmalarını önlemek için klasik portaldaki ayarları silmeniz gerekir. Örneğin, aynı ayar farklı değerlerle yapılandırıldığında bir çakışma vardır. Klasik portalda yapılandırılan ayar Azure portal görüntülenmediğinden, bildiğiniz kolay bir yol yoktur.  

## <a name="next-steps"></a>Sonraki adımlar
[Intune tarafından desteklenen Windows Update ayarları](../windows-update-settings.md)  

[Güncelleştirmeler için Intune uyumluluk raporları](../windows-update-compliance-reports.md)

[Windows 10 güncelleştirme halkaları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

