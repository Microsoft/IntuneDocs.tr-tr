---
title: Uygulama koruma ilkelerini oluşturma ve dağıtma
titleSuffix: Microsoft Intune
description: Bu konu başlığında Microsoft Intune uygulama koruma ilkelerini oluşturma ve atama adımları anlatılmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8e105dae43c4e7139c8e44a8c6535baebe31cc4
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585457"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkelerini oluşturma ve atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kuruluşunuzun kullanıcıları için Microsoft Intune uygulama koruma ilkeleri (uygulama) oluşturmayı ve atamayı öğrenin. Bu konu, mevcut ilkelerde nasıl değişiklik yapılacağını da açıklar.

## <a name="before-you-begin"></a>Başlamadan önce

Uygulama koruma ilkeleri, Intune tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin çalışması ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolar ile ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

MAM destekli uygulamalar listesi arıyorsanız bkz. [MAM uygulamaları listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Kuruluşunuzun iş kolu (LOB) uygulamalarını uygulama koruma ilkelerine hazırlamak üzere Microsoft Intune'a ekleme hakkında bilgi için bkz. [Uygulamaları Microsoft Intune'a ekleme](apps-add.md).

Şu anda, bir uygulama koruma ilkesi oluşturmak için işlem akışı platforma göre farklılık gösterir:
- İOS/ıpados ve Android uygulamaları için uygulama koruma ilkeleri
- Windows 10 uygulamaları için uygulama koruma ilkeleri

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>İOS/ıpados ve Android uygulamaları için uygulama koruma ilkeleri

