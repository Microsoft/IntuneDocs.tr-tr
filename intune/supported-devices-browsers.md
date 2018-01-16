---
title: Desteklenen cihazlar - Microsoft Intune
description: "Intune cihaz yönetimi için desteklenen cihaz platformlarını ve tarayıcıları listeler"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/03/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 56516562b9a7510020475d226c74bf719bdd33a3
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="supported-devices-and-browsers"></a>Desteklenen cihazlar ve tarayıcılar

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu makale, kuruluşta cihaz yönetiminden sorumlu olan yöneticilere yöneliktir. Telefonunuza Intune yüklerken yardım almak için bkz. [İşleri halletmek için yönetilen cihazları kullanma](/intune-user-help/company-portal-frequently-asked-questions).

Microsoft Intune’u kurmaya başlamadan önce, aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen cihazlar ve bilgisayarlar](#intune-supported-devices)
- [Intune kullanan desteklenen web tarayıcıları listesi](#intune-supported-web-browsers)

Ayrıca [Intune ağ bant genişliği kullanımı](network-bandwidth-use.md) ([klasik portal](/intune-classic/get-started/network-bandwidth-use)) hakkında da bilgi edinmelisiniz.

## <a name="intune-supported-devices"></a>Intune desteklenen cihazlar

Intune mobil cihaz yönetimi kullanarak aşağıdaki cihazları yönetebilirsiniz:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Desteklenen Samsung Knox Standard cihazları

Şirket Portalı uygulaması, yalnızca cihazın [desteklenen Knox cihazları listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) görüntülendiği durumlarda MDM kaydı sırasında Samsung Knox etkinleştirmesi yapmaya çalışır. Böylece MDM kaydını önleyen Knox kayıt hatalarının önüne geçilir. Samsung Knox etkinleştirmesini desteklemeyen cihazlar, standart Android cihazlar olarak kaydedilir. Bir Samsung cihazının Knox’u destekleyen model numaraları olabilir, diğerlerinin olamaz. Samsung cihazlar satın alıp dağıtmadan önce, cihazınızın kurumsal bayisinden Knox uyumluluğunu doğrulayın.

> [!NOTE]
> Samsung Knox cihazlarının kaydı için [Samsung sunucularına erişimi etkinleştirmeniz](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers) gerekebilir. 

Aşağıdaki Samsung cihaz modelleri Knox’u desteklemez ve Android için Şirket Portalı uygulaması tarafından yerel Android cihazlar olarak kaydedilir:

| **Cihaz Adı** | **Cihaz Model Numaraları** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |

Intune Windows Server işletim sistemlerini yönetmek için kullanılamaz.

### <a name="windows-pc-software-client"></a>Windows bilgisayarı yazılım istemcisi

Bir [Intune yazılım istemcisi](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) alternatif bir kayıt yöntemi olarak Windows bilgisayarlara dağıtılabilir ve yüklenebilir. Bu işlev, yalnızca klasik Intune portalında kullanılabilir. Intune yazılım istemcisini, Windows 7 ve üzerini (Windows 10 Home Edition dışında) çalıştıran bilgisayarları yönetmek için kullanabilirsiniz.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Intune desteklenen web tarayıcıları

Farklı yönetim görevleri aşağıdaki yönetim web sitelerinden birini kullanmanızı gerektirir.

- [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure portalı](https://portal.azure.com/)

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
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx)’ı desteklemediklerinden klasik Intune portalı için desteklenmez.

Yalnızca hizmet yöneticisi izinlerine sahip olan veya genel yönetici rolüne sahip bir kiracı yöneticisi olan kullanıcılar bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız Intune kullanma lisansına ve **İzin Verildi** oturum açma durumuna sahip olmalıdır.
