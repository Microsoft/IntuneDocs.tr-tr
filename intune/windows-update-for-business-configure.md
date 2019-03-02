---
title: Microsoft Intune - Azure’da İş İçin Windows Update’i yapılandırma | Microsoft Docs
description: Windows 10 cihazlarda Microsoft Intune kullanarak İş İçin Windows Update ayarlarında bir güncelleştirme halkası oluşturmak, uyumluluğu gözden geçirmek ve güncelleştirmeleri duraklatmak için bir profildeki Yazılım Güncelleştirme ayarlarını güncelleştirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9b769b25a8f45d6ee19f9082a20b9816c7f3814
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229616"
---
# <a name="manage-software-updates-in-intune"></a>Intune’da yazılım güncelleştirmelerini yönetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Nasıl ve ne zaman Windows 10 cihazlarınızın hizmet olarak Windows güncelleştirmeleri belirtin güncelleştirme halkalarını tanımlamak üzere Intune kullanın. Güncelleştirme kademeleri olan ilkeleri, cihaz gruplarına atayabilirsiniz. Güncelleştirme kademelerini kullanarak işletmenizin ihtiyaçlarına uygun bir güncelleştirme stratejisi oluşturabilirsiniz. Daha fazla bilgi için bkz. [İşletmeler için Windows Update'i kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Windows 10 ile yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri kapsar. En son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.


İş İçin Windows Update kullanarak güncelleştirme yönetimi deneyimini basitleştirirsiniz. Cihaz grupları için ayrı ayrı güncelleştirmeleri onaylamanız gerekmez. Bir güncelleştirmeyi piyasaya sunma stratejisi yapılandırarak ortamlarınızda riskleri yönetebilirsiniz. Intune aşağıdakileri yapabilmenizi sağlar [güncelleştirme ayarlarını yapılandırma](windows-update-settings.md) cihazlarda ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. Windows 10 güncelleştirmelerini yüklendiğinde, yapılandıran bu ayarlar koleksiyonunu adlı bir *Windows 10 güncelleştirme halkası*.

Windows 10 güncelleştirme halkası Destek [kapsam etiketleri](scope-tags.md). Kapsam etiketleri, filtrelemek ve kullandığınız yapılandırmaları kümelerini yönetmenize yardımcı olmak için güncelleştirme halkaları ile kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar  

Intune'da Windows 10 cihazları için Windows güncelleştirmelerini kullanmak için aşağıdaki önkoşulların karşılanması gerekir.  

- Windows 10 bilgisayarları en az çalıştırmalısınız Windows 10 Pro veya sonraki sürümleriyle Windows Yıldönümü Güncelleştirmesi (sürüm 1607 veya üzeri)
- Windows güncelleştirme, aşağıdaki Windows 10 sürümleri destekler:
  - Windows 10
  - Windows 10 Team (Surface Hub cihazları için)
  - Windows 10 Holographic for Business  

    Windows Holographic for Business dahil olmak üzere Windows güncelleştirmeleri için ayarların bir alt kümesini destekler:
    - **Otomatik güncelleştirme davranışı**
    - **Microsoft ürün güncelleştirmeleri**
    - **Hizmet kanalı**: Destekler **yarı yıllık kanal** ve **yarı yıllık kanal (hedefli)** seçenekleri  

    Daha fazla bilgi için [Windows Holographic yönetme](windows-holographic-for-business.md)  
  
  Windows 10 Mobile çalıştıran cihazlar desteklenmez.

- Windows cihazlarda **geri bildirim ve tanılama** > **tanılama ve kullanım verileri** ayarlanmalıdır **temel**, **geliştirilmiş**, veya **tam**.  

  Bu ayarı el ile yapılandırabilir veya bir Intune cihaz kısıtlama profili Windows 10 ve üzeri için kullanın. Cihaz kısıtlama profili kullanmak için ayarın **genel** > **tanılama verilerinin gönderimine** için en az **temel**. Cihaz profilleri hakkında daha fazla bilgi için bkz. [cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md).  

