---
title: "İlke oluşturma ve uygulama yayımlama | Microsoft Intune"
description: "Intune aboneliğiniz için ilkeleri nasıl oluşturacağınız ve örnek bir uygulamayı nasıl yayımlayacağınız anlatılır."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: da46c83d43f4ce4c5ae22b87638ad747a57b9e3f


---

# İlke oluşturma ve uygulama yayımlama
Intune ilkeleri, mobil cihazlarda güvenlik ayarlarını denetlemenize, bilgisayarlar için Windows Güvenlik Duvarı ve Endpoint Protection ayarlarını korumanıza ve uygulamaları dağıtmanıza yardımcı olan ayarlar sağlar. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) ve [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) konu başlıkları altında daha fazla bilgi bulabilirsiniz.

Intune kullanarak iki uygulama yükleme türü gerçekleştirebilirsiniz. İlki, uygulamayı yönetilen bilgisayarlara otomatik olarak dağıtan **gerekli yüklemedir**. Diğeri, bir uygulamayı veya uygulama bağlantısını kullanıcıların uygulamayı bilgisayarlarına veya mobil cihazlarına yükleyip yüklememeyi seçebilmeleri için Intune Şirket Portalı’na dağıtan **kullanılabilir yüklemedir**.

Aşağıdaki adımlar, bir mobil cihaz yapılandırma ilkesi ve bir Windows bilgisayar güvenlik duvarı ilkesi ayarlamanıza ve Skype’ı mobil cihazlar kaydolduktan sonra kullanılabilir bir yükleme olarak yapılandırmanıza yardımcı olur.

> [!TIP]
> Yeni bir ilke ekleyip dağıttıktan sonra, ilkeyi dağıttığınız gruptaki tüm kullanıcılar veya cihazlar ayarları temel ilke olarak alır. Bu ilkelerin ayarlarını istediğiniz zaman İlke çalışma alanında gözden geçirebilir ve düzenleyebilirsiniz.


## Bir mobil cihaz yapılandırma ilkesi oluşturma ve dağıtma

1.  [Intune Yönetim Konsolu](https://manage.microsoft.com/)'nu açın.

2.  Sol bölmede **İlke** simgesini seçin.

    ![admin-console-policy-workspace](./media/policy.png)

3.  **İlkeye Genel Bakış** sayfasındaki **Görevler** listesinde, **İlke Ekle**'yi seçin.

4.  İlke listesinde, ilke oluşturmak istediğiniz platformu genişletin ve ardından **Genel Yapılandırma** > **Önerilen Ayarlarla İlke Oluştur ve Dağıt** > **İlke Oluştur**’u seçin.

> [!NOTE]
> Cihaz yapılandırma ilkeleri için önerilen ayarlar sağlanmaz çünkü aralarından seçim yapabileceğiniz birçok seçenek vardır. Özel bir cihaz yapılandırma ilkesi oluşturmanız gerekir.


5.  **Bu ilkeyi dağıtmak istediğiniz grupları seçmeniz** istendiğinde, kullanılabilir gruplar listesinden bir grup seçin ve sonra **Ekle** > **Tamam**’ı seçin.

İlkeniz, yapılandırma ilkeleri listesinde görüntülenir ve **Intune Kullanıcıları** grubuna dağıtılmış olur. Ayarlarını görüntülemek için ilkeye çift tıklayın.

## Mobil cihazlar için Skype uygulamasını yayımlama

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Uygulamalar** simgesini ve sonra **Uygulamalar** > **Uygulama Ekle**’yi seçin. İstenirse, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kimlik bilgilerinizi girin.

    ![admin-console-apps-workspace](./media/apps.png)

    > [!NOTE]
    > **Intune Software Publisher** 'ı ilk kez başlattığınızda, uygulama yüklenirken kısa bir gecikme oluşur.

2.  Güvenlik uyarısını gözden geçirin ve **Çalıştır**'ı seçin.

3.  **Başlamadan önce** sayfasında **İleri**'yi seçin.

4.  **Yazılım kurulumu** sayfasındaki **Bu yazılımın cihazlar için nasıl kullanılabilir hale getirileceğini seçin** bölümünden **Dış bağlantı**'yı seçin.

5.  **URL'yi belirtin**bölümünde, yazılıma ait dış bağlantıyı girin ve ardından **İleri**'yi seçin. URL’nin başına **http://** yazdığınızdan emin olun. Skype uygulaması için, kullandığınız mobil cihaz platformuyla eşleşen aşağıdaki bağlantıyı kullanın:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 veya Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  **Yazılım açıklaması** sayfasında, kullanıcıların Şirket Portalı’nda yazılım için görmesini istediğiniz bilgileri sağlayın ve ardından **İleri**'yi seçin. Aşağıdaki ayarlar kullanılabilir (bu örnek, Skype'a atıfta bulunmaktadır):

    -   **Yayımcı:** Yayımcının adını girin ("Microsoft"):

    -   **Ad:** **Skype** girin.

    -   **Açıklama:** Yazılım için bir açıklama girin; örn. **Skype iletişim uygulaması**

    -   **Kategori:** Bu yazılıma en uygun kategoriyi seçin, örneğin **Birlikte çalışma**

    -   **Şirket portalında bu uygulamayı öne çıkan uygulama olarak görüntüle ve vurgula:** Uygulamayı mobil cihazlardaki Şirket Portalı’nda öne çıkarmak için bu seçeneği belirleyin.

    -   **Simge:** Yazılımla bir simge ilişkilendirmek isteyip istemediğinizi seçin. İsteğe bağlı simge için boyut üst sınırı 250 x 250 pikseldir ve önerilen boyut da 32 x 32 pikseldir.

7.  **Özet** sayfasında, yazılım bilgilerini doğrulayın ve ardından **Karşıya yükle**'yi seçin. Sihirbazdan çıkmak için **Kapat**’ı seçin.

8.  [Intune yönetim konsolunda](https://manage.microsoft.com/) **Uygulamalar** > **Uygulamalar** > **Skype** > **Dağıtımı Yönet**’i seçin.

9. **Grup Seç** sayfasında, **Intune Kullanıcıları**’nı seçerek yazılımı bu kullanıcı grubuna dağıtın ve ardından **Ekle** > **İleri**’yi seçin.

10. **Dağıtım Eylemi** sayfasında, **Onay** sütunundan grubunuz için **Kullanılabilir Yükleme** 'yi seçin.

11. **Son**’u seçin.

Skype uygulaması artık Şirket Portalı’ndan mobil cihazlara yüklenebilir, ancak önce [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] yazılımını bilgisayarlara ve mobil cihazlara yüklemeniz gerekir.


### Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* 6. adımını tamamlamış oldunuz.

>[!div class="step-by-step"]

>[&larr; **Kullanıcıları ve cihazları düzenleme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Şirket Portalı’nı özelleştirme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Aug16_HO4-->


