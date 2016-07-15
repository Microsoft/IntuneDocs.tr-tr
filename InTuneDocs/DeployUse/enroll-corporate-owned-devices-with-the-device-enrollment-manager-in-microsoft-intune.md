---
title: "Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.sourcegitcommit: 7b0154d73ab540e7543fab9088463ed8b61b45a0
ms.openlocfilehash: 74ff3209d00dee0b5ddd14e107b5544b364d08f7


---


# Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme
Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, 1000 adede kadar cihazı kaydetme izni olan özel bir Intune hesabıdır. Kişisel ("BYOD") cihazlar yerine, cihaz kayıt yöneticisi hesabı kullanılarak, paylaşılan cihazlar olarak kaydedilen cihazları kullanın. Kullanıcılar, örneğin "yerel" e-posta uygulamalarını kullanamayacaktır. Örneğin bir mağaza yöneticisi veya süpervizöre bir cihaz kayıt yöneticisi kullanıcı hesabını atayarak aşağıdakileri yapmasına imkan sağlayabilirsiniz:

-   Intune'a cihaz kaydetme

-   Şirket uygulamalarına erişmek için şirket portalında oturum açma

-   Yazılım yükleme ve kaldırma

-   Şirket verilerine erişimi yapılandırma


**Cihaz kayıt yöneticisi örnek senaryoları:** Bir restoran, garsonlar için satış noktası tabletleri ve mutfak çalışanları için sipariş izleyiciler istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya bir kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi bir cihaz kayıt yöneticisi hesabı oluşturur ve bu hesabı kullanarak şirkete ait cihazları kaydeder. Alternatif olarak, yönetici cihaz kayıt yöneticisi kimlik bilgilerini restoran müdürüne verip cihazları müdürün kaydetmesine ve yönetmesine imkan sağlayabilir.

Yönetici veya müdür, restoran cihazlarına role özel uygulamalar dağıtabilir. Yönetici ayrıca Intune konsolunda cihazı seçebilir ve yönetim konsolu ile mobil cihaz yönetiminden devre dışı bırakabilir.

Cihaz kayıt yöneticisi hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:
  - Belirli bir kullanıcı yoktur dolayısıyla tüm cihazlar "kullanıcısızdır"; bu nedenle, örneğin VPN cihaz uygulamalarına yine veri erişimi sağlasa da, e-postaya veya şirket verilerine erişilmez
  - Koşullu erişim yoktur çünkü bunlar kullanıcı başına senaryolardır
  - Şirket Portalından cihazlar sıfırlanamaz
  - Şirket Portalı uygulaması veya web sitesinde yalnızca yerel cihaz görünür
  - Uygulama yönetimi için kullanıcı başına Apple Kimliği gereksinimlerinden dolayı Apple Volume Purchase Program (VPP) uygulamaları yoktur
  - Aynı zamanda Apple Configurator veya Apple cihaz kaydı programına (iOS cihazları) kaydedilemez

> [!NOTE]
> Şirket uygulamalarını cihaz kayıt yöneticisiyle yönetilen cihazlara dağıtmak için Şirket Portalı uygulamasını **Gerekli Yükleme** olarak cihaz kayıt yöneticisinin kullanıcı hesabına dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.

## Cihaz kayıt yöneticisi hesapları oluşturma
Cihaz kayıt yöneticisi hesapları, şirkete ait çok sayıda cihazı kaydetme izni olan kullanıcı hesaplarıdır. Yalnızca Intune konsolundaki kullanıcılar cihaz kayıt yöneticileri olabilir.

#### Intune'a cihaz kayıt yöneticisi ekleme

1.  [Microsoft Intune hesap portalına](http://go.microsoft.com/fwlink/?LinkId=698854) gidin ve yönetici hesabınızda oturum açın.

2.  **Kullanıcı ekle**’yi seçin.

3.  Bir cihaz kayıt yöneticisi olacak kullanıcı hesabının listelendiğini onaylayın. Aksi durumda, **Yeni** 'yi seçerek ve Kullanıcı ekle işlemlerini tamamlayarak kullanıcıyı ekleyin. Hizmet'e erişen her bir kullanıcı için bir abonelik lisansı gereklidir ve *cihaz kayıt yöneticisi* bir Intune yöneticisi olamaz. Bu özelliği kullanmadan önce daha fazla lisans eklemenizin gerekli olup olmadığını belirleyin.

4.   [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) yönetici hesabınızla oturum açın.

5.  Gezinme bölmesinde, **Yönetici**'yi seçin, **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. Cihaz Kayıt Yöneticileri sayfası açılır.

6.  **Ekle...**’yi seçin.  **Cihaz Kayıt Yöneticisi Ekle** iletişim kutusu açılır.

7.  Intune hesabının **Kullanıcı Kimliği**'ni girin ve ardından **Tamam**'ı seçin. Cihaz kayıt yöneticisi olan kullanıcı Intune yöneticisi olamaz.

8.  Cihaz kayıt yöneticisi artık şirket portalında BYOD senaryosu için son kullanıcıların kendi cihazlarını kaydetmek için kullandığı yordamın aynısını kullanarak mobil cihazları kaydedebilirsiniz.

## Delete a device enrollment manager from Intune

1.  [Microsoft Intune yönetici portalında](http://manage.microsoft.com) yönetici hesabınızla oturum açın.

2.  Gezinme bölmesinde, **Yönetici**'yi seçin ve **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. Cihaz Kayıt Yöneticileri sayfası açılır.

3.  Silmek istediğiniz cihaz kayıt yöneticisi **Kullanıcı** 'yı silin ve ardından **Sil**'i seçin. Bu kullanıcı Intune'dan silinmez ve bu kullanıcının yönettiği cihazlar Intune'da kayıtlı kalır. Bir cihaz kayıt yöneticisini silme, bu kullanıcının Intune'a daha fazla cihaz kaydetmesini engeller.

4.  Cihaz kayıt yöneticisini silmek istediğinizi onaylamak için **Evet**’i seçin.

Bir cihaz kayıt yöneticisinin silinmesi, kaydedilen cihazları etkilemez. Bir cihaz kayıt yöneticisi silindiğinde:

-   Kaydedilen hiçbir cihaz etkilenmez

-   Kaydedilen cihazlar tam olarak yönetilmeye devam eder.

-   Silinen cihaz kayıt yöneticisinin kimlik bilgileri, şirket portalında oturum açıp uygulama erişmek için geçerli kalır

-   Silinen cihaz kayıt yöneticisi hesabının kimlik bilgileri yine cihazları temizleyemez veya kullanımdan kaldıramaz

-   Silinen cihaz kayıt yöneticisinin hesabı ile kayıtlı cihazlar arasındaki ilişkisi devam eder, ancak başka bir cihaz kaydedilemez


<!--HONumber=Jul16_HO2-->


