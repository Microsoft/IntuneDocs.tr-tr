---
title: Cihaz erişimini denetleme | Microsoft Docs
description: Cihazınızın gereksinimleri karşılayıp karşılamadığını, iş ve okul kaynaklarına erişimi olup olmadığını öğrenmek için cihaz erişimini denetleyin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 162891253c63e785e07ae8c46996f40f19472317
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828976"
---
# <a name="check-access-from-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasından erişimi denetleme

Cihazınızın iş veya okul kaynaklarına erişimi olduğunu doğrulayın. 

Kuruluşlar, verilerine yalnızca güvenli ve güvenilir cihazların eriştiğinden emin olmak için &ndash;şifreleme ve parola sınırları gibi&ndash; gereksinimleri zorunlu tutabilir. Yönetilen cihazların kuruluşun kaynaklarına erişebilmesi için bu gereksinimleri karşılaması ve bu durumu koruması gerekir.

**Erişimi denetle** eylemi, cihazınızın ayarlarını ve erişim durumunu değerlendirir. **Cihaz ayrıntıları** sayfasında, tekrar erişim sağlamak için değiştirmeniz gereken ayarlar listelenir. 

Windows için Şirket Portalı uygulamasından erişimi denetlemek için bu makaledeki adımları tamamlayın.  

## <a name="check-access-from-device-details-page"></a>Cihaz ayrıntıları sayfasından erişimi denetleme  
1. Windows için Şirket Portalı uygulamasını açın ve **Cihazlarım**'a gidin.  

    ![Windows için Şirket Portalı uygulaması Giriş sayfasının, Cihazlarım bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Context_Select_Device.png)  
2. Cihaz seçin.  
3. **Cihaz ayrıntıları** sayfasında **Erişimi denetle**’yi seçin. Uygulama, cihazınızı kuruluşunuzun geçerli gereksinimleriyle eşitler ve cihazınızın bunları karşılayıp karşılamadığını denetler. Bu denetim birkaç dakika sürebilir.  

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, Erişimi Denetle düğmesi vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Checking_Status.png) 

4. Durum güncelleştirmesine bakın. Cihazınızın **kuruluşunuzun kaynaklarına erişebildiğini** veya **kuruluşunuzun kaynaklarına erişemediğini** gösterir.  

   ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, Durum bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Device_details_status1.png)  
   
5. Cihazınız kaynaklara erişemiyorsa, sayfanın üst kısmındaki uyarıya gidin. Ayrıntılarını genişletmek için **Daha fazla**’ya tıklayın. Bunları daraltmak için **Daha az**’a tıklayın.  

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, sayfanın üst kısmındaki uyarı vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Uygun olduğunda, ileti ek yardım bağlantılarını ve düzeltme eylemlerini gösterir. Sorun gidermeye hemen başlamak için bu seçeneklerden birini veya daha fazlasını seçin. &ndash;Aşağıda açıklanan&ndash; çözümleme, eşitleme ve başvuru eylemleri, yalnızca Şirket Portalı etkilenen cihazlarda kullanıldığında görüntülenir.  

     * **Bu nasıl çözülür** seçeneği, ilgili yardım makalesini (varsa) açar.  
     * **Çözümle** seçeneği sizi cihazınızın ayarlarına yönlendirir.  
     * **Eşitle** seçeneği, kuruluşunuzun gereksinimlerini karşıladığından emin olmak için cihazınızı değerlendirir.  
     * **BT’ye başvur** seçeneği sizi BT ekibinizin iletişim bilgilerine yönlendirir.   
 
6. Ayarları güncelleştirdikten sonra cihazınızın durumunu onaylamak için **Erişimi denetle**’ye tıklayın.  

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, Durum bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Device_details_status1.png)  

## <a name="check-access-from-device-context-menu"></a>Cihaz bağlam menüsünden erişimi denetleme  
1. Windows için Şirket Portalı uygulamasını açın ve **Cihazlarım**'a gidin.  

    ![Windows için Şirket Portalı uygulaması Giriş sayfasının, Cihazlarım bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Context_Select_Device.png)  

2. [Bağlam menüsünü](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus) açmak için cihaza sağ tıklayın veya cihazı basılı tutun.  

    ![Windows için Şirket Portalı uygulaması Giriş sayfasının örnek ekran görüntüsü. Cihaz bağlam menüsü sayfanın **Cihazlarım** bölümünde görülebilir ve "Yeniden adlandır", "Kaldır" ve "Erişimi denetle" eylemlerini gösterir.](./media/1809_DeviceContextMenu_Windows_CP.png)  
3. **Erişimi denetle**’yi seçin. Uygulama, cihazınızı kuruluşunuzun geçerli gereksinimleriyle eşitler ve cihazınızın bunları karşılayıp karşılamadığını denetler. Bu denetim birkaç dakika sürebilir.  
 
4. Cihazın altında, **kuruluşun kaynaklarına erişebildiğini** veya **kuruluşun kaynaklarına erişemediğini** gösteren bir ileti gösterilir. 

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, Durum bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Context_Menu_Alert2.png) 

5. Cihazınız kaynaklara erişemiyorsa, cihazı seçin.  
6. **Cihaz ayrıntıları** sayfasında, sayfanın üst kısmındaki uyarıya gidin. Ayrıntılarını genişletmek için **Daha fazla**’ya tıklayın. Bunları daraltmak için **Daha az**’a tıklayın.  

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, sayfanın üst kısmındaki uyarı vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Uygun olduğunda, ileti ek yardım bağlantılarını ve düzeltme eylemlerini gösterir. Sorun gidermeye hemen başlamak için bu seçeneklerden birini veya daha fazlasını seçin. &ndash;Aşağıda açıklanan&ndash; çözümleme, eşitleme ve başvuru eylemleri, yalnızca Şirket Portalı etkilenen cihazlarda kullanıldığında görüntülenir.  

     * **Bu nasıl çözülür** seçeneği, ilgili yardım makalesini (varsa) açar.  
     * **Çözümle** seçeneği sizi cihazınızın ayarlarına yönlendirir.  
     * **Eşitle** seçeneği, kuruluşunuzun gereksinimlerini karşıladığından emin olmak için cihazınızı değerlendirir.  
     * **BT’ye başvur** seçeneği sizi BT ekibinizin iletişim bilgilerine yönlendirir.    

7. Ayarlarını güncelleştirdikten sonra sayfanın altındaki **Erişimi denetle**’ye tıklayın.  

    ![Windows için Şirket Portalı uygulaması Cihaz ayrıntıları sayfasının, Erişimi denetle eylemi vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Device_details_button.png) 


Daha fazla yardıma mı ihtiyacınız var? Şirketinizin destek biriminin iletişim bilgilerini [Şirket Portalı web sitesinde](https://go.microsoft.com/fwlink/?linkid=2010980) bulabilirsiniz.
