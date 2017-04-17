## <a name="enable-windows-10-automatic-enrollment"></a>Windows 10 otomatik kayıt özelliğini etkinleştirme

Otomatik kayıt, kullanıcıların şirkete ait ya da kişisel Windows 10 bilgisayarlarını veya Windows 10 Mobile cihazlarını, bir iş veya okul hesabı ekleyip yönetilmeyi kabul ederek Intune’a kaydetmelerine izin verir. Bu kadar basit. Arka planda, kullanıcının cihazı kaydolur ve Azure Active Directory’ye katılır. Kaydedildikten sonra cihaz, Intune ile yönetilir.

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

4. Otomatik olarak kaydolacak kullanıcıları yapılandırın.

  ![Azure portalının ekran görüntüsü](../media/auto-enroll-scope.png)

  Aşağıdaki URL'ler için varsayılan değerleri kullanın:
  - **MDM Kaydı**
  - **MDM Kullanım Koşulları**
  - **MDM Uyumluluğu**

5. Cihazları Microsoft Intune tarafından yönetilecek kullanıcıları belirtin. Bu kullanıcıların Windows 10 cihazları, Microsoft Intune ile yönetim için otomatik olarak kaydedilir.

  - **Tümü**
  - **GRUPLAR**
  - **Yok.**

6. **Kaydet**’i seçin.
