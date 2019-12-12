---
title: Microsoft Intune-Azure 'da Windows 10 cihazları için şablonları kullanma | Microsoft Docs
description: Windows 10 cihazları için ayar grupları oluşturmak üzere Microsoft Intune içindeki Yönetim şablonlarını kullanın. Office programlarını, Microsoft Edge 'i, Internet Explorer 'daki güvenli özellikleri denetlemek, OneDrive 'a erişimi denetlemek, uzak masaüstü özelliklerini kullanmak, otomatik yürütmeye olanak tanımak, uzaktan yürütmeye izin vermek, güç yönetimi ayarlarını yapmak, HTTP yazdırmayı kullanmak için bir cihaz yapılandırma profilinde Bu ayarları kullanın. farklı Kullanıcı oturum açma seçenekleri kullanın ve olay günlüğü boyutunu denetleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca087ec67542102a0cd3111d27a860500b23d3c4
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74547983"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Microsoft Intune 'de Grup İlkesi ayarlarını yapılandırmak için Windows 10 şablonlarını kullanın

Kuruluşunuzdaki cihazları yönetirken, farklı cihaz gruplarına uygulanan ayar grupları oluşturmak istersiniz. Örneğin, birkaç cihaz grubunuz vardır. GroupA için belirli bir ayar kümesi atamak istersiniz. GroupB için farklı bir ayar kümesi atamak istersiniz. Ayrıca yapılandırabileceğiniz ayarların basit bir görünümünü de istiyorsunuz.

Bu görevi, Microsoft Intune **Yönetim Şablonları** kullanarak tamamlayabilirsiniz. Yönetim Şablonları, Microsoft Edge sürüm 77 ve üzeri, Internet Explorer, Microsoft Office programlar, Uzak Masaüstü, OneDrive, parolalar ve PIN 'Ler gibi özellikleri denetleyen yüzlerce ayarı içerir. Bu ayarlar, grup yöneticilerinin bulutu kullanarak grup ilkelerini yönetmesine olanak tanır.

Windows ayarları Active Directory (AD) içindeki Grup İlkesi (GPO) ayarlarına benzerdir. Bu ayarlar Windows 'da yerleşiktir ve XML kullanan [ADMX ile desteklenen ayarlardır](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) . Office ve Microsoft Edge ayarları, ADMX kullanımına alınır ve [Office Yönetim şablonu dosyaları](https://www.microsoft.com/download/details.aspx?id=49030) ve [Microsoft Edge YÖNETIM şablonu dosyalarında](https://www.microsoftedgeinsider.com/enterprise)ADMX ayarlarını kullanır. Ancak, Intune şablonları %100 bulut tabanlıdır. Ayarları yapılandırmak için basit ve düz ileri bir yol sunar ve istediğiniz ayarları bulur.

**Yönetim Şablonları** , Intune 'da yerleşik olarak bulunur ve OMA-URI kullanımı dahil olmak üzere herhangi bir özelleştirme gerektirmez. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, Windows 10 cihazlarınızı yönetmek için bu şablon ayarlarını tek durdurulmalı bir mağaza olarak kullanın.

Bu makalede, Windows 10 cihazları için şablon oluşturma adımları listelenir ve Intune 'da kullanılabilen tüm ayarların nasıl filtreleneceği gösterilir. Şablonu oluşturduğunuzda, bir cihaz yapılandırma profili oluşturur. Daha sonra bu profili, kuruluşunuzdaki Windows 10 cihazlarına atayabilir veya dağıtabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

- Bu ayarlardan bazıları Windows 10 sürüm 1703 (RS2) ile başlayarak kullanılabilir. Bazı ayarlar tüm Windows sürümlerinde bulunmaz. En iyi deneyim için, Windows 10 Enterprise sürüm 1903 (19H1) ve daha yeni bir sürümü kullanmanız önerilir.

- Windows ayarları [Windows Ilkesi CSP 'leri](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies)kullanır. CSP 'Ler Home, Professional, Enterprise vb. gibi farklı Windows sürümlerinde çalışır. CSP 'nin belirli bir sürümde çalışıp çalışmadığını görmek için [Windows Ilke CSP 'leri](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies)' ne gidin.

## <a name="create-a-template"></a>Bir şablon oluşturun

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: profil için bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **Yönetim Şablonları**seçin.

