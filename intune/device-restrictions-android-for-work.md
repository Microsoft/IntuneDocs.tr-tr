---
title: "Android for Work için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "Android for Work cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca51c413e3148039b05a9d05a9a511e7158c9a1c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Android for Work cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>İş profili ayarları
- **İş ve kişisel profiller arasında veri paylaşımı** - İş profilindeki uygulamaların kişisel profildeki uygulamalarla paylaşıp paylaşamayacağını denetlemek için bu ayarı kullanın. Bu ayar, uygulamalar içindeki paylaşma eylemlerini (Chrome tarayıcı uygulamasındaki **Paylaş...** seçeneği gibi) denetler ve kopyala/yapıştır pano davranışına uygulanmaz. [Uygulama koruma ilkesi ayarlarından](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) farklı olarak, cihaz kısıtlama ayarları Intune portalından yönetilir ve yönetilen uygulamaları yalıtmak için Android for Work iş profili ayrımını kullanır. Aşağıdakilerden birini seçin:
    - **Varsayılan paylaşım kısıtlamaları** - Bu, cihazın çalıştırdığı Android sürümüne göre farklılık gösteren varsayılan paylaşım davranışıdır. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu, iş profilinden kişisel profile veri paylaşılmasını önler. Google, 6.0 ve sonrası sürümleri çalıştıran cihazlarda, kişisel profilden iş profiline verileri paylaşmayı engellemek için bir yol sunmaz.   
    - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir** - Kişisel profilden iş profiline paylaşıma izin veren bu yerleşik Android özelliğini etkinleştirmek için bu seçeneği kullanın. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
    - **Sınırların ötesinde paylaşıma izin ver** - İş profili sınırının ötesinde her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki armasız uygulamalar ile veri paylaşabilir. İş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmına aktarılmasına izin verdiğinden, bu ayarı dikkatli kullanın.

-   **Cihaz kilitliyken iş profili bildirimleri** - İş profilindeki uygulamaların cihaz kilitliyken bildirimlerde veri gösterip gösteremeyeceğini denetler.
-   **Varsayılan uygulama izinleri** - İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilke, tüm izinlerin sorulmadan otomatik olarak verilmesi, reddedilmesi veya kararın son kullanıcıya bırakılması seçeneklerinden birini belirlemenizi sağlar. Aşağıdakilerden birini seçin:
    -   **Cihaz varsayılanı**
    -   **Sor**
    -   **Otomatik olarak izin ver**
    -   **Otomatik olarak reddet**

    İzinlerin verme durumu, (**Mobil Uygulamalar** > **Uygulama yapılandırma ilkeleri** altından) bir Uygulama Yapılandırma ilkesi tanımlanarak tek uygulamalar için daha da netleştirilebilir.

### <a name="work-profile-password"></a>İş profili parolası
- **İş Profili Parolası İste** - (iş profili etkin olarak Android 7.0 ve üstü) Yalnızca iş profilindeki uygulamalar için geçerli olan bir geçiş kodu ilkesi tanımlayın. Son kullanıcının, varsayılan olarak, tanımlı iki ayrı PIN kullanma veya bu tanımlı iki PIN’den güçlü olanı kullanma seçeneği bulunur.
- **En düşük parola uzunluğu** - Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını belirtin (**4**-**16** arası)
- **Kilitlenmesine kadar ekranın boşta kalma süresi** - Etkin olmayan bir cihazın iş profilindeki bir uygulamayı çalıştırmak için kullanıcıdan iş profili parolasını yeniden girmesini istemesine kadar geçecek süreyi seçin.
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
- **Akıllı Kilit ve diğer güven aracıları** - Uyumlu cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) iş profili parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanabilirsiniz.

## <a name="password"></a>Parola

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
- **Akıllı Kilit ve diğer güven aracıları** - Uyumlu cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı, kullanıcıların Akıllı Kilit’i yapılandırmasını önlemek için kullanabilirsiniz.
