---
title: "Microsoft Intune kullanarak macOS cihazlarına Office 365 yükleme"
titlesuffix: 
description: "macOS cihazlarında Office 365 uygulamalarını yüklemek için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune ile macOS cihazlarına Office 365'i atama

**Mağaza uygulaması** türü, macOS cihazlarına Office 365 uygulamaları atamanızı kolaylaştırır. Bu uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar, uygulamalarınızın güvenli ve güncel tutulmasına yardımcı olmak için ayrıca Microsoft AutoUpdate (MAU) ile gelir. Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görünmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

macOS cihazlarına Office 365'i eklemeye başlamadan önce aşağıdaki ayrıntıları anlamalısınız:

- Bu uygulamaları dağıtacağınız cihazların macOS 10.10 veya üzerini çalıştırıyor olması gerekir.
- Intune yalnızca Office Mac 2016 paketindeki Office uygulamalarının eklenmesini destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa kaydedilmeyen dosyalardaki veriler kaybedilebilir.

## <a name="create-and-configure-the-app-suite"></a>Uygulama paketini oluşturma ve yapılandırma

Office 365'i eklemek için **Uygulamalar** dikey penceresini kullanın.
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde, **Yönet** bölümünden **Uygulamalar**’ı seçin. 
5. **Ekle**'yi seçerek **Uygulama ekle** dikey penceresini görüntüleyin.
6. **Uygulama türü** listesinde, **Office 365 Paketi** grubundan **macOS** öğesini seçin.
7. Uygulama paketi hakkında bilgi sağlamak için **Uygulama Paketi Bilgileri**'ni seçin. Bu bilgiler, Intune’da uygulama paketini bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı uygulamasında paketi bulması kolaylaşır.
8.  Aşağıdaki bilgileri belirtin:
    - **Paket Adı** - Uygulama paketinin şirket portalında görüntülenen adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket Açıklaması** - Uygulama paketi için bir açıklama girin.
    - **Yayımcı** - Yayımcı olarak Microsoft gösterilir.
    - **Kategori** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu ayar, kullanıcıların şirket portalına göz atarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle** - Bu ayar uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si** (isteğe bağlı) - Bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si** (isteğe bağlı) - Bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - Geliştirici olarak Microsoft gösterilir.
    - **Sahip** - Sahip olarak Microsoft gösterilir.
    - **Notlar** (isteğe bağlı) - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** - Kullanıcılar şirket portalına göz attığında uygulamayla birlikte Office 365 logosu görüntülenir.
9.  **Uygulama bilgileri** bölmesinde **Tamam**’a tıklayın.
10. **Uygulama ekle** dikey penceresinde **Ekle**’ye tıklayın.
    Paket, uygulama listesinde tek bir girdi olarak gösterilir.

## <a name="configure-app-assignments"></a>Uygulama atamalarını yapılandırma

Bu adımda, uygulama paketi için atamaları yapılandırın. 

1. Uygulama listesinde **Office 365** uygulama paketini seçerek **Office 365** genel bakış dikey penceresini görüntüleyin.
2. **Office 365** dikey penceresinde **Atamalar**'a tıklayın.
3. Uygulama paketini kullanacak bir grup eklemek için **Grup ekle**'ye tıklayın. **Grup ekle** dikey penceresi görüntülenir.
3. **Atama türü** olarak **Gerekli** ayarlayın.
4. Paketi seçtiğiniz gruba atayın. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

    >[!Note]
    > Office 365 uygulama paketinin gerekli olmasını istediğiniz hiçbir grupta, bu paketi Microsoft Intune aracılığıyla silemezsiniz.

5. **Ata** dikey penceresinde **Tamam**'ı seçin.
6. **Grup ekle** dikey penceresinde **Tamam**’ı seçin.
7. Atamalarınızın kaydedilmesi için **Kaydet**'i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Windows 10 cihazına Office 365 uygulamalarını ekleme hakkında bilgi edinmek için bkz. [Microsoft Intune ile Office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlara atama](apps-add-office365.md).
- Kullanıcı gruplarında uygulama atamalarını dahil etme ve dışlamayı öğrenmek için, bkz. [Uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).
