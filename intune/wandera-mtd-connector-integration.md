---
title: Intune ile Mobile Threat Protection Wandera tümleştirmesini ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek Intune Wandera mobil tehdit koruma çözümüyle ayarlama yapma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76d5ca2d1f1c23a5d5aef4af3904fc8d9c76e947
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407726"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Wandera mobil tehdit koruması ile Intune tümleştirmesi  

Wandera Mobile Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.  

## <a name="before-you-begin"></a>Başlamadan önce  

Wandera Intune ile tümleştirme sürecini başlatmadan önce aşağıdaki önkoşulların sağlandığından emin olun:
- Microsoft Intune aboneliği  
- Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:  
  - Oturum açma ve kullanıcı profilini okuma  
  - Oturum açmış kullanıcı olarak dizine erişim  
  - Dizin verilerini okuma  
  - Intune’a cihaz bilgilerini gönderme  

- Wandera aboneliği:
  - EMM bağlanmak için lisanslı bir veya daha fazla Wandera hesapları  
  - Wandera içinde Süper yönetici ayrıcalıkları olan bir hesabı  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Mobile Threat Defense Wandera uygulama yetkilendirme  

Mobile Threat Defense Wandera uygulama Yetkilendirme işlemi:  
- Wandera mobil tehdit savunması hizmetine ıntune'a cihazın sistem durumuyla ilgili bilgi iletme izni verin.  
- Cihazının veritabanını doldurmak için Azure AD kayıt grubu üyeliğiyle eşitlenmesi Wandera.  
- Wandera RADAR yönetici portalının Azure AD çoklu oturum açma (SSO) kullanmasına izin verin.  
- Azure AD SSO kullanarak oturum açmanız Wandera Mobile Threat Defense uygulamasını sağlar.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Mobile Threat Defense Wandera tümleştirmesini ayarlama  
Kurulum, *EMM bağlanma* hem Intune hem de Wandera konsollarında tamamlamanız için tek seferlik yapılandırma işlemi Wandera gerekir. Yapılandırma işlemini yaklaşık 15 dakika sürer. Wandera teknik hesabınızla koordinasyon olmadan yapılandırmasını tamamlamak veya destek temsilcinize.  

### <a name="enable-support-for-wandera-in-intune"></a>Intune'da Wandera desteğini etkinleştirme
1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) gidin **cihaz uyumluluğu** > **Mobile Threat Defense** > seçip **Ekle**.

2. Üzerinde **ekleme bağlayıcı** sayfasında, açılan listeyi kullanın ve seçin **Wandera**. Ve ardından **Oluştur**.  

