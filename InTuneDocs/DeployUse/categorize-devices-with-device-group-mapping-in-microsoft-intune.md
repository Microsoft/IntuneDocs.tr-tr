---
# required metadata

title: Cihaz grubu eşleme ile cihazları kategorilere ayırma | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Cihazları Microsoft Intune’da cihaz grubu eşleme ile kategorilere ayırma
Cihazların yönetimini kolaylaştırmak için, Microsoft Intune **cihaz grubu eşleme** kullanarak bu cihazları kendi tanımladığınız kategoriler altında gruplandırın. 

Cihaz grubu eşleme aşağıdaki iş akışını kullanır:
1. Kullanmak istediğiniz her kategori için Intune cihaz grupları oluşturursunuz.
2. Seçtiğiniz kategoriyi oluşturduğunuz cihaz grubuna eşleyen cihaz grubu eşleme kuralları yapılandırırsınız.
3. Son kullanıcılar cihazlarını kaydettiklerinde, yapılandırdığınız kategorilerden birini seçmeleri gerekir. Bu seçimi yaptıklarında cihazları, oluşturduğunuz ilgili cihaz grubuna otomatik olarak eklenir.
4. Bundan sonra, ilkeleri ve uygulamaları dağıtırken bu cihaz gruplarını kullanabilirsiniz.

Kategori örnekleri:
* Kişisel
* Satış noktası cihazı
* Tanıtım cihazı
* Satış
* Muhasebe
* Yönetici

Öte yandan, istediğiniz tüm kategorileri yapılandırabilirsiniz.

## Cihaz grubu eşlemeyi yapılandırma
1. Kullanmak istediğiniz her cihaz kategorisi için, bir Intune cihaz grubu oluşturun. Grupları oluşturma hakkında bilgi için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’ye tıklayın.
3. **Yönetim** çalışma alanında, **Mobil Cihaz Yönetimi**’ni genişletin ve **Cihaz Grubu Eşleme**’ye tıklayın.
4. **Cihaz Grubu Eşleme** sayfasında cihaz grubu eşlemeyi etkinleştirin.
5. Yeni eşleme kuralı oluşturmak için **Ekle**’ye tıklayın.
6. **Cihaz grubu eşleme kuralı ekle** iletişim kutusunda, oluşturmak istediğiniz kategorinin adını girin ve ardından açılan listede bu kategoriyi eşlemek istediğiniz cihaz koleksiyonunu seçin. İşiniz bittiğinde **Ekle**’ye tıklayın.
7. Kategorileri ve grupları eklemeyi tamamladığınızda **Kaydet**’e tıklayın.

Artık, kullanıcılar cihazlarını kaydettiklerinde onlara sizin yapılandırdığınız kategori listesi gösterilir. Kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen cihaz grubuna eklenir.

### Ayrıca bkz.
[Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

<!--HONumber=May16_HO2-->


