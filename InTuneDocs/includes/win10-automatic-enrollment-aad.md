## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 otomatik kayıt özelliğini etkinleştirme

Otomatik kayıt, iş hesaplarını kişisel cihazlarına eklerken veya şirkete ait cihazlarının Azure Active Directory’nize katılmalarını sağlarken kullanıcıların Windows 10 cihazlarını Intune'a kaydetmelerine olanak sağlar. Arka planda, kullanıcının cihazı kaydolur ve Azure Active Directory’ye katılır. Kaydedildikten sonra cihaz, Intune ile yönetilir.

**Önkoşullar**
- Azure Active Directory Premium aboneliği ([deneme aboneliği](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune aboneliği


### <a name="configure-automatic-mdm-enrollment"></a>Otomatik MDM kaydını yapılandırma

1. [Azure yönetim portalında](https://portal.azure.com) (https://manage.windowsazure.com) oturum açın ve **Azure Active Directory**'yi seçin.

  ![Azure portalının ekran görüntüsü](../media/auto-enroll-azure-main.png)

2. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

  ![Azure portalının ekran görüntüsü](../media/auto-enroll-mdm.png)

3. **Microsoft Intune**'u seçin.

  ![Azure portalının ekran görüntüsü](../media/auto-enroll-intune.png)

4. **MDM Kullanıcı kapsamını** yapılandırın. Cihazları Microsoft Intune tarafından yönetilecek kullanıcıları belirtin. Bu kullanıcıların Windows 10 cihazları, Microsoft Intune ile yönetim için otomatik olarak kaydedilir.

  - **Yok.**
  - **Bazı**
  - **Tümü**

 ![Azure portalının ekran görüntüsü](../media/auto-enroll-scope.png)

5. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
  - **MDM Kullanım Koşulları URL’si**
  - **MDM Bulma URL’si**
  - **MDM Uyumluluğu URL’si**

6. **Kaydet**’i seçin.

Varsayılan olarak, iki faktörlü kimlik doğrulaması hizmet için etkin değildir. Ancak, bir cihaz kaydederken iki faktörlü kimlik doğrulaması önerilir. Bu hizmet için iki faktörlü kimlik doğrulaması gerektirmeden önce, Azure Active Directory'de bir iki faktörlü kimlik doğrulaması sağlayıcısı yapılandırmanız ve çok faktörlü kimlik doğrulaması için kullanıcı hesaplarınızı yapılandırmanız gerekir. Bkz. [Azure Multi-Factor Authentication Sunucusunu kullanmaya başlama](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