3. Mobile Threat Defense bölmeden **Wandera** açmak için bağlayıcı listeden MTD bağlayıcısını *bağlayıcısını Düzenle* bölmesi. Seçin **Wandera yönetici konsolunu Aç** açmak için [RADAR](https://radar.wandera.com/login), Wandera Yönetici Konsolu ve oturum açın. 

4. Wandera konsolunda Git **ayarları** > **EMM tümleştirme**seçip **EMM bağlanma** sekmesi. Kullanım *EMM satıcı* açılır ve select *Intune*.

   ![Intune seçin](media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

5. Seçin **izinleri verin** Intune portalına bir bağlantı açmak için. Intune yönetici kimlik bilgilerinizi kullanarak oturum açın, onay kutusunu işaretleyin ve ardından **kabul** izinlere ilişkin istek.  

   ![İzinleri kabul etmiş olursunuz](media/wandera-mtd-connector-integration/permissions.png) 

6. Wandera bağlantı tamamlandıktan ve RADAR yönetim konsoluna döndürür. Bu işlemi yinelemeniz **Grant** gerektiğinde ek yapılandırmaları için erişim.  

   ![Tümleştirmeler ve izinleri](media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

7. RADAR konsolunda, adını kopyalayın **SyncOnly** aşağıda görüntülenen grubu **EMM etiket**. Bir grup eşitleme Wandera ile Intune yapılandırma için bu adı kullanacaksınız.

   ![Tümleştirmeler ve izinleri](media/wandera-mtd-connector-integration/sync-group-name.png) 

8. Geri dönüp [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) konsol ve Wandera MTD Bağlayıcısı'nı düzenleyin. Kullanılabilir değiştirme düğmelerini kümesine **üzerinde**ve **Kaydet** yapılandırma.  

   ![Wandera etkinleştir](media/wandera-mtd-connector-integration/enable-wandera.png) 

Intune ve Wandera artık bağlanır.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Eşitleme grubu ve Wandera uygulamaları yapılandırma  
Wandera dağıtmak için Wandera mobil uygulamalar ekleyeceksiniz platformlar için (iOS ve Android) için Intune kullanın ve bunları belirli bir grup eşitleme için; atama *SyncOnly* grubu. 

Aşağıdaki bölümler ve yordamlardan size bu süreçte yol gösterir.

Bu işlemden Wandera hakkında daha fazla bilgi için Wandera için oturum [RADAR](https://radar.wandera.com/login). Git **ayarları** > **EMM tümleştirme**seçin **gönderme** sekmesine tıklayın ve ardından **Intune**. Intune'a özgü yönergeleri uygulama iletimi sekmesini güncelleştirmeleriyle.  

### <a name="add-the-wandera-apps"></a>Wandera uygulama ekleme  
İstemci Wandera uygulamasını Android ve iOS cihazlarına dağıtmak için ıntune'a uygulamalar oluşturun. Bkz: [ekleme MTD uygulamaları](mtd-apps-ios-app-configuration-policy-add-assign.md) Wandera uygulamalarınıza özgü özel ayrıntıları ve yordamları için.  

Uygulamaları oluşturduktan sonra eşitleme grubu oluşturma ve uygulamaları atamak için buraya dönün.  


### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Eşitleme grubu oluşturma ve uygulamaları atama

1. Adını alın **SyncOnly** aşağıda görüntülenen grubu **EMM etiket** içinde Wandera RADAR konsolunu. Bu ad 7. adım sırasında sırasında kaydedilmiş [Wandera ıntune desteği etkinleştirme](#enable-support-for-wandera-in-intune). Bu ad Wandera eşitleme için ıntune'da grup adını kullanın.  

2. Intune konsolunda Git **grupları** seçip **yeni grup**. Eşitleme grubu Wandera tarafından kullanılmak üzere yapılandırmak için aşağıdakileri belirtin:
   - **Grup türü**: **Güvenlik**
   - **Grup adı**: Belirtin **SyncOnly** Wandera RADAR yönetici konsolundan aldığınız adı.

   ![Eşitleme grubunu yapılandırma](media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Seçin **üyeleri** ve Wandera ile kullanmak istediğiniz Android ve iOS aygıtları içeren grupları atayabilirsiniz.

4. Seçin **Oluştur** grubunu kaydetmek için.

Daha fazla bilgi için [uygulamaları dağıtma](apps-deploy.md)

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Eşitleme grubuna Wandera uygulamaları atama  
İOS ve Android için oluşturduğunuz Wandera uygulaması için aşağıdaki yordamı yineleyin.

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) gidin **istemci uygulamaları** > **uygulamaları** ve Wandera uygulamayı seçin.  

2. Seçin **atamaları** ardından **Grup Ekle**.  

3. Üzerinde *Grup Ekle* bölmesinde için *atama türü* seçin **gerekli**.

4. Seçin **eklenen gruplar**, ardından **dahil edilecek grupları seçin**. Wandera eşitleme için oluşturduğunuz grubu belirtin ve ardından **seçin** > **Tamam** > **Tamam**. Seçin **Kaydet** Grup atamasını tamamlamak için.  
 

## <a name="next-steps"></a>Sonraki Adımlar  
Tümleştirmeyi yapılandırdıktan sonra ilkeleri yapılandırmaya başlamak, Gelişmiş koşullu erişimi ayarlama ve Wandera yönetici konsolundan raporlarını görüntüleyin. Daha fazla yönetme ve Wandera yapılandırması hakkında bilgi edinmek için [Destek Merkezi Başlarken Kılavuzu](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) Wandera belgelerinde.  
 