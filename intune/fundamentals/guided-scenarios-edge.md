---
title: Kılavuzlu senaryo-mobil için Microsoft Edge dağıtma
titleSuffix: Microsoft Intune
description: Mobil için Microsoft Edge 'i Microsoft 365 cihaz yönetim portalından dağıtmaya yönelik Kılavuzlu senaryo hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88beb8f4791c127b0a225878f5bc43b6dd9b4025
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839368"
---
# <a name="guided-scenario---deploy-microsoft-edge-for-mobile"></a>Kılavuzlu senaryo-mobil için Microsoft Edge dağıtma 

Bu [Kılavuzlu senaryoyu](~/fundamentals/guided-scenarios-overview.md)izleyerek, kuruluşunuzda IOS veya Android cihazlarda Microsoft Edge uygulamasını kullanıcılarınıza atayabilirsiniz. Bu uygulamayı atamak, kullanıcılarınızın kurumsal cihazlarını kullanarak içeriğe sorunsuz bir şekilde gözatmasına olanak tanır. 

Microsoft Edge, kullanıcıların, iş içeriğini birleştirmelerine, düzenlemenize ve yönetmesine yardımcı olan yerleşik özelliklerle Web 'in dağınıklığını kesmesine olanak sağlar. Microsoft Edge uygulamasındaki kurumsal Azure AD hesaplarıyla oturum açan iOS ve Android cihazlarının kullanıcıları, çalışma alanı **sık kullanılanları** ve tanımladığınız Web sitesi filtreleriyle önceden yüklenmiş olan tarayıcılarıdır.

> [!NOTE]
> Kullanıcıların iOS veya Android cihazlarını kaydetmelerine izin verirseniz, bu senaryo kaydı etkinleştirmez ve kullanıcıların kendi başına Microsoft Edge yüklemesi gerekir.
Intune ilkeleri tarafından etkinleştirilen aşağıdaki Microsoft Edge kurumsal özellikleri şunları içerir: 

- **Çift kimlik**: Kullanıcılar hem iş hesabı hem de kişisel hesap ekleyerek göz atabilir. Office 365 ve Outlook mimarilerinde ve deneyimlerinde olduğu gibi iki kimlik arasında belirgin bir ayrım vardır. Intune yöneticileri, iş hesabını kullanarak korumalı bir göz atma deneyimi sağlamak üzere istenen ilkeleri belirleyebilir. 
- **Intune uygulama koruma ilkesi tümleştirmesi**: Yöneticiler artık uygulama koruma ilkeleri için Microsoft Edge'i hedefleyerek kes, kopyala ve yapıştır denetimi, ekran görüntüsü almayı engelleme ve kullanıcı tarafından seçilen bağlantıların yalnızca diğer yönetilen uygulamalarda açılmasını sağlama gibi denetimlere sahip olabilir.
- **Azure Uygulama Ara Sunucusu tümleştirmesi**: Yöneticiler artık SaaS ve web uygulamaları erişimini denetleyerek kullanıcıların şirket ağı veya İnternet üzerinden bağlanma durumlarından bağımsız olarak tarayıcı tabanlı uygulamaların yalnızca güvenli Microsoft Edge tarayıcısında çalıştırılmasının sağlanmasına yardımcı olabilir. 
- **Yönetilen Sık Kullanılanlar ve Giriş Sayfası kısayolları**: Yöneticiler, erişim kolaylığı sunmak için şirket bağlamına geçen son kullanıcıların sık kullanılanlar listesinde yer alacak URL'ler belirleyebilir. Yöneticiler, şirket kullanıcıları Microsoft Edge'de yeni bir sayfa veya sekme açtığında birincil kısayol olarak görüntülenecek bir giriş sayfası kısayolu ayarlayabilir.

## <a name="prerequisites"></a>Prerequisites

