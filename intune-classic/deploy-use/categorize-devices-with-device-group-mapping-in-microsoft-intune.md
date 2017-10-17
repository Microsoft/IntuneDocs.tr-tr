---
title: "Cihazları cihaz grubu eşleme ile kategorize etme"
description: "Cihazların yönetimini kolaylaştırmak için, Microsoft Intune cihaz grubu eşleme özelliğini kullanarak bu cihazları kendi tanımladığınız kategoriler altında gruplandırın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d6783f0dbf21d8bb1e652522df7ae1f37cbf4ffd
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Cihazları Microsoft Intune’da cihaz grubu eşleme ile kategorilere ayırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cihazların yönetimini kolaylaştırmak için cihazları kendi tanımladığınız kategorilere göre otomatik olarak gruplara eklemek için Microsoft Intune **cihaz grubu eşleme** kullanın. 

Cihaz grubu eşleme aşağıdaki iş akışını kullanır:
1. Kullanıcıların cihazlarını kaydederken arasından seçim yapacağı kategoriler oluşturma
2. Kullanmak istediğiniz her kategori için gruplar oluşturur veya var olan grupları kullanırsınız. Kullanmakta olduğunuz Intune sürümüne bağlı olarak, bunlar ya Intune grupları ya da Azure Active Directory güvenlik grupları olacaktır.
2. Seçtiğiniz kategoriyi oluşturduğunuz cihaz grubuna eşleyen kurallar yapılandırırsınız.
3. iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Bir Windows cihazına bir kategori atamak için, son kullanıcıların Şirket Portalı web sitesini kullanmaları gerekir (ayrıntılar için bu konu başlığındaki **Cihaz gruplarını yapılandırdıktan sonra** bölümüne bakın).
4. Ardından bu gruplara ilkeler ve uygulamalar dağıtabilirsiniz.

İstediğiniz herhangi bir cihaz kategori oluşturabilirsiniz, örneğin:
* Satış noktası cihazı
* Tanıtım cihazı
* Satış
* Muhasebe
* Yönetici

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Intune için grup yönetimindeki bir değişiklik hakkında önemli bilgiler

Geri bildiriminize dayalı olarak, Enterprise Mobility + Security genelinde gruplandırma ve hedefleme deneyimini birleştirme sürecindeyiz. Bu nedenle, yakında Intune gruplarını Azure Active Directory tabanlı güvenlik gruplarına dönüştüreceğiz. Bu değişiklikten sonra, artık Intune kullanarak grup oluşturmayacaksınız. Bunun yerine, bunları Azure portalında oluşturacaksınız. Bu değişiklik kademeli olarak yapılacaktır ve bu değişiklik hakkındaki tüm ayrıntıları [bu konuda](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) okuyabilirsiniz.

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Cihaz grubu eşlemeyi yapılandırmak için bu konudaki hangi yordamı kullanmalısınız?

Azure Active Directory tabanlı güvenlik gruplarının aşamalı olarak uygulanması nedeniyle, hangi yordamı kullanacağınızı belirlemek için **Intune yönetici konsolunda** [Gruplar](https://manage.microsoft.com) çalışma alanını açmanız gerekir:

-  Azure portalına bir bağlantı görüyorsanız, artık Intune grupları kullanmıyorsunuz demektir. Aşağıdaki [Azure Active Directory grupları için cihaz grubu eşlemeyi yapılandırma](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) yordamını izleyin.
-  Azure portalına bir bağlantı görmüyorsanız, Intune grupları kullanmaya devam ediyorsunuz demektir. Aşağıdaki [Intune grupları için cihaz grubu eşlemeyi yapılandırma](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) yordamını izleyin.

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Intune grupları için cihaz grubu eşlemeyi yapılandırma
1. Kullanmak istediğiniz her cihaz kategorisi için bir Intune cihaz grubu oluşturun veya var olan bir grup tanımlayın. Grupları oluşturma hakkında bilgi için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
3. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve ardından **Cihaz Grubu Eşleme**’yi seçin.
4. **Cihaz Grubu Eşleme** sayfasında cihaz grubu eşlemeyi etkinleştirin.
5. Yeni eşleme kuralı oluşturmak için **Ekle**’yi seçin.
6. **Cihaz grubu eşleme kuralı ekle** iletişim kutusunda, oluşturmak istediğiniz kategorinin adını girin ve ardından açılan listede bu kategoriyi eşlemek istediğiniz cihaz koleksiyonunu seçin. Bitirdiğinizde, **Ekle**’yi seçin.
7. Kategorileri ve grupları eklemeyi tamamladığınızda **Kaydet**’i seçin.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Azure Active Directory grupları için cihaz grubu eşlemeyi yapılandırma

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>1. Adım - Intune yönetim konsolunda cihaz kategorileri oluşturma
1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
3. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve ardından **Cihaz Kategorileri**’ni seçin.
4. **Cihaz Kategorileri** sayfasında, cihaz kategorilerini yapılandırabileceğiniz bir liste göreceksiniz: 
- Bir ad girip, ardından **Ekle**’ye tıklayarak bunu yeni bir cihaz kategorisi olarak ekleyebilirsiniz.
- Ayrıca, bir kategori seçip ardından **Silebilirsiniz**.

Adımda 2 Azure Active Directory güvenlik grupları oluştururken cihaz kategorisi adını kullanacaksınız.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. Adım - Active Directory güvenlik grupları oluşturma

Bu adımda, Azure portalında cihaz kategorisi ve cihaz kategorisi adına dayalı dinamik gruplar oluşturacaksınız.

Devam etmek için Azure Active Directory belgelerindeki [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) konusuna bakın.
**deviceCategory** özniteliğini kullanarak gelişmiş bir kural ile bir cihaz grubu oluşturmak için bu konudaki bilgilerden yararlanın.
Örneğin (**device.deviceCategory -eq** "<*Intune yönetici konsolundan aldığınız cihaz kategorisi adı*>")


## <a name="after-you-configure-device-groups"></a>Cihaz gruplarını yapılandırdıktan sonra

iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Intune cihaz grubuna veya Active Directory güvenlik grubuna eklenir.

Bir Windows cihazına bir kategori atamak için, cihazı kaydettikten sonra son kullanıcıların Şirket Portalı web sitesini (portal.manage.microsoft.com) kullanmaları gerekir. Bir Windows cihazında, web sitesine erişin ve **Menü** > **Cihazlarım**'a gidin. Sayfada listelenen kayıtlı bir cihazı seçin, sonra bir kategori seçin. 

Bir kategori seçtikten sonra cihaz, oluşturduğunuz karşılık gelen gruba otomatik olarak eklenir. Cihaz siz kategorileri yapılandırmadan önce kaydedildiyse, son kullanıcı Şirket Portalı web sitesinde cihaz hakkında bir bildirim görür ve Şirket Portalı uygulamasına iOS veya Android üzerinde bir daha eriştiğinde kendisinden bir kategori seçmesi istenir.



### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
