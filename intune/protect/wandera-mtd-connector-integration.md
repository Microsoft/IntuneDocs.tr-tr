---
title: Intune ile Wandera Mobile Threat Protection tümleştirmesi ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Wandera mobil tehdit koruması çözümünü ayarlama.
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
ms.openlocfilehash: 64a560dc79d3c03f52b8e9389c3e47e3e256ee58
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306671"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Wandera Mobile Threat Protection 'ı Intune ile tümleştirme  

Wandera Mobile Threat Defense çözümünü Intune ile bütünleştirmek için aşağıdaki adımları izleyin.  

## <a name="before-you-begin"></a>Başlamadan önce  

Wandera 'yı Intune ile tümleştirme işlemine başlamadan önce, aşağıdaki önkoşulların yerine geldiğinden emin olun:
- Microsoft Intune aboneliği  
- Aşağıdaki izinleri vermek için yönetici kimlik bilgilerini Azure Active Directory:  
  - Oturum açın ve kullanıcı profilini okuyun  
  - Oturum açmış kullanıcı olarak dizine erişin  
  - Dizin verilerini okuma  
  - Cihaz bilgilerini Intune 'a gönderme  

- Wandera aboneliği:
  - EMM bağlantısı için lisanslı bir veya daha fazla Wandera hesabı  
  - Wandera 'da süper yönetici ayrıcalıklarına sahip bir hesap  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Wandera Mobile Threat Defense uygulama yetkilendirmesi  

Wandera Mobile Threat Defense uygulaması yetkilendirme işlemi:  
- Wandera Mobile Threat Defense hizmetinin cihaz sistem durumu ile ilgili bilgileri Intune 'a geri iletmesini sağlar.  
- Wandera, cihazının veritabanını doldurmak için Azure AD kayıt grubu üyeliğiyle eşitlenir.  
- Wandera RADAR yönetici portalının Azure AD çoklu oturum açma (SSO) kullanmasına izin verin.  
- Wandera Mobile Threat Defense uygulamasının Azure AD SSO 'yu kullanarak oturum açmasını sağlar.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Wandera Mobile Threat Defense tümleştirmesi ayarlama  
Wandera için *EMM Connect* kurulumu, hem Intune hem de wandera konsollarında tamamladığınız tek seferlik bir yapılandırma işlemi gerektirir. Yapılandırma işlemi yaklaşık 15 dakika sürer. Bu yapılandırmayı, Wandera teknik hesabınızla veya destek temsilcinizle koordine etmeden tamamlayabilirsiniz.  

### <a name="enable-support-for-wandera-in-intune"></a>Intune 'da Wandera desteğini etkinleştir
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz uyumluluğu** > **Mobil tehdit savunması** > gidin ve **Ekle**' yi seçin.

2. **Bağlayıcı Ekle** sayfasında, açılan menüyü kullanın ve **wandera**' yı seçin. Sonra **Oluştur**' u seçin.  

