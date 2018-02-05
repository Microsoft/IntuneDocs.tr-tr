---
title: "Microsoft Intune’da cihaz profilleri nelerdir?"
titlesuffix: Azure portal
description: "Intune cihaz profillerini ve bunların şirketinizdeki cihazların yönetilmesine ve korunmasına nasıl yardımcı olabileceğini öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c745f9f745802e0de7a58e3dd7570c0e363ab5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Microsoft Intune cihaz profilleri nedir?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Yönettiğiniz cihazların tümünde ayarları ve özellikleri yönetmek için Microsoft Intune **Cihaz yapılandırması** iş yükünü kullanın. Bu iş yükünü çoğunlukla, cihazlarda bir dizi farklı özelliği ve işlevselliği yönetmenize ve denetlemenize izin veren cihaz profilleri oluşturmak için kullanırsınız.

Bu iş yükünü açtığınızda, aşağıdaki seçenekleri görürsünüz:

- **Genel Bakış** - Bu sayfa size, kullanıcılara ve cihazlara atadığınız cihaz yapılandırmalarını izlemenize yardımcı olan durum bilgilerini ve raporları sağlar.
- **Profilleri Yönet** - Cihaz yapılandırma profilleri oluşturmak için bu bölüme gidersiniz. Bu konuda aşağıda, oluşturabileceğiniz tüm profil türlerinin bir listesini bulabilirsiniz.
- **Sertifika Yetkilisi Kurulumu** - Bu iş akışı, Intune sertifika profillerini yapılandırmak için gereken adımları gösterir.

## <a name="getting-started"></a>Başlarken

Cihaz profillerini oluşturma iş akışı, tüm profiller için benzer çalışır. Bilgi için [Microsoft Intune cihaz yapılandırma profilleri oluşturma](device-profile-create.md) konusunu okuyun. Sonra, her profil türünün ayarlarını oluşturma hakkındaki özel bilgileri okuyun.

Cihazlarınızda aşağıdaki özellikleri yönetebilirsiniz:

## <a name="device-features"></a>Cihaz özellikleri

Cihaz özellikleri, iOS ve macOS cihazlarda AirPrint, bildirimler ve paylaşılan cihaz yapılandırmaları gibi özellikleri denetlemenize olanak tanır.
Daha fazla bilgi için bkz. [Cihaz özelliği ayarlarını yapılandırma](device-features-configure.md) iOS ve macOS’u destekler.

## <a name="device-restrictions"></a>Cihaz kısıtlamaları
Cihaz kısıtlamaları, yönettiğiniz cihazlarda güvenlik, donanım ve veri paylaşma ayarları gibi kategoriler dahil olmak üzere birçok ayarı denetlemenize izin verir. Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.
Daha fazla bilgi için bkz. [Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) Android, iOS, macOS, Windows 10 ve Windows 10 Team'i destekler.

## <a name="email"></a>E-posta
E-posta profilleri, yönettiğiniz cihazlarda Exchange ActiveSync e-posta ayarları oluşturmanıza, atamanıza ve izlemenize olanak tanır. E-posta profilleri tutarlılık sağlar, destek çağrılarını azaltır ve son kullanıcıların, herhangi bir kurulum yapmalarına gerek kalmadan kendi cihazlarından şirket e-postasına erişmelerini sağlar.
Daha fazla bilgi için bkz. [E-posta ayarlarını yapılandırma](email-settings-configure.md) Android, iOS, Windows Phone 8.1 ve Windows 10'u destekler.

## <a name="wi-fi"></a>Wi-Fi
Kablosuz ağ ayarlarını kuruluşunuzdaki kullanıcılara ve cihazlara atamak için Wi-Fi profillerini kullanın. Bir Wi-Fi profili atadığınızda, kullanıcılarınız kurumsal Wi-Fi ağınıza, ağı kendileri yapılandırmak zorunda kalmadan erişim elde eder.
Daha fazla bilgi için bkz. [Wi-Fi ayarlarını yapılandırma](wi-fi-settings-configure.md) Android, iOS, macOS ve Windows 8.1'i (yalnızca içeri aktarma) destekler.

## <a name="vpn"></a>VPN
Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. VPN profillerini, ağa kolay ve güvenli bir şekilde bağlanabilmeleri için kuruluşunuzdaki kullanıcılara ve cihazlara atayın.
Daha fazla bilgi için [VPN ayarlarını yapılandırma](vpn-settings-configure.md) konusuna bakın.
Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 ve Windows 10'u destekler.

## <a name="education"></a>Eğitim
Windows Sınav Zamanı uygulamasının seçeneklerini yapılandırmanıza olanak tanır. Bu seçenekleri yapılandırdığınızda, sınav tamamlanana kadar cihazda başka uygulama çalıştırılamaz.
Daha fazla bilgi için bkz. [Eğitim ayarlarını yapılandırma](education-settings-configure.md)

## <a name="certificates"></a>Sertifikalar
Bu profil türü cihazlara atanabilen ve Wi-Fi, VPN ve e-posta profillerinin kimliğini doğrulamak için kullanılan güvenilen, SCEP ve PKCS sertifikalarını yapılandırmanıza olanak tanır.
Daha fazla bilgi için bkz. [Sertifikaları yapılandırma](certificates-configure.md) Android, iOS, Windows Phone 8.1 ve Windows 8.1 ve Windows 10'u destekler.

## <a name="edition-upgrade"></a>Sürüm yükseltme
Bu profil türü, Windows 10'un bazı sürümlerini çalıştıran cihazları otomatik olarak yeni bir sürüme yükseltmenizi sağlar.
Daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md) Yalnızca Windows 10'u destekler.

## <a name="endpoint-protection"></a>Endpoint protection
Bu profil türü, Windows 10 cihazları için BitLocker ve Windows Defender ayarlarını yapılandırmanızı sağlar.
Daha fazla bilgi için bkz. [Windows 10 için Endpoint protection ayarları ](endpoint-protection-windows-10.md) Yalnızca Windows 10'u destekler.

## <a name="windows-information-protection"></a>Windows Bilgi Koruması
Windows Bilgi Koruması, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.
Daha fazla bilgi için [Windows Bilgi Koruması’nı yapılandırma](windows-information-protection-configure.md) konusuna bakın. Yalnızca Windows 10’u destekler.

## <a name="custom"></a>Özel
Özel ayarlar, Intune’da yerleşik olarak sağlanmayan cihaz ayarlarını atamanıza olanak tanır. Android cihazlarda, örneğin cihazı yapılandıran OMA-URI değerlerini belirtebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz.
Daha fazla bilgi için bkz. [Özel ayarları yapılandırma](custom-settings-configure.md) Android, iOS, macOS ve Windows Phone 8.1'i destekler.

## <a name="next-steps"></a>Sonraki adımlar
Cihazları yapılandırmaya başlamak için listedeki profil türlerinden birini seçin.
