---
title: "Uygulama koruma ilkelerini oluşturma ve dağıtma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune uygulama koruma ilkelerinin, yönettiğiniz uygulamalarda kullanılan şirket verilerinin korunmasına nasıl yardımcı olabileceğini öğrenin."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 119c7172f8175d128c3e13d37bb9ec3c91719bcf
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkelerini oluşturma ve atama

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Azure Portal önizleme programındaki Intune hizmetinde değilseniz**, bu konu başlığı altında klasik Intune konsolunda [uygulama koruma ilkelerinin nasıl oluşturulacağı](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) anlatılır.

Uygulama koruma ilkeleri, Intune tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin çalışmasıyla ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolarla ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma ilkeleri nedir](what-is-app-protection-policy.md).

##  <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma
1.  **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulama koruma ilkeleri**’ni seçin.

2.  Yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** dikey penceresi açılır. **İlke ekle**‘yi seçin.

  ![İlke ekle dikey penceresinin ekran görüntüsü](../media/app-protection-add-policy.png)

3.  İlke için bir ad yazın, kısa bir açıklama ekleyin ve iOS veya Android için ilke oluşturmak üzere platform türünü seçin. Her platform için birden çok ilke oluşturabilirsiniz.

4.  Kullanılabilir uygulamaların listesini görüntüleyen **Uygulamalar dikey penceresini** açmak için **Uygulamalar**'ı seçin. Oluşturmakta olduğunuz ilke ile ilişkilendirmek istediğiniz bir veya daha fazla uygulamayı listeden seçin. Uygulamaları seçtikten sonra, seçiminizi kaydetmek için **Uygulamalar** dikey penceresinin altındaki **Seç**'i kullanın.

    > [!IMPORTANT]
    > Bir ilke oluşturmak için en az bir uygulama seçmeniz gerekir.

5.  **İlke ekle dikey penceresinde** **Gerekli ayarları yapılandır**’ı seçerek ilke ayarları dikey penceresini açın.

    İlke ayarlarının iki kategorisi vardır: **Veri konumu değiştirme** ve **Erişim**.  Veri konumu değiştirme ilkeleri, uygulama içindeki ve dışındaki veri hareketleri için geçerlidir. Erişim ilkeleri ise son kullanıcının uygulamalara iş bağlamında nasıl eriştiğini belirler.
    Başlamanıza yardımcı olması için ilke ayarlarına varsayılan değerler atanmıştır. Varsayılan değerler gereksinimlerinizi karşılıyorsa değişiklik yapmanız gerekmez.

    > [!TIP]
    > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır.  Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez.



6.  Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **İlke ekle** dikey penceresine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.


İlke oluşturmayı önceki yordamda açıklandığı şekilde tamamladığınızda, ilke kullanıcılara dağıtılmaz. Bir ilkeyi dağıtmak için aşağıdaki "Bir ilkeyi kullanıcılara dağıtma" bölümüne bakın.

## <a name="deploy-a-policy-to-users"></a>Bir ilkeyi kullanıcılara dağıtma

1.  **İlke** dikey penceresinde  **Kullanıcı grupları**‘nı seçerek **Kullanıcı grupları** dikey penceresini açın. **Kullanıcı grupları** dikey penceresinde **Kullanıcı grubu ekle**’yi seçerek **Kullanıcı grubu ekle** dikey penceresini açın.

  ![Kullanıcı grubu ekle menü seçeneğinin vurgulandığı Kullanıcı grupları dikey penceresinin ekran görüntüsü](../media/app-protection-policy-add-users.png)

2.  **Kullanıcı grubu ekle** dikey penceresinde kullanıcı gruplarının listesi gösterilir. Bu liste **Azure Active Directory**’deki tüm güvenlik gruplarını içerir. Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da **Seç**'i belirleyin. **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.
  ![Azure Active Directory kullanıcılarının listesini gösteren Kullanıcı grubu ekle dikey penceresinin ekran görüntüsü](../media/azure-ad-user-group-list.png)

Bir ilke oluşturdunuz ve kullanıcılara dağıttınız.

Yalnızca Microsoft Intune lisansları atanmış kullanıcılar ilkeden etkilenir. Seçtiğiniz güvenlik grubunda olan ve atanmış Microsoft Intune lisansı bulunmayan kullanıcılar etkilenmez.

>[!IMPORTANT]
> iOS ve Android cihazlarınızı yönetmek için Configuration Manager ile Intune kullanıyorsanız ilke yalnızca doğrudan seçtiğiniz grupta bulunan kullanıcılara uygulanır. Seçtiğiniz grubun içindeki alt grupların üyeleri etkilenmez.

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-android-apps.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-ios-apps.md)

##  <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde, uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri 8 saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekecektir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.

2.  İlke dikey penceresinde **Hedeflenen uygulamalar**’ı seçerek uygulama listesini açın.

3.  Uygulamaları listeden kaldırın veya listeye ekleyin ve değişikliklerinizi kaydetmek için **Kaydet** simgesini seçin.

### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.

2.  İlke dikey penceresinde **Kullanıcı grupları**’nı seçerek, bu ilkeye sahip geçerli kullanıcı gruplarının listesini gösteren **Kullanıcı grubu** dikey penceresini açın.

3.  İlkeye yeni kullanıcı grubu eklemek için **Kullanıcı grubu ekle**'yi seçin ve sonra da kullanıcı grubunu seçin. İlkeyi seçtiğiniz gruba dağıtmak için **Seç**öğesini seçin.

4.  Bir kullanıcı grubunu silmek için önce kaldırmak istediğiniz kullanıcı grubunu vurgulayın. Ardından üç noktaya (…) tıklayın ve **Sil**'i seçerek kullanıcı grubunu kaldırın.
  ![Sil seçeneğinin gösterildiği ekran görüntüsü ](../media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1.  **Uygulama ilkesi** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. Seçtiğiniz ilkeye özel bir dikey pencere açılır.


2.  **İlke ayarları**’nı seçerek **İlke ayarları** dikey penceresini açın.

3.  Ayarları değiştirin ve **Kaydet** simgesini seçerek yaptığınız değişiklikleri kaydedin.

## <a name="policy-settings"></a>İlke ayarları
iOS ve Android ilke ayarlarının tam listesini görmek için, aşağıdakilerden birini seçin:

> [!div class="op_single_selector"]
- [iOS ilkeleri](ios-app-protection-policy-settings.md)
- [Android ilkeleri](android-app-protection-policy-settings.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](monitor-app-protection-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Ayrıca bkz.
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-android-apps.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-ios-apps.md)

