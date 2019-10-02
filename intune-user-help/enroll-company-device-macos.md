---
title: Kuruluşunuzda sağlanmış macOS cihazınızı yönetime kaydetme | Microsoft Docs
description: Kuruluşunuz tarafından satın alınan ve sunulan bir macOS cihazının Intune 'a nasıl kaydedileceğini açıklar.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f2e2ecc79cd24a68c1a5642f64474f2d31217bd7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721028"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Kuruluşunuzda sağlanmış macOS cihazınızı yönetime kaydetme

Yeni macOS cihazınızı Intune 'da yönetilen şekilde nasıl alabileceğinizi öğrenin.  

Çalışmanız veya okulunuz tarafından sunulan cihazlar, genellikle bunları almadan önce önceden yapılandırılmıştır. Kuruluşunuz, önceden bu ayarları açtıktan sonra, ilk kez oturum açtıktan sonra cihazınıza gönderir. Cihazınız kurulumu tamamladıktan sonra, iş veya okul kaynaklarınıza erişim elde edersiniz.

Yönetim Kurulumu 'nu başlatmak için cihazınızda güç açın ve iş veya okul kimlik bilgilerinizle oturum açın. Bu makalenin geri kalanında, Kurulum Yardımcısı ' na kılavuzluk ettiğiniz için göreceğiniz adımlar ve ekranlar açıklanmaktadır.

## <a name="what-is-apple-dep"></a>Apple DEP nedir?

