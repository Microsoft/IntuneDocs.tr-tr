---
title: "Intune kullanım örneği senaryosu gereksinimlerini belirleme | Microsoft Docs"
description: "Bu makale bir Microsoft Intune yalnızca bulut uygulaması için Intune kullanım örneğini ve alt kullanım örneği senaryosu gereksinimlerini belirlemeye yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Intune kullanım örneği senaryosu gereksinimlerini belirleme

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bu bölümde, her kullanım örneği senaryosu içindeki tüm kuruluş grupları için gereksinimleri belirlersiniz. Bu süreç sonunda mimari ve tasarım, ekleme ve dağıtım gibi diğer Intune dağıtım planlama alanlarına daha iyi hazırlanmanız mümkün olacaktır. Intune dağıtım projenizle ilgili olası boşlukları ve zorlukları da tanımlamanıza yardımcı olacaktır.

Kullanım örneği/alt kullanım örneği senaryolarınızın her biri ve bunlarla ilişkili kuruluş grupları ve mobil cihaz platformları için farklı gereksinimler kümesine sahip olabilirsiniz. Örneğin kurumsal kullanım örneği senaryosu gereksinimleriniz, daha az kısıtlayıcı ayarlar gerektiren (örneğin 4 karakterli PIN, buluta yedeklemeye izin verme) “Kendi cihazını getir” (KCG) kullanım örneği senaryosuna göre daha kısıtlayıcı cihaz ayarlarıyla (örneğin 6 karakterli PIN, buluta yedeklemeyi devre dışı bırakma) Intune’a cihaz kaydı yapılmasını gerektirebilir.

Ayrıca, kurumsal kullanım örneği senaryosu için farklı gereksinimler kümesine (Örneğin PIN ayarları, Wi-Fi veya VPN profili, dağıtılan uygulamalar) sahip kuruluş gruplarınız olabilir. Ek olarak, gereksinimleriniz mobil cihaz platformunun yetenekleri (örneğin parmak izi okuyucu, e-posta profili) tarafından belirlenmiş olabilir.

Her bir kullanım örneği/alt kullanım örneği senaryosu, kuruluş grubu ve mobil cihaz platformu için farklı gereksinimler kümesini gösteren kuruluş kullanım örneği gereksinimlerine birkaç örneği aşağıda bulabilirsiniz. Kuruluşunuzun kullanım örneği gereksinimlerini girmek için aşağıdaki tabloyu da kullanabilirsiniz:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Gruplar** | **Cihaz işletim sistemi platformları** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Kurumsal | Bilgi Çalışanı | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, Profiller, Uygulamalar |                                                          
| Kurumsal | Yöneticiler | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, Profiller, Uygulamalar |                                                         
| Kurumsal | Bilgi noktası | Perakende | Android | Cihaz ayarları, Profiller, Uygulamalar |
| KCG | Bilgi Çalışanı | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, Profiller, Uygulamalar |                                                         
| KCG | Yöneticiler | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, Profiller, Uygulamalar |

## <a name="examples-of-requirements"></a>Gereksinim örnekleri

Yukarıdaki tabloda bahsedilen "Gereksinimler" sütununda kullanılabilecek birkaç örnek daha verelim:

- **Güvenli e-posta**
    - Exchange Online / Şirket İçi Exchange için koşullu erişim
    - Outlook uygulaması koruma ilkeleri
<br></br>
- **Cihaz ayarları**
    - Dört, altı karakterli PIN ayarı
    - Bulut yedeklemeyi kısıtla
<br></br>
- **Profiller**
    - Wi-Fi
    - VPN
    - e-posta (Windows 10 mobile)
<br></br>
- **Uygulamalar**
    - Uygulama koruma ilkeleriyle Office 365
    - Uygulama koruma ilkeleri ile iş kolu (LOB)

## <a name="next-section"></a>Sonraki Bölüm

Sonraki bölümde [bir Intune dağıtımı planı geliştirme](section-4-develop-a-rollout-plan.md) hakkında yönergeler sağlanır.



<!--HONumber=Dec16_HO5-->


