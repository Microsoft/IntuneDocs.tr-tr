---
title: Uyumluluk için Jamf Pro’yu Microsoft Intune ile tümleştirme
titleSuffix: Microsoft Intune
description: JAMF tarafından yönetilen cihazların güvenliğini sağlamaya yardımcı olmak için Azure Active Directory Koşullu erişimle Microsoft Intune uyumluluk ilkeleri kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b439067d06cf49a4ff83288e109d1fccd3801106
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729773"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Uyumluluk için Jamf Pro’yu Intune ile tümleştirme

Uygulama hedefi: Azure portalında Intune

Kuruluşunuz, son kullanıcılarınızın Mac 'nizi yönetmek için [JAMF Pro 'yu](https://www.jamf.com) kullanıyorsa, kuruluşunuzdaki cihazların uyumlu olmasını sağlamak için Microsoft Intune uyumluluk Ilkelerini Azure Active Directory koşullu erişime sahip olarak kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

JAMF Pro ile koşullu erişimi yapılandırmak için aşağıdakiler gerekir:

- Jamf Pro 10.1.0 veya daha yenisi
- [MacOS için Şirket Portalı uygulaması](https://aka.ms/macoscompanyportal)
- OS X 10.11 ile Yosemite veya sonrası olan macOS cihazları

## <a name="connect-intune-to-jamf-pro"></a>Intune 'U JAMF Pro 'ya bağlama

Intune 'u JAMF Pro ile bağlamak için:

1. Azure 'da yeni bir uygulama oluşturun.
2. Intune 'u JAMF Pro ile tümleşecek şekilde etkinleştirin.
3. JAMF Pro 'da koşullu erişimi yapılandırın.

## <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory bir uygulama oluşturma

1. [Azure Portal](https://portal.azure.com), **Azure Active Directory** > **uygulama kaydı**' na gidin ve ardından **Yeni kayıt**' ı seçin. 

2. **Uygulama kaydetme** sayfasında, aşağıdaki ayrıntıları belirtin:
   - **Ad** bölümünde, bir anlamlı uygulama adı girin, örneğin **JAMF koşullu erişim**.
   - **Desteklenen hesap türleri** bölümü için **herhangi bir kuruluş dizininde hesaplar**' ı seçin. 
   - **Yeniden yönlendirme URI 'si**için, varsayılan Web ' i bırakın ve sonra JAMF Pro örneğiniz için URL 'yi belirtin.  

3. Uygulamayı oluşturmak için **Kaydet** ' i seçin ve yeni uygulama Için **genel bakış** sayfasını açın.  

4. Uygulamaya **genel bakış** sayfasında, **uygulama (istemci) kimlik** değerini kopyalayın ve daha sonra kullanmak üzere kaydedin. Sonraki yordamlarda bu değere ihtiyacınız olacaktır.  

5. **Yönet**altında **Sertifikalar & parolaları** ' nı seçin. **Yeni istemci parolası** düğmesini seçin. **Açıklama**değerinde bir değer girin, **süre sonu** için herhangi bir seçenek belirleyin ve **Ekle**' yi seçin.

   > [!IMPORTANT]  
   > Bu sayfadan ayrılmadan önce, istemci sırrı için değeri kopyalayın ve daha sonra kullanmak üzere kaydedin. Sonraki yordamlarda bu değere ihtiyacınız olacaktır. Bu değer, uygulama kaydını yeniden oluşturmadan tekrar kullanılamaz.  

6. **Yönet**altında **API izinleri** ' ni seçin. Mevcut izinleri seçin ve ardından bu izinleri silmek için **Izni kaldır** ' ı seçin. Yeni bir izin ekleyeceğiniz için tüm mevcut izinlerin kaldırılması gerekir ve uygulama yalnızca tek gerekli izni varsa işe yarar.  

7. Yeni bir izin atamak için **Izin Ekle**' yi seçin. **API Izinleri iste** sayfasında, **Intune**' u seçin ve ardından **Uygulama izinleri**' ni seçin. Yalnızca **update_device_attributes**onay kutusunu seçin.  

   Bu yapılandırmayı kaydetmek için **Izin Ekle** ' yi seçin.  

8. **API izinleri** sayfasında, **Microsoft Için yönetici onayı ver**' i seçin ve ardından **Evet**' i seçin.  

   Azure AD 'de uygulama kayıt işlemi tamamlanmıştır.


    > [!NOTE]
    > İstemci parolasının süresi dolarsa, Azure 'da yeni bir istemci parolası oluşturmanız ve ardından JAMF Pro 'daki koşullu erişim verilerini güncelleştirmeniz gerekir. Azure, hizmet kesintilerini engellemek için hem eski gizli anahtar hem de yeni anahtarın etkin olmasını sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Jamf Pro ile tümleştirmek için Intune’u etkinleştirme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın ve **Microsoft Intune** > **cihaz uyumluluğu** > **iş ortağı cihaz yönetimi**' ne gidin.

2. Önceki yordam sırasında kaydettiğiniz uygulama KIMLIĞINI **jamf Azure Active Directory Uygulama kimliği** alanına yapıştırarak JAMF Için uyumluluk bağlayıcısını etkinleştirin.

3. **Kaydet**’i seçin.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Jamf Pro'da Microsoft Intune tümleştirmesini yapılandırma

1. Jamf Pro'da **Küresel Yönetim** > **Şartlı Erişim**'e gidin. **MacOS Intune tümleştirmesi** sekmesinde **Düzenle** düğmesine tıklayın.

2. **MacOS Için Intune tümleştirmesini etkinleştir**onay kutusunu işaretleyin.

3. Azure kiracınız hakkında **konum**, **etki alanı adı**, **uygulama kimliği**ve Azure AD 'de uygulamayı oluştururken kaydettiğiniz *istemci sırrı* için değer dahil olmak üzere gerekli bilgileri sağlayın.  

4. **Kaydet**’i seçin. JAMF Pro, ayarlarınızı sınar ve başarısını doğrular.

## <a name="set-up-compliance-policies-and-register-devices"></a>Uyumluluk ilkelerini ayarlama ve cihazları kaydetme

Intune ve JAMF arasındaki tümleştirmeyi yapılandırdıktan sonra, [JAMF tarafından yönetilen cihazlara uyumluluk ilkeleri uygulamanız](conditional-access-assign-jamf.md)gerekir.

## <a name="disconnect-jamf-pro-and-intune"></a>JAMF Pro ve Intune bağlantısını kesme 

Kuruluşunuzda Mac 'i yönetmek için JAMF Pro 'Yu kullanmıyorsanız ve kullanıcıların Intune tarafından yönetilmesini istiyorsanız, JAMF Pro ve Intune arasındaki bağlantıyı kaldırmanız gerekir. JAMF Pro konsolunu kullanarak bağlantıyı kaldırın. 

1. JAMF Pro 'da **genel yönetim** > **koşullu erişim**' e gidin. **MacOS Intune tümleştirmesi** sekmesinde **Düzenle**' yi seçin.
2. **MacOS Için Intune tümleştirmesini etkinleştir** onay kutusunu temizleyin.
3. **Kaydet**’i seçin. JAMF Pro, yapılandırmanızı Intune 'a gönderir ve tümleştirme sonlandırılacak.
4. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın. Durumun artık **sonlandırıldığını**doğrulamak için, **Microsoft Intune** > **cihaz uyumluluğu** > **iş ortağı cihaz yönetimi** ' ne gidin. 

   > [!NOTE]
   > Kuruluşunuzun Mac cihazları konsolunda gösterilen tarihte (3 ay) kaldırılacaktır. 

## <a name="next-steps"></a>Sonraki adımlar

- [Jamf tarafından yönetilen cihazlar için uyumluluk ilkelerini uygula](conditional-access-assign-jamf.md)
- [Veri JAMF, Intune 'a gönderiyor](data-jamf-sends-to-intune.md)
