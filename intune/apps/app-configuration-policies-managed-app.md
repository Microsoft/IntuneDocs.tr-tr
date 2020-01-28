---
title: Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri
titleSuffix: Microsoft Intune
description: Cihaz kaydı olmadan yönetilen uygulamalar için ilkeleri yapılandırmayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06c1119b474d82c4d00db3276179b962ff5b5a44
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755570"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune App SDK’sını destekleyen yönetilen uygulamalarla uygulama yapılandırma ilkelerini, kayıtlı olmayan cihazlarda dahi kullanabilirsiniz. 

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2.  > **yönetilen uygulamalar** **eklemek** > **uygulama yapılandırma ilkeleri** > **uygulamalar** ' ı seçin.
3. **Temel bilgiler** sayfasında, aşağıdaki ayrıntıları ayarlayın:
    - **Ad**: Azure Portal görünecek profilin adı.
    - **Açıklama**: Azure Portal görüntülenecek profil açıklaması.
    - **Cihaz kayıt türü**: yönetilen uygulamalar seçilidir.
4. Yapılandırmak istediğiniz uygulamayı seçmek için **ortak uygulamaları seçin** ya da **özel uygulamalar** ' ı seçin. Onayladığınız ve Intune ile eşitlenmiş uygulamalar listesinden uygulamayı seçin.
5. **İleri** ' ye tıklayarak **Ayarlar** sayfasını görüntüleyin.
6. Uygulamanın desteklediği her yapılandırma ayarı için, **adı** ve **değeri**yazın. 

   Intune Uygulama SDK’sı özellikli uygulamalar, anahtar/değer çiftlerinde yapılandırmaları destekler. Hangi anahtar-değer yapılandırmalarının desteklendiğini öğrenmek için uygulamaların kendi belgelerine bakın. Uygulama tarafından oluşturulan verilerle dinamik olarak doldurulacak belirteçler kullanabileceğinizi unutmayın. Daha fazla bilgi için bkz. [belirteçleri kullanmak Için yapılandırma değerleri](~/apps/app-configuration-policies-managed-app.md#configuration-values-for-using-tokens). iOS için Outlook uygulama yapılandırma ilke ayarları hakkında daha fazla bilgi için bkz. [Microsoft Intune ile iOS için Outlook uygulama yapılandırması](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

    Bir yapılandırmayı silmek için üç nokta simgesini ( **…** ) seçip **Sil**’e tıklayın.  

7. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
8. **Dahil edilecek grupları seç ' e**tıklayın.
9. **Dahil edilecek grupları seçin** bölmesinde bir grup seçin ve **Seç**' e tıklayın.
10. İlgili bölmeyi görüntülemek için **Dışlanacak grupları seçin**’e tıklayın.
11. Dışlamak istediğiniz grupları seçin ve **Seç**’e tıklayın.

    >[!NOTE]
    >Bir grup eklerken, herhangi bir atama türü için başka bir grup önceden dahil edilmişse bu grup, diğer dahil etme atama türleri için önceden seçili ve değiştirilemez bir biçimde görüntülenir. Dolayısıyla bu grup zaten kullanılmıştır ve dışlanmış bir grup olarak kullanılamaz.

12. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin.
13. Uygulama yapılandırma ilkesini Intune 'a eklemek için **Oluştur** ' a tıklayın.

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
