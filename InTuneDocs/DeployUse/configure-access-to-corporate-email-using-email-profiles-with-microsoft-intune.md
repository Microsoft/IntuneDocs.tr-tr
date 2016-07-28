---
title: "E-posta profilleriyle şirket e-postasına erişim | Microsoft Intune"
description: "E-posta profili ayarları, mobil cihazlarda belirli e-posta istemcilerinin e-posta erişim ayarlarını yapılandırmak için kullanılır."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/021/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c7a3ca7b0390a001624871342c9aa04802be27ff


---

# Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma
Birçok mobil platformda, işletim sisteminin parçası olarak gönderilen bir *yerel* e-posta istemcisi bulunur.  Bu istemcilerden bazıları, bu konu başlığı altında açıklandığı gibi e-posta profilleri kullanılarak yapılandırılabilir.

Ek veri kaybı önleme (DLP) özelliğine gerek duyuyorsanız, yerel e-posta istemcileri de dahil olmak üzere tüm e-posta istemcileri için kullanıcının posta kutusuna erişimi denetleyen [Koşullu erişim](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)’i seçin.

E-posta profili ayarları, mobil cihazlarda belirli e-posta istemcilerinin e-posta erişim ayarlarını yapılandırmak için kullanılır. Çoğu mobil platformda, işletim sisteminin parçası olarak gönderilen bir *yerel* e-posta istemcisi bulunur.  Desteklenen platformlarda, kullanıcıların herhangi bir kurulum yapmadan kişisel cihazlarda şirket e-postasına erişebilmelerini sağlamak için, yerel e-posta istemcileri Microsoft Intune tarafından yapılandırılabilir.  

BT yöneticileri veya kullanıcılar, Android ve iOS için Microsoft Outlook gibi alternatif e-posta istemcileri yüklemeyi de seçebilirler.  Bu e-posta istemcileri e-posta profillerini destekleyemeyebilir ve Microsoft Intune e-posta profilleri kullanılarak yapılandırılamaz.  

Aşağıdaki cihaz türlerinde yerel e-posta istemcisini yapılandırmak için e-posta profillerini kullanabilirsiniz:
-   Windows Phone 8 ve üzeri
-   Windows 10 masaüstü, Windows 10 Mobile ve üzeri
-   iOS 7.1 ve üzeri
-   Samsung KNOX Standard (4.0 ve üzeri)


Cihazda bir e-posta hesabı yapılandırmaya ek olarak, ne kadar e-postanın eşitleneceği ve cihaz türüne bağlı olarak eşitlenecek içerik türleri gibi eşitleme ayarlarını da yapılandırabilirsiniz.

## E-posta profillerinin güvenliğini sağlama
E-posta profillerinin güvenliği sağlamak için iki yöntemden biri kullanabilirsiniz:

### Sertifikalar
E-posta profilini oluştururken, daha önce Intune’da oluşturduğunuz SCEP sertifika profilini seçersiniz. Bu, kimlik sertifikası olarak bilinir ve kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için güvenilir bir sertifika profiline (veya kök sertifikaya) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, e-posta bağlantısı kimliğini doğrulayan bilgisayara (genellikle yerel posta sunucusu) dağıtılır.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).

### Kullanıcı adı ve parola
Kullanıcı, kullanıcı adı ve parolasını sağlayarak yerel posta sunucusunda kimliğini doğrular.

E-posta profilinde parola yer almadığı için e-postaya bağlanırken kullanıcı tarafından belirtilmesi gerekir.

### E-posta profili oluştur

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**'ye tıklayın.

2.  Aşağıdaki ilke türlerinden birini yapılandırın:

    -   **Samsung KNOX Standard (4.0 ve üzeri) için E-posta Profili**

    -   **E-posta Profili (iOS 7.1 ve üzeri)**

    -   **E-posta Profili (Windows Phone 8 ve üzeri)**

    -   **E-posta Profili (Windows 10 Masaüstü ile Mobile ve üzeri)**

    Yalnızca özel bir e-posta profili ilkesi oluşturup dağıtabilirsiniz. Önerilen ayarlar kullanılamaz.

