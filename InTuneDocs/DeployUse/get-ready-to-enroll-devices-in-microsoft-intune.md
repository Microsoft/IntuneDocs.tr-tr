---
# required metadata

title: Cihazları kaydetmeye hazırlanma | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da cihazları kaydetmeye hazırlanma
Çalışanların mobil cihazları ([Android](set-up-android-management-with-microsoft-intune.md), [iOS ve Mac](set-up-ios-and-mac-management-with-microsoft-intune.md), [Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md) ve [Windows bilgisayarları](set-up-windows-device-management-with-microsoft-intune.md)) Intune’a kaydetmesine olanak sağlamak için, cihaz kaydını etkinleştirmeniz gerekir. Kayda izin vermek için, bir mobil cihaz yönetimi yetkilisi ayarlamanız, Intune Şirket Portalı’nı yapılandırmanız, lisanslar atamanız ve cihaz platformu için kaydı etkinleştirmeniz gerekir.

## Mobil cihaz yönetimi yetkilisini ayarlama
MDM yetkilisi, bir grup cihazı yönetme iznine sahip olan yönetim hizmetini tanımlar. MDM yetkilisi seçenekler arasında Intune’un kendisi ve Intune ile Configuration Manager vardır. Configuration Manager’ı yönetim yetkilisi olarak ayarlarsanız, mobil cihaz yönetimi için başka bir hizmet kullanılamaz.

>[!IMPORTANT]
> Mobil cihazları yalnızca Intune kullanarak mı (çevrimiçi hizmet) yoksa Intune ile System Center Configuration Manager kullanarak mı (çevrimiçi hizmetle birlikte şirket içi yazılım çözümü) yönetmek istediğinizi dikkatlice düşünün. Mobil cihaz yönetim yetkilisini ayarlandıktan sonra, bu değiştirilemez.



1.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi**’ni seçin.

2.  **Görevler** listesinde **Mobil Cihaz Yönetimi Yetkilisini Ayarla**öğesine tıklayın. **MDM Yetkilisini Ayarla** iletişim kutusu açılır.

    ![MDM yetkilisi ayarla iletişim kutusu](../media/intune-mdm-authority.png)

3.  Intune, Intune’u MDM yetkiliniz olarak isteyip istemediğinizi onaylamanızı ister. Mobil cihazları yönetmek için Microsoft Intune kullanmak istiyorsanız kutuyu işaretleyin ve ardından **Evet**'i seçin.

## Intune Şirket Portalı’nı yapılandırma

Intune Şirket Portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.

> [!TIP] Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, bir kiracı veya hizmet yöneticisi olarak [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) oturum açmanız, **Yönetici** &gt; **Şirket Portalı**’nı seçmeniz ve Şirket Portalı ayarlarını yapılandırmanız yeterli olur.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

#### Şirket iletişim bilgileri ve gizlilik bildirimi

Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Kullanıcılara kişi bilgileri ve ayrıntıları Şirket Portalı’nın BT’ye Başvur ekranında görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Şirket adı|40|Bu ad Şirket Portalı’nın başlığı olarak gösterilir.|
    |BT departmanı ilgili kişi adı|40|Bu ad **BT’ye Başvur**sayfasında gösterilir.|
    |BT departmanı telefon numarası|20|Bu iletişim numarası **BT'ye Başvur** sayfasında gösterilir.|
    |BT departmanı e-posta adresi|40|Bu iletişim adresi **BT'ye Başvur** sayfasında gösterilir. **diğerad@etkialanıadı.com** biçiminde geçerli bir e-posta adresi girmeniz gerekir.|
    |Ek bilgiler|120|**BT'ye Başvur** sayfasında gösterilir.|
    |Şirket gizlilik bildirimi URL'si|79|Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. https://www.contoso.com biçiminde geçerli bir URL girmelisiniz.|

