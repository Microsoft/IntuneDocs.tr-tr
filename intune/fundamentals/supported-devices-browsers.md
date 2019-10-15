---
title: Microsoft Intune tarafından desteklenen işletim sistemleri ve tarayıcılar
titleSuffix: ''
description: Intune cihaz yönetimi için desteklenen cihaz platformlarını ve tarayıcılarını listeler
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d2777f2caabc24a457fc407b3e47facb1f6fc3c
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314625"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Intune 'da desteklenen işletim sistemleri ve tarayıcılar

Microsoft Intune ayarlamadan önce desteklenen işletim sistemlerini ve tarayıcıları gözden geçirin.

Intune 'u cihazınıza yükleme konusunda yardım için bkz. iş ve [Intune ağ bant genişliği kullanımını](network-bandwidth-use.md) [almak için yönetilen cihazları kullanma](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) .

Yapılandırma hizmeti sağlayıcısı desteği hakkında daha fazla bilgi için [yapılandırma hizmeti sağlayıcı başvurusunu](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)ziyaret edin.

## <a name="intune-supported-operating-systems"></a>Intune tarafından desteklenen işletim sistemleri

Aşağıdaki işletim sistemlerini çalıştıran cihazları yönetebilirsiniz:

[!INCLUDE [mdm-supported-devices](../../intune-classic/includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Desteklenen Samsung KNOX Standard cihazları

MDM kaydını önleyen Knox etkinleştirme hatalarının önüne geçmek için, Şirket Portalı uygulaması yalnızca cihaz [desteklenen Knox cihazları listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace)görünürse MDM kaydı sırasında Samsung KNOX etkinleştirmesine çalışır. Samsung KNOX etkinleştirmesini desteklemeyen cihazlar, standart Android cihazlar olarak kayıt kaydeder. Samsung cihazında Knox 'u destekleyen bazı model numaraları olabilir, diğerleri de değildir. Samsung cihazlar satın alıp dağıtmadan önce cihaz satıcılarınızla Knox uyumluluğunu doğrulayın.

> [!NOTE]
> Samsung KNOX cihazlarını kaydetme, [Samsung sunucularına erişimi etkinleştirmenizi](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers)gerektirebilir. 

Aşağıdaki Samsung cihaz modelleri listesi Knox 'ı desteklemez. Android için Şirket Portalı uygulamasına göre yerel Android cihazlar olarak kaydedilir:

| **Cihaz adı** | **Cihaz model numaraları** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/çekirdek 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy çekirdek ana | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy genel | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy genel 3 | SM-G7200 |
| Galaxy genel Neo | GT-I9060I |
| Galaxy genel ana değer sürümü | SM-G531H |
| Galaxy J maks | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 ası | SM-J110F<br>SM-J110H |
| Galaxy J1 mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy ışığı | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10,1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0 @ no__t-0 | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7 @ no__t-0/Tab 3 Lite 7 @ no__t-1 | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0 @ no__t-0 | SM-T311 |
| Galaxy Tab 3 10.1 @ no__t-0 | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy eğilimi 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy başak 2 Duos | SM-G130BU |


### <a name="windows-pc-software-client"></a>Windows BILGISAYARı yazılım istemcisi

[Intune yazılım istemcisi](../manage-windows-pcs-with-microsoft-intune.md) , Windows bilgisayarlarına alternatif bir kayıt yöntemi olarak dağıtılabilir ve yüklenebilir. Bu işlevsellik yalnızca klasik Intune Portalı kullanılarak kullanılabilir. Windows 7 ve üzeri bilgisayarları Windows 10 Home Edition dışında yönetmek için Intune yazılım istemcisini kullanabilirsiniz.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](../enrollment/device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Intune tarafından desteklenen Web tarayıcıları

Farklı yönetim görevleri aşağıdaki yönetim Web sitelerinden birini kullanmanızı gerektirir.

- [Microsoft 365 Yönetim Merkezi](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure portalda](https://portal.azure.com/)

Aşağıdaki tarayıcılar bu portallar için desteklenir:
- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en son sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)




### <a name="intune-classic-portal"></a>Klasik Intune portalı

Klasik Intune portalı yalnızca Intune PC yazılım istemcisi (https://manage.microsoft.com) ' a kaydedilmiş cihazların yönetilmesi için kullanılır. Klasik Intune portalı, Silverlight tarayıcı desteği gerektirir.

Aşağıdaki Silverlight tarayıcıları Intune konsolunu destekler:
- Internet Explorer 10 veya üzeri
- Google Chrome (sürüm 42 ' den önceki sürümler)
- Silverlight özellikli Mozilla Firefox (sürüm 56 ' den önceki sürümler)

> [!Note]
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight 'ı](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx)desteklemediği Için klasik Intune portalında desteklenmez.

Yalnızca Hizmet Yöneticisi izinlerine sahip kullanıcılar veya genel yönetici rolüne sahip kiracı yöneticileri bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız, Intune 'U kullanmak için bir lisansa ve **Izin verildi**oturum açma durumuna sahip olmalıdır.
