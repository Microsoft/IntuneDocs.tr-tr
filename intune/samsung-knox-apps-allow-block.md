---
title: "Samsung KNOX için uygulamalara izin verme veya uygulamaları engelleme Intune ilkesi"
titlesuffix: Azure portal
description: "Samsung KNOX Standard cihazlarında uygulamalara izin vermek veya uygulama engellemek için bir özel profil oluşturun.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7be589889cab1e04eeebdac7091c7ce573a3dcc9
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Microsoft Intune’da özel ilkeler kullanarak Samsung KNOX Standard cihazları için uygulamalara izin verme veya bunları engelleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu başlığı altındaki yordamları kullanarak, aşağıdakilerden birini oluşturan bir Microsoft Intune özel ilkesi oluşturun:

- Cihazda çalışması engellenmiş uygulamaların listesi. İlke uygulandığı sırada zaten yüklenmiş durumda olsalar bile, bu listede yer alan uygulamaların çalışması engellenir.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Yalnızca listelediğiniz uygulamalar yüklenebilir. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX Standard çalıştıran cihazlar tarafından kullanılabilir.

## <a name="create-an-allowed-or-blocked-app-list"></a>izin verilen veya engellenen uygulama listesi oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
2. Profil listesi dikey penceresinde **Profil Oluştur**’u seçin.
3. **Profil Oluştur** dikey penceresinde, bu cihaz profili için **Ad** ve isteğe bağlı bir **Açıklama** girin.
2. Bir **Android** **Profil türü** ve bir de **Özel** Profil türü seçin.
3. **Ayarlar**’a tıklayın.
3. **Özel OMA-URI Ayarları** dikey penceresinde **Ekle**’yi seçin.
4. **OMA-URI Ayarı Ekle veya Düzenle** iletişim kutusunda aşağıdaki bilgileri belirtin:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Cihazda çalıştırılması engellenen uygulamalar listesi için:

- **Ad** - **PreventStartPackages** girin.
- **Açıklama** - 'Çalıştırılması engellenen uygulamalar listesi' gibi isteğe bağlı bir açıklama girin.
-   **Veri türü** - Açılan listeden **Dize**’yi seçin.
-   **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** girin.
-   **Değer** - İzin vermek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Diğer tüm uygulamaları hariç tutarak, kullanıcıların Google Play mağazasından yüklemesine izin verilen uygulamaların listesi için:
- **Ad** - **AllowInstallPackages** girin.
- **Açıklama** - 'Kullanıcıların Google Play mağazasından yükleyebilecekleri uygulamaların listesi' gibi isteğe bağlı bir açıklama girin.
- **Veri türü** - Açılan listeden **Dize**’yi seçin.
- **OMA-URI** - **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** girin.
- **Değer** - İzin vermek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

4. **Tamam**’a tıklayın ve ardından **Profil Oluştur** dikey penceresinde **Oluştur**’u seçin.

>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

Hedeflenen her cihazın bir sonraki girişinde, uygulama ayarları uygulanır.


<!---## Assign the custom profile--->
