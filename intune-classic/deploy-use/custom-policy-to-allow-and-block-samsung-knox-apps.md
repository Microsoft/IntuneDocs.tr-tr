---
title: KNOX için izin verilen ve engellenen uygulamalar
description: KNOX için izin verilen ve engellenen uygulamaların listesini oluşturmaya yönelik özel profil.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 11/02/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a47e1388f640f96c2650e284ae0a5311fd816ba7
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Özel ilkeler kullanarak Samsung KNOX Standard cihazlar için uygulamalara izin verme veya bunları engelleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altındaki yordamları kullanarak, aşağıdakilerden birini oluşturan bir Microsoft Intune özel ilkesi oluşturun:

- Cihazda çalışması engellenmiş uygulamaların listesi. İlke uygulandığı sırada zaten yüklenmiş durumda olsalar bile, bu listede yer alan uygulamaların çalışması engellenir.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Yalnızca listelediğiniz uygulamalar yüklenebilir. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX Standard çalıştıran cihazlar tarafından kullanılabilir.

## <a name="to-create-an-allowed-or-blocked-app-list"></a>izin verilen veya engellenen uygulama listesi oluşturmak için

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **İlke** &gt; **Yapılandırma İlkeleri** &gt; **Ekle**’yi seçin.
2. **Yeni İlke Oluştur** iletişim kutusunda **Android**’i genişletin, **Özel Yapılandırma**’yı seçin ve sonra da **İlke Oluştur**’u seçin.
3. İlke için bir ad ve isteğe bağlı bir açıklama sağlayın, ardından **OMA-URI Ayarları** bölümünde **Ekle**’yi seçin.
4. **OMA-URI Ayarı Ekle veya Düzenle** iletişim kutusunda şunları belirtin: Cihazda çalıştırılması engellenen uygulamalar listesi için:
    
    - **Ayar adı.** **PreventStartPackages** girin.
    - **Ayar açıklaması.** 'Çalıştırılması engellenen uygulamalar listesi' gibi isteğe bağlı bir açıklama girin.
    -   **Veri türü.** Açılan listeden **Dize**’yi seçin.
    -   **OMA-URI.** **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** girin.
    -   **Değer.** Engellemek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

    Diğer tüm uygulamaları hariç tutarak, kullanıcıların Google Play mağazasından yüklemesine izin verilen uygulamaların listesi için:

    - **Ayar adı.** **AllowInstallPackages** girin.
    - **Ayar açıklaması.** 'Kullanıcıların Google Play mağazasından yükleyebilecekleri uygulamaların listesi' gibi isteğe bağlı bir açıklama girin.
    - **Veri türü.** Açılan listeden **Dize**’yi seçin.
    - **OMA-URI.** **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** girin.
    - **Değer.** İzin vermek istediğiniz uygulama paket adlarının listesini girin. Sınırlayıcı olarak **; : ,** veya **|** kullanabilirsiniz. (Örnek: paket1;paket2;)

4. **Tamam**’a ve ardından **İlkeyi Kaydet**’e tıklayın. 

>[!TIP]
> Uygulamanın paket kimliğini, Google Play mağazasında uygulamaya göz atarak bulabilirsiniz. Paket kimliği, uygulanın sayfasının URL’sinde yer alır. Örneğin, Microsoft Word uygulamasının paket kimliği **com.microsoft.office.word**’dür.

Hedeflenen her cihazın bir sonraki girişinde, uygulama ayarları uygulanır.


## <a name="deploy-the-policy"></a>İlkeyi dağıtma

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi seçin ve ardından **Dağıtımı Yönet**’e tıklayın.

2.  **Dağıtımı Yönet** iletişim kutusunda ilkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle** &gt; **Tamam**'a tıklayın.

 
Dağıtılan bir ilkeyi seçtiğinizde, ilkeler listesinin alt bölümünde dağıtım hakkında daha fazla bilgi görüntüleyebilirsiniz.

### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune’daki Android ve Samsung KNOX ilke ayarları](android-policy-settings-in-microsoft-intune.md)
