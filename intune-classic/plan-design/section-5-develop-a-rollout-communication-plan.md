---
title: "Intune dağıtımı iletişim planı geliştirme | Microsoft Docs"
description: "Bu makale, Microsoft Intune yalnızca bulut tasarımı ve uygulaması için bir dağıtım iletişim planı oluşturmaya yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 393ebe75-d001-485a-b81c-6361c8b5e6ee
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 959b1a02fe86a3b8f2aacb31483f942b51e30aab
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="develop-an-intune-rollout-communication-plan"></a>Intune dağıtımı iletişim planı geliştirme

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Kuruluşun Intune yönetimi için hedeflenecek gruplarından, Intune dağıtımı zaman çizelgelerinden ve kayıt yaklaşımlarından Intune dağıtım planı geliştirme adlı önceki bölümde bahsetmiştik. Şimdi, Intune dağıtımınız için bir iletişim planı geliştirmeniz gerekir. Intune dağıtımı iletişim planınız dört alanı içermelidir:

-   İletilecek bilgiler

-   İletişim için kullanılan teslim yöntemi

-   İletişim kurulacak kişiler

-   İletişim için zaman çizelgesi

Her alanı daha ayrıntılı bir şekilde inceleyeceğiz.

## <a name="what-needs-to-be-communicated"></a>Neyin iletilmesi gerekir?

Hangi bilgilerin iletileceği, iletmekte olduğunuz Intune dağıtım sürecine dayalı olacaktır. Bazı kuruluşlar kendi kuruluş gruplarına ve kullanıcılarına Intune dağıtımının başlatılması, ön kayıt ve kayıt sonrası aşamalarından oluşan dalgalar halinde iletişim sağlamayı tercih edebilir. Her dalgada iletilebilecek bilgi türlerinden bahsedelim.

**Başlangıç dalgası:** Intune’un ne olduğu, neden Intune’u benimsediklerini (kuruluşa ve kullanıcılara sağlanan yararlar gibi) ve dağıtım ve sunum çalışmasının yüksek düzey planı gibi Intune projesini tanıtan geniş kapsamlı iletişimlerdir.

**Kayıt öncesi dalgası**: Intune ve tamamlayıcı teklifler (örneğin Office, Outlook, OneDrive), kullanıcı kaynakları ve kuruluş gruplarının/kullanıcılarının ne zaman Intune edineceğine ilişkin belirli zaman çizelgeleri hakkında geniş kapsamlı iletişimlerdir.

**Kayıt dalgası:** Intune alması planlanmış kuruluş gruplarını/kullanıcılarını hedefleyen, kullanıcılara Intune almaya hazır olduklarını bildiren ve kayıt yönergeleri sağlayan, ayrıca yardım istemek veya soru sormak için irtibat bilgileri de veren iletişimlerdir.

**Kayıt sonrası dalgası:** Intune'a kaydedilmiş kuruluş gruplarını/kullanıcılarını hedefleyen, kullanıcıya yardımcı olabilecek ek kaynaklar sağlayan, kayıt öncesi ve sonrasındaki deneyimleri hakkında geri bildirim toplayan iletişimlerdir.

## <a name="communication-delivery-methods"></a>İletişim teslim yöntemleri

Intune dağıtım bilgilerini hedeflediğiniz gruplara ve kullanıcılara iletmek için kullanabileceğiniz çeşitli teslim yöntemleri vardır. Aşağıda iletişim teslim yöntemleri ve bunların birlikte kullanılabileceği dalgaya ilişkin bazı örnekler verilmiştir:

-   Kuruluş genelinde yüz yüze ve/veya Skype görüşmeleri Başlangıç dalgası için kullanılır

-   E-posta kayıt öncesi, kayıt ve kayıt sonrası dalgaları için kullanılır

-   Kuruluş web siteleri, tüm dalgalar için kullanılır

-   Yammer ve posterler/el ilanları, Başlangıç ve kayıt öncesi dalgaları için kullanılır

## <a name="communications-timeline"></a>İletişim zaman çizelgesi

Neyin iletileceği ve iletişim için kullanılacak yöntem belirlendikten sonraki adım, iletişimin ne zaman ve kime iletileceğini içeren iletişim zaman çizelgelerini belirlemektir. Örneğin, ilk Intune proje başlangıç iletişimi tüm kuruluşu veya bir alt kümeyi hedefleyebilir ve Intune dağıtımı başlamadan birkaç hafta önce gerçekleştirilebilir. Bundan sonra, bilgiler dalgalar halinde kuruluş gruplarına ve kullanıcılarına, Intune dağıtım zaman çizelgelerine uygun şekilde iletilebilir. Aşağıda, üst düzey bir Intune dağıtımı iletişim planı örneği verilmiştir:

  | **İletişim planı** | **Temmuz** | **Ağustos** | **Eylül** | **Ekim** |
|:---:|:---:|:---:|:---:|:---:|
| Dalga 1  | Tümü |  |  |  |                                                         
| Başlangıç toplantısı | İlk hafta |  |  |  |                                                         
| Dalga 2 | BT | Satış ve Pazarlama | Perakende | İK, Finans ve Yöneticiler |
| Kayıt Öncesi E-postası 1 | İlk hafta | İlk hafta | İlk hafta | İlk hafta |
| Dalga 3 | BT | Satış ve Pazarlama | Perakende | İK, Finans ve Yöneticiler |
| Kayıt Öncesi E-postası 2 | İkinci hafta | İkinci hafta | İkinci hafta | İkinci hafta |
| Dalga 4 | BT | Satış ve Pazarlama | Perakende | İK, Finans ve Yöneticiler |
| Kayıt e-postası | Üçüncü hafta | Üçüncü hafta | Üçüncü hafta | Üçüncü hafta |
| Dalga 5 | BT | Satış ve Pazarlama | Perakende | İK, Finans ve Yöneticiler |
| Kayıt sonrası e-postası | Dördüncü hafta | Dördüncü hafta | Dördüncü hafta | Dördüncü hafta |

## <a name="next-section"></a>Sonraki bölüm

Sonraki bölümde [destek planı geliştirme](section-6-develop-a-support-plan.md) konusunda yönergeler sağlanır.

