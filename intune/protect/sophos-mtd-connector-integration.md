---
title: Intune ile Sophos Mobile tümleştirmesini ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Sophos Mobile çözümünü ayarlama.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0802148884363b9b1bb83cb07824accb7abee66
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508905"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Sophos Mobile 'ı Intune ile tümleştirme  

Sophos Mobile Threat Defense çözümünü Intune ile bütünleştirmek için aşağıdaki adımları izleyin.  

## <a name="before-you-begin"></a>Başlamadan önce  

Sophos Mobile 'ı Intune ile tümleştirme işlemine başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:  
- Microsoft Intune aboneliği  
- Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:  
  - Oturum açma ve kullanıcı profilini okuma  
  - Oturum açmış kullanıcı olarak dizine erişim  
  - Dizin verilerini okuma  
  - Intune’a cihaz bilgilerini gönderme  
- Sophos Mobile Yönetici konsoluna erişmek için yönetici kimlik bilgileri.  


### <a name="sophos-mobile-app-authorization"></a>Sophos mobil uygulama yetkilendirmesi  
  
Sophos mobil uygulama yetkilendirme işlemi aşağıdaki gibidir:  
- Sophos Mobile hizmetinin cihaz sistem durumu ile ilgili bilgileri Intune 'a geri iletmesini sağlar.  
- Sophos Mobile, cihazının veritabanını doldurmak için Azure AD kayıt grubu üyeliğiyle eşitlenir.  
- Sophos Mobile yönetici konsolunun Azure AD çoklu oturum açma (SSO) kullanmasına izin verin.  
- Sophos Mobile uygulamasının Azure AD SSO kullanarak oturum açmasını sağlar.  


## <a name="to-set-up-sophos-mobile-integration"></a>Sophos Mobile tümleştirmesini ayarlamak için  

1. [Azure Portal]( https://portal.azure.com/)oturum açın, **Intune** > **cihaz uyumluluğu** > **Mobil tehdit savunması** > ve **Ekle**' yi seçin.  
2. **Bağlayıcı Ekle** sayfasında, açılan menüyü kullanın ve **Sophos**' ı seçin. Sonra **Oluştur**' u seçin.  
3. *Sophos yönetici konsolunu açmak*için bağlantıyı seçin.  
4. Sophos kimlik bilgilerinizle, [Sophos yönetici konsolunda](https://central.sophos.com/) oturum açın.  
5. **Mobil** > **ayarları** > **Kurulum** > **Sophos Setup**' a gidin.  
6. **Sophos kurulum** sayfasında, **Intune MTD** sekmesini seçin.  
   ![Sophos Setup @ no__t-1 
 
7. **Bağla**' yı seçin ve ardından **Evet**' i seçin. Sophos, Intune 'a bağlanır ve Intune aboneliğinizde oturum açmanızı gerektirir. 
8. Microsoft Intune kimlik doğrulaması penceresinde, Intune kimlik bilgilerinizi girin ve *Sophos Mobile Iş parçacığı savunması*için Izin Isteğini **kabul edin** .  
   ![ıntune kimlik doğrulaması @ no__t-1

9. **Sophos kurulum** sayfasında, Intune yapılandırmasını gerçekleştirmek için **Kaydet** ' i seçin:  
   ![Kaydet Sophos Setup @ no__t-1  

1. **Başarılı Tümleştirme** iletisi göründüğünde tümleştirme tamamlanmıştır.  
1. Intune konsolunda, Sophos artık kullanılabilir.  


## <a name="next-steps"></a>Sonraki Adımlar  
[Sophos istemci uygulamalarını yapılandırma](mtd-apps-ios-app-configuration-policy-add-assign.md)
