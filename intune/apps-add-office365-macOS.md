---
title: "Intune kullanarak macOS cihazlarına Office 365 yükleme"
titlesuffix: Azure portal
description: "macOS cihazlarında Office 365 uygulamalarını yüklemeyi kolaylaştırmak için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune ile macOS cihazlarına Office 365'i atama

Bu uygulama türü, macOS cihazlarına Office 365 uygulamaları atamanızı kolaylaştırır. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar, uygulamalarınızın güvenli ve güncel tutulmasına yardımcı olmak için ayrıca Microsoft AutoUpdate (MAU) ile gelir. Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görünmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

- Bu uygulamaları dağıtacağınız cihazların macOS 10.10 veya üzerini çalıştırıyor olması gerekir.
- Intune yalnızca Office Mac 2016 paketindeki Office uygulamalarının eklenmesini destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa kaydedilmeyen dosyalardaki veriler kaybedilebilir.


## <a name="get-started"></a>Başlarken
Office 365'i eklemek için **Uygulamalar** dikey penceresini kullanın.
1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3.  **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4.  **Mobil uygulamalar** iş yükündeki **Yönet** grubunda **Uygulamalar**’ı seçin. **Ekle**’yi seçin.
5.  **Uygulama Ekle** dikey penceresinde **Office 365** > **macOS**'u seçin.
6.  **Ekle**’yi seçin.

## <a name="configure-the-app-suite"></a>Uygulama paketini yapılandırma

Uygulama paketi hakkında bilgi sağlayın. Bu bilgiler, Intune’da paketi bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı uygulamasında paketi bulması kolaylaşır.

1.  **Uygulama Ekle** dikey penceresinde **Uygulama Paketi Bilgileri**’ni seçin.
2.  Aşağıdaki bilgileri belirtin:
    - **Paket Adı** - Uygulama paketinin şirket portalında görüntülenen adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket Açıklaması** - Uygulama paketi için bir açıklama girin.
    - **Yayımcı** - Yayımcı olarak Microsoft gösterilir.
    - **Kategori** - İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Kategorileri kullanmak, kullanıcıların şirket portalına gözatarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle** - Uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - Geliştirici olarak Microsoft gösterilir.
    - **Sahip** - Sahip olarak Microsoft gösterilir.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Simge Yükle** - Kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
3.  **Tamam**’ı seçin. Paket, uygulama listesinde tek bir girdi olarak gösterilir.

## <a name="configure-app-assignments"></a>Uygulama atamalarını yapılandırma

Bu adımda, uygulama paketi için atamaları yapılandırın. Kullanılabilir uygulama türünün yakında sağlanacağını unutmayın.

1.  Uygulama listesinde uygulama paketini seçin ve sonra da **Atamalar**'ı seçin.
2.  **Grup seç** öğesini seçin.
3.  Paketi seçtiğiniz gruba atayın. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](/intune/apps-deploy).
4.  Her grup için **Yükleme Gerektir**'i seçersiniz.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Atamalarınızın kaydedilmesi için **Kaydet**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Windows 10 cihazına Office 365 uygulamalarını ekleme hakkında bilgi edinmek için bkz. [Microsoft Intune ile Office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlara atama](/intune/apps-add-office365).
