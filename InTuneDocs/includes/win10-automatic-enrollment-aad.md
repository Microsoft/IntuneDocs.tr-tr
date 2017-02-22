## <a name="set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium"></a>Azure Active Directory Premium ile Windows 10 ve Windows 10 Mobile otomatik kaydını ayarlama

Otomatik kayıt, kullanıcıların şirkete ait ya da kişisel Windows 10 bilgisayarlarını veya Windows 10 Mobile cihazlarını, bir iş veya okul hesabı ekleyip yönetilmeyi kabul ederek Intune’a kaydetmelerine izin verir. Bu kadar basit. Arka planda, kullanıcının cihazı kaydolur ve Azure Active Directory’ye katılır. Kaydedildikten sonra cihaz, Intune ile yönetilir.

**Önkoşullar**
- Azure Active Directory Premium aboneliği ([deneme aboneliği](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune aboneliği


### <a name="configure-automatic-mdm-enrollment"></a>Otomatik MDM kaydını yapılandırma

1. [Azure yönetim portalında](https://manage.windowsazure.com) (https://manage.windowsazure.com), **Active Directory** düğümüne gidin ve dizininizi seçin.

2. **Uygulamalar** sekmesini seçin. Uygulama listesinde **Microsoft Intune** gösterilir.

    ![Microsoft Intune ile Azure AD uygulamaları](../media/aad-intune-app.png)

3. **Microsoft Intune**’un okunu seçin. Microsoft Intune’u yapılandırmanızı sağlayan bir sayfa görürsünüz.

4. Microsoft Intune ile otomatik MDM kaydını yapılandırmaya başlamak için **Yapılandır**’ı seçin.

5. Intune için URL'leri belirtin:

  - **MDM Kayıt URL’si** – Varsayılan değeri kullanın.
  - **MDM Kullanım Koşulları URL’si** – Varsayılan değeri kullanın. Bu URL, kullanıcılara cihazlarını kaydederken kullanım koşullarını gösterilir.
  - **MDM Uyumluluk URL’si** – Varsayılan değeri kullanın. Bir cihazın uyumsuz olduğunu bulunursa, bu URL ile bir **Erişim reddedildi** iletisi gösterilir. URL, kullanıcıların cihazlarının ilke ile neden uyumsuz olduğunu ve nasıl yeniden uyumlu hale getirebileceklerini anlamalarına yardımcı olan bir sayfayı işaret eder.

6.  Cihazları Microsoft Intune tarafından yönetilecek kullanıcıları belirtin. Bu kullanıcıların Windows 10 cihazları, Microsoft Intune ile yönetim için otomatik olarak kaydedilir.

  - **Tümü**
  - **GRUPLAR**
  - **Yok.**

7. **Kaydet**’i seçin.


<!--HONumber=Feb17_HO2-->


