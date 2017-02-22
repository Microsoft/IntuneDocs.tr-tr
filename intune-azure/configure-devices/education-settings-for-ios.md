---
title: "iOS için Intune eğitim ayarlarını yapılandırma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS cihazlarında eğitim ayarlarını denetlemek için kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: e52fdf8c30a680d62071cd31e308dd0180e8b9dc


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde iOS cihazları için Intune eğitim ayarlarını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>iOS eğitim ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, sürüm yükseltme profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **iOS**’yi seçin.
6. **Profil türü** açılan listesinde **Eğitim**’i seçin.
7. **Eğitim** dikey penceresinde aşağıdakilerden birini seçin:
    - **Öğretmen kök sertifika dosyası**
    - **Öğretmen PKCS12 / PFX profili**
    - **Öğrenci kök sertifika profili**
    - **Öğrenci PKCS12 / PFX profili**
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.



<!--HONumber=Feb17_HO1-->


