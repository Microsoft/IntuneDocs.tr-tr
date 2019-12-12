---
title: Microsoft Intune kullanarak macOS cihazlarına Office 365 yükleme
titleSuffix: ''
description: macOS cihazlarında Office 365 uygulamalarını yüklemek için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01ca17c9f8e3fd86e12f225621e6dc0e07bb4acb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74564071"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune ile macOS cihazlara Office 365 atama

Bu uygulama türü, macOS cihazlara Office 365 2016 uygulamaları atamanızı kolaylaştırır. Bu uygulama türünü kullanarak Word, Excel, PowerPoint, Outlook ve OneNote yükleyebilirsiniz. Uygulamaların daha güvende ve güncel tutulabilmesi amacıyla uygulamalar, Microsoft AutoUpdate (MAU) ile gelir. Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görüntülenmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

macOS cihazlarına Office 365’i eklemeye başlamadan önce aşağıdaki ayrıntıları kavramanız gerekir:

- Bu uygulamaları dağıtacağınız cihazların macOS 10.10 veya üzerini çalıştırıyor olması gerekir.
- Intune yalnızca Office Mac 2016 paketindeki Office uygulamalarının eklenmesini destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa kaydedilmeyen dosyalardaki veriler kaybedilebilir.

## <a name="create-and-configure-the-app-suite"></a>Uygulama paketini oluşturma ve yapılandırma

**Uygulamalar** bölmesinden Office 365 uygulamaları ekleyin.
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türü** listesinde, **Office 365 Paketi** grubundan **macOS** öğesini seçin.
4. Uygulama paketi hakkında bilgi almak için **Uygulama Paketi Bilgileri**’ni seçin.  
    Bu bilgiler, Intune’da uygulama paketini bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı’nda paketi bulması kolaylaşır.
5. Aşağıdaki bilgileri girin:
    - **Paket Adı**: Uygulama paketinin Şirket Portalı’nda görüntülenen adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket Açıklaması**: Uygulama paketi için bir açıklama girin.
    - **Yayımcı**: Yayımcı olarak Microsoft gösterilir.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu ayar, kullanıcıların şirket portalına göz atarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: Geliştirici olarak Microsoft gösterilir.
    - **Sahip**: Sahip olarak Microsoft gösterilir.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Kullanıcılar şirket portalına göz attığında uygulamayla birlikte Office 365 logosu görüntülenir.
6. **Tamam**’ı seçin.
7. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.  
    Paket, uygulama listesinde tek bir girdi olarak gösterilir.

## <a name="configure-app-assignments"></a>Uygulama atamalarını yapılandırma

Bu adımda, uygulama paketi için atamaları yapılandırın. 

1. Uygulama listesinde **Office 365** uygulama paketini seçerek **Office 365** genel bakış bölmesini görüntüleyin.
2. **Office 365** bölmesinde **Atamalar**’ı seçin.
3. Uygulama paketini kullanacak bir grup eklemek için **Grup ekle**’yi seçin.  
    **Grup ekle** bölmesi görüntülenir.
4. **Atama türü**’nü **Gerekli** veya **Kullanılabilir** olarak ayarlayın.
5. Paketi seçtiğiniz gruplara atayın. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

    >[!Note]
    > Office 365 uygulama paketini Intune’da kaldıramazsınız.

5. **Ata** bölmesinde **Tamam**’ı seçin.
6. **Grup ekle** bölmesinde **Tamam**’ı seçin.
7. Atamalarınızı işlemek için **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Windows 10 cihazlara Office 365 uygulamaları ekleme hakkında bilgi edinmek için bkz. [Microsoft Intune ile Office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlara atama](apps-add-office365.md).
- Kullanıcı gruplarında uygulama atamalarını dahil etme ve dışlama hakkında bilgi edinmek için, bkz. [Uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).
