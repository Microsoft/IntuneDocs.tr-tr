---
title: Microsoft Intune ile Lookout tümleştirmenizi ayarlama
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için bir Mobile Threat Defense çözümü olarak Intune Lookout mobil uç nokta güvenliği ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d146b211c42c20b1381b238311db6a10295ef4a
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67044924"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Intune ile Lookout mobil uç nokta güvenliği tümleştirmesini ayarlama
Uygun bir ortam ile [önkoşulları](lookout-mobile-threat-defense-connector.md#prerequisites), Intune ile Lookout mobil uç nokta güvenliği tümleştirebilirsiniz. Bu makaledeki bilgiler tümleştirmenin ayarlanması ve Intune ile kullanmak için Lookout'ta önemli ayarları yapılandırma size yol gösterir.  

> [!IMPORTANT]
> Daha önceden Azure AD kiracınız ile ilişkilendirilmemiş mevcut bir Lookout Mobil Uç Nokta Güvenliği kiracısı, Azure AD ve Intune tümleştirmesi için kullanılamaz. Yeni bir Lookout Mobil Uç Nokta Güvenliği kiracısı oluşturmak için Lookout desteğine başvurun. Azure AD kullanıcılarınızı eklemek için yeni kiracıyı kullanın.

## <a name="collect-azure-ad-information"></a>Azure AD bilgileri toplama  
Intune ile tümleşik Lookout, Lookout mobil uç nokta güvenliği kiracınız Azure Active Directory (AD) aboneliğinizle ilişkilendirin.

Intune ile Lookout mobil uç nokta güvenliği abonelik tümleştirmenizi etkinleştirmek için Lookout desteği için aşağıdaki bilgileri sağlayın (enterprisesupport@lookout.com):  

- **Azure AD Kiracı dizin kimliği**  

- **Azure AD grubu nesne kimliği** grupla **tam** Lookout mobil uç nokta güvenliği (MES) konsol erişimi.  
  Bu kullanıcı grubuna sahip kullanıcıları içerecek şekilde, Azure AD'de oluşturduğunuz *tam erişim* oturum açmak için **Lookout konsolunda**. Kullanıcıların bu grup veya isteğe bağlı bir üyesi olması gerekir *sınırlı erişim* Lookout konsoluna oturum açmak için grubu. 

- **Azure AD grubu nesne kimliği** grupla **kısıtlı** Lookout MES konsol erişimi *(isteğe bağlı bir grup)*. 
  Birçok yapılandırma ve kayıtla ilgili modüllerin çoğuna erişimi olmaması kullanıcıları içeren Azure AD'de Bu isteğe bağlı kullanıcı grubu oluşturun. Bunun yerine, bu kullanıcılara salt okunur erişimi **Güvenlik İlkesi** Lookout konsolunun modülü. Kullanıcıların bu isteğe bağlı bir grup veya gerekli üyeleri olmalıdır *tam erişim* Lookout konsoluna oturum açmak için grubu.

 > [!TIP] 
 > İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/articles/114094105653) okuyun.

### <a name="collect-information-from-azure-ad"></a>Azure AD bilgileri toplama 

