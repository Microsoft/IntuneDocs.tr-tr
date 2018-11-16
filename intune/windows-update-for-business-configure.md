---
title: Microsoft Intune - Azure’da İş İçin Windows Update’i yapılandırma | Microsoft Docs
description: Windows 10 cihazlarda Microsoft Intune kullanarak İş İçin Windows Update ayarlarında bir güncelleştirme halkası oluşturmak, uyumluluğu gözden geçirmek ve güncelleştirmeleri duraklatmak için bir profildeki Yazılım Güncelleştirme ayarlarını güncelleştirin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: 0e82a63cfbbb0780566f9dc1f4ddf0b914e4ca2c
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576843"
---
# <a name="manage-software-updates-in-intune"></a>Intune’da yazılım güncelleştirmelerini yönetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Hizmet olarak Windows, Windows 10 cihazları güncelleştirmenin yoludur. Windows 10 ile yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri kapsar. En son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İş İçin Windows Update kullanarak güncelleştirme yönetimi deneyimini basitleştirirsiniz. Cihaz grupları için ayrı ayrı güncelleştirmeleri onaylamanız gerekmez. Bir güncelleştirmeyi piyasaya sunma stratejisi yapılandırarak ortamlarınızda riskleri yönetebilirsiniz. Bunun yanı sıra Windows Update, güncelleştirmelerin doğru zamanda yüklenmesini sağlar. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini geciktirme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme halkalarını** yapılandırmak ve yönetmek için Intune kullanın. Güncelleştirme halkası, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Örneğin, aşağıdaki ayarları yapılandırabilirsiniz:

- **Windows 10 Hizmet Kanalı**: Cihaz gruplarının güncelleştirmeleri almasını istediğiniz hizmet kanalını seçin. Aşağıdaki kanallar kullanılabilir: 
  - Yarı&#8208;Yıllık Kanal
  - Yarı&#8208;Yıllık Kanal (Hedefli)
  - Windows Insider &#8208; Hızlı
  - Windows Insider &#8208; Yavaş
  - Windows Insider Yayımlama 
      
  Kullanılabilir hizmet kanalları hakkında ayrıntılar için bkz. [Hizmet olarak Windows’a genel bakış](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels).
- **Erteleme Ayarları**: Cihaz gruplarının güncelleştirme yüklemelerini erteleyen erteleme ayarlarını yapılandırın. Güncelleştirme dağıtımınızı aşamalandırarak güncelleştirme boyunca ilerleme durumunu gözden geçirmek için bu ayarları kullanın.
- **Duraklatma**: Güncelleştirme dağıtımı sırasında bir sorun varsa, güncelleştirme yüklemesini erteleyebilirsiniz. 
- **Bakım penceresi**: Güncelleştirmelerin hangi saatler arasında yüklenebileceğini yapılandırın.
- **Güncelleştirme türü**: Yüklenecek güncelleştirme türlerini seçin. Örneğin, Kalite Güncelleştirmeleri, Özellik Güncelleştirmeleri veya sürücüleri seçebilirsiniz.
- **Yükleme davranışı**: Güncelleştirmelerin nasıl yükleneceğini yapılandırır. Örneğin, cihaz yüklemeden sonra otomatik olarak yeniden başlatılacak mı?
- **Eşler arası indirme**: Eşler arası indirme özelliğini yapılandırmak isteyip istemediğinizi seçin. Bu özelliği yapılandırırsanız, bir cihaz güncelleştirmeyi indirmeyi bitirdiğinde diğer cihazlar güncelleştirmeyi bu cihazdan indirebilir. Bu ayar, indirme işlemini hızlandırır.

