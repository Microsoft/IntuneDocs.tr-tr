---
title: "Microsoft Intune için rol tabanlı erişim denetimi (RBAC) | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: RBAC’nin, işlem gerçekleştirebilecek ve değişiklik yapabilecek kişileri denetlemenize nasıl yardımcı olduğunu öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: db0f88db8eee33781ccf3ef54e34089a25118726


---

# <a name="role-based-access-control-rbac-for-microsoft-intune"></a>Microsoft Intune için rol tabanlı erişim denetimi (RBAC)

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Basitçe açıklamak gerekirse, Intune **rolleri** (veya RBAC) çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin kimlere uygulanacağını denetlemenize yardımcı olur. Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.

Bir rol, şunlarla tanımlanır:

- **Tanım** - Rolün adı ve yapılandırdığı izinler.
- **Üyeler** - Bu izinlerin verileceği kullanıcı veya kullanıcılar grubu.
- **Kapsam** - Belirtilen kişinin (üye) yönetebileceği kullanıcılar veya cihazlar.
- **Atama** - Tanım, üyeler ve kapsam yapılandırıldığında, rol atanır.

## <a name="built-in-roles"></a>Yerleşik roller

Aşağıdaki roller Intune’da yerleşik olarak sağlanır ve bu rolleri özelleştirebilir veya başka yapılandırma yapmadan gruplara atayabilirsiniz.

- **Intune Yöneticisi** - Tüm Intune işlemleri üzerinde tüm izinlere sahiptir.
- **Uygulama Yöneticisi** - Uygulamaları ve profilleri yönetin ve dağıtın.
- **Yapılandırma İlkesi Yöneticisi** - Yapılandırma ayarlarını ve profilleri yönetin ve dağıtın.
- **Yardım Masası İşletmeni** - Uzak görevleri gerçekleştirin, kullanıcı ve cihaz bilgilerini görüntüleyin.
- **Salt Okunur İşletmeni** - Değişiklik yapma becerisi olmadan Intune portalındaki bilgileri görüntüleyin.


## <a name="custom-roles"></a>Özel roller

Yerleşik rollerden hiçbiri gereksinimlerinize uygun değilse, Intune’un birçok özelliğini kapsayan ayarlar seçerek kendi rolünüzü oluşturabilirsiniz. Bu konunun devamında kullanılabilir ayarların listesine bakabilirsiniz.

### <a name="example"></a>Örnek

Londra ofisinizdeki kullanıcılara uygulamaları dağıtmaktan ve bunları yönetmekten sorumlu olacak yeni bir BT yöneticisi işe aldınız. Kullanıcılar, **Londra** adlı bir Azure AD grubunda yer alıyorlar. BT yöneticisinin başka herhangi bir ofisteki kullanıcılara uygulama dağıtamamasını istiyorsunuz. Aşağıdaki eylemleri gerçekleştirirsiniz:

- Aşağıdaki özelliklerle, yerleşik **Uygulama Yöneticisi** rolünü atarsınız:
    - **Üyeler** - Uygulamaları dağıtacak olan BT yöneticisinin içinde bulunduğu grubu seçin
    - **Kapsam** - **Londra** Azure AD grubunu seçin.

    >[!IMPORTANT]
    >Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
    >- **Genel AAD Yöneticisi**
    >- **Intune Hizmet Yöneticisi**

### <a name="how-to-create-a-custom-role"></a>Özel rol oluşturma

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Erişim denetimi**’ni seçin.
![Erişim denetimi iş yükü](./media/axxess-control.png)
1. **Erişim denetimi** iş yükünün **Roller** dikey penceresinde **Özel ekle**’yi seçin.
2. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, sonra da **İzinler**’e tıklayın.
3. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin. Yardımcı olması için bu konunun devamındaki özel rol ayarları başvuru listesini kullanın.
4. Bitirdiğinizde, **Tamam**’a tıklayın.
5. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın.

Yeni rol, **Roller** dikey penceresindeki listede görüntülenir.

## <a name="how-to-assign-a-role"></a>Rol atama

1. **Erişim denetimi** iş yükünün **Roller** dikey penceresinde, atamak istediğiniz yerleşik veya özel rolü seçin.
2. <*Rol adı*> - **Özellikler** dikey penceresinde **Yönet** > **Atamalar**’ı seçin.
    >[!TIP]
    >Ayrıca bu dikey pencerede var olan rolleri düzenleyebilir veya silebilirsiniz.
3. Sonraki dikey pencerede **Ata**’yı seçin.
4. **Rol Atamaları** dikey penceresinde, atama için **Ad** ve isteğe bağlı olarak **Açıklama** girin, sonra da aşağıdakileri seçin:
    - **Üyeler** - İzinleri vermek istediğiniz kullanıcıyı içeren grubu seçin.
    - **Kapsam** - Yukarıda seçilen üyenin yönetmesine izin verilecek kullanıcıları içeren grubu seçin.