- Azure Klasik portalı kullanıyorsanız [ayarlarınızı Azure portalına geçiş](#migrate-update-settings-to-the-azure-portal).  

## <a name="create-and-assign-update-rings"></a>Güncelleştirme halkaları oluşturma ve atama

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin.
3. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları** > **Oluştur**’u seçin.
4. Bir ad ve açıklama (isteğe bağlı) girin ve ardından **Yapılandır**’ı seçin.
5. İçinde **ayarları**, iş gereksinimleriniz için ayarları yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Windows update ayarları](windows-update-settings.md).  
6. İşiniz bittiğinde **Tamam**’ı seçin. **Güncelleştirme Halkası Oluştur**’da **Oluştur**’u seçin. Yeni güncelleştirme kademesi, güncelleştirme kademeleri listesinde görünür.
7. Güncelleştirme kademeleri listesinde kademeyi atamak kademeyi seçin ve ardından \<kademe adı > sekmesinde **atamaları**.
8. Kullanım **Ekle** ve **hariç** sekmeler, gruplar bu kademeyi tanımlamak için atanan ve ardından **Kaydet** seçerek atama işlemini tamamlayın.

## <a name="manage-your-windows-10-update-rings"></a>Windows 10 güncelleştirme halkaları yönetme
Portalı'nda açmak için bir Windows 10 güncelleştirme kademesi seçin, **genel bakış** bölmesi. Bu bölmeden halkaları atama durumu görüntüleyebilir ve halka yönetmek için ek eylemler. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Bir güncelleştirme halkaları genel bakış bölmesini görüntülemek için: 
1. Azure Portal’da oturum açın.
2. Gidin **Intune** > **yazılım güncelleştirmelerini** > **Windows 10 güncelleştirme halkaları**.
3. Yönetmek veya görüntülemek istediğiniz güncelleştirme kademesi seçin.  

