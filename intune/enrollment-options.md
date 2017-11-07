---
title: "Intune için kayıt seçenekleri"
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: 22efa23e989ed949d22c3c25b2ea4d37559b0a25
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2017
---
# <a name="enrollment-options-for-intune"></a>Intune için kayıt seçenekleri

Bir Intune yöneticisi olarak kullanıcılara yardımcı olmak ve Intune yeteneklerini etkinleştirmek için cihaz kaydını yapılandırabilirsiniz.  Intune, aşağıdaki kayıt seçeneklerini sunar:

## <a name="terms-and-conditions"></a>hüküm ve koşullar

Cihazlarını kaydetmek ve uygulama ve e-posta gibi şirket kaynaklarına erişmek üzere Şirket Portalı’nı kullanabilmeleri için önce şirketin hüküm ve koşullarını kabul etmelerini zorunlu tutabilirsiniz. Hüküm ve koşulların yapılandırması isteğe bağlıdır. [Hüküm ve koşullar](terms-and-conditions-create.md) hakkında daha fazla bilgi edinin.

## <a name="enrollment-restrictions"></a>Kayıt kısıtlamaları

Cihaz kaydını şunlara göre kısıtlayabilirsiniz:
- Cihaz platformu
- Kişi başına düşen cihaz sayısı
- Kişisel cihazları engelleme

[Kayıt kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

## <a name="enable-apple-device-enrollment"></a>Apple cihaz kaydını etkinleştirme

iOS ve macOS cihaz kaydı için bir MDM anında iletme sertifikası gereklidir. [MDM anında iletme sertifikaları](apple-mdm-push-certificate-get.md) hakkında daha fazla bilgi edinin.

## <a name="corporate-identifiers"></a>Kurumsal tanımlayıcılar

Şirkete ait cihazları belirlemek için uluslararası mobil cihaz tanımlayıcısı (IMEI) numaralarını ve seri numaraları listeleyebilirsiniz. [Kurumsal tanımlayıcılar](corporate-identifiers-add.md) hakkında daha fazla bilgi edinin.
## <a name="multi-factor-authentication"></a>Çok faktörlü kimlik doğrulaması

Kullanıcıların bir cihaz kaydederken telefon, PIN veya biyometrik veri gibi ilave doğrulama yöntemleri kullanmasını gerekli kılabilirsiniz. [Çok faktörlü kimlik doğrulaması](multi-factor-authentication.md) hakkında daha fazla bilgi edinin.

## <a name="device-enrollment-manager"></a>Cihaz kayıt yöneticisi
Kullanıcıları, cihaz kayıt yöneticileri yapabilirsiniz.  DEM kullanıcıları, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetebilir. Cihaz kayıt yöneticisi (DEM) hesabı, 1.000’e kadar cihazı kaydedebilir. [Cihaz kayıt yöneticileri](device-enrollment-manager-enroll.md) hakkında daha fazla bilgi edinin.

## <a name="device-categories"></a>Cihaz kategorileri

Tanımladığınız cihaz kategorilerine dayanarak cihazları gruplara otomatik olarak ekleyebilirsiniz. Cihazları gruplar halinde düzenlemek, bu cihazları yönetmenizi kolaylaştırır. [Cihaz kategorileri](device-group-mapping.md) hakkında daha fazla bilgi edinin.
