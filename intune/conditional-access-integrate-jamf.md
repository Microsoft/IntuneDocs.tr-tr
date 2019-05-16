---
title: Uyumluluk için Jamf Pro’yu Microsoft Intune ile tümleştirme
titleSuffix: Microsoft Intune
description: Jamf tarafından yönetilen cihazların güvenliğine yardımcı olmak için Microsoft Intune uyumluluk ilkelerini Azure Active Directory koşullu erişimiyle birlikte kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
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
ms.openlocfilehash: cac92aeac895201459e692aae164f51dab10dfb0
ms.sourcegitcommit: ca0f48982e49e90bc14fac5575077445e027f728
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65712633"
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

1. İçinde [Azure portalında](https://portal.azure.com)Git **Azure Active Directory** > **uygulama kayıtları**ve ardından **yeni kayıt**. 

2. Üzerinde **bir uygulamayı kaydetme** sayfasında, aşağıdaki bilgileri belirtin:
   - İçinde **adı** bölümünde, bir anlamlı uygulama adı girin, örneğin **Jamf koşullu erişim**.
   - İçin **desteklenen hesap türleri** bölümünden **herhangi bir kuruluş dizini hesaplarında**. 
   - İçin **yeniden yönlendirme URI'si**, varsayılan Web değerini bırakın ve ardından Jamf Pro örneğinizin URL'sini belirtin.  

3. Seçin **kaydetme** uygulama oluşturmak için ve yeni bir uygulama için genel bakış sayfasını açın.  

4. Uygulamasında **genel bakış** sayfasında, kopya **uygulama (istemci) kimliği** değeri ve daha sonra kullanmak üzere kaydedin. Bu değer sonraki yordamlarda gerekir.  

5. Seçin **sertifikaları ve parolaları** altında **Yönet**. Seçin **yeni gizli** düğmesi. Bir değer girin **açıklama**, tüm seçeneğini **Expires** ve **Ekle**.

   > [!IMPORTANT]  
   > Bu sayfadan ayrılmadan önce gizli anahtar değerini kopyalayın ve daha sonra kullanmak üzere kaydedin. Bu değer sonraki yordamlarda gerekir. Bu değer, uygulama kaydını yeniden oluşturmanıza gerek kalmadan kullanılamaz.  

6. Seçin **API izinleri** Yönet altında.  Mevcut izinleri seçin ve ardından **kaldırma izni** bu izinleri silinemedi. Var olan tüm izinleri kaldırma işlemi, yeni bir izin ekleyeceksiniz ve uygulamayı sadece tek gerekli izni varsa çalışır gereklidir.  

7. Yeni bir izin atamak için **bir izin eklemek**. Üzerinde **istek API izinleri** sayfasında **Intune**ve ardından **uygulama izinleri**. Yalnızca ait onay kutusunu **update_device_attributes**.  

   Seçin **iznini ekleyin** bu yapılandırmayı kaydetmek için.  

8. Üzerinde **API izinleri** sayfasında **Microsoft için yönetici onayı vermek**ve ardından Evet'i seçin.  

   Azure AD'de uygulama kayıt işlemi tamamlanmıştır.


    > [!NOTE]
    > İstemci gizli anahtarı süresi dolarsa, Azure'da yeni bir istemci gizli anahtarı oluşturma ve ardından Jamf Pro koşullu erişim verileri güncelleştirin. Azure, hem eski gizli ve yeni anahtar hizmet kesintilerini önlemek için etkin olmasını sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Jamf Pro ile tümleştirmek için Intune’u etkinleştirme

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=20909)ve Git **Intune** > **cihaz uyumluluğu** > **iş ortağı cihaz Yönetimi**.

2. Önceki yordama sırasında kaydedilmiş uygulama kimliği yapıştırarak Jamf için Uyumluluk Bağlayıcısı'nı etkinleştir **Jamf Azure Active Directory Uygulama Kimliği** alan.

3. **Kaydet**’i seçin.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Jamf Pro'da Microsoft Intune tümleştirmesini yapılandırma

1. Jamf Pro'da **Küresel Yönetim** > **Şartlı Erişim**'e gidin. **Microsoft Intune Tümleştirmesi** sekmesinde **Düzenle** düğmesine tıklayın.

2. **Microsoft Intune Tümleştirmesini Etkinleştir** onay kutusunu seçin.

3. Dahil olmak üzere Azure kiracısı hakkında gerekli bilgileri sağlayın **konumu**, **etki alanı adı**, **uygulama kimliği**ve değeri *istemci Gizli dizi* Azure AD'de uygulama oluştururken kaydedildi.  

4. **Kaydet**’i seçin. Jamf Pro, test ayarlarınızı ve başarınızı doğrular.

## <a name="set-up-compliance-policies-and-register-devices"></a>Uyumluluk ilkelerini ayarlama ve cihazları kaydetme

Intune ve Jamf arasındaki tümleştirmeyi yapılandırdıktan sonra yapmanız [Jamf tarafından yönetilen cihazlar için Uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Sonraki adımlar

- [Jamf tarafından yönetilen cihazlar için uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md)
- [Veri Jamf'ın Intune'a gönderdiği](data-jamf-sends-to-intune.md)
