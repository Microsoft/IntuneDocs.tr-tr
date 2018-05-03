---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d6a06326fbb60d910aef0411fc666b82a5f22078
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Microsoft Intune için erken sürüm - Nisan 2018

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için [Karma Yenilikler](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) sayfasını gözden geçirin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1804 start -->




### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler <!-- 1403702 -->
Windows 10 cihazlar için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabileceksiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir olacak. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme <!-- 1553555 -->
Intune, AutoPilot cihazlar hazırlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler; son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek.

### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza imkan veren yeni kurallar kullanılabilir olacak. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz kaldırma kuralları**’nı seçin.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz kaydı** > **Windows kaydı** > **Windows AutoPilot profilleri** > **Yeni Oluştur** > **Kayıt ayarları**’na gidin. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->

Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, birden çok Exchange Connector’u destekleyeceği için Intune koşullu erişimini birden çok şirket içi Exchange kuruluşunda ayarlayabilirsiniz.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>iOS için yeni Cisco AnyConnect istemcisi desteği geliyor <!-- 1333708 -->

iOS için Cisco AnyConnect'e yönelik oluşturulan yeni VPN profilleri Cisco AnyConnect 4.0.7x ve üstüyle çalışacaktır. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenecek ve bugün olduğu gibi Cisco AnyConnect 4.0.5x ile çalışmaya devam edecektir.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir; Android, Android for Work ve macOS için yine tek Cisco AnyConnect seçeneği olacaktır.

#### <a name="more-information"></a>Daha fazla bilgi

Yeni uygulamayı desteklemek için yeni bir iOS Cisco AnyConnect VPN profili oluşturmalısınız çünkü yeni Cisco AnyConnect uygulaması ve Cisco Eski AnyConnect uygulaması ayrı uygulamalardır. Ortamınızda AnyConnect istemcisini yönetiyorsanız, yeni Cisco AnyConnect uygulamasını da dağıtmanız gerekir. Ayrıca yükseltmeyi tamamlamak için, Cisco Eski AnyConnect VPN profilini silmeli ve Cisco Eski AnyConnect uygulamasını kaldırmalısınız.

İlk sürümde yeni AnyConnect istemcisi için ağ erişim denetimi (NAC) tümleştirmesi çalışmaz. Gelecek Intune sürümlerinden birinde NAC tümleştirmesi sağlamak için Cisco'yla çalışmaları sürdürüyoruz.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Gerekli iş kolu (LOB) uygulamalarını Windows 10 Masaüstü cihazlarında Tüm Kullanıcılara dağıtabilme <!-- 1627835 RS4 -->
Müşteriler gerekli iş kolu Windows 10 uygulamalarını cihaz bağlamlarına yüklemek üzere dağıtabilecek. Böylelikle bu uygulamalar cihazdaki tüm kullanıcılara sağlanabilir. Bu yalnızca Windows 10 Masaüstü cihazları için geçerlidir.

### <a name="company-portal-enrollment-improved----1874230--"></a>Şirket Portalı kaydı geliştirildi <!-- 1874230-->
Windows 10 derleme 1703'te ve üstünde Şirket Portalı'nı kullanarak cihaz kaydı yapan kullanıcılar, uygulamadan çıkmadan kaydın ilk adımını tamamlayabilecekler.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştiriyoruz. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulamasını güncelleştirerek **Yardım ve Geri Bildirim** menü öğesini **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayıracağız. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.


<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.




## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.


### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


