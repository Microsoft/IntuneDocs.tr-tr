---
title: Microsoft Intune ile Lookout tümleştirmenizi ayarlama
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için mobil bir tehdit savunması çözümü olarak Intune 'u mobil uç nokta güvenliği ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 331d4d312541f587077c70e19634e331f9ddc21e
ms.sourcegitcommit: de663ef5f3e82e0d983899082a7f5b62c63f24ef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75956344"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Intune ile mobil uç nokta güvenliği tümleştirmesini ayarlama
[Önkoşulları](lookout-mobile-threat-defense-connector.md#prerequisites)karşılayan bir ortam sayesinde, mobil uç nokta güvenliğini Intune ile tümleştirebilirsiniz. Bu makaledeki bilgiler, Intune ile kullanım için, tümleştirme ayarlama ve önemli ayarları yapılandırma konusunda size kılavuzluk eder.  

> [!IMPORTANT]
> Daha önceden Azure AD kiracınız ile ilişkilendirilmemiş mevcut bir Lookout Mobil Uç Nokta Güvenliği kiracısı, Azure AD ve Intune tümleştirmesi için kullanılamaz. Yeni bir Lookout Mobil Uç Nokta Güvenliği kiracısı oluşturmak için Lookout desteğine başvurun. Azure AD kullanıcılarınızı eklemek için yeni kiracıyı kullanın.

## <a name="collect-azure-ad-information"></a>Azure AD bilgileri toplama  
Intune ile tümleşik bir sorun olması için, Gevite Mobility uç noktası güvenlik kiracınızı Azure Active Directory (AD) aboneliğinizle ilişkilendirirsiniz.

Mobil uç nokta güvenlik aboneliği tümleştirmesini Intune ile etkinleştirmek için, destek sağlamak için aşağıdaki bilgileri sağlayın (enterprisesupport@lookout.com):  

- **Azure AD kiracı dizin KIMLIĞI**  

- **Tam** GEVME mobil uç nokta GÜVENLIĞI (MES) konsol erişimine sahip Grup IÇIN **Azure AD grubu nesne kimliği** .  
  Bu kullanıcı grubunu, Azure AD 'de, **gevrme konsolunda**oturum açmak için *tam erişimi* olan kullanıcıları içerecek şekilde oluşturursunuz. Kullanıcılar, Gevrme konsolunda oturum açmak için bu grubun veya isteğe bağlı *kısıtlı erişim* grubunun üyesi olmalıdır. 

- **Kısıtlanmış** bir sorun olması halinde konsol erişimi olan grup IÇIN **Azure AD grubu nesne kimliği** *(isteğe bağlı Grup)* . 
  Bu isteğe bağlı kullanıcı grubunu Azure AD 'de oluşturun ve bu, şifreleme konsolunun çeşitli yapılandırma ve kayıt ile ilgili modüllerine erişimi olmayan kullanıcıları içerir. Bunun yerine, bu kullanıcıların, Gevl konsolunun **güvenlik ilkesi** modülüne salt okuma erişimi vardır. Kullanıcılar, bu isteğe bağlı grubun veya gerekli *tam erişim* grubunun üyesi olmalıdır ve bu da gevrme konsolunda oturum açabilirler.

 > [!TIP] 
 > İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/articles/114094105653) okuyun.

### <a name="collect-information-from-azure-ad"></a>Azure AD 'den bilgi toplayın 

