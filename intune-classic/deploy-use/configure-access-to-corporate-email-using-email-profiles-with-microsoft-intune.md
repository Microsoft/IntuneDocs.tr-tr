---
title: "E-posta profilleriyle şirket e-postasına erişim | Microsoft Docs"
description: "E-posta profili ayarları, mobil cihazlarda belirli e-posta istemcilerinin e-posta erişim ayarlarını yapılandırmak için kullanılır."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 21eee53a4e3674dc28b01311a61dda0d71f9f7fa
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Birçok mobil platformda, işletim sisteminin parçası olarak gönderilen bir yerel e-posta istemcisi bulunur. Bu istemcilerden bazıları, bu konu başlığı altında açıklandığı gibi e-posta profilleri kullanılarak ayarlanabilir.

E-posta profili ayarları, mobil cihazlarda belirli e-posta istemcilerinin e-posta erişim ayarlarını belirlemek için kullanılır. Desteklenen platformlarda, kullanıcıların başka bir kurulum yapmadan kişisel cihazlarda şirket e-postasına erişebilmelerini sağlamak için, yerel e-posta istemcileri Microsoft Intune tarafından ayarlanabilir.

Veri kaybını önlemek için ek önlemler almaya gerek duyuyorsanız, yerel e-posta istemcileri de dahil olmak üzere tüm e-posta istemcileri için kullanıcının posta kutusuna erişimi denetleyen [Koşullu erişim](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)’i kullanın.

BT yöneticileri veya kullanıcılar, Android ve iOS için Microsoft Outlook gibi alternatif e-posta istemcileri yüklemeyi de seçebilirler. Bu e-posta istemcileri e-posta profillerini destekleyemeyebilir ve Intune e-posta profilleri kullanılarak ayarlanamaz.  

Aşağıdaki cihaz türlerinde yerel e-posta istemcisini yapılandırmak için e-posta profillerini kullanabilirsiniz:
-    Windows Phone 8.1 ve üzeri
-    Windows 10 (masaüstü için), Windows 10 Mobile ve üzeri
-    iOS 8.0 ve üzeri
-    Samsung KNOX Standard (4.0 ve üzeri)
-    Android for Work (üçüncü taraf e-posta uygulamaları, yerel e-posta uygulaması yalnızca kişisel profildir)

Cihazda bir e-posta hesabı ayarlamaya ek olarak, ne kadar e-postanın eşitleneceğini ve cihaz türüne bağlı olarak eşitlenecek içerik türlerini de ayarlayabilirsiniz.

Intune tarafından profil ayarlanmadan önce kullanıcı bir e-posta profili yüklediyse, Intune e-posta profili dağıtımının sonucu cihaz platformuna bağlıdır:

**Android**<br>Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Kullanıcı tarafından oluşturulmuş yinelenen e-posta profili, Intune yöneticisinin oluşturduğu profilin dağıtımını engeller. iOS kullanıcıları normalde e-posta profili oluşturduğundan ve ardından kaydolduğundan, bu yaygın görülen bir sorundur. Şirket portalı, el ile yapılandırılan e-posta profilinden dolayı uyumlu olmadığını kullanıcıya bildirir ve kullanıcıdan söz konusu profili kaldırmasını ister. Intune profilinin ayarlanabilmesi için, kullanıcının e-posta profilini kaldırması gerekir. Bu sorunun önüne geçmek için, kullanıcılarınızdan bir e-posta profilini yüklemeden önce kaydolmalarını ve Intune’un profili ayarlamasına izin vermelerini isteyin.

**Windows**<br>Konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğu algılanır. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

**Samsung KNOX**<br>E-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili algılanır ve Intune profili bunun üzerine yazılır. Kullanıcı bu hesabı ayarlarsa, Intune profili tarafından hesabın üzerine yeniden yazılır. Bu durumun kullanıcıda kafa karışıklığına neden olabileceğini unutmayın.

Samsung KNOX’un profili algılamak için konak adını kullanmaması nedeniyle, farklı konaklarda aynı e-posta adresinde kullanmak üzere birden çok e-posta profili oluşturursanız bunlar birbirinin üzerine yazılacağından, bunu yapmamanızı öneririz.

**Android for Work**<br>Intune; Gmail ve Nine Work e-posta uygulamaları için birer tane olmak üzere iki Android for Work profili sağlar. Bu uygulamalar Google Play Store’da mevcuttur, cihaz iş profiline yüklenir ve bu yüzden yinelenen profiller oluşturmazlar. Her iki uygulama da Exchange bağlantılarını destekler. E-posta bağlantısını etkinleştirmek için bu e-posta uygulamalarından birini kullanıcılarınızın cihazlarına dağıtın ve ardından uygun e-posta profilini oluşturup dağıtın. Nine Work gibi e-posta uygulamaları ücretsiz olmayabilir. Uygulamanın lisanslama ayrıntılarını gözden geçirin veya sorunuz varsa uygulama şirketine başvurun.

## <a name="secure-email-profiles"></a>E-posta profillerinin güvenliğini sağlama
E-posta profillerinin güvenliğini sertifika veya parola kullanarak sağlayabilirsiniz.

### <a name="certificates"></a>Sertifikalar
E-posta profilini oluştururken, daha önce Intune’da oluşturduğunuz SCEP sertifika profilini seçersiniz. Bu, kimlik sertifikası olarak bilinir ve kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için güvenilir bir sertifika profiline (veya kök sertifikaya) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, e-posta bağlantısı kimliğini doğrulayan bilgisayara (genellikle yerel posta sunucusu) dağıtılır.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).