Güncelleştirme kademeleri oluşturduktan sonra bunları cihaz gruplarına atayabilirsiniz. Güncelleştirme kademelerini kullanarak işletmenizin ihtiyaçlarına uygun bir güncelleştirme stratejisi oluşturabilirsiniz. Daha fazla bilgi için bkz. [İşletmeler için Windows Update'i kullanarak güncelleştirmeleri yönetme](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Başlamadan önce

- Windows 10 bilgisayarlarının güncelleştirilebilmesi için en az Windows 10 Yıldönümü güncelleştirmesi yapılmış Windows 10 Pro çalıştırıyor olmaları gerekir.

- Windows Update, Windows 10'un aşağıdaki sürümlerini destekler:
  - Windows 10
  - Windows 10 Team (Surface Hub cihazları için)
  - [Windows Holographic for Business](#windows-holographic-for-business-support)

  Windows 10 Mobile çalıştıran cihazlar desteklenmez.

- Windows cihazlarında **Geri Bildirim ve Tanılama** > **Tanılama ve kullanım verileri** seçeneği, en az **Temel** olarak ayarlanmış olmalıdır.

    ![Tanılama ve kullanım verileri için Windows ayarı](./media/telemetry-basic.png)

    Bu ayarı el ile yapılandırabilir veya Windows 10 ve üzeri için bir Intune profili kullanabilirsiniz (**Cihaz kısıtlamaları** > **Raporlama ve Telemetri** > **Kullanım verilerini paylaş**’ı en az **Temel** olarak ayarlayın). Cihaz profilleri hakkında daha fazla bilgi için bkz. [cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md).

- Ayrıca Azure klasik portalındaki cihaz yapılandırma profilinde de sınırlı sayıda Windows 10 güncelleştirme ayarı bulunur. Azure portala geçerken bu ayarlardan herhangi biri yapılandırılmışsa aşağıdakileri yapmanızı kesinlikle öneririz:

  1. Azure portalında ihtiyaç duyduğunuz ayarlara sahip Windows 10 güncelleştirme kademeleri oluşturun. **Yayın öncesi özelliklere izin ver** ayarı, en son Windows 10 derlemelerinde geçerli olmadığından Azure portal’da desteklenmez. Güncelleştirme halkalarını oluştururken kalan ayarları ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.

   > [!NOTE]
   > Klasik portalda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portalında görüntülenmez. Ancak bu ayarlar uygulanır. Bu ayarlardan herhangi birini geçirir ve geçirilen ilkeyi Azure portalından düzenlerseniz söz konusu ayarlar ilkeden kaldırılır.

  2. Güncelleştirme ayarlarını klasik portaldan silin. Azure portalına geçiş yaptıktan ve aynı ayarları bir güncelleştirme halkasına ekledikten sonra, olası ilke çakışmalarını önlemek için ayarları klasik portaldan silin. Örneğin aynı ayar farklı değerlerle yapılandırılırsa bir çakışma olur. Bunu anlamanın kolay bir yolu yoktur çünkü klasik portalda yapılandırılan ayarlar Azure portalda görüntülenmez.

## <a name="create-and-assign-update-rings"></a>Güncelleştirme halkaları oluşturma ve atama

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve daha sonra **Microsoft Intune**’u seçin.
2. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları** > **Oluştur**’u seçin.
3. Bir ad ve açıklama (isteğe bağlı) girin ve ardından **Yapılandır**’ı seçin.
4. **Ayarlar**’da aşağıdaki bilgileri girin:

   - **Hizmet kanalı**: Cihazın Windows güncelleştirmelerini alacağı kanalı ayarlayın.
   - **Microsoft ürün güncelleştirmeleri**: Microsoft Update’ten uygulama güncelleştirmeleri için tarama yapmayı seçin.
   - **Windows sürücüleri**: Güncelleştirmeler sırasında Windows Update sürücülerini hariç tutmayı seçin.
   - **Otomatik güncelleştirme davranışı**: Otomatik güncelleştirmelerin nasıl yüklendiğini ve ne zaman yeniden başlatılacağını seçin. Ayrıntılı bilgi için bkz. [Güncelleştir/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).
     - **Otomatik davranış sıklığı**: Güncelleştirme davranışı olarak **Zamanlanan tarih ve saatte otomatik olarak yükle ve yeniden başlat**’ı seçerseniz bu ayar gösterilir. Bu ayarı kullanarak güncelleştirmelerin yüklenmesini hafta, gün ve saat olarak zamanlayın.

   - **Yeniden başlatma denetimleri**: Varsayılan olarak etkindir. Bir cihazı yeniden başlattığınızda ortaya çıkan bazı denetimler vardır; örneğin etkin kullanıcı, pil düzeyi, çalışan oyunlar vb. Cihazı yeniden başlattığınızda bu denetimleri atlamak için **Atla**’yı seçin.

   - **Kalite güncelleştirmesi geciktirme süresi (gün)**: Kalite güncelleştirmelerinin kaç gün geciktirileceğini girin. Bu Kalite Güncelleştirmelerini almayı, yayımlanmalarından sonra 30 güne kadar geciktirebilirsiniz.

     Kalite Güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltme ve iyileştirmelerdir ve her ayın ikinci salı günü yayımlanır. İş için Windows Update yoluyla dağıtılan Kalite Güncelleştirmeleri, Microsoft tarafından herhangi bir anda başka güncelleştirmeler yayımlansa bile yalnızca bu güncelleştirmeleri (‘B’ yayını) alır. Kalite Güncelleştirmeleri, Windows Update’te kullanılabilir olduktan sonra bunları geciktirmeyi seçebilir ve ne kadar süre geciktireceğinizi belirtebilirsiniz. Daha fazla bilgi için bkz. [İş için Windows Update’i kullanarak güncelleştirme dağıtma](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).

   - **Özellik güncelleştirmesi geciktirme süresi (gün)**: Özellik Güncelleştirmelerinin kaç gün geciktirileceğini girin. Bu Özellik Güncelleştirmelerini almayı, yayımlanmalarından sonra 180 güne kadar geciktirebilirsiniz.

     Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir. **Hizmet kanalı** ayarını yapılandırdıktan sonra Özellik Güncelleştirmeleri, Windows Update’te kullanılabilir olduktan sonra bunları geciktirmeyi seçebilir ve ne kadar süre geciktireceğinizi belirtebilirsiniz.

     Örneğin: **Hizmet kanalı, Yarı Yıllık Kanal (Hedefli) olarak ayarlı ve geciktirme süresi 30 gün ise**: Diyelim ki X Özellik Güncelleştirmesi Windows Update’te önce herkese açık şekilde Ocak ayında Yarı Yıllık Kanal (Hedefli) olarak yayımlandı. Cihaz bu güncelleştirmeyi Şubat ayına kadar (30 gün sonrası) almaz.

     **Hizmet kanalı, Yarı Yıllık Kanal olarak ayarlı ve geciktirme süresi 30 gün ise**: Diyelim ki X Özellik Güncelleştirmesi, Windows Update’te önce herkese açık şekilde Ocak ayında Yarı Yıllık Kanal (Hedefli) olarak yayımlandı. X Özellik Güncelleştirmesi, dört ay sonra nisanda Yarı Yıllık Kanal kapsamında yayımlanıyor. Cihaz, Özellik Güncelleştirmesini bu Yarı Yıllık Kanal sürümünden 30 gün sonra alır ve Mayıs ayında güncelleştirilir.

   - **Teslim iyileştirme indirme modu**: Cihazların Windows güncelleştirmelerini indirme yöntemini seçin. Ayrıntılar için bkz. [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

5. İşiniz bittiğinde **Tamam**’ı seçin. **Güncelleştirme Halkası Oluştur**’da **Oluştur**’u seçin.

Yeni güncelleştirme kademesi, güncelleştirme kademeleri listesinde görünür.

1. Kademeyi atamak için, güncelleştirme kademeleri listesinde kademeyi ve sonra <*kademe adı*> sekmesinde **Atamalar**’ı seçin.
2. Sonraki sekmede **Dahil edilecek grupları seçin** öğesini ve sonra bu kademeyi atamak istediğiniz grupları seçin.
3. İşiniz bittiğinde **Seç**’i seçerek atama işlemini tamamlayın.

## <a name="update-compliance-reporting"></a>Güncelleştirme uyumluluğunu raporlama
Güncelleştirme uyumluluğunu, Intune’da Güncelleştirme Uyumluluğu adlı ücretsiz bir çözümü kullanarak görüntüleyebilirsiniz.

### <a name="review-update-compliance-in-intune"></a>Intune’da güncelleştirme uyumluluğunu gözden geçirme 
<!-- 1352223 --> Yapılandırdığınız Windows 10 güncelleştirme halkalarının dağıtım durumunu görüntülemek için bir ilke raporunu gözden geçirin.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve daha sonra **Microsoft Intune**’u seçin.
2. **Yazılım güncelleştirmeleri** > **Genel bakış**’ı seçin. Atadığınız tüm güncelleştirme halkalarının durumu hakkında genel bilgileri görebilirsiniz.
3. Aşağıdaki raporlardan birini açın:

   **Tüm dağıtım halkaları için**:  
   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları**’nda
   2. **İzle** bölümünde **Uygulama başına halka dağıtım durumu**’nu seçin.

   **Belirli dağıtım halkaları için**:  
   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları**’nda gözden geçirmek istediğiniz dağıtım kademesini seçin.
   2. **İzle** bölümünde, güncelleştirme halkası hakkında ayrıntılı bilgileri görüntülemek için aşağıdaki raporlardan birini seçin:
      - **Cihaz durumu**
      - **Kullanıcı durumu**

### <a name="review-update-compliance-using-oms"></a>OMS kullanarak güncelleştirme uyumluluğunu gözden geçirme
Windows 10 güncelleştirme dağıtımlarını, Güncelleştirme Uyumluluğu adlı ücretsiz bir çözümü kullanarak izleyebilirsiniz. Ayrıntılı bilgi için bkz. [Windows Güncelleştirmelerini Güncelleştirme Uyumluluğu ile İzleme](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Bu çözümü kullandığınızda, güncelleştirme uyumluluğunu raporlamak istediğiniz Intune tarafından yönetilen herhangi bir Windows 10 cihazınıza bir ticari kimlik dağıtabilirsiniz.

Intune konsolunda özel bir ilkenin OMA-URI ayarlarını kullanarak ticari kimliği yapılandırabilirsiniz. Ayrıntılı bilgi için bkz. [Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Ticari kimliği yapılandırmaya ilişkin OMA-URI (büyük/küçük harfe duyarlı) yolu: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:

- **Ayar Adı**: Windows Analytics Ticari Kimliği
- **Ayar Açıklaması**: Windows Analytics çözümleri için ticari kimliği yapılandırma
- **OMA-URI** (büyük/küçük harfe duyarlı): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Veri Türü:** Dize
- **Değer**: <*OMS çalışma alanınızdaki Windows Telemetri sekmesinde gösterilen GUID’yi kullanın*>

![OMA-URI Ayarı - Satırı Düzenleme](./media/commID-edit.png)

> [!NOTE]
> MS DM Sunucusu hakkında daha fazla bilgi için bkz. [DMClient yapılandırma hizmet sağlayıcısı (CSP)](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Güncelleştirmeleri duraklatma
Bir cihazın Özellik Güncelleştirmeleri veya Kalite Güncelleştirmeleri almasını en çok 35 günlük bir süre boyunca duraklatabilirsiniz. En fazla gün sayısı geçtikten sonra duraklatma işlevi otomatik olarak sona erer ve cihaz, kullanılabilecek güncelleştirmeleri bulmak için Windows Güncelleştirmeleri’ni tarar. Bu taramanın ardından güncelleştirmeleri yeniden duraklatabilirsiniz.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve daha sonra **Microsoft Intune**’u seçin.
2. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları**’nı seçin.
3. Güncelleştirme halkaları listesinde, duraklatmak istediğiniz halkayı seçin ve sonra duraklatmak istediğiniz güncelleştirme türünü bağlı olarak **...** > **Kaliteyi Duraklat** > veya **Özelliği Duraklat**’ı seçin.

> [!IMPORTANT]
> Bir duraklatma komutu verdiğinizde, cihazlar bu komutu hizmete bir sonraki giriş yaptıkları sırada alır. Bu nedenle, hizmete giriş yapmadan önce, zamanlanmış bir güncelleştirmenin yüklenmesi mümkündür.
> Ayrıca, hedeflenen bir cihaz duraklatma komutunu verdiğiniz sırada kapalıysa bu cihaz açıldığında Intune’u denetlemeden önce, zamanlanmış güncelleştirmeleri indirip yükleyebilir.

### <a name="uninstall-the-latest-from-windows-10-software-updates"></a>En son Windows 10 yazılım güncelleştirmesini kaldırma 
Windows 10 makinelerinizde çalışmanın kesilmesine neden olan bir sorun varsa, en son özellik güncelleştirmesini veya en son kalite güncelleştirmesini kaldırmayı (geri almayı) seçebilirsiniz. Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir. Kaldırma işlemi, Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemeye yönelik bir ilkeyi tetikler. Özellik güncelleştirmeleri için, en son sürümü kaldırma işleminin uygulanabilme süresini 2-60 gün arasıyla sınırlandırabilirsiniz. Yazılım güncelleştirmesini kaldırma seçeneklerini ayarlamak için:

1. Intune’da **Yazılım güncelleştirmeleri**’ni seçin.
2. **Windows 10 Güncelleştirme Halkaları**’nı, mevcut bir güncelleştirme halkasını ve **Kaldır**’ı seçin.

> [!NOTE]
> Windows 10 makinelerde kalite güncelleştirmesi başarıyla geri alındıktan sonra son kullanıcılar, **Windows ayarları** > **Güncelleştirmeler** > **Güncelleştirme Geçmişi**’nde listelenen güncelleştirmeyi görmeye devam eder.

## <a name="windows-holographic-for-business-support"></a>Windows Holographic for Business Desteği

Windows Holographic for Business, aşağıdaki ayarları destekler:

- **Otomatik güncelleştirme davranışı**
- **Microsoft ürün güncelleştirmeleri**
- **Bakım kanalı**: **Yarı yıllık kanal** ve **Yarı yıllık kanal (Hedefli)** seçeneklerini destekler
