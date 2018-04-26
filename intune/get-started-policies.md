---
title: Microsoft Intune’daki ilkeleri kullanmaya başlama
titlesuffix: ''
description: Şirket verilerinin korunmasına yardımcı olmak ve son kullanıcıların şirket kaynaklarına erişirken kullandıkları cihazları yönetmek için ilkeler oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b8bffd0435988cc59c5c0e4d754b861729d466ae
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-with-creating-policies"></a>Özel ilkeler oluşturmaya başlama

Intune ile çalışmaya başlamanın ana hedeflerinden biri, cihaz ilkeleriyle uyumlu olduklarından emin olmak için cihazları kaydetmektir. Uyumluluk ilkeleri, yalnızca şirkete ait bilgi noktası gibi özelleştirilmiş cihaz türlerini değil ayrıca kişisel (Kendi Cihazını Getir) cihazları, tabletleri ve kullanıcısız cihazları da yönetmenize yardımcı olur.

![Çok az veriyle uyumluluk panosu](/intune/media/generic-compliance-dashboard.png)

Uyumluluk ilkelerini kullanarak aşağıdaki alanlarda mobil cihazları yönetin:

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

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Cihaz uyumluluğu**'nu seçin.
4. **Cihaz uyumluluğu** bölmesinde **İlkeler**'i seçin.
5. **İlke Oluştur**'u seçin, sonra **Adı** ve **Açıklama** gibi ayrıntıları girin. 
6. **Platform** olarak **iOS**'u seçin.
6. **Ayarlar**'da **Sistem Güvenliği**'ni seçin, sonra **Mobil cihazların kilidini açmak için parola gerektir**'de **Gerekli**'ye geçin. **En düşük parola uzunluğu**, **Gerekli parola türü** ve **Paroladaki alfasayısal karakter sayısı** gibi başka kurallar da koyabilirsiniz. İlkenizi ayarlamayı tamamladığınızda **Tamam**'ı seçin.
7. **İlke oluştur** bölmesine dönün ve **Oluştur**'u seçin.
8. İlke oluşturulduktan sonra ilkeyi sınama grubunuza atamak için **Atamalar**'ı seçin. İçinde sınama kullanıcınız olması gereken sınama grubunuzu seçin, sonra **Kaydet**'e tıklayarak ilkeyi bu gruba atayın.
9. Birkaç dakika bekleyin; kaydettiğiniz cihaz, kurumsal ilkeyle uyumlu kalmak için güncelleştirilmiş bir parola gerektiğini size bildirir. Bunu, **iOS için Şirket Portalı uygulaması**'nda cihaz adına, sonra **Eşitle** düğmesine dokunarak el ile de denetleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Cihazları kaydetmeye başlama](get-started-enroll.md) - Bir iOS cihazın tam kayıt deneyimini yaşayarak kayıt deneyimi hakkında bilgi edinin.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
* [Intune ile koşullu erişim ilkelerini kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md)
