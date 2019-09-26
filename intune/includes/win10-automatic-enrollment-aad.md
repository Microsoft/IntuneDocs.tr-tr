---
ms.openlocfilehash: 3aadafbcf9c9208e7c87504c5459731de1e402b5
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "71302618"
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
      > KCG cihazlarında, tüm kullanıcılar (veya aynı kullanıcı grupları) için hem MAM Kullanıcı kapsamı hem de MDM Kullanıcı kapsamı (otomatik MDM kaydı) etkinleştirilmişse MAM Kullanıcı kapsamı önceliklidir. Cihaz, MDM kaydı yerine Windows Information Protection (WıP) Ilkelerini kullanır (bunları yapılandırdıysanız).
      >
      > Kurumsal cihazlarda, her iki kapsam de etkinse MDM Kullanıcı kapsamı öncelikli olur. Cihazlar MDM 'ye kaydolmuş.

   > [!NOTE]
   > MDM Kullanıcı kapsamı, Kullanıcı nesneleri içeren bir Azure AD grubuna ayarlanmalıdır.

   ![Azure portalının ekran görüntüsü](../media/auto-enroll-scope.png)

5. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
    - **MDM Kullanım Koşulları URL’si**
    - **MDM Bulma URL’si**
    - **MDM Uyumluluğu URL’si**

6. **Kaydet**’i seçin.

Varsayılan olarak, iki faktörlü kimlik doğrulaması hizmet için etkin değildir. Ancak, bir cihaz kaydederken iki faktörlü kimlik doğrulaması önerilir. İki öğeli kimlik doğrulamasını etkinleştirmek için Azure AD’de bir iki öğeli kimlik doğrulaması sağlayıcısı yapılandırmanız ve çok faktörlü kimlik doğrulaması için kullanıcı hesaplarınızı yapılandırmanız gerekir. Bkz. [Azure Multi-Factor Authentication Sunucusunu kullanmaya başlama](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
