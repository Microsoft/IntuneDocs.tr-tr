---
ms.openlocfilehash: 6f5b0c8df86cf5bf1206c1cccb879e37c7944a21
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71912786"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 otomatik kayıt özelliğini etkinleştirme

Otomatik kayıt, kullanıcıların Windows 10 cihazlarını Intune’a kaydetmesine olanak tanır. Kayıt için kullanıcılar, kişisel cihazlarına iş hesaplarını ekler veya şirkete ait cihazları Azure Active Directory’ye ekler. Arka planda cihaz kaydolur ve Azure Active Directory’ye katılır. Kaydedildikten sonra cihaz, Intune ile yönetilir.

**Önkoşullar**

- Azure Active Directory Premium aboneliği ([deneme aboneliği](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune aboneliği

### <a name="configure-automatic-mdm-enrollment"></a>Otomatik MDM kaydını yapılandırma

1. [Azure portalında](https://portal.azure.com) oturum açın ve **Azure Active Directory**’yi seçin.

   ![Azure portalının ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-azure-main.png)

2. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

   ![Azure portalının ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-mdm.png)

3. **Microsoft Intune**'u seçin.

   ![Azure portalının ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-intune.png)

4. **MDM Kullanıcı kapsamını** yapılandırın. Cihazları Microsoft Intune tarafından yönetilecek kullanıcıları belirtin. Bu Windows 10 cihazlar, Microsoft Intune ile yönetim için otomatik olarak kaydedilebilir.

   - **Hiçbiri** - MDM otomatik kayıt devre dışı
   - **Bazıları** - Windows 10 cihazlarını otomatik olarak kaydedebilecek **Grupları** seçin
   - **Tümü** - Tüm kullanıcılar Windows 10 cihazlarını otomatik olarak kaydedebilir

      > [!IMPORTANT]
      > KCG cihazlarında hem MAM kullanıcı kapsamı hem de MDM kullanıcı kapsamı (otomatik MDM kaydı) tüm kullanıcılar (veya aynı kullanıcı grupları) için etkinleştirilmişse MAM kullanıcı kapsamı önceliklidir. Cihaz MDM''ye kayıtlı olmak yerine Windows Bilgi Koruması (WIP) ilkelerini (yapılandırıldıysa) kullanır.
      >
      > Her iki kapsam da etkinleştirilmişse şirket cihazları için MDM kullanıcı kapsamı önceliklidir. Cihazlar MDM kayıtlı olur.

   > [!NOTE]
   > MDM Kullanıcı kapsamı, Kullanıcı nesneleri içeren bir Azure AD grubuna ayarlanmalıdır.

   ![Azure portalının ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-scope.png)

5. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
    - **MDM Kullanım Koşulları URL’si**
    - **MDM Bulma URL’si**
    - **MAM uyumluluk URL’si**

6. **Kaydet**’i seçin.

Varsayılan olarak, iki faktörlü kimlik doğrulaması hizmet için etkin değildir. Ancak, bir cihaz kaydederken iki faktörlü kimlik doğrulaması önerilir. İki öğeli kimlik doğrulamasını etkinleştirmek için Azure AD’de bir iki öğeli kimlik doğrulaması sağlayıcısı yapılandırmanız ve çok faktörlü kimlik doğrulaması için kullanıcı hesaplarınızı yapılandırmanız gerekir. Bkz. [Azure Multi-Factor Authentication Sunucusunu kullanmaya başlama](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
