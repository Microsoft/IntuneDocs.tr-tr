---
title: iOS cihaz kayıt deneyimini anlama
titlesuffix: Microsoft Intune
description: Bir iOS cihazın tam kayıt deneyimini yaşayarak kayıt deneyimi hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a31722bbaf43b099c42673e4a807a8e896bf1fd2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="understand-the-users-experience-enrolling-an-ios-device"></a>Kullanıcının iOS cihazı kaydetme deneyimini anlama

Microsoft Intune, şirket verilerinizi korurken iş gücünüze mobil cihazlar sağlamaya yardımcı olur. Son kullanıcılarınız Intune ile yönetici konsolundan çok cihazlarından etkileşimde bulunacakları için kayıt deneyimine hakim olduğunuzdan emin olmalısınız. Böylece deneyimi, özenle oluşturulmuş uyumluluk ilkeleriyle birleştirip kullanıcılarınıza kolaylık sağlayabilirsiniz. Bu özellikle önemli bir konudur çünkü kullanıcılarınız, yönetici olarak sizin hangi bilgileri görebildiğinizden haberdar olacaktır:

| BT’nin göremedikleri | BT’nin görebildikleri |
|---|---|
| Arama ve web tarama geçmişi | Model |
| Konum | Seri numarası |
| Kişisel e-posta | İşletim sistemi sürümü |
| SMS mesajları | Uygulama adları |
| Kişiler | Sahip |
| Kişisel hesaplarınızın parolaları | Cihaz adı |
| Takvim etkinlikleri | Üretici (Apple tarafından üretilmeyen cihazlar için) |
| Fotoğraflar uygulamasında veya film rulosunda yer alanları da içeren resimler | Telefon numarası (İş cihazları için numaranın tamamı. Kişisel cihazlar için yalnızca son dört rakamı.) |

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

## <a name="next-steps"></a>Sonraki adımlar

[Uygulama eklemeye başlama](get-started-apps.md) - Çalışanlarınızın işlerini yapabilmeleri için uygulamalar bulun ve bunları cihazlara ekleyin.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune için kayıt seçenekleri](enrollment-options.md)
* [Intune ile kendi cihazını getirmeyi etkinleştirme](byod-enable.md)
* [Son kullanıcılarınızı kayıt ve cihaz yönetimi hakkında bilgilendirme](end-user-educate.md)
