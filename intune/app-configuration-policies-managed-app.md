---
title: "Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme | Microsoft Docs"
titlesuffix: Azure portal
description: "Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkelerini kullanmayı öğrenin."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 750ce7dbb0dccf08757e076826e2d3650b6e6ab5
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune App SDK’sını destekleyen yönetilen uygulamalarla uygulama yapılandırma ilkelerini kayıtlı olmayan cihazlarda da kullanabilirsiniz. 

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar** iş yükünü seçin.
4. **Yönet** grubunda, **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**  
      Azure portalında görünecek profil adı.
    - **Açıklama**  
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**  
      **Uygulamaları yönet**’i seçin.
6. Yapılandıracağınız uygulamayı seçmek için **İlişkili uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş uygulamalar listesinden uygulamayı seçin.
7. Uygulama tarafından desteklenen her bir yapılandırma ayarı için, **Ad** ve **Değer** yazıp üç nokta işaretine (**…**) tıklayın.  
    Bir yapılandırmayı silmek için, üç nokta işaretine (**…**) tıklayıp **Sil**’i seçin.  
    Intune Uygulama SDK’sı özellikli uygulamalar, anahtar-değer çiftlerinde yapılandırmaları destekler. Hangi anahtar-değer yapılandırmalarının desteklendiğini öğrenmek için her bir uygulamanın belgelerine bakın.  
    Ayrıca, uygulama tarafından oluşturulan verilerle dinamik olarak doldurulacak belirteçler kullanabilirsiniz.

## <a name="configuration-values-using-tokens"></a>Belirteç kullanan yapılandırmalar

Bazı belirteçler Intune tarafından oluşturularak yönetilen uygulamaya gönderilebilir. Örneğin uygulama yapılandırmanız bir e-posta ayarı kullanabiliyorsa, bir belirteç kullanarak dinamik bir e-posta ekleyebilirsiniz. **Ad** alanına uygulama tarafından beklenen adı yazıp **Değer** alanına `\{\{mail\}\}` yazın.

Intune yapılandırma ayarlarında aşağıdaki belirteç türlerini destekler:

- \{\{userprincipalname\}\} - (Örnek: **John@contoso.com**)
- \{\{mail\}\} - (Örnek: **John@contoso.com**)
- \{\{partialupn\}\} - (Örnek: **John**)
- \{\{accountid\}\} - (Örnek: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Örnek: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Örnek: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Örnek: **John Doe**)
- \{\{PrimarySMTPAddress\}\} - (Örnek: testuser@ad.domain.com) 


> [!Note]  
> \{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

## <a name="next-steps"></a>Sonraki adımlar

Normal yollarla, uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.