3.  E-posta profili ayarlarını yapılandırmanıza yardımcı olması için aşağıdaki tabloyu kullanın:
    |Ayar adı|Daha fazla bilgi|
    |----------------|-----------------------------------------------------------------------------|
    |**Ad**|E-posta profili için benzersiz bir ad.|
    |**Açıklama**|Bu profili tanımlamanıza yardımcı olacak bir açıklama.|
    |**Ana bilgisayar**|Yerel e-posta hizmetinizi barındıran şirket sunucunuzun konak adı.|
    |**Hesap adı**|E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.|
    |**Kullanıcı adı**|E-posta hesabı için kullanıcı adının nasıl elde edileceği. Şirket İçi Exchange sunucusu için **Kullanıcı Adı**’nı veya Office 365 için **Kullanıcı Asıl Adı**’nı seçin.|
    |**E-posta adresi**|E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.|
    |**Kimlik doğrulama yöntemi** (Samsung KNOX ve iOS)|E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.|
    |**İstemci kimlik doğrulaması (Kimlik Sertifikası) için bir istemci sertifikası seçin** (Samsung KNOX ve iOS)|Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP sertifikasını seçin. Intune’da sertifika profillerini kullanma hakkında daha fazla bilgi için bkz. [Sertifika profillerini kullanarak kaynak erişiminin güvenliğini sağlama](secure-resource-access-with-certificate-profiles.md).<br /><br />Bu seçenek yalnızca kimlik doğrulama yöntemi **Sertifikalar** olduğunda görüntülenir.|
    |**S/MIME kullan** (Samsung KNOX ve iOS)|S/MIME şifrelemesi kullanarak giden e-posta gönderin.|
    |**İmzalama sertifikası** (Samsung KNOX ve iOS)|Giden e-postayı imzalamak için kullanılan imzalama sertifikasını seçin.<br /><br />Bu seçenek yalnızca **S/MIME kullan**’ı seçtiğinizde görüntülenir.|
    |**E-posta eşitlemek için gün sayısı**|Eşitlemek istediğiniz e-posta sayısı; tüm kullanılabilir e-postaları eşitlemek için **Sınırsız**’ı seçin.|
    |**Eşitleme zamanlaması** (Samsung KNOX, Windows Phone 8 ve üstü, Windows 10)|Cihazların Exchange Server'dan verileri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri ulaşır ulaşmaz eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılması gereken **El ile** seçeneğini belirleyebilirsiniz.|
    |**SSL Kullan**|E-posta gönderirken, e-posta alırken ve Exchange Server ile iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.<br /><br />Samsung KNOX 4.0 veya üzeri bir sürümü çalıştıran cihazlarda Exchange Server’ın SSL sertifikasını dışarı aktarmanız ve Intune’da bunu Android Güvenilir Sertifika Profili olarak dağıtmanız gerekir. Intune, Exchange Server'a başka yollarla yüklenirse bu sertifikaya erişimi desteklemez.|
    |**Eşitlenecek içerik türü**|Cihazlara eşitlemek için istediğiniz içerik türlerini seçin.| 
    |**Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver** (yalnızca iOS)|Kullanıcının, bu profili, e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamalarının, yerel e-posta uygulamasında e-posta açmasına izin verin (örneğin e-postaya dosya eklemek için).|

    > [!IMPORTANT]
    > Bir e-posta profilini dağıttıktan sonra **konak** veya **E-posta adresi** değerlerini değiştirmek isterseniz mevcut e-posta profilini silmeniz ve gerekli değerlerle yeni bir tane oluşturmanız gerekir.

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.

## İlkeyi dağıtma

1.   **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.   **Dağıtımı Yönet** iletişim kutusunda:

    -   **İlkeyi dağıtmak için** - İlkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

    -   **Dağıtmadan iletişim kutusunu kapatmak için** - **İptal**'e tıklayın.

 **İlke** çalışma alanının **Genel Bakış** sayfasında, bir durum özeti ve uyarılar ilkeyle ilgili işlem yapmanız gereken durumları tanımlar. Ayrıca, Pano çalışma alanında bir durum özeti görüntülenir.

> [!NOTE]
> Bir cihazdan e-posta profilini kaldırmak isterseniz, dağıtımı düzenleyin ve cihazın üye olduğu tüm grupları kaldırın.





<!--HONumber=Jul16_HO3-->


