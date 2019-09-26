---
title: Microsoft Intune - Azure ile Windows 10 cihazlarını sıfırlama | Microsoft Docs
description: Microsoft Intune kullanarak Windows 10 bilgisayarlarındaki uygulamaları silmek veya kaldırmak için Yeni Başlangıç'ı kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 291c439cb4fca353ad83546c1dfaa4eee104d671
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71304847"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Windows 10 cihazlarını Intune ile sıfırlamak için Fresh Start kullanma


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Yeni Başlangıç** cihaz eylemi, Windows 10 sürüm 1703 veya üstünü çalıştıran bir bilgisayara yüklü tüm uygulamaları kaldırır. Yeni Başlangıç, genellikle yeni bir bilgisayara önceden yüklenmiş (OEM) uygulamaları kaldırmaya yardımcı olur. 

1. [Azure portalında](https://portal.azure.com) oturum açın ve > **Microsoft Intune** > **Cihazlar** > **Tüm cihazlar**'a gidin.
2. Yönettiğiniz cihazların listesinden bir Windows 10 masaüstü cihazını seçin.
3. **Yeni Başlangıç**'a tıklayın. 
4. **Bu cihazdaki kullanıcı verilerini sakla**'yı seçerek:
   * Cihazın Azure AD'ye katılmış durumda kalmasını sağlayın
   * Azure Active Directory etkinleştirilmiş bir Kullanıcı cihazda oturum açtığında cihaz, mobil cihaz yönetimine yeniden kaydoldu.
   * Kullanıcının Giriş klasörünün içeriğini saklayın ve uygulamalarla ayarları kaldırın

  > [!IMPORTANT]
 > Kullanıcı verilerini koruuyorsanız cihaz, yerleşik yönetici hesabını koruyarak varsayılan OOBE (kullanıma hazır deneyim) tamamlandı durumuna geri yüklenir.
 > KCG cihazlarının Azure AD ve mobil cihaz yönetiminden kaydı kaldırılacak.
 > Azure Active Directory etkinleştirilmiş bir Kullanıcı cihazda oturum açtığında, Azure AD 'ye katılmış cihazlar mobil cihaz yönetimine yeniden kaydedilir.
 
5. **Tamam**'ı tıklatın.   
6. Bu eylemin durumunu görmek için, **Cihazlar**'a dönün ve **Cihaz eylemleri**'ne tıklayın.  
7. Cihaz ilk oturum açma ekranına geri yüklenecek.
