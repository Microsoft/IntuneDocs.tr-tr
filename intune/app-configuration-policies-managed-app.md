---
title: "Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri"
titlesuffix: Microsoft Intune
description: "Cihaz kaydı olmadan yönetilen uygulamalar için ilkeleri yapılandırmayı öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 384804029ecbf403f526144136dc187212e6cf4a
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune App SDK’sını destekleyen yönetilen uygulamalarla uygulama yapılandırma ilkelerini, kayıtlı olmayan cihazlarda dahi kullanabilirsiniz. 

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Mobil uygulamalar** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**  
      Azure portalında görünecek profil adı.
    - **Açıklama**  
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**  
      **Uygulamaları yönet**’i seçin.
6. Yapılandıracağınız uygulamayı seçmek için **İlişkili uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş uygulamalar listesinden uygulamayı seçin.
7. Uygulamanın desteklediği her bir yapılandırma ayarı için **Ad** ve **Değer** yazın ve üç nokta simgesini (**...**) seçin.  
    Bir yapılandırmayı silmek için üç nokta simgesini (**…**) seçip **Sil**’e tıklayın.  
    
Intune Uygulama SDK’sı özellikli uygulamalar, anahtar/değer çiftlerinde yapılandırmaları destekler. Hangi anahtar-değer yapılandırmalarının desteklendiğini öğrenmek için uygulamaların kendi belgelerine bakın. Uygulama tarafından oluşturulan verilerle dinamik olarak doldurulacak belirteçler kullanabileceğinizi unutmayın. iOS için Outlook uygulama yapılandırma ilke ayarları hakkında daha fazla bilgi için bkz. [Microsoft Intune ile iOS için Outlook uygulama yapılandırması](https://technet.microsoft.com/en-us/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Belirteç kullanmak için yapılandırma değerleri

Intune bazı belirteçleri oluşturabilir ve yönetilen uygulamaya gönderebilir. Örneğin uygulama yapılandırmanız bir e-posta ayarı kullanabiliyorsa, bir belirteç kullanarak dinamik bir e-posta ekleyebilirsiniz. **Ad** alanına uygulama tarafından beklenen adı yazıp **Değer** alanına `\{\{mail\}\}` yazın.

Intune yapılandırma ayarlarında aşağıdaki belirteç türlerini destekler:

- \{\{userprincipalname\}\}—örneğin, **John@contoso.com**
- \{\{mail\}\}—örneğin, **John@contoso.com**
- \{\{partialupn\}\}—örneğin, **John**
- \{\{accountid\}\}—örneğin, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\}—örneğin, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—örneğin, **John Doe**
- \{\{PrimarySMTPAddress\}\}—örneğin, **testuser@ad.domain.com** 


> [!Note]  
> \{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

## <a name="next-steps"></a>Sonraki adımlar

Normal yollarla, uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.
