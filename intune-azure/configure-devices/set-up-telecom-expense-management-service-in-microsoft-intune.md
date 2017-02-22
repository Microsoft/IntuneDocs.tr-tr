---
title: "Telekom gider yönetimi hizmetini ayarlama | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Saaswedo telekom gider yönetimi hizmetini Intune ile tümleştirilecek şekilde yapılandırın."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Intune Azure önizlemesinde telekom gider yönetimi hizmetini ayarlama
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune, üçüncü taraf yazılım geliştiricisi Saaswedo’nun Datalert telekom gider yönetimi çözümüyle tümleştirilmiştir. Datalert, telekom veri kullanımını yönetmenize ve Intune tarafından yönetilen cihazlarınızda veri ve dolaşımda yüksek maliyetli ve beklenmedik fazla kullanımları önlemenize olanak tanıyan gerçek zamanlı bir telekom gider yönetimi yazılımıdır. Intune'un Datalert’le tümleştirilmesi, sınırlar önceden tanımlanmış eşikleri aştığında verilen otomatik uyarıları kullanarak, dolaşım ve yerel veri kullanım sınırlarını merkezi olarak ayarlamanıza, izlemenize ve zorunlu tutmanıza olanak tanır. Kullanıcıların eşiği aşması durumunda, tek tek son kullanıcılara veya son kullanıcı gruplarına dolaşımı devre dışı bırakma gibi farklı eylemler uygulanacak şekilde hizmeti yapılandırabilirsiniz. Datalert yönetim konsolundan veri kullanım ve izleme bilgilerini içeren raporlar sağlanır.

Intune ile Datalert hizmetini kullanabilmeniz için, önce Datalert konsolunda ve Intune’da ayarları yapılandırmalısınız. Datalert hizmeti ve Intune için bağlantının açılması gerekir. Bağlantının Datalert tarafı etkinleştirilir ancak Intune tarafı etkinleştirilmezse, Intune iletişimi alır ancak yoksayar.

>[!NOTE]
>Deneme kiracınızda bu özelliği etkinleştirmek için, gerekli yazılım lisanslarında Datalert desteği ve etkinleştirme konusunda lütfen [Microsoft desteğine başvurun](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

## <a name="supported-platforms"></a>Desteklenen platformlar

- Samsung Knox
- iOS 8.0 ve üzeri

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Intune için abonelik
- Datalert telekom gider yönetimi hizmeti için abonelik

## <a name="list-of-telecom-expense-management-providers"></a>Telekom gider yönetimi sağlayıcıları listesi

Intune şu anda aşağıdaki telekom gider yönetimi sağlayıcılarıyla tümleştirilmiştir:

[Saaswedo Datalert telekom gider yönetimi hizmeti](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Intune’u Datalert hizmetiyle çalışacak şekilde yapılandırma

 

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Kurulum** > **Telecom Gider Yönetimi**’ni seçin.
2. **Telecom Gider Yönetimi**’nin altında **Bağlantı durumu**’nu seçin.

3. **TEM hizmet sağlayıcılarının listesi**’ni seçin ve ardından gösterilen listeden sağlayıcınızı seçin. Sağlayıcınıza özgü bir sayfa açılır. Saaswedo için, Datalert sayfası açılır. Abonelik satın almak için Saaswedo Datalert ile çalışmalısınız.

4. **Datalert** yönetim konsolunda:

    a. **Ayarlar** sekmesine gidin ve sonra da **MDM yapılandırması** bölümüne gidin.

    b. Sayfada ayarları girebilmek için **Kilidi Aç**’ı seçin.

    c. **Sunucu MDM** için **Microsoft Intune**’u seçin.

    d. **Kiracı Kimliği** için Intune kiracı kimliğinizi girin ve **Bağlantı** düğmesini seçin. **Bağlantı**’nın seçilmesi, önceden Intune ile Datalert bağlantılarının olmadığından emin olmak için Intune ile Datalert hizmetini denetler. Birkaç saniye sonra Microsoft oturum açma sayfası görüntülenir ve onun ardından Datalert Azure kimlik doğrulaması gelir.

    e. Microsoft kimlik doğrulaması sayfasında **Kabul Et**’i seçin. Datalert “teşekkür ederiz” sayfasına yönlendirilirsiniz ve bu sayfa birkaç saniye sonra kapatılır. Datalert bağlantıyı doğrular ve doğrulanan öğe listesinin yanında yeşil onay işaretleri görüntülenir. Doğrulama başarısız olursa, kırmızı bir ileti görürsünüz. Böyle bir durum olursa, yardım için Datalert Desteği’ne başvurun.

5. Birkaç dakika bekleyin ve ardından Azure portalına gidin ve Bağlantı durumunun **Etkin** olarak gösterilip gösterilmediğini denetleyin. 

    >[!NOTE]
    >Deneme kiracınızda bu özelliği etkinleştirmek için lütfen [Microsoft desteğe başvurun](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Datalert yönetim konsoluna dönün ve veri satırlarınızı yapılandırın:

    a. **Ayarlar** sekmesine gidin.

    b. **Kurulum** sihirbazına gidin ve sihirbazdaki adımları izleyin.



Datalert hizmeti artık etkindir; veri kullanımını izlemeye ve yapılandırılmış kullanım sınırlarını aşan cihazlarda hücresel ve dolaşım verilerini devre dışı bırakmaya başlar.

## <a name="turning-off-the-datalert-service"></a>Datalert hizmetini kapatma

Azure portalında Datalert hizmetini devre dışı bırakırsanız:

- Geçmişte kullanım sınırlarının ihlal edilmesinden dolayı cihazlara uygulanmış olan tüm eylemler geri alınır.
- Artık kullanıcıların veri erişimi ve dolaşımı engellenmez.
- Intune hizmetten gelen sinyalleri almaya devam eder ancak bunları yoksayar.

**Hizmeti kapatmak için**

1. Azure portalının **Telekom Gider Yönetimi** dikey penceresinde **Devre Dışı Bırak**’ı seçin.

2. **Kaydet**’i seçin.

## <a name="viewing-data-usage-and-roaming-reports"></a>Veri kullanımı ve dolaşım raporlarını görüntüleme

Veri kullanım raporlaması şu anda yalnızca Saaswedo’nun Datalert yönetim konsolunda sağlanmaktadır.



<!--HONumber=Feb17_HO2-->


