---
title: "Şirket kaynaklarına erişimi etkinleştirme | Microsoft Intune"
description: "Wi-Fi, VPN ve e-posta profilleri, kullanıcılarınızın gereken dosyalara ve kaynaklara erişim kazanmasına yardımcı olmak için birlikte çalışır."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b4acce1b1861ca2c2d1432b0258ad1e95e46d2a
ms.openlocfilehash: 2959ad5f09be686e4dae9b751e8ede5e6b60bd89


---

# <a name="enable-access-to-company-resources-with-microsoft-intune"></a>Microsoft Intune ile şirket kaynaklarına erişimi etkinleştirme
Microsoft Intune Wi-Fi, VPN ve e-posta profilleri, kullanıcılarınızın nerede olurlarsa olsunlar, işlerini gerçekleştirmek için ihtiyaç duydukları dosyalara ve kaynaklara erişim kazanmalarına yardımcı olmak için birlikte çalışır. Sertifika profilleri bu erişimin güvenliğini sağlamaya yardımcı olur.

## <a name="wifi-profileswificonnectionsinmicrosoftintunemd-and-supported-platforms"></a>[Wi-Fi profilleri](wi-fi-connections-in-microsoft-intune.md) ve desteklenen platformlar

Kablosuz ağ ayarlarını kullanıcılarınıza dağıtın. Bu ayarlar, kullanıcılarınızın şirket ağına bağlanmalarını kolaylaştırır.
#### <a name="supported-platforms"></a>Desteklenen platformlar

|Windows 8.1 ve üzeri|Windows Phone 8.1 ve üzeri|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Evet (Windows Wi-Fi profilini içeri alabilirsiniz)|Evet (OMA-URI’yi yapılandırabilirsiniz) |Evet|Evet|Evet|

## <a name="vpn-profilesvpnconnectionsinmicrosoftintunemd-and-supported-platforms"></a>[VPN profilleri](vpn-connections-in-microsoft-intune.md) ve desteklenen platformlar
Sanal özel ağ (VPN) ayarlarını kullanıcılarınıza dağıtın. Bu ayarlar, kullanıcıların şirket ağındaki kaynaklara bağlanmalarını kolaylaştırır.

|Windows 8.1 ve üzeri|Windows Phone 8.1 ve üzeri|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Evet|Evet|Evet|Evet|Evet|

## <a name="email-profilesconfigureaccesstocorporateemailusingemailprofileswithmicrosoftintunemd-and-supported-platforms"></a>[E-posta profilleri](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) ve desteklenen platformlar
Kuruluşunuzdaki cihazlarda yerel e-posta istemcisi ayarlarını oluşturun, dağıtın ve izleyin.

|Windows 8.1 ve üzeri|Windows Phone 8.1 ve üzeri|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Hayır|Evet|Evet|Hayır|Evet|
> [!NOTE]
> [Bu Intune ekibi blog gönderisi](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/), OMA-URI kullanarak Windows Phone 8.1 Wi-Fi profilinin nasıl yapılandırılacağı hakkında bilgi verir.

## <a name="certificate-profilessecureresourceaccesswithcertificateprofilesmd-and-supported-platforms"></a>[Sertifika profilleri](secure-resource-access-with-certificate-profiles.md) ve desteklenen platformlar
Kablosuz ağlar ve VPN bağlantıları gibi şirket kaynaklarına güvenli erişime yardımcı olur.

|Windows 8.1 ve üzeri|Windows Phone 8.1 ve üzeri|iOS|Android|Samsung KNOX|
|---------------------|---------------------------|---|-------|------------|
|Evet|Evet|Evet|Evet|Evet|



<!--HONumber=Oct16_HO2-->