### <a name="user-name-and-password"></a>Kullanıcı adı ve parola
Kullanıcı, kullanıcı adını ve parolasını sağlayarak yerel posta sunucusunda kimliğini doğrular.

E-posta profilinde parola bulunmadığından, e-postaya bağlanırken kullanıcı tarafından belirtilmesi gerekir.

### <a name="create-an-email-profile"></a>E-posta profili oluştur

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**’yi seçin.

2.  Aşağıdaki ilke türlerinden birini ayarlayın:

    -   **Samsung KNOX Standard (4.0 ve üzeri) için E-posta Profili**

    -   **E-posta Profili (iOS 8.0 ve üzeri)**

    -   **E-posta Profili (Windows Phone 8.1 ve üzeri)**

    -   **E-posta Profili (Windows 10 Masaüstü ile Mobile ve üzeri)**

    -   **E-posta Profili (Android for Work - Gmail)**

    -    **E-posta Profili (Android for Work - Nine Work)**

    Yalnızca özel bir e-posta profili ilkesi oluşturup dağıtabilirsiniz. Önerilen ayarlar kullanılamaz.

3.  E-posta profili ayarlarını belirlemenize yardımcı olması için aşağıdaki tabloyu kullanın:

|Ayar adı | Daha fazla bilgi|
| ----------- | --------------- |
    |**Ad**|E-posta profili için benzersiz bir ad.|
    |**Açıklama**|Bu profili tanımlamanıza yardımcı olacak bir açıklama.|
    |**Konak**|Yerel e-posta hizmetinizi barındıran şirket sunucunuzun konak adı.|
    |**Hesap adı**|E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.|
    |**Kullanıcı adı**|Bu öznitelik, bu e-posta profili için kullanıcı adını oluşturmak üzere kullanılacak Active Directory (AD) veya Azure AD özniteliğidir. Birincil SMTP Adresi için *user1@contoso.com* gibi bir değer seçin veya Kullanıcı Birincil Adı için *user1* ya da *user1@contoso.com* yazın.|
    |**E-posta adresi**|E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.|
    |**Kimlik doğrulama yöntemi** (Android for Work, Samsung KNOX ve iOS)|E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.|
    |**İstemci kimlik doğrulaması (Kimlik Sertifikası) için bir istemci sertifikası seçin** (Android for Work, Samsung KNOX ve iOS)|Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP sertifikasını seçin. Intune’da sertifika profillerini kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md). Bu seçenek yalnızca kimlik doğrulama yöntemi **Sertifikalar** olduğunda görüntülenir.|
    |**S/MIME kullan** (Samsung KNOX ve iOS)|S/MIME imzalama kullanarak giden e-posta gönderin.|
    |**İmzalama sertifikası** (Samsung KNOX ve iOS)|Giden e-postayı imzalamak için kullanılan imzalama sertifikasını seçin. Bu seçenek yalnızca **S/MIME kullan**’ı seçtiğinizde görüntülenir.|
    |**E-posta eşitlemek için gün sayısı**|Eşitlemek istediğiniz e-posta sayısı; tüm kullanılabilir e-postaları eşitlemek için **Sınırsız**’ı seçin.|
    |**Eşitleme zamanlaması** (Android for Work, Samsung KNOX, Windows Phone 8 ve üzeri, Windows 10)|Cihazların Exchange sunucusundan verileri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri ulaşır ulaşmaz eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.|
    |**SSL Kullan**|E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın. Samsung KNOX 4.0 veya üzeri bir sürümü çalıştıran cihazlarda Exchange Server SSL sertifikasını dışarı aktarmanız ve Intune’da bunu Android Güvenilir Sertifika Profili olarak dağıtmanız gerekir. Intune, Exchange sunucusuna başka yollarla yüklenirse bu sertifikaya erişimi desteklemez.|
    |**Eşitlenecek içerik türü** (Android for Work Gmail harici tüm platformlar)|Cihazlara eşitlemek için istediğiniz içerik türlerini seçin.|
    |**Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver** (yalnızca iOS)|Kullanıcının, bu profili, e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamalarının, yerel e-posta uygulamasında e-postayı açmasına izin verin (örneğin e-postaya dosya eklemek için).|

> [!IMPORTANT]
>
> Bir e-posta profilini dağıttıktan sonra **konak** veya **E-posta adresi** değerlerini değiştirmek isterseniz mevcut e-posta profilini silmeniz ve gerekli değerlerle yeni bir tane oluşturmanız gerekir.

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.

## <a name="deploy-the-policy"></a>İlkeyi dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.

2.  **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'ı seçin.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**’i seçin.

**İlke** çalışma alanının **Genel Bakış** sayfasında, bir durum özeti ve uyarılar ilkeyle ilgili işlem yapmanız gereken durumları tanımlar. Ayrıca, Pano çalışma alanında bir durum özeti görüntülenir.

> [!NOTE]
> - Android for Work için uygun e-posta profilinin yanı sıra Gmail veya Nine Works uygulamalarını da dağıttığınızdan emin olun.
> - Bir cihazdan e-posta profilini kaldırmak isterseniz, dağıtımı düzenleyin ve cihazın üye olduğu tüm grupları kaldırın. Cihazda yalnızca bir e-posta profili olduğunda, bu e-posta profilini bu yöntemle kaldıramayacağınızı unutmayın.
> - Önceden dağıttığınız bir e-posta profilinde değişiklik yaparsanız son kullanıcılardan e-posta ayarları yeniden yapılandırma işlemini onaylanmasını isteyen bir ileti görüntülenebilir.

