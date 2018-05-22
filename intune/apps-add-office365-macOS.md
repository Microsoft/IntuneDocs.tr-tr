---
title: Microsoft Intune kullanarak macOS cihazlarına Office 365 yükleme
titlesuffix: ''
description: macOS cihazlarında Office 365 uygulamalarını yüklemek için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78158afeb9c12e8056f42066be78c37f962b4462
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune ile macOS cihazlara Office 365 atama

*Mağaza uygulaması* türü, macOS cihazlarına Office 365 uygulamaları atamanızı kolaylaştırır. Bu uygulama türünü kullanarak Word, Excel, PowerPoint, Outlook ve OneNote yükleyebilirsiniz. Uygulamaların daha güvende ve güncel tutulabilmesi amacıyla uygulamalar, Microsoft AutoUpdate (MAU) ile gelir. Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görüntülenmesini istediğiniz uygulamalar.


## <a name="before-you-start"></a>Başlamadan önce

macOS cihazlarına Office 365’i eklemeye başlamadan önce aşağıdaki ayrıntıları kavramanız gerekir:

- Bu uygulamaları dağıtacağınız cihazların macOS 10.10 veya üzerini çalıştırıyor olması gerekir.
- Intune yalnızca Office Mac 2016 paketindeki Office uygulamalarının eklenmesini destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa kaydedilmeyen dosyalardaki veriler kaybedilebilir.

## <a name="create-and-configure-the-app-suite"></a>Uygulama paketini oluşturma ve yapılandırma

**Uygulamalar** bölmesinden Office 365 uygulamaları ekleyin.
1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükü bölmesindeki **Yönet**'in altında **Uygulamalar**’ı seçin. 
5. **Ekle**’yi seçin.
6. **Uygulama türü** listesinde, **Office 365 Paketi** grubundan **macOS** öğesini seçin.
7. Uygulama paketi hakkında bilgi almak için **Uygulama Paketi Bilgileri**’ni seçin.  
    Bu bilgiler, Intune’da uygulama paketini bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı’nda paketi bulması kolaylaşır.
8. Aşağıdaki bilgileri girin:
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
9. **Tamam**’ı seçin.
10. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.  
    Paket, uygulama listesinde tek bir girdi olarak gösterilir.

## <a name="configure-app-assignments"></a>Uygulama atamalarını yapılandırma

Bu adımda, uygulama paketi için atamaları yapılandırın. 

1. Uygulama listesinde **Office 365** uygulama paketini seçerek **Office 365** genel bakış bölmesini görüntüleyin.
2. **Office 365** bölmesinde **Atamalar**’ı seçin.
3. Uygulama paketini kullanacak bir grup eklemek için **Grup ekle**’yi seçin.  
    **Grup ekle** bölmesi görüntülenir.
4. **Atama türü** olarak **Gerekli** ayarlayın.
5. Paketi seçtiğiniz gruplara atayın. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

    >[!Note]
    > Office 365 uygulama paketini Intune’da kaldıramazsınız.

5. **Ata** bölmesinde **Tamam**’ı seçin.
6. **Grup ekle** bölmesinde **Tamam**’ı seçin.
7. Atamalarınızı işlemek için **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Windows 10 cihazlara Office 365 uygulamaları ekleme hakkında bilgi edinmek için bkz. [Microsoft Intune ile Office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlara atama](apps-add-office365.md).
- Kullanıcı gruplarında uygulama atamalarını dahil etme ve dışlama hakkında bilgi edinmek için, bkz. [Uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).
