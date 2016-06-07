---
# required metadata

title: Şirket İçi Exchange için Microsoft Intune Exchange bağlayıcısını yükleme | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune Şirket İçi Exchange Bağlayıcısı’nı yükleme


Microsoft Intune’la mobil cihazların posta kutularını barındıran Exchange Server'ın iletişim kurmasını sağlayan bir bağlantı ayarlamak için, Intune yönetici konsolundan Şirket İçi Bağlayıcı aracını indirip yapılandırmanız gerekir.

## Şirket İçi Bağlayıcı Gereksinimleri
Aşağıdaki tabloda Şirket İçi Exchange Bağlayıcısı’nı yüklediğiniz bilgisayara ilişkin gereksinimler listelenmiştir.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemleri|Intune; Windows Server 2008 SP2 64 bit, Windows Server 2008 R2, Windows Server 2012 veya Windows Server 2012 R2’nin herhangi bir sürümünü çalıştıran bilgisayarlarda Şirket İçi Exchange Bağlayıcısı’nı destekler.<br /><br />Bağlayıcı hiçbir Sunucu Çekirdeği yüklemesinde desteklenmez.|
|Microsoft Exchange sürümü|Şirket İçi Bağlayıcı, Microsoft Exchange 2010 SP1 veya üstünü gerektirir.|
|Mobil cihaz yönetimi yetkilisi| Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama|
|Donanım|Bağlayıcıyı yüklediğiniz bilgisayar 2 GB ram ve 10 GB boş disk alanı en düşük donanımı ile birlikte 1,6 GHz CPU gerektirir.|
|Active Directory Eşitlemesi|Intune’u Exchange Server'a bağlamak üzere herhangi bir bağlayıcıyı kullanabilmeniz için, yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenebilmesi amacıyla [Active Directory eşitlemesini](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) ayarlamanız gerekir.|
|Ek yazılım|Bağlayıcıyı barındıran bilgisayara Microsoft .NET Framework 4 ve Windows PowerShell 2.0 tam yüklemesi yapılmalıdır.|
|Ağ|Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, 80 ve 443 numaralı Bağlantı Noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesine olanak sağlayacak yapılandırmalar gerektirir. Intune tarafından kullanılan etki alanları manage.microsoft.com, &#42;manage.microsoft.com ve &#42;.manage.microsoft.com’dur.|
|Barındırılan Exchange yapılandırılmış ve çalışıyor|Daha fazla bilgi için bkz. [Exchange Server 2016](https://technet.microsoft.com/library/mt170645.aspx). |
|Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama|[Mobil cihaz yönetimi yetkiliniz olarak Intune’u ayarlama](get-ready-to-enroll-devices-in-microsoft-intune.md#BKMK_Set_MDM_Authority)|

### Exchange cmdlet gereksinimleri

Intune Exchange Bağlayıcısı tarafından kullanılacak bir Active Directory kullanıcı hesabı oluşturmanız gerekir. Hesabın aşağıdaki gerekli Windows PowerShell Exchange cmdlet'lerini çalıştırma izni olması gerekir:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## Şirket İçi Exchange Bağlayıcısı yazılım yükleme paketini indirme

1. Şirket İçi Exchange Bağlayıcısı için desteklenen bir işletim sisteminde, Exchange kiracısında yönetici olan ve Exchange Server’ı kullanma lisansı bulunan bir kullanıcı hesabıyla [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) (http://manage.microsoft.com) açın.
![Exchange Bağlantısını Ayarla sayfasını açın](../media/ExchangeConnector.gif)

2.  Çalışma alanı kısayolları bölmesinde **YÖNETİCİ**'yi seçin.

3.  Gezinti bölmesindeki **Mobil Cihaz Yönetimi**’nin altında **Microsoft Exchange**'i genişletin ve ardından **Exchange Bağlantısı Ayarla**'yı seçin.

4.  **Exchange Bağlantısı Ayarla** sayfasında **Şirket İçi Bağlayıcıyı İndir**'i seçin.

5.  Şirket İçi Exchange Bağlayıcısı, açılabilen veya kaydedilebilen sıkıştırılmış (.zip) bir klasörde yer alır. **Dosya İndirme** iletişim kutusunda **Kaydet**'i seçerek sıkıştırılmış klasörü güvenli bir konuma depolayın.

> [!IMPORTANT]
> Şirket İçi Exchange Bağlayıcısı klasöründeki dosyaları yeniden adlandırmayın veya taşımayın. Klasörün içeriğini taşımak veya yeniden adlandırmak, yüklemenin çalışmamasına neden olur.

## Intune Şirket İçi Exchange Bağlayıcısı’nı yükleme ve yapılandırma
Intune Şirket İçi Exchange Bağlayıcısı'nı yüklemek için aşağıdaki adımları gerçekleştirin. Şirket İçi Exchange Bağlayıcısa, Intune aboneliği başına yalnızca bir kez ve yalnızca bir bilgisayara yüklenebilir. Bir Şirket İçi Exchange Bağlayıcısı daha yapılandırmayı denerseni, yeni bağlantı ilkinin yerini alır.

1.  Şirket İçi Bağlayıcı için desteklenen işletim sistemlerinden birinde, **Exchange_Connector_Setup.zip** içindeki dosyaları güvenli bir konuma ayıklayın.

2.  Dosyalar ayıklandıktan sonra, Şirket İçi Bağlayıcı'yı yüklemek için ayıklanan klasörü açın ve **Exchange_Connector_Setup.exe** dosyasına çift tıklayın.

    > Hedef klasör güvenli bir konum değilse, Şirket İçi Bağlayıcı'yı yükledikten sonra **WindowsIntune.accountcert** sertifika dosyasını silmelisiniz.

3.  **Exchange sunucusu** alanında **Şirket İçi Microsoft Exchange Server** ve **Barındırılan Microsoft Exchange Server** arasından Exchange sunucusu ortam türünüzü seçin.

  ![Exchange Server türünü seçin](../media/IntuneSA1dconfigureExchConnector.png)

  Şirket içi Exchange sunucusu için, **İstemci Erişimi Sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

  Barındırılan bir Exchange sunucusu için, Exchange sunucusunun adresini belirtin. Barındırılan Exchange sunucusunun URL'sini bulmak için:

      1.  Office 365 için Outlook Web App'i açın.

      2.  Sol üst kısımdaki “?” simgesini seçin ve **Hakkında**’yı seçin.

      3.   **POP Dış Sunucu** değerini bulun.

      4.  Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.
        1.  **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

        2.  Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

        3.  Proxy sunucusuna erişmek için kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, Proxy sunucusuna bağlanmak için kimlik bilgilerini kullan'ı seçin, ardından **etkialanı\kullanıcı** ve **parola** girin.

        4.  **Tamam**’ı seçin.

5.  Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini (**Kullanıcı (Etki alanı/kullanıcı)** ve **Parola**) sağlayın.

6.  Kullanıcıların Exchange posta kutularına bildirim göndermek için gereken yönetici kimlik bilgilerini sağlayın. Bu bildirimler Intune kullanılarak Koşullu Erişim ilkeleriyle yapılandırılabilir.

    Otomatik Bulma hizmeti ve Exchange Web Hizmetleri'nin Exchange İstemci Erişimi Sunucusu'nda yapılandırıldığından emin olun. Bu konu hakkında daha fazla bilgi için bkz. [İstemci Erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

7.  **Parola** alanında, Intune’un Exchange Server'a erişmesini etkinleştirmek için bu hesabın parolasını sağlayın.

8. **Bağlan**’ı seçin.

    Bağlantının ayarlanması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange Bağlayıcısı İnternet erişimini sağlamak için proxy ayarlarınızı depolar. Proxy ayarlarınız değişirse, güncelleştirilen proxy ayarlarını Exchange Bağlayıcısı’na uygulamak için Exchange Bağlayıcısı’nı yeniden yapılandırmanız gerekir.

Exchange Bağlayıcısı bağlantıyı ayarladıktan sonra, Exchange Bağlayıcısı’nda yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange Bağlayıcısı’na eklenir. Bu eşitlemenin tamamlanması biraz sürebilir.

> Şirket İçi Exchange Bağlayıcısı'nı yüklediyseniz ve ileride Exchange bağlantısını silerseniz, Şirket İçi Exchange Bağlayıcısı'nı yüklü olduğu bilgisayardan kaldırmanız gerekir.

## Exchange bağlantısını doğrulama

Exchange Bağlayıcısı’nı başarıyla yapılandırdıktan sonra, bağlantının durumunu ve son başarılı eşitleme girişimini görüntüleyebilirsiniz. [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **YÖNETİCİ** çalışma alanını seçin ve **Mobil Cihaz Yönetimi**’nin altında **Microsoft Exchange**’i seçin. Ardından, sağladığınız ayrıntıların **Exchange Bağlantı Bilgileri** altında gösterildiğini doğrulayın.


Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.


<!--HONumber=May16_HO2-->

