---
title: "iOS iş kolu uygulamalarını Intune’a ekleme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS iş kolu uygulamalarını Intune’a eklemeyi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: d8615611eb715da66b1cf0972b885fbccb12fe6a

---

# <a name="how-to-add-ios-line-of-business-lob-apps-to-intune"></a>iOS iş kolu (LOB) uygulamalarını Intune’a ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>1. Adım - Yazılım kurulum dosyasını belirtme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. Intune dikey penceresinde **Uygulamaları yönetme**’yi seçin.
4. **Mobil uygulamalar** iş yükünde Yönet > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** dikey penceresinde **Yazılım Kurulum Dosyası**’nı seçin.
7. **Kurulum dosyası seçin** dikey penceresinde göz at düğmesine tıklayarak iOS uygulaması kurulum dosyasına (.ipa uzantılı) gidin ve **Tamam**’a tıklayın.

## <a name="step-2---configure-app-information"></a>2. Adım - Uygulama bilgilerini yapılandırma

1. **Uygulamayı Düzenle** dikey penceresinde aşağıdaki bilgileri yapılandırın. Bitirdiğinizde, **Ekle**’ye tıklayın. Seçtiğiniz uygulamaya bağlı olarak, dikey penceredeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Uygulama Adı** - Uygulamanın şirket portalında görüntülenecek olan adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Uygulama Açıklaması** - Uygulama için bir açıklama girin. Bu, şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **İlgili Cihaz Türü** - Bu uygulamaların iPad, iPhone veya uyumlu iPod’lara yüklenip yüklenemeyeceğini seçin.
    - **Minimum İşletim Sistemi** - Listeden uygulamanın yüklenebileceği minimum işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Simgeyi Karşıya Yükle** - Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.
2. İşiniz bittiğinde, **Uygulama Ekle** dikey penceresinde **Kaydet**’i seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


