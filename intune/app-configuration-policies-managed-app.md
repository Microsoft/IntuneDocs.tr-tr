---
title: Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri
titlesuffix: Microsoft Intune
description: Cihaz kaydı olmadan yönetilen uygulamalar için ilkeleri yapılandırmayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9cde71d7c4c23aeb91c1e43469e23a4764e62b5b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238600"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune App SDK’sını destekleyen yönetilen uygulamalarla uygulama yapılandırma ilkelerini, kayıtlı olmayan cihazlarda dahi kullanabilirsiniz. 

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **İstemci uygulamaları** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**  
      Azure portalında görünecek profil adı.
    - **Açıklama**  
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**  
      **Uygulamaları yönet**’i seçin.
6. Seçin **ilişkili uygulama** yapılandırmak için oluşturacağınız uygulamasını seçin. Onayladığınız ve Intune ile eşitlenmiş uygulamalar listesinden uygulamayı seçin.
7. Uygulamanın desteklediği her bir yapılandırma ayarı için **Ad** ve **Değer** yazın ve üç nokta simgesini (**...**) seçin.  
    Bir yapılandırmayı silmek için üç nokta simgesini (**…**) seçip **Sil**’e tıklayın.  
    
Intune Uygulama SDK’sı özellikli uygulamalar, anahtar/değer çiftlerinde yapılandırmaları destekler. Hangi anahtar-değer yapılandırmalarının desteklendiğini öğrenmek için uygulamaların kendi belgelerine bakın. Uygulama tarafından oluşturulan verilerle dinamik olarak doldurulacak belirteçler kullanabileceğinizi unutmayın. iOS için Outlook uygulama yapılandırma ilke ayarları hakkında daha fazla bilgi için bkz. [Microsoft Intune ile iOS için Outlook uygulama yapılandırması](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Belirteç kullanmak için yapılandırma değerleri

Intune bazı belirteçleri oluşturabilir ve yönetilen uygulamaya gönderebilir. Örneğin uygulama yapılandırmanız bir e-posta ayarı kullanabiliyorsa, bir belirteç kullanarak dinamik bir e-posta ekleyebilirsiniz. **Ad** alanına uygulama tarafından beklenen adı yazıp **Değer** alanına `\{\{mail\}\}` yazın.

Intune, yapılandırma ayarlarında aşağıdaki belirteç türlerini destekler. Diğer özel anahtar/değer çiftleri desteklenmez.

- \{\{userprincipalname\}\}: örneğin John@contoso.com
- \{\{mail\}\}: örneğin John@contoso.com
- \{\{partialupn\}\}: örneğin John
- \{\{accountid\}\}: örneğin fc0dc142-71d8-4b12-bbea-bae2a8514c81
- \{\{userid\}\}: örneğin 3ec2c00f-b125-4519-acf0-302ac3761822
- \{\{username\}\}: örneğin John Doe
- \{\{PrimarySMTPAddress\}\}: örneğin testuser@ad.domain.com


> [!Note]  
> \{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

## <a name="next-steps"></a>Sonraki adımlar

Normal yollarla, uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.
