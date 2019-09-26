---
title: Intune’un Google’a gönderdiği veriler
titleSuffix: Microsoft Intune
description: Intune’un Google’a gönderdiği verilerin listesi.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 44ee999291b241da599d66caaf75b504dd4b02ca
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "71304946"
---
# <a name="data-intune-sends-to-google"></a>Intune’un Google’a gönderdiği veriler

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihazda Android kurumsal cihaz yönetimi etkinleştirildiğinde Microsoft Intune, Google ile bir bağlantı kurar ve Google ile kullanıcı ve cihaz bilgilerini paylaşır. Microsoft Intune’un bağlantı kurabilmesi için önce bir Google hesabı oluşturmanız gerekir.

Aşağıdaki tabloda, bir cihazda cihaz yönetimi etkinleştirildiğinde Microsoft Intune’un Google’a gönderdiği veriler listelenir:


| Google’a gönderilen veriler | Ayrıntılar | Kullanıldığı yer | Örnek |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Gmail hesabınızı Intune’a bağladıktan sonra Google’da oluşturulur. | Intune ve Google arasında iletişim kurmak için kullanılan birincil tanımlayıcı.  Bu iletişim; ilkeleri ayarlama, cihazları yönetme ve Android kuruluşunun Intune’a bağlamasını/bağlamayı kaldırır içerir. | Benzersiz tanımlayıcı, örnek biçim: LC04eik8a6 |
| İlke Gövdesi | Yeni bir uygulama veya yapılandırma ilkesi kaydederken Intune’da oluşturulur. | İlkeleri cihazlara uygulama. | Bu, bir uygulama veya yapılandırma ilkesi için tüm yapılandırılmış ayarların bir koleksiyonudur. Ağ adları, uygulama adları ve uygulamaya özel ayarlar gibi bir ilkenin parçası olarak sağlanmışsa müşteri bilgilerini içerebilir. |
| Cihaz Verileri | İş Profili senaryoları için cihazlar Intune'a kayıt ile başlar. Yönetilen cihaz senaryoları için cihazlar Google'a kayıt ile başlar. | Cihaz Verileri bilgileri; ilkeleri uygulama, cihazı yönetme ve genel raporlama gibi çeşitli eylemler için Intune ve Google arasında gönderilir. | **Cihaz Adını temsil eden benzersiz tanımlayıcı.** Örnek: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Kullanıcı Adını temsil eden benzersiz tanımlayıcı.** Örnek: Kuruluşlar/LC04ebru7b/kullanıcılar/116838519924207449711<br>**Cihaz durumu.** Örnekler: Etkin, devre dışı, sağlama.<br>**Uyumluluk durumları.** Örnekler: Ayar desteklenmiyor, gerekli uygulamalar eksik<br>**Yazılım Bilgileri.** Örnekler: Yazılım sürümleri ve düzeltme eki düzeyi.<br>**Ağ Bilgileri.** Örnekler: IMEı, MEıD, WifiMacAddress<br>**Cihaz Ayarları.** Örnekler: Şifreleme düzeyleri hakkında bilgi, cihazın bilinmeyen uygulamalara izin verip etmeyeceğini &.<br> Bir JSON ileti örneği için aşağıya bakın. |
| newPassword | Intune'da oluşturulur. | Cihaz parolası sıfırlanıyor. | Yeni parolayı temsil eden dize. |
| Google User | Google | İş Profili (KCG) senaryolarında iş profilini yönetme. | Bağlantılı Gmail hesabını temsil eden benzersiz tanımlayıcı. Örnek: 114223373813435875042 |
| Uygulama verileri | Uygulama ilkesi kaydedilirken Intune’da oluşturulur. |  | Uygulama Adı dizesi. Örnek: app:com.microsoft.windowsintune.companyportal |
| Kurumsal Hizmet Hesabı | Intune isteği üzerine Google’da oluşturulur. | Bu müşteriyle ilgili işlemler için Intune ve Google arasında kimlik doğrulamasında kullanılır. | Bunun birkaç bölümü vardır:<br> **Kuruluş kimliği**: Daha önce belgelenmiştir.<br>**UPN**: Oluşturulan UPN, müşteri adına yapılan kimlik doğrulamasında kullanılır.<br>Örnek: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Anahtar**: Kimlik doğrulama isteklerinde kullanılan Base64 kodlamalı blob, hizmette şifreli olarak depolanır, ancak blob şöyle görünür:<br> Müşterinin anahtarını temsil eden Benzersiz Tanımlayıcı<br>Örnek: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |


Microsoft Intune ile Android kurumsal cihaz yönetimini kullanmayı bırakmak ve verileri silmek için hem Microsoft Intune Android kurumsal cihaz yönetimini devre dışı bırakmanız hem de Google hesabınızı silmeniz gerekir. Hesap yönetimini nasıl gerçekleştireceğinizi görmek için Google hesabına bakın.


