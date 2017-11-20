---
title: "Şirket içi EAS için Exchange bağlayıcısını Intune ile ayarlama"
titleSuffix: Azure portal
description: "Bağlayıcı aracını kullanarak Intune ve şirket içi Exchange Server arasında iletişimi etkinleştirme"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c7947c9d047c6f206f9f93c389d418379fe8267a
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2017
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Microsoft Intune Azure’da Intune şirket içi Exchange Bağlayıcısını ayarlama

Şirket içi Exchange Server ortamları, cihazların Intune’a kayıtlı olup olmamasına ve Intune cihaz uyumluluk ilkelerine uyup uymamasına bağlı olarak şirket içi Exchange posta kutularına erişen cihazları yönetmek için Intune şirket içi Exchange bağlayıcısını kullanabilir. Şirket içi Exchange bağlayıcısı, Intune ile mevcut Exchange Active Sync (EAS) kaydını eşitleyerek şirket içi Exchange sunucularına bağlanan mobil cihazları bulmaktan da sorumludur.

> [!IMPORTANT]
> Intune, abonelik başına herhangi bir türde tek bir şirket içi Exchange Connector bağlantısını destekler.

Microsoft Intune’un şirket içi Exchange Server ile iletişim kurmasını sağlayan bir bağlantı ayarlamak için aşağıdaki adımları izlemeniz gerekir:

1.  Intune şirket içi Exchange Connector’ı Azure portalından indirin.
2.  Intune şirket içi Exchange bağlayıcısını yükleyin ve yapılandırın.
3.  Exchange bağlantısını doğrulayın.

