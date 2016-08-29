---
title: "Cihazları kaydetme | Microsoft Intune"
description: "Mobil cihaz yönetimi (MDM), kaydı, cihazları yönetime getirmek ve kaynaklara erişim izni vermek için kullanır."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7bea7ba4ef59c6b1400414b59456e19dc1c152fb
ms.openlocfilehash: 41c21da7c95ef15f817aa344aa5b2d6479b65922


---

# Cihazları yönetim için Intune’a kaydetme
Microsoft Intune mobil cihaz yönetimi (MDM), cihazları yönetime getirmek ve kaynaklara erişim izin vermek için, kayıt olma kullanır. Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve gereken yönetim seviyesine bağlıdır. "Kendi cihazını getir" (BYOD) ve şirkete ait cihaz (COD) senaryoları bir kayıt işlemi gerektirir. Şirket içinde veya bulutta barındırılan Exchange ActiveSync kullanan kuruluşlar, kayıt gereksinimleri olmadan daha hafif yönetim etkinleştirebilir. Windows bilgisayarlar, Intune istemci yazılımı kullanılarak da yönetilebilir.

###  Desteklenen cihaz platformları

Intune aşağıdaki cihaz platformlarını yönetebilir:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Mobil cihaz yönetimi yetkilisini ayarlama
MDM yetkilisi, bir grup cihazı yönetme iznine sahip olan yönetim hizmetini tanımlar. MDM yetkilisi seçenekleri arasında Intune’un kendisi ve Intune ile Configuration Manager vardır. Configuration Manager’ı yönetim yetkilisi olarak ayarlarsanız, mobil cihaz yönetimi için başka bir hizmet kullanılamaz.

>[!IMPORTANT]
> Mobil cihazları yalnızca Intune kullanarak mı (çevrimiçi hizmet) yoksa Intune ile System Center Configuration Manager kullanarak mı (çevrimiçi hizmetle birlikte şirket içi yazılım çözümü) yönetmek istediğinizi dikkatle düşünün. Mobil cihaz yönetim yetkilisini ayarlandıktan sonra, bu değiştirilemez.

1.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi**’ni seçin.

2.  **Görevler** listesinde **Mobil Cihaz Yönetimi Yetkilisini Ayarla**öğesine tıklayın. **MDM Yetkilisini Ayarla** iletişim kutusu açılır.

    ![MDM yetkilisi ayarla iletişim kutusu](../media/intune-mdm-authority.png)

3.  Intune, Intune’u MDM yetkiliniz olarak isteyip istemediğinizi onaylamanızı ister. Mobil cihazları yönetmek için Microsoft Intune kullanmak istiyorsanız onay kutusunu işaretleyin ve ardından **Evet**'i seçin.

## Intune Şirket Portalı’nı yapılandırma

Intune Şirket Portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir.

> [!TIP]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur.

Şirket Portalı’nı özelleştirmek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlamaya yardımcı olur. Bunu yapmak için, bir kiracı veya hizmet yöneticisi olarak [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) oturum açmanız, **Yönetici** &gt; **Şirket Portalı**’nı seçmeniz ve Şirket Portalı ayarlarını yapılandırmanız yeterli olur.

![admin-console-admin-workspace-comp-portal-settings](../media/cp_sa_cpsetup.PNG)

## Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda kuruluşa ait cihaz kayıt yöntemleri ve bunların avantajları gösterilir.

**iOS Kayıt Yöntemleri**

