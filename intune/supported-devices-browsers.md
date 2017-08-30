---
title: Desteklenen cihazlar - Microsoft Intune
description: "Intune cihaz yönetimi için desteklenen cihaz platformlarını ve tarayıcıları listeler"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f862129d73c83e078d8b29201f1d92b9b65aa609
ms.sourcegitcommit: ce8a1f0f4e95444949556600d1837937b6efd769
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2017
---
# <a name="supported-devices-and-browsers"></a>Desteklenen cihazlar ve tarayıcılar

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu makale, kuruluşta cihaz yönetiminden sorumlu olan yöneticilere yöneliktir. Telefonunuza Intune yüklerken yardım almak için bkz. [İşleri halletmek için yönetilen cihazları kullanma](/intune-user-help/company-portal-frequently-asked-questions).

Microsoft Intune’u kurmaya başlamadan önce, aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen cihazlar ve bilgisayarlar](#intune-supported-devices)
- [Intune kullanan desteklenen web tarayıcıları listesi](#intune-supported-web-browsers)

Ayrıca [Intune ağ bant genişliği kullanımı](network-bandwidth-use.md) ([Klasik konsol](/intune-classic/get-started/network-bandwidth-use)) hakkında da bilgi edinmelisiniz.

## <a name="intune-supported-devices"></a>Intune desteklenen cihazlar

Intune mobil cihaz yönetimi kullanarak aşağıdaki cihazları yönetebilirsiniz:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Intune Windows Server işletim sistemlerini yönetmek için kullanılamaz.

### <a name="windows-pc-software-client"></a>Windows bilgisayarı yazılım istemcisi

Bir [Intune yazılım istemcisi](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) alternatif bir kayıt yöntemi olarak Windows bilgisayarlara dağıtılabilir ve yüklenebilir. Bu işlev, yalnızca Intune klasik konsolunda bulunur. Intune yazılım istemcisini, Windows 7 ve üzerini (Windows 10 Home Edition dışında) çalıştıran bilgisayarları yönetmek için kullanabilirsiniz.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Intune desteklenen web tarayıcıları

Farklı yönetim görevleri aşağıdaki yönetim web sitelerinden birini kullanmanızı gerektirir.

- [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Intune portalı](https://portal.azure.com/)

Bu portallar için aşağıdaki tarayıcılar desteklenir:
- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en so sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

### <a name="intune-classic-portal"></a>Intune klasik portalı

Intune bilgisayar istemci yazılımı ve Mobil Tehdit Savunması ortakları ile tümleştirme gibi özellikler yalnızca klasik Intune portalında (https://manage.microsoft.com) bulunur. Klasik Intune portalı, Silverlight tarayıcı desteği gerektirir.

Aşağıdaki Silverlight tarayıcıları klasik Intune konsolunu destekler:
- Internet Explorer 10 veya üstü
- Google Chrome (42. sürümden önceki sürümler)
- Silverlight etkinleştirilmiş olarak Mozilla Firefox [Daha fazla bilgi](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx)'ı desteklemediklerinden klasik Intune konsolu için desteklenmez.

Yalnızca hizmet yöneticisi izinlerine sahip olan veya genel yönetici rolüne sahip bir kiracı yöneticisi olan kullanıcılar bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız Intune kullanma lisansına ve **İzin Verildi** oturum açma durumuna sahip olmalıdır.
