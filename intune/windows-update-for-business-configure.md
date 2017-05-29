---
title: "İşletmeler için Windows Update ayarlarını yapılandırma - Intune | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Windows 10 cihazlarına yönelik güncelleştirmeleri denetlemek amacıyla Intune’da İşletmeler için Windows Update ayarlarını yapılandırmayı öğrenin."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: b0bc3e557f303cd80c780634ba47b24405c327e1
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-windows-update-for-business-settings-with-microsoft-intune"></a>İşletmeler için Windows Update ayarlarını Microsoft Intune ile yapılandırma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="introduction"></a>Giriş
Hizmet olarak Windows, Windows 10 güncelleştirmeleri sağlamanın yeni yoludur. Windows 10’dan itibaren tüm yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri de kapsayacaktır. Böylece, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın tamamen güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İşletmeler için Windows Update’i kullanarak güncelleştirme yönetimi deneyimini, cihaz grupları için tek tek güncelleştirmelerin onaylanması gerekmeyecek şekilde basitleştirebilirsiniz. Ortamlarınızdaki riski yönetmek amacıyla hala bir güncelleştirme dağıtım stratejisi yapılandırabilirsiniz. Böyle yaptığınızda Windows Update güncelleştirmelerin doğru zamanda yüklenmesini sağlayacaktır. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme kademelerini** yapılandırmak ve yönetmek için Intune’u kullanın. Güncelleştirme kademesi, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Örneğin, aşağıdakileri yapılandırabilirsiniz:

- **Windows 10 Bakım Dalı**: Cihaz gruplarının güncelleştirmeleri Güncel Dalı üzerinden mi yoksa İş İçin Güncel Dalı üzerinden mi alacağını seçin.  
- **Erteleme Ayarları**: Cihaz gruplarının güncelleştirme yüklemelerini erteleyen erteleme ayarlarını yapılandırın. Böylece, aşamalı bir güncelleştirme dağıtımı oluşturarak ilerleme durumunu güncelleştirme boyunca gözden geçirebilirsiniz.
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

- Klasik Intune yönetim konsolunda yazılım güncelleştirmelerinin davranışını denetleyen dört ayar vardır. Bu ayarlar, Windows 10 masaüstü ve Windows 10 Mobile cihazlarına ait genel yapılandırma ilkesinin bir parçasıdır:
    - **Otomatik güncelleştirmelere izin ver**
    - **Yayın öncesi özelliklere izin ver**
    - **Zamanlanan Yükleme Günü**
    - **Zamanlanan Yükleme Saati**

  Ayrıca klasik konsoldaki cihaz yapılandırma profilinde de sınırlı sayıda Windows 10 güncelleştirme ayarı bulunur. Klasik Intune yönetim konsolunda bu ayarlardan herhangi birini yapılandırdıysanız Azure portalına geçiş sırasında aşağıdakileri yapmanız önemle önerilir:

1. Azure portalında ihtiyaç duyduğunuz ayarlara sahip Windows 10 güncelleştirme kademeleri oluşturun. **Yayın öncesi özelliklere izin ver** ayarı, en son Windows 10 derlemelerinde geçerli olmadığından Azure portalında desteklenmez. Windows 10 güncelleştirme kademeleri oluştururken kalan üç ayarı ve diğer Windows 10 güncelleştirme ayarlarını yapılandırabilirsiniz.

  > [!NOTE]
  > Klasik konsolda oluşturulan Windows 10 güncelleştirme ayarları geçişten sonra Azure portalında görüntülenmez. Ancak, bu ayarlar uygulanamaya devam edilir. Bu ayarlardan herhangi birini geçirdiyseniz ve geçirilen ilkeyi Azure portalından düzenlerseniz, söz konusu ayarlar ilkeden kaldırılır.

2. Güncelleştirme ayarlarını klasik konsolda silin. Azure portalına geçiş yaptıktan ve aynı ayarları bir güncelleştirme kademesine ekledikten sonra olası ilke çakışmalarını önlemek için ayarları klasik portalda silmeniz gerekir. Örneğin, aynı ayar farklı değerlerle yapılandırıldığında bir çakışma oluşur ve klasik konsolda yapılandırdığınız ayar Azure portalında görüntülenmediğinden bunun fark edilmesi çok zor olabilir.