5. Bitirdiğinizde, **Tamam**’a tıklayın.

Yeni atama, atamalar listesinde görüntülenir.

## <a name="custom-role-settings-reference"></a>Özel rol ayarları başvurusu

Özel rol oluşturduğunuzda, aşağıdaki ayarlardan birini veya birden çoğunu yapılandırabilirsiniz:

### <a name="device-configurations"></a>Cihaz yapılandırmaları

|||
|-|-|
|**Ata**|Cihaz profillerini gruplara atayın.|
|**Oluştur**|Cihaz profillerini oluşturun.|
|**Sil**|Cihaz profillerini silin.|
|**Okuma**|Cihaz profillerini ve onların özelliklerini okuyun.|
|**Güncelleştir**|Var olan cihaz profillerini güncelleştirin.|

### <a name="managed-apps"></a>Yönetilen uygulamalar

|||
|-|-|
|**Ata**|Yönetilen uygulamaları gruplara atayın.|
|**Oluştur**|Intune’a yeni yönetilen uygulamalar ekleyin.|
|**Sil**|Yönetilen uygulamaları silin.|
|**Okuma**|Yönetilen uygulamaları ve onların özelliklerini okuyun.|
|**Güncelleştir**|Var olan yönetilen uygulamaları güncelleştirin.|
|**Silme**|Cihazlardan yönetilen uygulamaları temizleyin.|

### <a name="managed-devices"></a>Yönetilen cihazlar

|||
|-|-|
|**Sil**|Yönetilen cihazları Intune’dan silin.|
|**Okuma**|Intune portalında yönetilen cihazlar hakkındaki bilgileri görüntüleyin.|
|**Güncelleştir**|Yönetilen cihazlar hakkındaki bilgileri güncelleştirin.|

### <a name="mobile-apps"></a>Mobil uygulamalar

|||
|-|-|
|**Ata**|Mobil uygulamaları gruplara atayın.|
|**Oluştur**|Intune’a yeni mobil uygulamalar ekleyin.|
|**Sil**|Mobil uygulamaları silin.|
|**Okuma**|Mobil uygulamaları ve onların özelliklerini okuyun.|
|**Güncelleştir**|Var olan mobil uygulamaları güncelleştirin.|

### <a name="organization"></a>Kuruluş

|||
|-|-|
|**Okuma**|Kiracı ayarlarını okuyun.|
|**Güncelleştir**|Kiracı ayarlarını güncelleştirin.|

### <a name="remote-tasks"></a>Uzak görevler

|||
|-|-|
|**Etkinleştirme Kilidini Atla**|Kullanıcının Apple kimliği ve parolası olmadan iOS cihazının etkinleştirme kilidini kaldırın. |
|**Kayıp Modunu Devre Dışı Bırak**|Kayıp Modu’nu devre dışı bırakın. Kayıp modu, cihazın kilit ekranında görüntülenecek mesajı ve telefon numarasını belirtmenize olanak tanır.|
|**Kayıp Modunu Etkinleştir**|Kayıp Modu’nu etkinleştirin. Kayıp modu, cihazın kilit ekranında görüntülenecek mesajı ve telefon numarasını belirtmenize olanak tanır.|
|**Cihazı Bul**|-|
|**Şimdi Yeniden Başlat**|Cihazın yeniden başlatılmasına neden olur.|
|**Uzaktan Kilitleme**|Cihazı kilitler. Cihaz sahibinin kilidi açmak için geçiş kodunu kullanması gerekir.|
|**Geçiş Kodunu Sıfırla**|Cihaz için <device name> Genel Bakış dikey penceresinde görüntülenecek yeni geçiş kodunu oluşturur.|
|**Devre Dışı Bırak**|Yalnızca Intune tarafından yönetilen şirket verilerini kaldırır. Cihazdan kişisel verileri kaldırmaz.|
|**Silme**|Cihazı varsayılan ayarlarına döndürür.|



### <a name="telecom-expenses"></a>Telekom giderleri

|||
|-|-|
|**Okuma**|Telekom Gider Yönetimi (TEM) ayarlarını okuyun.|
|**Güncelleştir**|Telekom Gider Yönetimi (TEM) ayarlarını güncelleştirin.|

### <a name="terms-and-conditions"></a>hüküm ve koşullar

|||
|-|-|
|**Ata**|Hüküm ve koşulları gruplara atayın.|
|**Oluştur**|Hüküm ve koşullar ayarlarını oluşturun.|
|**Sil**|Hüküm ve koşullar ayarlarını silin.|
|**Okuma**|Intune portalında hüküm ve koşullar ayarlarını okuyun.|
|**Güncelleştir**|Mevcut hüküm ve koşullar ayarlarını güncelleştirin.|


<!--HONumber=Feb17_HO1-->


