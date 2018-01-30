---
title: "Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme"
titlesuffix: Azure portal
description: "Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için nasıl karşıya yükleyeceğinizi öğrenin."
keywords: 
author: dougeby
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8c959ca3df62cbda17e5a659d0703cbc37f3249
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme
Intune yönetim uzantısı, Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için karşıya yüklemenize olanak sağlar. Yönetim uzantısı Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmayı kolaylaştırır.

## <a name="moving-to-modern-management"></a>Modern yönetime geçiş
Son kullanıcı işlemi dijital bir dönüşüm geçiriyor. Klasik, geleneksel BT tek bir cihaz platformu, şirkete ait cihazlar, ofisten çalışan kullanıcılar ve elle gerçekleştirilen çeşitli geriye dönük BT süreçlerine odaklanır. Ancak yeni çalışma alanı hem kullanıcıya hem de şirkete ait çoklu cihaz platformlarını kullanmaya olanak sağlar, kullanıcıların her yerden çalışmalarına olanak sağlar ve otomatik ve öngörülü BT süreçleri sunar. 

Microsoft Intune gibi MDM hizmetleri MDM protokolünü kullanarak Windows 10 cihazlarını yönetebilir. Yerleşik Windows 10 yönetim istemcisi kurumsal yönetim görevlerini gerçekleştirmek için Intune’la iletişim kurabilir. Windows 10 cihazlarda modern yönetime geçiş yapmanıza yardımcı olur. Ancak gelişmiş cihaz yapılandırma, sorun giderme ve eski Win32 uygulama yönetimi gibi şu anda Windows 10 MDM’de desteklenmeyen belirli özelliklere ihtiyacınız olabilir. Bu özellikler için, Intune yazılım istemcinizi Windows 10 cihazlarınızda çalıştırmanız gerekebilir. Sonuç olarak, Windows 10 MDM’nin sağladığı yeni özelliklerden yararlanamazsınız. [Intune yazılım istemcisi ile Windows 10 MDM arasındaki farkları karşılaştırın](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

Intune yönetim uzantısı yerleşik Windows 10 MDM özelliklerini tamamlar. İhtiyacınız olan özellikleri sağlayan Windows 10 cihazlarda çalışan PowerShell betikleri oluşturabilirsiniz. Örneğin, Windows 10 cihazlarınıza eski bir Win32 uygulaması yükleyen bir PowerShell betiği oluşturabilir, betiği Intune’a yükleyebilir, betiği bir Azure Active Directory (AD) grubuna atayabilir ve Windows 10 cihazlarında çalıştırabilirsiniz. Daha sonra betiğin Windows 10 cihazlarda çalışma durumunu baştan sona izleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
Intune yönetim uzantısı şu önkoşullara sahiptir:
- Cihazların Azure AD’ye katılmış olması gerekir
- Cihazlar Windows 10, sürüm 1607 veya üzeri çalıştırmalıdır

## <a name="create-a-powershell-script-policy"></a>PowerShell betik ilkesi oluşturma 
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **PowerShell betikleri**’ni seçin.
5. **PowerShell betikleri** dikey penceresinde, **Betik ekle**’yi seçin.
6. **PowerShell Betiği Ekle** dikey penceresinde, PowerShell betiği için bir **Ad** ve **Açıklama** girin.
7. **Betik konumu** için, PowerShell betiğine gözatın. Betik en fazla 10 KB (ASCII) veya 5 KB (Unicode) olmalıdır.
8. **Yapılandır**’ı seçin ve ardından betiği cihazda kullanıcının kimlik bilgileriyle (**Evet**) veya sistem bağlamıyla (**Hayır**) çalıştırmak istediğinizi seçin. Varsayılan olarak, betik sistem bağlamında çalıştırılır. Betiğin sistem bağlamında çalıştırılması gerekli değilse **Evet**’i seçin. 
  ![PowerShell betiği dikey penceresi ekleme](./media/mgmt-extension-add-script.png)
9. Betiğin güvenilir bir yayımcı tarafından imzalanmış olup olmaması gerektiğini seçin (**Evet**). Varsayılan olarak, betiğin imzalanmasına yönelik bir gereksinim yoktur. 
10. **Tamam**’a tıklayın ve daha sonra betiği kaydetmek için **Oluştur**’a tıklayın.

## <a name="assign-a-powershell-script-policy"></a>PowerShell betik ilkesi atama
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **PowerShell betikleri**’ni seçin.
5. **PowerShell betikleri** dikey penceresinde, atanacak betiği seçin ve daha sonra **Yönet** > **Atamalar**’ı seçin.
  ![PowerShell betiği dikey penceresi ekleme](./media/mgmt-extension-assignments.png)
 
6. Kullanılabilir Azure AD gruplarını listelemek için **Grupları Seç**’i seçin. 
7. Cihazları betiği alacak olan kullanıcıların bulunduğu bir veya birden çok grup seçin ve ardından **Seç**'e tıklayarak seçili gruplara ilkeyi atayın.

Intune yönetim uzantısı saatte bir kez Intune ile eşitlenir. İlkeyi Azure AD gruplarına atadıktan sonra, PowerShell betiği çalıştırılır ve çalıştırma sonuçları raporlanır. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>PowerShell betikleri için çalıştırma durumunu izleme
Azure portalda kullanıcılar ve cihazlar için PowerShell betiklerinin çalıştırma durumunu izleyebilirsiniz.
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **PowerShell betikleri**’ni seçin.
5. **PowerShell betikleri** dikey penceresinde, izlenecek betiği seçin ve daha sonra **İzle**’yi ve şu raporlardan birini seçin:
   - **Cihaz durumu**
   - **Kullanıcı durumu**
