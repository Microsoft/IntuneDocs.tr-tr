---
title: "Microsoft Intune’la özel VPN profilleri oluşturma | Microsoft Docs"
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: e92593062ad2ed7a4098922715106f47f4e78d4f


---

# <a name="how-to-create-custom-vpn-profiles-with-microsoft-intune"></a>Microsoft Intune’la özel VPN profilleri oluşturma

## <a name="create-a-custom-configuration"></a>Özel yapılandırma oluşturma
Aşağıdakilere yönelik VPN profilleri oluşturmak için Intune özel yapılandırma ilkeleri kullanabilirsiniz:

* Android 4 ve üzeri çalıştıran cihazlar
* Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
* Windows Phone 8.1 ve üzeri sürümleri çalıştıran cihazlar 
* Windows 10 masaüstü çalıştıran kayıtlı cihazlar 
* Windows 10 Mobile çalıştıran cihazlar

Standart Intune VPN ilkeleri, kullanmak istediğiniz ayarları içermiyorsa bu tür bir ilke yararlı olabilir.

## <a name="to-create-a-custom-configuration-policy"></a>Özel yapılandırma ilkesi oluşturmak için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
4. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
5. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
6. **Profil Oluştur** dikey penceresinde, VPN profili için **Ad** ve **Açıklama** girin.
7. **Platform** açılan listesinden, VPN ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, özel cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **iOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **macOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **Windows Phone 8.1**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **Özel**’i seçin.
7. **Özel OMA-URI Ayarları** dikey penceresinde, belirtmek istediğiniz her URI ayarı için **Ekle**’yi seçin, gerekli bilgileri sağlayın ve **Tamam**’ı seçin. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

4.  İhtiyacınız olan tüm URI ayarlarını girdikten sonra **Tamam**’ı seçin ve ardından **Profil Oluştur** dikey penceresinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).

## <a name="example-uri-settings"></a>Örnek URI ayarları

Contoso adlı kurgusal bir şirkette VPN’e özel yapılandırma oluşturmak için bu ayarlar kullanılabilir.
Kullanabileceğiniz tüm ayarlar hakkındaki ayrıntılar için bkz. [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx).

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

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>PulseSecure üzerinde Android uygulaması başına VPN için URI ayarları
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






<!--HONumber=Feb17_HO1-->


