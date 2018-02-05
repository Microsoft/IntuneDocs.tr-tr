---
title: "Intune’da İş İçin Windows Update ayarlarını yapılandırma"
titleSuffix: Azure portal
description: "Windows 10 cihazlarına yönelik güncelleştirmeleri denetlemek amacıyla Intune’da İş İçin Windows Update ayarlarını yapılandırmayı öğrenin.\""
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: fa9b09f97568b54a68f34a609c91426eb12b71e0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="manage-software-updates"></a>Yazılım güncelleştirmelerini yönetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Hizmet olarak Windows, Windows 10 cihazları güncelleştirmenin yoludur. Windows 10 ile yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri kapsar. Böylece, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İşletmeler için Windows Update’i kullanarak güncelleştirme yönetimi deneyimini, cihaz grupları için tek tek güncelleştirmelerin onaylanması gerekmeyecek şekilde basitleştirebilirsiniz. Ortamlarınızdaki riski yönetmek amacıyla bir güncelleştirme dağıtım stratejisi yapılandırabilirsiniz. Böylece Windows Update güncelleştirmelerin doğru zamanda yüklenmesini sağlar. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme halkalarını** yapılandırmak ve yönetmek için Intune kullanın. Güncelleştirme kademesi, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Örneğin, aşağıdakileri yapılandırabilirsiniz:

- **Windows 10 Bakım Kanalı**: Cihaz gruplarının güncelleştirmeleri Yarı Yıllık Kanal (Hedefli) veya Yarı Yıllık Kanal’ın hangisinden almasını istediğinizi seçin.  
- **Erteleme Ayarları**: Cihaz gruplarının güncelleştirme yüklemelerini erteleyen erteleme ayarlarını yapılandırın. Aşamalı bir güncelleştirme dağıtımı oluşturarak güncelleştirme boyunca ilerleme durumunu gözden geçirmek için bu ayarları kullanın.
- **Duraklatma**: Güncelleştirme dağıtımı sırasında herhangi bir noktada bir sorun keşfederseniz güncelleştirmelerin yüklenmesini erteleyin.
- **Bakım penceresi**: Güncelleştirmelerin hangi saatler arasında yüklenebileceğini yapılandırın.
- **Güncelleştirme türü**: Yüklenecek güncelleştirme türlerini seçin. Örneğin, Kalite Güncelleştirmeleri, Özellik Güncelleştirmeleri veya sürücüleri seçebilirsiniz.
- **Yükleme davranışı**: Güncelleştirmelerin nasıl yükleneceğini yapılandırır. Örneğin, cihaz yüklemeden sonra otomatik olarak yeniden başlatılacak mı?
- **Eşler arası indirme**: Eşler arası indirme özelliğini yapılandırmak isteyip istemediğinizi belirtin. Bu özelliği yapılandırırsanız, bir cihaz güncelleştirmeyi indirmeyi bitirdiğinde diğer cihazlar güncelleştirmeyi bu cihazdan indirebilir. Bu sayede indirme işlemi hızlandırılmış olur.

