---
title: "Uygulamalardan yalnızca şirket verilerini temizleme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune’la uygulamaları seçmeli olarak temizlemeyi öğrenin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: affe7323b8572aa17122011b293cb6a3a2fd7747
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak, özellikle de çalışanın kendi cihazından kişisel verilerin kaldırılmasını istemeyebilirsiniz.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1.  [Azure portalı](https://portal.azure.com)’nda oturum açın.

2.  **Diğer Hizmetler**’i seçin, filtre metin kutusuna **Intune** yazın ve **Intune**’u seçin. Intune önizleme dikey penceresi açıldığında, **Uygulamaları yönet** dikey penceresini seçin.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](./media/intune-azure-preview-blade.png)

3.  **Mobil Uygulamalar** dikey penceresinde **Yeni temizleme isteği**’ni seçin. **Yeni temizleme isteği** dikey penceresi açılır.

4.  **Yeni temizleme isteği**’ni seçin. **Yeni temizleme isteği** dikey penceresi açılır.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  **Kullanıcı**'yı seçerek **Kullanıcı** dikey penceresini açın ve uygulama verilerini temizlemek istediğiniz kullanıcıyı seçin.

6.  **Cihaz**’ı seçin. Bu, seçilen kullanıcıyla ilişkilendirilmiş tüm cihazları listeleyen ve aynı zamanda biri cihaz adı (kullanıcı tarafından tanımlanan kolay ad) ve diğeri de cihaz türü (cihaz platformu) olmak üzere iki sütun sağlayan **Cihaz** dikey penceresini açar. Silmek istediğiniz cihazı seçin.

7.  Şimdi **Yeni temizleme isteği** dikey penceresine geri dönersiniz. Temizleme isteğinde bulunmak için **Tamam**’ı seçin. 

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu isteklerle temizleme isteği ile ilişkilendirilmiş kullanıcıyı izler.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Temizleme isteğinin genel durumunu gösteren ve bekleyen isteklerle hataların sayısını içeren bir özet raporunuz olabilir. Daha fazla bilgi almak için şu adımları izleyin:

1.  **Mobil Uygulamalar - Uygulama Seçmeli Silme** dikey penceresinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](./media/wipe-request-status-1.png)

Buna ek olarak, cihaz adını ve cihaz türünü görebilirsiniz; bunlar raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

## <a name="delete-a-wipe-request"></a>Temizleme isteğini silme

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir.  Temizleme isteğini el ile silmek için:

1.  **Silme isteği** dikey penceresinde, **Silme isteği** dikey penceresini açmak için **Silme isteği**kutucuğunu seçin.

2.  Silmek istediğiniz temizleme isteğine sağ tıklayın ve **Temizleme isteğini sil**’i seçin.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](./media/delete-wipe-request.png)

3.  Silme işlemini onaylamanız istenir; **Evet** veya **Hayır**’ı seçin, sonra da **Tamam**’a tıklayın.

### <a name="see-also"></a>Ayrıca bkz.
[Uygulama koruma ilkesi nedir](app-protection-policy.md)

[Uygulama yönetimi nedir](app-management.md)
