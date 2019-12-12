---
title: Kılavuzlu senaryo-güvenli Microsoft Office mobil uygulamalar
titleSuffix: Microsoft Intune
description: Microsoft 365 cihaz yönetim portalından güvenli Microsoft Office mobil uygulamalar dağıtmaya yönelik Kılavuzlu senaryo hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd02e2b7f9582308109d1e6986d7e6a8014e5af7
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585894"
---
# <a name="guided-scenario---secure-microsoft-office-mobile-apps"></a>Kılavuzlu senaryo-güvenli Microsoft Office mobil uygulamalar 

Cihaz yönetimi portalında Bu Kılavuzlu senaryoyu izleyerek iOS ve Android cihazlarda temel Intune uygulama korumasını etkinleştirebilirsiniz.

Etkinleştirdiğiniz uygulama koruması aşağıdaki eylemleri uygular: 
- İş dosyalarını şifreleyin.
- Çalışma dosyalarına erişmek için PIN gerektir.
- PIN 'in beş başarısız denemeden sonra sıfırlanmasını gerektir.
- Çalışma dosyalarının iTunes, iCloud veya Android Backup hizmetlerinde yedeklenmesini engelleyin.  
- Çalışma dosyalarının yalnızca OneDrive veya SharePoint 'e kaydedilmesini gerektir.
- Korunan uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda iş dosyalarını yüklemesini engelleyin.
- Cihaz 720 dakika boyunca çevrimdışıysa, çalışma dosyalarına erişimi engelleyin.
- Cihaz 90 gün boyunca çevrimdışı ise iş dosyalarını kaldırın. 

## <a name="background"></a>Arka Plan

Office Mobile Apps 'in yanı sıra mobil için Microsoft Edge, ikili kimlik desteği. Çift kimlik, uygulamaların iş dosyalarını kişisel dosyalardan ayrı olarak yönetmesine olanak tanır. 

![Şirket verileri ve kişisel veriler görüntüsü](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-01.png)

[Intune uygulama koruma ilkeleri](~/apps/app-protection-policy.md) , Intune 'a kayıtlı cihazlarda iş dosyalarınızın korunmasına yardımcı olur. Uygulama koruma ilkelerini, yönetilmek üzere Intune’da kaydedilmemiş çalışan cihazları üzerinde de uygulayabilirsiniz. Bu durumda, şirketiniz cihazı yönetmese de, iş dosyalarının ve kaynakların korunduğundan emin olmanız gerekir.

Kullanıcıların korumasız konumlarda iş dosyalarını kaydetmesini engellemek için uygulama koruma ilkelerini kullanabilirsiniz. Ayrıca Uygulama koruma ilkesi kapsamında olmayan diğer uygulamalara veri taşımayı da kısıtlayabilirsiniz. Uygulama koruma ilkesi ayarları aşağıdakileri içerir:
- Farklı Kaydet 'i engelle, kesme, kopyalama ve yapıştırmayı kısıtla gibi veri konumu değiştirme ilkeleri.
- Erişim için basit PIN gerektirmek ve yönetilen uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemek için ilke ayarlarına erişin.

Uygulama tabanlı koşullu erişim ve istemci uygulama yönetimi Exchange online ve diğer Office 365 hizmetlerine yalnızca Intune uygulama koruma ilkelerini destekleyen istemci uygulamaların erişmesine izin vererek bir güvenlik katmanı ekler.

Exchange Online'a yalnızca Microsoft Outlook uygulamasının erişmesine izin verdiğinizde, iOS ve Android üzerindeki yerleşik posta uygulamalarını engelleyebilirsiniz. Ayrıca, Intune uygulama koruma ilkelerinin uygulanmadığı uygulamaların SharePoint Online'a erişmesini engelleyebilirsiniz.

Bu örnekte, yönetici Outlook uygulamasına uygulama koruma ilkeleri uygulamış, ardından Outlook uygulamasını kurumsal e-postaya erişirken kullanılabilecek onaylı uygulamalar listesine ekleyen bir koşullu erişim ilkesi eklemiştir.

![Outlook uygulaması koşullu erişim işlem akışı](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-02.png)

## <a name="prerequisites"></a>Önkoşullar

Intune yönetici izinlerini takip etmeniz gerekir:

   - Yönetilen uygulamalar okuma, oluşturma, silme ve atama izinleri
   - İlke ayarları okuma, oluşturma ve atama izinleri
   - Kuruluş okuma izni

## <a name="step-1---introduction"></a>Adım 1 - Giriş

**Intune uygulama koruması** Kılavuzlu senaryoyu izleyerek verilerin kuruluşunuz dışında paylaşılmasını veya sızmasını önleyecaksınız. 

Atanan iOS ve Android kullanıcıları, her bir Office uygulaması her açtıklarında PIN girmeleri gerekir. 5 başarısız PIN girişiminden sonra, kullanıcılar PIN kodlarını sıfırlamalıdır. Zaten bir cihaz PIN 'ı gerekliyse, kullanıcılar etkilenmez.

### <a name="what-you-will-need-to-continue"></a>Devam etmeniz gerekenler

Kullanıcılarınızın ihtiyacı olan uygulamaları ve bunlara erişmek için gerekenleri isteyeceğiz. Aşağıdaki bilgilere sahip olduğunuzdan emin olun:
- Kurumsal kullanım için onaylanan Office uygulamalarının listesi.
- Yönetilmeyen cihazlarda onaylanan uygulamaları başlatmaya yönelik tüm PIN gereksinimleri.

## <a name="step-2---basics"></a>2\. adım-temel bilgiler

