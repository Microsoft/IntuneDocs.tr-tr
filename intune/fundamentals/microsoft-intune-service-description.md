---
title: Microsoft Intune Hizmeti Açıklaması
description: Microsoft Intune; Windows, iOS, Mac OS X, Android ve Windows Mobile cihazlarını yönetmenize yardımcı olan bulut tabanlı bir hizmettir.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 05/30/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7744fe217f39436e91f90fdf567f469c01986da4
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885648"
---
# <a name="microsoft-intune-service-description"></a>Microsoft Intune hizmet açıklaması

Intune, çalışanlarınızın üretken olmasını sağlarken kurumsal verilerinizin korunmasına yardımcı olan bulut tabanlı bir kurumsal mobilite yönetim (EMM) hizmetidir. Intune ile şunları yapabilirsiniz:
* Çalışanlarınızın şirket verilerine erişmek için kullandığı mobil cihazları yönetebilirsiniz.
* Çalışanlarınızın kullandığı istemci uygulamaları yönetebilirsiniz.
* Çalışanlarınızın erişim ve paylaşım yöntemlerinin denetlenmesine yardımcı olarak şirket bilgilerinizi koruyabilirsiniz.
* Cihazların ve uygulamaların şirket güvenlik gereksinimlerine uygun olduğundan emin olabilirsiniz.

Intune, kimlik ve erişim denetimi için Azure Active Directory (Azure AD), veri koruma için ise Azure Information Protection ile yakın bir tümleştirmede çalışır. Ayrıca, yönetim olanaklarınızı genişletmek için Configuration Manager ile tümleştirebilirsiniz.

Intune ile cihazları ve uygulamaları nasıl yöneteceğiniz ve kurumsal verileri nasıl koruyacağınız hakkında bilgi için bkz. [Intune belgeleri](../index.yml).

## <a name="30-day-free-trial"></a>30 günlük ücretsiz deneme sürümü
Intune'u 100 kullanıcı lisansı içeren 30 günlük ücretsiz bir denemeyle kullanmaya başlayabilirsiniz. Ücretsiz denemeyi başlatmak için [Intune Kayıt sayfasına gidin](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Kuruluşunuzda bir Kurumsal Anlaşma veya eşdeğer toplu lisans sözleşmesi varsa, ücretsiz deneme sürümünüzü ayarlamak için Microsoft temsilcinize başvurun.

> [!NOTE]
> Kuruluşunuzda bir Microsoft Online Services iş ya da okul hesabı varsa ve deneme süresi sona erdikten sonra üretimde bu Intune aboneliğiyle devam edecekseniz, ilgili sayfada **Oturum aç**'ı seçin ve kuruluşunuzun Genel Yönetici hesabını kullanarak kimlik doğrulaması yapın. Bu işlem Intune denemenizin mevcut iş veya okul hesabınızla ilişkilendirilmesini sağlar.

<!--- For a list of settings that you can set up on mobile devices, see:

- [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)

