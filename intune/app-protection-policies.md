---
title: Uygulama koruma ilkelerini oluşturma ve dağıtma
titleSuffix: Microsoft Intune
description: Bu konuda, oluşturma ve atama Intune uygulama koruma ilkelerini (APP) açıklar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db4f218f41dbbbdfbdde5cb32efd561a224222f3
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57400305"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkelerini oluşturma ve atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune uygulama koruma ilkelerini oluşturmayı ve kullanıcılarınıza atamayı öğrenin. Bu konu, mevcut ilkelerde nasıl değişiklik yapılacağını da açıklar.

## <a name="before-you-begin"></a>Başlamadan önce

Uygulama koruma ilkeleri, Intune tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin çalışması ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolar ile ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

MAM destekli uygulamalar listesi arıyorsanız bkz. [MAM uygulamaları listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Kuruluşunuzun iş kolu (LOB) uygulamalarını uygulama koruma ilkelerine hazırlamak üzere Microsoft Intune'a ekleme hakkında bilgi için bkz. [Uygulamaları Microsoft Intune'a ekleme](apps-add.md).

##  <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
1. Intune portalında **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ne gidin. Bu seçim, yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
2. **İlke Oluştur**'u seçin.

   ![“İlke ekle” dikey penceresinin ekran görüntüsü](./media/app-protection-add-policy.png)

3. İlke için bir ad belirtin, kısa bir açıklama ekleyin ve ilkeniz için platform türünü seçin. Her platform için birden çok ilke oluşturabilirsiniz.

4. Kullanılabilir uygulamaların listesini görüntüleyen **Uygulamalar** dikey penceresini açmak için **Uygulamalar**'ı seçin. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin. İlke oluşturmak için en az bir uygulama seçin.  

5. Uygulamaları seçtikten sonra seçiminizi kaydetmek için **Seç**’i seçin.

6. **İlke ekle** dikey penceresinde, **Ayarlar**’ı açmak için **Gerekli ayarları yapılandır**’ı seçin.

   İlke ayarları üç kategoriye ayrılır:
   - **Veri koruma** -veri kaybı önleme (DLP) denetimleri, kaydetme ve kesme, kopyalama, yapıştırma gibi bu grup içeren-kısıtlamaları olarak. Bu ayarlar, kullanıcıların uygulamalarda verilerle nasıl etkileşim kurduğunu belirler.
   - **Erişim gereksinimleri** - Bu grup, son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirleyen uygulama başına PIN seçenekleri içerir.  
   - **Koşullu başlatma** - Bu grup en düşük işletim sistemi ayarları, jailbreak uygulanmış ve kök erişim izni verilmiş cihazları algılama ve çevrimdışı yetkisiz kullanım süreleri gibi ayarları içerir.

   Başlamanıza yardımcı olması için ilke ayarlarına varsayılan değerler atanmıştır. Varsayılan değerler gereksinimlerinizi karşılıyorsa değişiklik yapmanız gerekmez.

   > [!TIP]
   > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır. Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez. Yeni bir dosya oluşturduğunuzda bunun kişisel bir dosya olarak kabul edildiğini unutmayın. 

7. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **İlke ekle** dikey penceresine geri dönersiniz.
8. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Oluşturduğunuz yeni ilkeler siz açıkça dağıtana kadar herhangi bir kullanıcıya dağıtılmaz. Bir ilkeyi dağıtmak için bkz. [Bir ilkeyi kullanıcılara dağıtma](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Bir ilkeyi kullanıcılara dağıtma

1. **Uygulama koruma ilkeleri** bölmesinde, bir ilke seçin.

2. ***Intune Uygulama Koruması** bölmesinde, **Intune Uygulama Koruması - Atamalar** bölmesini açmak için **Atamalar**’ı seçin. *Ekle* sekmesinde **Dahil edilecek gruplar**’ı seçin. 

   ![Grupları seçin menü eklemek için atamalar bölmesinin ekran görüntüsü](./media/app-protection-policy-add-users.png)

3.  **Azure Active Directory**’nizdeki tüm güvenlik gruplarının listesi görüntülenir. Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da **Seç**'i kullanın. 

    ![Kullanıcı grubu Ekle bölmesinin ekran görüntüsü ile Azure AD kullanıcı listesi](./media/azure-ad-user-group-list.png)

4.  Dahil ve grupları dışlama sonra seçin **Kaydet** yapılandırmayı kaydedin ve ilkeyi kullanıcılara dağıtma. Seçerseniz **at** yapılandırmanızı kaydetmeden önce için yaptığınız tüm değişiklikleri atacak *INCLUDE* ve *hariç* sekmeler.   
 
     ![Kaydetme gösteren ekran görüntüsü ve seçenekleri atın](./media/save-assignment.png)
  
Bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca Microsoft Intune lisansları atanmış kullanıcılar ilkeden etkilenir. Seçilen güvenlik grubunda atanmış Intune lisansına sahip olmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> Cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grubun içindeki alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri sekiz saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1.  **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2.  *Intune Uygulama Koruması* bölmesinde, uygulamaların listesini açmak için **Hedeflenen uygulamalar**’ı seçin.

3.  Uygulamaları listeden kaldırın veya listeye ekleyin ve ardından değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için


1.  **Uygulama koruma ilkeleri** bölmesinde, değiştirmek istediğiniz ilkeyi seçin.

2.  *Intune Uygulama Koruması* bölmesinde, bu ilkeye sahip mevcut kullanıcı gruplarının listesini gösteren **Intune Uygulama Koruması - Atamalar** bölmesini açmak için **Atamalar**'ı seçin.

3.  İlkeye yeni bir kullanıcı grubu eklemek için, *Dahil Et* sekmesinde **Dahil edilecek grupları seç**’i ve kullanıcı grubunu seçin. Seçin **seçin** grubu eklemek için. 

4.  Bir kullanıcı grubu dışlanacak *hariç* sekmesini seçin **dışlanacak Grupları Seç**ve kullanıcı grubunu seçin. Kullanıcı grubunu kaldırmak için **Seç**’i seçin.  

5.  Daha önce üzerinde eklenen grubunu silmek için *INCLUDE* veya *hariç* sekmeler, nokta (...) seçip **Sil**. 

5.  Değişikliklerinizi atamalarını hazır olduktan sonra seçin **Kaydet** yapılandırmayı kaydedin ve ilkeyi kullanıcılara yeni kümesine dağıtmak için. Seçerseniz **at** yapılandırmanızı kaydetmeden önce için yaptığınız tüm değişiklikleri atacak *INCLUDE* ve *hariç* sekmeler.

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1.  **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2.  *Intune Uygulama Koruması* bölmesinde, düzenleyebileceğiniz ayar alanlarının listesini açmak için **Özellikler**’i seçin. 

3.  Değiştirmek istediğiniz ayarların bulunduğu ayarlar alanını seçin (örneğin **Verileri yeniden konumlandırma** veya **Erişim gereksinimleri**). Ardından ayarları yeni değerlerle değiştirin.

4.  Değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin. Tüm değişiklikleriniz tamamlanana kadar bir ayarlar alanı seçmek ve ardından değişikliklerinizi kaydetmek için işlemi yineleyin. Ardından *Intune Uygulama Koruması - Özellikler* bölmesini kapatabilirsiniz. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme
Pek çok kuruluşta son kullanıcıların Intune Mobil Cihaz Yönetimi (MDM) ile yönetilen cihazları (şirkete ait cihazlar gibi) ve yalnızca Intune uygulama koruma ilkeleriyle korunan yönetilmeyen cihazları kullanmalarına izin verilir. Yönetilmeyen cihazlar genellikle Kendi Cihazını Getir (KCG) cihazları olarak bilinir.

Intune uygulama koruma ilkeleri, bir kullanıcının kimliğini hedeflendiği için kullanıcı koruma ayarları hem kaydedilmiş (MDM ile yönetilen) hem de kaydedilmemiş (MDM’siz) cihazlara uygulanabilir. Bu nedenle bir Intune uygulama koruma ilkesinde Intune’a kayıtlı olan veya olmayan iOS ve Android cihazları hedefleyebilirsiniz. Yönetilmeyen cihazlar için katı veri kaybı önleme (DLP) denetimlerinin etkin olduğu bir koruma ilkesi ve MDM ile yönetilen cihazlar için DLP denetimlerinin daha esnek olabileceği ayrı bir koruma ilkesi yapılandırabilirsiniz. 

Bu ilkeleri oluşturmak için Intune konsolunda **İstemci uygulamaları** > **Uygulama koruma ilkeleri**'ne gidin ve **İlke Oluştur**’u seçin. Mevcut bir koruma ilkesini de düzenleyebilirsiniz. Uygulama koruma ilkesinin hem yönetilen hem yönetilmeyen cihazlara uygulanması için, **Tüm uygulama türlerini hedefle**’nin varsayılan değer olan **Evet** değerine ayarlandığını doğrulayın. Yönetim durumuna bağlı olarak ayrı atamalar yapmak istiyorsanız **Tüm uygulama türlerini hedefle** seçeneğini **Hayır** olarak ayarlayın. 

![Tüm uygulama türleri için hedef Ekle İlkesi dikey penceresinin ekran görüntüsü](./media/app-protection-policies-target-all.png)

Uygulama ayarlarının Intune'a kayıtlı cihazlardaki uygulamalara yansıtılması için iOS cihazlarda ek uygulama yapılandırma ayarları gereklidir:
- MDM ile yönetilen tüm uygulamalarda **IntuneMAMUPN** yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune’da iOS uygulamaları arasında veri aktarımını yönetme](https://docs.microsoft.com/intune/data-transfer-between-apps-manage-ios#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- Üçüncü taraf ve LOB MDM ile yönetilen tüm uygulamalarda **IntuneMAMDeviceID** yapılandırılmalıdır. **IntuneMAMDeviceID**, cihaz kimliği belirtecinde yapılandırılmalıdır. Örneğin, `key=IntuneMAMDeviceID, value={{deviceID}}`. Daha fazla bilgi için bkz. [Yönetilen iOS cihazlar için uygulama yapılandırma ilkeleri ekleme](https://docs.microsoft.com/intune/app-configuration-policies-use-ios).
- Yalnızca **IntuneMAMDeviceID** yapılandırıldığında Intune uygulaması cihazı yönetilmeyen cihaz olarak görür.  

> [!NOTE]
> Yönetim durumuna bağlı uygulama koruma ilkeleri hakkında belirli iOS destek bilgilerine ulaşmak istiyorsanız bkz. [Yönetim durumuna bağlı olarak hedeflenen MAM koruma ilkeleri](whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state-).

## <a name="policy-settings"></a>İlke ayarları
iOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdaki bağlantılardan birini seçin:

- [iOS ilkeleri](app-protection-policy-settings-ios.md)
- [Android ilkeleri](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](app-protection-policies-monitor.md)

### <a name="see-also"></a>Ayrıca bkz.
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)
