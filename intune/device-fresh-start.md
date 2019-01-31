---
title: Microsoft Intune - Azure ile Windows 10 cihazlarını sıfırlama | Microsoft Docs
description: Microsoft Intune kullanarak Windows 10 bilgisayarlarındaki uygulamaları silmek veya kaldırmak için Yeni Başlangıç'ı kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1eb1e671cc16196974cb15cdc785ba7d99fa8f46
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303421"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Windows 10 cihazlarını Intune ile sıfırlamak için Fresh Start kullanma


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Yeni Başlangıç** cihaz eylemi, Windows 10 sürüm 1703 veya üstünü çalıştıran bir bilgisayara yüklü tüm uygulamaları kaldırır. Yeni Başlangıç, genellikle yeni bir bilgisayara önceden yüklenmiş (OEM) uygulamaları kaldırmaya yardımcı olur.  

1. [Azure portalında](https://portal.azure.com) oturum açın ve > **Microsoft Intune** > **Cihazlar** > **Tüm cihazlar**'a gidin.
2. Yönettiğiniz cihazların listesinden bir Windows 10 masaüstü cihazını seçin.
3. **Yeni Başlangıç**'a tıklayın. 
4. **Bu cihazdaki kullanıcı verilerini sakla**'yı seçerek:
   * Cihazın Azure AD'ye katılmış durumda kalmasını sağlayın
    * Azure Active Directory kullanıcı işaretlerini cihazında etkinleştirildiğinde cihaz mobil cihaz Yönetimi yeniden zaman kaydedilir.
    * Kullanıcının Giriş klasörünün içeriğini saklayın ve uygulamalarla ayarları kaldırın  
  > [!IMPORTANT]
 > Kullanıcı verilerini saklamazsanız, cihaz hazır geldiği duruma geri yüklenir. KCG cihazları Azure AD'den kaydı ve mobil cihaz yönetimi.
 > Azure AD'ye katılmış cihazları Azure Active Directory kullanıcı işaretlerini cihazında etkinleştirildiğinde mobil cihazı yönetime yeniden kaydedilir.
 
5. **Tamam** düğmesine tıklayın.   
6. Bu eylemin durumunu görmek için, **Cihazlar**'a dönün ve **Cihaz eylemleri**'ne tıklayın.  
