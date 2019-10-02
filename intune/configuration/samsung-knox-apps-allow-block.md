---
title: Samsung Knox için uygulamalara izin veren veya uygulamaları engelleyen Microsoft Intune ilkesi
titleSuffix: ''
description: Samsung Knox Standard cihazlarında uygulamalara izin vermek veya uygulama engellemek için bir özel profil oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a8486e121e6497eefdd2d098c2421f2f3b53b8a2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730541"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Microsoft Intune’da özel ilkeler kullanarak Samsung Knox Standard cihazları için uygulamalara izin verme veya bunları engelleme 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makaledeki yordamı kullanarak, aşağıdakilerden birini oluşturan bir Microsoft Intune özel ilkesi oluşturun:

- Cihazda çalışması engellenmiş uygulamaların listesi. İlke uygulandığı sırada zaten yüklenmiş durumda olsalar bile, bu listede yer alan uygulamaların çalışması engellenir.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Yalnızca listelediğiniz uygulamalar yüklenebilir. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung Knox Standard çalıştıran cihazlar tarafından kullanılabilir.

## <a name="create-an-allowed-or-blocked-app-list"></a>izin verilen veya engellenen uygulama listesi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Cihaz yapılandırması**’nı seçin.
2. **Cihaz yapılandırması** bölmesinde **Yönet** > **Profiller**’i seçin.
2. Profil listesi bölmesinde **Profil oluştur**’u seçin.
3. **Profil oluştur** bölmesinde, bu cihaz profili için **Ad** ve isteğe bağlı bir **Açıklama** girin.
2. Bir **Android** **Platformu** ve bir de **Özel** **Profil türü** seçin.
3. **Ayarlar**’a tıklayın.
3. **Özel OMA-URI Ayarları** bölmesinde **Ekle**’yi seçin.
4. **OMA-URI Ayarı Ekle veya Düzenle** iletişim kutusunda aşağıdaki ayarları belirtin:

   Cihazda çalıştırılması engellenen uygulamalar listesi için:

   - **Ad** - **PreventStartPackages** girin.
   - **Açıklama** - 'Çalıştırılması engellenen uygulamalar listesi' gibi isteğe bağlı bir açıklama girin.
   - **Veri türü** - Açılan listeden **Dize**’yi seçin.
   - **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** girin.
   - **Değer** - İzin vermek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

   Diğer tüm uygulamaları hariç tutarak, kullanıcıların Google Play mağazasından yüklemesine izin verilen uygulamaların listesi için:
   - **Ad** - **AllowInstallPackages** girin.
   - **Açıklama** - 'Kullanıcıların Google Play mağazasından yükleyebilecekleri uygulamaların listesi' gibi isteğe bağlı bir açıklama girin.
   - **Veri türü** - Açılan listeden **Dize**’yi seçin.
   - **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** girin.
   - **Değer** - İzin vermek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

4. **Tamam**’a tıklayın ve ardından **Profil Oluştur** bölmesinde **Oluştur**’u seçin.

>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

Hedeflenen her cihazın bir sonraki girişinde, uygulama ayarları uygulanır.


<!---## Assign the custom profile--->
