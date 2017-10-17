---
title: Desteklenen cihazlar - Microsoft Intune
description: "Intune cihaz yönetimi için desteklenen cihaz platformlarını ve tarayıcıları listeler"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6c9cc3a6a84c48da36b0219743012a15b72e6810
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
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

### <a name="supported-samsung-knox-standard-devices"></a>Desteklenen Samsung KNOX Standard cihazlar

Şirket Portalı uygulaması, yalnızca cihazın [desteklenen KNOX cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) görüntülendiği durumlarda MDM kaydı sırasında Samsung KNOX etkinleştirmesi yapmaya çalışır. Böylece MDM kaydını önleyen KNOX kayıt hatalarının önüne geçilir. Samsung KNOX etkinleştirmesini desteklemeyen cihazlar, standart Android cihazlar olarak kaydedilir. Bir Samsung cihazın KNOX’u destekleyen model numaraları olabilir, diğerlerinin olamaz. Samsung cihazlar satın alıp dağıtmadan önce, cihazınızın kurumsal bayisinden KNOX uyumluluğunu doğrulayın.

Aşağıdaki Samsung cihaz modelleri KNOX’u desteklemez ve Android için Şirket Portalı uygulaması tarafından yerel Android cihazlar olarak kaydedilir:

| **Cihaz adı** | **Cihaz model numaraları** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
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
