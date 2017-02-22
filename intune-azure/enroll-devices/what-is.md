---
title: "Microsoft Intune cihaz kaydı nedir | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS, Android ve Windows cihazlarının kaydını öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/26/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 10cf9980468eff912557747c31994747c17a3ab4
ms.openlocfilehash: 01bf32ef874385019ea4b0fb0ce278554459287d


---

# <a name="what-is-device-enrollment"></a>Cihaz kaydı nedir?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bu konu başlığı altında, Intune yönetiminde kayıt konusu açıklanır ve mobil cihazları kaydetmenin farklı yollar listelenir.

Windows bilgisayarları da dahil olmak üzere cihazları Intune’a kaydeder, böylece bu cihazları yönetebilirsiniz. Intune belgelerinde bu özellik mobil cihaz yönetimi (MDM) olarak adlandırılır. Cihazlar bilgisayar değil mobil cihaz olarak kaydedildiğinde, bunlara bir MDM sertifikası verilir ve cihazlar bu sertifikayı Intune hizmetiyle iletişim kurmak için kullanır. 

Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve size gereken yönetim düzeyine bağlıdır. "Kendi cihazını getir" (KCG) kaydı, kullanıcıların kendi kişisel telefonlarını, tabletlerini veya bilgisayarlarını kaydetmesine izin verir. Şirkete ait cihaz (COD) kaydetme; otomatik kaydetme, paylaşılan cihazlar veya önceden yetkilendirilmiş kaydetme gereksinimleri gibi yönetim senaryolarına olanak tanır.

Şirket içinde veya bulutta barındırılan Exchange ActiveSync kullanırsanız, kayda gerek kalmadan basit Intune yönetimini etkinleştirebilirsiniz (çok yakında daha fazla bilgi sağlanacaktır). Windows bilgisayarlarını mobil cihazlar olarak yönetebilirsiniz. Aşağıda açıklandığı gibi önerilen yöntem budur. Bu cihazları, [Intune istemci yazılımını](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) kullanıp bilgisayar olarak da yönetebilirsiniz.


## <a name="overview-of-device-enrollment-methods"></a>Cihaz kayıt yöntemlerine genel bakış

Aşağıdaki tabloda Intune'a kayıt yöntemleri ve her yöntem için desteklenen özellikler ile gereksinimler gösterilmektedir. Özellik ve gereksinimleri açıklamaları aşağıda verilmiştir. Tabloda aşağıdaki terimler kullanılır:

