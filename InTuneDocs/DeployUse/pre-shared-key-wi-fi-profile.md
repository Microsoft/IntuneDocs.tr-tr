---
title: PSK Kullanarak Wi-Fi | Microsoft Intune
description: "Önceden paylaşılan anahtarla Wi-Fi profili oluşturmak için Özel Yapılandırma’yı kullanın."
keywords: 
author: nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: afdd0c3569c0c294a9bef47755de2d9e77e7507d



---
# Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma
Intune'un **Özel Yapılandırmasını**, önceden paylaşılan anahtar ile Wi-Fi profili oluşturmak üzere kullanma Bu konuda, bir EAP tabanlı Wi-Fi profili oluşturmaya bir örnek de yer almaktadır.

Not:
-   Aşağıda açıklandığı gibi bu ağa bağlanan bir bilgisayardan kodu kopyalamak size daha kolay gelebilir.
- Android için, Johnathon Biersack tarafından sağlanan bu [Android PSK Oluşturucu](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/)’yu kullanma seçeneğiniz de vardır.
-   Daha fazla OMA-URI ayarı ekleyerek, birden çok ağ ve anahtar ekleyebilirsiniz.
-  iOS için, Apple Configurator’u bir Mac istasyonunda profil yapılandırmak için kullanın. Alternatif olarak, Johnathon Biersack tarafından sağlanan bu [iOS PSK Mobile Config Oluşturucu](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/)’yu kullanın.


1.  Android veya Windows için önceden paylaşılan anahtar ile bir Wi-Fi profili oluşturmak için veya bir EAP tabanlı Wi-Fi profili oluşturmak için, bir ilke oluşturduğunuzda o cihaz platformu için, bir Wi-Fi profili yerine **Özel Yapılandırma** seçin.

2.  Bir ad ve açıklama sağlayın.
3.  Yeni bir OMA-URI ayarı ekleyin:

   a.   Bu Wi-Fi ağ ayarı için bir ad girin.

   b.   OMA-URI ayarı için bir açıklama girin veya boş bırakın.

   c.   **Veri Türü**: "String(XML)" olarak ayarlayın

   d.   **OMA-URI**: ./Vendor/MSFT/Wi-Fi /Profile/<SSID>/Settings

Not: Başına nokta karakterini eklediğinizden emin olun.

SSID, ilkeyi oluşturmakta olduğunuz SSID’dir. Örneğin,
`./Vendor/MSFT/Wi-Fi/Profile/Hotspot-1/Settings`

  e.    Değer Alanı: buraya XML kodunuzu yapıştırırsınız. Bir örneğe bakalım. Her değer, ağ ayarlarınıza uyarlanmış olmalıdır. Bazı işaretçiler için kodun açıklamalar bölümüne bakın.


    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
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

## EAP tabanlı Wi-Fi profili
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

4.  Tamam’a tıklayın, ardından ilkeyi kaydedin ve dağıtın.
NOT. Bu ilke yalnızca kullanıcı gruplarına dağıtılabilir

Her cihaz daha sonra denetlediğinde, ilke uygulanır ve cihazda bir Wi-Fi profili oluşturulur. Cihaz ağa otomatik olarak bağlanabilecektir.
## XML dosyasını mevcut bir Wi-Fi bağlantısından oluşturun
Varolan bir Wi-Fi bağlantısından bir XML dosyası da oluşturabilirsiniz:
1.     Kablosuz ağa bağlanmış veya bir kablosuz ağa yakın zamanda bağlanmış bir bilgisayarda şu klasörü açın: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\\{guid. Doğru olanı bulmak için her profili aramanız gerekeceğinden, birçok kablosuz ağa bağlanmamış bir bilgisayar kullanmak en iyisidir.
3.     Doğru ada sahip olanı bulmak üzere XML dosyalarını arayın.
4.     Doğru XML dosyasını bulduktan sonra, XML kodunu kopyalayıp OMA-URI ayarlar sayfasının Veri alanına yapıştırın.

## İlkeyi dağıtma

1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

### Ayrıca bkz.
[Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


