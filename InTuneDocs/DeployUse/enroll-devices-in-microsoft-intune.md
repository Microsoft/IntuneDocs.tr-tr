---
# required metadata

title: Cihazları Microsoft Intune’a kaydetme | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Cihazları yönetim için Intune’a kaydetme
Microsoft Intune mobil cihaz yönetimi (MDM), cihazları yönetime getirmek ve kaynaklara erişim izin vermek için, kayıt olma kullanır. Cihazları kaydetme biçiminiz, cihaz türüne, sahipliğine ve gereken yönetim seviyesine bağlıdır. "Kendi cihazını getir" (BYOD) ve şirkete ait cihaz (COD) senaryoları bir kayıt işlemi gerektirir. Şirket içinde veya bulutta barındırılan Exchange ActiveSync kullanan kuruluşlar, kayıt gereksinimleri olmadan daha hafif yönetim etkinleştirebilir. Windows bilgisayarlar, Intune istemci yazılımı kullanılarak da yönetilebilir.

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


<!--HONumber=May16_HO2-->


