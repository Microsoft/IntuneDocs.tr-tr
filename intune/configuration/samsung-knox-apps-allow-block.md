---
title: Samsung Knox için uygulamalara izin veren veya uygulamaları engelleyen Microsoft Intune ilkesi
titleSuffix: ''
description: Samsung Knox Standard cihazlarında uygulamalara izin vermek veya uygulama engellemek için bir özel profil oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b83a0339d87375502159467af323fceae5eb6e2
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207086"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Microsoft Intune’da özel ilkeler kullanarak Samsung Knox Standard cihazları için uygulamalara izin verme veya bunları engelleme 

Bu makaledeki yordamı kullanarak, aşağıdakilerden birini oluşturan bir Microsoft Intune özel ilkesi oluşturun:

- Cihazda çalışması engellenmiş uygulamaların listesi. İlke uygulandığı sırada zaten yüklenmiş durumda olsalar bile, bu listede yer alan uygulamaların çalışması engellenir.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Yalnızca listelediğiniz uygulamalar yüklenebilir. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung Knox Standard çalıştıran cihazlar tarafından kullanılabilir.

## <a name="create-an-allowed-or-blocked-app-list"></a>izin verilen veya engellenen uygulama listesi oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı **Windows Phone özel profilidir**.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
    - **Platform**: **Android**' i seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    Cihazda çalıştırılması engellenen uygulamalar listesi için:

    - **Ad**: **preventstartpackages**girin.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve profili bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama girin. Örneğin, **çalışması engellenen uygulamaların listesini**girin.
    - **OMA-URI** (büyük/küçük harfe duyarlı): **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/preventstartpackages**girin.
    - **Veri türü**: **dize**seçin.
    - **Değer**: izin vermek istediğiniz uygulama paket adlarının bir listesini girin. `;`, `:`veya `|` sınırlayıcı olarak kullanabilirsiniz. Örneğin, şunu girin: `package1;package2;`.

   Diğer tüm uygulamaları hariç tutarak, kullanıcıların Google Play mağazasından yüklemesine izin verilen uygulamaların listesi için:

    - **Ad**: **Allowınstallpackages**girin.
    - **Açıklama**: ayara genel bir bakış sağlayan bir açıklama ve profili bulmanıza yardımcı olacak diğer ilgili bilgileri girin. Örneğin, **kullanıcıların Google Play yükleye, uygulamaların listesini**girin.
    - **OMA-URI** (büyük/küçük harfe duyarlı): **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/allowınstallpackages**yazın.
    - **Veri türü**: **dize**seçin.
    - **Değer**: izin vermek istediğiniz uygulama paket adlarının bir listesini girin. `;`, `:`veya `|` sınırlayıcı olarak kullanabilirsiniz. Örneğin, şunu girin: `package1;package2;`.

5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.
6. İşiniz bittiğinde, Intune profilini oluşturmak için **tamam** > **Oluştur** ' u seçin. Bu tamamlandığında, profiliniz **cihazlar-yapılandırma profilleri** listesinde gösterilir.

>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

Her hedeflenen cihaz bir sonraki sefer iade ettiğinde, uygulama ayarları uygulanır.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).
