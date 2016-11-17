---
title: "VPN profilleri için özel yapılandırmalar | Microsoft Intune"
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1035a8ca4f63ad973e83ec24a7d700fac1d256cc
ms.openlocfilehash: ee36cd5f3c64fc5dbeeb7265116c14be33b50067


---

# <a name="custom-configurations-for-vpn-profiles"></a>VPN profilleri için özel yapılandırmalar

## <a name="create-a-custom-configuration"></a>Özel yapılandırma oluşturma
Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanabilirsiniz. Özel yapılandırma oluşturmak için:

   1. Intune yönetici konsolunda **İlke** > **İlke Ekle** > *Platformu genişlet* > **Özel yapılandırma** > **İlke Oluştur**’a tıklayın.
   2. İlke için bir ad sağlayın.
   3. Her URI ayarı için, **Ekle**’yi seçin ve istenen bilgileri sağlayın. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

   4.  URI ayarlarının tümünü girdikten sonra **İlkeyi kaydet**’i seçin ve ilkeyi dağıtın.

## <a name="deploy-a-configuration-policy"></a>Yapılandırma ilkesini dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**’a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**’i seçin.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

##<a name="example-of-uri-settings-for-a-custom-vpn-profile-configuration"></a>Özel VPN profili yapılandırması için örnek URI ayarları
Burada, Contoso adlı kurgusal bir şirkette VPN’e özel yapılandırma oluşturmak için örnek URI değerleri girdileri verilmiştir. Her girdinin veri türü gibi daha fazla bilgi edinmek için, bkz. [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

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

Bu ayarların nasıl kullanılacağı hakkındaki sorular veya ne yaptıklarıyla ilgili ek ayrıntılar için, müşteriler yapılandırma servisi sağlayıcısı (CSP) belgelerine bakabilir: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

## <a name="uri-settings-for-android-perapp-vpn-on-pulsesecure"></a>PulseSecure üzerinde Android uygulaması başına VPN için URI ayarları
### <a name="custom-uri-for-package-list"></a>PAKET LİSTESİ İÇİN ÖZEL URI
-  Veri türü = String
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Değer = Sınırlayıcıyla ayrılmış paket listesi.
   - Sınırlayıcılar:  noktalı virgül (;), iki nokta (:), virgül (,), dikey çizgi (|)

Örnekler:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>MOD İÇİN ÖZEL URI (İSTEĞE BAĞLI)
- Veri Türü = String
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Notlar
> - Özel profile atadığınız adla aynı *adı* kullanın.
> - Olası değerler: *GENEL*, *BEYAZ LİSTE*, *KARA LİSTE*
> - PackageList sağlamadıysa, varsayılan değer *GENEL*’dir (sistem genelindeki profillerle geriye dönük uyumluluk)
> - PackageList sağlandıysa varsayılan değer *BEYAZ LİSTE* olur.


### <a name="see-also"></a>Ayrıca bkz.
(Microsoft Intune’da VPN bağlantıları)[vpn-connections-in-microsoft-intune.md]



<!--HONumber=Nov16_HO1-->