4. **Oluştur**’u seçin. Yeni pencerede **Ayarlar**' ı seçin. Her ayar listelenir ve daha fazla ayarı görmek için önceki ve sonraki okları kullanabilirsiniz:

    ![Ayarların örnek listesini görüntüleyin ve önceki ve sonraki düğmeleri kullanın](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > Intune 'daki Windows ayarları Yerel Grup İlkesi Düzenleyicisi (`gpedit`) ' de gördüğünüz şirket içi Grup İlkesi yoluyla ilişkilendirilebilir.

5. Açılan listede, **Tüm ürünler**' i seçin. Ayrıca, ayarları yalnızca **Windows** ayarlarını göstermek, yalnızca **Office** ayarlarını göstermek veya yalnızca **Edge sürüm 77 veya üzeri** ayarları göstermek için filtreleyebilirsiniz:

    ![Intune 'da yönetim şablonlarındaki tüm pencereleri veya tüm Office ayarlarını göstermek için listeyi filtreleyin](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > Microsoft Edge ayarları için geçerlidir:
    >
    > - Microsoft Edge sürüm 77 ve üzeri. Microsoft Edge sürüm 45 ve önceki sürümlerini yapılandırmak için bkz. [Microsoft Edge tarayıcı cihaz kısıtlama ayarları](device-restrictions-windows-10.md#microsoft-edge-browser).
    > - [KB 4512509](https://support.microsoft.com/kb/4512509) yüklü WINDOWS 10 RS4 ve üzeri
    > - [KB 4512534](https://support.microsoft.com/kb/4512534) yüklü WINDOWS 10 RS5 ve üzeri
    > - [KB 4512941](https://support.microsoft.com/kb/4512941) yüklü Windows 10 19H1 ve üzeri

6. Herhangi bir ayarı seçin. Örneğin, **Office**üzerinde filtreleme yapın ve **Kısıtlanmış taramayı etkinleştir**' i seçin. Ayarın ayrıntılı bir açıklaması gösterilir. **Etkin**, **devre dışı**seçeneğini belirleyin veya ayarı **Yapılandırılmadı** (varsayılan) olarak bırakın. Ayrıntılı açıklama Ayrıca **etkin**, **devre dışı**veya **yapılandırılmamış**' ı seçtiğinizde ne olacağını açıklar.
7. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

Ayarlar listesinden ilerleyin ve ortamınızda istediğiniz ayarları yapılandırın. Bazı örnekler şunlardır:

- Word ve Excel dahil farklı Microsoft Office programlarındaki VBA makrolarını işlemek için **VBA makro bildirimi ayarları** ayarını kullanın.
- Internet Explorer 'dan İndirmeleri izin vermek veya engellemek için **Dosya Indirmelerine Izin ver** ayarını kullanın.
- Cihazlar uyku modundan çıktığında kullanıcılara parola istemek için bir **bilgisayar uyandığında (prize takılıyken) parola gerektir '** i kullanın.
- Kullanıcıların Internet Explorer 'dan imzasız ActiveX denetimlerini indirmesini engellemek için **Imzasız ActiveX denetimlerini indir** ayarını kullanın.
- Kullanıcıların cihazda sistem geri yükleme çalıştırmasını sağlamak veya bunu engellemek için **sistemi geri yüklemeyi** kapat ayarını kullanın.
- Kullanıcıların başka bir tarayıcıdan Microsoft Edge 'e sık kullanılanları içeri aktarmaya izin vermek veya bunları engellemek için **sık kullanılanları içeri aktarmaya Izin ver** ayarını kullanın.
- Ve çok daha fazlası...

## <a name="find-some-settings"></a>Bazı ayarları bul

Bu şablonlarda yüzlerce ayar bulunur. Belirli ayarları bulmayı kolaylaştırmak için yerleşik özellikleri kullanın:

- Şablonunuzda, listeyi sıralamak için **Ayarlar**, **durum**, **ayar türü**veya **yol** sütunlarını seçin. Örneğin, `Microsoft Excel` yolundaki tüm ayarları görmek için **yol** sütununu seçin:

  ![Intune 'daki yönetim şablonlarında Grup İlkesi veya ADMX yolu tarafından gruplanmış tüm ayarları göstermek için yol ' a tıklayın](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- Şablonunuzda, belirli ayarları bulmak için **arama** kutusunu kullanın. Başlık veya yol ayarlayarak arama yapabilirsiniz. Örneğin, `copy`araması yapın. `copy` olan tüm ayarlar gösterilir:

  ![Intune 'da yönetim şablonlarındaki tüm Windows ve Office ayarlarını göstermek için Kopyala araması yapın](./media/administrative-templates-windows/search-copy-settings.png) 

  Başka bir örnekte, `microsoft word`için arama yapın. Microsoft Word programı için ayarlayabileceğiniz tüm ayarları görürsünüz. Şablonunuza ekleyebileceğiniz tüm Internet Explorer ayarlarını görmek için `explorer` aratın.

## <a name="next-steps"></a>Sonraki adımlar

Şablon oluşturuldu, ancak henüz bir şey yapmadım. Sonra, [profil olarak da adlandırılan şablonu atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Yönetim şablonlarını kullanarak Office 365](administrative-templates-update-office.md)' i güncelleştirin.
