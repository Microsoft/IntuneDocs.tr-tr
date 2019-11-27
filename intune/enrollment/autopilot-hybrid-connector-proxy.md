---
title: Active Directory için Intune Bağlayıcısı için proxy ayarlarını yapılandırma
description: Active Directory Intune bağlayıcısının mevcut şirket içi ara sunucularla çalışması için nasıl yapılandırılacağını ele alır.
keywords: ''
author: master11218
ms.author: erikje
manager: dougeby
ms.date: 4/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a1af2e7c8aff281e04e92344b3e2c762bb23e0a
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465754"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Mevcut şirket içi proxy sunucularıyla çalışma

Bu makalede, Active Directory için Intune bağlayıcısının giden proxy sunucularıyla çalışacak şekilde nasıl yapılandırılacağı açıklanmaktadır. Mevcut proxy 'leri olan ağ ortamları olan müşterilere yöneliktir.

Bağlayıcıların nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Azure AD uygulama ara sunucusu bağlayıcıları anlama](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-connectors).

## <a name="bypass-outbound-proxies"></a>Giden proxy 'leri atla

Bağlayıcılar, giden istekleri yapan temel işletim sistemi bileşenlerine sahiptir. Bu bileşenler, Web proxy otomatik bulma (WPAD) kullanarak ağ üzerindeki bir proxy sunucusunu otomatik olarak bulmayı dener.

İşletim sistemi bileşenleri, WPAD. domainsuffix için bir DNS araması gerçekleştirerek bir ara sunucu bulmaya çalışır. Arama DNS 'de çözümlenirse, WPAD. dat için IP adresine bir HTTP isteği yapılır. Bu istek, ortamınızda ara sunucu yapılandırma betiği haline gelir. Bağlayıcı, giden bir ara sunucu seçmek için bu betiği kullanır. Bununla birlikte, ara sunucuda gereken ek yapılandırma ayarları nedeniyle bağlayıcı trafiği yine de gidemeyebilir.

Bağlayıcıyı, Azure hizmetlerine doğrudan bağlantı kullandığından emin olmak için şirket içi ara sunucusunu atlayacak şekilde yapılandırabilirsiniz. Bu yaklaşım, Ağ ilkeniz izin verdiği sürece, devam etmek için daha az bir yapılandırmaya sahip olduğunuz anlamına gelir.

Bağlayıcı için giden proxy kullanımını devre dışı bırakmak için: \Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config dosyasını düzenleyin ve bu kod örneğinde gösterilen bölümünde proxy adresini ve proxy bağlantı noktasını ekleyin:

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

Bağlayıcı Güncelleştiricisi hizmetinin proxy 'yi de atlayacak emin olmak için, C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config. 'de benzer bir değişiklik yapın

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

Varsayılan. config dosyalarına döndürmeniz gerekiyorsa, özgün dosyaların kopyalarını aldığınızdan emin olun.

Yapılandırma dosyaları değiştirildikten sonra, Intune Bağlayıcısı hizmetini yeniden başlatmanız gerekir. 

1. **Services. msc**dosyasını açın.
2. **Intune ODJConnector hizmetini**bulun ve seçin.
3. **Yeniden Başlat**' ı seçin.

![Hizmetin yeniden başlatılması ekran görüntüsü](./media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Sonraki adımlar

[Cihazlarınızı yönetin](../remote-actions/device-management.md)
