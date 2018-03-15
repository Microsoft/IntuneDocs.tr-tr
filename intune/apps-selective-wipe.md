---
title: "Uygulamalardan yalnızca şirket verilerini temizleme"
titleSuffix: Microsoft Intune
description: "Microsoft Intune ile uygulamaları seçmeli olarak silme hakkında bilgi edinin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfd1b37c1b944a545234b93b44d651ead8f0f486
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak özellikle cihaz çalışana aitse kişisel verilerin kaldırılmasını istemeyebilirsiniz.

>[!NOTE]
> Şu anda Intune yönetilen uygulamalarından şirket verilerinin silinmesini destekleyen iki platform iOS ve Android platformlarıdır.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1.  [Azure portalı](https://portal.azure.com)’nda oturum açın.

2.  **Diğer Hizmetler**’i seçin, filtre metin kutusuna **Intune** yazın ve **Intune**’u seçin. Intune dikey penceresi açılır. **Mobil uygulamalar**’ı seçin.

    ![Microsoft Intune dikey penceresinin ekran görüntüsü](./media/apps-selective-wipe01.png)

3.  **Mobil uygulamalar** dikey penceresinde **Uygulama seçmeli silme**’yi seçin.

4.  **Yeni temizleme isteği**’ni seçin. **Yeni temizleme isteği** bölmesi açılır.

    ![Yeni temizleme isteği bölmesinin ekran görüntüsü](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  **Kullanıcı**'yı seçerek **Kullanıcı** dikey penceresini açın ve uygulama verilerini temizlemek istediğiniz kullanıcıyı seçin.

6.  Ardından, **Yeni temizleme isteği** dikey penceresinde **Cihaz**'ı seçin. Bu eylem, **Cihaz Seçin** dikey penceresini açar. Bu, seçilen kullanıcıyla ilişkili tüm cihazları listeler. Ayrıca bu bölme, kullanıcı tarafından tanımlanan kolay bir ad olan cihaz adını ve cihaz platformunu belirten cihaz türünü sağlar. 

7. Silmek istediğiniz cihazı listeden seçin.

8.  Şimdi **Yeni temizleme isteği** dikey penceresine geri dönersiniz. Temizleme isteğinde bulunmak için **Tamam**’ı seçin.

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu isteklerle temizleme isteği ile ilişkilendirilmiş kullanıcıyı izler.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Temizleme isteğinin genel durumunu gösteren ve bekleyen isteklerle hataların sayısını içeren bir özet raporunuz olabilir. Daha fazla bilgi almak için şu adımları izleyin:

1.  **Mobil Uygulamalar - Uygulama seçmeli silme** dikey penceresinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği durumunun ekran görüntüsü](./media/wipe-request-status-1.png)

Buna ek olarak, cihaz adını ve cihaz türünü görebilirsiniz; bunlar raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

## <a name="delete-a-wipe-request"></a>Temizleme isteğini silme

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir. Temizleme isteğini el ile silmek için:

1.  **Mobil Uygulamalar - Uygulama seçmeli silme** dikey penceresini açın.

2.  Listede silmek istediğiniz temizleme isteğine sağ tıklayın ve **Temizleme isteğini sil**’i seçin.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği listesinin ekran görüntüsü](./media/delete-wipe-request.png)

3.  Silme işlemini onaylamanız istenir; **Evet** veya **Hayır**’ı seçin, sonra da **Tamam**’a tıklayın.

### <a name="see-also"></a>Ayrıca bkz:
[Uygulama koruma ilkesi nedir](app-protection-policy.md)

[Uygulama yönetimi nedir](app-management.md)
