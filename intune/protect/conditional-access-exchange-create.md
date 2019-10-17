---
title: Exchange koşullu erişim ilkesi oluşturma
titleSuffix: Microsoft Intune
description: Intune 'da Exchange şirket içi ve eski Exchange Online adanmış koşullu erişimi yapılandırın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: stama
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c18da57282a190dec363e3dfbde5293f5228cb0b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504626"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Exchange şirket içi ve eski Exchange Online ayrılmış için koşullu erişim ilkesi oluşturma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede cihaz uyumluluğuna göre şirket içi Exchange için Koşullu erişimin nasıl yapılandırılacağı gösterilir.

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, hesap yöneticinize başvurun. Şirket içi Exchange 'e veya eski Exchange Online ayrılmış ortamınıza e-posta erişimini denetlemek için, Intune 'da şirket içi Exchange 'e koşullu erişimi yapılandırın.

## <a name="before-you-begin"></a>Başlamadan önce

Koşullu erişimi yapılandırmadan önce, aşağıdaki yapılandırmaların mevcut olduğunu doğrulayın:

- Exchange sürümünüz **exchange 2010 SP1 veya sonraki**bir sürümü. Exchange Server İstemci Erişimi Sunucusu (CAS) dizisi desteklenir.

- Intune 'u şirket içi Exchange 'e bağlayan [Şirket Içi Exchange bağlayıcısını Exchange Active Sync](exchange-connector-install.md)yüklediniz ve kullanıyorsunuz.

    >[!IMPORTANT]  
    >Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler.  Ancak, her bir şirket içi Exchange Bağlayıcısı tek bir Intune kiracısına özeldir ve başka hiçbir kiracıyla kullanılamaz.  Birden çok şirket içi Exchange kuruluşunuz varsa, her Exchange kuruluşu için ayrı bağlayıcılar ayarlayabilirsiniz.

- Şirket içi Exchange kuruluşunun Bağlayıcısı, makinenin Exchange sunucusuyla iletişim kurabildiği sürece herhangi bir makineye yüklenebilir.

- Bağlayıcı **Exchange CAS ortamını** destekler. Intune, bağlayıcıyı doğrudan Exchange CAS sunucusuna yüklemeyi destekler, ancak bağlayıcının sunucuya koyduğu ek yük nedeniyle ayrı bir bilgisayara yüklemenizi öneririz. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.

- **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

- Koşullu erişim ilkeleri yapılandırıldığında ve bir kullanıcıya hedeflenirse, bir kullanıcının e-postasına bağlanabilmesi için, kullandıkları **cihaz** şu şekilde olmalıdır:
  - Intune’a **kayıtlı** veya etki alanına katılmış bir bilgisayar olmalıdır.
  - **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

- Azure AD Cihaz Kayıt Hizmeti (DRS), Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS cihaz kayıt hizmeti 'ni zaten dağıtan müşteriler, kayıtlı cihazları şirket içi Active Directory göremez. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

- Söz konusu cihaza dağıtılan cihaz uyumluluk ilkeleriyle **uyumluluk**.

- Cihaz koşullu erişim ayarlarını karşılamıyorsa, oturum açtığında kullanıcıya şu iletilerden biri sunulur:
  - Cihaz Intune 'a kaydedilmediyse veya Azure Active Directory kayıtlı değilse, Şirket Portalı uygulamasının nasıl yükleneceğine, cihazın nasıl kaydedileceği ve e-postayı nasıl etkinleştireceğinize ilişkin yönergeler içeren bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.
  - Cihaz uyumlu değilse, kullanıcıyı Intune Şirket Portalı Web sitesine veya sorun hakkında bilgi bulabileceği ve sorunu nasıl düzeltebileceği Şirket Portalı uygulamayı yönlendiren bir ileti görüntülenir.

### <a name="support-for-mobile-devices"></a>Mobil cihaz desteği

- Windows Phone 8.1 ve üzeri
- iOS’ta yerel e-posta uygulaması.
- Android 4 veya sonraki sürümlerdeki Gmail gibi EAS posta istemcileri.
- EAS posta istemcileri **Android iş profili cihazları:** Android iş profili cihazlarında yalnızca **iş profilindeki** **Gmail** ve **Android Enterprise için Nine Work** desteklenir. Android iş profilleriyle çalışmak üzere koşullu erişim için, Android Enterprise uygulaması için Gmail veya dokuz Iş için bir e-posta profili dağıtmanız ve ayrıca bu uygulamaları gerekli bir yükleme olarak dağıtmanız gerekir.

> [!NOTE]
> Android ve iOS için Microsoft Outlook, şirket içi Exchange Bağlayıcısı aracılığıyla desteklenmez. Şirket içi posta kutularınız için iOS ve Android için Outlook ile koşullu erişim ilkeleri ve Intune Uygulama Koruması Ilkeleri Azure Active Directory yararlanmak istiyorsanız lütfen bkz. [iOS ve Android Için Outlook ile karma modern kimlik doğrulamasını kullanma](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) . 

### <a name="support-for-pcs"></a>Bilgisayarlar için destek

