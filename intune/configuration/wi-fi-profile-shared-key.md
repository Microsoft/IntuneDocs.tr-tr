---
title: Microsoft Intune-Azure 'da önceden paylaşılan anahtarla WiFi profili oluşturma | Microsoft Docs
description: Önceden paylaşılan bir anahtarla Wi-Fi profili oluşturmak için özel bir profil kullanma ve Microsoft Intune'da Android, Windows ve EAP tabanlı Wi-Fi profilleri için örnek XML kodu alma
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9b56ba1515608afb6c2a0d151f5412711d49e57
ms.sourcegitcommit: 5ad0ce27a30ee3ef3beefc46d2ee49db6ec0cbe3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76886707"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key-in-intune"></a>Intune 'da önceden paylaşılan anahtarla bir WiFi profili oluşturmak için özel cihaz profili kullanma



Önceden paylaşılan anahtarlar (PSK) genellikle WiFi ağlarında veya kablosuz LAN 'Larda kullanıcıların kimliğini doğrulamak için kullanılır. Intune ile önceden paylaşılan bir anahtar kullanarak bir WiFi profili oluşturabilirsiniz. Profili oluşturmak için Intune’daki **Özel cihaz profilleri** özelliğini kullanın. Bu makalede ayrıca, EAP tabanlı bir Wi-Fi profilinin nasıl oluşturulacağına ilişkin bazı örnekler yer alır.

Bu özellik şunları destekler:

- Android Cihaz Yöneticisi
- Windows
- EAP tabanlı Wi-Fi

> [!IMPORTANT]
> - Windows 10 ile önceden paylaşılan bir anahtar kullanılması, Intune 'da bir düzeltme hatasına neden olur. Bu durumda, Wi-Fi profili cihaza düzgün bir şekilde atanır ve profil beklendiği gibi çalışır.
> - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız dosyanın korumalı olduğundan emin olun. Anahtar düz metin biçimindedir, yani anahtarı korumak sizin sorumluluğunuzdadır.

## <a name="before-you-begin"></a>Başlamadan önce

- Kodu, bu makalenin sonraki bölümlerinde açıklandığı gibi, o ağa bağlanan bir bilgisayardan kopyalamak daha kolay olabilir.
- Daha fazla OMA-URI ayarı ekleyerek, birden çok ağ ve anahtar ekleyebilirsiniz.
- iOS için, bir Mac istasyonunda profili kurmak üzere Apple Configurator’ı kullanın.
- PSK 64 onaltılık rakamdan oluşan bir dize veya 8 ile 63 arası yazdırılabilir ASCII karakterden oluşan bir parola gerektirir. Yıldız işareti (*) gibi bazı karakterler desteklenmez.

## <a name="create-a-custom-profile"></a>Özel profil oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir ilke adı, **Android cihazlar Için özel OMA-URI Wi-Fi profili ayarlarıdır**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: platformunuzu seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Ayarlar**' da **Ekle**' yi seçin. Aşağıdaki özelliklerle yeni bir OMA-URI ayarı girin:

    1. **Ad**: OMA-URI ayarı için bir ad girin.
    2. **Açıklama**: OMA-URI ayarı için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    3. **OMA-URI**: aşağıdaki seçeneklerden birini girin:

        - **Android için**: `./Vendor/MSFT/WiFi/Profile/SSID/Settings`
        - **Windows için**: `./Vendor/MSFT/WiFi/Profile/SSID/WlanXml`

        > [!NOTE]
        > Başına nokta karakterini eklediğinizden emin olun.

        SSID, ilkeyi oluşturmakta olduğunuz SSID’dir. Örneğin, Wi-Fi adı `Hotspot-1`, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`girin.

    4. **Veri türü**: **dize**seçin.

    5. **Değer**: xml kodunuzu yapıştırın. Bu makaledeki [örneklere](#android-or-windows-wi-fi-profile-example) bakın. Her bir değeri ağ ayarlarınıza uyacak şekilde güncelleştirin. Kodun açıklamalar bölümü bazı işaretçiler içerir.

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profiliniz profiller listesinde gösterilir. Sonra, [Bu profili](../device-profile-assign.md) Kullanıcı gruplarınıza atayın. Bu ilke yalnızca kullanıcı gruplarına atabilir.

Cihazların bir sonraki iadesinde, ilke uygulanır ve cihazda bir Wi-Fi profili oluşturulur. Cihaz daha sonra ağa otomatik olarak bağlanabilir.

## <a name="android-or-windows-wi-fi-profile-example"></a>Android veya Windows Wi-Fi profili örneği

Aşağıdaki örnek bir Android veya Windows Wi-Fi profili için XML kodu örneği içerir. Doğru biçimi göstermek ve ayrıntı sağlamak için örnek gösterilmiştir. Bu yalnızca bir örnektir ve ortamınız için önerilen yapılandırma olarak verilmemiştir.

### <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- `<protected>false</protected>`, **false** olarak ayarlanmalıdır. **true** olarak ayarlandığında, cihazın şifreli bir parola beklemesine ve bunun şifresini çözmeye çalışmasına neden olur; bu da başarısız bağlantıyla sonuçlanabilir.

- `<hex>53534944</hex>`, `<name><SSID of wifi profile></name>` onaltılı değerine ayarlanmalıdır. Windows 10 cihazları yanlış bir `x87D1FDE8 Remediation failed` hatası döndürebilir, ancak cihaz hala profili içerir.

- XML 'de `&` (ampersan) gibi özel karakterler vardır. Özel karakterlerin kullanılması, XML 'nin beklenen şekilde çalışmasını engelleyebilir. 

### <a name="example"></a>Örnek

``` xml
<!--
<hex>53534944</hex> = The hexadecimal value of <name><SSID of wifi profile></name>
<Name of wifi profile> = Name of profile shown to users. It could be <name>Your Company's Network</name>.
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped. It could be <name>Your Company's Network</name>.
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network, such as AES.
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Plain text of the password to connect to the network
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
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

