---
title: Microsoft Intune - Azure’da Android bilgi noktası ayarlarını görüntüleme | Microsoft Docs
description: Android kurumsal bilgi noktası cihazlarını yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e43ab0d088edc87e814ad2c4317d7b7336d34d5
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312905"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Intune’da Android kurumsal bilgi noktası ayarları

Android bilgi noktası profilleri, aşağıdaki yapılandırma ayarlarını destekler. Bir profil oluştururken **Profil türü** > **Yalnızca Cihaz Sahibi** > **Cihaz kısıtlamaları**’nı seçtiğinizde bu ayarlar karşınıza çıkar. Bu ayarları görmek için bir Android kurumsal cihaz kısıtlama profilinde **Özellikler**’i, daha sonra **Yapılandır**’ı seçin.

## <a name="general-settings"></a>Genel ayarlar

- **Ekran yakalama**: Kullanıcıların cihaz ekranını yakalamalarını önlemek için **Engelle** olarak ayarlayın.
- **Kamera**: Cihazın kamerasını devre dışı bırakmak için **Engelle** olarak ayarlayın.
- **Varsayılan izin ilkesi**: Bu ayar, çalışma zamanı izin istekleri için varsayılan izin ilkesini tanımlar. Olası değerler şöyledir:
    - **Cihaz varsayılanı**: Cihazın varsayılan ayarını kullanın.
    - **İstem**: Kullanıcıdan izni onaylaması istenir.
    - **Otomatik olarak izin ver**: İzinler otomatik olarak verilir.
    - **Otomatik olarak reddet**: İzinler otomatik reddedilir.
- **Ses düzeyi değişiklikleri**: Kullanıcıların cihaz ses düzeyini değiştirmesini önlemek için **Engelle** olarak ayarlayın.
- **Silme**: Kullanıcıların cihazı silmesini önlemek için **Engelle** olarak ayarlayın.
- **Güvenli önyükleme**: Kullanıcıların cihazı güvenli moda önyüklemesini önlemek için **Engelle** olarak ayarlayın.
- **Durum çubuğu**: Kullanıcıların bildirimler ve hızlı ayarlar dahil olmak üzere durum çubuğuna erişmesini önlemek için **Engelle** olarak ayarlayın.
- **Wi-Fi ayar değişiklikleri**: Kullanıcıların cihaz sahibi tarafından oluşturulan Wi-Fi yapılandırmalarını değiştirmesini önlemek için **Engelle** olarak ayarlayın. Kullanıcılar kendi Wi-Fi yapılandırmalarını oluşturabilir.
- **Wi-Fi erişim noktası yapılandırması**: Kullanıcıların Wi-Fi yapılandırması oluşturmasını veya düzenlemesini önlemek için **Engelle** olarak ayarlayın.
- **Hata ayıklama özellikleri**: Kullanıcıların hata ayıklama özellikleri kullanmasına izin vermek için **İzin Ver** olarak ayarlayın.
- **Mikrofonu ayarlama**: Kullanıcıların mikrofon sesini ayarlamasını veya kapatmasını önlemek için **Engelle** olarak ayarlayın.
- **E-postaları silmeye karşı koruma**: Silme işleminden sonra cihazın kilidini açabilecek e-posta adreslerini (noktalı virgülle ayrılmış) tanımlamak için **Google hesabı e-posta adresleri**’ni seçin. E-posta belirtilmezse, silme işleminden sonra cihazın kilidini herkes açabilir.
- **Ağ kaçış noktası**: Ağ kaçış noktası özelliğinin açılmasına izin vermek için **Etkinleştir** olarak ayarlayın. Önyükleme zamanında bir ağ bağlantısı yapılamazsa kaçış noktası, cihaz ilkesini yenilemek için kullanıcıdan geçici olarak bir ağa bağlanmasını ister. Bu ilke uygulandıktan sonra geçici ağ unutulur ve cihaz önyüklemeye devam eder. Böylece son ilkede uygun bir ağ yoksa ve cihaz bir uygulamaya görev kilitleme modunda önyükleniyorsa veya kullanıcı cihaz ayarlarına ulaşamıyorsa bir ağa bağlanamama sorunu ortadan kalkar.
- **Bilinmeyen kaynaklardan yüklemeye izin ver**: Kullanıcıların bilinmeyen kaynaklardan yüklemesine izin vermek için **İzin Ver** olarak ayarlayın.
- **Sistem güncelleştirmesi**: Cihazın havadan güncelleştirmeleri nasıl yöneteceğini belirlemek için bir seçenek belirtin:
    - **Cihaz Varsayılanı**: Cihazın varsayılan ayarını kullanın.
    - **Otomatik**: Güncelleştirmeler otomatik olarak yüklenir.
    - **Ertelenmiş**: Güncelleştirmeler sonraki bir tarihe ertelenir.
    - **Bakım penceresi**: Bir bakım penceresi ile kullanıcılardan güncelleştirmeyi onaylamaları istenir.

## <a name="kiosk-settings"></a>Bilgi noktası ayarları

- **Bilgi noktası modu**: Cihazın tek bir uygulama mı yoksa birden fazla uygulama mı çalıştırabileceğini belirtir. Daha fazla bilgi için bkz. [Android cihazları için bilgi noktası ayarları](android-kiosk-settings.md).
    - **Tekli uygulama bilgi noktası**: Kullanıcılar yalnızca bir uygulamaya erişebilir.
    - **Çoklu uygulama bilgi noktası**: Kullanıcılar sınırlı bir grup uygulamaya erişebilir.

## <a name="device-password-settings"></a>Cihaz parola ayarları

- **Tuş Koruması**: Kullanıcıların cihazda Tuş Koruması kullanmasını önlemek için **Devre Dışı Bırak** olarak ayarlayın.
- **Gerekli parola türü**: Cihaz için gerekli parola türünü tanımlayın.
- **En düşük parola uzunluğu**: Cihaz için gerekli en düşük parola uzunluğunu tanımlayın.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihazın silinmesi için kaç başarısız oturum açma denemesi yapılması gerektiğini belirtin.

## <a name="power-settings"></a>Güç ayarları

- **Ekran kilitlenme süresi**: Cihaz kilitlenmeden önce boşta geçmesi gereken süreyi belirtin.
- **Cihaz prize takılıyken ekran açık**: Cihaz prize takılıyken hangi güç kaynaklarının ekranın açık kalmasına neden olacağını seçin.

## <a name="users-and-accounts-settings"></a>Kullanıcılar ve Hesaplar ayarları

- **Yeni kullanıcı ekle**: Kullanıcıların yeni kullanıcı eklemesini önlemek için **Engelle** olarak ayarlayın.
- **Kullanıcı kaldırma**: Kullanıcıların kullanıcı kaldırmasını önlemek için **Engelle** olarak ayarlayın.
- **Hesap değişiklikleri**: Kullanıcıların hesaplarda değişiklik yapmasını önlemek için **Engelle** olarak ayarlayın.

## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).



