---
title: "Uyumluluk için Jamf Pro’yu Intune ile tümleştirme"
titlesuffix: Azure portal
description: "Jamf tarafından yönetilen cihazların güvenliğini sağlamak için uyumluluk kullanın."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Uyumluluk için Jamf Pro’yu Intune ile tümleştirme

|Uygulama hedefi: Azure portalında Intune |
|--|
|Klasik portalda Intune hakkında belgeler mi arıyorsunuz? [Buraya gidin](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Şu anda özel olarak incelenmektedir|
|--|
|Bu konuda açıklanan özellikler, yalnızca şu anda önizlemede olan müşteriler tarafından kullanılabilir. Özellikler tüm müşterilerin kullanımına sunulduğunda bu ileti kaldırılacaktır.|
| |

Kuruluşunuz son kullanıcılarınızın Mac'lerini yönetmek için [Jamf Pro](https://www.jamf.com) kullanıyorsa, kuruluşunuzdaki cihazların uyumlu olmasını sağlamak için Azure Active Directory koşullu erişimiyle Microsoft Intune uyum ilkelerini kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Jamf Pro ile koşullu erişimi yapılandırmak için aşağıdakiler gerekir:

- MacOS koşullu erişim için Intune özel Önizleme erişimi
- Jamf Pro 10.1.0 veya daha yenisi
- [MacOS için Şirket Portalı uygulaması](https://aka.ms/macoscompanyportal)
- OS X 10.11 ile Yosemite veya sonrası olan macOS cihazları

## <a name="connecting-intune-to-jamf-pro"></a>Intune’u Jamf Pro’ya bağlama

Intune'u Jamf Pro’ya şu şekilde bağlayabilirsin:

1. Azure'da yeni bir uygulama oluşturma
2. Jamf Pro ile tümleştirmek için Intune’u etkinleştirme
3. Jamf Pro’daki koşullu erişim ilkelerini yapılandırma

## <a name="create-a-new-application-in-azure-active-directory"></a>Azure Active Directory'de yeni bir uygulama oluşturma

1. **Azure Active Directory** >  **Uygulama Kaydı** 'nı açın.
2. **+Yeni uygulama kaydı**'na tıklayın.
3. **Jamf Koşullu Erişim** gibi bir **görünen ad** girin.
4. **Web uygulaması / API**’yi seçin.
5. Jamf Pro için **oturum açma URL'si** belirtin.
6. **Uygulama oluştur**’a tıklayın.
7. Yeni bir Uygulama Anahtarı oluşturmak için yeni oluşturulan **Uygulama Kimliği**'ni kaydedin ve ardından **Tüm Ayarlar** >  **Anahtarlar**’ı açın. Uygulama Anahtarını kaydedin.

  > [!NOTE]
  > Uygulama Anahtarı yalnızca bir kez bu işlem sırasında gösterilir. Kolayca alabileceğiniz bir yere kaydettiğinizden emin olun.

8. **Tüm Ayarlar** > **API Erişimi** > **Gerekli İzinler**'e gidin ve tüm izinleri silin.

  > [!NOTE]
  > Yeni bir gerekli izni ekleyin. Uygulama yalnızca tek gerekli izni varsa düzgün çalışabilir.

9.  **Microsoft Intune API**’yi seçin ve **Seç**’e tıklayın.
10. **Microsoft Intune cihaz öznitelikleri gönder**’i seçin ve **Seç**’e tıklayın.
11. Uygulama için gerekli izinleri kaydettikten sonra **İzinleri Ver** düğmesine tıklayın.

  > [!NOTE]
  > Uygulama anahtarı süresi dolarsa, Microsoft Azure'da yeni bir Uygulama Anahtarı oluşturmalısınız ve ardından Jamf Pro koşullu erişim verileri güncelleştirin. Azure, servis kesintilerini önlemek için hem eski anahtarı hem de yeni anahtarı aktif hale getirmenizi sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Jamf Pro ile tümleştirmek için Intune’u etkinleştirme

1. Microsoft Azure portalında **Microsoft Intune** > **Cihaz Uyumluluğu** > **Jamf için Uyum Bağlayıcı**’yı açın.
2. Uygulama Kimliği'ni **Jamf Azure Active Directory Uygulama Kimliği** alanına yapıştırarak Jamf için Uygunluk Bağlayıcı'yı etkinleştirin.
3. **Kaydet**'e tıklayın.

## <a name="configure-conditional-access-in-jamf-pro"></a>Jamf Pro’daki koşullu erişim ilkelerini yapılandırma

1. Jamf Pro'da **Küresel Yönetim** > **Şartlı Erişim**'e gidin. **Microsoft** sekmesi üzerinde **Düzenle** düğmesine tıklayın.
2. **Microsoft ile Şartlı Erişimi Etkinleştir** için onay kutusunu işaretleyin.
3. Önceki adımlardan kaydettiğiniz **Yer**, **Alan Adı**, **Uygulama Kimliği** ve **Uygulama Anahtarı** de dahil olmak üzere Azure kiracısı hakkında gerekli bilgileri sağlayın.
4. **Kaydet**'e tıklayın. Jamf Pro, ayarlarınızı test edecek ve başarınızı doğrulayacaktır.

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
