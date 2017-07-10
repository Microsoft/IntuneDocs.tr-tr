---
title: "Apple Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme"
titleSuffix: Intune on Azure
description: "Apple Configurator'ı şirkete ait iOS cihazlarını doğrudan kayıtla kaydetmek için kullanmayı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd856cc3c9d11d1079c6092025200059f0ace437
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>Apple Configurator ve doğrudan kayıt ile iOS cihazlarını kaydetme 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, **kullanıcı benzeşimi yok** ayarına sahip cihazlar içindir ve kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanız gerekir.

>[!NOTE]
>Bu kayıt yöntemi, [cihaz kaydı yöneticisi](device-enrollment-manager-enroll.md) yöntemiyle birlikte kullanılamaz.

iOS cihazlarını doğrudan kaydederken, cihazın seri numarasını almadan kayıt işlemini yapabilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu kılavuz bir Mac bilgisayarda Apple Configurator 2.0 kullandığınızı varsayar.

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](enrollment-method-choose-ios.md) başlığı altında açıklanır.


## <a name="prerequisites"></a>Önkoşullar

iOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](custom-domain-name-configure.md)
- [MDM Yetkilisini ayarlama](mdm-authority-set.md)
- [Grup oluşturma](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Şirket Portalı’nı yapılandırma](company-portal-app.md)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md)
- iOS cihazlarına fiziksel erişiminizin olduğundan emin olun
- Cihaz seri numaralarına sahip olun (bkz. [iOS seri numarası alma](https://support.apple.com//HT204308))
- USB bağlantı kablolarını hazır bulundurun
- [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)’ın yüklü olduğu bir Mac bilgisayarınızın olduğundan emin olun

## <a name="create-an-apple-configurator-profile-for-devices"></a>Cihazlar için Apple Configurator profili oluşturma

Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımları, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

3. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **AC Profilleri**’ni seçin.

4. **Apple Configurator Kayıt Profilleri** dikey penceresinde **Oluştur**’u seçin.

5. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.

6. Cihazın bir kullanıcıyla ilişkili olmadığından emin olmak için **Kullanıcı Benzeşimi**’nde **Kullanıcı benzeşimi olmadan kaydet**’i seçin. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

7. Profili kaydetmek için **Oluştur**’u seçin.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Profili iOS cihazlarına .mobileconfig olarak dışarı aktarma

1. **Profili Dışarı Aktar** dikey penceresinde, kayıt profilini [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)'a indirerek bağlı bir iOS cihazına doğrudan bir yönetim profili olarak iletin. Bu yöntem, cihazda fabrika sıfırlaması yapmaz.

2. Aşağıdaki adımları izleyerek cihazı Apple Configurator ile hazırlayın.

   a. Mac bilgisayarda Apple Configurator 2.0'ı açın.

   b. iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. Fotoğraflar’ı, iTunes’u ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.

   c. Apple Configurator’da, bağlı iOS cihazını ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.

   d. Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir. Cihaz Denetimsiz ise, yüklemenin cihazda kabul edilmesi gerekir.

3. Profili iOS cihazına yüklemek için aşağıdaki adımları kullanın. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır. Kayıt için uygulama dağıtımları gerekiyorsa, uygulama dağıtımları App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektireceğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.

   a. iOS cihazının kilidini açın.

   b. **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’yi seçin.

   c. Gerekirse, Cihaz Geçiş Kodu veya Apple Kimliği sağlayın.

   d. **Uyarı**’yı kabul edin ve **Yükle**’yi seçin.

   e. **Uzak Uyarı**’yı kabul edin ve **Güven**’i seçin.

   f. **Profil Yüklendi** kutusu profilin Yüklü olduğunu doğruladığında **Bitti**’yi seçin.

4. iOS cihazında **Ayarlar**’ı açın ve **Genel** > **Cihaz Yönetimi** > **Yönetim Profili**’ne gidin. Profil yüklemesinin listelendiğini onaylayın, iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakika kadar sürebilir.

5. Cihazları dağıtın. iOS cihazı Intune’a kaydedilmiştir ve yönetilmektedir.
