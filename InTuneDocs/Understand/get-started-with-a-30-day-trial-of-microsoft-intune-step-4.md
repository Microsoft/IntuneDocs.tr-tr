---
title: "İlke oluşturma ve değerlendirme kullanıcılarına bir uygulama yayımlama | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9755499575118feecf33780ee29a70525f95508e
ms.openlocfilehash: 658806c07ea78a327819376c1b47af53ac51f0f9


---


# İlke oluşturma ve değerlendirme kullanıcılarına bir uygulama yayımlama
Intune ilkeleri, mobil cihazlarda güvenlik ayarlarını denetlemenize, bilgisayarlar için Windows Güvenlik Duvarı ve Endpoint Protection ayarlarını korumanıza ve uygulamaları dağıtmanıza yardımcı olan ayarlar sağlar. Değerlendirme sonrasında Intune’u üretim için yapılandırdığınız cihazlar için kullanmayı planlıyorsanız, [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) ve [Windows Bilgisayarları Microsoft Intune için Uç Nokta Korumasıyla Güvenli Hale Getirmeye Yardımcı Olma](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) kısmındaki yönergeleri izlemeniz kesinlikle gereklidir.

Intune kullanarak iki uygulama yükleme türü gerçekleştirebilirsiniz. İlki, uygulamayı yönetilen bilgisayarlara otomatik olarak dağıtan **gerekli yüklemedir**. Diğeri, bir uygulamayı veya uygulama bağlantısını kullanıcıların uygulamayı bilgisayarlarına veya mobil cihazlarına yükleyip yüklememeyi seçebilmeleri için Intune Şirket Portalı’na dağıtan **kullanılabilir yüklemedir**.

Uygulama dağıtmak için Intune kullanmadan önce, uygulamayı yayımlamak, dağıtmak ve kullanmak için uygun izinlere sahip olduğunuzdan emin olun. **Lisanslar** çalışma alanı, Microsoft Toplu Lisans sözleşmeleriyle satın alınmış uygulama veya yazılımlar ile farklı yöntemlerle satın alınmış Microsoft ya da Microsoft dışı uygulamalar veya yazılımlar için lisans sözleşmesi bilgilerini eklemenize ve yönetmenize olanak sağlar. Lisans kullanımı etkinlikleri hakkında bilgi sahibi olmak için, şirketinizdeki yönetilen lisans kullanımı bilgilerini gösteren lisans raporları oluşturabilirsiniz.

Bu adımlarda, bir mobil cihaz yapılandırma ilkesi ve bir Windows bilgisayar güvenlik duvarı ilkesi ayarlayacak ve Skype’ı mobil cihazlar kaydolduktan sonra kullanılabilir bir yükleme olarak yapılandıracaksınız. Yeni bir ilke ekleyip dağıttıktan sonra, ilkeyi dağıttığınız gruptaki tüm kullanıcılar veya cihazlar ayarları temel ilke olarak alır. Bu ilkelerin ayarlarını istediğiniz zaman yönetim konsolundaki **İlke** çalışma alanında gözden geçirebilir ve düzenleyebilirsiniz.

## Bir mobil cihaz yapılandırma ilkesi oluşturma ve dağıtma