1. Oturum [Azure portalında](https://portal.azure.com) bir genel yönetici hesabıyla.

2. Git **Azure Active Directory** > **özellikleri** bulun, **dizin kimliği**. Kullanım *kopyalama* dizin kimliği kopyalamak için düğme ve bir metin dosyasına kaydedin.

   ![Azure AD özellikleri](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Ardından, Azure AD kullanıcılarının Lookout konsoluna erişimi vermek için kullandığınız hesap için Azure AD grubu Kimliğini bulun. Bir grup içindir *tam erişim*ve ikinci grup için *sınırlı erişim* isteğe bağlıdır. Alınacak *nesne kimliği*, her hesap için:  
   1. Git **Azure Active Directory** > **grupları** açmak için *gruplar - tüm gruplar* bölmesi.  

   2. İçin oluşturduğunuz grubu seçin *tam erişim* açmak için kendi *genel bakış* bölmesi.  

   3. Kullanım *kopyalama* nesne kimliği kopyalamak için düğme ve bir metin dosyasına kaydedin.  

   4. İçin işlemi tekrarlayın *sınırlı erişim* bu grubu kullanıyorsanız grup.  

      ![Azure AD grubu nesne kimliği](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Bu bilgileri topladıktan sonra Lookout desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com). Lookout desteği, birincil ilgili kişiyle çalışır ve sağladığınız bilgileri kullanarak Lookout Enterprise hesabınızı oluşturun.  

## <a name="configure-your-lookout-subscription"></a>Lookout aboneliğinizi yapılandırma  
Lookout desteği Lookout Enterprise hesabınızı oluşturduktan sonra Lookout desteği e-posta için birincil ilgili kişi oturum açma URL'sine bir bağlantı ile şirketinizin gönderir: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>İlk oturum açma  
İlk oturum açma MES Lookout konsoluna bir onay sayfası görüntüler (https://aad.lookout.com/les?action=consent). Bir Azure AD genel Yöneticisi yalnızca oturum açma ve **kabul**. Sonraki oturum açma kullanıcının bu Azure AD ayrıcalık düzeyine sahip olmasını gerektirmez. 

 Bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin. 
   ![Lookout konsolunda ilk kez oturum açma sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Kabul edin ve onay, Lookout konsoluna yönlendirilirsiniz.

İlk oturum açma ve onay tamamlandıktan sonra kullanıcılar, oturum gelen https://aad.lookout.com MES konsoluna yönlendirilirsiniz. Tüm oturum açma denemesi, onayı henüz verilen değildi, hatalı bir oturum açma hatasına neden.

### <a name="configure-the-intune-connector"></a>Intune bağlayıcısını yapılandırma  
Aşağıdaki yordam, Lookout dağıtımınızı test için Azure AD'de bir kullanıcı grubu daha önce oluşturduğunuz varsayılır. Küçük bir ürün tümleştirmeleri ile ilgili bilgi sahibi olma Lookout ve Intune yöneticilerinin izin vermek için kullanıcı grubuyla başlamak en iyi yöntem olacaktır. Bunlar öğrendikten sonra kaydı ek kullanıcı gruplarına genişletebilirsiniz.

1. Oturum [Lookout MES konsolunda](https://aad.lookout.com) gidin **sistem** > **Bağlayıcılar**ve ardından **bağlayıcı Ekle**.  Seçin **Intune**.

   ![Lookout MTP konsolunu bağlayıcılar sekmesi Intune seçeneğini görüntüsü](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. Üzerinde *Intune* bölmesinde **bağlantı ayarlarını** belirtin **sinyal sıklığını** dakikalar içinde. 

   ![Bağlantı ayarları sekmesinin sinyal sıklığını yapılandırılmış ile görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. Seçin **kayıt yönetimi**ve **Lookout for Work kaydedilmesi cihazları belirlemek için aşağıdaki Azure AD güvenlik grupları kullanın**, belirtin *grup adı*Lookout ile kullanın ve ardından seçmek için bir Azure AD grubunun **değişiklikleri kaydetmek**.

    ![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **Kullandığınız grupları hakkında**:
   - En iyi uygulama, Lookout tümleştirmesini sınamak için kullanıcıların küçük bir sayı içeren bir Azure AD güvenlik grubu ile başlayın.
   - **Grup adı** gösterildiği gibi büyük küçük harfe duyarlıdır **özellikleri** güvenlik grubunun Azure portalında.  
   - İçin belirttiğiniz grupları **kayıt yönetimi** kullanıcılar cihazlarını Lookout ile kaydedilir kümesini tanımlar. Bir kullanıcı bir kayıt grubunda olduğunda, kullanıcıların cihazlarını Azure AD'ye kaydedilir ve Lookout MES Etkinleştirilmeye uygun hale. Bir kullanıcı ilk kez *Lookout for Work* uygulama desteklenen bir cihazda, bunlar etkinleştirmeniz istenir.

4. Seçin **durum eşitlemeyi** ve her ikisi de olun *cihaz durumu* ve *tehdit durumu* ayarlandığından **üzerinde**.  İkisi de, Lookout Intune tümleştirmesinin düzgün çalışması için gereklidir.  

5. Seçin **hata Yönetimi**, hata raporları alan ve ardından e-posta adresi belirtin **değişiklikleri kaydetmek**.
 
   ![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Seçin **Bağlayıcısı oluşturma** bağlayıcının yapılandırmayı tamamlamak için. Daha sonra sonuçlarınızdan memnun olduğunuzda, kaydı ek kullanıcı gruplarına genişletebilirsiniz.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Lookout Mobile Threat Defense sağlayıcısı olarak kullanmak için Intune'u yapılandırma
Lookout MES yapılandırdıktan sonra ıntune'da Lookout bağlantı ayarlamanız gerekir.  

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Git **cihaz uyumluluğu** > **Mobile Threat Defense** seçip **Ekle**.

3. Üzerinde *ekleme bağlayıcı* bölmesinde, açılan listeyi kullanın ve select **Lookout for Work**.  

4. **Oluştur**’u seçin. Bağlayıcısı, Lookout MES kişiyle iletişim kurduktan sonra *bağlayıcı ayarları* kullanılabilir hale gelir.

5. Ayarlama **iOS cihazlar için uygulama eşitlemeyi etkinleştirmek** için **üzerinde**. 

6. Seçin **Kaydet** yapılandırmasını tamamlamak için.  Intune ve Lookout MES tümleşik ve kullanıma hazır sunulmuştur.


## <a name="additional-settings-in-the-lookout-mes-console"></a>MES Lookout konsolunda ek ayarlar
Lookout MES konsolunda yapılandırabileceğiniz ek ayarlar aşağıda verilmiştir.  

### <a name="configure-enrollment-settings"></a>Kayıt ayarlarını yapılandırma
Lookout MES konsolunda seçin **sistem** > **yönetme kayıt** > **kayıt ayarları**.  

- İçin **bağlantı kesildi durumu**, bağlantısız bir cihaz bağlantısı kesilmiş olarak işaretlenmeden önce gün sayısını belirtin.  

  Bağlantısı kesilmiş cihazlar uyumsuz olarak kabul edilir ve Intune koşullu erişim ilkelerine bağlı olarak şirket uygulamalarınıza erişimleri engellenir. 1 ila 90 gün arasında bir değer belirtebilirsiniz.

  ![Lookout kayıt ayarları sistem Modülü](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak için oturum açın [Lookout MES konsolunda](https://aad.lookout.com) bildirimlerin gönderileceği kullanıcı hesabını.  

- Git **tercihleri** ve bildirimler almasını istediğiniz ayarlayın **ON**ve ardından **Kaydet** değişiklikleri.  

- Artık e-posta bildirimleri almak istemiyorsanız, bildirimleri kümesine **OFF** ve değişikliklerinizi kaydedin.

  ![Kullanıcı hesabının görüntülendiği Tercihler sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)



## <a name="configure-threat-classifications"></a>Tehdit sınıflandırmaları yapılandırın  
Lookout mobil uç nokta güvenliği, çeşitli türlerdeki mobil tehditleri sınıflandırır. Lookout tehdit sınıflandırmaları kendileriyle ilişkilendirilmiş varsayılan risk düzeylerine sahip. Risk düzeyleri, şirket gereksinimlerinize uyacak şekilde herhangi bir anda değiştirilebilir.

Tehdit düzeyi sınıflandırmalarını ve bunlarla ilişkili risk düzeyleri yönetme hakkında daha fazla bilgi için bkz: [Lookout tehdit başvuru](https://enterprise.support.lookout.com/hc/articles/360011812974).

>[!IMPORTANT]
> Cihaz uyumluluğunu çalışma zamanı bu risk düzeylerine göre hesapladığından bunlar Intune tümleştirmesi risk düzeyleri bir mobil uç nokta güvenliği için önemlidir.  
> 
> Intune yöneticisi; bir cihazın **Yüksek**, **Orta** veya **Düşük** düzeyde etkin bir tehdidi varsa cihazı uyumsuz olarak tanımlamak için ilke içinde bir kural koyar. Lookout mobil uç nokta güvenliği, tehdit sınıflandırma İlkesi, Intune'da cihaz uyumluluk hesaplamasını doğrudan yürütür.  

## <a name="monitor-enrollment"></a>İzleyici kayıt
Kurulum tamamlandıktan sonra Lookout mobil uç nokta güvenliği belirlenen kayıt gruplarına karşılık gelen cihazlar için Azure AD'yi yoklamaya başlar.  Kayıtlı cihazlar hakkındaki bilgileri giderek bulabilirsiniz **cihazları** MES Lookout konsolundaki.  
- Cihazların ilk durumu *bekleyen*.  
- Cihaz durumu güncelleştirmeleri sonra *Lookout for Work* uygulaması yüklü, açık ve cihazda etkinleştirildi.

Nasıl alınacağına yönelik ayrıntılar için *Lookout for Work* uygulama bir cihaza dağıtılan görmek [ekleme Lookout for work uygulamalarını Intune ile](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

[Lookout uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
