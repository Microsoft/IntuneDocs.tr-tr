---
title: Exchange koşullu erişim ilkesi oluşturma
titleSuffix: Microsoft Intune
description: Intune 'da Exchange şirket içi ve eski Exchange Online adanmış koşullu erişimi yapılandırın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6650c091917ea265783044efd78b19a7e032e6a7
ms.sourcegitcommit: 5511b4f2b8a3383176a7afe2a22ad5a8d42caf7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78169306"
---
# <a name="configure-exchange-on-premises-access-for-intune"></a>Intune için Exchange şirket içi erişimini yapılandırma

Bu makalede cihaz uyumluluğuna göre şirket içi Exchange için Koşullu erişimin nasıl yapılandırılacağı gösterilir.

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, hesap yöneticinize başvurun. Şirket içi Exchange 'e veya eski Exchange Online ayrılmış ortamınıza e-posta erişimini denetlemek için, Intune 'da şirket içi Exchange 'e koşullu erişimi yapılandırın.

## <a name="before-you-begin"></a>Başlamadan önce

Koşullu erişimi yapılandırmadan önce, aşağıdaki yapılandırmaların mevcut olduğunu doğrulayın:

- Exchange sürümünüz **exchange 2010 SP1 veya sonraki**bir sürümü. Exchange Server İstemci Erişimi Sunucusu (CAS) dizisi desteklenir.

- Intune 'u şirket içi Exchange 'e bağlayan [Exchange ActiveSync şirket Içi Exchange bağlayıcısını](exchange-connector-install.md)yüklediniz ve kullanıyorsunuz.

    >[!IMPORTANT]  
    >Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler.  Ancak, her bir şirket içi Exchange Bağlayıcısı tek bir Intune kiracısına özeldir ve başka hiçbir kiracıyla kullanılamaz.  Birden çok şirket içi Exchange kuruluşunuz varsa, her Exchange kuruluşu için ayrı bağlayıcılar ayarlayabilirsiniz.

- Şirket içi Exchange kuruluşunun Bağlayıcısı, makinenin Exchange sunucusuyla iletişim kurabildiği sürece herhangi bir makineye yüklenebilir.

- Bağlayıcı **Exchange CAS ortamını** destekler. Intune, bağlayıcıyı doğrudan Exchange CAS sunucusuna yüklemeyi destekler. Bağlayıcının sunucuya koyduğu ek yük nedeniyle ayrı bir bilgisayara yüklemenizi öneririz. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.

- **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

- Koşullu erişim ilkeleri yapılandırıldığında ve bir kullanıcıya hedeflenirse, bir kullanıcının e-postasına bağlanabilmesi için, kullandıkları **cihaz** şu şekilde olmalıdır:
  - Intune’a **kayıtlı** veya etki alanına katılmış bir bilgisayar olmalıdır.
  - **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

- Azure AD Cihaz Kayıt Hizmeti (DRS), Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS cihaz kayıt hizmeti 'ni zaten dağıtan müşteriler, kayıtlı cihazları şirket içi Active Directory göremez. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

- Söz konusu cihaza dağıtılan cihaz uyumluluk ilkeleriyle **uyumluluk**.

- Cihaz koşullu erişim ayarlarını karşılamıyorsa, oturum açtığında kullanıcıya şu iletilerden biri sunulur:
  - Cihaz Intune 'a kaydedilmediyse veya Azure Active Directory kayıtlı değilse, Şirket Portalı uygulamasının nasıl yükleneceğine, cihazın nasıl kaydedileceği ve e-postayı nasıl etkinleştireceğinize ilişkin yönergeler içeren bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.
  - Cihaz uyumlu değilse, kullanıcıyı Intune Şirket Portalı Web sitesine veya Şirket Portalı uygulamasına yönlendiren bir ileti görüntülenir. Şirket portalından, sorun ve sorunu nasıl düzeltebileceğiniz hakkında bilgi bulabilir.

### <a name="support-for-mobile-devices"></a>Mobil cihaz desteği

- **Windows Phone 8,1 ve üzeri** -koşullu erişim ilkesi oluşturmak için bkz. [koşullu erişim ilkeleri oluşturma](../protect/create-conditional-access-intune.md)
- **İOS/ıpados üzerinde yerel e-posta uygulaması** -koşullu erişim ilkesi oluşturmak için bkz. [koşullu erişim ilkeleri oluşturma](../protect/create-conditional-access-intune.md)
- **Android 4 veya üzeri sürümlerde Gmail gibi EAS posta istemcileri** -koşullu erişim ilkesi oluşturmak için bkz. [koşullu erişim ilkeleri oluşturma](../protect/create-conditional-access-intune.md)

