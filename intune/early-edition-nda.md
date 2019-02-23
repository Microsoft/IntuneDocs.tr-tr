---
title: Erken sürüm - Intune
titlesuffix: ''
description: Microsoft Intune erken sürüm
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1ff65e1b48815cd5964aa7498fa6ba54df50e09
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742304"
---
# <a name="the-early-edition-for-microsoft-intune---february-2019"></a>Erken sürüm Microsoft Intune - Şubat 2019

> [!Note]
> NDA bildirimi: Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune
<!-- 1902 start-->


<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>İş uygulamalarına yönelik çevrimiçi lisanslı Microsoft Store dağıtımı <!-- 1672660  -->
Gerekli çevrimiçi lisanslı Microsoft Store cihaz bağlamında kurumsal uygulamalar için atayamazsınız olacaktır. Bu şekilde bir iş uygulaması için Microsoft Store dağıtımı, cihazdaki tüm kullanıcılar için yüklenecek uygulamayı etkinleştirir. Bu yalnızca Windows 10 RS4 + Masaüstü cihazları için geçerlidir. Cihaz bağlamında yükleme seçeneği, istemci uygulamaları atama sayfasında MSFB çevrimiçi lisanslı uygulamaları için kullanılabilir.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı <!-- 1171203 -->
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, şunları yapabileceksiniz yönetilen Google Play mağazası uygulamalarını dağıtma ve LOB uygulamaları kullanıcılara için kullanılacak. Özellikle, BT'nin son kullanıcılara cihazlarının güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi sağlamak. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune ilkeleri, kimlik doğrulama yöntemi ve şirket Portalı Uygulama yüklemesi güncelleştirme  <!-- 1927359 -->
Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlarda, el ile uygulama Mağazası'ndan son kullanıcılar tarafından yüklendiğinde, Intune Şirket portalı artık destekleyecektir. Bu değişiklik, yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile doğrulandığında geçerlidir. Bu değişiklik, yalnızca aracılığıyla kaydedilmiş iOS cihazları etkiler:  
* Apple configurator
* Apple İşletme Yöneticisi
* Apple School Manager
* Apple aygıt kayıt programı (DEP)

Kullanıcıların uygulama Mağazası'ndan Şirket portalı uygulamasını yüklediğinizde ve onun üzerinden bu cihazları kaydetmek deneyin, bunlar bir hatayla karşılaşırsınız. Bu cihazlar, bu, otomatik olarak, kayıt sırasında Intune tarafından gönderildiğinde yalnızca şirket portalını kullanması beklenen. Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. DEP cihaz kullanıcılarınız Şirket portalı olmasını istiyorsanız, tercihlerinizi bir kayıt profili belirtmeniz gerekir. Ayrıca, **Cihazınızı tanımlamanız** Şirket portalı uygulamasında ekran yakında geçersiz olacak.  
Zaten kayıtlı DEP cihazlarında şirket Portalı'nı yüklemek için Intune'a gitmeniz gerekir > istemci uygulamaları ve uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak gönderin. Bu adımların hakkında ayrıntılı bilgi gelecekteki belgelere renkle gösterilir.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Yönetim Şablonları genel Önizleme aşamasındadır ve kendi yapılandırma profiline taşınır <!-- 3322847 -->
Intune Yönetim Şablonları (**cihaz Yapılandırması** > **Yönetim Şablonları**) şu anda özel Önizleme aşamasındadır. Bu güncelleştirme ile: Yönetim Şablonları, Intune'da yönetilebilir 300 ayarları içerir. Daha önce bu ayarlar, yalnızca Grup İlkesi Düzenleyicisi'nde vardı.
Yönetim Şablonları genel önizlemede Yönetim Şablonları hareket etmesini **cihaz Yapılandırması** > **Yönetim Şablonları** için **cihaz Yapılandırma** > **profilleri** >**profili oluşturma** > içinde **Platform**, seçin  **Windows 10 ve üzeri**, **profil türü**, seçin **Yönetim Şablonları**.
Raporlama etkinse geçerlidir: Windows 10 ve üzeri

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Intune macOS Şirket portalı koyu modu <!-- 3300524 -->
Intune macOS Şirket portalı, macOS için artık koyu modunu destekler. Bir macOS 10.14 + cihazda koyu modunu etkinleştirdiğinizde, Şirket portalı görünümünü mod yansıtan renkleri için ayarlanır.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
