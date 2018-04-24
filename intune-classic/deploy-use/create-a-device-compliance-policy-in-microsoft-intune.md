---
title: Cihaz uyumluluğu ilkesi oluşturma
description: Şirket verilerinize erişirken kullanılan mobil cihazların ve bilgisayarların güvenliğini sağlamaya yardımcı olması için bir uyumluluk ilkesi oluşturun.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/12/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed6f66747364debd89661d78bcf3b002b1c8a9b6
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-device-compliance-policy-in-microsoft-intune"></a>Microsoft Intune’da cihaz uyumluluk ilkesi oluşturma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında, bir cihazın uyumlu olarak kabul edilmek için uyması gereken bir uyumluluk ilkesi oluştururken kullanabileceğiniz adımlar açıklanır.

##  <a name="step-1-add-a-new-policy"></a>1. Adım: Yeni bir ilke ekleme
  [Microsoft Intune yönetim konsolu](https://manage.microsoft.com)’nda, **İlke** &gt; **Uyumluluk İlkeleri** &gt; **Ekle**’yi seçin.

  ![Intune yönetim konsolunda uyumluluk ilkesi sayfasını ve sayfanın en üstündeki menüde ekle seçeneğini gösteren ekran görüntüsü](./media/intune-sa-3a-add-compliance-policy.png)

##  <a name="step-2--configure-settings"></a>2. Adım: Ayarlarını yapılandırma
**İlke Oluştur** sayfasında gereken ayarları etkinleştirin:
  -   Parola ve şifreleme gibi Sistem güvenlik ayarları.
  -   Cihazın yazılım kilidinin kırılmış olup olmadığı veya Windows cihaz durumu kanıtlama hizmeti tarafından sağlıklı olarak raporlanıp raporlanmadığı gibi cihaz durumu ayarları.
  -   Gerekli en düşük işletim sistemi sürümü veya izin verilen en yüksek işletim sistemi sürümü gibi cihaz özelliği ayarları.
![İlke Oluştur sayfasının Genel sekmesi ](./media/intune-sa-3b-create-policy.png)


##  <a name="step-3-save-the-policy"></a>3. Adım: İlkeyi kaydetme
İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

İlkeyi kaydettikten hemen sonra dağıtma seçeneği sağlanır veya daha sonra dağıtmayı seçebilirsiniz. Yeni ilke, **İlke** çalışma alanının **Uyumluluk İlkeleri** düğümünde görüntülenir.

##  <a name="step-4-set-the-compliance-status-validity-period"></a>4. Adım: Uyumluluk durumu geçerlilik süresini ayarlama
Cihaz uyumsuz olarak kabul edilmeden önce cihazın iade edilmesi gereken zamanı belirtmek için, uyumluluk ilkesi ayarlarına gidin ve süreyi güncelleştirin. Varsayılan olarak 30 güne ayarlanmıştır.

![İlke menü çubuğunda uyumluluk ilkesi ayarları seçeneği](../media/mdm-compliance-policy-settings.png)

![Uyumluluk ilkesi iletişim kutusu](../media/mdm-ca-compliance-status-validity-period.png)

## <a name="supported-policy-settings"></a>Desteklenen ilke ayarları
Aşağıdaki tabloda uyumluluk ilkesi ayarları ve bunların desteklendiği platformlar listelenir.

-------------

|Ayar|iOS|Android|Windows|
|-----|----|-----|-----|
|Mobil cihazların kilidini açmak için bir parola gerektir|iOS 6 ve üzeri|Android 4.0 ve üzeri <br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri|
|Basit parolalara izin ver|iOS 6 ve üzeri|Desteklenmez|Windows Phone 8.1 ve üzeri|
|Parola uzunluğu alt sınırı|iOS 6 ve üzeri| Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri| Windows Phone 8.1 ve üzeri<br>Windows 8.1|
|Gerekli parola türü|iOS 6 ve üzeri|Yok|Windows Phone 8.1 ve üzeri <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Minimum karakter kümesi sayısı|iOS 6 ve üzeri|Yok|Windows Phone 8.1 ve üzeri <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Parola kalitesi|Yok|Android 4.0 ve üzeri <br>Samsung KNOX Standard 4.0 ve üzeri|Yok|
|Parola istenmeden önce geçen işlem yapılmayan dakika sayısı|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br>Windows RT ve Windows RT 8.1<br>Windows 8.1|
|Parola zaman aşımı (gün sayısı)|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br>Windows RT ve Windows RT 8.1<br>Windows 8.1|
|Parola geçmişini anımsa|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br>Windows RT ve Windows RT 8.1<br>Windows 8.1|
|Önceki parolaların yeniden kullanılmasını engelleme|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br>Windows RT ve Windows RT 8.1<br>Windows 8.1|
|Cihaz boş bir durumdan döndürüldüğünde parola iste| Yok| Yok|Windows 10 Mobile|
|Cihazda şifrelemeyi gerektir|Geçerli değil|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br> Windows 8.1|
|Cihazların sağlıklı olarak bildirilmesini gerektirme| Yok| Yok|Windows <br>Windows 10 Mobile|
|Cihazın Güvenliğinin kırılmamış olması veya yolda kök belirtilmemesi gerekir|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Yok|
|E-posta hesabı, Intune tarafından yönetilmelidir|iOS 6 ve üzeri|Yok| Yok|
|Intune tarafından yönetilmesi gereken e-posta profilini seçme|iOS 6 ve üzeri|Yok| Yok|
|Gereken en düşük işletim sistemi|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri| Windows Phone 8.1 ve üzeri<br>Windows 8.1|
|İzin verilen en yüksek işletim sistemi sürümü|iOS 6 ve üzeri|Android 4.0 ve üzeri<br>Samsung KNOX Standard 4.0 ve üzeri|Windows Phone 8.1 ve üzeri<br>Windows 8.1|

Her platformda desteklenen uyumluluk ayarları hakkında daha fazla bilgi edinmek için aşağıdakilerden birini seçin:
> [!div class="op_single_selector"]
> - [iOS cihazları için uyumluluk ilkesi ayarları](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Android cihazları için uyumluluk ilkesi ayarları](android-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows ve Windows Phone cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)


## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluk ilkesini dağıtma ve izleme](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Ayrıca bkz:
[Cihaz uyumluluk ilkelerine giriş](introduction-to-device-compliance-policies-in-microsoft-intune.md)
