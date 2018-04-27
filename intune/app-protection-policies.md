---
title: Uygulama koruma ilkelerini oluşturma ve dağıtma
titleSuffix: Microsoft Intune
description: Microsoft Intune uygulama koruma ilkelerini oluşturmayı ve atamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ffe409e376ec2d15c537fb6ac258e5b3b71cdf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkelerini oluşturma ve atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune uygulama koruma ilkelerini oluşturmayı ve kullanıcılarınıza atamayı öğrenin. Bu konu, mevcut ilkelerde nasıl değişiklik yapılacağını da açıklar.

## <a name="before-you-begin"></a>Başlamadan önce

Klasik Intune portalında yönergeler arıyorsanız bkz. [uygulama koruma ilkeleri oluşturma](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

Uygulama koruma ilkeleri, Intune tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin çalışmasıyla ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolarla ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma ilkeleri nedir](app-protection-policy.md).

MAM destekli uygulamalar listesi arıyorsanız bkz. [MAM uygulamaları listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
1. **Mobil uygulamalar** iş yükünde, **Yönet** bölümünden **Uygulama koruma ilkeleri**’ni seçin. Bu seçim, yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
2. **İlke ekle**‘yi seçin.

   ![“İlke ekle” dikey penceresinin ekran görüntüsü](./media/app-protection-add-policy.png)

3. İlke için bir ad yazın, kısa bir açıklama ekleyin ve ilkeniz için platform türünü seçin. Gerekirse, her platform için birden çok ilke oluşturabilirsiniz.

4. Kullanılabilir uygulamaların listesini görüntüleyen **Uygulamalar dikey penceresini** açmak için **Uygulamalar**'ı seçin. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin.
5. Uygulamaları seçtikten sonra seçiminizi kaydetmek için **Seç**’i seçin.

    > [!IMPORTANT]
    > Bir ilke oluşturmak için en az bir uygulama seçmeniz gerekir.

6. **Ayarlar**’ı açmak için **İlke ekle** dikey penceresinde **Gerekli ayarları yapılandır**’ı seçin.

   İlke ayarlarının iki kategorisi vardır: **Veri konumu değiştirme** ve **Erişim**.  Veri konumunu değiştirme ilkeleri, uygulamalara giren ve çıkan veri hareketlerine uygulanabilir. Erişim ilkeleri, son kullanıcının bir çalışma bağlamında uygulamalara nasıl eriştiğini belirler.
   Başlamanıza yardımcı olması için ilke ayarlarına varsayılan değerler atanmıştır. Varsayılan değerler gereksinimlerinizi karşılıyorsa değişiklik yapmanız gerekmez.

   > [!TIP]
   > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır. Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez.

7. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **İlke ekle** bölmesine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.
8. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **İlke ekle** dikey penceresine geri dönersiniz.
9. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

İlke oluşturmayı önceki yordamda açıklandığı şekilde tamamladığınızda, ilke kullanıcılara dağıtılmaz. Bir ilkeyi dağıtmak için bkz. [Bir ilkeyi kullanıcılara dağıtma](app-protection-policies.md#deploy-a-policy-to-users).

## <a name="deploy-a-policy-to-users"></a>Bir ilkeyi kullanıcılara dağıtma


1. **Uygulama koruma ilkeleri** bölmesinde, bir ilke seçin.

1. **İlke** bölmesinde **Atamaları** seçin; böylece **Intune Uygulama Koruması - Atamalar** bölmesi açılır. **Atamalar** bölmesinde **Dahil edilecek grupları seçin**’i seçerek, **Dahil edilecek grupları seçin** bölmesini açın.

   ![Dahil edilecek grupları seçin menü seçeneği vurgulanmış olarak Atamalar bölmesinin ekran görüntüsü](./media/app-protection-policy-add-users.png)

2.  **Kullanıcı grubu ekle** bölmesinde kullanıcı gruplarının listesi gösterilir. Bu liste **Azure Active Directory**’nizdeki tüm güvenlik gruplarını gösterir. Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da **Seç**'i belirleyin. **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

    ![Azure Active Directory kullanıcılarının listesini gösteren Kullanıcı grubu ekle bölmesinin ekran görüntüsü](./media/azure-ad-user-group-list.png)

Bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca Microsoft Intune lisansları atanmış kullanıcılar ilkeden etkilenir. Seçilen güvenlik grubunda atanmış Intune lisansına sahip olmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> Cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grubun içindeki alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde, uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri 8 saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1.  **Uygulama koruma ilkeleri** bölmesinde yeni seçtiğiniz ilkeye özel bir bölme açmak için değiştirmek istediğiniz ilkeyi seçin.

2.  İlke bölmesinde **Hedeflenen uygulamalar**’ı seçerek uygulama listesini açın.

3.  Uygulamaları listeden kaldırın veya listeye ekleyin ve değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için


1.  **Uygulama koruma ilkeleri** bölmesinde seçtiğiniz ilkeye özel bir bölme açmak için değiştirmek istediğiniz ilkeyi seçin.

2.  İlke bölmesinde, bu ilkeye sahip mevcut kullanıcı gruplarının listesini gösteren **Intune Uygulama Koruması - Atamalar** bölmesini açmak için **Atamalar**'ı seçin.

3.  İlkeye yeni bir kullanıcı grubu eklemek için, **Dahil Et** sekmesinde **Dahil edilecek grupları seç**’i ve kullanıcı grubunu seçin. İlkeyi seçtiğiniz gruba dağıtmak için **Seç**öğesini seçin.

4.  Bir kullanıcı grubunu silmek için, **Dışla** sekmesinde **Dışlanacak grupları seç**’i ve kullanıcı grubunu seçin. Kullanıcı grubunu kaldırmak için **Seç**’i seçin.

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1.  **Uygulama koruma ilkeleri** bölmesinde yeni seçtiğiniz ilkeye özel bir bölme açmak için değiştirmek istediğiniz ilkeyi seçin.

2.  **İlke ayarları**’nı seçerek **İlke ayarları** bölmesini açın.

3.  Ayarları değiştirin ve **Kaydet** simgesini seçerek yaptığınız değişiklikleri kaydedin.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme
Pek çok kuruluşta son kullanıcıların Intune Mobil Cihaz Yönetimi (MDM) ile yönetilen cihazları (şirkete ait cihazlar gibi) ve yalnızca Intune uygulama koruma ilkeleriyle korunan yönetilmeyen cihazları (KCG cihazlar gibi) kullanmalarına izin verilir.

Intune uygulama koruma ilkeleri, bir kullanıcının kimliğine hedeflendiği için kullanıcı koruma ayarları eskiden beri hem kaydedilmiş (MDM ile yönetilen) ve kaydedilmemiş (MDM’siz) cihazlara uygulanır. Bu sebeple bir Intune uygulama koruma ilkesini Intune’a kayıtlı olan veya olmayan iOS ve Android cihazlara hedefleyebilirsiniz. Yönetilmeyen cihazlar için katı veri kaybı önleme (DLP) denetimlerinin etkin olduğu bir koruma ilkesi ve MDM ile yönetilen cihazlar için DLP denetimlerinin daha esnek olabileceği ayrı bir koruma ilkesi yapılandırabilirsiniz. 

Bu ilkeleri oluşturmak için Intune konsolunda **Mobil uygulamalar** > **Uygulama koruma** ilkelerine gözatın ve **Bir ilke ekle**’ye tıklayın. Mevcut bir koruma ilkesini de düzenleyebilirsiniz. Uygulama koruma ilkesinin hem yönetilen hem yönetilmeyen cihazlara uygulanmasını istiyorsanız, **Tüm uygulama türlerine hedefle**’nin varsayılan değer olan **Evet** olarak ayarlandığını doğrulayın. Yönetim durumuna bağlı olarak ayrı atamalar yapmak istiyorsanız **Tüm uygulama türlerine hedefle** seçeneğini **Hayır** olarak ayarlayın. 

> [!NOTE]
> Yönetim durumuna bağlı uygulama koruma ilkeleri hakkında belirli iOS destek bilgilerine ulaşmak istiyorsanız bkz. [Yönetim durumuna bağlı olarak hedeflenen MAM koruma ilkeleri](whats-new.md#mam-protection-policies-targeted-based-on-management-state----1665993---).

## <a name="policy-settings"></a>İlke ayarları
iOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdaki bağlantılardan birini seçin:

- [iOS ilkeleri](app-protection-policy-settings-ios.md)
- [Android ilkeleri](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](app-protection-policies-monitor.md)

### <a name="see-also"></a>Ayrıca bkz:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)
