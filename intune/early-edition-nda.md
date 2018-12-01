---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 542efda11e6d1c6b61f8cbc08ea6c29e36e1f8fc
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728727"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>Microsoft Intune için erken sürüm - Kasım 2018

> [!Note]
> NDA bildirimi: Aşağıdaki değişiklikler, Intune için geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Şirkete ait, denetimli iOS cihazlarından uygulamaları kaldırma <!-- 1281677 -->
Şirkete ait, denetimli iOS cihazlarından herhangi bir uygulamayı kaldırabileceksiniz. **Kaldırma** atama türüyle kullanıcı veya cihaz gruplarını hedefleyerek herhangi bir uygulamayı kaldırabilirsiniz. Kişisel veya denetimsiz iOS cihazlarında yalnızca Intune kullanarak yüklenen uygulamaları kaldırabilirsiniz.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>Apple School Manager hesapları için macOS Aygıt Kayıt Programı desteği <!--3006133-->
Intune, Apple School Manager hesapları için macOS cihazlarında Aygıt Kayıt Programı kullanımını destekleyecektir.

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Yönetilen Giriş Ekranı uygulamasında özel arka plan ayarlama  <!-- 3041945 -->
Android Kurumsal çok uygulamalı bilgi noktası modu cihazlarında Yönetilen Giriş Ekranı arka planının görünümünü özelleştirmenizi sağlayan bir ayar ekleyeceğiz.  **Özel URL arka planı**’nı yapılandırmak için Azure portalı > Cihaz yapılandırması’ndaki Intune’a gidin. Geçerli cihaz yapılandırma profilini seçin veya bilgi noktası ayarlarını yapılandırmak için yeni profil oluşturun.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Windows 10 ve üzeri için yeni Microsoft Edge tarayıcı ayarları <!-- 3174639 -->
Cihazlarınızda Microsoft Edge tarayıcısını denetlemenize ve yönetmenize yardımcı olan yeni bir ayar eklenecektir. Geçerli ayarların listesi için bkz. [Windows 10 (ve üzeri) için cihaz kısıtlaması](device-restrictions-windows-10.md#microsoft-edge-browser).

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Intune uygulama koruma ilkeleri kullanıcı arabirimi güncelleştirmesi <!-- 3251427 -->

Intune Uygulama koruma ilkeleri, Microsoft Outlook ve Word gibi Intune tarafından korunan uygulamalar için çeşitli veri koruma ayarlarını yapılandırmanıza olanak sağlar. Daha kolay anlaşılabilmeleri için ayar ve düğme etiketlerini değiştiriyoruz. Denetimler **evet**/**hayır** denetimlerinden **engelle**/**izin ver** ve **devre dışı bırak**/**etkinleştir** denetimlerine dönüştürülecek ve netlik sağlamak amacıyla etiketler de güncelleştirilecek. Ayrıca ayarlar da yeni denetiminde ayar ve etiketinin yan yana olduğu, daha iyi gezinti sağlayan biçimde yeniden biçimlendirilecek. Varsayılan ayarlar ve ayar sayısı aynı kalacak ancak bu değişiklik kullanıcının seçili uygulama koruma ilkelerini uygulaması için ayarları anlamasını, gezinmesini ve kullanmasını kolaylaştıracak.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Microsoft tarafından önerilen Güvenlik Taban Çizgili ayarları kullanma <!-- 2055484 -->
Intune, Windows Defender ATP ve Office 365 ATP dahil güvenliğe odaklı diğer hizmetlerle tümleşir. Müşteriler, Microsoft 365 hizmetleri çapında ortak bir strateji ve birbiriyle bütünleşen bir dizi uçtan uca güvenlik iş akışı istiyor. Amacımız, stratejileri birbiriyle uyumlu hale getirmek ve güvenlik işlemleri ve sık kullanılan yönetici görevleri arasında bir köprü oluşturan çözümler geliştirmek. Intune olarak bu amaca Microsoft tarafından önerilen bir dizi "Güvenlik taban çizgisini" (**Intune** > **Güvenlik taban çizgileri**) yayımlayarak ulaşmayı hedefliyoruz.  Yöneticiler, doğrudan bu taban çizgilerinden güvenlik ilkeleri oluşturabilecek ve sonra bunları kullanıcılarına dağıtabilecekler. Ayrıca en iyi yöntem olan önerileri kuruluşlarının ihtiyaçlarını karşılayacak şekilde özelleştirebilirler. Intune, cihazların bu taban çizgilerle uyumlu kalmasını sağlar ve yöneticilere uyumlu olmayan kullanıcıları ve cihazları bildirir.

### <a name="scope-tags-for-apps---1081941---"></a>Uygulamalar için kapsam etiketleri <!--1081941 -->
Intune kaynaklarına erişimi sınırlamak için kapsam etiketleri oluşturabileceksiniz. Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.
Bir kapsam etiketi oluşturmak için **Intune rolleri** > **Kapsam (Etiketler)** > **Oluştur**’u seçin.
Kapsam etiketini bir rol atamasına eklemek için **Intune rolleri** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)**’i seçin.
Kapsam etiketini bir yapılandırma profiline eklemek için **Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)**’i seçin.

### <a name="tenant-health-dashboard----1124854---"></a>Kiracı Sistem Durumu panosu <!-- 1124854 -->
Intune Kiracı Durumu sayfası tek bir yerde kiracı durumu bilgileri sağlayacaktır. Sayfa 4 bölüme ayrılmıştır:  
- **Kiracı Ayrıntıları**: MDM Yetkiliniz, kiracınızdaki toplam kayıtlı cihaz sayısı ve lisans sayınız gibi bilgileri içerir. Bu bölüm, kiracınız için geçerli hizmet sürümünü de sağlanır.
- **Bağlayıcı Durumu**: Apple VPP, İş için Windows Store ve Sertifika bağlayıcıları gibi yapılandırılmış bağlayıcıların bilgilerini içerir. Bunların geçerli durumu temel alındığında bağlayıcılar *Sağlıklı*, *Uyarı* veya *Sağlıksız* olarak işaretlenir.
- **Intune Hizmet Durumu**: Kiracınız için etkin olayları ve kesintileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.
- **Intune Haberleri**: Kiracınızın en yeni Intune özelliklerini aldığı bildirimleri gibi şeyler dahil, kiracınız için etkin iletileri içerir. Bu bölümdeki bilgiler doğrudan Office İleti Merkezi'nden ([https://portal.office.com](https://portal.office.com)) alınır.


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Kullanıcı kaydı olmadan dağıtılan WIP ilkeleri <!-- 1434452 -->
Windows Bilgi Koruması (WIP) ilkeleri, MDM kullanıcılarının Windows 10 cihazlarını kaydetmesini gerektirmeden dağıtılabilecektir. Bu yapılandırma, kullanıcıların Windows cihazlarının yönetimini sürdürmesini sağlarken şirketlerin de kurumsal belgelerini WIP yapılandırmasına göre korumasını sağlar. Belgeler bir kez bir WIP ilkesiyle korunduktan sonra korumalı veriler bir Intune yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihaz seçilerek ve bir silme isteği gönderilerek WIP İlkesi aracılığıyla korunan tüm veriler kullanılamaz hale getirilir. Azure portalındaki Intune'dan **Mobil uygulama** > **Uygulama seçmeli silme**'yi seçin.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Web verileri için Uygulama Koruma İlkesi (APP) ayarları <!-- 2662995 -->
Gerek Android gerekse iOS cihazlarında Web içeriği için uygulama ilke ayarları, gerek http gerekse https Web bağlantılarını, ayrıca iOS Evrensel Bağlantıları ve Android Uygulama Bağlantıları aracılığıyla veri aktarımını daha iyi işleyecek şekilde güncelleştirilecektir.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Şirket içi bağlayıcılar için güncelleştirme işleminde değişiklik <!-- 2277554 -->
Müşterilerden gelen geri bildirimlere dayalı olarak şirket içi bağlayıcılarda güncelleştirme işlemi değiştirilecek. Bir şirket içi bağlayıcıyı ilk yüklediğinizde güncelleştirmeler otomatik olarak gerçekleşecek. Bu değişiklik, yeni Microsoft Intune için PFX Sertifika Bağlayıcısı ile başlayacak ve ardından diğer şirket içi bağlayıcı türlerine de sağlanacak. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Configuration Manager uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager uyumluluk ayarı olacak (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Windows 10**). Configuration Manager, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak tüm Configuration Manager sinyallerinin “uyumlu” olarak döndürülmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).



