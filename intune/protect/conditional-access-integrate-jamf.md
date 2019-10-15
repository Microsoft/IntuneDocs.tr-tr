---
title: JAMF Pro 'Yu uyumluluk için Microsoft Intune tümleştirin
titleSuffix: Microsoft Intune
description: JAMF tarafından yönetilen cihazların tümleştirilmesine ve güvenliğini sağlamaya yardımcı olmak için Azure Active Directory Koşullu erişimle Microsoft Intune uyumluluk ilkeleri kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/20/2019
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
ms.openlocfilehash: 09566e314f801c0de3f371384126cf672403b6a3
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306627"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Uyumluluk için JAMF Pro 'Yu Intune ile tümleştirme

Uygulama hedefi: Intune Azure portal

Kuruluşunuz macOS cihazlarını yönetmek için [JAMF Pro 'yu](https://www.jamf.com) kullandığında, kuruluşunuzdaki cihazların erişebilmeleri için uyumlu olduğundan emin olmak için Azure Active Directory (Azure AD) koşullu erişim ile Microsoft Intune uyumluluk ilkelerini kullanabilirsiniz. Şirket kaynakları. Bu makale, Intune ile JAMF tümleştirmesini yapılandırmanıza yardımcı olur.

JAMF Pro, Intune ile tümleştiriliyorsa, macOS cihazlarındaki envanter verilerini Azure AD aracılığıyla Intune ile eşitleyebilirsiniz. Intune 'un uyumluluk altyapısı daha sonra bir rapor oluşturmak için envanter verilerini analiz eder. Intune 'un analizi, koşullu erişim aracılığıyla uygulamanın zorlanması için cihaz kullanıcısının Azure AD kimliğiyle ilgili zeka birleştirilir. Koşullu erişim ilkeleriyle uyumlu olan cihazlar, korunan şirket kaynaklarına erişim elde edebilir.

Tümleştirmeyi yapılandırdıktan sonra JAMF ve Intune 'u, JAMF tarafından yönetilen cihazlarda [koşullu erişimle uyumluluğu zorlamak üzere yapılandırırsınız](conditional-access-assign-jamf.md) .  


## <a name="prerequisites"></a>Önkoşullar

### <a name="products-and-services"></a>Ürünler ve hizmetler
JAMF Pro ile koşullu erişimi yapılandırmak için aşağıdakiler gerekir:

- JAMF Pro 10.1.0 veya üzeri
- [MacOS için Şirket Portalı uygulaması](https://aka.ms/macoscompanyportal)
- OS X 10,11 Yosemite veya üzeri olan macOS cihazları

### <a name="network-ports"></a>Ağ bağlantı noktaları
<!-- source: https://support.microsoft.com/en-us/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune -->
JAMF ve Intune 'un doğru tümleşmesini sağlamak için aşağıdaki bağlantı noktalarına erişilebilir olmalıdır: 
- **Intune**: bağlantı noktası 443
- **Apple**: Ports 2195, 2196 ve 5223 (Intune 'a anında iletme bildirimleri)
- **JAMF**: bağlantı noktaları 80 ve 5223

APNS 'nin ağda düzgün çalışmasını sağlamak için, giden bağlantıları da etkinleştirmeniz ve ' den yeniden yönlendirmelerinin olması gerekir:
- Tüm istemci ağlarından 5223 ve 443 TCP bağlantı noktaları üzerinde Apple 17.0.0.0/8 bloğu.   
- JAMF Pro sunucularından 2195 ve 2196 bağlantı noktaları.  

Bu bağlantı noktaları hakkında daha fazla bilgi için aşağıdaki makalelere bakın:  
- [Intune ağ yapılandırma gereksinimleri ve bant genişliği](../fundamentals/network-bandwidth-use.md).
- Jamf.com üzerinde [JAMF Pro tarafından kullanılan ağ bağlantı noktaları](https://www.jamf.com/jamf-nation/articles/34/network-ports-used-by-jamf-pro) .
- Support.apple.com üzerinde [Apple yazılım ürünleri tarafından kullanılan TCP ve UDP bağlantı noktaları](https://support.apple.com/HT202944)


## <a name="connect-intune-to-jamf-pro"></a>Intune 'U JAMF Pro 'ya bağlama

Intune 'u JAMF Pro ile bağlamak için:

1. Azure 'da yeni bir uygulama oluşturun.
2. Intune 'u JAMF Pro ile tümleşecek şekilde etkinleştirin.
3. JAMF Pro 'da koşullu erişimi yapılandırın.

## <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory’de uygulama oluşturma

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

8. **API izinleri** sayfasında, * * * > kiracınız @no__t için * * yönetici onayı ver ' i seçin ve ardından **Evet**' i seçin.  Uygulama başarıyla kaydedildikten sonra, API izinleri şu şekilde görünmelidir: ![Başarılı izinleri @ no__t-1

   Azure AD 'de uygulama kayıt işlemi tamamlanmıştır.


    > [!NOTE]
    > İstemci parolasının süresi dolarsa, Azure 'da yeni bir istemci parolası oluşturmanız ve ardından JAMF Pro 'daki koşullu erişim verilerini güncelleştirmeniz gerekir. Azure, hizmet kesintilerini engellemek için hem eski gizli anahtar hem de yeni anahtarın etkin olmasını sağlar.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Intune 'u JAMF Pro ile tümleşecek şekilde etkinleştirme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın ve **Microsoft Intune** > **cihaz uyumluluğu** > **iş ortağı cihaz yönetimi**' ne gidin.

2. Önceki yordam sırasında kaydettiğiniz uygulama KIMLIĞINI **jamf Azure Active Directory Uygulama kimliği** alanına yapıştırarak JAMF Için uyumluluk bağlayıcısını etkinleştirin.

3. **Kaydet**’i seçin.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>JAMF Pro 'da Microsoft Intune tümleştirmesini yapılandırma

1. JAMF Pro 'da **genel yönetim** > **koşullu erişim**' e gidin. **MacOS Intune tümleştirmesi** sekmesinde **Düzenle** düğmesine tıklayın.

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

- [JAMF tarafından yönetilen cihazlara uyumluluk ilkeleri uygulama](conditional-access-assign-jamf.md)
- [Veri JAMF, Intune 'a gönderiyor](data-jamf-sends-to-intune.md)
