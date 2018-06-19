---
title: Intune’un Google’a gönderdiği veriler
titleSuffix: Microsoft Intune
description: Intune’un Google’a gönderdiği verilerin listesi.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed713e63b63b4eb4a2696e9fd53b39cb139b4115
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
ms.locfileid: "31617286"
---
# <a name="data-intune-sends-to-google"></a>Intune’un Google’a gönderdiği veriler

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihazda Android kurumsal cihaz yönetimi etkinleştirildiğinde Microsoft Intune, Google ile bir bağlantı kurar ve Google ile kullanıcı ve cihaz bilgilerini paylaşır. Microsoft Intune’un bağlantı kurabilmesi için önce bir Google hesabı oluşturmanız gerekir.

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


Microsoft Intune ile Android kurumsal cihaz yönetimini kullanmayı bırakmak ve verileri silmek için hem Microsoft Intune Android kurumsal cihaz yönetimini devre dışı bırakmanız hem de Google hesabınızı silmeniz gerekir. Hesap yönetimini nasıl gerçekleştireceğinizi görmek için Google hesabına bakın.


