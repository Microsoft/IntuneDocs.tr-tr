---
title: "Önkoşullar | Microsoft Docs"
description: "Intune önkoşullarını ve gereksinimlerini içeren bağlantılar"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e13a9c426e07ebb2443bd403d1a5c7274afd387e
ms.openlocfilehash: d07c7e667dbb5c01a9dcd8b2f69e7d930c27f25a


---

# <a name="prerequisites-to-getting-started-with-intune"></a>Intune kullanmaya başlamak için önkoşullar

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune’u kurmaya başlamadan önce, aşağıdaki gereksinimleri gözden geçirin:

- [Desteklenen cihazlar ve bilgisayarlar](#intune-supported-devices)
- [Intune kullanan desteklenen web tarayıcıları listesi](#intune-supported-web-browsers)

Ayrıca [Intune ağ bant genişliği kullanımı](network-bandwidth-use.md) hakkında bilgi edinmelisiniz.

## <a name="intune-supported-devices"></a>Intune desteklenen cihazlar

Intune mobil cihaz yönetimi kullanarak aşağıdaki cihazları yönetebilirsiniz:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune Windows Server işletim sistemlerini yönetmek için kullanılamaz.

Intune cihaz yönetimi [bu yetenekleri](mobile-device-management-capabilities-in-microsoft-intune.md) sağlar.

### <a name="windows-pc-software-client"></a>Windows bilgisayarı yazılım istemcisi

Bir [Intune yazılım istemcisi](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) alternatif bir kayıt yöntemi olarak Windows bilgisayarlara dağıtılabilir ve yüklenebilir. Intune yazılım istemcisini Windows 10 Home sürümü hariç, Windows 7 ve üzeri bilgisayarları yönetmek için kullanabilirsiniz. Bilgisayarları istemci yazılımıyla yönetmek [bu özelliklerden](windows-pc-management-capabilities-in-microsoft-intune.md) yararlanmanızı sağlar.

### <a name="exchange-activesync-management"></a>Exchange ActiveSync yönetimi

Intune konsolundan [Exchange ActiveSync cihazlarını](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) yönetebilirsiniz. Bu seçenek, diğer yöntemler ile karşılaştırıldığında sınırlı sayıda yönetim özelliği sunar. Desteklenen cihaz listesi için bkz. [Office 365'te yerleşik Mobil Cihaz Yönetimi yetenekleri](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0).

## <a name="intune-supported-web-browsers"></a>Intune desteklenen web tarayıcıları

Farklı yönetim görevleri aşağıdaki yönetim web sitelerinden birini kullanmanızı gerektirir.

- [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune yönetici konsolu](https://admin.manage.microsoft.com/)

|Intune özelliği |Desteklenen tarayıcılar|
|---------|---------|
|**Intune Yönetici konsolu**     |  Internet Explorer 10 veya üstü<br /><br />Google Chrome (42. sürümden önceki sürümler)<br /><br />Silverlight özelliği etkin Mozilla Firefox<br />**Not:** Mozilla, Mart 2017’den itibaren geçerli olacak şekilde Silverlight desteğini kaldıracaktır. [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Office 365 Yönetici Portalı**     |Mobil tarayıcılar ve yönetilen tarayıcılar dahil tüm tarayıcılar  |
|**Şirket Portalı web sitesi**     |**Mobil cihazlarda:** desteklenen her platform için varsayılan web tarayıcısını kullanın   <br /><br />**Windows bilgisayarlarında:** Internet Explorer 10 veya üstü ya da Microsoft Edge<br /><br />**Mac OS X 10.9 veya sonraki sürümlerde:** Apple Safari    |

> [!Note]
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) desteklemediklerinden yönetici konsolu için desteklenmez. Intune konsolu belirli bir zaman dilimi içinde Silverlight deneyiminden uzaklaşacaktır; bir süre sonra Intune’un tüm mobil cihaz ve uygulama yönetimi özellikleri [yeni Microsoft Azure portalında kullanılabilir olacaktır](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Yalnızca hizmet yöneticisi izinlerine sahip olan veya genel yönetici rolüne sahip bir kiracı yöneticisi olan kullanıcılar bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız Intune kullanma lisansına ve **İzin Verildi** oturum açma durumuna sahip olmalıdır.

>[!div class="step-by-step"]

>[**Ağ oluşturma** &rarr;](network-bandwidth-use.md)  



<!--HONumber=Dec16_HO3-->