## <a name="how-to-create-and-assign-update-rings"></a>Güncelleştirme kademeleri oluşturma ve atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Yazılım Güncelleştirmeleri**’ni seçin.
4. **Yazılım Güncelleştirmeleri** dikey penceresinde **Yönet** > **Windows 10 Güncelleştirme Kademeleri**’ni seçin.
5. Güncelleştirme kademeleri listesinin gösterildiği dikey pencerede **Oluştur**’u seçin.
6. **Güncelleştirme Kademesi Oluştur** dikey penceresinde güncelleştirme kademesi için bir ad ve isteğe bağlı olarak bir açıklama girin ve sonra **Ayarlar**’ı seçin.
7. **Ayarlar** dikey penceresinde aşağıdaki bilgileri yapılandırın:
    - **Bakım dalı**: Cihazın hangi dalın Windows güncelleştirmelerini alacağını ayarlayın (Güncel Dalı veya İş İçin Güncel Dalı).
    - **Microsoft güncelleştirmeleri**: Microsoft Update’ten uygulama güncelleştirmeleri için tarama yapılıp yapılmayacağını seçin.
    - **Windows sürücüleri**: Güncelleştirmeler sırasında Windows Update sürücülerini hariç tutmak isteyip istemediğinizi seçin.
    - **Otomatik güncelleştirme davranışı**: Tarama, indirme ve güncelleştirmeleri yükleme ile ilgili otomatik güncelleştirme davranışlarının nasıl yönetileceğini seçin. Ayrıntılı bilgi için bkz. [Güncelleştir/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Kalite güncelleştirmesi erteleme dönemi (gün)**: Kalite güncelleştirmelerinin kaç gün erteleneceğini belirtin. Bu Kalite Güncelleştirmelerini almayı yayımlanmalarından sonra 30 güne kadar erteleyebilirsiniz.  

      Kalite Güncelleştirmeleri, genellikle mevcut Windows işlevselliğine yönelik düzeltme ve iyileştirmelerdir. Normal olarak her ayın ilk salı günü yayımlanırlar ancak Microsoft tarafından herhangi bir zamanda yayımlanmaları mümkündür. Kullanıma sunulduktan sonra Kalite Güncelleştirmelerinin alınmasını ertelemek isteyip istemediğinizi ve ne kadar süreyle erteleyeceğinizi tanımlayabilirsiniz.
    - **Özellik güncelleştirmesi erteleme dönemi (gün)**: Özellik Güncelleştirmelerinin kaç gün erteleneceğini belirtin. Bu Özellik Güncelleştirmelerini almayı yayımlanmalarından sonra 180 güne kadar erteleyebilirsiniz.

    Özellik Güncelleştirmeleri genellikle Windows’un yeni özellikleridir. **Bakım dalı** ayarını yapılandırmanızın ardından (**Güncel Dalı** veya **İş İçin Güncel Dalı**), Microsoft tarafından Windows Update'te kullanıma sunulduktan sonra Özellik Güncelleştirmelerinin alınmasını ertelemek isteyip istemediğinizi ve ne kadar süreyle erteleyeceğinizi tanımlayabilirsiniz.

    Örneğin:  
    **Bakım dalı, Güncel Dalı olarak ayarlanmışsa ve erteleme süresi 30 günse**: X Özellik Güncelleştirmesinin, Windows Update'te Güncel Dalı kapsamında ilk olarak Ocak ayında genel kullanıma sunulduğunu varsayalım. Cihaz bu güncelleştirmeyi Şubat ayına kadar (30 gün sonra) almaz.

    **Bakım dalı, İş İçin Güncel Dalı olarak ayarlanmışsa ve erteleme süresi 30 günse**: X Özellik Güncelleştirmesinin, Windows Update'te Güncel Dalı kapsamında ilk olarak Ocak ayında genel kullanıma sunulduğunu varsayalım. X Özellik Güncelleştirmesi, dört ay sonra Nisan’da İş İçin Güncel Dalı kapsamında yayımlanıyor. Cihaz, Özellik Güncelleştirmesini bu İş İçin Güncel Dalı sürümünden 30 gün sonra alır ve Mayıs ayında güncelleştirilir.

    - **Teslim iyileştirme**: Cihazların Windows güncelleştirmelerini indireceği yöntemi seçin. Ayrıntılar için bkz. [DeliveryOptimization/DODownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode).
8. İşiniz bittiğinde **Tamam**’a ve sonra da **Güncelleştirme Kademesi Oluştur** dikey penceresinde **Oluştur**’a tıklayın.

Yeni güncelleştirme kademesi, güncelleştirme kademeleri listesinde görünür.

1. Kademeyi atamak için, güncelleştirme kademeleri listesinde kademeyi ve sonra <*kademe adı*> sekmesinde **Atamalar**’ı seçin.
2. Sonraki sekmede **Grup Seç**‘i ve sonra bu kademeyi atamak istediğiniz grupları seçin.
3. İşiniz bittiğinde **Seç**’i seçerek atama işlemini tamamlayın.



## <a name="update-compliance-reporting"></a>Güncelleştirme uyumluluğunu raporlama
Windows 10 güncelleştirme dağıtımlarını, Operations Management Suite’teki (OMS) Güncelleştirme Uyumluluğu adlı ücretsiz bir çözümü kullanarak izleyebilirsiniz. Ayrıntılı bilgi için bkz. [Windows Güncelleştirmelerini Güncelleştirme Uyumluluğu ile İzleme](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Bu çözümü kullandığınızda, güncelleştirme uyumluluğunu raporlamak istediğiniz Intune tarafından yönetilen herhangi bir Windows 10 cihazınıza bir ticari kimlik dağıtabilirsiniz.

Intune konsolunda özel bir ilkenin OMA-URI ayarlarını kullanarak ticari kimliği yapılandırabilirsiniz. Ayrıntılı bilgi için bkz. [Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Ticari kimliği yapılandırmaya ilişkin OMA-URI (büyük/küçük harfe duyarlı) yolu: ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:

- **Ayar Adı**: Windows Analytics Ticari Kimliği
- **Ayar Açıklaması**: Windows Analytics çözümleri için ticari kimliği yapılandırma
- **Veri Türü:** Dize
- **OMA-URI** (büyük/küçük harfe duyarlı): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Değer**: <*OMS çalışma alanınızdaki Windows Telemetri sekmesinde gösterilen GUID’yi kullanın*>

![Tanılama ve kullanım verileri için Windows ayarı](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





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