Atama durumu görüntülemenin yanı sıra güncelleştirme kademesi yönetmek için genel bakış bölmesinin üst kısmından aşağıdaki eylemlerden birini seçebilirsiniz:  
- [Silme](#delete)  
- [Duraklat](#pause)  
- [Sürdür](#resume)  
- [Genişletme](#extend)  
- [Kaldırma](#uninstall)  

![Kullanılabilir eylemler](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Sil  
Seçin **Sil** seçilen Windows 10 güncelleştirme halkası ayarlarını zorlamayı durdurmak için. Intune artık uygular ve bu ayarlar zorunlu kılar. böylece bir halka silme yapılandırmasıyla Intune'dan kaldırır.  

Bir halka Intune kaydını silme, güncelleştirme kademesi atanmış olan cihazlarda ayarları değiştirmez.  Bunun yerine, cihaz, geçerli ayarlarını korur. Bu cihazlar hangi ayarları yerinde önceden yapılan bir geçmiş kaydını bulundurmaz olduğundan ve cihaz ayarları etkin ek güncelleştirme halkaları alabilirsiniz çünkü değildir.  

#### <a name="to-delete-a-ring"></a>Bir halka silmek için  
1. Genel Bakış sayfası için bir güncelleştirme halkası görüntülerken seçin **Sil**.  
2. **Tamam**’ı seçin.  

### <a name="pause"></a>Duraklat  
Seçin **duraklatmak** halka duraklatma atanan cihazların zamandan 35 güne kadar özellik güncelleştirmeleri veya kalite güncelleştirmeleri almasını önlemek için. En fazla gün sayısı geçtikten sonra duraklatma işlevi otomatik olarak sona erer ve cihaz, kullanılabilecek güncelleştirmeleri bulmak için Windows Güncelleştirmeleri’ni tarar. Bu taramanın ardından güncelleştirmeleri yeniden duraklatabilirsiniz. Sürdürürseniz, duraklatılmış bir güncelleştirme kademesi ve sonra bu kademeyi yeniden duraklatma 35 gün dönem sıfırlar duraklatın.  

 #### <a name="to-pause-a-ring"></a>Bir halka duraklatma  
1. Genel Bakış sayfası için bir güncelleştirme halkası görüntülerken seçin **duraklatma**.  
2. Şunlardan birini seçin **özellik** veya **kalite** güncelleştirme türü duraklatmak ve ardından **Tamam**.  
3. Duraklattıktan sonra bir güncelleştirme türü, bir güncelleştirme türünü yeniden duraklatmak için duraklatma seçebilirsiniz.  

Kaç gün önce bu güncelleştirmeyi kalır genel bakış bölmesinin o kademesi için bir güncelleştirme türünü duraklatıldığında görüntüler yazın sürdürür.

> [!IMPORTANT]  
> Bir duraklatma komutu yürütün sonra cihaz, bu komut onlar iade hizmette oturum açtığında alır. Bu nedenle, hizmete giriş yapmadan önce, zamanlanmış bir güncelleştirmenin yüklenmesi mümkündür. Ayrıca, hedeflenen bir cihaz duraklatma komutunu verdiğiniz sırada kapalıysa bu cihaz açıldığında Intune’u denetlemeden önce, zamanlanmış güncelleştirmeleri indirip yükleyebilir.

### <a name="resume"></a>Sürdür  
Güncelleştirme halkası duraklatılmış durumdayken, seçebileceğiniz **sürdürme** çan özellik ve kalite güncelleştirmeleri etkin bir işlem için geri yüklemek için. Güncelleştirme halkası sürdürme sonra bu kademeyi yeniden duraklatabilirsiniz.  

#### <a name="to-resume-a-ring"></a>Bir halka sürdürmek için  
1. Duraklatılmış bir güncelleştirme kademesi için bir genel bakış sayfası görüntülerken seçin **sürdürme**.  
2. Ya da sürdürmek için kullanılabilir seçenekler arasından seçim **özellik** veya **kalite** güncelleştirmeleri tıklayın ve ardından **Tamam**.  
3. Bir güncelleştirme türü devam ettirildikten sonra bir güncelleştirme türünü yeniden sürdürmek için devam seçebilirsiniz.  

### <a name="extend"></a>Genişletme  
Güncelleştirme halkası duraklatılmış durumdayken, seçebileceğiniz **Genişlet** hem özellik ve kalite güncelleştirmelerini duraklatma süresi söz konusu güncelleştirme kademesi için 35 gün öncesine sıfırlanır.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Bir halka duraklatma süresini uzatmak için  
1. Duraklatılmış bir güncelleştirme kademesi için bir genel bakış sayfası görüntülerken seçin **Genişlet**. 
2. Ya da sürdürmek için kullanılabilir seçenekler arasından seçim **özellik** veya **kalite** güncelleştirmeleri tıklayın ve ardından **Tamam**.  
3. Bir güncelleştirme tipi için duraklatma genişletildikten sonra yeniden başka bir güncelleştirme türü genişletmek için Genişlet seçebilirsiniz.  

### <a name="uninstall"></a>Kaldır  
Intune yönetici **kaldırma** en son (geri alma) kaldırmak için *özellik* güncelleştirme veya en son *kalite* etkin ya da duraklatılmış güncelleştirme halkası güncelleştirmesi. Bir tür kaldırıldıktan sonra diğer tür kaldırabilirsiniz. Intune desteklemez veya güncelleştirmelerini kaldırma yeteneğinin kullanıcıları yönetme.  

Kaldırma başarılı olması için:  
- Bir cihaz Windows çalıştırmalısınız 10 Nisan 2018 Güncelleştirmesi (sürüm 1803) veya üzeri.  

Bir cihazı en son güncelleştirmeyi yüklemiş olmanız gerekir. Güncelleştirmeleri birikmeli özelliktedir olduğundan, en son güncelleştirmeyi yükleme cihazları en son özellik ve kalite güncelleştirmelerini olmayacak. Son güncelleştirme, Windows 10 makinelerde en son sorun keşfedin geri almak için bu seçeneği ne zaman kullanabileceğinize bir örnek olduğu.  

Kaldırma kullanırken aşağıdakileri göz önünde bulundurun:  
- Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir.  

- Özelliği kaldırmak veya kalite güncelleştirmeleri, Windows 10 makineler önceki güncelleştirmeye geri yüklemek için bir ilke tetikler.  

- Kalite güncelleştirme başarıyla geri alındıktan sonra bir Windows 10 cihazında bulunan son kullanıcılara listelenen güncelleştirmeyi görmeye devam **Windows ayarları** > **güncelleştirmeleri**  >  **Güncelleştirme geçmişi**.  

- Özel özellik güncelleştirmelerinin için özellik güncelleştirmesini kaldırma güncelleştirme kademeleri güncelleştirme ayarında yapılandırılan 2-60 gün cinsinden sınırlı zamandır **özellik güncelleştirmesini kaldırma süresini Ayarla (2-60 gün)**. Özellik Güncelleştirme için yapılandırılan süre kaldırmak daha uzun yüklendikten sonra bir cihazda yüklü olan bir özellik güncelleştirmesini geri alamazsınız.  

  Örneğin, bir özellik ile güncelleştirme halkası düşünün güncelleştirmesini kaldırma süresini 20 güne. 25 gün sonra en son özellik güncelleştirmesine geri alma ve Kaldır seçeneğini kullanmak karar verin.  Özellik güncelleştirmesini üzerinde 20 gün önce yüklü olduğu cihazlara bakım işleminin bir parçası olarak gerekli bitleri kaldırdıysanız gibi kaldıramazsınız. Ancak, bunlar başarıyla 20 gün kaldırma süresi aşan önce kaldırma komutu almak üzere giriş yalnızca özellik güncelleştirmesini yukarı 19 gün önce yüklü olduğu cihazlara güncelleştirme kaldırabilirsiniz.  

Windows Update ilkeleri hakkında daha fazla bilgi için bkz. [CSP'yi güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp) Windows istemci yönetim belgelerinde.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>En son Windows 10 güncelleştirme kaldırmak için  
1. Duraklatılmış bir güncelleştirme kademesi için bir genel bakış sayfası görüntülerken seçin **kaldırma**.  
2. Ya da kaldırmak için kullanılabilir seçenekler arasından seçim **özellik** veya **kalite** güncelleştirmeleri tıklayın ve ardından **Tamam**.  
3. Bir güncelleştirme türünü kaldırma işlemini tetikleme sonra kalan güncelleştirme türü yeniden kaldırmak için Uninstall seçebilirsiniz.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Güncelleştirme ayarlarını Azure portalına geçirme  
Ayrıca Azure klasik portalındaki cihaz yapılandırma profilinde de sınırlı sayıda Windows 10 güncelleştirme ayarı bulunur. Bu ayarlardan herhangi birini yapılandırdıysanız Azure portalına geçiş sırasında aşağıdakileri yapmanız kesinlikle önerilir:  

1. Azure portalında ihtiyaç duyduğunuz ayarlara sahip Windows 10 güncelleştirme kademeleri oluşturun. **Yayın öncesi özelliklere izin ver** ayarı, en son Windows 10 derlemelerinde geçerli olmadığından Azure portal’da desteklenmez. Windows 10 güncelleştirme kademeleri oluştururken kalan üç ayarı ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.  

   > [!NOTE]  
   > Klasik portalda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portalında görüntülenmez. Ancak bu ayarlar uygulanır. Bu ayarlardan herhangi birini geçirir ve geçirilen ilkeyi Azure portalından düzenlerseniz söz konusu ayarlar ilkeden kaldırılır.  

2. Güncelleştirme ayarlarını klasik portaldan silin. Azure portalına geçiş yaptıktan ve aynı ayarları bir güncelleştirme halkasına ekledikten sonra, olası ilke çakışmalarını önlemek için ayarları klasik portalda silmeniz gerekir. Örneğin aynı ayar farklı değerlerle yapılandırılırsa bir çakışma olur. Klasik portalda yapılandırdığınız ayar Azure portalında görüntülemez bilmek kolay bir yol değil.  

## <a name="next-steps"></a>Sonraki adımlar
[Windows Intune tarafından desteklenen ayarlarını güncelleştirme](windows-update-settings.md)  

[Güncelleştirmeler için Intune uyumluluk raporları](windows-update-compliance-reports.md)

