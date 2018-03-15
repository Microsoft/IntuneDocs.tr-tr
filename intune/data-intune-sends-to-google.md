---
title: "Intune’un Google’a gönderdiği veriler"
titlesuffix: Azure portal
description: "Intune’un Google’a gönderdiği verilerin listesi."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5f8c71115b8c3ee761fbc8d303f87e8aaabd5e1
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="data-intune-sends-to-google"></a>Intune’un Google’a gönderdiği veriler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir cihazda Android cihaz yönetimi etkinleştirildiğinde Microsoft Intune, Google ile bir bağlantı kurar ve Google ile kullanıcı ve cihaz bilgilerini paylaşır. Microsoft Intune’un bağlantı kurabilmesi için önce bir Google hesabı oluşturmanız gerekir.

Aşağıdaki tabloda, bir cihazda cihaz yönetimi etkinleştirildiğinde Microsoft Intune’un Google’a gönderdiği veriler listelenir:


| Google’a gönderilen veriler | Ayrıntılar | Ne için kullanılır | Örnek |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Gmail hesabınızı Intune’a bağladıktan sonra Google’da oluşturulur. | Intune ve Google arasında iletişim kurmak için kullanılan birincil tanımlayıcı.  Bu iletişim; ilkeleri ayarlama, cihazları yönetme ve Android kuruluşunun Intune’a bağlamasını/bağlamayı kaldırır içerir. | Benzersiz tanımlayıcı, Örnek biçim: LC04eik8a6 |
| İlke Gövdesi | Yeni bir uygulama veya yapılandırma ilkesi kaydederken Intune’da oluşturulur. | İlkeleri cihazlara uygulama. | Bu, bir uygulama veya yapılandırma ilkesi için tüm yapılandırılmış ayarların bir koleksiyonudur. Ağ adları, uygulama adları ve uygulamaya özel ayarlar gibi bir ilkenin parçası olarak sağlanmışsa müşteri bilgilerini içerebilir. |
| Cihaz Verileri | İş Profili senaryoları için cihazlar Intune'a kayıt ile başlar. Yönetilen cihaz senaryoları için cihazlar Google'a kayıt ile başlar. | Cihaz Verileri bilgileri; ilkeleri uygulama, cihazı yönetme ve genel raporlama gibi çeşitli eylemler için Intune ve Google arasında gönderilir. | **Cihaz Adını temsil eden benzersiz tanımlayıcı.** Örnek: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Kullanıcı Adını temsil eden benzersiz tanımlayıcı.** Örnek: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Cihaz durumu.** Örnekler: Etkin, Devre Dışı, Sağlanıyor.<br>**Uyumluluk durumları.** Örnekler: Ayar desteklenmiyor, gerekli uygulamalar eksik<br>**Yazılım Bilgileri.** Örnekler: Yazılım sürümleri ve düzeltme eki düzeyi.<br>**Ağ Bilgileri.** Örnekler: IMEI, MEID, WifiMacAddress<br>**Cihaz Ayarları.** Örnekler: Şifreleme düzeyleri ve cihazın bilinmeyen uygulamalara izin verip vermediğine ilişkin bilgiler.<br> Bir JSON ileti örneği için aşağıya bakın. |
| newPassword | Intune'da oluşturulur. | Cihaz parolası sıfırlanıyor. | Yeni parolayı temsil eden dize. |
| Google User | Google | İş Profili (KCG) senaryolarında iş profilini yönetme. | Bağlantılı Gmail hesabını temsil eden benzersiz tanımlayıcı. Örnek: 114223373813435875042 |
| Uygulama Verileri | Uygulama ilkesi kaydedilirken Intune’da oluşturulur. |  | Uygulama Adı dizesi. Örnek: app:com.microsoft.windowsintune.companyportal |
| Kurumsal Hizmet Hesabı | Intune isteği üzerine Google’da oluşturulur. | Bu müşteriyle ilgili işlemler için Intune ve Google arasında kimlik doğrulamasında kullanılır. | Bunun birkaç bölümü vardır:<br> **Kuruluş kimliği**: Daha önce belgelenmiştir.<br>**UPN**: Oluşturulan UPN, müşteri adına yapılan kimlik doğrulamasında kullanılır.<br>Örnek: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Anahtar**: Base64 kodlu blob, hizmette şifrelenmiş olarak saklanan kimlik doğrulama isteklerinde kullanılır, blob görünümü şöyledir:<br> Müşterinin anahtarını temsil eden Benzersiz Tanımlayıcı<br>Örnek: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Cihaz Verisi örneği**

Google’dan JSON cihazı iletisi örneği aşağıdadır:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Microsoft Intune ile Android cihaz yönetimini kullanmayı bırakmak ve verileri silmek için, hem Microsoft Intune Android cihaz yönetimini devre dışı bırakmanız hem de Google hesabınızı silmeniz gerekir. Hesap yönetimini nasıl gerçekleştireceğinizi görmek için Google hesabına bakın.