Windows 8.1 ve sonraki sürümlerde yerel **posta** uygulaması (ıNTUNE ile MDM 'ye kaydolduğunda)

## <a name="configure-exchange-on-premises-access"></a>Şirket içi Exchange erişimini yapılandırma

Şirket içi Exchange erişim denetimini ayarlamak için aşağıdaki yordamı kullanabilmeniz için önce şirket içi Exchange için en az bir [Intune şirket Içi Exchange Bağlayıcısı](exchange-connector-install.md) yükleyip yapılandırmanız gerekir.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açma

2. **Exchange erişimi**' ne gidin ve **Şirket içi Exchange erişimi**' ni seçin. 

3. Şirket içi **Exchange erişimi** bölmesinde, Şirket *içi Exchange erişim denetimini etkinleştirmek*için **Evet** ' i seçin.

4. **Atama**altında, **dahil edilecek grupları seç**' i seçin ve ardından erişimi yapılandırmak için bir veya daha fazla grup seçin. 

   Seçtiğiniz grupların üyelerine, şirket içi Exchange erişimi için koşullu erişim ilkesi uygulanır. Bu ilkeyi alan kullanıcıların şirket içi Exchange 'e erişebilmesi için cihazlarını Intune 'A kaydetmesi ve uyumluluk profilleriyle uyumlu olmaları gerekir.

5. Grupları dışlamak için, **hariç tutulacak grupları seçin**' i seçin ve ardından Şirket içi Exchange 'e erişmeden önce cihazları kaydetmek ve uyumluluk profilleriyle uyumlu olmak için gereksinimlerden muaf tutulan bir veya daha fazla grup seçin. 

6. Ardından, Intune şirket içi Exchange Connector ayarlarını yapılandırın.  **Exchange erişimi bölmesindeki** **Kurulum** ' un altında **Exchange ActiveSync şirket içi Bağlayıcısı** ' nı seçin ve ardından yapılandırmak istediğiniz Exchange kuruluşunun bağlayıcısını seçin.

7. **Ayarlar**altında **Kullanıcı bildirimleri** ' ni seçerek, cihazları uyumlu olmayan ve şirket içi Exchange 'e erişmek istedikleri kullanıcılara gönderilen varsayılan e-posta iletisini değiştirin. İleti şablonunda Biçimlendirme dili kullanılır.  Ayrıca yazarken iletinin nasıl görüneceğini gösteren bir önizleme de görebilirsiniz.
   > [!TIP]
   > Biçimlendirme dili hakkında daha fazla bilgi edinmek için bu Wikipedia [makalesine](https://en.wikipedia.org/wiki/Markup_language) bakın.
 
   Exchange şirket içi erişimi yapılandırmasını tamamladıktan sonra düzenlemelerinizi kaydetmek için **Tamam ' ı** seçin.

8. Ardından, **gelişmiş Exchange Active Sync erişim ayarları** ' nı seçerek cihaz erişim kurallarını yapılandırdığınız *Gelişmiş Exchange ActiveSync erişim ayarları* bölmesini açın:  

   - **Yönetilmeyen cihaz erişimi**Için, koşullu erişim veya diğer kurallardan etkilenmeyen cihazlardan erişim için genel varsayılan kuralı ayarlayın:

     - **Erişime Izin ver** -tüm cihazlar şirket içi Exchange 'e hemen erişebilir. Önceki yordamda dahil olarak yapılandırdığınız gruplardaki kullanıcılara ait olan cihazlar, daha sonra uyumlu ilkelerle uyumlu değil veya Intune 'A kayıtlı değil olarak değerlendiriliyorsa engellenir.

     - **Erişimi engelle** ve **karantinaya al** – tüm cihazların başlangıçta şirket içi Exchange 'e erişimi hemen engellenir. Önceki yordamda dahil olarak yapılandırdığınız gruplardaki kullanıcılara ait cihazlar, cihazın Intune 'A kaydolur ve uyumlu olarak değerlendirilmesinden sonra erişim sağlar. 

       Samsung KNOX Standard *çalıştırmayan Android* cihazlar bu ayarı desteklemez ve her zaman engellenir.

   -  **Cihaz platformu özel durumları**Için, **Ekle**' yi seçin ve ardından ortamınız için gereken platform ayrıntılarını belirtin. 
   
      **Yönetilmeyen cihaz erişimi** ayarı **engellendi**olarak ayarlandıysa, bunları engellemek için bir platform özel durumu olsa bile, kayıtlı ve uyumlu cihazlara izin verilir.  
   
   Düzenlemelerinizi kaydetmek için **Tamam ' ı** seçin.

9. Exchange koşullu erişim ilkesini kaydetmek için **Kaydet** ' i seçin.

Ardından, bir uyumluluk ilkesi oluşturun ve Intune 'un mobil cihazlarını değerlendirmesi için kullanıcılara atayın, bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="see-also"></a>Ayrıca bkz:

[Microsoft Intune 'de Intune şirket Içi Exchange Connector sorunlarını giderme](https://support.microsoft.com/help/4471887)