| **Yöntem** |  **[Silme](#Wipe)** | **[Benzeşim](#Affinity)**   |   **[Kilitli](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Hayır|    Evet |   Hayır |
|**[DEM](#DEM)**|   Hayır |Hayır |Hayır  |
|**[DEP](#DEP)**|   Evet |   Seçenek |   Seçenek|
|**[USB-SA](#USB-SA)**| Evet |   Seçenek |   Hayır|
|**[USB-Direct](#USB-Direct)**| Hayır |    Hayır  | Hayır|

**Windows ve Android Kayıt Yöntemleri**

| **Yöntem** |  **[Silme](#Wipe)** | **[Benzeşim](#Affinity)**   |   **[Kilitli](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Hayır|    Evet |   Hayır |
|**[DEM](#DEM)**|   Hayır |Hayır |Hayır  |

**Kuruluşa ait cihazlar için kayıt yöntemleri**

### BYOD
“Kendi Cihazını Getir.” Şirket Portalı uygulamasını kullanıcılar yükler ve cihazlarını kaydeder. Cihazı Şirket Portalı’na kaydetmek cihazın çalışma alanına katılmasını sağlar. iOS cihazlarını Şirket Portalı’na kaydetmek için Apple Kimliği gerekir. Kuruluşa ait cihazlarda KCG ek yapılandırma gerektirmez. [Cihaz yönetimini ayarlama](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management) adımlarına bakın. ([Tabloya dön](#overview-of-device-enrollment-methods))

### DEM
Cihaz kayıt yöneticisi. Yönetici, şirkete ait cihazları yönetmek için DEM hesapları oluşturur. Bundan sonra, yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### DEP
Apple Cihaz Kaydı Programı. DEP yönetilen ve satın alınan iOS cihazları için, “uzaktan” ilkesini oluşturur ve dağıtır. Kullanıcı iOS Kurulum Yardımcısı’nı çalıştırdığında, cihaz kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[DEP](ios-device-enrollment-program-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### USB-SA
USB bağlantılı, Kurulum Yardımcısı kaydı. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı, şirkete ait cihazlar Intune ilkesiyle hazırlanır. Yöneticinin her cihazı el ile kaydetmesi gerekir. Kullanıcılar cihazlarını alır ve Kurulum Yardımcısını çalıştırarak cihazlarını kaydederler. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Koşullu erişim
  - Kaçış algılama
  - Mobil uygulama yönetimi

[Apple Configurator ile Kurulum Yardımcısı kaydı](ios-setup-assistant-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### USB-Direct
Doğrudan kayıt. Yönetici Intune ilkesini oluşturur ve bunu Apple Configurator’a aktarır. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Yöneticinin her cihazı el ile kaydetmesi gerekir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, kaçış algılamasını, mobil uygulama yönetimini destekleyemez. [Apple Configurator ile doğrudan kayıt](ios-direct-enrollment-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

**Kuruluşa ait mobil cihazların davranışı**

### Silme
Cihazı kaydetmek için cihazın fabrika ayarlarına sıfırlanması, cihazdan tüm veriler kaldırılarak ilk durumuna döndürülmesi gerekip gerekmediğini belirtir.
[Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md) ([Tabloya dön](#overview-of-device-enrollment-methods))

### Benzeşim
Kayıt yönteminin, cihazı belirli bir kullanıcıya bağlayan “Kullanıcı Benzeşimi” özelliğini destekleyip desteklemediğini belirtir. “Seçenek” ile işaretli cihazlar kullanıcı benzeşimiyle veya benzeşim olmadan kaydedilebilir. Aşağıdakileri desteklemek için kullanıcı benzeşimi gereklidir:
  - Mobil uygulama yönetimi (MAM) uygulamaları
  - E-postaya ve şirket verilerine koşullu erişim
  - Şirket Portalı uygulaması

[Kullanıcı Benzeşimi](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) ([Tabloya dön](#overview-of-device-enrollment-methods))

### Kilitle
Kullanıcının Intune ilkesini kaldırıp cihazı etkili bir şekilde yönetimden kaldırmasını önlemek için cihazın kilitlenip kilitlenemeyeceğini belirtir. iOS cihazlarında, cihazın kilitlenmesi için cihaz Denetimli modda olmalıdır.
([Tabloya dön](#overview-of-device-enrollment-methods))

## Cihaz kaydını etkinleştirme  
 Kayıt, kullanıcıların kişisel cihazlarında şirket kaynaklarına erişmesini ve yöneticinin, bu cihazların şirket kaynaklarını koruyan ilkelerle uyumluluğunu sağlamasına olanak tanır. Intune ile "kendi cihazını getir" senaryolarını etkinleştirmenin en iyi yolu budur. Yönetici, kaydı Intune konsolunda etkinleştirilmelidir, bu, cihaz ve kullanıcılara lisanslar atama arasında bir güven ilişkisi oluşturulmasını gerektirebilir. Cihaz ardından, genellikle kullanıcıların iş veya okul kimlik bilgilerini girmesiyle kaydedilir. Cihaz ardından Intune'dan ilke alır ve kaynaklara erişim kazanır.

[Intune’da cihazları kaydetmeye hazır olun](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Şirkete ait cihazları kaydedin
Şirkete ait cihazlar (COD) Intune konsolu ile yönetilebilir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

[Şirkete ait cihazları kaydedin](manage-corporate-owned-devices.md)

## Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır.

[Exchange ActiveSync ve Intune ile mobil cihaz yönetimi](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Intune ile Windows bilgisayarlarını yönetme  
Windows bilgisayarları, Intune Windows PC istemci yazılımını kullanarak yönetmek için Microsoft Intune da kullanabilirsiniz. Intune istemcisiyle yönetilen bilgisayarlar aşağıdakileri yapabilir:

 - Yazılım ve donanım envanterlerini raporlama
 - Masaüstü uygulamaları yükleme (örneğin, .exe ve .msi dosyaları)
 - Güvenlik duvarı ayarları

Intune istemci yazılımıyla yönetilen bilgisayarlar, seçilerek silinemez veya devre dışı bırakılamaz ve koşullu erişim, VPN ve Wi-Fi ayarları ya da sertifika ve e-posta yapılandırmalarının dağıtımı gibi birçok Intune yönetimi özelliğinden yararlanamaz.

[Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Aug16_HO2-->


