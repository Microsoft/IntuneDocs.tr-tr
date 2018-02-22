---
title: "Azure portalında Intune’a giriş"
titlesuffix: Azure portal
description: "Azure portalında Intune hakkındaki temel bilgileri alın ve Intune’un cihazlarınızı yönetmenize nasıl yardımcı olabileceğini öğrenin.”"
keywords: 
author: arob98
ms.author: angrobe
nmanager: dougeby
ms.date: 02/14/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 6e2528c243938e81a6f730a950ee3949ca44047c
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Azure portalında Microsoft Intune’a giriş


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Diğer Azure hizmetleri gibi Microsoft Intune da Azure portalında kullanılabilir. Azure portalında **Intune**’u seçerek kuruluşunuzun mobil cihazlarını, bilgisayarlarını ve uygulamalarını yönetebilirsiniz.

>[!NOTE] 
> Microsoft Intune’un önceki bir sürümünü kullandıysanız aşağıdaki bilgiler işinize yarayabilir:
    * [Özelliklerim Azure’da nereye gitti?](ui-changes.md) size, Azure’a taşınma sonucu değişmiş olan iş akışları ve kullanıcı arabirimlerini gösteren bir başvurudur.
    * [Azure portalında klasik Intune grupları](groups-get-started.md), grup yönetimi için Azure Active Directory güvenlik gruplarına geçmiş olmanın olası sonuçlarını açıklar.

Azure portalında Microsoft Intune deneyiminin en önemli özellikleri şunlardır:

- Tüm Enterprise Mobility + Security (EMS) bileşenleriniz için tümleşik bir konsol
- Web standartlarında hazırlanan HTML tabanlı bir konsol
- Birçok eylemi otomatik hale getirmek için Microsoft Graph API’si desteği
- Tüm Azure uygulamalarınız genelinde uyumluluk sağlamak için Azure Active Directory (AD) grupları
- En modern web tarayıcıları için destek

## <a name="before-you-start"></a>Başlamadan önce

Azure Portal’da Intune’u kullanmak için, bir Intune yönetici ve kiracı hesabınız olmalıdır. Hesabınız yoksa [bir hesap için kaydolun](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal için desteklenen web tarayıcıları

Azure Portal, modern PC ve Mac bilgisayarlarla tabletlerin çoğunda çalışır. Cep telefonları desteklenmez.
Şu anda, aşağıdaki web tarayıcıları desteklenmektedir:

- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en so sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

Desteklenen tarayıcılar hakkındaki en son bilgiler için [Azure portalını](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) kontrol edin.

## <a name="microsoft-intune-in-the-azure-portal"></a>Azure portalında Microsoft Intune

[Azure portalı](https://portal.azure.com), Microsoft Intune hizmetini bulabileceğiniz yerdir. Azure’da, birçoğunu düzenli olarak kullanamayacağınız birkaç hizmet mevcuttur. Portal deneyiminizi özelleştirmeye yönelik hızlı bir kılavuz için bkz. [Azure portalında Intune’a başlarken](get-started-azure.md).

## <a name="the-microsoft-intune-documentation"></a>Microsoft Intune belgeleri

Bu konu ve diğer tüm Microsoft Intune belge setleri, devamlı olarak güncelleştirilmektedir. Görmek istediklerinize ilişkin önerileriniz varsa konu yorumlarında geri bildirim sağlayın. Görüşlerinizi öğrenmeyi çok isteriz.

Belgeler, ihtiyacınız olan bilgileri bulmanızı kolaylaştırmak için Azure portalında Microsoft Intune düzenini (aşağıda gösterildiği gibi) yansıtır.

![Azure Portal iş yükleri](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Belge kılavuzu

Microsoft Intune’un genel alanlarını kolayca bulmak ve anlamak için aşağıdaki tabloyu kullanın.

| Bölüm                                                      | Description                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Giriş ve çalışmaya başlama](introduction-intune.md)       | Intune’un temel özelliklerini kavrayın:<br /> - Yaygın çözümler<br /> - Microsoft Intune’un çalışma şekli<br /> - Intune’da cihaz yönetimi<br /> - Intune’da uygulama yönetimi<br /> - Cihaz kaydıyla veya kayıt olmaksızın Enterprise Mobility Management (EMM)                                                         |
| [Planlama ve tasarım](planning-guide.md)                         | Microsoft Intune ortamınızı başarıyla planlamanıza ve tasarlamanıza yardımcı rehber.                                                                                                                                                                                                             |
| [Cihaz kaydı](device-enrollment.md)                    | İş gücünüzün cihazlarını Microsoft Intune’a kaydederek Intune hizmetinin bu cihazları yönetmenize nasıl yardımcı olduğunu kavrayın. İş gücünüzün cihazlarını kaydetmek için çeşitli yöntemler vardır.                                                                                                         |
| [Cihaz uyumluluğu](device-compliance.md)                    | Intune cihaz uyumluluk ilkeleri, bir cihazın Microsoft Intune tarafından uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar. Örneğin cihaza erişim için bir parola gerektirme, cihaz şifreleme ve en düşük işletim sistemi sürümü gerektirme gibi işlemler uyumluluk örnekleridir. |
| [Cihaz yapılandırması](device-profiles.md)                   | Microsoft Intune ile cihaz profilleri oluşturarak, yönettiğiniz tüm cihazlarda ayarlar ve özellikleri yapılandırın. Örneğin bildirimler, veri paylaşımı, e-posta desteği, Wi-Fi bağlantısı, sertifikalar ve uç nokta koruması gibi işlevleri yapılandırabilirsiniz.              |
| [Cihazlar](device-management.md)                              | Yönettiğiniz cihazların, son kullanıcılarınızın işlerini yapması için gereken kaynakları sağladığından ve aynı zamanda verilerin risklerden korunduğundan emin olun. İş gücü cihaz envanterini gözden geçirerek ve uzak cihaz eylemleri gerçekleştirerek cihazları yönetin.                                                      |
| [Mobil uygulamalar](app-management.md)                             | Uygulamaları nasıl ekleyeceğinizi, dağıtacağınızı, izleyeceğinizi, yapılandıracağınızı ve koruyacağınızı kavrayın.                                                                                                                                                                                                                             |
| [Koşullu erişim](conditional-access.md)                  | Şirket verilerinize erişimi yöneten cihaz temelli ve uygulama temelli koşullar tanımlayın.                                                                                                                                                                                                            |
| [Kullanıcılar](users-add.md)                                        | Yönettiğiniz cihaz ve uygulamalara nasıl kullanıcı ekleyeceğinizi öğrenin.                                                                                                                                                                                                                                           |
| [Gruplar](groups-get-started.md)                              | Intune ile grupları nasıl oluşturacağınızı ve yöneteceğinizi öğrenin. Grupları kullanarak hızlıca cihaz ve uygulama yapılandırma ve koruma ilkeleri atayabilirsiniz.                                                                                                                                             |
| [Intune rolleri](role-based-access-control.md)                 | Çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin nasıl uygulanacağını denetlemeyi öğrenin. Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.                                                                                 |
| [Yazılım güncelleştirmeleri](windows-update-for-business-configure.md) | Windows 10 cihazlar için yazılım güncelleştirmelerini nasıl yapılandıracağınızı öğrenin.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Yenilikler

Microsoft Intune’un en son işlevleri hakkında bilgi için bkz. [Yenilikler](whats-new.md).
