---
title: Uygulamalardan yalnızca şirket verilerini temizleme
titleSuffix: Microsoft Intune
description: Microsoft Intune ile yalnızca şirket verilerini Intune tarafından yönetilen uygulamalardan seçerek silmeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a5bcdf9c3218df91bea85858ea21e88718e81633
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72498321"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak özellikle cihaz çalışana aitse kişisel verilerin kaldırılmasını istemeyebilirsiniz.

>[!NOTE]
> İOS, Android ve Windows 10 platformları, şu anda Intune tarafından yönetilen uygulamalardan şirket verilerini silmek için desteklenen platformlardır. Intune ile yönetilen uygulamalar, Intune uygulama SDK 'sını içeren ve kuruluşunuz için lisanslı bir kullanıcı hesabına sahip olan uygulamalardır. Uygulama koruma Ilkelerinin dağıtımı, uygulama seçmeli silme özelliğini etkinleştirmek için gerekli değildir.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır. Silme isteğine ek olarak, Uygulama Koruma İlkeleri (APP) Erişim ayarlarının koşullarına uyulmadığında yeni bir eylem olarak kuruluşunuzun verilerinin seçmeli silinmesini yapılandırabilirsiniz. Bu özellik, önceden yapılandırılmış ölçütler temelinde hassas kuruluş verilerini otomatik olarak korumanıza ve uygulamalardan kaldırmanıza yardımcı olur.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Kullanıcı kaydı olmadan dağıtılmış WıP ilkeleri
Windows Information Protection (WıP) ilkeleri, MDM kullanıcılarının Windows 10 cihazını kaydetmesine gerek kalmadan dağıtılabilir. Bu yapılandırma, kullanıcıların Windows cihazlarının yönetimini sürdürmesini sağlarken şirketlerin de kurumsal belgelerini WIP yapılandırmasına göre korumasını sağlar. Belgeler bir kez bir WIP ilkesiyle korunduktan sonra korumalı veriler bir Intune yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihaz seçilerek ve bir silme isteği gönderilerek WIP İlkesi aracılığıyla korunan tüm veriler kullanılamaz hale getirilir. Azure portal Intune 'da, **istemci uygulaması** > **uygulamayı seçmeli silme**' yi seçin. Daha fazla bilgi için bkz. [Intune ile Windows Bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.

2. **Tüm hizmetler**’i seçin, filtre metin kutusuna **Intune** yazın ve **Intune**’u seçin. Intune bölmesi açıldığında **İstemci uygulamaları** bölmesini seçin.

    ![Microsoft Intune bölmesinin ekran görüntüsü](./media/apps-selective-wipe/apps-selective-wipe01.png)

3. **İstemci uygulamalar bölmesi**'nde, **Uygulama seçmeli silme**'yi seçin.

4. **Yeni temizleme isteği**’ni seçin. **Yeni temizleme isteği** bölmesi açılır.

    ![Yeni temizleme isteği bölmesinin ekran görüntüsü](./media/apps-selective-wipe/AzurePortal_MAM_NewWipeRequest.png)

5. Bir kullanıcı seçin ve ardından uygulama verilerini silmek istediğiniz kullanıcıyı seçmek üzere **Seçin** öğesini seçin.

6. Ardından, **Yeni temizleme isteği** bölmesinde **Cihaz**'ı seçin. Bu, seçilen kullanıcıyla ilişkilendirilmiş tüm cihazları listeleyen ve aynı zamanda biri cihaz adı (kullanıcı tarafından tanımlanan kolay ad) ve diğeri de cihaz türü (cihaz platformu) olmak üzere iki sütun sağlayan **Cihaz Seçin** bölmesini açar. Silmek istediğiniz cihazı seçin.

7. Şimdi **Yeni temizleme isteği** bölmesine geri dönersiniz. Temizleme isteğinde bulunmak için **Tamam**’ı seçin.

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu isteklerle temizleme isteği ile ilişkilendirilmiş kullanıcıyı izler.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Temizleme isteğinin genel durumunu gösteren ve bekleyen isteklerle hataların sayısını içeren bir özet raporunuz olabilir. Daha fazla bilgi almak için şu adımları izleyin:

1. **İstemci Uygulamalar - Uygulama seçmeli silme** bölmesinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği durumunun ekran görüntüsü](./media/apps-selective-wipe/wipe-request-status-1.png)

Buna ek olarak, cihaz adını ve cihaz türünü görebilirsiniz; bunlar raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

## <a name="delete-a-wipe-request"></a>Temizleme isteğini silme

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir. Temizleme isteğini el ile silmek için:

1. **İstemci Uygulamalar - Uygulama seçmeli silme** bölmesinde.

2. Listede silmek istediğiniz temizleme isteğine sağ tıklayın ve **Temizleme isteğini sil**’i seçin.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği listesinin ekran görüntüsü](./media/apps-selective-wipe/delete-wipe-request.png)

3. Silme işlemini onaylamanız istenir; **Evet** veya **Hayır**’ı seçin, sonra da **Tamam**’a tıklayın.

## <a name="see-also"></a>Ayrıca bkz:
[Uygulama koruma ilkesi nedir](app-protection-policy.md)

[Uygulama yönetimi nedir](app-management.md)