- **Android iş profili cihazlarda EAS posta istemcileri** -Android iş profili cihazlarında yalnızca *Gmail* ve *dokuz iş için* desteklenir. Android iş profilleriyle çalışmak üzere koşullu erişim için, *Android Enterprise uygulaması Için Gmail veya dokuz iş* için bir e-posta profili dağıtmanız ve ayrıca bu uygulamaları gerekli bir yükleme olarak dağıtmanız gerekir. Uygulamayı dağıttıktan sonra cihaz tabanlı koşullu erişim ayarlayabilirsiniz.

#### <a name="to-set-up-conditional-access-for-android-work-profile-devices"></a>Android iş profili cihazlarına koşullu erişim ayarlamak için

  1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
  
  2. Gmail veya dokuz Iş uygulamasını **gerektiği**şekilde dağıtın.

  3. **Cihaz** > **yapılandırma profilleri** > **Profil oluştur**' u seçin, profil için **ad** ve **Açıklama** girin.

  4. Platformda **Android Enterprise** 'u seçin, **profil türünde** **e-posta** ' yı seçin.

  5. [E-posta profili ayarlarını](https://docs.microsoft.com/intune/configuration/email-settings-android-enterprise#android-enterprise)yapılandırın.

  6. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

  7. E-posta profilini oluşturduktan sonra [gruplara atayın](https://docs.microsoft.com/intune/device-profile-assign).

  8. [Cihaz tabanlı koşullu erişimi](https://docs.microsoft.com/intune/protect/conditional-access-intune-common-ways-use#device-based-conditional-access)ayarlayın.

> [!NOTE]
> Android ve iOS için Microsoft Outlook/ıpados, şirket içi Exchange Bağlayıcısı aracılığıyla desteklenmez. Şirket içi posta kutularınız için iOS/ıpados ve Android için Outlook ile koşullu erişim ilkeleri ve Intune Uygulama Koruması Ilkeleri Azure Active Directory yararlanmak istiyorsanız lütfen bkz. [iOS Için Outlook ile karma modern kimlik doğrulamasını kullanma/ıpados ve Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).

### <a name="support-for-pcs"></a>Bilgisayarlar için destek

Windows 8.1 ve sonraki sürümlerde yerel **posta** uygulaması (ıNTUNE ile MDM 'ye kaydolduğunda)

## <a name="configure-exchange-on-premises-access"></a>Şirket içi Exchange erişimini yapılandırma

Şirket içi Exchange erişim denetimini ayarlamak için aşağıdaki yordamı kullanabilmeniz için önce şirket içi Exchange için en az bir [Intune şirket Içi Exchange Bağlayıcısı](exchange-connector-install.md) yükleyip yapılandırmanız gerekir.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Exchange access** > **Kiracı Yönetimi** ' ne gidin ve **Şirket içi Exchange erişimi**' ni seçin.

3. Şirket içi **Exchange erişimi** bölmesinde, Şirket *içi Exchange erişim denetimini etkinleştirmek*için **Evet** ' i seçin.

   > [!div class="mx-imgBorder"]
   > Şirket içi Exchange erişimi ekranının örnek ekran görüntüsünü ![](./media/conditional-access-exchange-create/exchange-on-premises-access.png)

4. **Atama**altında, **dahil edilecek grupları seç**' i seçin ve ardından erişimi yapılandırmak için bir veya daha fazla grup seçin.

   Seçtiğiniz grupların üyelerine, şirket içi Exchange erişimi için koşullu erişim ilkesi uygulanır. Bu ilkeyi alan kullanıcıların şirket içi Exchange 'e erişebilmesi için cihazlarını Intune 'A kaydetmesi ve uyumluluk profilleriyle uyumlu olmaları gerekir.

   > [!div class="mx-imgBorder"]
   > ![eklenecek grupları seçin](./media/conditional-access-exchange-create/select-groups.png)

5. Grupları dışlamak için, **hariç tutulacak grupları seç**' i seçin ve ardından cihazları kaydetmek ve şirket içi Exchange 'e erişmeden önce uyumluluk profilleriyle uyumlu olmak için gereksinimlerden muaf tutulan bir veya daha fazla grup seçin.

   Yapılandırmanızı kaydetmek için **Kaydet** ' i seçin ve **Exchange erişimi** bölmesine dönün.

6. Ardından, Intune şirket içi Exchange Connector ayarlarını yapılandırın. Konsolunda, **kiracı yönetimi** > exchange **Access**> **Exchange ActiveSync şirket içi Bağlayıcısı** ' nı seçin ve ardından yapılandırmak istediğiniz Exchange kuruluşunun bağlayıcısını seçin.

7. **Kullanıcı bildirimleri**Için, *Kullanıcı bildirim* iletisini değiştirebileceğiniz kuruluş iş akışını **Düzenle** ' yi açmak için **Düzenle** ' yi seçin.

   > [!div class="mx-imgBorder"]
   > bildirim için kuruluş iş akışını Düzenle](./media/conditional-access-exchange-create/edit-organization-user-notification.png) örnek ekran görüntüsünü ![

   Cihazları uyumlu olmayan ve şirket içi Exchange 'e erişmek istedikleri durumlarda kullanıcılara gönderilen varsayılan e-posta iletisini değiştirin. İleti şablonunda Biçimlendirme dili kullanılır. Ayrıca, iletinin yazarken nasıl görüneceğine ilişkin önizlemeyi görebilirsiniz

   **Gözden geçir + kaydet**' i seçin **ve ardından değişikliklerinizi kaydederek Exchange** şirket içi erişimi yapılandırmasını tamamladıktan sonra değişikliklerinizi kaydedin.

   > [!TIP]
   > Biçimlendirme dili hakkında daha fazla bilgi edinmek için bu Wikipedia [makalesine](https://en.wikipedia.org/wiki/Markup_language) bakın.

8. Ardından, **Gelişmiş Exchange ActiveSync erişim ayarları** ' nı seçerek cihaz erişim kurallarını yapılandırdığınız *Gelişmiş Exchange ActiveSync erişim ayarları* iş akışını açın.

   > [!div class="mx-imgBorder"]
   > Gelişmiş ayarlar için kuruluş iş akışını Düzenle ' nin örnek ekran görüntüsünü ![](./media/conditional-access-exchange-create/edit-organization-advanced-settings.png)

   - **Yönetilmeyen cihaz erişimi**Için, koşullu erişim veya diğer kurallardan etkilenmeyen cihazlardan erişim için genel varsayılan kuralı ayarlayın:

     - **Erişime Izin ver** -tüm cihazlar şirket içi Exchange 'e hemen erişebilir. Önceki yordamda dahil olarak yapılandırdığınız gruplardaki kullanıcılara ait olan cihazlar, daha sonra uyumlu ilkelerle uyumlu değil veya Intune 'A kayıtlı değil olarak değerlendiriliyorsa engellenir.

     - **Erişimi engelle** ve **karantinaya al** – tüm cihazların başlangıçta şirket içi Exchange 'e erişimi hemen engellenir. Önceki yordamda dahil olarak yapılandırdığınız gruplardaki kullanıcılara ait cihazlar, cihazın Intune 'A kaydolur ve uyumlu olarak değerlendirilmesinden sonra erişim sağlar.

       Samsung KNOX Standard *çalıştırmayan Android* cihazlar bu ayarı desteklemez ve her zaman engellenir.

   - **Cihaz platformu özel durumları**Için, **Ekle**' yi seçin ve ardından ortamınız için gereken ayrıntıları belirtin.

      **Yönetilmeyen cihaz erişimi** ayarı **engellendi**olarak ayarlandıysa, bunları engellemek için bir platform özel durumu olsa bile, kayıtlı ve uyumlu cihazlara izin verilir.  

9. Düzenlemelerinizi kaydetmek için **Tamam ' ı** seçin.

10. **Gözden geçir + kaydet**' i seçin ve ardından **Kaydet** ' i seçerek Exchange koşullu erişim ilkesini kaydedin.

## <a name="next-steps"></a>Sonraki adımlar

Ardından, bir uyumluluk ilkesi oluşturun ve Intune 'un mobil cihazlarını değerlendirmesi için kullanıcılara atayın, bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

[Microsoft Intune 'de Intune şirket içi Exchange Connector sorunlarını giderme](https://support.microsoft.com/help/4471887)
