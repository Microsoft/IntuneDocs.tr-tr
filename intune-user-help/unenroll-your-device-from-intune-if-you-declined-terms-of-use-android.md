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
ms.subservice: end-user
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: f54f0d9453e93ad54a1d2a96ff25051f3d8bd3a1
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75857682"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>“Kullanım Koşulları”nı reddetmeniz durumunda cihazınızı Intune yönetiminden kaldırma

Şirket Portalı uygulamasında oturum açmaya çalışırken kullanım koşullarını reddettiyseniz gelecek denemelerde Şirket Portalı uygulamasında oturum açmanız engellenir, dolayısıyla cihazınızı Intune’dan kaldırmak için bu “geçici çözüm” yönergelerini kullanmanız gerekir.

Şirket Portalı uygulamasını kaldırdığınızda, cihazınız da Intune’dan kaldırılır. Cihazınız artık şirket kaynaklarına erişemez. Cihazınızı yönetimden kaldırdığınızda ne olacağı hakkında daha fazla bilgi için bkz. [Cihazınızı Intune’dan kaldırdığınızda ne olur?](what-happens-if-you-unenroll-your-device-from-intune-android.md).

Şirket Portalı uygulamasını kaldırabilmeniz için **Cihaz yöneticileri** ayarına gidip **Şirket Portalı**’nı kapatmanız gerekir. Hangi Android cihazına sahip olduğunuza bağlı olarak adımlar biraz farklılık gösterebilir.

## <a name="removing-the-device-from-the-company-portal-app"></a>Cihazınızı Şirket Portalı uygulamasından kaldırma

Cihazınızı Intune’dan kaldırmak ve Şirket Portalı uygulamasını silmek için:

1. **Cihaz yöneticilerine**&gt; **ayarlar** &gt; **güvenlik &amp; ekran kilidi** ' ne gidin.

    Bu adım tamamlandıktan hemen sonra cihazınızın kaydı silinir.

2. **Şirket Portalı**’nı kapatın veya yanındaki onay kutusunun işaretini kaldırın.

    Şirket Portalı uygulamasını şimdi kaldırabilirsiniz.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

- Uygulamalar’a gidin -> Uygulamaya tıklayın -> “Verileri temizle” düğmesine basarak verileri temizleyin
- ‘\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal’ klasörünü silin


Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.
