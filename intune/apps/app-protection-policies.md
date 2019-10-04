---
title: Uygulama koruma ilkeleri oluşturma ve dağıtma
titleSuffix: Microsoft Intune
description: Bu konu, Microsoft Intune uygulama koruma ilkelerinin (uygulama) nasıl oluşturulacağını ve atanacağını açıklamaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4958a35f3a83fecffacf26421e4c1d797f45ddaa
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940385"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkeleri oluşturma ve atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kullanıcılarınıza Microsoft Intune uygulama koruma ilkeleri oluşturmayı ve atamayı öğrenin. Bu konu başlığı altında, var olan ilkelerde nasıl değişiklik yapılacağı de açıklanmaktadır.

## <a name="before-you-begin"></a>Başlamadan önce

Uygulama koruma ilkeleri, Intune tarafından yönetilmeyen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin nasıl çalıştığı ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolarla ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma Ilkeleri nelerdir?](app-protection-policy.md)

MAM desteklenen uygulamaların bir listesini arıyorsanız, bkz. [mam Apps List](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Kuruluşunuzun iş kolu (LOB) uygulamalarını uygulama koruma ilkelerine hazırlanmak için Microsoft Intune ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](apps-add.md).

## <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
1. Intune portalında, **istemci uygulamaları** > **Uygulama koruma ilkeleri**' ne gidin. Bu seçim, yeni ilkeler oluşturduğunuz ve var olan ilkeleri düzenlediğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
2. **Ilke oluştur**' u seçin.

   ![' İlke Ekle ' dikey penceresinin ekran görüntüsü](./media/app-protection-policies/app-protection-add-policy.png)

3. İlke için bir ad belirtin, kısa bir açıklama ekleyin ve ilkenizin için Platform türünü seçin. Her platform için birden çok ilke oluşturabilirsiniz.

4. Uygulamalar **Dikey penceresini açmak için uygulamalar** ' ı seçin, burada **kullanılabilir uygulamalar listesi** görüntülenir. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin. İlke oluşturmak için en az bir uygulama seçin.  

5. Uygulamaları seçtikten sonra seçiminizi kaydetmek için **Seç** ' i seçin.

6. **Ilke Ekle** dikey penceresinde, **ayarları**açmak için **gerekli ayarları Yapılandır** ' ı seçin.

   İlke ayarlarının üç kategorisi vardır:
   - **Veri koruma** -bu grup, kesme, kopyalama, yapıştırma ve farklı kaydet kısıtlamaları gibi veri kaybı önleme (DLP) denetimlerini içerir. Bu ayarlar, kullanıcıların uygulamalardaki verilerle nasıl etkileşime gireceğini tespit ediyor.
   - **Erişim gereksinimleri** -bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini tespit eden uygulama başına PIN seçeneklerini içerir.  
   - **Koşullu başlatma** -bu grup, en düşük işletim sistemi ayarları, jailbreak ve kökü belirtilmiş cihaz algılama ve çevrimdışı kullanım süreleri gibi ayarları barındırır.

   Çalışmaya başlamak için, ilke ayarlarının varsayılan değerleri vardır. Varsayılan değerler gereksinimlerinizi karşılıyorsa, herhangi bir değişiklik yapmanız gerekmez.

   > [!TIP]
   > Bu ilke ayarları, yalnızca iş bağlamındaki uygulamalar kullanılırken uygulanır. Son kullanıcılar, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez. Yeni bir dosya oluşturduğunuzda kişisel bir dosya olarak kabul edileceğini unutmayın. 

7. Bu yapılandırmayı kaydetmek için **Tamam ' ı** seçin. **Ilke Ekle** dikey penceresine geri dönersiniz.
8. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur** ' u seçin.

