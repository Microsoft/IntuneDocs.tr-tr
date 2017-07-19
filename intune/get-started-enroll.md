---
title: "Cihazları kaydetmeye başlama"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36e658cebdfd23547e3c376124289046f81acc1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-enrolling-devices"></a>Cihazları kaydetmeye başlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Şirket Portalı uygulamasını gösteren iOS cihaz. kayıt sürecinde kullanıcıya sunulan ilk ekran gösterilmektedir.](/intune-user-help/media/ios-enroll-1a-comp-access-setup.png)

Microsoft Intune, şirket verilerinizi korurken iş gücünüze mobil cihazlar sağlamaya yardımcı olur. Son kullanıcılarınız Intune ile yönetici konsolundan çok cihazlarından etkileşimde bulunacakları için kayıt deneyimine hakim olduğunuzdan emin olmalısınız. Böylece deneyimi, özenle oluşturulmuş uyumluluk ilkeleriyle birleştirip kullanıcılarınıza kolaylık sağlayabilirsiniz. Bu özellikle önemli bir konudur çünkü kullanıcılarınız, yönetici olarak sizin hangi bilgileri görebildiğinizden haberdar olacaktır:

## <a name="what-it-cannot-see"></a>BT’nin göremedikleri
* Arama ve web tarama geçmişi
* Konum
* Kişisel e-posta
* SMS mesajları
* Kişiler
* Kişisel hesaplarınızın parolaları
* Takvim etkinlikleri
* Fotoğraflar uygulamasında veya film rulosunda yer alanları da içeren resimler

## <a name="what-it-can-see"></a>BT’nin görebildikleri
* Model
* Seri numarası
* İşletim sistemi sürümü
* Uygulama adları
* Sahip
* Cihaz adı
* Üretici (Apple tarafından üretilmeyen cihazlar için)
* Telefon numarası (İş cihazları için numaranın tamamı. Kişisel cihazlar için yalnızca son dört rakamı.)

## <a name="how-do-i-enroll-a-device"></a>Cihazlar nasıl kaydedilir?

Cihaz kaydı, şirket kaynaklarına erişirken pek çok son kullanıcının ilk deneyimleyeceği şeydir. [Bu deneyimini anlamak](end-user-educate.md), olası bir kötü deneyimi önlemeye yardımcı olabilir.

1. **App Store**’u açın ve **Intune Şirket Portalı** için arama yapın.
2. **Microsoft Intune Şirket Portalı** uygulamasını indirin.
3. **Şirket Portalı** uygulamasını açın, sınama kullanıcınızın e-posta adresini ve parolasını girip **Oturum aç**’a dokunun.
4. Geçici şifreyi yeni bir şifreye güncelleştirin.
5. **Şirket Erişimi Kurulumu** sayfasında, **Cihaz Kaydı**’na dokunun.
6. **Cihazınızı neden kaydetmelisiniz?** sayfasında, bir kullanıcının cihazını kaydettiğinde neler yapabileceğini okuyun ve sonra **Devam**’a dokunun.
7. Bir kullanıcının cihazını kaydettiğinde erişebileceklerinin listesini inceleyin ve sonra **Devam**’a dokunun.
8. BT yöneticilerinin bir cihazda neleri görüp göremeyeceğini inceleyin ve sonra **Devam**’a dokunun.
9. **Sıradaki** sayfasında kayıt sırasında ne olduğunu okuyun ve ardından **Kaydet**’e dokunun.
10. **Profil Yükle** sayfasında **Yükle**’ye dokunun ve istenirse cihaz geçiş kodunu girin.
11. **Yükle**’ye dokunun.
12. Uyarıyı okuduğunuzu göstermek için **Yükle**’ye tekrar dokunun.
13. Açılan **Uyarı** penceresinde **Güven**’e dokunun.
14. Ekran değişerek profilin yüklenmesinin tamamlandığını gösterdiğinde, **Bitti**’ye dokunun.
15. Ekranda bir “Cihaz kaydediliyor” iletisi görüntülenir ve daha sonra cihazın başarıyla kaydedildiği yazar. Bir açılır pencerede, sayfayı Şirket Portalı’nda açmak için izin istenecektir. **Aç**’a dokunun.
16. **Şirket Erişimi Kurulumu** ekranına dönersiniz. Hiçbir sınama ilkesi ayarlamadıysanız cihaz uyumlu olarak görünecektir. Sınama ilkeleriniz varsa **Cihaz Uyumluluğu**’na dokunarak cihazı güvenli hale getirmek için yapmanız gereken şeyler olduğunu görebilirsiniz.