#### Destek kişileri
Şirket Portalı’nda kullanıcılara, çevrimiçi desteğe erişebilmeleri için destek web sitesi gösterilir.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
    |----------|------------------------|----------------|
    |Destek web sitesi URL'si|150|Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, https://www.contoso.com biçiminde olmalıdır. Bir URL belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında destek web sitesi için hiçbir şey görünmez.|
    |Web sitesinin adı|40|Bu ad destek web sitesi URL'si için görüntülenen kolay addır. Bir destek web sitesi URL'si belirtir ve bir kolay ad belirtmezseniz, Şirket Portalı’ndaki **BT'ye Başvur** sayfasında **BT web sitesine gidin** ifadesi gösterilir.|


#### Şirket markasıyla özelleştirme

Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.

|Alan adı|Daha fazla bilgi|
    |----------|----------------|
    |Tema rengi|Şirket Portalı’na uygulamak için bir tema rengi seçin.|
    |Şirket logosunu ekle|Bu seçeneği etkinleştirdiğinizde, Şirket Portalınızda görüntülemek için şirket logonuzu yükleyebilirsiniz. İki logo yükleyebilirsiniz: birisi Şirket Portalı’nın arka planı beyaz olduğunda, diğeriyse Şirket Portalı arka planında seçilen Tema rengi kullanıldığında görüntülenir. Her logo .png veya .jpg dosya türünde olmalı, en yüksek çözünürlüğü 400 x 100 piksel olmalı ve boyutu 750 KB veya daha az olmalıdır.|
    |[!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Şirket Portalı uygulaması için bir arka plan seçin|Bu ayar yalnızca [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)] Şirket Portalı uygulamasını etkiler.|


Değişiklikleri kaydettikten sonra, Şirket Portalı web sitesini görüntülemek için yönetici konsolunun **Şirket Portalı** sayfasının sonunda sağlanan bağlantıları kullanabilirsiniz. Bu bağlantılar değiştirilemez. Bir kullanıcı oturum açtığında bu bağlantılar Şirket Portalı’ndaki aboneliklerinizi görüntüler.

## Intune kullanıcı lisansı atama

Bulut tabanlı kullanıcıları el ile eklemek ve hem bulut tabanlı kullanıcı hesaplarına hem de şirket içi Active Directory’nizden Azure AD’ye eşitlenen hesaplara lisans atamak için **Office 365 yönetim portalını** kullanırsınız.

1.  Kiracı yöneticisi kimlik bilgilerinizi kullanarak [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx) oturum açın.

2.  Intune kullanıcı lisansı atamak istediğiniz kullanıcı hesabını seçin ve kullanıcı hesabı özelliklerinde **Microsoft Intune** onay kutusunu etkinleştirin.

3.  Kullanıcı hesabı artık Microsoft Intune kullanıcı grubuna eklenir. Bu grup kullanıcıya hizmeti kullanmak ve cihazlarını yönetime kaydetmek için izinler verir.

## Cihaz yönetimi ayarlama
MDM yetkilisini ayarladıktan sonra, kuruluşunuzun desteklemek istediği işletim sistemleri için cihaz yönetimi ayarlamanız gerekir. Cihaz yönetimi ayarlamak için gerekli adımlar, işletim sistemine göre farklılık gösterir. Örneğin, Android işletim sistemi, Intune yönetim konsolunda herhangi bir şey yapmanızı gerektirmez. Diğer taraftan, Windows ve iOS, yönetime olanak sağlamak için cihazlar ve Intune arasında bir güven ilişkisi gerektirir.

> [!div class="op_single_selector"]
- [Microsoft Intune ile Android yönetimini ayarlama](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Microsoft Intune ile Windows Phone yönetimin ayarlama](set-up-windows-phone-management-with-microsoft-intune.md)
- [Microsoft Intune ile Windows cihazı yönetimini ayarlama](set-up-windows-device-management-with-microsoft-intune.md)

Ayrıca şunları yapabilirsiniz:
 - Birçok cihaz kaydetmek için, [cihaz kaydı yöneticisi hesabını](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) kullanabilirsiniz
 - Cihazları kaydetmeye ve hedef ilkeye yardımcı olmak için [IMEI numaraları kullanarak şirkete ait cihazlar belirtebilirsiniz](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=Jun16_HO1-->


