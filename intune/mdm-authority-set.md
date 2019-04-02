---
title: Mobil cihaz yönetimi yetkilisini ayarlayın
titleSuffix: Microsoft Intune
description: Intune’da mobil cihaz yönetimi yetkilisini ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 898c4eee19aa50136736f4ee72c55e4e8931317d
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799299"
---
# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.

Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir. [MDM yetkilisini Intune konsolundan ayarlama](#set-mdm-authority-to-intune).

- **Intune ortak yönetim** -Windows 10 cihazları için Intune bulut çözümünün System Center Configuration Manager ile tümleştirme. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız. [Intune'da cihazların otomatik kaydını yapılandırma](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >Yeni Karma MDM müşterilerin ekleme kullanım dışıdır. Daha fazla bilgi için [taşıma karma mobil cihaz Yönetimi'nden Intune'a Azure'da](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) blog gönderisi.

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Microsoft 365 Yönetim Merkezi'nden Intune'u siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir. MDM yetkilisini, Microsoft 365 Yönetim Merkezi'nden ayarlama.

> [!IMPORTANT]
> Configuration Manager'ın 1610 veya sonraki bir sürümü ve Microsoft Intune'un 1705 sürümünde, MDM yetkilisini, Microsoft Destek ile iletişim kurmaya ve mevcut yönetilen cihazlarınızın kaydını silip tekrar kaydetmeye gerek kalmadan değiştirebilirsiniz. Ayrıntılar için bkz [MDM yetkilisini Configuration Manager olarak değiştirme hazırlanma](mdm-authority-set.md#prepare-to-change-the-mdm-authority-to-configuration-manager).

## <a name="set-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

MDM yetkilisini henüz ayarlamadıysanız, aşağıdaki adımları izleyin. Bir MDM yetkilisinden bir diğerine geçmek için, aşağıdaki [MDM yetkilisini değiştirme](#prepare-to-change-the-mdm-authority-to-configuration-manager) bölümüne bakın.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Mobil Cihaz Yönetim Yetkilisi** ayarını açmak için turuncu başlığı seçin. Turuncu başlık, ancak henüz MDM yetkilisini ayarlamadıysanız görüntülenir.
4. **Mobil Cihaz Yönetimi Yetkilisi** altında, aşağıdakilerden birini MDM yetkiliniz olarak belirtin:
   - **Intune MDM Yetkilisi**
   - **System Center Configuration Manager MDM Yetkilisi**
   - **Yok.**

   ![Intune tarafından ayarlı mobil cihaz yönetim yetkilisi ekranının ekran görüntüsü](media/set-mdm-auth.png)

   MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

### <a name="workflow-of-intune-administration-ui"></a>Intune Yönetim UI’si iş akışı
Android veya Apple cihaz yönetimi etkinleştirildiğinde Intune, ilgili cihazları yönetmek üzere bu üçüncü taraf hizmetleriyle tümleştirmek için cihaz ve kullanıcı bilgilerini gönderir.

Veri pencerelerini paylaşma onayı ekleyen senaryolar şu durumlarda eklenir:
- Android iş profillerini etkinleştirdiğinizde.
- Apple MDM anında iletme sertifikalarını etkinleştirdiğinizde ve karşıya yüklediğinizde.
- Aygıt Kayıt Programı, School Manager ve Volume Purchasing Program gibi Apple hizmetlerinden herhangi birini etkinleştirdiğinizde.

Bu durumların tamamında onay kesinlikle bir mobil cihaz yönetimi hizmetinin çalışmasıyla ilgilidir. Örneğin bir BT yöneticisinin Google veya Apple cihazların kaydını yetkilendirmesini onaylamak gibi. Yeni iş akışları yayınlandığında hangi bilgilerin paylaşıldığına ilişkin belgeler şu konumlarda bulunabilir:
- [Intune’un Google’a gönderdiği veriler](https://aka.ms/Data-intune-sends-to-google)
- [Intune’un Apple’a gönderdiği veriler](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Dikkat Edilmesi Gereken Önemli Noktalar
Yeni MDM yetkilisine geçtikten sonra cihazın iade edilmesi ve hizmetle eşitlenmesi için bir geçiş süresi (sekiz saate kadar) olması olasıdır. Kayıtlı cihazların değişiklikten sonra yönetilmeye ve korunmaya devam edeceğinden emin olmak için yeni MDM yetkilisinde (karma) ayarları yapılandırmanız gerekir. 
- Yeni MDM yetkilisinden (tek başına Intune) gelen ayarların cihazdaki mevcut ayarların yerini alması için değişiklik sonrasında cihazların hizmete bağlanması gerekir.
- MDM yetkilisini değiştirdikten sonra önceki MDM yetkilisine ait (tek başına Intune) bazı temel ayarlar (profiller gibi) yedi güne kadar veya cihaz hizmete ilk kez bağlanana kadar cihazda kalır. Yeni MDM yetkilisinde (karma) uygulama ve ayarları (ilkeler, profiller, uygulamalar vb.) mümkün olduğunca çabuk yapılandırmanız ve mevcut kayıtlı cihazları olan kullanıcıları barındıran gruplara bu ayarları dağıtmanız önerilir. MDM yetkilisindeki değişiklikten sonra cihaz hizmete ilk bağlandığı zaman, yeni MDM yetkilisinden yeni ayarları alacaktır, böylece yönetim ve korumada boşluk oluşması önlenecektir.
- Aynı cihaz kategorileri hem Intune hem de Configuration Manager’da mevcutsa, yeni MDM yetkilisine geçtiğinizde cihazların cihaz kategorisi atamaları taşınmaz. Cihaz kategorilerini kullanmaya devam etmek için MDM yetkilisi değiştirildikten ve cihazlar Configuration Manager konsolunda gösterilmeye başladıktan sonra aktarılan cihazların uygun koleksiyonlara el ile eklenmesi gerekir.
- İlişkili kullanıcısı olmayan cihazlar (genellikle iOS Aygıt Kayıt Programı veya toplu kayıt senaryoları kullandığınızda ortaya çıkar), yeni MDM yetkilisine geçirilmez. Bu cihazları yeni MDM yetkilisine taşımak için destek ile iletişime geçip yardım almanız gerekir.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>MDM yetkilisini Configuration Manager olarak değiştirmeye hazırlanma

MDM yetkilisindeki değişikliğe hazırlanmak için aşağıdaki bilgileri gözden geçirin:
- MDM yetkilisini değiştirme seçeneğinin açılması için Configuration Manager sürüm 1610 veya üzerine sahip olmanız gerekir.
- Yeni MDM yetkilisine geçtikten sonra bir cihazın hizmete bağlanması sekiz saati bulabilir.
- Configuration Manager konsolunda Intune aboneliğini ayarladığınızda kullanacağınız ve tek Başına Intune tarafından yönetilen tüm kullanıcıları içeren bir Configuration Manager kullanıcı koleksiyonu oluşturun. Bu koleksiyon sayesinde MDM yetkilisindeki değişiklikten sonra kullanıcıların ve kullanıcı cihazlarının kendilerine atanmış bir Configuration Manager lisansı olduğundan ve karma ortamda yönetilebileceklerinden emin olursunuz.
- BT Yöneticisi kullanıcısının da bu koleksiyonda olduğundan emin olun.  
- Değişiklikten önce MDM Yetkilisi, Intune yönetim konsolunda **Microsoft Intune olarak ayarlı** (tek başına) şeklinde görünecektir.
- MDM yetkilisindeki değişiklikten önce MDM Yetkilisi, Microsoft Intune yönetim konsolunda **Microsoft Intune olarak ayarlı** (tek başına kiracı) olarak görüntülenmelidir.
    > [!NOTE]    
    > MDM yetkiliniz **Intune ve Office 365 tarafından yönetiliyor** olarak görünüyorsa MDM yetkilinizi **Configuration Manager** (karma) olarak değiştirdiğinizde, Office 365 tarafından yönetilen MDM cihazlarınız artık yönetilmez. MDM yetkilisini değiştirmeden önce bu kullanıcılara Intune veya Enterprise Mobility Suite lisansı atamanızı öneririz.   

- [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) Cihaz Kayıt Yöneticisi rolünü kaldırın. Ayrıntılar için bkz. [Intune’dan bir cihaz kayıt yöneticisini silme](device-enrollment-manager-enroll.md#remove-device-enrollment-manager-permissions).
- Yapılandırılmış tüm cihaz grup eşlemelerini kapatın. Ayrıntılar için bkz. [Microsoft Intune’da cihazları cihaz grubu eşleme ile kategorilere ayırma](device-group-mapping.md).
- MDM yetkilisindeki değişiklik sırasında son kullanıcılar etkilenmeyecektir. Ancak, cihazlarının açık olduğundan ve değişiklikten hemen sonra hizmete bağlandıklarından emin olmak için son kullanıcılara bu değişikliği bildirmek isteyebilirsiniz. Bu önlemi almanız, olabildiğince çabuk bir şekilde olabildiğince fazla cihazın değişiklik sonrasında hizmete bağlanmasını ve kaydolmasını sağlar.
- MDM yetkilisindeki değişiklikten önce iOS cihazları yönetmek için tek başına Intune kullanıyorsanız, Intune’da önceden kullanılan bu Apple Anında İletilen Bildirim hizmetinin (APNs) Configuration Manager’da (karma) yenilendiğinden ve kiracıyı ayarlamak için kullanıldığından emin olmalısınız.    

    > [!IMPORTANT]  
    > Karma için farklı bir APNs kullanılırsa önceden kaydedilen TÜM iOS cihazların kaydı silinir ve bunlar için yeniden kayıt işlemi yapmanız gerekir. MDM yetkilisindeki değişiklikten önce, Intune’da iOS cihazları yönetmek için tam olarak hangi APNs sertifikasının kullanıldığını öğrenin. Apple Anında İletme Sertifikası Portalı’ndaki (https://identity.apple.com) listede aynı sertifikayı bulun, daha sonra asıl APNs sertifikasını oluştururken Apple Kimliği kullanılan kullanıcının belirlendiğinden ve MDM yetkilisindeki değişikliğin parçası olarak bu APNs sertifikasını yenilemek için kullanıcının uygun olduğundan emin olun.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>MDM yetkilisini Configuration Manager olarak değiştirme

1. Configuration Manager konsolunda **Yönetim** &gt; **Genel Bakış** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve bir Intune aboneliği eklemeyi seçin.
2. Intune’da MDM yetkilisini ayarlarken kullandığınız Intune kiracısında oturum açın ve **İleri**’ye tıklayın.
3. **MDM Yetkilimi Configuration Manager olarak değiştir**’i seçin ve **İleri**’ye tıklayın.
4. Yeni karma MDM yetkilisi tarafından yönetilmeye devam eden tüm kullanıcıları içerecek şekilde kullanıcı koleksiyonunu ayarlayın.
5. Tıklayın **sonraki** ve Sihirbazı tamamlayın. Artık MDM yetkilisi, **Configuration Manager** olarak değiştirildi.
6. Aynı Intune kiracısını kullanarak [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) oturum açın ve MDM yetkilisinin **Configuration Manager olarak ayarla** şeklinde değiştirildiğini doğrulayın.
7. MDM yetkilisini Configuration Manager olarak değiştirdikten sonra [iOS kaydını](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) ve [Android kaydını](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-android) ayarlayabilirsiniz.
8. Configuration Manager konsolunda yeni MDM yetkilisinden (karma) gelen ayarları ve uygulamaları yapılandırın ve dağıtın.

Cihazlar hizmete bağlandığı zaman, yeni MDM yetkilisinden yeni ayarlar eşitlenir ve alınır.

## <a name="change-mdm-authority-to-office-365"></a>MDM yetkilisini Office 365 olarak değiştirme

Mevcut Intune Hizmetinize ek olarak Office 365 MDM’yi etkinleştirmek için [https://protection.office.com](https://protection.office.com) öğesine gidin, **Veri Kaybını Önleme** > **Cihaz Güvenlik İlkeleri** > **Yönetilen Cihazlar listesini görüntüle** > **Başlayalım**’ı seçin.

Daha fazla bilgi için bkz. [Office 365’te Mobil Cihaz Yönetimi (MDM) ayarlama](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Son kullanıcıların yalnızca Office 365 MDM tarafından yönetilmesini istiyorsanız Office 365 MDM’yi etkinleştirdikten sonra atanmış tüm Intune ve/veya EMS lisanslarını kaldırın.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.

## <a name="remove-mdm-authority"></a>MDM yetkilisini kaldırma

MDM yetkilisi tekrar Bilinmeyen olarak değiştirilemez. MDM yetkilisi, kaydedilen cihazların hangi portala (ConfigMGR, Azure Intune, Office 365 MDM) rapor vereceğini belirlemek için Microsoft sunucuları tarafından kullanılır.

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>MDM yetkilisini değiştirdikten sonra ne olur

- Intune hizmeti, bir kiracının MDM yetkilisinin değiştiğini algıladığında kayıtlı tüm cihazlara hizmete iade etmeleri ve hizmetle eşitlenmeleri için bir bildirim iletisi gönderir (bu bildirim, düzenli olarak zamanlanmış iadenin dışındadır). Böylece MDM yetkilisi tek başına Intune’dan karmaya değiştirildikten sonra, açık ve çevrimiçi olan cihazlar hizmete bağlanır, yeni MDM yetkilisini alır ve karma tarafından yönetilmeye başlar. Bu cihazların yönetiminde ve korunmasında bir kesinti olmaz.
- MDM yetkilisindeki değişiklik sırasında (veya hemen sonrasında) açık ve çevrimiçi olan cihazlarda bile, cihazlar yeni MDM yetkilisi altında hizmete kaydolmadan önce sekiz saate kadar (bir sonraki zamanlanmış düzenli iadenin zamanına bağlı olarak) bir gecikme olur.    

  > [!IMPORTANT]    
  > MDM yetkilisini değiştirmeniz ve yeni yetkiliye yenilenmiş APNs sertifikasının yüklenmesi arasında geçen sürede, yeni iOS cihazların kaydı ve bildirimi başarısız olacaktır. Bu nedenle MDM yetkilisindeki değişiklikten hemen sonra APNs sertifikasını gözden geçirmeniz ve yeni yetkiliye yüklemeniz önemlidir.

- Kullanıcılar, el ile cihazdan hizmete iadeyi başlatarak hızlıca yeni MDM yetkilisine geçebilir. Bu değişikliği Şirket Portalı uygulamasını kullanarak ve bir cihaz uyumluluk denetimi başlatarak kolaylıkla yapabilirler.
- Cihazlar, MDM yetkilisindeki değişikliği takiben hizmete iade edildikten ve hizmetle eşitlendikten sonra her şeyin düzgün çalıştığını doğrulamak için Configuration Manager konsolunda cihazları arayın. Önceden Intune tarafından yönetilen cihazlar artık Configuration Manager konsolunda yönetilen cihazlar olarak görüntülenir.    
- Cihaz MDM yetkilisindeki değişiklik sırasında çevrimdışı olduğu zaman ile hizmete giriş yaptığı zaman arasında bir ara dönem vardır. Bu ara dönemde cihazın korunduğundan ve işlevsel olduğundan emin olmak için aşağıdaki profiller yedi güne kadar (veya cihaz yeni MDM yetkilisine bağlanıp mevcut ayarları yenileriyle değiştirene kadar) cihazda kalır:
    - E-posta profili
    - VPN profili
    - Sertifika profili
    - Wi-Fi profili
    - Yapılandırma profilleri
- Yeni MDM yetkilisine geçtikten sonra, Microsoft Intune yönetim konsolunda doğru uyumluluk verilerinin gösterilmesi bir haftayı bulabilir. Ancak Azure Active Directory’deki ve cihazdaki uyumluluk durumları doğru olacaktır, böylece cihaz korunmaya devam eder.
- Mevcut ayarların üzerine yazılması amaçlanan yeni ayarların, öncekilerle aynı ada sahip olduğundan emin olun. Aksi takdirde eski ayarların üzerine yazılmaz. Ve cihazlarda gereksiz profiller ve ilkeler ortaya çıkabilir.    

  > [!TIP]    
  > En iyi uygulama olarak, tüm yönetim ayarları ve yapılandırmaları ile dağıtımları, MDM yetkilisindeki değişiklik tamamlandıktan hemen sonra oluşturmalısınız. Böylece, ara dönemde cihazların korunduğundan ve etkin olarak yönetildiğinden emin olursunuz.

-  MDM yetkilisini değiştirdikten sonra cihazların yeni yetkiliye başarılı bir şekilde kaydedildiğini doğrulamak için aşağıdaki adımları gerçekleştirin:   
    - Yeni cihaz kaydetme
    - Yeni kaydedilen cihazın Configuration Manager’da görüntülendiğinden emin olun.
    - Yönetim konsolunu kullanarak cihazda Uzaktan Kilitleme gibi bir eylem gerçekleştirin. Bu eylem başarılı olursa cihaz, yeni MDM yetkilisi tarafından yönetiliyor demektir.
- Belirli cihazlarla sorun yaşıyorsanız bu cihazları kaldırıp yeniden kaydederek cihazların yeni yetkiliye bağlanması ve yönetilmeye devam etmesini sağlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

MDM yetkilisi ayarlandıktan sonra [cihazları kaydetmeye](device-enrollment.md) başlayabilirsiniz.
