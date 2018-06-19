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
ms.openlocfilehash: fcf71015d292ea22be1c818e526bc723b1af7165
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31017623"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>“Kullanım Koşulları”nı reddetmeniz durumunda cihazınızı Intune yönetiminden kaldırma

Şirket Portalı uygulamasında oturum açmaya çalışırken kullanım koşullarını reddettiyseniz gelecek denemelerde Şirket Portalı uygulamasında oturum açmanız engellenir, dolayısıyla cihazınızı Intune’dan kaldırmak için bu “geçici çözüm” yönergelerini kullanmanız gerekir.

Şirket Portalı uygulamasını kaldırdığınızda, cihazınız da Intune’dan kaldırılır. Cihazınız artık şirket kaynaklarına erişemez. Cihazınızı yönetimden kaldırdığınızda ne olacağı hakkında daha fazla bilgi için bkz. [Cihazınızı Intune’dan kaldırdığınızda ne olur?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Şirket Portalı uygulamasını kaldırabilmeniz için **Cihaz yöneticileri** ayarına gidip **Şirket Portalı**’nı kapatmanız gerekir. Hangi Android cihazına sahip olduğunuza bağlı olarak adımlar biraz farklılık gösterebilir.

## <a name="removing-the-device-from-the-company-portal-app"></a>Cihazınızı Şirket Portalı uygulamasından kaldırma

Cihazınızı Intune’dan kaldırmak ve Şirket Portalı uygulamasını silmek için:

1.  **Ayarlar** &gt; **Güvenlik &amp; Ekran Kilidi** &gt; **Cihaz yöneticileri**’ne gidin.

    Bu adım tamamlandıktan hemen sonra cihazınızın kaydı silinir.

2.  **Şirket Portalı**’nı kapatın veya yanındaki onay kutusunun işaretini kaldırın.

    Şirket Portalı uygulamasını şimdi kaldırabilirsiniz.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

  - Uygulamalar’a gidin -> Uygulamaya tıklayın -> “Verileri temizle” düğmesine basarak verileri temizleyin
  - ‘\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal’ klasörünü silin


Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.