Bu adımda, yeni uygulama koruma ilkeniz için bir **ön ek** ve **Açıklama** girmeniz gerekir. **Ön eki**eklerken, Kılavuzlu senaryonun oluşturduğu kaynaklarla ilgili ayrıntılar güncelleştirilir. Atamaları ve yapılandırmayı değiştirmeniz gerekiyorsa, bu ayrıntılar daha sonra ilkelerinizi bulmayı kolaylaştırır. 

> [!TIP]
> Daha sonra başvurabilmeniz için oluşturulacak kaynakları bir yere göz önünde bulundurmanız gerekir.

## <a name="step-3---apps"></a>3\. adım-uygulamalar

Başlamanıza yardımcı olması için, Bu Kılavuzlu senaryo iOS ve Android cihazlarda korumak üzere aşağıdaki mobil uygulamaları önceden seçer:
- Microsoft Excel 
- Microsoft Word 
- Microsoft Teams 
- Microsoft Edge 
- Microsoft PowerPoint 
- Microsoft Outlook 
- Microsoft OneDrive 

Bu Kılavuzlu senaryo, iş sitelerinin korumalı bir tarayıcıda açılmasını sağlamak üzere Microsoft Edge 'de Web bağlantıları açmak için de bu uygulamaları yapılandırır.

Korumak istediğiniz ilkeyle yönetilen uygulamaların listesini değiştirin. Bu listeye uygulama ekleyin veya kaldırın. 

Uygulamaları seçtikten **sonra ileri**' ye tıklayın.

## <a name="step-4---configuration"></a>4\. adım-yapılandırma

Bu adımda, bu uygulamalardaki kurumsal dosyalara ve e-postalara erişmek ve bunları paylaşmak için gereksinimleri yapılandırmanız gerekir. Varsayılan olarak, kullanıcılar kuruluşunuzun OneDrive ve SharePoint hesaplarına veri kaydedebilir.

| Ayar | Description | Varsayılan Değer |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| PIN türü | Sayısal PIN 'Ler tüm numaralardan oluşur. Passcodes, alfasayısal karakterlerden ve özel karakterlerden oluşur.  İOS/ıpados 'ta, "geçiş kodu" türünü yapılandırmak için, uygulamanın Intune SDK sürüm 7.1.12 veya üstüne sahip olmasını gerektirir. Sayısal türlerde Intune SDK sürümü kısıtlaması yoktur. | Sayısal |
| Minimum PIN uzunluğunu seçin | PIN dizisindeki basamak sayısı alt sınırını belirtin. | 6 |
| Daha sonra erişim gereksinimlerini yeniden denetle (dakika dışı) | İlke ile yönetilen uygulama, belirtilen işlem yapılmayan dakika sayısından daha uzun bir süre boyunca etkin değilse, uygulama erişim gereksinimlerini ister (ör. Uygulama başlatıldıktan sonra yeniden denetlenecek PIN, koşullu başlatma ayarları). | 30 |
| Kuruluş verilerini yazdırma | Engellenirse, uygulama korumalı verileri yazdıramaz. | Engelle |
| Yönetilmeyen tarayıcılarda ilkeyle yönetilen uygulama bağlantılarını açın | Engellenirse, ilkeyle yönetilen uygulama bağlantıları yönetilen bir tarayıcı açılmalıdır. | Engelle |
| Yönetilmeyen uygulamalara veri kopyalama | Engellenirse, yönetilen veriler yönetilen uygulamalarda kalır. | Allow |

## <a name="step-5---assignments"></a>5\. adım-atamalar

Bu adımda, şirket verilerinize erişimi olduğundan emin olmak için eklemek istediğiniz kullanıcı gruplarını seçebilirsiniz. Uygulama koruması cihazlara değil kullanıcılara atanır, bu nedenle şirket verileriniz, kullanılan cihaz ve kayıt durumu ne olursa olsun güvenli olacaktır.

Uygulama koruma ilkeleri ve koşullu erişim ayarları atanmayan kullanıcılar, mobil cihazlarında kişisel uygulamalara ve yönetilmeyen yerel depolamaya verileri şirket profilinden kaydedebilecektir. Ayrıca, kişisel uygulamalarla Microsoft Exchange gibi kurumsal veri hizmetlerine de bağlanabilirler.

## <a name="step-6---review--create"></a>6\. adım-Inceleme ve oluşturma

Son adım, yapılandırdığınız ayarların özetini incelemenizi sağlar. Seçimlerinizi inceledikten sonra, Kılavuzlu senaryoyu tamamlamaya yönelik **Oluştur** ' a tıklayın. Kılavuzlu senaryo tamamlandıktan sonra bir kaynak tablosu görüntülenir. Bu kaynakları daha sonra düzenleyebilirsiniz, ancak Özet görünümden ayrıldığınızda tablo kaydedilmez.

> [!IMPORTANT]
> Kılavuzlu senaryo tamamlandıktan sonra bir özet görüntülenir. Özette listelenen kaynakları daha sonra değiştirebilirsiniz, ancak bu kaynağı görüntüleyen tablo kaydedilmez.
## <a name="next-steps"></a>Sonraki adımlar

- Cloud Services 'ın korumasız uygulamalara iş dosyalarını göndermesini sağlamak üzere kullanıcılara uygulama tabanlı bir koşullu erişim ilkesi atayarak iş dosyalarının güvenliğini artırın. Daha fazla bilgi için bkz. [Intune ile uygulama tabanlı koşullu erişim Ilkeleri ayarlama](~/protect/app-based-conditional-access-intune-create.md).

