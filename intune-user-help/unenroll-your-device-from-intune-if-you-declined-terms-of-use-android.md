---
title: Kullanım Koşulları’nı reddetmeniz durumunda cihazınızı Intune yönetiminden kaldırma | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb4ac87bef7c822111e95c18f149fa8d0598c36e
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67546627"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>“Kullanım Koşulları”nı reddetmeniz durumunda cihazınızı Intune yönetiminden kaldırma

Şirket Portalı uygulamasında oturum açmaya çalışırken kullanım koşullarını reddettiyseniz gelecek denemelerde Şirket Portalı uygulamasında oturum açmanız engellenir, dolayısıyla cihazınızı Intune’dan kaldırmak için bu “geçici çözüm” yönergelerini kullanmanız gerekir.

Şirket Portalı uygulamasını kaldırdığınızda, cihazınız da Intune’dan kaldırılır. Cihazınız artık şirket kaynaklarına erişemez. Cihazınızı yönetimden kaldırdığınızda ne olacağı hakkında daha fazla bilgi için bkz. [Cihazınızı Intune’dan kaldırdığınızda ne olur?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Şirket Portalı uygulamasını kaldırabilmeniz için **Cihaz yöneticileri** ayarına gidip **Şirket Portalı**’nı kapatmanız gerekir. Hangi Android cihazına sahip olduğunuza bağlı olarak adımlar biraz farklılık gösterebilir.

## <a name="removing-the-device-from-the-company-portal-app"></a>Cihazınızı Şirket Portalı uygulamasından kaldırma

Cihazınızı Intune’dan kaldırmak ve Şirket Portalı uygulamasını silmek için:

1. **Ayarlar** &gt; **Güvenlik &amp; Ekran Kilidi** &gt; **Cihaz yöneticileri**’ne gidin.

    Bu adım tamamlandıktan hemen sonra cihazınızın kaydı silinir.

2. **Şirket Portalı**’nı kapatın veya yanındaki onay kutusunun işaretini kaldırın.

    Şirket Portalı uygulamasını şimdi kaldırabilirsiniz.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

  - Uygulamalar’a gidin -> Uygulamaya tıklayın -> “Verileri temizle” düğmesine basarak verileri temizleyin
  - ‘\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal’ klasörünü silin


Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.
