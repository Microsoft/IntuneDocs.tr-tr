---
title: "Intune değerlendirme kılavuzu | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 4af13629986e7cef814104f3d1f298eb2be240ac
ms.openlocfilehash: 26ecc3dfe8816da9f30829901d929af53b1bedc0


---

# Intune değerlendirme kılavuzu
Mobil cihazlarınızı ve bilgisayarlarınızı yönetmek için 30 günlük ücretsiz Intune değerlendirmesi ayarlamak hızlı ve kolaydır. Değerlendirme içinde birkaç basit adımla 100’e kadar kullanıcıyı ve cihazı ekleyebilir, gruplar oluşturabilir, uyumluluk ilkelerini yapılandırabilir, mobil cihazları ve bilgisayarları kaydedebilir ve yönetebilirsiniz.

Bu konuda, Intune’un özelliklerini ve becerilerini değerlendirebilmeniz için Intune değerlendirmesini çalışır duruma getirmenin temel adımlarını öğrenecek ve hizmet hakkında genel bir bakış edineceksiniz.

Microsoft Intune’un ücretsiz bir değerlendirmesine ve cihazlarınızı yönetmeye başlamanın ne kadar kolay olduğunu öğrenmek için aşağıdaki beş dakikalık tanıtım videosunu izleyin. Videonun ilk kısmında, “kullanımdan kaldırılmış” bir portaldan bahsedilmektedir, yani farklı bir portal kullanacak olsanız dahi, adımlar temelde aynı olacaktır. Portal hakkında daha fazla bilgiyi [buradan](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365) edinebilirsiniz.

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Başlamadan önce
Intune ile çalışmaya başlamadan önce şunlara ihtiyacınız vardır:

-   Intune kullanıcı hesaplarını oluşturacağınız (**Office 365 yönetim merkezi**) ve cihazları, grupları ve ilkeleri yöneteceğiniz (**Intune yönetim konsolu**) web sitelerine erişmek için kullanabileceğiniz, Silverlight özellikli web tarayıcısına sahip bir cihaz.

-   Intune kullanıcılarının Şirket Portalı’nı kullanarak cihazlarını nasıl kaydedeceğini ve yöneteceğini test etmek için kullanacağınız web tarayıcısı olan ikinci bir cihaz. Ayrıca, kullanıcıların uygulamaları nasıl bulacağını, yükleyeceğini ve yöneticilerden nasıl yardım isteyeceğini de test edeceksiniz. İkinci bir cihazınız yoksa Intune yönetimi için kullandığınız tarayıcının “gizlilik modu”nu kullanabilirsiniz (örneğin; Internet Explorer’da **Araçlar** &gt; **InPrivate Gözatma**’ya tıklayabilirsiniz).

-   Mevcut bir Microsoft Online Services hesabınız varsa, bu hesaba ait yönetici kimlik bilgilerine ihtiyacınız vardır. Bu tür bir hesabınız yoksa veya bu Intune kiracısını yalnızca değerlendirme amacıyla kullanmak istiyorsanız yönetici kimlik bilgilerine ihtiyacınız yoktur.

-   Intune değerlendirmesiyle iOS veya Windows Phone cihazlarını yönetecekseniz sertifikalara (veya anahtarlara) ve bu sertifikaları almak için gereken hesaplara ihtiyacınız vardır (aşağıdaki tabloya bakın). Android cihazlar için ek sertifika gereksinimi yoktur.

    |Platform|Sertifika Gereksinimleri|Daha fazla bilgi|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 ve Windows Phone 8 |Şirket Portalı uygulamasını Mağaza’dan yükleyen Windows Phone 8.1 kullanıcıları için sertifika gerekmez. Windows Phone 8.0 için veya Intune kullanarak Şirket Portalı uygulamasını Windows Phone 8.1 cihazlara dağıtmak için bir Symantec sertifikası gerekir.|Bu kılavuz, kullanıcılarınızın Şirket Portalı uygulamasını bir Windows Phone 8.1 veya üzeri bir cihazda Mağaza’dan aldığını varsayar. Windows Phone 8.0 desteği hakkında daha fazla bilgi için, bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).|
    |Windows 10, Windows RT 8.1, Windows RT veya Windows 8.1 cihazları|Windows RT ve Windows cihazlarını kaydetmek için sertifika gereksinimi yoktur.|[Microsoft Intune ile Windows bilgisayarı istemcisini yükleme](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 veya üzeri|Bir Apple Anında İletilen Bildirim Servisi sertifikası alın.|Burada açıklandığı gibi, Apple'dan bir Apple Anında İletilen Bildirim Servisi sertifikası isteyin: [Microsoft Intune ile iOS ve Mac yönetimi ayarlama](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).|

## Intune 30 günlük değerlendirmesini tamamlamak için adımlar
- [1. adım 30 günlük değerlendirme için oturum açma veya kaydolma](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Intune’a kaydolmadan veya oturum açmadan önce, mevcut bir hesabı kullanarak mı oturum açacağınızı yoksa yalnızca Microsoft Intune’un 30 günlük değerlendirmesi için kullanılacak geçici bir hesap mı oluşturacağınızı düşünmelisiniz.
- [2. adım: Kullanıcı ekleme](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Artık hesabınızı ayarladığınıza göre, Intune’a bireysel kullanıcılar ekleyeceksiniz veya toplu olarak kullanıcı ekleyeceksiniz (bu bölümdeki yönergelere bakın). Başlamadan önce, Intune’un yönetici hesaplarını nasıl işlediğini anlamanız önemlidir.
- [3. adım: Kullanıcıları ve cihazları düzenlemek için grup oluşturma](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Intune’daki gruplar, cihazlarınızı ve kullanıcılarınızı yönetmek için büyük esneklik sağlar. Grupları kuruluş gereksinimlerinize (örneğin, coğrafi konum, bölüm veya donanım özelliklerine göre) uygun şekilde ayarlayabilir ve bunları bir kullanıcı kümesi için ilke ayarlamaktan bir cihaz kümesi için uygulama dağıtmaya kadar çeşitli yönetim görevlerini gerçekleştirmek için kullanabilirsiniz.
- [4. adım: İlke oluşturma ve uygulama yayımlama](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Intune ilkeleri, mobil cihazlarda güvenlik ayarlarını denetlemenize, bilgisayarlar için Windows Güvenlik Duvarı ve Endpoint Protection ayarlarını korumanıza ve uygulamaları dağıtmanıza yardımcı olan ayarlar sağlar.
- [5. adım: Mobil cihazları kaydetme ve uygulama yükleme](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Intune ile mobil cihaz yönetimi ayarlamak için, mobil cihaz yönetimi yetkilisini ayarlamanız, belirli cihaz platformları için yönetimi etkinleştirmeniz ve cihazlarınızı Şirket Portalı uygulamasına kaydetmeniz gerekir. Ardından, yayımladığınız Microsoft Skype uygulamasını dağıtabilirsiniz.
- [6. adım: Diğer seçenekler ve ek özellikler](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Uyarıları, raporlar ve diğer Intune özelliklerini iş ihtiyaçlarınızı karşılamak için nasıl kullanılacağınızı seçin.
- [7. adım: Sonraki adımlar](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Bir Intune ücretli aboneliğine geçmeye hazırlanın ve "FastTrack Merkezi Avantajından”yararlanın.


### Sonraki adımlar
30 günlük değerlendirme aboneliğinizi kullanmaya başlama zamanı geldi!

>[!div class="step-by-step"]
[**Intune’a kaydolun** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Ayrıca bkz.
[Intune hızlı başlangıç kılavuzu](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Jun16_HO4-->


