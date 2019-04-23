---
title: Uyumluluk için Jamf Pro’yu Microsoft Intune ile tümleştirme
titleSuffix: Microsoft Intune
description: Jamf tarafından yönetilen cihazların güvenliğine yardımcı olmak için Microsoft Intune uyumluluk ilkelerini Azure Active Directory koşullu erişimiyle birlikte kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57527d0b1825d0e8d3fefb63d1b960ab3fb5c676
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508133"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Uyumluluk için Jamf Pro’yu Intune ile tümleştirme

Şunun için geçerlidir: Azure portalında Intune

Kuruluşunuz kullanıyorsa [Jamf Pro](https://www.jamf.com) , son kullanıcılar Mac'lerini yönetmek için Microsoft Intune uyumluluk ilkelerini Azure Active Directory koşullu erişim ile kuruluşunuzdaki cihazların uyumlu olmasını sağlamak için kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Jamf Pro ile koşullu erişimi yapılandırmak için aşağıdakiler gerekir:

- Jamf Pro 10.1.0 veya daha yenisi
- [MacOS için Şirket Portalı uygulaması](https://aka.ms/macoscompanyportal)
- OS X 10.11 ile Yosemite veya sonrası olan macOS cihazları

## <a name="connecting-intune-to-jamf-pro"></a>Intune’u Jamf Pro’ya bağlama

Intune'u Jamf Pro ile bağlamak için:

1. Azure'da yeni bir uygulama oluşturma
2. Jamf Pro ile tümleştirmek için Intune’u etkinleştirme
3. Jamf Pro’daki koşullu erişim ilkelerini yapılandırma

## <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory'de uygulama oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)Git **Azure Active Directory** > **uygulama kayıtları**.
2. Seçin **+ yeni uygulama kaydı**.
3. **Jamf Koşullu Erişim** gibi bir **görünen ad** girin.
4. Seçin **Web uygulaması / API**.
5. Jamf Pro örneği URL'nizi kullanarak **Oturum Açma URL'si** değerini belirtin.
6. **Oluştur**’u seçin. Uygulama oluşturulur ve portalın uygulama ayrıntıları sunar.
7. Bir kopyasını kaydedin **uygulama kimliği** yeni uygulama için. Daha sonraki bir yordamda bu kimliği belirt Ardından, **ayarları** gidin **API erişimi** > **anahtarları**.
8. Üzerinde *anahtarları* bölmesinde belirtin bir **açıklama**, ne kadar bekleneceğini **Expires**ve ardından **Kaydet** uygulama oluşturmak için Anahtar (değer).

   > [!IMPORTANT]
   > Uygulama Anahtarı yalnızca bir kez bu işlem sırasında gösterilir. Kolayca alabileceğiniz bir yere kaydettiğinizden emin olun.

8. Üzerinde *ayarları* uygulama bölmesine gidin **API erişimi** > **gerekli izinler**. Var olan herhangi bir izni seçin ve ardından **Sil** ve tüm izinleri silin. Mevcut eylemleri silerek, yeni bir izin eklemeniz ve uygulamayı sadece tek gerekli izni varsa çalışır gereklidir.  
9. Yeni bir izin atamak için **+ Ekle** > **bir API seçin** > **Microsoft Intune API**ve ardından **seçin**.
10. Üzerinde *erişimini etkinleştir* bölmesinde **Microsoft Intune cihaz öznitelikleri Gönder** ve ardından **seçin**, ardından **Bitti**.
11. Üzerinde *gerekli izinler* bölmesinde **izinler** ve ardından **Evet** uygulama için gerekli izinleri.

    > [!NOTE]
    > Uygulama anahtarı süresi dolarsa, Microsoft Azure'da yeni bir Uygulama Anahtarı oluşturmalısınız ve ardından Jamf Pro koşullu erişim verileri güncelleştirin. Azure, servis kesintilerini önlemek için hem eski anahtarı hem de yeni anahtarı aktif hale getirmenizi sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Jamf Pro ile tümleştirmek için Intune’u etkinleştirme

1. İçinde [Azure portalında](https://portal.azure.com)Git **Intune** > **cihaz uyumluluğu** > **iş ortağı cihaz Yönetimi**.
2. Önceki yordama sırasında kaydedilmiş uygulama kimliği yapıştırarak Jamf için Uyumluluk Bağlayıcısı'nı etkinleştir **Jamf Azure Active Directory Uygulama Kimliği** alan.
3. **Kaydet**’i seçin.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Jamf Pro'da Microsoft Intune tümleştirmesini yapılandırma

1. Jamf Pro'da **Küresel Yönetim** > **Şartlı Erişim**'e gidin. **Microsoft Intune Tümleştirmesi** sekmesinde **Düzenle** düğmesine tıklayın.
2. **Microsoft Intune Tümleştirmesini Etkinleştir** onay kutusunu seçin.
3. Önceki adımlardan kaydettiğiniz **Yer**, **Alan Adı**, **Uygulama Kimliği** ve **Uygulama Anahtarı** de dahil olmak üzere Azure kiracısı hakkında gerekli bilgileri sağlayın.
4. **Kaydet**’i seçin. Jamf Pro, test ayarlarınızı ve başarınızı doğrulayın.

## <a name="set-up-compliance-policies-and-register-devices"></a>Uyumluluk ilkelerini ayarlama ve cihazları kaydetme

Intune ve Jamf arasındaki tümleştirmeyi yapılandırdıktan sonra yapmanız [Jamf tarafından yönetilen cihazlar için Uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Sonraki adımlar

- [Jamf tarafından yönetilen cihazlar için uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md)
- [Veri Jamf'ın Intune'a gönderdiği](data-jamf-sends-to-intune.md)