3. Mobil tehdit savunması bölmesinde bağlayıcı listesinden **Wandera** MTD bağlayıcısını seçerek *bağlayıcı düzenleme* bölmesini açın. [Radar](https://radar.wandera.com/login), wandera Yönetici Konsolu 'nu açmak ve oturum açmak Için **wandera yönetici konsolunu aç** ' ı seçin. 

4. Wandera konsolunda **ayarlar** > **EMM tümleştirmesi**' ne gidin ve **EMM Connect** sekmesini seçin. *EMM satıcı* açılan listesini kullanın ve *Microsoft Intune*' ı seçin.

   ![Intune seçin](./media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

5. Intune portalına bir bağlantı açmak için **Izin ver** ' i seçin. Intune yönetici kimlik bilgilerinizi kullanarak oturum açın, onay kutusunu seçin ve ardından izin isteğini **kabul edin** .  

   ![İzinleri kabul et](./media/wandera-mtd-connector-integration/permissions.png) 

6. Wandera bağlantıyı tamamlar ve sizi RADAR yönetim konsoluna döndürür. Gerektiğinde ek yapılandırmalara erişim **sağlamak** için işlemi tekrarlayın.  

   ![Tümleştirmeler ve izinler](./media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

7. RADAR konsolundan, **EMM etiketinin**altında görünen **synconly** grubunun adını kopyalayın. Bu adı, bir grubu Wandera ile eşitleme için Intune 'da yapılandırmak üzere kullanacaksınız.

   ![Eşitleme grubu](./media/wandera-mtd-connector-integration/sync-group-name.png) 

8. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) konsoluna dönün ve Wandera MTD bağlayıcısını düzenleyin. Kullanılabilir geçiş düğmelerini **Açık**olarak ayarlayın ve yapılandırmayı **kaydedin** .  

   ![Wandera 'yi etkinleştir](./media/wandera-mtd-connector-integration/enable-wandera.png) 

Intune ve Wandera artık bağlı.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Wandera uygulamalarını ve eşitleme grubunu yapılandırma  
Wandera 'yi dağıtmak için, kullandığınız platformlar (iOS ve Android) için Wandera mobil uygulamalarını Intune 'a ekleyecek ve eşitleme için belirli bir gruba atayacaksınız; *Synconly* grubu. 

Aşağıdaki bölümler ve yordamlar, bu süreç boyunca size yol gösterecektir.

Bu işlem hakkında Wandera ile ilgili daha fazla bilgi için, Wandera [radar](https://radar.wandera.com/login)' de oturum açın. **Ayarlar** > **EMM tümleştirmesi**' ne gidin, **uygulama gönderme** sekmesini seçin ve **Microsoft Intune**' ı seçin. Uygulama gönderme sekmesi, Intune 'a özgü yönergelerden güncellenir.  

### <a name="add-the-wandera-apps"></a>Wandera uygulamalarını ekleme  
Android ve iOS cihazlarına Wandera uygulamasını dağıtmak için Intune 'da istemci uygulamaları oluşturun. Yordamlar ve Wandera uygulamalarına özgü özel ayrıntılar için bkz. [MTD uygulamaları ekleme](mtd-apps-ios-app-configuration-policy-add-assign.md) .  

Uygulamaları oluşturduktan sonra eşitleme grubunu oluşturmak ve uygulamaları atamak için buraya dönün.  


### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Eşitleme grubunu oluşturma ve uygulamaları atama

1. Wandera RADAR konsolunun içinden **EMM etiketinin** altında görünen **synconly** grubunun adını alın. [Intune 'Da Wandera desteğini etkinleştirirken](#enable-support-for-wandera-in-intune)bu adı 7. adımda kaydetmiş olabilirsiniz. Bu adı, Intune 'da, Wandera eşitlemesi için grubun adı olarak kullanın.  

2. Intune konsolunda, **gruplar** ' a gidin ve **Yeni Grup**' u seçin. Eşitleme grubunu Wandera tarafından kullanılmak üzere yapılandırmak için aşağıdakileri belirtin:
   - **Grup türü**: **güvenlik**
   - **Grup adı**: Wandera radar Yönetici konsolundan aldığınız **synconly** adını belirtin.

   ![Eşitleme grubunu yapılandırma](./media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Tüm **Üyeler** ' i seçin ve Wandera ile kullanmak istediğiniz Android ve iOS cihazlarını içeren grupları atayın.

4. Grubu kaydetmek için **Oluştur** ' u seçin.

Daha fazla bilgi için bkz. [uygulamaları dağıtma](../apps/apps-deploy.md)

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Wandera uygulamalarını eşitleme grubuna atama  
İOS ve Android için oluşturduğunuz Wandera uygulaması için aşağıdaki yordamı tekrarlayın.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **istemci uygulamaları** > **uygulamalar** ' a gidin ve wandera uygulamasını seçin.  

2. **Atamalar** ' ı ve sonra **Grup Ekle**' yi seçin.  

3. *Grup Ekle* bölmesinde *atama türü* için **gerekli**' yi seçin.

4. **Dahil edilen gruplar**' ı seçin ve ardından **dahil edilecek grupları seçin**. Wandera eşitlemesi için oluşturduğunuz grubu belirtin ve ardından @no__t **seçin**-1**Tamam** > **Tamam**' a tıklayın. Grup atamasını gerçekleştirmek için **Kaydet** ' i seçin.  
 

## <a name="next-steps"></a>Sonraki Adımlar  
Tümleştirmeyi yapılandırdığınıza göre, ilkeleri yapılandırmaya, gelişmiş koşullu erişimi ayarlamaya başlayabilir ve Wandera yönetim konsolunda raporları görüntüleyebilirsiniz. Wandera 'yi yönetme ve yapılandırma hakkında daha fazla bilgi edinmek için, bkz. Wandera belgelerindeki [Destek Merkezi Başlarken Kılavuzu](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) .  
 