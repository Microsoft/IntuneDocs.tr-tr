---
title: "Android for Work için Intune cihaz kısıtlama ayarları"
titlesuffix: Azure portal
description: "Android for Work cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: beb8368aa2db33df84bb64985177b47beebc80ac
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Android for Work cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>İş profili ayarları
-   **İş profilleri ve kişisel profiller arasında kopyalama ve yapıştırma** - İş uygulamaları ve kişisel uygulamalar arasında kopyalama ve yapıştırma işlemlerini denetler. Engellemeyi etkinleştirmek için **Engelle**’yi seçin. Engellemeyi devre dışı bırakmak için **Yapılandırılmadı**’yı seçin.
- **İş ve kişisel profiller arasında veri paylaşımı** - İş profilindeki uygulamaların kişisel profildeki uygulamalarla paylaşıp paylaşamayacağını denetlemek için bu ayarı kullanın. Bu ayar, uygulamalar içindeki paylaşma eylemlerini (Chrome tarayıcısı uygulamasındaki **Paylaş...** seçeneği gibi) denetler ve kopyala/yapıştır pano davranışında geçerli değildir. [Uygulama koruma ilkesi ayarlarından](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) farklı olarak, cihaz kısıtlama ayarları Intune portalından yönetilir ve yönetilen uygulamaları yalıtmak için Android for Work iş profili ayrımını kullanır. Aşağıdakilerden birini seçin:
    - **Varsayılan paylaşım kısıtlamaları** - Bu ayar, cihazın çalıştırdığı Android sürümüne göre farklılık gösteren varsayılan paylaşım davranışıdır. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Google, 6.0 ve sonrası sürümleri çalıştıran cihazlarda, kişisel profilden iş profiline verileri paylaşmayı engellemek için bir yol sunmaz.   
    - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir** - Kişisel profilden iş profiline paylaşıma izin veren bu yerleşik Android özelliğini etkinleştirmek için bu seçeneği kullanın. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
    - **Sınırların ötesinde paylaşıma izin ver** - İş profili sınırının ötesinde her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar ile iş profilindeki yönetilen uygulamalar, cihazın yönetilmeyen kısmındaki uygulamalarla paylaşım yapabilir. O yüzden bu ayarı kullanırken dikkatli olun.

-   **Cihaz kilitliyken iş profili bildirimleri** - İş profilindeki uygulamaların cihaz kilitliyken bildirimlerde veri gösterip gösteremeyeceğini denetler.
-   **Varsayılan uygulama izinleri** - İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilke, şu seçeneklerden birini belirlemenizi sağlar: Tüm izinlerin sorulmadan otomatik olarak verilmesi, reddedilmesi veya kararın son kullanıcıya bırakılması. Aşağıdakilerden birini seçin:
    -   **Cihaz varsayılanı**
    -   **Sor**
    -   **Otomatik olarak izin ver**
    -   **Otomatik olarak reddet**

    İzinlerin verme durumu, (**Mobil Uygulamalar** > **Uygulama yapılandırma ilkeleri** altından) bir Uygulama Yapılandırma ilkesi tanımlanarak tek uygulamalar için daha da netleştirilebilir.

### <a name="work-profile-password"></a>İş profili parolası
- **İş Profili Parolası İste** - (iş profili etkin olarak Android 7.0 ve üstü) Yalnızca iş profilindeki uygulamalar için geçerli olan bir geçiş kodu ilkesi tanımlayın. Son kullanıcının varsayılan olarak iki ayrı tanımlı PIN kullanma veya bunlardan güçlü olanını tercih etme seçeneği bulunur.
- **En düşük parola uzunluğu** - Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını belirtin (**4**-**16** arası)
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - İş profili kilitlenmeden önce geçmesi gereken süre miktarını seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı** - İş profili cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)** - Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
- **Gerekli parola türü** - Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
    - **Cihaz varsayılanı**
    - **Düşük güvenlik biyometriği**
    - **Gerekli**
    - **En az sayısal**
    - **Sayısal karmaşık** - ('1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez)
    - **En az alfabetik**
    - **En az alfasayısal**
    - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle** -Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak izi ile kilit açma** - Bir son kullanıcının cihaz kilidini açmak için parmak izi tarayıcısını kullanmasını engeller.
- **Akıllı Kilit ve diğer güven aracıları** - Uyumlu cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) iş profili parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.

## <a name="device-password"></a>Cihaz parolası

- **En düşük parola uzunluğu** - Kullanıcı parolalarının içermesi gereken en düşük rakam veya karakter sayısını belirtin (**4**-**14** arası)
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçmesi gereken süreyi seçin.
- **Cihaz silinmeden önceki oturum açma hatası sayısı** - Tüm veriler cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)** - Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
- **Gerekli parola türü** - Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
    - **Cihaz varsayılanı**
    - **Düşük güvenlik biyometriği**
    - **Gerekli**
    - **En az sayısal**
    - **Sayısal karmaşık** - ('1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez)
    - **En az alfabetik**
    - **En az alfasayısal**
    - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle** -Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak izi ile kilit açma** - Bir son kullanıcının cihaz kilidini açmak için parmak izi tarayıcısını kullanmasını engeller.
- **Akıllı Kilit ve diğer güven aracıları** - Uyumlu cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.

## <a name="system-security"></a>Sistem güvenliği

 - **Uygulamalarda tehdit taraması** - İş profillerinde ve kişisel profillerde **Uygulamaları Doğrula** ayarının açık olmasını zorunlu tutar.

   > [!Note]  
   > Bu ayar yalnızca Android O ve üstü cihazlarda çalışır. 

## <a name="next-steps"></a>Sonraki adımlar

[Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) konusundaki bilgileri kullanarak profili kaydedip kullanıcı ve cihazlara atayın.