1. [Azure Portal](https://portal.azure.com) bir genel yönetici hesabıyla oturum açın.

2. **Azure Active Directory** > **özellikleri** ' ne gidin ve **Dizin kimliğinizi**bulun. Dizin KIMLIĞINI kopyalamak için *Kopyala* düğmesini kullanın ve ardından bir metin dosyasına kaydedin.

   ![Azure AD özellikleri](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Daha sonra, Azure AD kullanıcılarına erişim sağlamak için kullandığınız hesapların Azure AD grubu KIMLIĞINI bulun. Tek bir grup *tam erişime*yöneliktir ve ikinci grup, *kısıtlı erişim* için isteğe bağlıdır. Her hesap için *nesne kimliğini*almak için:  
   1. *Gruplar-tüm gruplar* bölmesini açmak için **Azure Active Directory** > **gruplara** gidin.  

   2. *Tam erişim* için oluşturduğunuz grubu seçerek *genel bakış* bölmesini açın.  

   3. Nesne KIMLIĞINI kopyalamak için *Kopyala* düğmesini kullanın ve bir metin dosyasına kaydedin.  

   4. Bu grubu kullanırsanız, *kısıtlı erişim* grubu için işlemi tekrarlayın.  

      ![Azure AD grubu nesne KIMLIĞI](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Bu bilgileri topladıktan sonra, BT desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com). GEVME desteği, verdiğiniz bilgileri kullanarak aboneliğinizi eklemek ve GEVME kurumsal hesabınızı oluşturmak için birincil Kişinizden çalışacaktır.  

## <a name="configure-your-lookout-subscription"></a>Gevbir abonelik aboneliğinizi yapılandırma  

Aşağıdaki adımlar, kuruluş yönetim konsolunda tamamlanacaktır ve Intune 'a kayıtlı cihazlar (cihaz uyumluluğu aracılığıyla) **ve** kayıtlı olmayan cihazlar (uygulama koruma ilkeleri aracılığıyla) için bakım hizmetine bir bağlantı etkinleştirecektir.

Gevrme desteği, gevþsiz kurumsal hesabınızı oluşturduktan sonra, bir bağlantı, oturum açma URL 'si bağlantısı ile şirketiniz için birincil ilgili kişiye bir e-posta gönderir: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>İlk oturum açma  
Gevrme MES konsolundaki ilk oturum açma, bir onay sayfası (https://aad.lookout.com/les?action=consent) görüntüler. Bir Azure AD Genel Yöneticisi, oturum açıp **kabul etmeniz**yeterlidir. Sonraki oturum açma, kullanıcının bu düzeyde Azure AD ayrıcalığına sahip olmasını gerektirmez. 

 Bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin. 
   GEVME konsolunun ilk kez oturum açma sayfasının ekran görüntüsünü ![](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Kabul edip onay aldığınızda, Gevyorla konsoluna yönlendirilirsiniz.

İlk oturum açma ve onay tamamlandıktan sonra, https://aad.lookout.com oturum açma kullanıcılar MES konsoluna yönlendirilir. Onay henüz verilmediyse, tüm oturum açma girişimleri hatalı oturum açma hatası oluşmasına neden olacak.

### <a name="configure-the-intune-connector"></a>Intune bağlayıcısını yapılandırma  
Aşağıdaki yordamda, daha önce Azure AD 'de Gevyorma dağıtımınızı test etmek için bir Kullanıcı grubu oluşturmuş olduğunuz varsayılır. En iyi uygulama, Gevlüklerinizin ve Intune yöneticilerinin ürün tümleştirmelerini öğrenmesine olanak tanımak için küçük bir kullanıcı grubuyla başlamadır. Tanıdık olduktan sonra, kaydı ek kullanıcı gruplarına genişletebilirsiniz.

1. [GEVMES uçlarında](https://aad.lookout.com) oturum açın ve **System** > **bağlayıcıları**' na gidip **bağlayıcı Ekle**' yi seçin.  **Intune**' u seçin.

   ![Bağlayıcılar sekmesinde Intune seçeneğiyle GEVME konsolunun görüntüsü](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. *Microsoft Intune* bölmesinde **bağlantı ayarları** ' nı seçin ve dakika cinsinden **sinyal sıklığını** belirtin. 

   ![Sinyal frekansı yapılandırılmış bağlantı ayarları sekmesinin görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. **Kayıt yönetimi**' ni seçin ve **Lookout for Work kaydedilmesi gereken cihazları tanımlamak IÇIN aşağıdaki Azure AD güvenlik gruplarını kullanın, gevylede**kullanmak üzere bir Azure AD grubunun *Grup adını* belirtin ve ardından **Değişiklikleri Kaydet**' i seçin.

    ![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **Kullandığınız gruplar hakkında**:
   - En iyi uygulama olarak, sorun tümleştirmesinin test etmek için az sayıda kullanıcı içeren bir Azure AD güvenlik grubu ile başlayın.
   - **Grup adı** , Azure Portal güvenlik grubunun **özelliklerinde** gösterildiği gibi büyük/küçük harfe duyarlıdır.  
   - **Kayıt yönetimi** için belirttiğiniz gruplar, cihazları gevle kaydedilecek Kullanıcı kümesini tanımlar. Bir Kullanıcı bir kayıt grubunda olduğunda, Azure AD 'deki cihazları kaydedilir ve Gevaktif hale geldiğinde etkinleştirilmeye uygundur. Kullanıcı *Lookout for Work* uygulamayı desteklenen bir cihazda ilk kez açtığında, bunları etkinleştirmesi istenir.

4. **Durum eşitlemesini** seçin ve hem *cihaz durumunun* hem de *tehdit durumunun* **Açık**olarak ayarlandığından emin olun.  Her ikisi de Intune tümleştirmesinin düzgün çalışması için gereklidir.  

5. **Hata yönetimi**' ni seçin, hata raporlarını alması gereken e-posta adresini belirtin ve ardından **Değişiklikleri Kaydet**' i seçin.
 
   ![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Bağlayıcının yapılandırmasını tamamladıktan sonra **bağlayıcı oluştur** ' u seçin. Daha sonra, sonuçlarınızdan memnun kaldığınızda, kaydı ek kullanıcı gruplarına genişletebilirsiniz.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Intune 'U bir mobil tehdit savunma sağlayıcısı olarak GEVME kullanacak şekilde yapılandırma
GEVMES yapılandırıldıktan sonra [Intune 'Da GEVME](~/protect/mtd-connector-enable.md)bağlantısı ayarlamanız gerekir.  

## <a name="additional-settings-in-the-lookout-mes-console"></a>Gevmes uçlarınızdaki ek ayarlar
Aşağıda, GEVME MES konsolunda yapılandırabileceğiniz ek ayarlar verilmiştir.  

### <a name="configure-enrollment-settings"></a>Kayıt ayarlarını yapılandırma
Gevmes Uçpenceresinde **sistem** > kayıt > **kayıt ayarlarını** **Yönet** ' i seçin.  

- **Bağlantısı kesilmiş durum**için, bağlı olmayan bir cihazın bağlantısı kesik olarak işaretlenmeden önce geçecek gün sayısını belirtin.  

  Bağlantısı kesilmiş cihazlar uyumsuz olarak kabul edilir ve Intune koşullu erişim ilkelerine bağlı olarak şirket uygulamalarınıza erişimleri engellenir. 1 ila 90 gün arasında bir değer belirtebilirsiniz.

  ![Sistem modülündeki kayıt ayarlarını gevrme](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak için, uyarı almak zorunda olan kullanıcı hesabıyla [gevreleri](https://aad.lookout.com) ve sorun konsolunda oturum açın.  

- **Tercihler** ' e gidin ve ardından almak Istediğiniz bildirimleri **Açık**olarak ayarlayın ve ardından değişiklikleri **kaydedin** .  

- Artık e-posta bildirimleri almak istemiyorsanız, bildirimleri **kapalı** olarak ayarlayın ve değişikliklerinizi kaydedin.

  ![Kullanıcı hesabının görüntülendiği Tercihler sayfasının ekran görüntüsü](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)

## <a name="configure-threat-classifications"></a>Tehdit sınıflandırmalarını yapılandırma  
GEVME mobil uç nokta güvenliği, çeşitli türlerdeki mobil tehditleri sınıflandırır. GEVME tehdit sınıflandırmalarının kendileriyle ilişkili varsayılan risk düzeyleri vardır. Risk düzeyleri, Şirket gereksinimlerinize uyacak şekilde herhangi bir zamanda değiştirilebilir.

Tehdit düzeyi sınıflandırmaları ve bunlarla ilişkili risk düzeylerini yönetme hakkında bilgi için bkz. [GEVME tehdit başvurusu](https://enterprise.support.lookout.com/hc/articles/360011812974).

>[!IMPORTANT]
> Intune tümleştirmesi, çalışma zamanında cihaz uyumluluğunu bu risk düzeylerine göre hesapladığından, risk düzeyleri mobil uç nokta güvenliğinin önemli bir yönüdür.  
> 
> Intune yöneticisi; bir cihazın **Yüksek**, **Orta** veya **Düşük** düzeyde etkin bir tehdidi varsa cihazı uyumsuz olarak tanımlamak için ilke içinde bir kural koyar. Mobil uç nokta güvenliğini Gevşeden tehdit sınıflandırma ilkesi, Intune 'daki cihaz uyumluluk hesaplamasını doğrudan yürütür.  

## <a name="monitor-enrollment"></a>Kaydı izle
Kurulum tamamlandıktan sonra mobil uç nokta güvenliği, belirtilen kayıt gruplarına karşılık gelen cihazlar için Azure AD 'yi yoklamaya başlar.  Kayıtlı cihazlarla ilgili bilgileri, Gevlecekmes konsolundaki **cihazlara** giderek bulabilirsiniz.  
- Cihazların ilk durumu *bekliyor*.  
- Cihaz durumu, *Lookout for Work* uygulama yüklendikten, açıldıktan ve cihazda etkinleştirildikten sonra güncelleştirilir.

Cihaza dağıtılan *Lookout for Work* uygulamasının nasıl alınacağı hakkında daha fazla bilgi için, bkz. [Intune ile Iş uygulamaları için Gevbir cihaz ekleme](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Kayıtlı cihazlar için gevan uygulamaları ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Kayıtlı olmayan cihazlar için GEVME uygulamalarını ayarlama](~/protect/mtd-add-apps-unenrolled-devices.md)
