---
title: Microsoft Intune - Azure’da ilkeleri kullanmaya başlama | Microsoft Docs
description: Şirket verilerinin korunmasına yardımcı olmak ve son kullanıcıların şirket kaynaklarına erişirken kullandıkları cihazları yönetmek için ilkeler oluşturun. Daha sonra ilkeleri gruplara atayın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271533"
---
# <a name="get-started-with-creating-policies"></a>Özel ilkeler oluşturmaya başlama

Intune ilkeleri, cihaz kaydetmek ve bu cihazların şirket ilkeleriyle uyumlu olduğundan emin olmak için harika bir yoldur. Uyumluluk ilkeleri, şirkete ait bilgi noktası gibi özelleştirilmiş cihaz türlerini ve kişisel (Kendi Cihazını Getir) cihazları, tabletleri ve kullanıcısız cihazları yönetmenize yardımcı olur.

![Çok az veriyle uyumluluk panosu](/intune/media/generic-compliance-dashboard.png)

Mobil cihazlar, aşağıdakiler gibi uyumluluk ilkeleri kullanılarak yönetilebilir:

* Bir kullanıcının Intune’a kaydettiği cihaz sayısını düzenleme
* Cihaz düzeyinde şifreleme, parola uzunluğu ve kamera kullanımı gibi cihaz ayarlarını yönetme
* Uygulamalar, e-posta profilleri, VPN profilleri ve daha fazlasını sunma
* Güvenlik uyumluluk ilkeleri için cihaz düzeyinde ölçütleri değerlendirme

Uyumluluk ilkeleri iOS, Android, Windows vb. gibi her platform için oluşturulur. Bu alıştırma için iOS kullanın. iOS cihazları için aşağıdaki ilkeler mevcuttur:

* PIN veya parola yapılandırması
* Cihaz şifrelemesi
* Jailbreak uygulanmış cihaz
* E-posta profili
* En düşük işletim sistemi sürümü
* En yüksek işletim sistemi sürümü

## <a name="create-a-policy"></a>İlke oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**'u seçin.
4. İlke için bir **Ad** ve **Açıklama** girin. 
5. **Platform** olarak **iOS**’u seçin.
6. **Ayarlar**’da **Sistem Güvenliği**’ni seçin, sonra **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli** olarak belirtin. 

    Ayrıca, şunlar gibi diğer kuralları da ayarlayabilirsiniz: 
    - **En düşük parola uzunluğu**
    - **Gerekli parola türü**
    - **Paroladaki alfasayısal olmayan karakter sayısı**
    
    İlkenizi ayarlamayı tamamladığınızda **Tamam**’ı seçin.
  
7. **İlke oluştur**’a geri dönün ve **Oluştur**’u seçin. Bu adım, ilkeyi oluşturur ve ilkenizi **Cihaz uyumluluğu** > **İlkeler**’de listeler.
8. Yeni ilkenizi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
Mevcut Azure AD güvenlik gruplarınızı görmek için Seçili gruplar’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

Kaydettiğiniz cihazınız, yeni şirket ilkesiyle uyumlu olmak için birkaç dakika sonra güncelleştirilmiş bir parola ister. Güncelleştirmeyi **iOS için Şirket Portalı**’nda el ile denetleyebilirsiniz. Şirket Portalı uygulamasını açın, cihaz adını seçin ve daha sonra **Eşitle**’yi seçin.

> [!NOTE]
> Bir dinamik cihaz grubuna uygulanan yeni ilkelerin gruptaki tüm cihazlara uygulanması sekiz saati bulabilir.

## <a name="next-steps"></a>Sonraki adımlar

[Cihazları kaydetmeye başlama](get-started-enroll.md) - Bir iOS cihazın tam kayıt deneyimini yaşayarak kayıt deneyimi hakkında bilgi edinin.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
* [Intune ile koşullu erişim ilkelerini kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
