---
title: "Microsoft Intune VPN profilleri için özel yapılandırmalar"
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 634a2b72f2f4ae1b3164b0f063aba4b73f05f1fb
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Microsoft Intune VPN profilleri için özel yapılandırmalar

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Özel yapılandırma oluşturma
Aşağıdakilere yönelik VPN profilleri oluşturmak için Intune özel yapılandırma ilkeleri kullanabilirsiniz:

* Android 4 ve üzeri çalıştıran cihazlar
* Android for Work cihazlar
* Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
* Windows Phone 8.1 ve üzeri sürümleri çalıştıran cihazlar 
* Windows 10 masaüstü çalıştıran kayıtlı cihazlar
* Windows 10 Mobile çalıştıran cihaz

Standart Intune VPN ilkeleri, kullanmak istediğiniz ayarları içermiyorsa bu tür bir ilke yararlı olabilir.

## <a name="to-create-a-custom-configuration-policy"></a>Özel yapılandırma ilkesi oluşturmak için:

   1. [Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **İlke Ekle** > *Platformu genişlet* > **Özel yapılandırma** > **İlke Oluştur**’u seçin.
   2. İlke için bir ad girin.
   3. Belirtmek istediğiniz her URI ayarı için **Ekle**’yi seçin ve istenen bilgileri sağlayın. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

   4.  URI ayarlarının tümünü girdikten sonra **İlkeyi kaydet**’i seçin ve ilkeyi dağıtın.

Ardından, normal şekilde [ilkeyi dağıtın](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

## <a name="example-uri-settings"></a>Örnek URI ayarları

Contoso adlı kurgusal bir şirkette VPN’e özel yapılandırma oluşturmak için bu ayarlar kullanılabilir.
Kullanabileceğiniz tüm ayarlar hakkındaki ayrıntılar için bkz. [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).

**Native Contoso VPN (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Bu ayarların nasıl kullanılacağı hakkında sorular veya ne yaptıklarıyla ilgili ek ayrıntılar için müşteriler [yapılandırma hizmet sağlayıcısı (CSP) belgelerine](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) bakabilir.

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


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md)
