---
title: Intune ile Sophos Mobile tümleştirmesini ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek Intune Sophos mobil çözüm ayarlama yapma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ec60a618280caf6a5b7ef242c192cc64b5d839de
ms.sourcegitcommit: 84c79ceea27f7411528defc5ee8ba35ae2bf473c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67511914"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Sophos Mobile'ı Intune ile tümleştirme  

Sophos Mobile Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.  

## <a name="before-you-begin"></a>Başlamadan önce  

Sophos mobil Intune ile tümleştirme sürecini başlatmadan önce aşağıdakilere sahip olduğunuzdan emin olun:  
- Microsoft Intune aboneliği  
- Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:  
  - Oturum açma ve kullanıcı profilini okuma  
  - Oturum açmış kullanıcı olarak dizine erişim  
  - Dizin verilerini okuma  
  - Intune’a cihaz bilgilerini gönderme  
- Sophos Mobil Yönetim konsoluna erişmek için yönetici kimlik bilgileri.  


### <a name="sophos-mobile-app-authorization"></a>Sophos mobil uygulama yetkilendirme  
  
Sophos mobil uygulama Yetkilendirme işlemi aşağıdaki gibidir:  
- Intune'a cihazın sistem durumuyla ilgili bilgi iletme izni Sophos mobil hizmeti sağlar.  
- Sophos Mobile, cihazının veritabanını doldurmak için Azure AD kayıt grubu üyeliğiyle ile eşitler.  
- Sophos mobil, Azure AD çoklu oturum açma (SSO) kullanmak Yönetim Konsolu sağlar.  
- Azure AD SSO kullanarak oturum açmanız Sophos mobil uygulama izin verin.  


## <a name="to-set-up-sophos-mobile-integration"></a>Sophos Mobile tümleştirmesini ayarlamak için  

1. Oturum [Azure portalında]( https://portal.azure.com/)gidin **Intune** > **cihaz uyumluluğu** > **Mobile Threat Defense** > seçip **Ekle**.  
2. Üzerinde **ekleme bağlayıcı** sayfasında, açılan listeyi kullanın ve seçin **Sophos**. Ve ardından **Oluştur**.  
3. Bağlantıyı seçin *Sophos yönetici konsolunu Aç*.  
4. Oturum [Sophos Yönetici Konsolu](https://central.sophos.com/) Sophos kimlik bilgilerinizle.  
5. Git **mobil** > **ayarları** > **Kurulum** > **Sophos Kurulum**.  
6. Üzerinde **Sophos Kurulum** sayfasında **Intune MTD** sekmesi.  
   ![Sophos Kurulumu](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Seçin **bağlama**ve ardından **Evet**. Sophos Intune'a bağlanır ve Intune aboneliğiniz için oturum açmanız gerekir. 
8. Microsoft Intune kimlik doğrulaması penceresinde, Intune kimlik bilgilerinizi girin ve **kabul** için izinlere ilişkin istek *Sophos mobil iş parçacığı savunması*.  
   ![Intune kimlik doğrulaması](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. Üzerinde **Sophos Kurulum** sayfasında **Kaydet** Intune yapılandırmasını tamamlamak için:  
   ![Sophos Kurulum Kaydet](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. **Başarılı Tümleştirme** iletisi göründüğünde tümleştirme tamamlanmıştır.  
1. Intune konsolunda Sophos artık kullanılabilir.  


## <a name="next-steps"></a>Sonraki Adımlar  
[Sophos istemci uygulamalarını yapılandırın](mtd-apps-ios-app-configuration-policy-add-assign.md)