Kuruluşunuz cihazlarını *Apple aygıt kayıt programı* (DEP) adlı bir şekilde satın almış olabilir. Apple DEP, kuruluşların büyük miktarlarda iOS veya macOS cihazı satın almasını sağlar. Kuruluşlar daha sonra bu cihazları Intune gibi tercih edilen mobil cihaz yönetimi sağlayıcıları içinde yapılandırabilir ve yönetebilir. Yöneticiyseniz ve Apple DEP hakkında daha fazla bilgi istiyorsanız bkz. [macOS cihazlarını apple aygıt kayıt programı Ile otomatik olarak kaydetme](https://docs.microsoft.com/intune/enrollment/device-enrollment-program-enroll-macos.md).  

## <a name="get-your-device-managed"></a>Cihazınızın yönetilmesini sağlayın

MacOS cihazınızı yönetime kaydetmek için aşağıdaki adımları tamamlayın. Kuruluş tarafından sağlanmış bir cihaz yerine kendi cihazınızı kullanıyorsanız, [kişisel ve kendi cihazlarını getir](enroll-your-device-in-intune-macos-cp.md)adımlarını izleyin.  

1. MacOS cihazınızda güç.
2. Ülkenizi/bölgenizi seçin ve **devam**' a tıklayın.  

   ![Seçilecek dillerin listesini gösteren macOS cihaz Kurulum Yardımcısı hoş geldiniz ekranının ekran görüntüsü.](./media/macos-dep-welcome-1808.png)
3. Klavye düzeni seçin. Listede, seçtiğiniz ülkeyi/bölgenizi temel alan bir veya daha fazla seçenek gösterilmektedir. Seçtiğiniz ülke/bölgeinizden bağımsız olarak tüm düzen seçeneklerini görmek için **Tümünü göster**' e tıklayın. İşiniz bittiğinde devam ' a tıklayın **.**  

   ![Seçilecek klavye dillerinin bir listesini gösteren macOS cihaz Kurulum Yardımcısı klavye düzeni ekranının ekran görüntüsü, denetlenmeyen bir tümünü göster seçeneği ve geri ve devam düğmesi.](./media/macos-dep-keyboard-1808.png)  
4. Wi-Fi ağınızı seçin. Kuruluma devam etmek için bir internet bağlantınızın olması gerekir. Ağınızı görmüyorsanız veya kablolu ağ üzerinden bağlanmanız gerekiyorsa **diğer ağ seçenekleri**' ne tıklayın. İşiniz bittiğinde **devam**' a tıklayın.  

   ![MacOS cihaz Kurulum Yardımcısı 'nın ekran görüntüsü Wi-Fi ağ ekranınızı seçerek, aralarından seçim yapabileceğiniz kullanılabilir ağların bir listesini gösterir. Ayrıca diğer bir ağ seçenekleri düğmesini, geri düğmesini ve devam düğmesini gösterir.](./media/macos-dep-wifi-1808.png)  
5. Wi-Fi ' a Bağlandıktan sonra, **Uzaktan Yönetim** ekranı görünür. Uzaktan Yönetim, kuruluşunuzun yöneticisinin cihazınızı şirket için gerekli hesaplar, ayarlar, uygulamalar ve ağlarla uzaktan yapılandırmasını sağlar. Cihazınızın nasıl yönetildiğini anlamanıza yardımcı olması için uzaktan yönetim açıklamasını okuyun. Sonra **devam**' a tıklayın.  

   ![MacOS cihazı Kurulum Yardımcısı uzaktan yönetim ekranının ekran görüntüsü, uzaktan yönetimi açıklayan metin ve daha fazla bilgi için belgelere bir bağlantı. Ayrıca bir geri düğmesi gösterir ve devam et düğmesi.](./media/macos-dep-remote-management-1-1808.png)  
6. İstendiğinde, iş veya okul hesabınızla oturum açın. Kimliğiniz doğrulandıktan sonra, cihazınız bir yönetim profili yükler. Profil, kuruluşunuzun kaynaklarına erişiminizi yapılandırır ve sağlar.  
7. Daha sonra kişisel bilgilerin toplandığını tanımlayabilmeniz için Apple Data & Gizlilik simgesi hakkında bilgi edinin. Sonra **devam**' a tıklayın.  

   ![MacOS cihaz Kurulum Yardımcısı verileri & Gizlilik ekranının ekran görüntüsü, iki kişinin gerçekleşmesi ileri bir resmini gösterir ve Apple 'ın kişisel bilgi kullanımını açıklayarak tanımlar. Ayrıca bir geri ve devam düğmesi gösterir.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Cihazınız kaydedildikten sonra, tamamlanacak ek adımlara sahip olabilirsiniz. Gördüğünüz adımlar, kuruluşunuzun kurulum deneyimini nasıl özelleştirmiş olduğuna bağlıdır. Şunları yapmanız gerekebilir:
    * Apple hesabında oturum açın
    * Hüküm ve koşulları kabul etme
    * Bilgisayar hesabı oluşturma
    * Hızlı bir kurulum ile ilerleme
    * Mac 'nizi ayarlama

## <a name="get-the-company-portal-app"></a>Şirket Portalı uygulamayı alın

Cihazınızda macOS için Intune Şirket Portalı uygulamasını indirin. Uygulama, cihazınızı yönetimden izlemenize, eşitlemenizi, eklemenize ve kaldırmanıza ve uygulamaları yüklemenize imkan tanır. Bu adımlar, cihazınızı Şirket Portalı nasıl kaydedeceğinizi de açıklamaktadır.

1. MacOS cihazınızda [https://portal.manage.microsoft.com/EnrollmentRedirect.aspx](https://portal.manage.microsoft.com/EnrollmentRedirect.aspx)' e gidin.
2. İş veya okul hesabınızla Şirket Portalı Web sitesinde oturum açın. 
3. MacOS için Şirket Portalı yükleyicisini indirmek üzere **uygulamayı al** ' a tıklayın.
4. İstendiğinde,. pkg dosyasını açın ve yükleme adımlarını doldurun.
5. Şirket Portalı uygulamasını açın ve iş veya okul hesabınızla oturum açın.
6. Cihazınızı bulun ve **Kaydet**' e tıklayın.
7. **Devam**@no__t ' a tıklayın,-1**bitti**. Cihazınız artık Şirket Portalı uygulamasında kurumsal ve uyumlu bir cihaz olarak görünmelidir.

Hala yardıma mı ihtiyacınız var? Şirketinizin destek birimine başvurun. İletişim bilgileri için [Şirket portalı Web sitesini](https://go.microsoft.com/fwlink/?linkid=2010980)denetleyin.
