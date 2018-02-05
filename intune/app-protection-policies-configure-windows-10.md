---
title: "Windows 10 için uygulama koruma ilkeleri yapılandırmaya hazırlanma"
titlesuffix: Azure portal
description: "Azure AD’de mobil uygulama yönetimi (MAM) sağlayıcısı kurma"
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3254adc66c5fd5dc991364c3a33aabef8ac2030b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10 için uygulama koruma ilkeleri yapılandırmaya hazırlanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure AD’de MAM sağlayıcısını ayarlayarak Windows 10 için mobil uygulama yönetimini (MAM) etkinleştirin. Azure AD’de bir MAM sağlayıcısı ayarlamak, Intune ile yeni bir Windows Bilgi Koruması (WIP) ilkesi oluştururken kayıt durumunu belirtmenizi sağlar. Kayıt durumu MAM ya da mobil cihaz yönetimi (MDM) olabilir.

> [!NOTE]
> MAM kayıt durumu olan cihazların Azure AD’ye katılması gereklidir.

## <a name="to-configure-the-mam-provider"></a>MAM sağlayıcısını yapılandırmak için

1. Azure portalında oturum açın ve **Azure Active Directory** seçeneğini belirleyin.

2. **Yönet** grubunda **Mobilite (MDM ve MAM)** öğesini seçin.

3. **Microsoft Intune**’a tıklayın.

4. **Yapılandır** dikey penceresinde **Varsayılan MAM URL’lerini geri yükle** grubundaki ayarları yapılandırın.

    **MAM kullanıcı kapsamı**  
      Çalışanlarınızın Windows cihazlarındaki kurumsal verileri yönetmek için MAM otomatik kaydı kullanın. MAM otomatik kayıt, kendi cihazını getir senaryoları için yapılandırılacaktır.<ul><li>**Yok.**<br>Tüm kullanıcıların MAM’a kayıt olup olamayacağını seçin.</li><li>**Bazı**<br>MAM’a kayıt olacak kullanıcıları içeren Azure AD gruplarını seçin.</li><li>**Tümü**<br>Tüm kullanıcıların MAM’a kayıt olup olamayacağını seçin.</li></ul>

    **MDM kullanım koşulları URL’si**  
     MAM hizmeti uç noktasının kullanım koşulları URL’si. Uç nokta kullanım koşulları, son kullanıcılar cihazlarını yönetime kaydetmeden önce kullanım koşullarını göstermek için kullanılır. Kullanım koşulları metni, mobil cihazda zorlanan ilkeler hakkında kullanıcıyı bilgilendirir.

    **MDM bulma URL’si**  
    MAM hizmeti kayıt uç noktası URL'si. Kayıt uç noktası, cihazları MAM hizmetine yönetim için kaydetmek üzere kullanılır.

    **MAM uyumluluğu URL’si**  
      MAM hizmeti uyumluluk uç noktası URL’si. Bir kullanıcının uyumlu olmayan bir cihazdaki kaynağa erişimi reddedilirse kullanıcıya uyumluluk URL’sine bir bağlantı gösterilir. Kullanıcılar, cihazlarının neden uyumlu olmadığını görmek isterse MAM hizmeti tarafından barındırılan bu URL’ye gidebilir. Kullanıcılar, cihazlarını uyumlu hale getirip kaynaklara erişmeye devam etmek için self servis düzeltme de başlatabilir.

5.  **Kaydet**'e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

[WIP uygulama koruma ilkesi oluşturma](windows-information-protection-policy-create.md)
