---
title: "İlkelerle çalışmaya başlama"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd3279288fe5ea1fec16224c70b4562fcf53555d
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-policies"></a>İlkelerle çalışmaya başlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune ile çalışmaya başlamanın ana hedeflerinden biri, kurumsal ilkelerle uyumlu olduklarından emin olmak için cihazları kaydetmektir. Uyumluluk ilkeleri, yalnızca şirkete ait bilgi noktası gibi özelleştirilmiş cihaz türlerini değil ayrıca kişisel (Kendi Cihazını Getir) cihazları, tabletleri ve kullanıcısız cihazları da yönetmenize yardımcı olur.

![Çok az veriyle uyumluluk panosu](/intune/media/generic-compliance-dashboard.png)

Uyumluluk ilkeleri, mobil cihazlara aşağıdaki yönetim özelliklerini kazandırır:

* Her kullanıcının kaydettiği cihaz sayısını denetleme
* Cihaz ayarlarını (cihaz düzeyinde şifreleme, parola uzunluğu, kamera kullanımı gibi) yönetme
* Uygulama, e-posta profilleri, VPN profilleri vb. sunmak.
* Güvenlik uyumluluk ilkeleri için cihaz düzeyinde ölçütleri değerlendirme

Uyumluluk ilkelerini her platform için ayrı oluşturursunuz. Bu alıştırmada biz iOS kullanacağız. iOS cihazları için aşağıdaki ilkeler mevcuttur:

* PIN veya parola yapılandırması
* Cihaz şifrelemesi
* Jailbreak uygulanmış cihaz
* E-posta profili
* En düşük işletim sistemi sürümü
* En yüksek işletim sistemi sürümü

__Nasıl ilke oluşturulur?__

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Kaynak ara**'da **Intune**'u arayın.
3. **Cihaz uyumluluğu**'nu seçin.
4. **Cihaz uyumluluğu** dikey penceresinde **İlkeler**'i seçin.
5. **İlke Oluştur**'u seçin, sonra **Adı** ve **Açıklama** gibi ayrıntıları girin. **Platform** olarak **iOS**'u seçin.
6. **Ayarlar**'da **Sistem Güvenliği**'ni seçin, sonra **Mobil cihazların kilidini açmak için parola gerektir**'de **Gerekli**'ye geçin. **En düşük parola uzunluğu**, **Gerekli parola türü** ve **Paroladaki alfasayısal karakter sayısı** gibi başka kurallar da koyabilirsiniz. İlkenizi ayarlamayı tamamladığınızda **Tamam**'ı seçin.
7. **İlke oluştur** dikey penceresine dönün ve **Oluştur**'u seçin.
8. İlke oluşturulduktan sonra ilkeyi sınama grubunuza atamak için **Atamalar**'ı seçin. İçinde sınama kullanıcınız olması gereken sınama grubunuzu seçin, sonra **Kaydet**'e tıklayarak ilkeyi bu gruba atayın.
9. Birkaç dakika bekleyin; kaydettiğiniz cihaz, kurumsal ilkeyle uyumlu kalmak için güncelleştirilmiş bir parola gerektiğini size bildirir. Bunu, **iOS için Şirket Portalı uygulaması**'nda cihaz adına, sonra **Eşitle** düğmesine dokunarak el ile de denetleyebilirsiniz.