- [MDM yetkilisini Intune olarak ayarlama](mdm-authority-set.md#set-mdm-authority-to-intune) -mobil cihaz YÖNETIMI (MDM) yetkilisi ayarı, cihazlarınızı nasıl yöneteceğinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.
- Gerekli Intune yönetici izinleri:
    - Yönetilen uygulamalar okuma, oluşturma, silme ve atama izinleri
    - Mobil uygulamalar okuma, oluşturma ve atama izinleri
    - İlke ayarları okuma, oluşturma ve atama izinleri
    - Kuruluş okuma, güncelleştirme izni

## <a name="step-1---introduction"></a>Adım 1 - Giriş

Mobil destekli senaryo **Için Microsoft Edge** dağıtımı ' nı izleyerek, seçilen bir IOS ve Android kullanıcıları grubu Için Microsoft Edge 'in temel bir dağıtımını ayarlayacaksınız. Bu dağıtım, **çift kimlik** ve **yönetilen sık kullanılanlar ve giriş sayfası kısayollarını**uygular. Ayrıca, seçilen kullanıcılar tarafından kaydedilen cihazlar, Intune tarafından otomatik olarak yüklenen Microsoft Edge uygulamasına sahip olur. Bu otomatik yükleme, aşağıdakiler dahil olmak üzere tüm Kullanıcı odaklı kayıt türlerinde gerçekleşir: 
- Şirket Portalı uygulaması aracılığıyla iOS kaydı 
- Apple Business Manager aracılığıyla iOS Kullanıcı benzeşimi kaydı 
- Şirket Portalı uygulama aracılığıyla eski Android kaydı 

Bu Kılavuzlu senaryo, **Uyglların** Microsoft Edge sık kullanılanları 'nda görünmesini ve tarayıcıyı Intune şirket portalı uygulaması için ayarlamış olduğunuz markala yapılandırmasını otomatik olarak sağlayacaktır. 

### <a name="what-you-will-need-to-continue"></a>Devam etmeniz gerekenler
Kullanıcılarınızın ihtiyacı olan çalışma alanı sık kullanılanlarını ve Web 'e göz atmak için gereken filtreleri isteyeceğiz. Devam etmeden önce aşağıdaki görevleri tamamladığınızdan emin olun:

- Kullanıcıları Azure AD gruplarına ekleyin. Daha fazla bilgi için bkz. [temel Grup oluşturma ve Azure Active Directory kullanarak üye ekleme](https://go.microsoft.com/fwlink/?linkid=2102458).
- İOS veya Android cihazlarını Intune 'A kaydetme. Daha fazla bilgi için bkz. [cihaz kaydı](https://go.microsoft.com/fwlink/?linkid=2102547).
- Microsoft Edge 'de eklenecek çalışma alanı sık kullanılanları listesini toplayın.
- Microsoft Edge 'de zorlamak için Web sitesi filtrelerinin bir listesini toplayın.

## <a name="step-2---basics"></a>2\. adım-temel bilgiler

Bu adımda, yeni Microsoft Edge ilkeleriniz için bir ad ve açıklama girmeniz gerekir. Atamaları ve konfigürasyonları değiştirmeniz gerekiyorsa, bu ilkelere daha sonra başvurulabilir. Kılavuzlu senaryo iOS cihazlarınız için bir Microsoft Edge iOS uygulaması ve Android cihazlarınız için bir Microsoft Edge Android uygulaması ekler ve atayacaktır. Ayrıca, bu adım bu uygulamalar için yapılandırma ilkeleri oluşturacaktır.

## <a name="step-3---configuration"></a>3\. adım-yapılandırma

Bu adımda, Kılavuzlu senaryo Microsoft Edge 'i Intune aracılığıyla kullanıcılara atanan diğer tüm uygulamaları gösterecek şekilde yapılandıracak ve Microsoft Intune Şirket Portalı uygulamasıyla aynı markalamayı paylaşacak. Microsoft Edge 'i bir **giriş sayfası kısayol URL 'si**, **yönetilen yer Işaretlerinin**listesi ve **Engellenen URL**'lerin bir listesi ile daha fazla yapılandırabilirsiniz. **Giriş sayfası kısayol URL 'si** , kullanıcıların cihazlarındaki Microsoft Edge 'de yeni bir sekme açtıklarında arama çubuğunun altında ilk simge olarak kullanıcılara görünür. **Yönetilen yer işaretleri** kullanıcılarınızın Iş bağlamında Microsoft Edge kullanırken kullanılabilir olması için sık kullanılan URL 'lerin bir listesidir. **Engellenen URL 'ler** , iş bağlamdayken kullanıcılarınız için engellenen siteleri belirler. Diğer tüm sitelere izin verilir. 

## <a name="step-4---assignments"></a>4\. adım-atamalar

Bu adımda, Microsoft Edge Mobile 'ın iş için yapılandırılmasını sağlamak üzere eklemek istediğiniz kullanıcı gruplarını seçebilirsiniz. Microsoft Edge, bu kullanıcılar tarafından kaydedilen tüm iOS ve Android cihazlara da yüklenir.

## <a name="step-5---review--create"></a>5\. adım-Inceleme ve oluşturma

Son adım, yapılandırdığınız ayarların özetini incelemenizi sağlar. Seçimlerinizi inceledikten sonra, Kılavuzlu senaryoyu tamamlamaya yönelik **Oluştur** ' a tıklayın. 

> [!NOTE]
> Sınır, yapılandırmayı almak için 12 saate kadar sürebilir. Daha fazla bilgi için bkz. [Microsoft Intune Için uygulama yapılandırma ilkeleri](~/apps/app-configuration-policies-overview.md).

> [!IMPORTANT]
> Kılavuzlu senaryo tamamlandıktan sonra bir özet görüntülenir. Özette listelenen kaynakları daha sonra değiştirebilirsiniz, ancak bu kaynağı görüntüleyen tablo kaydedilmez.

## <a name="next-steps"></a>Sonraki adımlar

- Intune uygulama koruma ilkesi tümleştirmesini ayarlayarak Microsoft Edge 'i kullanmaya ilişkin güvenliği artırın. Daha fazla bilgi için bkz. [Microsoft Edge Için uygulama koruma ilkeleri](~/apps/manage-microsoft-edge.md#application-protection-policies-for-microsoft-edge).
- Dahil edilecek intranet siteleriniz varsa, Azure uygulama proxy 'Si tümleştirmesiyle erişimi korumayı keşfedebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Edge Için uygulama proxy ayarlarını yapılandırma](~/apps/manage-microsoft-edge.md#configure-application-proxy-settings-for-microsoft-edge).