### <a name="eap-based-wi-fi-profile-example"></a>EAP tabanlı Wi-Fi profili örneği
Aşağıdaki örnekte EAP tabanlı Wi-Fi profili için XML kodu verilmiştir: Doğru biçimi göstermek ve ayrıntı sağlamak için örnek gösterilmiştir. Bu yalnızca bir örnektir ve ortamınız için önerilen yapılandırma olarak verilmemiştir.


```xml
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
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>XML dosyasını mevcut bir Wi-Fi bağlantısından oluşturun

Ayrıca, var olan bir Wi-Fi bağlantısından bir XML dosyası da oluşturabilirsiniz. Bir Windows bilgisayarda aşağıdaki adımları kullanın:

1. C:\WiFi. gibi, dışarıya aktarılmış W-Fi profilleri için yerel bir klasör oluşturun
2. Yönetici olarak bir komut istemi açın ( **yönetici olarak çalıştır** > `cmd`sağ tıklayın).
3. `netsh wlan show profiles`'i çalıştırın. Tüm profillerin adları listelenir.
4. `netsh wlan export profile name="YourProfileName" folder=c:\Wifi`'i çalıştırın. Bu komut, c:\Wifi. içinde `Wi-Fi-YourProfileName.xml` adlı bir dosya oluşturur

    - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız komuta `key=clear` ekleyin:
  
        `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

        `key=clear`, profili başarılı bir şekilde kullanmak için gereken anahtarı düz metin olarak dışarı aktarır.

XML dosyasına sahip olduktan sonra, XML sözdizimini kopyalayıp OMA-URI ayarları > **veri türü**' ne yapıştırın. [Özel bir profil oluşturma](#create-a-custom-profile) (Bu makalede) adımları listeler.

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` tüm profilleri XML biçiminde de içerir.

## <a name="best-practices"></a>Önerilen uygulamalar

- PSK ile bir Wi-Fi profili dağıtmadan önce cihazın uç noktaya doğrudan bağlanabildiğini doğrulayın.

- Anahtarları (parolalar veya parola) döndürdükten sonra kapalı kalma süresi ve dağıtımlarınızı planlayın. Yeni Wi-Fi profillerini çalışma saatleri dışında itmeyi düşünebilirsiniz. Ayrıca, bağlantıyı etkileyebilecek kullanıcıları uyarın.

- Kesintisiz geçiş için, Son Kullanıcı cihazının Internet 'e alternatif bir bağlantısı olduğundan emin olun. Örneğin, Son Kullanıcı Konuk WiFi (veya başka bir WiFi ağına) geri dönebilir veya Intune ile iletişim kurmak için hücresel bağlantı kurabilir. Bu ek bağlantı, cihazda şirket WiFi Profili güncelleştirilirken kullanıcının ilke güncelleştirmeleri almasını sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atadığınızdan](device-profile-assign.md)emin olun ve durumunu [izleyin](device-profile-monitor.md) .
