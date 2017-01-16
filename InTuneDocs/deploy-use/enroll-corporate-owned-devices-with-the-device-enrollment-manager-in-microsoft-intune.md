---
title: "Cihaz kayıt yöneticisine kaydolma | Microsoft Docs"
description: "Cihaz kayıt yöneticisi (DEM) hesabı, paylaşılan, şirkete ait çok sayıda mobil cihazı tek bir kullanıcı hesabı ile yönetebilir."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 751c6bee73175b8e6ac5ad192f12540520c676c0


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Şirkete ait cihazları Microsoft Intune'daki cihaz kayıt yöneticisi ile kaydetme
Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, en fazla 1.000 cihazı kaydedebilen özel bir Intune hesabıdır. Kaydedilen her cihaz tek bir lisans kullanır. Bu hesap aracılığıyla kaydedilen cihazları, kişisel ("KCG") cihazlar olarak değil paylaşılan cihazlar olarak kullanmanızı öneririz. Kullanıcılar, örneğin "yerel" e-posta uygulamalarını kullanamayacaktır. DEM lisanslaması cihaz başına olup, kullanıcı başına değildir.

Örnek olarak, bir cihaz kayıt yöneticisi kullanıcı hesabını aşağıdakileri yapmaları için bir mağaza yöneticisine veya gözetmene atayabilirsiniz:

-   Cihazları Intune'da kaydedin.

-   Şirket uygulamalarını almak için Şirket Portalı’nda oturum açın.

-   Yazılımı yükleyin ve kaldırın.

-   Şirket verilerine erişim yapılandırın.


**Bir cihaz kayıt yöneticisi senaryosu:** Bir restoran, garsonları için satış noktası tabletleri ve mutfak çalışanları için sipariş monitörleri istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi bir cihaz kayıt yöneticisi hesabı oluşturur ve şirkete ait cihazları bu hesabı kullanarak kaydeder. Alternatif olarak yönetici, cihaz kayıt yöneticisi kimlik bilgilerini bir restoran müdürüne verip cihazları müdürün kaydetmesine ve yönetmesine olanak tanıyabilir.

Yönetici veya müdür, restoran cihazlarına role özgü uygulamalar dağıtabilir. Ayrıca yönetici, cihazı Intune konsolunda seçebilir ve yönetim konsolu ile mobil cihaz yönetiminden kaldırabilir.

Bir cihaz kayıt yöneticisi hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:
  - Belirli bir cihaz "kullanıcısı" yoktur, bu nedenle e-postaya veya şirket verilerine erişim de yoktur. Ancak örneğin VPN yine de verilere erişimi olan cihaz uygulamaları sağlayabilir.
  - Koşullu erişim yoktur çünkü bunlar kullanıcı başına senaryolardır.
  - Bu cihazları Şirket Portalı’ndan sıfırlayamazsınız.
  - Şirket Portalı uygulamasında veya web sitesinde yalnızca yerel cihaz görünür.
  - Uygulama yönetimi için kullanıcı başına Apple ID gereksinimlerinden dolayı Apple Toplu Satın Alma Programı (VPP) uygulamalarını kullanamazsınız.
  - (iOS) Bu cihazlar Apple Configurator veya Apple Aygıt Kayıt Programı’na (DEP) kaydedilemez, ancak DEP veya Apple Configurator ile yönetilen cihazlar kullanıcı benzeşimi olmadan kaydedilebilir.

> [!NOTE]
> Cihaz kayıt yöneticisiyle yönetilen cihazlara şirket uygulaması dağıtmak için Şirket Portalı uygulamasını cihaz kayıt yöneticisinin kullanıcı hesabına **Gerekli Yükleme** olarak dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.

## <a name="create-device-enrollment-manager-accounts"></a>Cihaz kayıt yöneticisi hesapları oluşturma
Cihaz kayıt yöneticisi hesapları, şirkete ait çok sayıda cihazı kaydetme izni olan kullanıcı hesaplarıdır. Yalnızca Intune konsolundaki kullanıcılar cihaz kayıt yöneticileri olabilir.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Intune'a cihaz kayıt yöneticisi ekleme

1.  [Microsoft Intune hesap portalına](http://go.microsoft.com/fwlink/?LinkId=698854) gidin ve yönetici hesabınızda oturum açın.

2.  **Kullanıcı ekle**’yi seçin.

3.  Bir cihaz kayıt yöneticisi olacak kullanıcı hesabının listelendiğini onaylayın. Listelenmiyorsa, **Yeni**’yi seçerek ve **Kullanıcı ekleme** işlemini tamamlayarak kullanıcıyı ekleyin. Hizmete erişen her kullanıcı için bir abonelik lisansı gerekir. Cihaz kayıt yöneticisi bir Intune yöneticisi olamaz. Bu özelliği kullanmadan önce daha fazla lisans eklemenizin gerekli olup olmadığını denetleyin.

4.  [Microsoft Intune yönetim konsolu](http://manage.microsoft.com)’nda yönetici kimlik bilgilerinizle oturum açın.

5.  Gezinti bölmesinde, **Yönetici**'yi seçin, **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. **Cihaz Kayıt Yöneticileri** sayfası açılır.

6.  **Ekle...**’yi seçin. **Cihaz Kayıt Yöneticisi Ekle** iletişim kutusu açılır.

7.  Intune hesabının **Kullanıcı Kimliği**'ni girin ve ardından **Tamam**'ı seçin. Cihaz kayıt yöneticisi bir Intune yöneticisi olamaz.

8.  Cihaz kayıt yöneticisi artık, bir son kullanıcının KCG senaryosu için Şirket Portalı’nda kullandığı yordamı kullanarak mobil cihaz kaydedebilir. Yönetici son kullanıcı, Şirket Portalı uygulamasını yükleyip, kendi DEM kimlik bilgilerini en fazla 1000 cihaz üzerinde kullanarak cihazı kaydedebilir.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Delete a device enrollment manager from Intune

1.  [Microsoft Intune yönetici portalında](http://manage.microsoft.com) yönetici kimlik bilgilerinizle oturum açın.

2.  Gezinti bölmesinde, **Yönetici**'yi seçin, **Yönetici Yönetimi**'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin. **Cihaz Kayıt Yöneticileri** sayfası açılır.

3.  Silmek istediğiniz cihaz kayıt yöneticisi **Kullanıcı** 'yı silin ve ardından **Sil**'i seçin. Bu kullanıcı Intune'dan silinmez ve bu kullanıcının yönettiği cihazlar Intune'da kayıtlı kalır. Bir cihaz kayıt yöneticisini silme, bu kullanıcının Intune'a daha fazla cihaz kaydetmesini engeller.

4.  Cihaz kayıt yöneticisini silmek istediğinizi doğrulamak için **Evet**’i seçin.

Bir cihaz kayıt yöneticisinin silinmesi, kaydedilen cihazları etkilemez. Bir cihaz kayıt yöneticisi silindiğinde:

-   Kaydedilen hiçbir cihaz bundan etkilenmez.

-   Kaydedilen cihazlar tam olarak yönetilmeye devam eder.

-   Silinen cihaz kayıt yöneticisinin hesap kimlik bilgileri, Şirket Portalı’nda oturum açıp uygulamalara erişmek için geçerliliğini korur.

-   Silinen cihaz kayıt yöneticisi hesabının kimlik bilgileri yine de cihazları temizleyemez ve kullanımdan kaldıramaz.

-   Silinen cihaz kayıt yöneticisi hesabının kayıtlı cihazlar ile ilişkisi devam eder, ancak başka bir cihaz kaydedilemez.



<!--HONumber=Dec16_HO2-->


