---
ms.openlocfilehash: 04afc9c44bc1c4898950e6f3aff5dac7cb93370f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "56323431"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 otomatik kayıt özelliğini etkinleştirme

Otomatik kayıt, kullanıcıların Windows 10 cihazlarını Intune’a kaydetmesine olanak tanır. Kayıt için kullanıcılar, kişisel cihazlarına iş hesaplarını ekler veya şirkete ait cihazları Azure Active Directory’ye ekler. Arka planda cihaz kaydolur ve Azure Active Directory’ye katılır. Kaydedildikten sonra cihaz, Intune ile yönetilir.

**Önkoşullar**
- Azure Active Directory Premium aboneliği ([deneme aboneliği](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune aboneliği


### <a name="configure-automatic-mdm-enrollment"></a>Otomatik MDM kaydını yapılandırma

1. [Azure portalında](https://portal.azure.com) oturum açın ve **Azure Active Directory**’yi seçin.

   ![Azure portalının ekran görüntüsü](../media/auto-enroll-azure-main.png)

2. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

   ![Azure portalının ekran görüntüsü](../media/auto-enroll-mdm.png)

3. **Microsoft Intune**'u seçin.

   ![Azure portalının ekran görüntüsü](../media/auto-enroll-intune.png)

4. **MDM Kullanıcı kapsamını** yapılandırın. Cihazları Microsoft Intune tarafından yönetilecek kullanıcıları belirtin. Bu Windows 10 cihazlar, Microsoft Intune ile yönetim için otomatik olarak kaydedilebilir.

   - **Hiçbiri** - MDM otomatik kayıt devre dışı
   - **Bazıları** - Windows 10 cihazlarını otomatik olarak kaydedebilecek **Grupları** seçin
   - **Tümü** - Tüm kullanıcılar Windows 10 cihazlarını otomatik olarak kaydedebilir

      > [!IMPORTANT]
      > MAM kullanıcı kapsamı hem de MDM kullanıcı kapsamı (otomatik MDM kaydını) tüm kullanıcılar (veya aynı kullanıcı gruplarını) etkinleştirilip etkinleştirilmediğini KCG cihazlarında, MAM kullanıcı kapsamı öncelik kazanır. (Bunları yapılandırdıysanız) cihaz MDM'ye olmak yerine Windows bilgi Koruması (WIP) ilkelerini kullanır.
      >
      > Her iki kapsam etkinleştirilip etkinleştirilmediğini şirket cihazları için MDM kullanıcı kapsamı öncelik kazanır. MDM kayıtlı cihazlara alın.

   > [!NOTE]
   > MAM kullanıcı kapsamı, bir kullanıcı grubu veya toplama ayarlamanız gerekir.

   ![Azure portalının ekran görüntüsü](../media/auto-enroll-scope.png)

5. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
    - **MDM Kullanım Koşulları URL’si**
    - **MDM Bulma URL’si**
    - **MDM Uyumluluğu URL’si**

6. **Kaydet**’i seçin.

Varsayılan olarak, iki faktörlü kimlik doğrulaması hizmet için etkin değildir. Ancak, bir cihaz kaydederken iki faktörlü kimlik doğrulaması önerilir. İki öğeli kimlik doğrulamasını etkinleştirmek için Azure AD’de bir iki öğeli kimlik doğrulaması sağlayıcısı yapılandırmanız ve çok faktörlü kimlik doğrulaması için kullanıcı hesaplarınızı yapılandırmanız gerekir. Bkz. [Azure Multi-Factor Authentication Sunucusunu kullanmaya başlama](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
