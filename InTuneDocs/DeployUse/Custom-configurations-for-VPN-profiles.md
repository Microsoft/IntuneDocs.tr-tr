---
title: "VPN profilleri için özel yapılandırmalar | Microsoft Intune"
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: b61a4c90cfed9922df151a6c1ac93e276db18623


---

# VPN profilleri için özel yapılandırmalar

## Özel yapılandırma oluşturma
Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanabilirsiniz. Özel yapılandırma oluşturmak için:

   1. Intune yönetim konsolunda **İlke** -> **İlke Ekle** -> *<Expand platform>* -> **Özel yapılandırma** -> **İlke Oluştur**’a tıklayın.
   2. İlke için bir ad sağlayın.
   3. Her URI ayarı için, **Ekle**’ye tıklayın ve istenen bilgileri sağlayın. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

   4.  URI ayarlarının tümünü girdikten sonra **İlkeyi kaydet**’e tıklayın ve ilkeyi dağıtın.

## Yapılandırma ilkesini dağıtma

1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

##Özel VPN profili yapılandırması için örnek URI ayarları
Burada, Contoso adlı kurgusal bir şirkette VPN’e özel yapılandırma oluşturmak için örnek URI değerleri girdileri verilmiştir. Her girdinin veri türü gibi daha fazla bilgi edinmek için, bkz. [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx)

Native Contoso VPN (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Bu ayarların nasıl kullanılacağı hakkındaki sorular veya ne yaptıklarıyla ilgili ek ayrıntılar için, müşteriler CSP belgelerine bakabilir: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## PulseSecure üzerinde Android uygulaması başına VPN için URI ayarları
### PAKET LİSTESİ İÇİN ÖZEL URI 
-  Veri türü = String
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Değer = Sınırlayıcıyla ayrılmış paket listesi.
   - Sınırlayıcılar:  noktalı virgül (;), iki nokta (:), virgül (,), dikey çizgi (|)

Örnekler: 
- com.android.chrome
- com.android.chrome;com.android.browser

### MOD İÇİN ÖZEL URI (İSTEĞE BAĞLI)
- Veri Türü = String
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Notlar
> - Özel profile atadığınız adla aynı *adı* kullanın.
> - Olası değerler: *GENEL*, *BEYAZ LİSTE*, *KARA LİSTE*
> - PackageList sağlamadıysa, varsayılan değer *GENEL*’dir (sistem genelindeki profillerle geriye dönük uyumluluk)
> - PackageList sağlandıysa varsayılan değer *BEYAZ LİSTE* olur.


### Ayrıca bkz.
(Microsoft Intune’da VPN bağlantıları)[vpn-connections-in-microsoft-intune.md]



<!--HONumber=Jul16_HO3-->


