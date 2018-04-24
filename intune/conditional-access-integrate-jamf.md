---
title: Uyumluluk için Jamf Pro’yu Microsoft Intune ile tümleştirme
titlesuffix: ''
description: Jamf tarafından yönetilen cihazların güvenliğine yardımcı olmak için Microsoft Intune uyumluluk ilkelerini Azure Active Directory koşullu erişimiyle birlikte kullanın.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 01/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cdeb3a21af2b4cf020d3e5029eeb5b0bc31db062
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Uyumluluk için Jamf Pro’yu Intune ile tümleştirme

|Uygulama hedefi: Azure portalında Intune |
|--|
|Klasik portalda Intune hakkında belgeler mi arıyorsunuz? [Buraya gidin](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

Kuruluşunuz son kullanıcılarınızın Mac'lerini yönetmek için [Jamf Pro](https://www.jamf.com) kullanıyorsa, kuruluşunuzdaki cihazların uyumlu olmasını sağlamak için Azure Active Directory koşullu erişimiyle Microsoft Intune uyum ilkelerini kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Jamf Pro ile koşullu erişimi yapılandırmak için aşağıdakiler gerekir:

- Jamf Pro 10.1.0 veya daha yenisi
- [MacOS için Şirket Portalı uygulaması](https://aka.ms/macoscompanyportal)
- OS X 10.11 ile Yosemite veya sonrası olan macOS cihazları

## <a name="connecting-intune-to-jamf-pro"></a>Intune’u Jamf Pro’ya bağlama

Intune'u Jamf Pro’ya şu şekilde bağlayabilirsin:

1. Azure'da yeni bir uygulama oluşturma
2. Jamf Pro ile tümleştirmek için Intune’u etkinleştirme
3. Jamf Pro’daki koşullu erişim ilkelerini yapılandırma

## <a name="create-a-new-application-in-azure-active-directory"></a>Azure Active Directory'de yeni bir uygulama oluşturma

1. **Azure Active Directory** > **Uygulama Kayıtları**'nı açın.
2. **+Yeni uygulama kaydı**'na tıklayın.
3. **Jamf Koşullu Erişim** gibi bir **görünen ad** girin.
4. **Web uygulaması / API**’yi seçin.
5. Jamf Pro örneği URL'nizi kullanarak **Oturum Açma URL'si** değerini belirtin.
6. **Uygulama oluştur**’a tıklayın.
7. Yeni oluşturulan **Uygulama Kimliği**'ni kaydedin, ardından yeni bir Uygulama Anahtarı oluşturmak için **Ayarlar**'ı açın ve **API Erişimi** > **Anahtarlar**'a gidin. **Açıklama**'yı ve **Süresi Dolmadan** ne kadar bekleneceğini girin, sonra da Uygulama Anahtarı'nı kaydedin.

   > [!IMPORTANT]
   > Uygulama Anahtarı yalnızca bir kez bu işlem sırasında gösterilir. Kolayca alabileceğiniz bir yere kaydettiğinizden emin olun.

8. **Ayarlar**'ı açın, **API Erişimi** > **Gerekli İzinler**'e gidin ve tüm izinleri silin.

   > [!NOTE]
   > Yeni bir gerekli izni ekleyin. Uygulama yalnızca tek gerekli izni varsa düzgün çalışabilir.

9. **Microsoft Intune API**’yi seçin ve **Seç**’e tıklayın.
10. **Microsoft Intune cihaz öznitelikleri gönder**’i seçin ve **Seç**’e tıklayın.
11. Uygulama için gerekli izinleri kaydettikten sonra **İzinleri Ver** düğmesine tıklayın.

    > [!NOTE]
    > Uygulama anahtarı süresi dolarsa, Microsoft Azure'da yeni bir Uygulama Anahtarı oluşturmalısınız ve ardından Jamf Pro koşullu erişim verileri güncelleştirin. Azure, servis kesintilerini önlemek için hem eski anahtarı hem de yeni anahtarı aktif hale getirmenizi sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Jamf Pro ile tümleştirmek için Intune’u etkinleştirme

1. Microsoft Azure portalında **Microsoft Intune** > **Cihaz Uyumluluğu** > **İş ortağı cihaz yönetimi**’ni açın.
2. Uygulama Kimliği'ni **Jamf Azure Active Directory Uygulama Kimliği** alanına yapıştırarak Jamf için Uygunluk Bağlayıcı'yı etkinleştirin.
3. **Kaydet**'e tıklayın.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Jamf Pro'da Microsoft Intune tümleştirmesini yapılandırma

1. Jamf Pro'da **Küresel Yönetim** > **Şartlı Erişim**'e gidin. **Microsoft Intune Tümleştirmesi** sekmesinde **Düzenle** düğmesine tıklayın.
2. **Microsoft Intune Tümleştirmesini Etkinleştir** onay kutusunu seçin.
3. Önceki adımlardan kaydettiğiniz **Yer**, **Alan Adı**, **Uygulama Kimliği** ve **Uygulama Anahtarı** de dahil olmak üzere Azure kiracısı hakkında gerekli bilgileri sağlayın.
4. **Kaydet**'e tıklayın. Jamf Pro, ayarlarınızı test edecek ve başarınızı doğrulayacaktır.

## <a name="set-up-compliance-policies-and-register-devices"></a>Uyumluluk ilkelerini ayarlama ve cihazları kaydetme

Intune ile Jamf arasındaki tümleştirmenin yapılandırmasını bitirdikten sonra, [Jamf ile yönetilen cihazlara uyumluluk ilkeleri uygulamanız](conditional-access-assign-jamf.md) gerekir.

## <a name="information-shared-from-jamf-pro-to-intune"></a>Jamf Pro'dan Intune'a paylaşılan bilgiler

Jamf Pro, yönetilen MacOS cihazları hakkında envanter bilgileri alır. Jamf Pro, Intune'a aşağıdaki bilgileri bildirir:

* Azure AD cihaz kimliği
* JAMF Envanter Durumu (son 24 saat içinde Jamf Pro ile kontrol edilen bir bilgisayar stok durumu)
* İşletim Sistemi Sürümü
* Azure AD cihaz kimliği
* Şifreli (FileVault 2)
* Ağ Geçidi Durumu
* Parola: minimum sayıda karakter kümesi
* Parola zaman aşımı (gün sayısı)
* Parola türü - basit, alfasayısal veya bilinmeyen
* Otomatik oturum açma engelleme
* Gerekli parola uzunluğu
* Parola: önceki parolaların yeniden kullanılmasını önlemek için önceki parola sayısı
* Sistem Bütünlüğü Koruması
* Son İade Zamanı
* Mimari Türü
* Kullanılabilir RAM Yuvaları
* Pil kapasitesi
* Önyükleme ROM'u
* Veri Yolu Hızı
* Önbellek Boyutu
* Aygıt Adı
* Etki Alanına Katılım
* Jamf kimliği
* MAC adresi
* Marka
* Model
* Model Tanımlayıcısı
* NIC Hızı
* Çekirdek Sayısı
* İşlemci Sayısı
* İşletim sistemi
* Platform
* İşlemci Hızı
* İşlemci Türü
* İkincil MAC Adresi
* Seri Numarası
* SMS Sürümü
* Toplam RAM
* UDID
* Kullanıcı E-postası

## <a name="next-steps"></a>Sonraki adımlar

- [Jamf tarafından yönetilen cihazlar için uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md)
