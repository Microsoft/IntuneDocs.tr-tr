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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 50ea427f1365285e08b6ad0e5a098b67421f941f
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940263"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune tarafından yönetilen uygulamalardan yalnızca şirket verilerini temizleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir cihaz kaybolduğunda veya çalındığında veya çalışan şirketten ayrıldığında şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak özellikle de cihaz çalışana ait bir cihaz ise, cihazdaki kişisel verileri kaldırmak istemeyebilirsiniz.

>[!NOTE]
> İOS, Android ve Windows 10 platformları, şu anda Intune tarafından yönetilen uygulamalardan şirket verilerini silmek için desteklenen platformlardır. Intune ile yönetilen uygulamalar, Intune uygulama SDK 'sını içeren ve kuruluşunuz için lisanslı bir kullanıcı hesabına sahip olan uygulamalardır. Uygulama koruma Ilkelerinin dağıtımı, uygulama seçmeli silme özelliğini etkinleştirmek için gerekli değildir.

Şirket uygulama verilerini seçmeli olarak kaldırmak için bu konudaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulamanın cihazda bir dahaki çalıştırılmasından sonra şirket verileri uygulamadan kaldırılır. Bir silme isteği oluşturmaya ek olarak, uygulama koruma Ilkeleri (uygulama) erişim ayarlarının koşulları karşılanmazsa, kuruluşunuzun verilerini yeni bir eylem olarak seçmeli silme işlemini yapılandırabilirsiniz. Bu özellik, önceden yapılandırılmış ölçütlere göre uygulamalardan hassas kuruluş verilerini otomatik olarak korumanıza ve kaldırmanıza yardımcı olur.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Kullanıcı kaydı olmadan dağıtılmış WıP ilkeleri
Windows Information Protection (WıP) ilkeleri, MDM kullanıcılarının Windows 10 cihazını kaydetmesine gerek kalmadan dağıtılabilir. Bu yapılandırma, şirketlerin WıP yapılandırmasına bağlı olarak şirket belgelerini korumasına olanak sağlarken, kullanıcının kendi Windows cihazlarının yönetimini sürdürmesine izin verir. Belgeler bir WıP ilkesiyle korunduktan sonra, korunan veriler bir Intune Yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihazı seçip silme isteği gönderdiğinizde, WıP ilkesi aracılığıyla korunan tüm veriler kullanılamaz hale gelir. Azure portal Intune 'da, **istemci uygulaması** > **uygulamayı seçmeli silme**' yi seçin. Daha fazla bilgi için bkz. [Intune Ile Windows Information Protection (WIP) uygulama koruma Ilkesi oluşturma ve dağıtma](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Silme isteği oluşturma

1. [Azure Portal](https://portal.azure.com)oturum açın.

2. **Tüm hizmetler**' i seçin, filtre metin kutusuna **Intune** yazın ve **Intune**' u seçin. Intune bölmesi açılır, **istemci uygulamaları** bölmesini seçin.

    ![Microsoft Intune bölmesinin ekran görüntüsü](./media/apps-selective-wipe/apps-selective-wipe01.png)

3. **İstemci uygulamaları bölmesinde**, **uygulama seçmeli silme**' yi seçin.

4. **Yeni silme isteği ' ni**seçin. **Yeni temizleme isteği** bölmesi açılır.

    ![Yeni temizleme isteği bölmesinin ekran görüntüsü](./media/apps-selective-wipe/AzurePortal_MAM_NewWipeRequest.png)

5. Bir kullanıcı seçin ve ardından, uygulama verilerini silmek istediğiniz kullanıcıyı seçmek için **Seç** ' i seçin.

6. Ardından **Yeni temizleme isteği** bölmesinden **cihaz** ' ı seçin. Bu, seçili kullanıcıyla ilişkili tüm cihazları listeleyen **cihaz Seç** bölmesini açar ve ayrıca iki sütun, Kullanıcı tarafından tanımlanan kolay bir ad olan cihaz adı ve cihaz türü, cihaz platformu sağlar. Silmek istediğiniz cihazı seçin.

7. Şimdi **Yeni temizleme isteği** bölmesine geri dönersiniz. Silme isteği oluşturmak için **Tamam ' ı** seçin.

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği ve silme isteğiyle ilişkili kullanıcıyı oluşturur ve izler.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Silme isteğinin genel durumunu gösteren ve bekleyen isteklerin ve hataların sayısını içeren özetlenmiş bir raporunuz olabilir. Daha fazla bilgi edinmek için şu adımları izleyin:

1. **Istemci uygulamaları-uygulama seçmeli silme** bölmesinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir silme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, silme isteğinin **bekliyor**, **başarısız**veya **başarılı**olup olmadığını gösterir.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği durumunun ekran görüntüsü](./media/apps-selective-wipe/wipe-request-status-1.png)

Ayrıca, cihaz adını ve cihaz türünü görebilirsiniz, bu da raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silme işleminin gerçekleşmesi için kullanıcının uygulamayı açması gerekir ve silme işlemi yapıldıktan sonra 30 dakika kadar sürebilir.

## <a name="delete-a-wipe-request"></a>Silme isteğini sil

Bekleme durumundaki wpes 'ler el ile silene kadar görüntülenir. Silme isteğini el ile silmek için:

1. **Istemci uygulamaları-uygulama seçmeli silme** bölmesinde.

2. Listeden silmek istediğiniz Temizleme isteğine sağ tıklayın ve **Temizleme Isteğini Sil**' i seçin.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği listesinin ekran görüntüsü](./media/apps-selective-wipe/delete-wipe-request.png)

3. Silmeyi onaylamanız istenir, **Evet** veya **Hayır**' ı seçin ve ardından **Tamam**' a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.
[Uygulama koruma ilkesi nedir?](app-protection-policy.md)

[Uygulama yönetimi nedir?](app-management.md)
