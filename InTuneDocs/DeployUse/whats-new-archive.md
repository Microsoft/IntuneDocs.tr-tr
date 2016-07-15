---
title: "Yenilikler arşivi | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 051d06afb0f29f2a97c1f06dc1102138e5f2be8f


---


## Eylül 2015
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
**Artık tüm Intune iOS yönetim özellikleri iOS 9’u destekler** iOS 9 yönetim özelliklerinin ayrıntıları için [bu blog gönderisine](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx) bakın.

**iOS için yeni mobil uygulama yapılandırma ilkesi** Yeni uygulama yapılandırma ilkesini kullanarak, iOS uygulamasına çalışırken gerekli olabilecek ayarları otomatik olarak sağlayın. Örneğin, bir ağ bağlantı noktası veya kullanıcı adı sağlayabilirsiniz. Ayrıntılar için bkz. [Uygulamaları Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://technet.microsoft.com/library/mt481447.aspx).

**iOS 9 kullanıcıları için daha kolay uygulama yönetimi**
 Bu sürümde, dağıtılmış uygulamaları iOS 9 kullanıcıları için Intune yönetimi altında kullanıma sunabilirsiniz. Daha önceki iOS sürümlerinde, bir uygulama dağıttığınızda uygulamanın yönetilmeyen bir sürümü cihazda zaten yüklü olsa bile, Intune yönetilen uygulamayı yüklemeden önce kullanıcıdan uygulamayı el ile kaldırmasını istemeniz gerekir.

 Bu Intune sürümünden itibaren, artık iOS 9 cihazlarının kullanıcılarından Intune’un uygulama yönetimini devralmasına ve ilgili mobil uygulama yönetim ilkelerini uygulamasına izin vermelerini isteyebilirsiniz.

 **Windows 10 yönetimi** Windows 10 ve Windows 10 Mobile çalıştıran kayıtlı cihazlarda parolayı, cihazı, tarayıcıyı ve diğer ayarları yapılandırmak için yeni [Windows 10 genel yapılandırma ilkesini](https://technet.microsoft.com/library/mt404697.aspx) kullanın.

 **Kayıtlı Windows 10 cihazlarında uygulamalar oluşturma ve dağıtma** Yeni yazılım yükleyici türü MDM aracılığıyla Windows Installer (&#42;.msi), Windows 10 çalıştıran kayıtlı cihazlara Windows Installer uygulamaları oluşturmanıza ve dağıtmanıza olanak tanır. Ayrıntılar için bkz. [Microsoft Intune'da uygulama dağıtımına başlayın](https://technet.microsoft.com/library/dn646955.aspx).

### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

**iOS**
* Microsoft, ürün ve hizmetlerini geliştirmek için şirket portalının performansı ve kullanımı hakkında anonim bilgileri otomatik olarak toplar. Son kullanıcılar cihazlarının Kullanım Verileri ayarını kullanarak veri toplamayı devre dışı bırakabilir, ancak yöneticilerin veri toplama üzerinde hiçbir denetimi yoktur ve son kullanıcının bu ayar ile ilgili seçimini değiştiremezler.
* iPhone 6 ve 6 Plus için tam ekran çözünürlüğü desteği
* Güvenliği arttırmaya yönelik hata düzeltmeleri

### Intune belgelerindeki yenilikler -- Eylül 2015
**Yeni konular**

|Ad|Ayrıntılar|
|----|--------|
|[Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx)|Bu, Windows 10 ve Windows 10 Mobile çalıştıran cihazlarda ayarları ve özellikleri yönetmenize olanak tanıyan yeni bir yapılandırma ilkesidir.
| [Uygulamaları Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://technet.microsoft.com/library/mt481447.aspx)|Bu, kullanıcı bir iOS uygulaması çalıştırdığında gerekebilecek ayarları otomatik olarak sağlamanıza olanak tanıyan yeni bir ilke türüdür. |

**Güncelleştirilmiş konular**

|Ad|Ayrıntılar|
|----|-------|
|[Microsoft Intune'la bilgisayarlar ve mobil cihazları yönetmek için ilkeleri kullanma](https://technet.microsoft.com/library/dn743712.aspx)|İlkeleri anlamanıza ve oluşturmanıza yardımcı olmak için en son bilgileri içerecek şekilde güncelleştirilmiştir.|

## Ağustos 2015
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
* Intune’a kaydolma ve şirket erişimi için**hüküm ve koşullar** artık [ilkeler kullanılarak yönetilir](https://technet.microsoft.com/library/mt405893.aspx). Belirli kullanıcı grupları için, kendilerine yönelik gereksinimleri karşılayacak farklı hüküm ve koşullar hedefleyebilirsiniz. Örneğin, coğrafi olarak tanımlanan kullanıcı gruplarına hüküm ve koşulları farklı dillerde dağıtabilirsiniz. Ayrıca [hüküm ve koşullarınızı düzenleyebilir](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) ve sürüm numaralarının artırılıp artırılmayacağını belirterek kullanıcıların şirket portalını kullanabilmek için yeni hüküm ve koşulları kabul etmelerini gerektirebilirsiniz.
* **Çeşitli Intune ilkeleri yeniden adlandırılarak** ürün içinde daha tutarlı ve bulunması daha kolay hale getirilmiştir. Kullanılabilir tüm Intune ilkelerinin listesi için bkz. [Microsoft Intune ile bilgisayarları ve mobil cihazları yönetmek için ilkeleri kullanma](https://technet.microsoft.com/library/dn743712.aspx).
* **PKCS #12 (.PFX) Sertifika Profilleri**, Android 4.0 veya sonraki sürümleri ve Windows 10 (masaüstü ve mobil) ve sonraki sürümleri için kullanılabilir. .PFX kullanmak için NDES sunucusu gerekli değildir. .PFX sertifika profilleri oluşturma hakkında bilgi için bkz. [Microsoft Intune ile sertifika profillerini kullanarak şirket kaynaklarına erişimi etkinleştirme](http://technet.microsoft.com/library/dn818904.aspx)
* [Kullanıcıların Microsoft Intune'la VPN profilleri kullanarak işlerine bağlanmasına yardımcı olun](https://technet.microsoft.com/library/dn818905.aspx) bölümünde açıklandığı gibi **Windows 10 Masaüstü ve Mobile için Kuruluş Sınırları ayarları** ayrıntılı VPN ayarlarını destekler
* **Android için OneDrive uygulaması artık birden çok kimliği desteklemektedir**. Mobil uygulama yönetimi ilkeleri ile ilgili bu ve diğer güncelleştirmeler [yönetilebilen Microsoft uygulamalarının listesi](https://technet.microsoft.com/library/dn708489.aspx)içinde açıklanmıştır.
* **iOS Etkinleştirme Kilidini atlama**. Şirkete ait iOS cihazları Etkinleştirme Kilidi ile korunuyorsa, cihazı silmek veya yeniden etkinleştirmek için önce kullanıcının Apple Kimliğini ve parolasını girmelisiniz. Bu, kullanıcılar şirketten ayrıldığında ve şirkete ait bir cihazı Etkinleştirme Kilidi’ni kapatmadan iade ettiğinde bir sorun oluşturabilir. Bu sorunun çözümüne yardımcı olmak için [Intune Etkinleştirme Kilidi’ni Atlama](https://technet.microsoft.com/library/mt414176.aspx) özelliğini kullanabilirsiniz

### Bilgisayarlar için koşullu erişim
Artık bilgisayarlar için koşullu erişim ilkeleri yapılandırabilirsiniz. Bu, Office masaüstü uygulamalarının Exchange Online ve SharePoint Online hizmetlerine erişmesini sağlar.
Bilgisayarlar için koşullu erişim ilkesini etkinleştirmek için bilgisayarın etki alanına katılmış ya da uyumlu olması gerekir.
* Bilgisayarlarda koşullu erişimi etkinleştirme gereksinimlerinin tam listesi için [Microsoft Intune ile e-posta ve SharePoint erişimini yönetme](http://technet.microsoft.com/library/dn818907).aspx) içindeki **Başlangıç** bölümüne bakın.
* E-posta erişimine yönelik koşullu erişimi etkinleştirmek üzere ayarlayabileceğiniz seçenekler için bkz. [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx).
* SharePoint Online’da koşullu erişimi etkinleştirmek üzere belirleyebileceğiniz ayarlar için bkz. [Microsoft Intune ile SharePoint Online erişimini yönetme](https://technet.microsoft.com/library/dn705844.aspx).

### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

**Android**

Cihazlarını henüz yönetilmek üzere kaydetmemiş kullanıcılar, artık oturum açtıklarında cihaz kaydı yönergelerini görürler.

### Intune belgelerindeki yenilikler -- Ağustos 2015
**Yeni konular**

|Başlık|Ayrıntılar|
|-----|-------|
|[Microsoft Intune için Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma](https://technet.microsoft.com/library/mt414176.aspx)|Şirketten ayrılan bir kullanıcı kilitli bir cihazı iade ettiğinde, Intune kullanarak iOS etkinleştirme kilidini nasıl atlayabileceğiniz hakkında bilgi edinin.|

**Güncelleştirilmiş konular**

|Başlık|Ayrıntılar|
|-----|-------|
|[Microsoft Intune mobil uygulama yönetimi ilkeleri ile kullanabileceğiniz Microsoft uygulamaları](https://technet.microsoft.com/library/dn708489.aspx)|Mobil uygulama yönetimi ilkeleriyle yönetebileceğiniz uygulamalar ile ilgili en son bilgilerle güncelleştirildi.
|[Microsoft Intune'la bilgisayarlar ve mobil cihazları yönetmek için ilkeleri kullanma](http://technet.microsoft.com/library/dn743712.aspx)|Intune’a eklenen en yeni ilkelerle güncelleştirildi.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jun16_HO4-->


