---
title: Uygulama koruma ilkeleri içeren iOS uygulamaları
description: Bu konu başlığı altında, iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f013ec1d40b9593e7eb8d317b5b63545c58f181
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57399141"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

 Bu konu başlığı altında, uygulama koruma ilkelerinin uygulandığı uygulamalar kullanıldığında kullanıcı deneyimini açıklar. Uygulama koruma ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: Örneğin, kullanıcı iş hesabı kullanarak uygulamalara veya şirketinizin OneDrive iş konumunda depolanan dosyalara eriştiğinde.

##  <a name="access-apps"></a>Erişim uygulamaları

Cihaz **Intune'a kayıtlı değilse**, kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir. Uygulamaya uygulama koruma ilkelerinin uygulanabilmesi için yeniden başlatma gereklidir.

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görür.

##  <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

Uygulama koruma ilkeleri uygulamalar yalnızca iş bağlamında kullanılırken uygulanırken, birden çok kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı hesaplar (iş ve kişisel) kullanmanıza izin verir.  

Örneğin, kullanıcı iş verilerine erişirken kendisinden bir PIN istenir. **Outlook uygulamasında**, kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, kullanıcı iş hesabında yazdığında bir PIN istenir.  Microsoft **Word**, **PowerPoint** ve **Excel** için, kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde PIN istenir.

- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

Uygulama koruma ilkeleri yalnızca iş bağlamında uygulanır. Bu nedenle uygulama, bağlamın iş veya kişisel olmasına göre farklı davranış gösterebilir.

##  <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Çoklu kimlik uygulamaları, kullanıcıların birden fazla hesap eklemelerine olanak tanır.  Intune uygulaması yalnızca bir yönetilen hesap destekler.  Intune uygulaması yönetilmeyen hesapların sayısını sınırlamaz.

Uygulamada bir yönetilen hesap olduğunda:
*   Kullanıcı ikinci bir yönetilen hesap eklemeye çalışırsa kendisinden hangi yönetilen hesabın kullanılacağını seçmesi istenir.  Diğer hesap kaldırılır.
*   BT yöneticisi ikinci bir mevcut hesaba ilke eklerse kullanıcıdan hangi yönetilen hesabın kullanılacağını seçmesi istenir.  Diğer hesap kaldırılır.

Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor—**Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili olan hesap, koruma ilkesini ilk olarak alır. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız ve Şirket Y ile ilişkili kullanıcı hesabını eklemeniz gerekir.

### <a name="add-a-second-account"></a>İkinci hesap ekleme

iOS cihazı kullanıyorsanız, bu cihaza ikinci bir iş hesabı eklemeye çalıştığınızda bir engelleme iletisi görebilirsiniz. Hesaplar görüntülenir ve kaldırmak istediğiniz hesabı seçebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](end-user-mam-apps-android.md)