--->
## <a name="intune-onboarding-benefit"></a>Intune Onboarding avantajı
Microsoft, uygun planlarda uygun hizmetler için Intune Onboarding avantajını sunar. Onboarding avantajı, ortamınızı kullanıma hazır hale getirmek için Microsoft uzmanlarıyla uzaktan çalışmanıza olanak sağlar. Ekleme avantajı hakkında daha fazla bilgi için bkz. [Microsoft Intune Ekleme Avantajı Açıklaması](https://go.microsoft.com/fwlink/?LinkId=619281).


## <a name="learn-how-intune-service-updates-affect-you"></a>Intune hizmet güncelleştirmelerinin size nasıl etkileyeceğini öğrenin

Mobil cihaz yönetimi ekosistemi, işletim sistemi güncelleştirmeleri ve mobil uygulama sürümleriyle sıkça değiştiğinden, Microsoft Intune'u düzenli olarak güncelleştirmektedir. Intune hizmetindeki değişiklikler hakkında bilgi alabileceğiniz üç yol vardır:

- [Microsoft Intune'daki yenilikler](whats-new.md). Bu konu, aylık hizmet güncelleştirmesiyle ve örneğin Şirket Portalı uygulaması gibi uygulamalar yayımlandığında haftalık olarak güncelleştirilir.

- Ayrıca, önemli hizmet güncelleştirmeleri [Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com/) ileti merkezinde duyurulmuştur. Yardımcı [Office 365 Yönetici mobil uygulamasını](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) yüklerseniz, mobil cihazınızda bildirimleri alabilirsiniz. [Office 365 İleti Merkezi](https://support.office.com/client/results?Shownav=true&ns=O365ENTADMIN&version=15&ver=15&HelpID=O365E_MCManageUpdates) ile çalışma hakkında bilgi edinin.

  Birkaç faydalı ipucu:

  - Office 365 İleti Merkezi’ndeki iletiler hedeflenir. Yani, şirketinizin EDU için Intune teklifi yoksa size EDU için Intune hakkında ileti göndermeyiz.

  - İletilerin süresi dolar. Örneğin, hizmetinizin Yenilikler sayfasına bağlantısı ile güncelleştirilen bildirim muhtemelen sonraki hizmet güncelleştirme bildiriminden önce sona erer. Aksi takdirde, artık geçerli olmayan birçok geçmiş gönderiye ilişkin günlükleriniz olurdu.

  - Office 365 yönetici mobil uygulaması, tüm iletiler arasında arama yapmanızı ve kuruluşunuzdakilerle paylaşmak istiyorsanız bildirimi iletmenizi sağlar.

  - Düzenleme ileti merkezi tercihleri altında, bir Intune aboneliğine gönderilen iletilere bakabilmeniz için bir süre sonra **Intune** için bir geçiş düğmemiz olacaktır. Office 365 için Mobil Cihaz Yönetimi görürseniz, bu Intune değil, farklı bir hizmettir.

- Ayrıca EMS iletisi ve Intune desteği en başarılı uygulamalarını paylaşmak için de iki blog kullanırız:

  - [Enterprise Mobility + Security blogu](https://blogs.technet.microsoft.com/enterprisemobility/)

  - [Intune destek blogu](https://blogs.technet.microsoft.com/intunesupport/)

> [!Note]
> Intune hizmet durumunu [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)izleyebilirsiniz. Sol bölmede **Hizmet Durumu**’nu seçin. Hizmet durumunu görüntülemek için [Office 365 Yönetici mobil uygulaması](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) da kullanabilirsiniz.

## <a name="types-of-notices-microsoft-provides-about-the-intune-service"></a>Microsoft’un Intune hizmeti hakkında sağladığı bildirim türleri

Hizmet değişikliklerini planlamanıza yardımcı olmak için değişikliğin etkisine bağlı olarak, hizmet değişikliğinden en az 7-90 gün önce size haber veririz. Bu değişiklikler aşağıdaki değişiklik türlerinden herhangi birini içerebilir:

- Yardım masası personeliniz veya son kullanıcılarınız ile paylaşmak isteyebileceğiniz son kullanıcı deneyiminde yapılan değişiklikler. Genellikle bu değişiklikleri 7-30 gün önceden duyururuz ve bunları [Intune Uygulaması Kullanıcı Arabirimindeki Yenilikler](whats-new-app-ui.md) bölümünde belgeleriz. Bir yazım hatası düzeltmesini genellikle belgelerde belirtmeyiz. Ancak, son kullanıcı kayıt deneyiminde bir değişiklik Kullanıcı Arabiriminde son derece önemlidir ve bu durumda nelerin değiştiğini öğrenmeniz ve değişiklikler devreye girmeden önce son kullanıcı rehberinizi değerlendirmeniz ve güncelleştirmeye vaktiniz olmasını sağlamak için Office 365 İleti Merkezi’ndeki müşterilere ileti göndeririz ve Intune Uygulama Arabirimindeki Yenilikler bölümüne bir bağlantı sağlarız.

- İşlem yapmanızı gerektiren değişikliklere **Değişiklik Planı** denir ve bunlar genellikle yaklaşık 30 gün önceden bildirilir. Office 365 İleti Merkezi’nde Kategori özellikle Değişiklik Planı diyorsa ve değişikliğin devreye gireceği gün için kesin tarih belliyse ayrıca size görsel bir sıra ve açıklama işareti sağlayan bir **Şu Tarihe Kadar İşlem Yapın** tarihi veririz.

- Kullanım dışı bırakılanların çoğunda, kullanım dışı bırakma işleminden 90 gün önce bildirim sağlamayı tercih ederiz. Örneğin artık IE’nin belirli bir sürümü için destek sağlamayacaksak hedefimiz 90 gün öncesinden bildirim sağlamaktır. Ancak, başka bir şirket kullanım dışı bıraktığı bir ürününü açıkladığında, kullanım dışı bırakmalar karmaşık hale gelir. Örneğin, bir tarayıcı şirketi en son sürümünde Silverlight için destek sağlamayacağına ilişkin bir bildirimde bulunduğunda, müşterilerimize bu tarayıcıya olan desteğimizi sonlandıracağımızı açıklarız, ancak bu bildirim 90 gün öncesinden bildirim süremize uymayabilir.

- Intune hizmetinin devre dışı bırakılması durumunda, 12 ay önce bu durum size bildirilecektir.

Son olarak, hizmetinizi normal durumuna döndürmek için herhangi bir olay sonrası eylem gerektiğinde veya müşteri geri bildirimi doğrultusunda olası kesintiye sebep olabileceğini düşündüğümüz büyük bir değişiklik olması gibi nadir rastlanan durumlarda, [Office 365 iletişim tercihleri](https://support.office.com/article/Change-your-contact-preferences-for-communications-from-Microsoft-6f70de1b-a64d-4498-bfbd-be8c83a9c0fc) ayarlarınıza bağlı olarak hizmet yöneticilerine ve varsa geçerli e-posta adresinize (tercihen iş) e-posta göndeririz.  


<!--- ## Choose the management solution that’s right for you
You can set up Intune in several ways to manage and help protect your company's mobile devices and computers (referred to as **devices** in this article).

- **Intune stand-alone configuration.** Use the web-based admin console in Intune to manage devices in your organization. Intune can be used without any on-premises IT infrastructure. If you use Intune with Active Directory Domain Services, you can use domain user accounts that you manage with Domain Services with Intune.

--->

## <a name="language-support"></a>Dil desteği
Intune, şu dilleri destekleyen Azure portalında çalışır: Çince (Basitleştirilmiş), Çince (Geleneksel), Çekçe, Felemenkçe, İngilizce, Almanca, Macarca, İtalyanca, Japonca, Portekizce (Brezilya), Portekizce (Portekiz), Rusça, İspanyolca, İngilizce, Fransızca, Korece, Lehçe, İsveççe, Türkçe.

Intune Yönetici Konsolu ve kullanıcıya yönelik mobil deneyimler, Azure portalının desteklediği tüm dillere ek olarak Danca, Yunanca, Fince, Norveççe ve Rumence destekler.

<!--- ## Learn more about Intune
Use these resources to learn more about Intune:

- The [Microsoft Intune Trust Center](https://www.microsoft.com/server-cloud/products/intune-trust-center/) provides information about the security, privacy, and compliance practices of Intune, and it describes some of Intune's certifications.

- [Enrolled device management capabilities of Microsoft Intune](introduction-intune.md)--->