Oluşturduğunuz yeni ilkeler, açıkça bunu yapana kadar hiçbir kullanıcıya dağıtılmaz. Bir ilkeyi dağıtmak için bkz. [bir ilkeyi kullanıcılara dağıtma](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Kullanıcılara ilke dağıtma

1. **Uygulama koruma ilkeleri** bölmesinde bir ilke seçin.

2. ***Intune uygulama koruması** bölmesinde, **Intune uygulama koruması** atamaları bölmesini açmak için **atamalar** ' ı seçin. *Dahil et* sekmesinde **dahil edilecek grupları seç**' i seçin. 

   ![Dahil edilecek grupları seç menü içeren atamalar bölmesinin ekran görüntüsü](./media/app-protection-policies/app-protection-policy-add-users.png)

3. **Azure Active Directory** tüm güvenlik gruplarının bir listesi görüntülenir. Bu ilkenin uygulanmasını istediğiniz kullanıcı gruplarını seçin ve ardından **Seç**' i seçin. 

    ![Azure AD kullanıcıları listesi ile Kullanıcı grubu ekle bölmesinin ekran görüntüsü](./media/app-protection-policies/azure-ad-user-group-list.png)

4. Grupları dahil ettikten Ve dışladıktan sonra, yapılandırmayı kaydetmek ve ilkeyi kullanıcılara dağıtmak için **Kaydet** ' i seçin. Yapılandırmanızı kaydetmeden önce **at** ' ı seçerseniz, *dahil etme* ve *çıkarma* sekmelerinde yaptığınız tüm değişiklikleri atlayacak.   
 
     ![Kaydet ve çıkart seçeneklerini gösteren ekran görüntüsü](./media/app-protection-policies/save-assignment.png)
  
Şimdi bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca atanmış Microsoft Intune lisansa sahip kullanıcılar ilkeden etkilenir. Seçili güvenlik grubundaki, atanmış bir Intune lisansı bulunmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> Cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız, ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grup içinde iç içe geçmiş alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store 'dan veya Google Play indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [İOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Var olan bir ilkeyi düzenleyebilir ve hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde, uygulamalarda zaten oturum açmış olan kullanıcılar sekiz saatlik bir dönem için değişiklikleri görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulamayı oturumu kapatıp yeniden oturum açması gerekir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamaların listesini değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde, **hedeflenen uygulamalar** ' ı seçerek uygulama listesini açın.

3. Listeden uygulamaları kaldırın veya listeye ekleyin ve sonra değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için


1. **Uygulama koruma ilkeleri** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde, bu ilkeye sahip geçerli kullanıcı gruplarının listesini gösteren **Intune uygulama koruması atamaları** bölmesini açmak için **atamalar** ' ı seçin.

3. İlkeye yeni bir Kullanıcı grubu eklemek için, *Ekle* sekmesinde **dahil edilecek grupları seç**' i seçin ve kullanıcı grubunu seçin. Grubu eklemek için **Seç ' i** seçin. 

4. Bir kullanıcı grubunu dışlamak için *Dışla* sekmesinde **hariç tutulacak grupları seçin**' i seçin ve kullanıcı grubunu seçin. Kullanıcı grubunu kaldırmak için **Seç ' i** seçin.  

5. Daha önce eklenen grupları silmek için, *Ekle* veya *Dışla* sekmelerinde üç nokta (...) simgesini seçin ve **Sil**' i seçin. 

5. Atamalardaki değişiklikleriniz hazırlandıktan sonra, yapılandırmayı kaydetmek ve ilkeyi yeni kullanıcı kümesine dağıtmak için **Kaydet** ' i seçin. Yapılandırmanızı kaydetmeden önce **at** ' ı seçerseniz, *dahil etme* ve *çıkarma* sekmelerinde yaptığınız tüm değişiklikleri atlayacak.

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde **Özellikler** ' i seçerek düzenleyebileceğiniz ayar alanlarının listesini açın. 

3. **Veri konumu** değiştirme veya **erişim gereksinimleri**gibi, değiştirmek istediğiniz ayarların bulunduğu ayarlar alanını seçin. Sonra ayarları yeni değerlerle değiştirin.

4. Değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin. Tüm değişiklikleriniz tamamlanana kadar bir ayarlar alanı seçip değişikliklerinizi değiştirip değişiklikleri kaydederek işlemi tekrarlayın. Daha sonra *Intune uygulama koruması-Özellikler* bölmesini kapatabilirsiniz. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkelerini hedefleme
Birçok kuruluşta, son kullanıcıların, şirkete ait cihazlar gibi Intune mobil cihaz yönetimi (MDM) ile yönetilen cihazları ve yalnızca Intune uygulama koruma ilkeleriyle korunan yönetilmeyen cihazları kullanmasına izin vermek yaygın bir uygulamadır. Yönetilmeyen cihazlar genellikle kendi cihazlarını getir (KCG) olarak bilinir.

Intune uygulama koruma ilkeleri bir kullanıcının kimliğini hedeflemesini sağladığından, bir kullanıcı için koruma ayarları, kayıtlı (MDM tarafından yönetilen) ve kayıtlı olmayan cihazlara (MDM yok) uygulanabilir. Bu nedenle, Intune 'a kayıtlı veya kayıtlı olmayan iOS ve Android cihazlar için bir Intune uygulama koruma ilkesini hedefleyebilirsiniz. Kesin veri kaybı önleme (DLP) denetimlerinin yerinde olduğu yönetilmeyen cihazlar için bir koruma ilkenize ve MDM ile yönetilen cihazlar için DLP denetimlerinin çok daha gevşek olabileceği ayrı bir koruma ilkesine sahip olabilirsiniz. Bunun kişisel Android Enterprise cihazlarında nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri ve iş profilleri](android-deployment-scenarios-app-protection-work-profiles.md).

Bu ilkeleri oluşturmak için Intune konsolundaki **istemci uygulamaları** > **Uygulama koruma ilkeleri** ' ne gidin ve ardından **ilke oluştur**' u seçin. Ayrıca, var olan bir uygulama koruma ilkesini de düzenleyebilirsiniz. Uygulama koruma ilkesinin hem yönetilen hem de yönetilmeyen cihazlara uygulanmasını sağlamak için, **tüm uygulama türleri hedefinin** , varsayılan değer olan **Evet**olarak ayarlandığını onaylayın. Yönetim durumuna temelsiz atama yapmak istiyorsanız, **hedefi tüm uygulama türlerine** **Hayır**olarak ayarlayın. 

![Tüm uygulama türlerine hedefle bir ilke Ekle dikey penceresinin ekran görüntüsü](./media/app-protection-policies/app-protection-policies-target-all.png)

### <a name="app-types"></a>Uygulama türleri

- **Yönetilmeyen cihazlardaki uygulamalar**: yönetilmeyen cihazlar, Intune MDM yönetiminin algılanmadığı cihazlardır. Buna üçüncü taraf MDM satıcıları dahildir.
- **Intune yönetilen cihazlarındaki uygulamalar**: yönetilen cihazlar, Intune MDM tarafından yönetilir.
- **Android Iş profilindeki uygulamalar**: Android kurumsal iş profili cihazları olarak kaydedilmiş yönetilen cihazlar.

> Android cihazları, hangi uygulama türünün seçildiğine bakılmaksızın Intune Şirket Portalı uygulamasını yüklemek için istemde bulunur. Örneğin, ' Intune yönetilen cihazlarda uygulamalar ' ı seçerseniz, yönetilmeyen Android cihazlara sahip olan kullanıcılara yine de sorulacaktır.

İOS için, uygulama koruma ilkesi (uygulama) ayarlarını Intune 'a kayıtlı cihazlardaki uygulamalara hedeflemek için ek uygulama yapılandırma ayarları gerekir:

- **Intunemamupn** , tüm MDM ile yönetilen uygulamalar için yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **Intunemamdeviceıd** , tüm üçüncü taraf ve LOB MDM ile yönetilen uygulamalar için yapılandırılmalıdır. **Intunemamdeviceıd** , cihaz kimliği belirtecine yapılandırılmalıdır. Örneğin, `key=IntuneMAMDeviceID, value={{deviceID}}`. Daha fazla bilgi için bkz. [yönetilen iOS cihazları için uygulama yapılandırma Ilkeleri ekleme](app-configuration-policies-use-ios.md).
- Yalnızca **ıntunemamdeviceıd** yapılandırılmışsa, Intune uygulaması cihazı yönetilmeyen olarak kabul eder.

> [!NOTE]
> Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hakkında belirli iOS destek bilgileri için, bkz. [Yönetim durumuna göre hedeflenen mam koruma ilkeleri](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>İlke ayarları
İOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdaki bağlantılardan birini seçin:

- [iOS ilkeleri](app-protection-policy-settings-ios.md)
- [Android ilkeleri](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve Kullanıcı durumunu izleme](app-protection-policies-monitor.md)

## <a name="see-also"></a>Ayrıca bkz.
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [İOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
