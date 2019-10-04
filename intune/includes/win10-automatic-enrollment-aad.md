---
ms.openlocfilehash: 6f5b0c8df86cf5bf1206c1cccb879e37c7944a21
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71912786"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 otomatik kaydını etkinleştir

Otomatik kayıt, kullanıcıların Windows 10 cihazlarını Intune 'A kaydetmesine olanak sağlar. Kaydolmak için kullanıcılar kendi kişisel cihazlarına kendi iş hesaplarını ekler veya şirkete ait cihazlara Azure Active Directory. Arka planda, cihaz Azure Active Directory kaydeder ve birleştirir. Kaydolduktan sonra cihaz Intune ile yönetilir.

**Önkoşullar**

- Azure Active Directory Premium aboneliği ([deneme aboneliği](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune aboneliği

### <a name="configure-automatic-mdm-enrollment"></a>Otomatik MDM kaydını yapılandırma

1. [Azure Portal](https://portal.azure.com)oturum açın ve **Azure Active Directory**' ı seçin.

   ![Azure portal ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-azure-main.png)

2. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

   ![Azure portal ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-mdm.png)

3. **Microsoft Intune**seçin.

   ![Azure portal ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-intune.png)

4. **MDM Kullanıcı kapsamını**yapılandırın. Hangi kullanıcıların cihazlarının Microsoft Intune tarafından yönetilmesi gerektiğini belirtin. Bu Windows 10 cihazları Microsoft Intune ile yönetim için otomatik olarak kaydolabilir.

   - **Hiçbiri** -MDM otomatik kaydı devre dışı
   - **Bazı** -Windows 10 cihazlarını otomatik olarak kaydedebilen **grupları** seçin
   - **Tümü** -tüm kullanıcılar Windows 10 cihazlarını otomatik olarak kaydedebilir

      > [!IMPORTANT]
      > KCG cihazlarında, tüm kullanıcılar (veya aynı kullanıcı grupları) için hem MAM Kullanıcı kapsamı hem de MDM Kullanıcı kapsamı (otomatik MDM kaydı) etkinleştirilmişse MAM Kullanıcı kapsamı önceliklidir. Cihaz, MDM kaydı yerine Windows Information Protection (WıP) Ilkelerini kullanır (bunları yapılandırdıysanız).
      >
      > Kurumsal cihazlarda, her iki kapsam de etkinse MDM Kullanıcı kapsamı öncelikli olur. Cihazlar MDM 'ye kaydolmuş.

   > [!NOTE]
   > MDM Kullanıcı kapsamı, Kullanıcı nesneleri içeren bir Azure AD grubuna ayarlanmalıdır.

   ![Azure portal ekran görüntüsü](../enrollment/media/windows-enroll/auto-enroll-scope.png)

5. Aşağıdaki URL 'Ler için varsayılan değerleri kullanın:
    - **MDM Kullanım koşulları URL 'SI**
    - **MDM bulma URL 'SI**
    - **MDM uyumluluk URL 'SI**

6. **Kaydet**' i seçin.

Varsayılan olarak, iki öğeli kimlik doğrulama hizmeti için etkin değildir. Ancak, bir cihaz kaydedilirken iki öğeli kimlik doğrulaması önerilir. İki öğeli kimlik doğrulamayı etkinleştirmek için Azure AD 'de iki öğeli kimlik doğrulama sağlayıcısı yapılandırın ve Multi-Factor Authentication için kullanıcı hesaplarınızı yapılandırın. Bkz. [Azure Multi-Factor Authentication sunucusu](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)kullanmaya başlama.