İOS/ıpados ve Android uygulamaları için bir uygulama koruma ilkesi oluşturduğunuzda, yeni bir uygulama koruma ilkesine neden olan modern bir Intune işlem akışını takip edersiniz.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>İOS/ıpados veya Android uygulama koruma ilkesi oluşturma
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Intune portalında, **istemci uygulamaları**  > **Uygulama koruma ilkeleri**' ni seçin. Bu seçim, yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
3. **Ilke oluştur** ' u seçin ve **IOS/ıpados** ya da **Android**' i seçin. **Ilke oluştur** dikey penceresi görüntülenir.
4. **Temel bilgiler** sayfasında, aşağıdaki değerleri ekleyin:

    | Değer | Description |
    |--------------|------------------------------------------------|
    | Ad | Bu uygulama koruma ilkesinin adı. |
    | Description | Seçim Bu uygulama koruma ilkesinin açıklaması. |


    **Platform** değeri, yukarıdaki seçeneğe göre ayarlanır.

    ![İlke oluştur dikey penceresinin temel bilgiler sayfasının ekran görüntüsü](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. **İleri** ' ye tıklayarak **uygulamalar** sayfasını görüntüleyin.<br>
    **Uygulamalar** sayfası, bu ilkeyi farklı cihazlardaki uygulamalara nasıl uygulamak istediğinizi seçmenizi sağlar. En az bir uygulama eklemeniz gerekir.<p>
    
    | Değer/seçenek | Description |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Tüm cihaz türlerindeki uygulamalar için hedef | İlkenizi herhangi bir yönetim durumundaki cihazlarda uygulamalara hedeflemek için bu seçeneği kullanın. Belirli cihaz türlerindeki uygulamaları hedeflemek için **Hayır** ' ı seçin. |
    |     Cihaz türleri | Bu ilkenin MDM yönetilen cihazlara veya yönetilmeyen cihazlara uygulanıp uygulanmayacağını belirtmek için bu seçeneği kullanın. İOS uygulama ilkeleri için **yönetilmeyen** ve **yönetilen** cihazlar arasından seçim yapın. Android uygulama ilkeleri için **yönetilmeyen**, **Android Cihaz Yöneticisi**ve **Android kurumsal**' i seçin.  |
    | Ortak uygulamalar | Hedeflenecek uygulamaları seçmek için **ortak uygulamaları seç** ' e tıklayın. |
    | Özel uygulamalar | Bir paket KIMLIĞINE göre hedeflemek üzere özel uygulamalar seçmek için **özel uygulamalar Seç** ' e tıklayın. |
    
    Seçtiğiniz uygulamalar ortak ve özel uygulamalar listesinde görünür. 
6. **İleri** ' ye tıklayarak **veri koruma** sayfasını görüntüleyin.<br>
    Bu sayfa, kesme, kopyalama, yapıştırma ve farklı kaydet kısıtlamaları dahil olmak üzere veri kaybı önleme (DLP) denetimleri için ayarlar sağlar. Bu ayarlar, kullanıcıların bu uygulama koruma ilkesinin uygulandığı uygulamalardaki verilerle nasıl etkileşime gireceğini tespit ediyor.

    **Veri koruma ayarları**:<br>
    - **iOS/ıpados veri koruma** -bilgi için bkz. [iOS uygulama koruma Ilkesi ayarları-veri koruma](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Android veri koruma** -bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-veri koruma](~/apps/app-protection-policy-settings-android.md#data-protection).

7. **İleri** ' ye tıklayarak **erişim gereksinimleri** sayfasını görüntüleyin.<br>
    Bu sayfa, kullanıcıların bir iş bağlamındaki uygulamalara erişmek için karşılaması gereken PIN ve kimlik bilgisi gereksinimlerini yapılandırmanıza izin veren ayarları sağlar. 
 
    **Erişim gereksinimleri ayarları**:<br>
    - **iOS/ıpados erişim gereksinimleri** -bilgi için bkz. [iOS uygulama koruma Ilkesi ayarları-erişim gereksinimleri](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Android erişim gereksinimleri** -daha fazla bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-erişim gereksinimleri](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. **Koşullu başlatma** sayfasını göstermek için **İleri** ' ye tıklayın.<br>
    Bu sayfa, uygulama koruma ilkeniz için oturum açma güvenlik gereksinimlerini ayarlamaya yönelik ayarları sağlar. Bir **Ayar** seçin ve kullanıcıların şirket uygulamanızda oturum açması için karşılaması gereken bir **Değer** girin. Ardından, kullanıcılar gereksinimlerinizi karşılamıyorsa gerçekleştirmek istediğiniz **eylemi** seçin. Bazı durumlarda tek bir ayar için birden çok eylem yapılandırılabilir.

    **Koşullu başlatma ayarları**:<br>
    - **iOS/ıpados koşullu başlatma** -bilgi için bkz. [iOS uygulama koruma Ilkesi ayarları-koşullu başlatma](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Android koşullu başlatma** -bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-koşullu başlatma](~/apps/app-protection-policy-settings-android.md#conditional-launch).

7. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.<br>
   **Atamalar** sayfası, uygulama koruma ilkesini Kullanıcı gruplarına atamanıza olanak tanır. 
8. **İleri** ' ye tıklayın ve bu uygulama koruma ilkesi için girdiğiniz değerleri ve ayarları gözden geçirin.
9. İşiniz bittiğinde, Intune 'da uygulama koruma ilkesini oluşturmak için **Oluştur** ' a tıklayın. 

## <a name="app-protection-policies-for-windows-10-apps"></a>Windows 10 uygulamaları için uygulama koruma ilkeleri

Windows 10 uygulamaları için bir uygulama koruma ilkesi oluşturduğunuzda, klasik bir Intune işlem akışını takip edersiniz.

### <a name="create-a-windows-10-app-protection-policy"></a>Windows 10 uygulama koruma ilkesi oluşturma
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Intune portalında, **istemci uygulamaları**  > **Uygulama koruma ilkeleri**' ni seçin. Bu seçim, yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
3. **Ilke oluştur**' u seçin.

    <img alt="Screenshot of the 'Create policy' blade for Windows 10" src="~/apps/media/app-protection-policies/app-protection-add-policy.png" width="350">

4. İlke için bir ad belirtin, kısa bir açıklama ekleyin ve ilkeniz için platform türünü seçin. Her platform için birden çok ilke oluşturabilirsiniz.

4. **Tüm uygulama türleri Için hedef**seçebilirsiniz seçeneğini belirleyebilirsiniz. Bu seçenek, ilkenizi herhangi bir yönetim durumunun cihazlarındaki uygulamalara hedefetmenize olanak tanır. İlke çakışma çözümü sırasında, bir kullanıcının belirli bir yönetim durumu için hedeflenmiş bir ilkesi varsa bu ayarın yerini alınır. Daha fazla bilgi için bkz. [Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme](~/apps/app-protection-policies.md#target-app-protection-policies-based-on-device-management-state).

5. Kullanılabilir uygulamaların listesini görüntüleyen **Uygulamalar** dikey penceresini açmak için **Uygulamalar**'ı seçin. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin. İlke oluşturmak için en az bir uygulama seçin.  

6. Uygulamaları seçtikten sonra seçiminizi kaydetmek için **Seç**’i seçin.

7. **İlke ekle** dikey penceresinde, **Ayarlar**’ı açmak için **Gerekli ayarları yapılandır**’ı seçin.

   İlke ayarları üç kategoriye ayrılır:
   - **Veri koruma** - Bu grup kesme, kopyalama, yapıştırma ve farklı kaydetme kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalarda verilerle nasıl etkileşim kurduğunu belirler.
   - **Erişim gereksinimleri** - Bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirleyen uygulama başına PIN seçenekleri içerir.  
   - **Koşullu başlatma** - Bu grup en düşük işletim sistemi ayarları, jailbreak uygulanmış ve kök erişim izni verilmiş cihazları algılama ve çevrimdışı yetkisiz kullanım süreleri gibi ayarları içerir.

   Başlamanıza yardımcı olması için ilke ayarlarına varsayılan değerler atanmıştır. Varsayılan değerler gereksinimlerinizi karşılıyorsa değişiklik yapmanız gerekmez.

   > [!TIP]
   > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır. Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez. Yeni bir dosya oluşturduğunuzda bunun kişisel bir dosya olarak kabul edildiğini unutmayın. 

8. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **İlke ekle** dikey penceresine geri dönersiniz.
9. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Oluşturduğunuz yeni Windows 10 ilkeleri, açıkça bunu yapana kadar hiçbir kullanıcıya atanmaz. Bir Windows 10 ilkesi atamak için bkz. [kullanıcılara Windows 10 Ilkesi atama](~/apps/app-protection-policies.md#assign-a-windows-10-policy-to-users)

### <a name="assign-a-windows-10-policy-to-users"></a>Kullanıcılara bir Windows 10 ilkesi atama 

1. **Uygulama koruma ilkeleri** bölmesinde, bir ilke seçin.

2. ***Intune Uygulama Koruması** bölmesinde, **Intune Uygulama Koruması - Atamalar** bölmesini açmak için **Atamalar**’ı seçin. *Ekle* sekmesinde **Dahil edilecek gruplar**’ı seçin. 

   ![Dahil edilecek grupları seçin menüsü ile Atamalar bölmesinin ekran görüntüsü](./media/app-protection-policies/app-protection-policy-add-users.png)

3. **Azure Active Directory**’nizdeki tüm güvenlik gruplarının listesi görüntülenir. Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da **Seç**'i kullanın. 

    ![Azure AD kullanıcılarının listesiyle Kullanıcı grubu ekle bölmesinin ekran görüntüsü](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Grupları dahil edip hariç tuttuktan sonra yapılandırmayı kaydetmek ve ilkeyi kullanıcılara dağıtmak için **Kaydet**'i seçin. Yapılandırmanızı kaydetmeden **Vazgeç**'i seçerseniz *Ekle* ve *Dışla* sekmesinde yaptığınız tüm değişiklikler silinir.   
 
     ![Kaydetme ve vazgeçme seçeneklerini gösteren ekran görüntüsü](./media/app-protection-policies/save-assignment.png)
  
Bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca Microsoft Intune lisansları atanmış kullanıcılar ilkeden etkilenir. Seçilen güvenlik grubunda atanmış Intune lisansına sahip olmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> Cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grubun içindeki alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)

### <a name="change-existing-windows-10-policies"></a>Mevcut Windows 10 ilkelerini değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri sekiz saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2. *Intune Uygulama Koruması* bölmesinde, uygulamaların listesini açmak için **Hedeflenen uygulamalar**’ı seçin.

3. Uygulamaları listeden kaldırın veya listeye ekleyin ve ardından değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

#### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

2. *Intune Uygulama Koruması* bölmesinde, bu ilkeye sahip mevcut kullanıcı gruplarının listesini gösteren **Intune Uygulama Koruması - Atamalar** bölmesini açmak için **Atamalar**'ı seçin.

3. İlkeye yeni bir kullanıcı grubu eklemek için, *Dahil Et* sekmesinde **Dahil edilecek grupları seç**’i ve kullanıcı grubunu seçin. Gruba eklemek için **Seç**'i belirleyin. 

4. Bir kullanıcı grubunu dışlamak için, *Dışla* sekmesinde **Dışlanacak grupları seç**’i ve kullanıcı grubunu seçin. Kullanıcı grubunu kaldırmak için **Seç**’i seçin.  

5. Önceden eklenen grupları silmek için *Ekle* veya *Dışla* sekmesinde üç noktayı (...) ve ardından **Sil**'i seçin. 

5. Atamalarda yaptığınız değişiklikler hazır duruma geldiğinde **Kaydet**'i seçerek yapılandırmayı kaydedebilir ve ilkeyi yeni kullanıcı grubuna dağıtabilirsiniz. Yapılandırmanızı kaydetmeden **Vazgeç**'i seçerseniz *Ekle* ve *Dışla* sekmesinde yaptığınız tüm değişiklikler silinir.

### <a name="to-change-windows-10-policy-settings"></a>Windows 10 ilke ayarlarını değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2. *Intune Uygulama Koruması* bölmesinde, düzenleyebileceğiniz ayar alanlarının listesini açmak için **Özellikler**’i seçin. 

3. Değiştirmek istediğiniz ayarların bulunduğu ayarlar alanını seçin (örneğin **Verileri yeniden konumlandırma** veya **Erişim gereksinimleri**). Ardından ayarları yeni değerlerle değiştirin.

4. Değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin. Tüm değişiklikleriniz tamamlanana kadar bir ayarlar alanı seçmek ve ardından değişikliklerinizi kaydetmek için işlemi yineleyin. Ardından *Intune Uygulama Koruması - Özellikler* bölmesini kapatabilirsiniz. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme
Pek çok kuruluşta son kullanıcıların Intune Mobil Cihaz Yönetimi (MDM) ile yönetilen cihazları (şirkete ait cihazlar gibi) ve yalnızca Intune uygulama koruma ilkeleriyle korunan yönetilmeyen cihazları kullanmalarına izin verilir. Yönetilmeyen cihazlar genellikle Kendi Cihazını Getir (KCG) cihazları olarak bilinir.

Intune uygulama koruma ilkeleri, bir kullanıcının kimliğini hedeflendiği için kullanıcı koruma ayarları hem kaydedilmiş (MDM ile yönetilen) hem de kaydedilmemiş (MDM’siz) cihazlara uygulanabilir. Bu nedenle bir Intune uygulama koruma ilkesinde Intune’a kayıtlı olan veya olmayan iOS ve Android cihazları hedefleyebilirsiniz. Kesin veri kaybı önleme (DLP) denetimlerinin yerinde olduğu yönetilmeyen cihazlar için bir koruma ilkenize ve MDM ile yönetilen cihazlar için DLP denetimlerinin çok daha gevşek olabileceği ayrı bir koruma ilkesine sahip olabilirsiniz. Bunun kişisel Android kurumsal cihazlarda nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri ve iş profilleri](android-deployment-scenarios-app-protection-work-profiles.md).

Bu ilkeleri oluşturmak için Intune konsolunda **İstemci uygulamaları** > **Uygulama koruma ilkeleri**'ne gidin ve **İlke Oluştur**’u seçin. Mevcut bir koruma ilkesini de düzenleyebilirsiniz. Uygulama koruma ilkesinin hem yönetilen hem de yönetilmeyen cihazlara uygulanmasını sağlamak için, **uygulamalar** sayfasına gidin ve **tüm cihaz türlerindeki uygulamalar hedefinin** , varsayılan değer olan **Evet**olarak ayarlandığını onaylayın. Yönetim durumuna göre daha fazla **atama yapmak istiyorsanız**, **hedefi tüm cihaz türlerindeki uygulamalar olarak** ayarlayın. 

![Tüm uygulama türlerini hedefle ile İlke ekle penceresinin ekran görüntüsü](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Uygulama türleri

- **Yönetilmeyen cihazlardaki uygulamalar**: yönetilmeyen cihazlar, Intune MDM yönetiminin algılanmadığı cihazlardır. Buna üçüncü taraf MDM satıcıları dahildir.
- **Intune yönetilen cihazlarındaki uygulamalar**: yönetilen cihazlar, Intune MDM tarafından yönetilir.
- **Android Iş profilindeki uygulamalar**: Android kurumsal iş profili cihazları olarak kaydedilmiş yönetilen cihazlar.

> Android cihazları, hangi uygulama türünün seçildiğine bakılmaksızın Intune Şirket Portalı uygulamasını yüklemek için istemde bulunur. Örneğin, ' Intune yönetilen cihazlarda uygulamalar ' ı seçerseniz, yönetilmeyen Android cihazlara sahip olan kullanıcılara yine de sorulacaktır.

İOS için, uygulama koruma ilkesi (uygulama) ayarlarını Intune 'a kayıtlı cihazlardaki uygulamalara hedeflemek için ek uygulama yapılandırma ayarları gerekir:

- MDM ile yönetilen tüm uygulamalarda **IntuneMAMUPN** yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- Üçüncü taraf ve LOB MDM ile yönetilen tüm uygulamalarda **IntuneMAMDeviceID** yapılandırılmalıdır. **IntuneMAMDeviceID**, cihaz kimliği belirtecinde yapılandırılmalıdır. Örneğin, `key=IntuneMAMDeviceID, value={{deviceID}}`. Daha fazla bilgi için bkz. [Yönetilen iOS cihazlar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-ios.md).
- Yalnızca **IntuneMAMDeviceID** yapılandırıldığında Intune uygulaması cihazı yönetilmeyen cihaz olarak görür.

> [!NOTE]
> Yönetim durumuna bağlı uygulama koruma ilkeleri hakkında belirli iOS destek bilgilerine ulaşmak istiyorsanız bkz. [Yönetim durumuna bağlı olarak hedeflenen MAM koruma ilkeleri](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>İlke ayarları
iOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdaki bağlantılardan birini seçin:

- [iOS ilkeleri](app-protection-policy-settings-ios.md)
- [Android ilkeleri](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](app-protection-policies-monitor.md)

## <a name="see-also"></a>Ayrıca bkz:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
