---
title: Microsoft Intune - Azure ile cihaz geçiş kodlarını sıfırlama | Microsoft Docs
description: Intune ile yönettiğiniz veya izlediğiniz cihazlarda Geçiş kodunu kaldır eylemini kullanarak geçiş kodunu kaldırın veya sıfırlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7ca53786d372f53d63388fef1179ca271fdb9d9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508592"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Intune’da bir cihazın geçiş kodunu sıfırlama veya kaldırma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu belgede, Android Enterprise 'ta (eski adıyla Android for Work veya AfW) cihaz düzeyinde geçiş kodu sıfırlama ve iş profili geçiş kodu sıfırlama açıklanmaktadır. Her biri için gereksinimler farklılık gösterebileceğinden, bu ayrımı dikkate almak önemlidir. Cihaz düzeyinde bir geçiş kodu sıfırlaması geçiş kodunu cihazın tamamı için sıfırlar. İş profili geçiş kodu sıfırlaması, geçiş kodunu yalnızca kullanıcının Android kurumsal cihazlarındaki iş profili için sıfırlar.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Cihaz düzeyinde geçiş kodu sıfırlama için desteklenen platformlar

| Platfveyam | Destekleniyor mu? |
| ---- | ---- |
| Sürüm 6.x veya öncesindeki Android cihazları | Evet |
| Bilgi noktası modundaki Android kurumsal cihazlar | Evet |
| iOS cihazları | Evet |
| Kullanıcı kaydıyla kaydedilen iOS cihazları | Hayır |
| İş profiliyle kaydedilmiş Android cihazları | Hayır |
| Sürüm 7.0 veya üzeri Android cihazlar | Hayır |
| Mac OS | Hayır |
| Windows | Hayır |

Android cihazlarda, bu, cihaz düzeyi geçiş kodu sıfırlamasının yalnızca 6. x veya önceki sürümleri çalıştıran cihazlarda ya da bilgi noktası modunda çalışan Android kurumsal cihazlarda desteklenir. Bunun nedeni Google'ın bir Android 7 cihazının geçiş kodunu/parolasını bir Cihaz Yöneticisi tarafından verilen bir uygulama içinden sıfırlama desteğini kaldırmış olması ve bunun tüm MDM satıcıları için geçerli olmasıdır.

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Android kurumsal iş profili geçiş kodu sıfırlaması için desteklenen platformlar

| Platfveyam | Destekleniyor mu? |
| ---- | ---- |
| Bir iş profili ile kaydedilmiş ve sürüm 8.0 ve sonrasını çalıştıran Android kurumsal cihazlar | Evet |
| Bir iş profili ile kaydedilmiş ve sürüm 7.x ve öncesini çalıştıran Android kurumsal cihazlar | Hayır |
| Sürüm 7.x ve öncesini çalıştıran Android cihazlar | Hayır |

Yeni bir iş profili geçiş kodu oluşturmak için Geçiş Kodunu Sıfırla eylemini kullanın. Bu eylem, bir geçiş kodu sıfırlaması ister ve yalnızca iş profili için yeni, geçici bir geçiş kodu oluşturur. 

## <a name="reset-a-passcode"></a>Geçiş kodu sıfırlama


1. [Azure Portal](https://portal.azure.com) aşağıdaki rollerden biriyle oturum açın: Azure Active Directory genel yönetici, Azure Active Directory Intune Hizmet Yöneticisi, yardım masası Işleci veya rol yöneticisi.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir cihaz seçin ve sonra da **...Diğer** öğesini seçin. Ardından **Geçiş kodunu kaldır** cihaz uzak eylemini seçin.

## <a name="reset-android-work-profile-passcodes"></a>Android iş profili geçiş kodlarını sıfırlama

İş profili ile kaydolmuş desteklenen Android Kurumsal cihazları, yeni bir yönetilen profil kilidi açma parolası veya son kullanıcı için bir yönetilen profil sınaması alır.

Sürüm 8.x veya sonrasını çalıştıran ve bir iş profili ile kayıtlı Android Kurumsal cihazlarda, kayıtları tamamlandıktan hemen sonra sıfırlama geçiş kodlarını etkinleştirmeleri için son kullanıcılara bildirim gönderilir. Bir iş profili parolası gerekli ve ayarlıysa bildirim görüntülenir. Geçiş kodu girildikten sonra bildirim kaybolur.


## <a name="remove-ios-passcodes"></a>iOS geçiş kodlarını kaldırma

Geçiş kodları sıfırlanmak yerine iOS cihazlardan kaldırılır. Ayarlı bir geçiş kodu uyumluluk ilkesi varsa, cihaz kullanıcıdan Ayarlar'da yeni bir geçiş kodu ayarlamasını ister.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz eylemin durumunu görmek için **Cihazlar**’da, **Cihaz eylemleri**’ni seçin.