## <a name="on-premises-exchange-connector-requirements"></a>Şirket içi Exchange Connector gereksinimleri
Aşağıdaki tabloda Şirket İçi Exchange Connector’ı yüklediğiniz bilgisayara ilişkin gereksinimler listelenmiştir.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemleri|Intune; Windows Server 2008 SP2 64 bit, Windows Server 2008 R2, Windows Server 2012 veya Windows Server 2012 R2’nin herhangi bir sürümünü çalıştıran bilgisayarlarda Şirket İçi Exchange Connector’ı destekler.<br /><br />Bağlayıcı hiçbir Sunucu Çekirdeği yüklemesinde desteklenmez.|
|Microsoft Exchange|Şirket içi Bağlayıcılar için Microsoft Exchange 2010 SP1 veya üzeri ya da eski Exchange Online Dedicated gerekir. Exchange Online Dedicated ortamınızın **yeni** yapılandırmada mı yoksa **eski** yapılandırmada mı olduğunu belirlemek için hesap yöneticinize başvurun.|
|Mobil cihaz yönetimi yetkilisi| [Mobil cihaz yönetimi yetkilisi olarak Intune’u ayarlama](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Donanım|Bağlayıcıyı yüklediğiniz bilgisayar 2 GB RAM ve 10 GB boş disk alanı ile birlikte 1,6 GHz CPU gerektirir.|users-add.md
|Active Directory eşitlemesi|Intune’u Exchange Server'a bağlamak üzere Bağlayıcıyı kullanabilmeniz için yerel kullanıcılarınızın ve güvenlik gruplarınızın Azure Active Directory örneğinizle eşitlenebilmesi amacıyla [Active Directory eşitlemesini](users-add.md) ayarlamanız gerekir.|
|Ek yazılım|Bağlayıcıyı barındıran bilgisayara Microsoft .NET Framework 4.5 ve Windows PowerShell 2.0 tam yüklemesi yapılmalıdır.|
|Ağ|Bağlayıcıyı yüklediğiniz bilgisayar, Exchange Server'ı barındıran etki alanı ile güven ilişkisi olan bir etki alanında olmalıdır.<br /><br />Bilgisayar, 80 ve 443 numaralı Bağlantı Noktaları üzerinden güvenlik duvarları ve proxy sunucular aracılığıyla Intune hizmetine erişmesine olanak sağlayacak yapılandırmalar gerektirir. Intune tarafından kullanılan etki alanları manage.microsoft.com, &#42;manage.microsoft.com ve &#42;.manage.microsoft.com’dur.|


### <a name="exchange-cmdlet-requirements"></a>Exchange cmdlet gereksinimleri

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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Şirket İçi Exchange Connector yazılım yükleme paketini indirme

1. Şirket İçi Exchange Connector için desteklenen bir Windows Server işletim sisteminde [Azure Portal](http://portal.azure.com)’ı açın ve şirket içi Exchange sunucusunda yönetici olan ve Exchange Server’ı kullanma lisansı bulunan bir kullanıcı hesabıyla oturum açın.

2. Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune**’u seçin, Intune Panosu açılır; **Şirket içi erişim**’i seçin.

4. **Şirket içi erişim - Exchange ActiveSync bağlayıcısı** dikey penceresinde, **Kurulum** bölümünden, **Şirket içi bağlayıcıyı indir**’i seçin.

5.  Şirket İçi Exchange Connector, açılabilen veya kaydedilebilen sıkıştırılmış (.zip) bir klasörde yer alır. **Dosya İndirme** iletişim kutusunda **Kaydet**'i seçerek sıkıştırılmış klasörü güvenli bir konuma depolayın.

    > [!IMPORTANT]
    > Şirket İçi Exchange Connector klasöründeki dosyaları yeniden adlandırmayın veya taşımayın. Klasörün içeriğini taşımak veya yeniden adlandırmak, Exchange Connector yüklemesinin başarısız olmasına neden olur.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Intune Şirket İçi Exchange Connector’ı yükleme ve yapılandırma
Intune Şirket İçi Exchange Connector'ı yüklemek için aşağıdaki adımları gerçekleştirin. Şirket İçi Exchange Connector, Intune aboneliği başına yalnızca bir kez ve yalnızca bir bilgisayara yüklenebilir. Bir Şirket İçi Exchange Connector daha yapılandırmayı denerseniz, yeni bağlantı ilkinin yerini alır.

1.  Şirket İçi Bağlayıcı için desteklenen işletim sistemlerinden birinde, **Exchange_Connector_Setup.zip** içindeki dosyaları güvenli bir konuma ayıklayın.

2.  Dosyalar ayıklandıktan sonra, Şirket İçi Exchange Connector'ı yüklemek için ayıklanan klasörü açın ve **Exchange_Connector_Setup.exe** dosyasına çift tıklayın.

    > [!IMPORTANT]
    > Hedef klasör güvenli bir konum değilse, Şirket İçi Bağlayıcı'yı yükledikten sonra **WindowsIntune.accountcert** sertifika dosyasını silmelisiniz.

3.  **Microsoft Intune Exchange Connector** iletişim kutusunda, **Şirket içi Microsoft Exchange Server** veya **Barındırılan Microsoft Exchange Server** seçeneklerinden birini belirleyin.

  ![Exchange Server türünü seçin](./media/intune-sa-exchange-connector-config.png)

  Şirket içi Exchange sunucusu için **İstemci Erişimi Sunucu** rolünü barındıran Exchange sunucusunun sunucu adını veya tam etki alanı adını belirtin.

  Barındırılan bir Exchange sunucusu için, Exchange sunucusunun adresini belirtin. Barındırılan Exchange sunucusunun URL'sini bulmak için:

    1. Office 365 için Outlook Web App'i açın.

    2. Sol üst taraftaki **?** simgesini ve ardından **Hakkında**’yı seçin.

    3. **POP Dış Sunucu** değerini bulun.

    4. Barındırılan Exchange sunucunuzun proxy sunucusu ayarlarını belirtmek için **Proxy Sunucusu**'nu seçin.
        1. **Mobil cihaz bilgileri eşitlenirken proxy sunucusu kullan**'ı seçin.

        2. Sunucuya erişmek için kullanılan **proxy sunucusu adı** ve **bağlantı noktası numarasını** belirtin.

        3. Proxy sunucusuna erişmek için kullanıcı kimlik bilgilerinin sağlanması gerekiyorsa, **Proxy sunucusuna bağlanmak için kimlik bilgilerini kullan**'ı seçin. Ardından **etki alanı\kullanıcı** ve **parola** girin.

        4. **Tamam**’ı seçin.

    5. **Kullanıcı (Etki alanı\kullanıcı)** ve **Parola** alanlarında Exchange sunucunuza bağlanmak için gereken kimlik bilgilerini sağlayın.

    6.  Kullanıcıların Exchange Server posta kutularına bildirim göndermek için gereken yönetici kimlik bilgilerini sağlayın. Bu bildirimleri Intune’da Koşullu Erişim ilkeleriyle yapılandırabilirsiniz.

        Otomatik Bulma hizmeti ve Exchange Web Hizmetleri'nin Exchange İstemci Erişimi Sunucusu'nda yapılandırıldığından emin olun. Daha fazla bilgi için bkz. [İstemci Erişimi sunucusu](https://technet.microsoft.com/library/dd298114.aspx).

    7.  **Parola** alanında, Intune’un Exchange Server'a erişmesini etkinleştirmek için bu hesabın parolasını sağlayın.

    8. **Bağlan**’ı seçin.

    > [!NOTE]
    > Bağlantının yapılandırılması birkaç dakika sürebilir.

Yapılandırma sırasında Exchange Bağlayıcısı İnternet erişimini sağlamak için proxy ayarlarınızı depolar. Proxy ayarlarınız değişirse, güncelleştirilen proxy ayarlarını Exchange Connector’a uygulamak için Exchange Connector’ı yeniden yapılandırmanız gerekir.

Exchange Connector bağlantıyı ayarladıktan sonra, Exchange Connector’da yönetilen kullanıcılarla ilişkili mobil cihazlar otomatik olarak eşitlenir ve Exchange Connector’a eklenir. Bu eşitlemenin tamamlanması biraz sürebilir.

> [!NOTE]
> Şirket İçi Exchange Connector'ı yüklediyseniz ve ileride Exchange bağlantısını silerseniz, Şirket İçi Exchange Connector'ı yüklü olduğu bilgisayardan kaldırmanız gerekir.

## <a name="monitor-the-exchange-connector-activity"></a>Exchange bağlayıcısı etkinliğini izleme

Exchange Bağlayıcısı’nı başarıyla yapılandırdıktan sonra, bağlantının durumunu ve son başarılı eşitleme girişimini görüntüleyebilirsiniz. Exchange Connector bağlantısını doğrulamak için:

1. Intune Panosu’nda, **Şirket içi erişim**’i seçin.
2. **Yönet** altında, **şirket içi Exchange erişimi**’ni seçerek bağlantı durumunu doğrulayın.

Ayrıca son başarılı eşitleme denemesinin tarih ve saatini kontrol edebilirsiniz.

### <a name="system-center-operations-manager-scom-management-pack"></a>System Center Operations Manager (SCOM) yönetim paketi

Intune 1710 sürümünden itibaren [Exchange bağlayıcısı ve Intune için SCOM yönetim paketi](https://www.microsoft.com/en-us/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True) kullanabilirsiniz. Bu yönetim paketi, sorun gidermeniz gerektiğinde Exchange bağlayıcısını izlemek için size farklı yollar sunar.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](conditional-access-exchange-create.md)
