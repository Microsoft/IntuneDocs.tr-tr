---
title: "Intune ile iOS cihazınızı telekomünikasyon gider yönetimine kaydetme"
description: "Bir iOS cihazının telekom gider yönetimine nasıl kaydedileceğini öğrenin."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope: User help
ROBOTS: 
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a71b8d1a100100e204eb7e90ba0ab00573ffc5c6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a>iOS cihazınızı telekomünikasyon gider yönetimine kaydetme

Kuruluşunuz, veri ve ses planlarının kabul edilebilir sınırlar içinde kullanıldığından emin olmak için telekomünikasyon gider yönetimi yazılımı kullanıyor olabilir. Cihazınızı kaydetmeyi tamamladıktan sonra, bu cihaz için en uygun kategoriyi seçmeniz istenir.

  ![Bir iOS cihazında "cihaz için en uygun kategoriyi seçme" ekranının ekran görüntüsü. Kurumsal veya kişisel kayıt seçimi gösterilmektedir.](./media/ios-enroll-10-tem-select-best-category.png)

Uygun seçeneği belirlediğinizde App Store’dan [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) uygulamasını yüklemek için bir bildirim alırsınız. Datalert uygulaması kuruluşunuzun veri kullanımını ölçmesine yöneliktir. Kuruluşunuz Microsoft iş veya okul kayıt seçeneğini yapılandırmışsa, iş veya okul hesabınızla oturum açmanız gerekir. Bu etkinleştirilmemişse, telefon numaranız gibi bilgiler sağlamanız ve Datalert hizmetine uygulamadan kaydolmak için bir kod kullanarak cihazınızı doğrulamanız gerekir.

  ![Datalert uygulamasının veri planınızdan en iyi şekilde faydalanmanızı nasıl sağlayacağına ilişkin kısa bir açıklamadan sonra sonraki ekrana geçmenizi belirten Datalert uygulaması hoş geldiniz ekranının ekran görüntüsü.](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a>Microsoft iş veya okul hesabınızı kullanarak Datalert’e kaydolma

> [!NOTE]
> Bu yolla kayıt olmak için telefonunuzda [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) uygulamasının yüklü ve etkin olması gerekir.

1. __Microsoft hesabı ile kaydol__’u seçin.

  ![Bir Microsoft Office 365 hesabı ve Intune aboneliğiniz olduğunda ekranın üst kısmında telefon numarası alanı ve alt kısmında "Microsoft hesabı ile kaydol" seçenekleri sunan Datalert uygulamasının Ayarlar ekranının görüntüsü.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. __"Datalert" "Authenticator"ı açmak istiyor__ şeklinde bir bildirim alırsınız. __Aç__'ı seçin.

  ![Datalert uygulamasının isteği üzerine kullanıcıdan Authenticator uygulamasını açmasını isteyen açılır pencerenin görüntüsü.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. __Microsoft okul veya iş hesabınızla__ oturum açın. Datalert kurulumu birkaç dakika çalışıp tamamlanmalıdır. Tamamlandığında __Son__’a dokunun.

## <a name="enroll-into-datalert-using-your-phone-number"></a>Telefon numaranızı kullanarak Datalert’e kaydolma

1. Cihazınızın telefon numarasını belirtin.

  ![Datalert uygulamasında telefon numarası istenen ekran görüntüsü.](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. Ardından SMS iletisi aracılığıyla doğrulama kodu alırsınız. Kodu sağlayın ve __Tamam__’a dokunun.

  ![Datalert uygulamasında SMS doğrulama kodu istenen ekran görüntüsü.](./media/ios-enroll-13-tem-datalert-sms.png)

3. Doğrulama kodunu sağladıktan sonra Datalert kurulumu tamamlanır. __Son__’a dokunmanızla birlikte verilerinizi Datalert uygulamasından izlemeniz mümkün olacaktır.

  ![Datalert uygulamasının bugünün veri kullanımını izleme görüntüsü.](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

Kaydolduktan sonra, veri kullanımınızı Datalert uygulamasında görmeye başlarsınız.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.
