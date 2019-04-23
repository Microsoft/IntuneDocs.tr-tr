---
title: Microsoft Intune - Azure'da Windows 10 cihazları için şablonları kullanma | Microsoft Docs
description: Yönetim Şablonları Intune Windows 10 cihazları için ayarlar grupları oluşturmak için kullanın. Bu ayarları bir cihaz yapılandırma profilinde de Office programları denetlemek, Internet Explorer özelliklerini güvenli, OneDrive erişimi denetlemek, Uzak Masaüstü özelliklerini kullanmak, otomatik etkinleştirmek, güç yönetimi ayarlarını ayarlayın, HTTP yazdırma, farklı bir kullanıcı için kullanın oturum açma seçenekleri ve olay günlüğünün boyutunu denetimi.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 704abe5e03410b52d54c7729e1832e527ae4dfb6
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61504323"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Intune Grup İlkesi ayarlarını yapılandırmak için Windows 10 şablonları kullanma

Kuruluşunuzdaki cihazları yönetirken, farklı cihaz gruplarına uygulanan ayarları bir grup oluşturmak istiyorsunuz. Örneğin, birkaç cihaz gruplarına sahip. GroupA için ayarları belirli bir kümesini atamak istediğiniz. GroupB için ayarları farklı bir kümesini atamak istediğiniz. Yapılandırabileceğiniz ayarların basit bir görünümünü de istiyor.

Kullanarak bu görevi tamamlayabilirsiniz **Yönetim Şablonları** Microsoft Intune. Yönetim Şablonları yüzlerce Internet Explorer, Microsoft Office programları, Uzak Masaüstü özellikleri denetleyen ayar Ekle, Onedrive'a erişmek, resimli parola veya PIN oturum açmak için ve daha fazlasını kullanın. Bu şablonlar, Grup İlkesi (GPO) ayarlarını Active Directory (AD) benzer ve olan [ADMX destekli ayarları](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) (başka bir Docs sitesi açılır) XML kullanın. Ancak, Intune şablonlarında %100 bulut tabanlı. Daha fazla basit sundukları ve istediğiniz şekilde ayarları yapılandırın ve ayarları bulmak için modellemeniz.

**Yönetim Şablonları** Intune'da yerleşiktir ve OMA-URI kullanma dahil olmak üzere, tüm özelleştirmeler gerekmez. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu şablon ayarları, Windows 10 cihazlarınızı yönetmek için bir tek Mağazanız kullanın.

Bu makalede, Windows 10 cihazları için bir şablon oluşturma adımları listelenir ve filtre Intune tüm kullanılabilir ayarları gösterilmektedir. Şablonu oluşturduğunuzda, bir cihaz yapılandırma profili oluşturur. Atayın veya bu profili, kuruluşunuzdaki Windows 10 cihazlarına dağıtabilirsiniz.

## <a name="create-a-template"></a>Bir şablon oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Profil için bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Seçin **Windows 10 ve üzeri**.
    - **Profil türü**: Seçin **Yönetimsel Şablonlar (Önizleme)**.

4. **Oluştur**’u seçin. Yeni pencerede seçin **ayarları**. Her ayar listelenir ve kullanabileceğiniz önce ve sonra diğer ayarları görmek için okları:

    ![Ayarları örnek listesini görmek ve önceki ve sonraki düğmelerini kullanın](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Herhangi bir ayar seçin. Örneğin, **izin Dosya indirmeleri**. Ayar ayrıntılı bir açıklaması gösterilir. Tercih **etkinleştirme**, **devre dışı**, veya ayarı olarak bırakın **yapılandırılmadı** (varsayılan). Ayrıntılı bir açıklaması, ayrıca seçtiğinizde neler olacağını açıklayan **etkinleştirme**, **devre dışı**, veya **yapılandırılmadı**.
6. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

Devam ayarlarının listesini sırasıyla izleyin ve ortamınızda istediğiniz ayarları yapılandırın. Bazı örnekler şunlardır:

- Kullanım **VBA makrosu bildirim ayarları** VBA makroları Word ve Excel gibi farklı Microsoft Office programlarında işlemek için ayarı.
- Kullanım **izin Dosya indirmeleri** izin vermek veya önlemek için ayarı Internet Explorer'dan indirir.
- Kullanım **(prize takılı) bir bilgisayar uyku modundan çıkar zaman parola iste** ayarı cihazları uyku modundan çıkarılırken bir parola için kullanıcılara sor.
- Kullanım **indirme işaretsiz ActiveX denetimlerini** yüklenmesini ayarı kullanıcıları engellemek işaretsiz Internet Explorer'dan ActiveX denetimleri.
- Kullanım **Sistem Geri Yükleme'yi** izin vermek veya kullanıcıların cihazda sistem geri yükleme çalıştırmasını engellemek için ayarı.
- Ve çok daha fazlası...

## <a name="find-some-settings"></a>Bazı ayarları bulunamıyor

Bu şablonları yüzlerce ayar vardır. Belirli ayarları bulmayı kolaylaştırmak için yerleşik özelliklerini kullanabilirsiniz:

- Şablonunuzda seçin **ayarları**, **durumu**, veya **yolu** Listeyi sıralamak için sütun. Örneğin, **yolu** , tüm ayarlarını görmek için sütun `Microsoft Excel` yolu:

  ![Yol alfabetik olarak sıralamak için tıklayın](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- Şablonunuz, kullanmak **arama** kutusu belirli ayarları bulunamıyor. Örneğin, arama `copy`. Tüm ayarlarla `copy` gösterilir:

  ![Yol alfabetik olarak sıralamak için tıklayın](./media/administrative-templates-windows/search-copy-settings.png)

  Başka bir örnekte, arama `microsoft word`. Microsoft Word program için ayarladığınız tüm ayarları görürsünüz. Arama `explorer` tüm Internet Explorer ayarlarını görmek için şablonunuza ekleyebilirsiniz.

Bu özelliği kullanan [CSP'ler Windows İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (başka bir Docs sitesi açılır). CSP'ler Windows, Home, Professional, Enterprise vb. gibi farklı sürümleri üzerinde çalışır. Bir CSP belirli bir sürümü üzerinde çalışıp çalışmadığını görmek için Git [CSP'ler Windows İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (başka bir Docs sitesi açılır).

## <a name="next-steps"></a>Sonraki adımlar

Şablon oluşturulur, ancak hiçbir şey henüz yapmakta olduğu değil. Ardından, [şablonun bir profili de denir, Ata](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).