1.  [Intune Yönetim Konsolu](https://manage.microsoft.com/)'nu açın.

2.  Sol bölmede **İlke** simgesini seçin.

3.  **İlkeye Genel Bakış** sayfasındaki **Görevler** listesinde, **İlke Ekle**'yi seçin.

4.  İlke listesinde, ilke oluşturmak istediğiniz platformu genişletin, **Genel Yapılandırma**’yı seçin, **Önerilen Ayarlarla İlke Oluştur ve Dağıt**’ı seçin ve ardından **İlkeyi Oluştur**’u seçin.

5.  **Bu ilkeyi dağıtmak istediğiniz grupları seçin** istemiyle karşılaştığınızda, listeden **Deneme Kullanıcılarım**’ı seçin ve **Ekle** &gt; **Tamam**’ı seçin.

İlkeniz, yapılandırma ilkeleri listesinde görüntülenir ve **Deneme Kullanıcılarım** grubuna dağıtılmış olur. Ayarlarını görüntülemek için ilkeye çift tıklayın.

## Mobil cihazlar için Skype uygulamasını yayımlama

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Uygulamalar** simgesini ve sonra **Uygulamalar** &gt; **Uygulama Ekle**’yi seçin. İstenirse, Intune kimlik bilgilerinizi girin.

    > [!NOTE]
    > **Intune Software Publisher** 'ı ilk kez başlattığınızda, uygulama yüklenirken kısa bir gecikme oluşur.

2.  Güvenlik uyarısını gözden geçirin ve **Çalıştır**'ı seçin.

3.  **Başlamadan önce** sayfasında **İleri**'yi seçin.

4.  **Yazılım kurulumu** sayfasındaki **Bu yazılımın cihazlar için nasıl kullanılabilir hale getirileceğini seçin**bölümünden **Dış bağlantı**'yı seçin.

5.  **URL'yi belirtin**bölümünde, yazılıma ait dış bağlantıyı girin ve ardından **İleri**'yi seçin. URL’nin başına **https://** yazdığınızdan emin olun. Skype uygulaması için, kullandığınız mobil cihaz platformuyla eşleşen aşağıdaki bağlantıyı kullanın:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 veya Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  **Yazılım açıklaması** sayfasında, kullanıcıların Şirket Portalı’nda yazılım için görmesini istediğiniz bilgileri sağlayın ve ardından **İleri**'yi seçin. Aşağıdaki ayarlar kullanılabilir (bu örnek, Skype'a atıfta bulunmaktadır):

    -   **Yayımcı:** Yayımcının adını girin, **Microsoft**

    -   **Ad:** **Skype** girin

    -   **Açıklama:** Yazılım için bir açıklama girin; örn. **Skype iletişim uygulaması**

    -   **Kategori:** Bu yazılıma en uygun kategoriyi seçin, örneğin **Birlikte çalışma**

    -   **Şirket portalında bu uygulamayı öne çıkan uygulama olarak görüntüle ve vurgula:** Uygulamayı mobil cihazlardaki Şirket Portalı’nda öne çıkarmak için bu seçeneği belirleyin.

    -   **Simge:**  (İsteğe bağlı) Yazılımla bir simgeyi ilişkilendirmek isteyip istemediğinizi seçin. En büyük simge boyutu 250 x 250 pikseldir, ancak önerilen simge boyutu 32 x 32 pikseldir.

7.  **Özet** sayfasında, yazılım bilgilerini doğrulayın ve ardından **Karşıya yükle**'yi seçin. Sihirbazdan çıkmak için **Kapat**’ı seçin.

8.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Uygulamalar** &gt; **Uygulamalar** &gt; **Skype** &gt; **Dağıtımı Yönet**’i seçin.

9. **Grup Seç** sayfasında, **Deneme Kullanıcılarım**’ı seçerek yazılımı bu kullanıcı grubuna dağıtın ve ardından **Ekle** &gt; **İleri**’yi seçin.

10. **Dağıtım Eylemi** sayfasında, **Onay** sütunundan grubunuz için **Kullanılabilir Yükleme** 'yi seçin.

11. **Son**’u seçin.

Skype uygulaması artık Şirket Portalı’ndan mobil cihazlara yüklenebilir, ancak önce Intune yazılımını bilgisayarlara ve mobil cihazlara yüklemeniz gerekir.

### Sonraki adımlar
Tebrikler! *Microsoft Intune değerlendirme* gözden geçirmesinin 4. adımını tamamladınız.

>[!div class="step-by-step"]

>[&larr; **Gruplar Oluşturma**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)     [**Cihazları Kaydetme** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md)  



<!--HONumber=Jun16_HO4-->


