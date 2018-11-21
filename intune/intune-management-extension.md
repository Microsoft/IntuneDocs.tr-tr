---
title: Windows 10 cihazları için Microsoft Intune’da PowerShell betiklerini ekleme - Azure | Microsoft Docs
description: PowerShell betiklerini ekleyin, Azure Active Directory gruplarına betik ilkesi atayın, betikleri izlemek için raporları kullanın ve Microsoft Intune'da Windows 10 cihazlarına eklediğiniz betikleri silme adımlarını görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 29a3f6c6e320f970ef7b2b086b8d25ab82453199
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179414"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme
Intune yönetim uzantısı, Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için karşıya yüklemenize olanak sağlar. Yönetim uzantısı Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmayı kolaylaştırır.

## <a name="moving-to-modern-management"></a>Modern yönetime geçiş
Son kullanıcı işlemi dijital bir dönüşüm geçiriyor. Klasik, geleneksel BT tek bir cihaz platformu, şirkete ait cihazlar, ofisten çalışan kullanıcılar ve elle gerçekleştirilen çeşitli geriye dönük BT süreçlerine odaklanır. Ancak yeni çalışma alanı hem kullanıcıya hem de şirkete ait çoklu cihaz platformlarını kullanmaya olanak sağlar, kullanıcıların her yerden çalışmalarına olanak sağlar ve otomatik ve öngörülü BT süreçleri sunar. 

Microsoft Intune gibi MDM hizmetleri MDM protokolünü kullanarak Windows 10 cihazlarını yönetebilir. Yerleşik Windows 10 yönetim istemcisi kurumsal yönetim görevlerini gerçekleştirmek için Intune’la iletişim kurabilir. Windows 10 cihazlarda modern yönetime geçiş yapmanıza yardımcı olur. Ancak, Windows 10 yerleşik MDM özelliklerinde kullanılamayan Gelişmiş cihaz yapılandırma gibi gerekebilecek bazı özellikleri vardır.

Intune yönetim uzantısı yerleşik Windows 10 MDM özelliklerini tamamlar. İhtiyacınız olan özellikleri sağlayan Windows 10 cihazlarda çalışan PowerShell betikleri oluşturabilirsiniz. Özel ayarları yapılandıran bir PowerShell betiği oluşturmak, betiği Intune'a yükleyebilir, betiği bir Azure Active Directory (AD) grubuna atayın ve Windows 10 cihazlarda betiği çalıştırın. Betik, başlangıçtan bitişe kadar Windows 10 cihazlarında betik çalıştırma durumunu görmek için izlenebilir.

## <a name="prerequisites"></a>Önkoşullar
Intune yönetim uzantısı şu önkoşullara sahiptir:
- Cihazların Azure AD’ye katılmış olması gerekir. Intune yönetim uzantısı Azure Active Directory’ye ve Karma Etki Alanına katılmış Windows cihazlar ile Ortak Yönetilen kayıtlı Windows cihazları destekler.
- Cihazlar Windows 10, sürüm 1607 veya üzerini çalıştırmalıdır.
- Otomatik MDM kaydı [Azure AD'de etkinleştirilmeli](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment) ve cihazlar Intune'a otomatik olarak kaydedilmelidir.

## <a name="create-a-powershell-script-policy"></a>PowerShell betik ilkesi oluşturma 
1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **PowerShell betikleri** > **Ekle**'yi seçin.
4. PowerShell betiği için **Ad** ve **Açıklama** girin. **Betik konumu** için, PowerShell betiğine göz atın. Betiğin boyutu 200 KB'tan (ASCII) veya 100 KB'tan (Unicode) küçük olmalıdır.
5. **Yapılandır**’ı seçin. Ardından betiği cihazda (**Evet**) veya sistem bağlamında (**Hayır**) kullanıcının kimlik bilgileriyle çalıştırmayı seçin. Varsayılan olarak, betik sistem bağlamında çalıştırılır. Betiğin sistem bağlamında çalıştırılması gerekli değilse **Evet**’i seçin. 
  ![PowerShell betiği ekleme bölmesi](./media/mgmt-extension-add-script.png)
6. Betiğin güvenilir bir yayımcı tarafından imzalanmış olup olmaması gerektiğini seçin (**Evet**). Varsayılan olarak, betiğin imzalanmasına yönelik bir gereksinim yoktur. 
7. **Tamam**’ı ve ardından **Oluştur**’u seçerek betiği kaydedin.

## <a name="assign-a-powershell-script-policy"></a>PowerShell betik ilkesi atama
1. **PowerShell betikleri**'nde, atanacak betiği seçin ve daha sonra **Yönet** > **Atamalar**’ı seçin.
  ![PowerShell betiği ekleme bölmesi](./media/mgmt-extension-assignments.png)
 
2. Kullanılabilir Azure AD gruplarını listelemek için **Grupları Seç**’i seçin. 
3. Cihazları betiği alan kullanıcıların yer aldığı bir veya birden çok grubu seçin. İlkeyi seçili gruplara atamak için **seçin**.

> [!NOTE]
> - Son kullanıcıların PowerShell betiklerini yürütmek için cihazda oturum açmış olmaları gerekmez. 
> - Intune’da PowerShell betikleri AAD cihaz güvenlik gruplarına hedeflenebilir.

Intune yönetim uzantısı saatte bir kez Intune ile eşitlenir. İlkeyi Azure AD gruplarına atadıktan sonra, PowerShell betiği çalıştırılır ve çalıştırma sonuçları raporlanır. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>PowerShell betikleri için çalıştırma durumunu izleme
Azure portalda kullanıcılar ve cihazlar için PowerShell betiklerinin çalıştırma durumunu izleyebilirsiniz.

**PowerShell betikleri**'nde izlenecek betiği seçin, **İzle**’yi ve ardından şu raporlardan birini seçin:
   - **Cihaz durumu**
   - **Kullanıcı durumu**

## <a name="delete-a-powershell-script"></a>PowerShell betiğini silme
**PowerShell betikleri**'nde, betiği sağ tıklayın ve **Sil**'i seçin.
