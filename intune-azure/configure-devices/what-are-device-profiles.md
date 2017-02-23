---
title: "Microsoft Intune’da cihaz profilleri nelerdir? | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune cihaz profillerini ve bunların şirketinizdeki cihazların yönetilmesine ve korunmasına nasıl yardımcı olabileceğini öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 0e126c067b5c212ae5bfe1cf69e01128a00b1c8e


---

# <a name="what-are-device-profiles"></a>Cihaz profilleri nedir?
<!--- This topic doesn't really answer the topic title: What are device profiles?" It needs to answer that question, then it can go on to discuss what profiles are in Intune and how to use them. Linda--->

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Yönettiğiniz cihazların tümünde ayarları ve özellikleri yönetmek için Microsoft Intune **Cihazları yapılandır** iş yükünü kullanın.

Bu iş yükünü açtığınızda aşağıdaki seçenekleri görürsünüz:

- **Genel Bakış** - Bu sayfa size, kullanıcılara ve cihazlara atadığınız cihaz yapılandırmalarını izlemenize yardımcı olan durum bilgilerini ve raporları sağlar.
- **Profilleri Yönet** - Cihaz yapılandırma profillerini oluşturmak için bu bölüme gidersiniz. Aşağıda, oluşturabileceğiniz tüm profil türlerinin listesini bulabilirsiniz.
- **Sertifika Yetkilisi Kurulumu** - Bu iş akışı, sertifikaları yapılandırmak için gereken adımlarda size yol gösterir. Intune sertifika profilleriyle çalışmak istiyorsanız bunu yapmanız gerekir.

## <a name="getting-started"></a>Başlarken

Cihaz profillerini oluşturma iş akışı, tüm profiller için benzer çalışır. Profilleri oluşturma hakkında bilgi için, [Microsoft Intune cihaz yapılandırma profillerini oluşturma](/intune-azure/configure-devices/how-to-create-device-profiles) konusunu okuyun. Sonra, her profil türünün ayarlarını oluşturma hakkındaki özel bilgileri okuyun.

Cihazlarınızda aşağıdaki özellikleri yönetebilirsiniz:

## <a name="device-restrictions"></a>Cihaz kısıtlamaları
Cihaz kısıtlamaları; güvenlik, tarayıcı, donanım ve veri paylaşım ayarları gibi bir dizi kategori altında yönettiğiniz çok çeşitli ayarları ve özellikleri denetlemenize olanak tanır. Örneğin, iOS cihazı kullanıcılarının cihaz kamerasına erişmesini engelleyen bir cihaz kısıtlama profili oluşturabilirsiniz.
Daha fazla bilgi için [Cihaz kısıtlama ayarlarını yapılandırma](how-to-configure-device-restrictions.md) konusuna bakın. Android, iOS, macOS, Windows 10 ve Windows 10 Team’i destekler.

## <a name="email"></a>E-posta
E-posta profilleri, yönettiğiniz cihazlarda Exchange ActiveSync e-posta ayarları oluşturmanıza, dağıtmanıza ve izlemenize olanak tanır. Bu ayarları dağıtarak tutarlılığı güvence altına alır, destek aramalarını azaltır ve son kullanıcıların herhangi bir kurulum yapmalarına gerek kalmadan kendi cihazlarında şirket e-postasına erişmelerini sağlarsınız.
Daha fazla bilgi için [E-posta ayarlarını yapılandırma](how-to-configure-email-settings.md) konusuna bakın. Android, iOS, Windows Phone 8.1 ve Windows 10’u destekler.

## <a name="wi-fi"></a>Wi-Fi
Kablosuz ağ ayarlarını kuruluşunuzdaki kullanıcılara ve cihazlara dağıtmak için Wi-Fi profillerini kullanın. Bir Wi-Fi profili dağıttığınızda, kullanıcılarınız kurumsal Wi-Fi ağınıza ağı kendileri yapılandırmak zorunda kalmadan erişir.
Daha fazla bilgi için [Wi-Fi ayarlarını yapılandırma](how-to-configure-wi-fi-settings.md) konusuna bakın. Android, iOS, macOS ve Windows 8.1’i (yalnızca içeri aktarma) destekler.

## <a name="vpn"></a>VPN
Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. VPN ayarlarını kuruluşunuzdaki kullanıcılar ve cihazlara dağıtmak için VPN profillerini kullanarak ağa kolay ve güvenli bir şekilde bağlanabilmelerini sağlayın.
Daha fazla bilgi için [VPN ayarlarını yapılandırma](how-to-configure-vpn-settings.md) konusuna bakın.
Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 ve Windows 10’u destekler.

## <a name="certificates"></a>Sertifikalar
Bu profil türü cihazlara atanabilen ve Wi-Fi, VPN ve e-posta profillerinin kimliğini doğrulamak için kullanılan güvenilen, SCEP ve PKCS sertifikalarını yapılandırmanıza olanak tanır.
Daha fazla bilgi için [Sertifikaları yapılandırma](how-to-configure-certificates.md) konusuna bakın. Android, iOS, Windows Phone 8.1 ve Windows 8.1 ve Windows 10’u destekler.

## <a name="education"></a>Eğitim
iOS cihazlarını eğitim ortamında kullanmak için doğru sertifikaları belirtmenize yardımcı olur.
Daha fazla bilgi için [iOS cihazları için Intune eğitim ayarlarını yapılandırma](education-settings-for-ios.md) Yalnızca iOS’u destekler.

## <a name="edition-upgrade"></a>Sürüm yükseltme
Bu profil, Windows 10’un bazı sürümlerini çalıştıran cihazları otomatik olarak yükseltmenize olanak tanır. Daha fazla bilgi için [Windows 10 sürüm yükseltmelerini yapılandırma](how-to-configure-windows-10-edition-upgrade.md) konusuna bakın. Yalnızca Windows 10’u destekler.

## <a name="windows-information-protection"></a>Windows Bilgi Koruması
Windows Bilgi Koruması, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden veri sızıntılarına karşı koruma sağlamaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.
Daha fazla bilgi için [Windows Bilgi Koruması’nı yapılandırma](how-to-configure-windows-information-protection.md) konusuna bakın. Yalnızca Windows 10’u destekler.

## <a name="custom"></a>Özel
Özel ayarlar, Intune’da yerleşik olarak sağlanmayan cihaz ayarlarını atamanıza olanak tanır. Android cihazlarda, örneğin cihazı yapılandıran OMA-URI değerlerini belirtebilirsiniz. iOS cihazları için, Apple Configurator’da oluşturduğunuz bir yapılandırma dosyasını içeri aktarabilirsiniz.
Daha fazla bilgi için [Özel ayarları yapılandırma](how-to-configure-custom-settings.md) konusuna bakın. Android, iOS, macOS ve Windows Phone 8.1’i destekler.



<!--HONumber=Feb17_HO1-->

