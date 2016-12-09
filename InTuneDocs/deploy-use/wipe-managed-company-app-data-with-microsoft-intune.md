---
title: "Yönetilen şirket uygulama verilerini silme | Microsoft Intune"
description: "Şirket verilerini cihazlardan uzaktan seçmeli olarak nasıl kaldırabileceğinizi öğrenin."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d32a66ee283906586e25173e736c02ee8bf23042


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>Microsoft Intune ile yönetilen şirket uygulama verilerini silme
Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak, özellikle de çalışanın kendi cihazından kişisel verilerin kaldırılmasını istemeyebilirsiniz.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır.
>[!NOTE]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.



## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1.  **Intune Mobil uygulama yönetimi** dikey penceresinde **Temizleme istekleri** kutucuğunu seçin.

    ![Özet kutucuğunu içeren Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  **Yeni silme istekleri**’ni seçin. **Yeni temizleme isteği** dikey penceresi açılır.

    ![Yeni temizleme isteği dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  **Kullanıcı**'yı seçerek **Kullanıcı** dikey penceresini açın ve uygulama verilerini temizlemek istediğiniz kullanıcıyı seçin.

4.  **Cihaz**’ı seçin.  Bu, seçili kullanıcıyla ilişkili tüm cihazları listeleyen **Cihaz** dikey penceresini açar.  Silmek istediğiniz cihazı seçin.

5.  Şimdi **Yeni temizleme isteği** dikey penceresine geri dönersiniz. Temizleme isteğinde bulunmak için **Tamam**’ı seçin. Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu istekleri izler.


![Temizleme istekleri kutucuğunun ekran görüntüsü ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme
 **Intune mobil uygulama yönetimi** dikey penceresindeki **Silme isteği** kutucuğunda bir özet rapor bulunur.  Bu rapor, genel durumu görüntüler ve bekleyen isteklerin ve hataların sayısını gösterir. Şu adımları izleyerek daha fazla ayrıntıya ulaşabilirsiniz:

1.  **Intune mobil uygulama yönetimi** dikey penceresinde **Temizleme isteği** kutucuğunu seçerek **Temizleme isteği** dikey penceresini açın.

2.  **Temizleme isteği** dikey penceresinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir.  Bir silme isteğini elle silmek için isteğe sağ tıklayın ve silmeyi seçin.

### <a name="see-also"></a>Ayrıca bkz.
[Mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Azure portalını kullanma](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Dec16_HO2-->


