---
title: Active Directory için Intune Bağlayıcısı için proxy ayarlarını yapılandırma
description: Mevcut şirket içi proxy sunucuları ile çalışmak Active Directory için Intune bağlayıcısının nasıl yapılandırılacağı ele alınmaktadır.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c47a7413d98467fffc26dee098a64cfeac770e4
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043554"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Mevcut şirket içi proxy sunucuları ile çalışma

Bu makalede, Intune bağlayıcısının giden proxy sunucuları ile çalışmak Active Directory için nasıl yapılandırılacağı açıklanmaktadır. Var olan proxy sahip ağ ortamları sahip müşteriler için tasarlanmıştır.

Bağlayıcıları nasıl çalışır hakkında daha fazla bilgi için bkz. [anlamak Azure AD uygulama ara sunucusu bağlayıcıları](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Giden proxy atlama

Bağlayıcılar, giden isteklerde temel işletim sistemi bileşeni vardır. Bu bileşenler, Web Proxy Otomatik Bulma (WPAD) kullanarak ağ üzerinde bir proxy sunucusunu bulmak otomatik olarak deneyin.

İşletim sistemi bileşenleri wpad.domainsuffix için DNS araması gerçekleştirerek bir ara sunucu bulmaya. DNS Arama çözümlenirse, bir HTTP isteği wpad.dat IP adresine yapılır. Bu istek proxy yapılandırma betiği, ortamınızdaki olur. Bağlayıcı, bir giden proxy sunucusunun seçmek için bu betiği kullanır. Ancak, bağlayıcı trafik yine de proxy gereken ek yapılandırma ayarları nedeniyle geçmesine değil.

Azure hizmetlerine doğrudan bağlantı kullandığından emin olmak için şirket içi proxy atlama bağlayıcıyı yapılandırabilirsiniz. Korumak için daha az bir yapılandırma olduğunu gösterdiğinden, ağ ilkesi, izin verdiği sürece bu yaklaşım önerilir.

Bağlayıcı için giden bağlantı proxy'si kullanımını devre dışı bırakmak için Düzenle: \Program Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config dosya ve bu kod örneğinde gösterilen bölümde proxy bağlantı noktası ve proxy adresi ekleyin:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```
Connector Updater Hizmeti ayrıca Proxy'yi atlar için benzer bir değişiklik için C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config olun.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Varsayılan .config dosyasına geri yapmanız durumunda orijinal dosyalarının kopyalarını emin olun.

Yapılandırma dosyalarını oluşturduktan sonra Intune bağlayıcı hizmetini yeniden başlatmanız gerekir. 

1. Açık **services.msc**.
2. Bulmak ve seçmek **Intune kullandığı hizmet**.
3. Seçin **yeniden**.

![Hizmeti yeniden başlatma işleminin ekran görüntüsü](media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Sonraki adımlar

[Cihazlarınızı yönetme](device-management.md)