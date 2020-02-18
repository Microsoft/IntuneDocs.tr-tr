---
title: Microsoft Intune kullanarak mobil cihazlara yerleşik uygulamalar yükleme
titleSuffix: ''
description: Mobil cihazlarda yerleşik uygulamaları yüklemeyi kolaylaştırmak için Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96cd4997029c15396db91e9866bbb387c20f1044
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414441"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Microsoft Intune’a yerleşik uygulama ekleme

*Yerleşik* uygulama türü, Office 365 uygulamaları gibi seçkin yönetilen uygulamaları IOS/ıpados ve Android cihazlara atamanızı kolaylaştırır. Bu uygulama türüne belirli uygulamaları atayabilirsiniz; örneğin Excel, OneDrive, Outlook, Skype ve diğerleri. Bir uygulamayı ekledikten sonra uygulama türü, *Yerleşik iOS uygulaması* veya *Yerleşik Android uygulaması* olarak görüntülenir. Yerleşik uygulama türünü kullanarak bu uygulamalardan hangilerini cihaz kullanıcılarına yayımlayacağınızı seçebilirsiniz.

Intune konsolunun önceki sürümlerinde Intune, Outlook ve OneDrive gibi varsayılan olarak yönetilen birkaç Office 365 uygulaması sağlar. Bu yönetilen uygulamalar için uygulama türü *Yönetilen iOS Mağaza Uygulaması* veya *Yönetilen Android Uygulaması* olarak etiketlenmiştir. Bu uygulama türlerini kullanmak yerine yerleşik uygulama türünü kullanmanızı öneririz. Yerleşik uygulama türünü kullanarak Office 365 uygulamalarını düzenleme ve silme konusunda daha fazla esneklik kazanırsınız.

>[!NOTE]
>*Yönetilen iOS Mağaza* veya *Yönetilen Android Uygulaması* olarak etiketli varsayılan Office 365 uygulamaları, tüm atamalar silindiğinde uygulama listesinden kaldırılır.

## <a name="add-a-built-in-app"></a>Yerleşik uygulama ekleme

Microsoft Intune’da mümkün olan uygulamalara yerleşik uygulama eklemek için şunları yapın:
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **Mağaza uygulama** türleri altında **yerleşik uygulama**' yı seçin.
4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.
5. **Yerleşik uygulamaları seçin** sayfasında, dahil etmek istediğiniz uygulamaları seçmek Için **Uygulama Seç** ' e tıklayın.
6. Dahil etmek istediğiniz yerleşik uygulamaları seçin. 
7. Uygulamaları seçtikten sonra, **yerleşik uygulamalar** ' ı seçin bölmesinde **Seç** ' e tıklayın.
8. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.
9. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. Daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).
10. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
11. Uygulama için Grup atamalarını seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md). 
12. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
13. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

    Oluşturduğunuz uygulamanın **genel bakış** dikey penceresi görüntülenir.

## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma

Yerleşik uygulama hakkındaki bilgileri değiştirebilirsiniz. Bu bilgiler, uygulamayı Intune’da bulmanıza yardımcı olur ve kullanıcıların uygulamayı Şirket Portalı’nda bulması kolaylaşır.
1. **Tüm uygulamalar** > **uygulamalar** ' ı seçin ve değiştirmek istediğiniz yerleşik uygulamayı seçin.  
   Yerleşik uygulamaya ait bir bölme görüntülenecektir.
2. **Özellikler**' i seçin.
3. **Uygulama bilgileri**' nin yanındaki **Düzenle** ' yi seçin.
4. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri değiştirebilirsiniz:
    - **Ad**: Yerleşik uygulamanın Şirket Portalı’nda görüntülenen adını girin. Kullandığınız tüm adların benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. 
    - **Yayımcı**: Uygulama yayıncısının adını girin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden birini seçin. Bu seçeneği ayarladığınızda, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu şirket portalı 'nda öne çıkan bir uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin (örneğin *İK departmanı*).
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Simge Yükle**: Kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
5. Gözden geçir + **Kaydet** ' e tıklayarak **İnceleme + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
13. İşiniz bittiğinde, uygulamayı Intune 'da güncelleştirmek için **Kaydet** ' e tıklayın.

    Oluşturduğunuz uygulamanın **genel bakış** dikey penceresi görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

- Artık seçtiğiniz gruplara uygulamaları atayabilirsiniz. Daha fazla bilgi için bkz. [Uygulamaları gruplara atama](apps-deploy.md).
