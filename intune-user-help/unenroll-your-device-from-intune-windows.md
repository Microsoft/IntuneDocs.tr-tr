---
title: Windows cihazınızı Intune yönetiminden kaldırma
description: Windows cihazınızı Intune yönetiminden nasıl kaldıracağınızı açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 018bda65-7238-41f5-b92a-e5f67b7fe085
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: e64911ea9b1b1d3c619a82eac9dc78e4e78a53e9
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72508135"
---
# <a name="remove-your-windows-device-from-management"></a>Windows cihazınızı yönetimden kaldırma

Artık aşağıdakileri yapmak istemediğinizde veya ihtiyaç duymadığınızda kayıtlı bir Windows cihazını Intune yönetiminden kaldırın:  
* İş veya okul cihazınızı kullanın. 
* İş veya okul e-postasına, uygulamasına ya da diğer kaynaklara erişin.

Cihazın kaydını sildikten sonra cihazla okul veya iş kaynaklarına erişemezsiniz. Aşağıdaki Windows cihazlarını yönetimden kaldırabilirsiniz.  
* Windows 10 cihazlar 
* Windows 8.1 bilgisayar
* Windows 8.1 telefon
 
Cihazınızı yönetiminden kaldırdığınızda ne olacağı hakkında daha fazla bilgi için bkz. [Cihazınızı Intune'dan kaldırdığınızda ne olur](what-happens-if-you-unenroll-your-device-from-intune-windows.md).  

## <a name="remove-your-windows-10-device"></a>Windows 10 cihazınızı kaldırma
Bir Windows 10 cihazını yönetimden kaldırmak için aşağıdaki adımları tamamlayın.

### <a name="remove-in-company-portal-app-home-page"></a>Şirket Portalı uygulaması **Giriş** sayfasında kaldırma  

1. Şirket Portalı uygulamasını açın.
2. **Giriş sayfası**'nda **Cihazlarım** bölümüne gidin.
3. Kaldırmak istediğiniz cihazı seçin.
3. Uygulamanın sağ üst köşesinde **Daha fazla** simgesini seçin.
4. **Kaldır**’a tıklayın. 
5. Cihazın kaldırılmasını onaylamak için **Kaldır**'ı seçin.  

### <a name="remove-in-company-portal-app-device-context-menu"></a>Şirket Portalı uygulaması cihaz bağlam menüsünde kaldırma  

1. Şirket Portalı uygulamasını açın ve **Cihazlarım**'a gidin.

    ![Windows için Şirket Portalı uygulaması Giriş sayfasının, Cihazlarım bölümü vurgulanmış olarak örnek ekran görüntüsü.](./media/1809_CheckAccess_Context_Select_Device.png)

2. [Bağlam menüsünü](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus) açmak için cihaza sağ tıklayın veya cihazı basılı tutun.  

3. **Kaldır**’a tıklayın.  

    ![Windows için Şirket Portalı uygulaması Giriş sayfasının örnek ekran görüntüsü. Cihaz bağlam menüsü sayfanın **Cihazlarım** bölümünde görülebilir ve "Yeniden adlandır", "Kaldır" ve "Erişimi denetle" eylemlerini gösterir.](./media/1809_DeviceContextMenu_Windows_CP.png)  

5. Onay kutusunda, iş ve okul kaynaklarınıza erişiminizin nasıl değişebileceği hakkında daha fazla bilgi edinmek için **Daha Fazla Bilgi**'ye tıklayın. Cihazın kaldırılmasını onaylamak için **Kaldır**'ı seçin.   

     ![Windows için Şirket Portalı uygulaması Giriş sayfasının örnek ekran görüntüsü. Yeniden adlandır alanı, cihazın kullanıcının yeni bir ad yazıp Yeniden Adlandır veya İptal'e tıklayabileceği yerin üzerinde görünür.](./media/1808_RemoveDevice_Popup.png)  


### <a name="remove-in-device-settings-app"></a>Cihaz Ayarlar uygulamasında kaldırma
1. Ayarlar uygulamasını açın. 
2. **Hesaplar** > **İşe veya okula erişmeye** gidin.
3. Kaldırmak istediğiniz bağlı hesabı ve ardından **Bağlantıyı kes**’i seçin.
4. Cihazın kaldırılmasını onaylamak için **Evet**’i seçin.

## <a name="remove-your-windows-81-computer"></a>Windows 8.1 bilgisayarınızı kaldırma
Bir Windows 8.1 bilgisayarı Intune’dan kaldırmak için aşağıdaki adımları tamamlayın.

1. **Bilgisayar Ayarları** > **Ağ** > **Çalışma Alanı**’na gidin.
2. **Çalışma Alanına Katılma** altında **Çık**’ı seçin.
3. **Cihaz yönetimini aç** altında **Kapat**’ı seçin.
4. Açılan pencerede **Kapat**’ı seçin.

## <a name="remove-your-windows-81-phone"></a>Windows 8.1 telefonunuzu kaldırma
Bir Windows 8.1 telefonunu Intune'dan kaldırmak için aşağıdaki adımları tamamlayın.

1. **Ayarlar** > **Çalışma Alanı**’na gidin.
2. Kaydını kaldırmak istediğiniz çalışma alanı hesabına dokunun.
3. Ekranın altındaki **Sil** seçeneğine dokunun.
4. **Hesabı sil** iletişim kutusunda **Sil**’e dokunun.  
## <a name="removing-your-personal-information-after-removing-the-company-portal"></a>Şirket Portalı’nı kaldırdıktan sonra kişisel bilgilerinizi kaldırma  

Şirket Portalı’nın Windows cihazınızda depoladığı iki tür veri vardır:

- **Tanılama günlükleri**: Microsoft’un topladığı standart uygulama etkinliği verileri. Bu, Şirket Portalı uygulamasını kaldırdığınızda otomatik olarak silinir. Uygulama etkinlik verileri, uygulamanın ne kadar süre açık kaldığı veya kilitlenip kilitlenmediği gibi verilerdir.
- **Uygulama önbelleği**: Simge ve ayarlar gibi bir uygulamanın çalışması için gereken destek dosyaları.

Depolanan günlükleri ve önbelleği silmek için aşağıdaki adımlardan birini tamamlayın:

* [Şirket Portalı uygulamasını kaldırma](https://support.microsoft.com/help/4028003/windows-10-uninstall-apps-and-programs) 

* Şirket Portalı uygulamasını sıfırlayın. **Ayarlar** uygulamasını açın ve **Uygulamalar** > **Şirket Portalı** > **Gelişmiş seçenekler** > **Sıfırla**’yı seçin. 

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
