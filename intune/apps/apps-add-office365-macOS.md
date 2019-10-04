---
title: Microsoft Intune kullanarak macOS cihazlarına Office 365 'yi yüklemeyin
titleSuffix: ''
description: MacOS cihazlarında Office 365 uygulamalarını yüklemek için Microsoft Intune nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 889cacbb56fb390b88c7db9c9516b8b43e4c3770
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940201"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Microsoft Intune ile macOS cihazlarına Office 365 atama

Bu uygulama türü, macOS cihazlarına Office 365 2016 uygulamaları atamanızı kolaylaştırır. Bu uygulama türünü kullanarak Word, Excel, PowerPoint, Outlook ve OneNote 'U yükleyebilirsiniz. Uygulamaları daha güvenli ve güncel tutmaya yardımcı olmak için uygulamalar Microsoft otomatik güncelleştirme (MAU) ile birlikte gelir. İstediğiniz uygulamalar, Intune konsolundaki uygulamalar listesinde tek bir uygulama olarak görüntülenir.


## <a name="before-you-start"></a>Başlamadan önce

MacOS cihazlarına Office 365 eklemeye başlamadan önce aşağıdaki ayrıntıları anlayın:

- Bu uygulamaları dağıttığınız cihazların macOS 10,10 veya sonraki bir sürümü çalıştırması gerekir.
- Intune yalnızca Mac için Office 2016 Suite 'e dahil edilen Office uygulamalarının eklenmesini destekler.
- Intune, uygulama paketini yüklerken herhangi bir Office uygulaması açıksa, kullanıcılar kaydedilmemiş dosyalardaki verileri kaybedebilir.

## <a name="create-and-configure-the-app-suite"></a>Uygulama paketi oluşturma ve yapılandırma

**Uygulamalar** bölmesinden Office 365 ekleyin.
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **istemci uygulamaları**' nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesinde, **Yönet**altında **uygulamalar**' ı seçin. 
5. **Ekle**' yi seçin.
6. **Uygulama türü** listesinde, **Office 365 Suite** grubunda **MacOS**' u seçin.
7. Uygulama paketi hakkında bilgi almak için **uygulama paketi bilgileri**' ni seçin.  
    Bu bilgiler, Intune 'da uygulama paketini belirlemenize yardımcı olur ve kullanıcıların şirket portalında uygulama paketini bulmasına yardımcı olur.
8. Aşağıdaki bilgileri girin:
    - **Paket adı**: uygulama paketinin şirket portalında görüntülendiği şekilde adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez varsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket açıklaması**: uygulama paketi için bir açıklama girin.
    - **Yayımcı**: yayımcı olarak Microsoft görünür.
    - **Kategori**: yerleşik uygulama kategorilerinden birini veya daha fazlasını veya oluşturduğunuz bir kategoriyi seçin. Bu ayar, kullanıcıların şirket portalına gözatarken uygulama paketini bulmasını kolaylaştırır.
    - **Bunu şirket portalı öne çıkan uygulama olarak görüntüle**: kullanıcılar uygulamalara gözatarken Şirket portalının ana sayfasında uygulama paketini göze çarpacak şekilde göstermek için bu seçeneği belirleyin.
    - **Bilgi URL 'si**: isteğe bağlı olarak, bu uygulamayla ilgili bilgileri içeren bir Web sitesinin URL 'sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL 'si**: isteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir Web sitesinin URL 'sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: Microsoft Geliştirici olarak görünür.
    - **Sahip**: Microsoft, sahip olarak görünür.
    - **Notlar**: isteğe bağlı olarak, bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Office 365 logosu, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
9. **Tamam ' ı**seçin.
10. **Uygulama Ekle** bölmesinde **Ekle**' yi seçin.  
    Paket, uygulamalar listesinde tek bir girdi olarak görüntülenir.

## <a name="configure-app-assignments"></a>Uygulama atamalarını yapılandırma

Bu adımda, uygulama paketi atamalarını yapılandırın. 

1. **Office 365** genel bakış bölmesini göstermek için uygulamalar listesinde **Office 365** uygulama paketi ' ni seçin.
2. **Office 365** bölmesinde **atamalar**' ı seçin.
3. Uygulama paketini kullanacak bir grup eklemek için **Grup Ekle**' yi seçin.  
    **Grup Ekle** bölmesi görüntülenir.
4. **Atama türünü** **gerekli** veya **kullanılabilir**olarak ayarlayın.
5. Paketi seçtiğiniz gruplara atayın. Daha fazla bilgi için bkz. [Microsoft Intune sahip gruplara uygulama atama](apps-deploy.md).

    >[!Note]
    > Office 365 uygulama paketini Intune aracılığıyla kaldıramazsınız.

5. **Ata** bölmesinde **Tamam**' ı seçin.
6. **Grup Ekle** bölmesinde **Tamam**' ı seçin.
7. Atamalarınızı yürütmek için **Kaydet**' i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Windows 10 cihazlarına Office 365 uygulamaları ekleme hakkında bilgi edinmek için bkz. [Microsoft Intune Ile office 365 ProPlus 2016 uygulamalarını Windows 10 cihazlarına atama](apps-add-office365.md).
- Kullanıcı gruplarından uygulama atamalarını dahil etme ve hariç tutma hakkında bilgi edinmek için bkz. [uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).