- **Temizle** - Kullanıcıların cihazı kaydedebilmesi için temizleme yapılıp yapılmaması gerektiğini belirtir. "Temizleme" terimi, cihazın fabrika verilerine döndürülerek tüm verilerin silinmesini ifade eder. Daha fazla bilgi için bkz. [Cihazlarda tam veya seçmeli temizleme kullanma](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Benzeşim** - Cihazlarla kullanıcıları ilişkilendirir. Mobil uygulama yönetimi (MAM) ve şirket verilerine koşullu erişim için gereklidir. Daha fazla bilgi için bkz. [Kullanıcı benzeşimi](enroll-ios-devices-using-device-enrollment-program.md).
- **Kilitle** - Kullanıcıların cihaz kayıtlarını yönetimden kaldırmasının engellenip engellenmediğini gösterir. Kullanıcılar, Şirket Portalı uygulamalarını kullanarak tüm platformlarda cihaz kaydını kaldırabilir. Cihaz kaydını kaldırma işlemi için yerel işletim sistemi menüleri kullanılamaz.


**iOS kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar** |
|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | Çok yakında daha fazla bilgi sağlanacaktır|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  | [Daha fazla bilgi](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|   Evet |   İsteğe bağlı |  İsteğe bağlı|[Daha fazla bilgi](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**| Evet |   İsteğe bağlı |  Hayır| [Daha fazla bilgi](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**| Hayır |    Hayır  | Hayır|[Daha fazla bilgi](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Windows kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Evet|   Evet |   Hayır | Çok yakında daha fazla bilgi sağlanacaktır|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](enroll-devices-using-device-enrollment-manager.md)|

**Android kayıt yöntemleri**

| **Yöntem** |  **Temizleme gerekli mi?** |    **Benzeşim**    |   **Kilitle** | **Ayrıntılar**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[KCG](#byod)** | Hayır|    Evet |   Hayır | Çok yakında daha fazla bilgi sağlanacaktır|
|**[DEM](#dem)**|   Hayır |Hayır |Hayır  |[Daha fazla bilgi](enroll-ios-devices-using-device-enrollment-program.md)|


## <a name="byod"></a>KCG
“Kendi cihazını getir” kullanıcıları Şirket Portalı uygulamasını yükler ve cihazlarını kaydeder. Bu, kullanıcıların şirket ağına bağlanarak etki alanına veya Azure Active Directory’ye katılmasına olanak tanır. Çoğu platformda, birçok COD senaryosu için KCG’yi etkinleştirmeniz gerekir.

## <a name="corporate-owned-devices"></a>Şirkete ait cihazlar
Şirkete ait cihazlar (COD) Azure Portal kullanılarak yönetilebilir. iOS cihazları, Apple tarafından sağlanan araçlar üzerinden doğrudan kaydedilebilir. Tüm cihaz türleri, cihaz kayıt yöneticisini kullanan bir yönetici ya da müdür tarafından kaydedilebilir. IMEI numaralı cihazlar da, COD senaryolarını etkinleştirmek için şirkete ait olarak tanımlanabilir ve etiketlenebilir.

### <a name="dem"></a>DEM
Cihaz kayıt yöneticisi, şirkete ait birden çok cihazı kaydetmek ve yönetmek için kullanılan özel bir kullanıcı hesabıdır. Yöneticiler Şirket Portalı’nı yükleyebilir ve kullanıcısı olmayan birçok cihazı kaydedebilir. [DEM](enroll-devices-using-device-enrollment-manager.md) hakkında daha fazla bilgi edinin. ([Tabloya dön](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Apple Aygıt Kayıt Programı (DEP) yönetimi, “havadan” ilke oluşturmanıza ve DEP ile satın alınan ve yönetilen iOS cihazlara dağıtmanıza olanak sağlar. Cihaz, kullanıcı cihazı ilk açtığında ve iOS Ayarlama Yardımcısı’nı çalıştırdığında kaydedilir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:

  - Kilitli kayıt
  - Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğini belirleme](choose-ios-enrollment-method.md)
- [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](enroll-ios-devices-using-device-enrollment-program.md). 
- [Yukarıdaki tabloya dön](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
BT yöneticileri, şirkete ait tüm cihazları Kurulum Yardımcısı kullanarak el ile kaydetme işlemine hazırlamak için USB aracılığıyla Apple Configurator kullanır. BT yöneticisi bir kayıt profili oluşturur ve bunu Apple Configurator’a aktarır. Kullanıcılar cihazlarını aldığında, bu cihazları kaydetmek için Kurulum Yardımcısını çalıştırmaları istenir. Bu yöntem **iOS Denetimli** modunu destekler ve bu mod şunlara olanak tanır:
  - Kilitli kayıt
  - Bilgi noktası modu ile diğer gelişmiş yapılandırmalar ve kısıtlamalar

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](choose-ios-enrollment-method.md)
- [Configurator ve Kurulum Yardımcısı ile iOS cihazlarını kaydetme](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). 

### <a name="usb-direct"></a>USB-Direct
Doğrudan kayıt için yöneticinin bir kayıt ilkesi oluşturup bunu Apple Configurator’a aktararak her cihazı el ile kaydetmesi gerekir. USB bağlantılı, şirkete ait cihazlar fabrika sıfırlamasına gerek kalmadan doğrudan kaydedilir. Cihazlar, kullanıcısız cihaz olarak yönetilir. Bunlar kilitli veya denetimli değildir ve koşullu erişimi, jailbreak algılamasını ya da mobil uygulama yönetimini destekleyemez. 

iOS kaydı hakkında daha fazla bilgi için bkz:

- [iOS cihazlarının nasıl kaydedileceğine karar verme](choose-ios-enrollment-method.md)
- [Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Exchange ActiveSync ve Intune ile mobil cihaz yönetimi
Kaydedilmemiş ancak Exchange ActiveSync’e (EAS) bağlanan mobil cihazlar, EAS MDM ilkesi kullanılarak Intune tarafından yönetilebilir. Intune, şirket içinde veya bulutta barındırılan EAS ile iletişim kurmak için bir Exchange Connector kullanır. Çok yakında daha fazla bilgi sağlanacaktır.


## <a name="windows-pc-management-with-intune"></a>Intune ile Windows bilgisayarı yönetimini etkinleştirme  
Windows bilgisayarları, Intune istemci yazılımı ile yönetmek için Microsoft Intune da kullanabilirsiniz. Intune istemcisiyle yönetilen bilgisayarlar aşağıdakileri yapabilir:

 - Yazılım ve donanım envanterlerini raporlama
 - Masaüstü uygulamaları yükleme (örneğin, .exe ve .msi dosyaları)
 - Güvenlik Duvarı ayarlarını yönet

Intune istemci yazılımı ile yönetilen bilgisayarlar tamamen silinemese de, seçmeli silme kullanılabilir. Intune yazılım istemcisi ile yönetilen bilgisayarlar, koşullu erişim, VPN ve Wi-Fi ayarları ya da sertifika ve e-posta yapılandırmalarının dağıtımı gibi birçok Intune yönetimi özelliğinden yararlanamaz. Çok yakında daha fazla bilgi sağlanacaktır.

## <a name="supported-device-platforms-and-browsers"></a>Desteklenen cihaz platformları ve tarayıcılar

Bkz. [Intune için desteklenen cihazlar ve tarayıcılar](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar (PC değil) temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.



<!--HONumber=Feb17_HO1-->


