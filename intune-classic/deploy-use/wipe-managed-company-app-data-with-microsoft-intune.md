---
title: "Yönetilen şirket uygulama verilerini silme"
description: "Şirket verilerini cihazlardan uzaktan seçmeli olarak nasıl kaldırabileceğinizi öğrenin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7025bdd5d89e52f1c99f9cd834232daf324f3285
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="wipe-company-app-data-with-intune-mam"></a>Intune MAM ile şirket uygulama verilerini temizleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak, özellikle de çalışanın kendi cihazından kişisel verilerin kaldırılmasını istemeyebilirsiniz.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1.  [Azure portalı](https://portal.azure.com)’nda oturum açın.

2.  **Diğer Hizmetler**’i seçin, filtre metin kutusuna **Intune** yazın ve **Intune Uygulama Koruması**’nı seçin. Intune mobil uygulama yönetimi dikey penceresi açılır.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  **Ayarlar** dikey penceresinde **Temizleme istekleri**’ni seçin.

3.  **Yeni temizleme isteği**’ni seçin. **Yeni temizleme isteği** dikey penceresi açılır.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  **Kullanıcı**'yı seçerek **Kullanıcı** dikey penceresini açın ve uygulama verilerini temizlemek istediğiniz kullanıcıyı seçin.

5.  **Cihaz**’ı seçin. Bu, seçilen kullanıcıyla ilişkilendirilmiş tüm cihazları listeleyen ve aynı zamanda biri cihaz adı (kullanıcı tarafından tanımlanan kolay ad) ve diğeri de cihaz türü (cihaz platformu) olmak üzere iki sütun sağlayan **Cihaz** dikey penceresini açar. Silmek istediğiniz cihazı seçin.

6.  Şimdi **Yeni temizleme isteği** dikey penceresine geri dönersiniz. Temizleme isteğinde bulunmak için **Tamam**’ı seçin. 

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu isteklerle temizleme isteği ile ilişkilendirilmiş kullanıcıyı izler.

>[!NOTE]
> Intune mobil uygulama yönetimi dikey penceresinde **Temizleme isteği kutucuğuna** tıklayarak da **Temizleme istekleri** oluşturabilirsiniz.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Temizleme isteğinin genel durumunu gösteren ve bekleyen isteklerle hataların sayısını içeren bir özet raporunuz olabilir. Daha fazla bilgi almak için şu adımları izleyin:

1.  Intune mobil uygulama yönetimi dikey penceresinde **Temizleme istekleri** kutucuğuna tıklayın.

2.  **Silme isteği** dikey penceresinde, **Silme isteği** dikey penceresini açmak için **Silme isteği**kutucuğunu seçin.

3.  **Temizleme isteği** dikey penceresinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](../media/AppManagement/wipe-request-status-1.png)

Buna ek olarak, cihaz adını ve cihaz türünü görebilirsiniz; bunlar raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

## <a name="delete-a-wipe-request"></a>Temizleme isteğini silme

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir.  Temizleme isteğini el ile silmek için

1.  Intune mobil uygulama yönetimi dikey penceresinde **Temizleme istekleri** kutucuğuna tıklayın.

2.  **Silme isteği** dikey penceresinde, **Silme isteği** dikey penceresini açmak için **Silme isteği**kutucuğunu seçin.

3.  Silmek istediğiniz temizleme isteğine sağ tıklayın ve **Temizleme isteğini sil**’i seçin.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](../media/AppManagement/delete-wipe-request.png)

4.  Silme işlemini onaylamanız istenir; **Evet** veya **Hayır**’ı seçin, sonra da **Tamam**’a tıklayın.


### <a name="see-also"></a>Ayrıca bkz.
[Mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Azure portalını kullanma](azure-portal-for-microsoft-intune-mam-policies.md)
