---
title: Uygulama koruma ilkelerine sahip iOS/ıpados uygulamaları
description: Bu konuda, iOS/ıpados uygulamanız uygulama koruma ilkeleriyle yönetildiğinde ne bekleneceğiniz açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c854811a9deb938613af872f3cf86244ab9121b3
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514668"
---
# <a name="what-to-expect-when-your-iosipados-app-is-managed-by-app-protection-policies"></a>İOS/ıpados uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

Intune uygulama koruma ilkeleri, iş veya okul için kullanılan uygulamalar için geçerlidir. Diğer bir deyişle, çalışanlarınız ve öğrencileriniz uygulamalarını kişisel bir bağlamda kullanırken, deneyimlerinde fark olmadığını fark edebilirler. Bununla birlikte iş veya okul bağlamında, hesap kararları almak, ayarlarını güncelleştirmek veya yardım için sizinle iletişim kurmak için istemler alabilir. Kullanıcılarınızın Intune ile korunan uygulamalara erişmeye ve bu uygulamaları kullanmaya çalıştıklarında nasıl deneyim sağladığını öğrenmek için bu makaleyi kullanın.  

## <a name="access-apps"></a>Erişim uygulamaları

Cihaz **Intune'a kayıtlı değilse**, kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir. Uygulama koruma ilkelerinin uygulamaya uygulanabilmesi için yeniden başlatma gereklidir.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS/iPadOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görür.

## <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

Çoklu kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı iş ve kişisel hesaplar kullanmanıza olanak sağlar. Bir cihaz PIN 'i gibi uygulama koruma ilkeleri, kullanıcılar bu uygulamalara iş veya okul bağlamında erişirken etkinleştirilir.   

Kullanıcılar, ilkeleri nasıl yapılandırdığınıza bağlı olarak, tüm uygulamaları genelinde PIN istemiyle farklı şekilde karşılaşabilir.  Örneğin, ilkelerinizi şu şekilde yapılandırabilirsiniz:       
* Microsoft Outlook, uygulamayı başlatırken kullanıcıdan bir PIN 'ı ister. 
* OneDrive, iş hesabında oturum açtıklarında kullanıcıdan PIN 'i ister.  
* Microsoft Word, PowerPoint ve Excel, şirket OneDrive Iş konumunda depolanan belgelere erişirken kullanıcıdan PIN kodu ister.  

- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.  

## <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme  

Intune uygulama koruma ilkeleri, kullanıcıları her uygulama için bir yönetilen iş veya okul hesabıyla sınırlandırır. Uygulama koruma ilkeleri, bir kullanıcının ekleyebilecek yönetilmeyen hesap sayısını sınırlamaz.   

- Kullanıcı ikinci bir yönetilen hesap eklemeye çalışırsa kendisinden hangi yönetilen hesabın kullanılacağını seçmesi istenir. Kullanıcı ikinci hesabı eklerse, ilk hesap kaldırılır.
- Kullanıcı hesaplarından başka birine koruma ilkeleri eklerseniz, kullanıcıdan hangi yönetilen hesabın kullanılacağını seçmesi istenir. Diğer hesap kaldırılır. 

Bazı kullanıcılar yönetilen hesapları değiştirme veya seçme seçeneğini almaz. Seçeneği şu şekilde olan cihazlarda kullanılamaz:
* Intune tarafından yönetiliyor  
* Üçüncü taraf Kurumsal Mobilite yönetim çözümleri tarafından yönetilir ve ıntunemamupn ayarıyla yapılandırılır 

Aşağıdaki örnek senaryo, birden çok kullanıcı hesabının nasıl ele alınacağını açıklar:  

Kullanıcı A,**Şirket X** ve **Şirket Y**olmak üzere iki şirket için geçerlidir. Kullanıcı A 'nın her şirket için bir iş hesabı vardır ve her ikisi de uygulama koruma ilkelerini dağıtmak için Intune 'u kullanır. **Şirket X** , **Şirket Y** **'den önce** uygulama koruma ilkeleri dağıtır. **Şirket X** ile ilişkili hesap, önce uygulama koruma ilkesini alır. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız ve Şirket Y ile ilişkili kullanıcı hesabını eklemeniz gerekir.  

## <a name="next-steps"></a>Sonraki adımlar

[Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](end-user-mam-apps-android.md)
