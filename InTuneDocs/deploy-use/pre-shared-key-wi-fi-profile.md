---
title: PSK Kullanarak Wi-Fi | Microsoft Intune
description: "Önceden paylaşılan anahtarla Wi-Fi profili oluşturmak için Özel Yapılandırma’yı kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: ad5bb09eb18463f541ca0cbb60ff1f27bdc3251e



---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Önceden paylaşılan anahtarla Wi-Fi profili oluşturmak için özel ilke kullanma
Intune'un **Özel Yapılandırmasını**, önceden paylaşılan anahtar ile Wi-Fi profili oluşturmak üzere kullanma Bu konuda, bir EAP tabanlı Wi-Fi profili oluşturmaya bir örnek de yer almaktadır.

> [!NOTE]
-   Aşağıda anlatıldığı gibi kodu söz konusu ağa bağlanan bir bilgisayardan kopyalamak size daha kolay gelebilir.
- Android için, Johnathon Biersack tarafından sağlanan bu [Android PSK Oluşturucu](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/)’yu kullanma seçeneğiniz de vardır.
-   Daha fazla OMA-URI ayarı ekleyerek, birden çok ağ ve anahtar ekleyebilirsiniz.
-  iOS için, bir Mac istasyonunda profili kurmak üzere Apple Configurator’ı kullanın. Alternatif olarak, Johnathon Biersack tarafından sağlanan bu [iOS PSK Mobile Config Oluşturucu](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/)’yu kullanın.


1.  Android veya Windows için önceden paylaşılan anahtar ile bir Wi-Fi profili oluşturmak veya bir EAP tabanlı Wi-Fi profili oluşturmak için, ilke oluşturduğunuzda o cihaz platformu için Wi-Fi profili yerine **Özel Yapılandırma**’yı seçin.

2.  Bir ad ve açıklama sağlayın.
3.  Yeni bir OMA-URI ayarı ekleyin:

   a.   Bu Wi-Fi ağ ayarı için bir ad girin.

   b.   OMA-URI ayarı için bir açıklama girin veya boş bırakın.

   c.   **Veri Türü**: "String(XML)" olarak ayarlayın

   d.   **OMA-URI**:

    - **Android için**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Windows için**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Başına nokta karakterini eklediğinizden emin olun.

    SSID, ilkeyi oluşturmakta olduğunuz SSID’dir. Örneğin, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e. **Değer Alanı**, XML kodunuzu yapıştırdığınız yerdir. Bir örneğe bakalım. Her değer, ağ ayarlarınıza uyarlanmış olmalıdır. Bazı işaretçiler için kodun açıklamalar bölümüne bakın.
4. **Tamam**’ı seçin, ilkeyi kaydedin ve dağıtın.

    > [!NOTE]
    > Bu ilke yalnızca kullanıcı gruplarına dağıtılabilir.

Her cihaz daha sonra denetlediğinde, ilke uygulanır ve cihazda bir Wi-Fi profili oluşturulur. Cihaz ağa otomatik olarak bağlanabilecektir.
## <a name="android-or-windows-wi-fi-profile"></a>Android veya Windows Wi-Fi profili

Bir Android veya Windows Wi-Fi profili için XML kodu örneği aşağıdaki verilmiştir:

> [!IMPORTANT]
> 
> `<protected>false</protected>`, **false** olarak ayarlanmalıdır, çünkü **true** ayarı cihazın şifreli bir parola beklemesine ve bunun şifresini çözmeye çalışmasına neden olur; bunun sonucunda bağlantı başarısız olabilir.
> 
>  `<hex>53534944</hex>`, `<name><SSID of wifi profile></name>` onaltılı değerine ayarlanmalıdır.
>  Windows 10 cihazları yanlışlıkla *0x87D1FDE8 Düzeltme başarısız* hatasını döndürebilir, ancak yine de profille hazırlanır.

    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
    <hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
    -->
    <WLANProfile
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <hex>53534944</hex>
        <name><SSID of wifi profile></name>
        </SSID>
        <nonBroadcast>false</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication><Type of authentication></authentication>
            <encryption><Type of encryption></encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>

## <a name="eap-based-wi-fi-profile"></a>EAP tabanlı Wi-Fi profili
Bir EAP tabanlı Wi-Fi profili için bir XML kodu örneği aşağıdaki verilmiştir:

    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>XML dosyasını mevcut bir Wi-Fi bağlantısından oluşturun
Varolan bir Wi-Fi bağlantısından bir XML dosyası da oluşturabilirsiniz:
1. Kablosuz ağa bağlanmış veya bir kablosuz ağa yakın zamanda bağlanmış bir bilgisayarda şu klasörü açın: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\\{guid.

    Doğru olanı bulmak için her profili aramanız gerekeceğinden, çok sayıda kablosuz ağa bağlanmamış bir bilgisayar kullanmak en iyisidir.
3.     Doğru ada sahip olanı bulmak üzere XML dosyalarını arayın.
4.     Doğru XML dosyasını bulduktan sonra, XML kodunu kopyalayıp OMA-URI ayarlar sayfasının Veri alanına yapıştırın.

## <a name="deploy-the-policy"></a>İlkeyi dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'ı seçin.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**’i seçin.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


