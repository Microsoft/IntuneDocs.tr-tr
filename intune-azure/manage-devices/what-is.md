---
title: "Intune ile cihazları yönetme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune ile yönettiğiniz cihazları görüntülemeyi ve bu cihazlar üzerinde çeşitli işlemler yapmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 040c4e18d87110ab7380a64540d08127574a7c46
ms.openlocfilehash: 5a967cc1be387f83f95591186f786db61d3debcd


---

# <a name="what-is-device-management"></a>Cihaz yönetimi nedir? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Cihazlar ve gruplar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar ve Gruplar**’ı seçin.

    ![Cihazlar ve gruplar iş yükü](./media/devices-and-groups-workload.png)

Şimdi, aşağıdakilerden birini seçin:

- **Genel Bakış** Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemleri hakkında bilgi alın.
- **Yönet** - Yönettiğiniz tüm cihazların listesini görmek için **Tüm Cihazlar**’ı seçin.
    Listedeki cihazlardan birini seçerek <*cihaz adı*> **Genel Bakış** dikey penceresini açın. Burada aşağıdakilerden birini seçebilirsiniz:
    - **Genel Bakış**  - Cihaz hakkında adı, sahibi, bir KCG cihazı olup olmadığı, en son ne zaman iade edildiği gibi genel bilgilere bakın. Buna ek olarak, cihaz üzerinde aşağıdaki uzak eylemleri de gerçekleştirebilirsiniz (tüm cihaz platformları tüm eylemleri desteklemez):
        - **Şirket verilerini kaldır** - Yalnızca Intune tarafından yönetilen şirket verilerini kaldırır. Cihazdan kişisel verileri kaldırmaz. Cihaz artık Intune tarafından yönetilmez ve şirket kaynaklarına erişemez (Azure Active Directory’ye katılmış olan Windows cihazlarında desteklenmez).
        - **Fabrika sıfırlaması** - Cihazı varsayılan ayarlarına döndürür. Cihaz artık Intune tarafından yönetilmez ve hem şirket verileri hem de kişisel veriler kaldırılır. Bu eylemi geri alamazsınız.
        - **Uzaktan kilitleme** -Cihazı kilitler. Cihaz sahibinin kilidi açmak için geçiş kodunu kullanması gerekir. PIN veya parola ayarlanmış bir cihazı yalnızca uzaktan kilitleyebilirsiniz.
        - **Geçiş kodunu sıfırla** - Cihaz için, *cihaz adı*> **Genel Bakış** dikey penceresinde görüntülenecek yeni geçiş kodunu oluşturur.
        - **Etkinleştirme Kilidini Atla** - Kullanıcının Apple kimliği ve parolası olmadan iOS cihazının etkinleştirme kilidini kaldırır. Siz etkinleştirme kilidini atladıktan sonra, iPhone’umu Bul uygulaması başlatıldığında cihaz etkinleştirme kilidini yeniden açar. Etkinleştirme kilidini, ancak cihaza fiziksel erişiminiz varsa atlayın.
        - **Kayıp modu** - Cihaz çalınırsa, kayıp modunu etkinleştirebilirsiniz. Bu, cihazın kilit ekranında görüntülenecek bir mesaj ve telefon numarası belirtmenize olanak tanır.
        - **Yeniden başlat** - Cihazın yeniden başlatılmasına neden olur. Yeniden başlatma işlemi cihaz sahibine otomatik olarak bildirilmez, dolayısıyla cihaz sahibi çalışmasını kaybedebilir.
        ![Cihaza genel bakış](http://i.imgur.com/4Rx4VXm.png)
        
    - **Donanım** - Cihaz hakkında boş depolama alanı, modeli ve üreticisi gibi daha ayrıntılı bilgilere bakın.
    ![Yönetilen cihaz donanım envanteri](./media/hardware-inventory.png)
    - **Algılanan Uygulamalar** - Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaların listesini görüntüler.
    ![Algılanan uygulamalar düğümü](./media/detected-applications.png)
- **İzleme** Yönettiğiniz cihazlarda gerçekleştirilen cihaz eylemlerinin listesini ve bu eylemlerin geçerli durumu görmek için **Cihaz Eylemleri**’ni seçin.
![Cihaz eylemlerini izleme](./media/monitor-device-actions.png)



<!--HONumber=Feb17_HO1-->