Güncelleştirme kademeleri oluşturduktan sonra bunları cihaz gruplarına atayabilirsiniz. Güncelleştirme kademelerini kullanarak işletmenizin ihtiyaçlarına uygun bir güncelleştirme stratejisi oluşturabilirsiniz. Daha fazla bilgi için bkz. [İşletmeler için Windows Update'i kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Başlamadan önce

- Windows 10 bilgisayarlarının güncelleştirilebilmesi için en az Windows 10 Yıldönümü güncelleştirmesi yapılmış Windows 10 Pro çalıştırıyor olmaları gerekir.

- Windows Update, Windows 10'un aşağıdaki sürümlerini destekler:
    - Windows 10
    - Windows 10 Team (Surface Hub cihazları için)

 Windows 10 Mobile ve Windows 10 Holographic çalıştıran cihazlar desteklenmez.

- Windows cihazlarında **Geri Bildirim ve Tanılama** > **Tanılama ve kullanım verileri** seçeneği, en az **Temel** olarak ayarlanmış olmalıdır.

    ![Tanılama ve kullanım verileri için Windows ayarı](./media/telemetry-basic.png)

    Bu ayarı el ile yapılandırabilir veya Windows 10 ve üzeri sürümlerine yönelik bir Intune cihaz kısıtlama profili kullanabilirsiniz. Bunu gerçekleştirmek için **Genel** > **Tanılama verisi gönderme** ayarını en az **Temel** olarak yapılandırın. Cihaz profilleri hakkında daha fazla bilgi için bkz. [Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md).

- Intune yönetim konsolunda yazılım güncelleştirmelerinin davranışını denetleyen dört ayar vardır. Bu ayarlar, Windows 10 masaüstü ve Windows 10 Mobile cihazlarına ait genel yapılandırma ilkesinin bir parçasıdır:
    - **Otomatik güncelleştirmelere izin ver**
    - **Yayın öncesi özelliklere izin ver**
    - **Zamanlanan Yükleme Günü**
    - **Zamanlanan Yükleme Saati**

  Ayrıca klasik portaldaki cihaz yapılandırma profilinde de sınırlı sayıda Windows 10 güncelleştirme ayarı bulunur. Intune yönetim konsolunda bu ayarlardan herhangi birini yapılandırdıysanız Azure portalına geçiş sırasında aşağıdakileri yapmanız kesinlikle önerilir:

1. Azure portalında ihtiyaç duyduğunuz ayarlara sahip Windows 10 güncelleştirme kademeleri oluşturun. **Yayın öncesi özelliklere izin ver** ayarı, en son Windows 10 derlemelerinde geçerli olmadığından Azure portalında desteklenmez. Windows 10 güncelleştirme kademeleri oluştururken kalan üç ayarı ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.

  > [!NOTE]
  > Klasik portalda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portalında görüntülenmez. Ancak, bu ayarlar uygulanamaya devam edilir. Bu ayarlardan herhangi birini geçirdiyseniz ve geçirilen ilkeyi Azure portalından düzenlerseniz söz konusu ayarlar ilkeden kaldırılır.

2. Güncelleştirme ayarlarını klasik portaldan silin. Azure portalına geçiş yaptıktan ve aynı ayarları bir güncelleştirme kademesine ekledikten sonra olası ilke çakışmalarını önlemek için ayarları klasik portalda silmeniz gerekir. Örneğin, aynı ayar farklı değerlerle yapılandırıldığında bir çakışma oluşur ve klasik portalda yapılandırdığınız ayar Azure portalında görüntülenmediğinden bunun fark edilmesi zor olabilir.

## <a name="how-to-create-and-assign-update-rings"></a>Güncelleştirme kademeleri oluşturma ve atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Yazılım Güncelleştirmeleri**’ni seçin.
4. **Yazılım Güncelleştirmeleri** dikey penceresinde **Yönet** > **Windows 10 Güncelleştirme Kademeleri**’ni seçin.
5. Güncelleştirme kademeleri listesinin gösterildiği dikey pencerede **Oluştur**’u seçin.
6. **Güncelleştirme Kademesi Oluştur** dikey penceresinde güncelleştirme kademesi için bir ad ve isteğe bağlı olarak bir açıklama girin ve sonra **Ayarlar**’ı seçin.
7. **Ayarlar** dikey penceresinde aşağıdaki bilgileri yapılandırın:
    - **Bakım kanalı**: Cihazın Windows güncelleştirmelerini alacağı kanalı ayarlayın (Yarı Yıllık Kanal (Hedefli) veya Yarı Yıllık Kanal).
    - **Microsoft güncelleştirmeleri**: Microsoft Update’ten uygulama güncelleştirmeleri için tarama yapılıp yapılmayacağını seçin.
    - **Windows sürücüleri**: Güncelleştirmeler sırasında Windows Update sürücülerini hariç tutmak isteyip istemediğinizi seçin.
    - **Otomatik güncelleştirme davranışı**: Tarama, indirme ve güncelleştirmeleri yükleme ile ilgili otomatik güncelleştirme davranışlarının nasıl yönetileceğini seçin. Ayrıntılı bilgi için bkz. [Güncelleştir/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Kalite güncelleştirmesi erteleme dönemi (gün)**: Kalite güncelleştirmelerinin kaç gün erteleneceğini belirtin. Bu Kalite Güncelleştirmelerini almayı yayımlanmalarından sonra 30 güne kadar erteleyebilirsiniz.  

    Kalite Güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltme ve iyileştirmelerdir. Normal olarak her ayın ilk salı günü yayımlanırlar ancak Microsoft tarafından herhangi bir zamanda yayımlanmaları mümkündür. Kullanıma sunulduktan sonra Kalite Güncelleştirmelerinin alınmasını ertelemek isteyip istemediğinizi ve ne kadar süreyle erteleyeceğinizi tanımlayabilirsiniz.
    - **Özellik güncelleştirmesi erteleme dönemi (gün)**: Özellik Güncelleştirmelerinin kaç gün erteleneceğini belirtin. Bu Özellik Güncelleştirmelerini almayı yayımlanmalarından sonra 180 güne kadar erteleyebilirsiniz.

    Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir. **Bakım kanalı** ayarını yapılandırmanızın ardından (Yarı Yıllık Kanal (Hedefli) veya Yarı Yıllık Kanal), Microsoft tarafından Windows Update'te kullanıma sunulduktan sonra Özellik Güncelleştirmelerinin alınmasını ertelemek isteyip istemediğinizi ve ne kadar süreyle erteleyeceğinizi tanımlayabilirsiniz.

    Örneğin:  
    **Bakım kanalı Yarı Yıllık Kanal (Hedefli) olarak ayarlı ve erteleme süresi 30 gün ise**: Diyelim ki X Özellik Güncelleştirmesi Windows Update’te önce herkese açık şekilde ocak ayında Yarı Yıllık Kanal (Hedefli) olarak yayımlandı. Cihaz bu güncelleştirmeyi Şubat ayına kadar (30 gün sonra) almaz.

    **Bakım kanalı Yarı Yıllık Kanal olarak ayarlı ve erteleme süresi 30 gün ise**: Diyelim ki X Özellik Güncelleştirmesi Windows Update’te önce herkese açık şekilde ocak ayında Yarı Yıllık Kanal (Hedefli) olarak yayımlandı. X Özellik Güncelleştirmesi, dört ay sonra nisanda Yarı Yıllık Kanal kapsamında yayımlanıyor. Cihaz, Özellik Güncelleştirmesini bu Yarı Yıllık Kanal sürümünden 30 gün sonra alır ve mayıs ayında güncelleştirilir.

    - **Teslim iyileştirme**: Cihazların Windows güncelleştirmelerini indireceği yöntemi seçin. Ayrıntılar için bkz. [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).
1. İşiniz bittiğinde **Tamam**’a ve sonra da **Güncelleştirme Kademesi Oluştur** dikey penceresinde **Oluştur**’a tıklayın.

Yeni güncelleştirme kademesi, güncelleştirme kademeleri listesinde görünür.

1. Kademeyi atamak için, güncelleştirme kademeleri listesinde kademeyi ve sonra <*kademe adı*> sekmesinde **Atamalar**’ı seçin.
2. Sonraki sekmede **Grup Seç**‘i ve sonra bu kademeyi atamak istediğiniz grupları seçin.
3. İşiniz bittiğinde **Seç**’i seçerek atama işlemini tamamlayın.

## <a name="update-compliance-reporting"></a>Güncelleştirme uyumluluğunu raporlama
Güncelleştirme uyumluluğunu, Intune’da veya Operations Management Suite’teki (OMS) Güncelleştirme Uyumluluğu adlı ücretsiz bir çözümü kullanarak görüntüleyebilirsiniz.

### <a name="review-update-compliance-in-intune"></a>Intune’da güncelleştirme uyumluluğunu gözden geçirme 
<!-- 1352223 -->
Yapılandırdığınız Windows 10 güncelleştirme halkalarının dağıtım durumunu görüntülemek için bir ilke raporunu gözden geçirin. 
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Yazılım Güncelleştirmeleri**’ni seçin.
4. **Yazılım Güncelleştirmeleri** dikey penceresinde **Genel Bakış**’ı seçin. Burada, atadığınız tüm güncelleştirme halkalarının durumu hakkında genel bilgileri bulabilirsiniz.
5. Aşağıdaki raporlardan birini açın: 
     
   **Tüm dağıtım halkaları için:**
   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları** dikey penceresinde. 
   2. **İzle** bölümünde **Uygulama başına halka dağıtım durumu**’nu seçin.
                   
   **Belirli dağıtım halkaları için:** 
   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları** dikey penceresinde, gözden geçirmek istediğiniz dağıtım halkasını seçin.
   2. **İzle** bölümünde, güncelleştirme halkası hakkında ayrıntılı bilgileri görüntülemek için aşağıdaki raporlardan birini seçin:
      - **Cihazlar için güncelleştirme halkası dağıtımı**
      - **Kullanıcılar için güncelleştirme halkası dağıtımı**
      - **Ayar başına dağıtım durumu**

### <a name="review-update-compliance-using-oms"></a>OMS kullanarak güncelleştirme uyumluluğunu gözden geçirme
Windows 10 güncelleştirme dağıtımlarını, Operations Management Suite’teki (OMS) Güncelleştirme Uyumluluğu adlı ücretsiz bir çözümü kullanarak izleyebilirsiniz. Ayrıntılı bilgi için bkz. [Windows Güncelleştirmelerini Güncelleştirme Uyumluluğu ile İzleme](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Bu çözümü kullandığınızda, güncelleştirme uyumluluğunu raporlamak istediğiniz Intune tarafından yönetilen herhangi bir Windows 10 cihazınıza bir ticari kimlik dağıtabilirsiniz.

Intune konsolunda özel bir ilkenin OMA-URI ayarlarını kullanarak ticari kimliği yapılandırabilirsiniz. Ayrıntılı bilgi için bkz. [Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Ticari kimliği yapılandırmaya ilişkin OMA-URI (büyük/küçük harfe duyarlı) yolu: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:

- **Ayar Adı**: Windows Analytics Ticari Kimliği
- **Ayar Açıklaması**: Windows Analytics çözümleri için ticari kimliği yapılandırma
- **Veri Türü:** Dize
- **OMA-URI** (büyük/küçük harfe duyarlı): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Değer**: <*OMS çalışma alanınızdaki Windows Telemetri sekmesinde gösterilen GUID’yi kullanın*>

![Tanılama ve kullanım verileri için Windows ayarı](./media/commID.png)

## <a name="how-to-pause-updates"></a>Güncelleştirmeleri duraklatma
Bir cihazın Özellik Güncelleştirmeleri veya Kalite Güncelleştirmeleri almasını en çok 35 günlük bir süre boyunca duraklatabilirsiniz. En fazla gün sayısı kadar bir süre geçtikten sonra duraklatma işlevi otomatik olarak sona erer ve cihaz, kullanılabilecek güncelleştirmeleri bulmak için Windows Güncelleştirmelerini tarar. Bu taramanın ardından güncelleştirmeleri yeniden duraklatabilirsiniz.
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Yazılım Güncelleştirmeleri**’ni seçin.
4. **Yazılım Güncelleştirmeleri** dikey penceresinde **Yönet** > **Windows 10 Güncelleştirme Kademeleri**’ni seçin.
5. Güncelleştirme kademeleri listesinin gösterildiği dikey pencerede, duraklatmak istediğiniz kademeyi seçin ve sonra duraklatmak istediğiniz güncelleştirme türünü bağlı olarak **...** > **Kaliteyi Duraklat** > veya **Özelliği Duraklat**’ı seçin.

> [!IMPORTANT]
> Bir duraklatma komutu verdiğinizde, cihazlar bu komutu hizmete bir sonraki giriş yaptıkları sırada alır. Bu nedenle, hizmete giriş yapmadan önce, zamanlanmış bir güncelleştirmenin yüklenmesi mümkündür.
> Ayrıca, hedeflenen bir cihaz duraklatma komutunu verdiğiniz sırada kapalıysa bu cihaz açıldığında Intune’u denetlemeden önce, zamanlanmış güncelleştirmeleri indirip yükleyebilir.
