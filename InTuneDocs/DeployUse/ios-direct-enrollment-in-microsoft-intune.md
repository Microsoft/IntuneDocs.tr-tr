---
title: "iOS cihazları için doğrudan kayıt | Microsoft Intune"
description: "Şirkete ait cihazları Mac bilgisayarına USB ile bağlayarak önceden yapılandırılmış bir ilkeyle doğrudan kaydetmek için, Apple Configurator aracını kullanın."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 52069f551b73ee938818c30de664e93d1775a061
ms.openlocfilehash: 9526ac2eb902198597ba811c5d957d69e1b991c6


---

# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>Apple Configurator kullanarak iOS cihazlarını doğrudan kaydetme
Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, **Kullanıcı benzeşimi yok** ayarına sahip cihazlar içindir ve kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanız gerekir.

iOS cihazlarını doğrudan kaydederken, cihazın seri numarasını almadan kayıt işlemini yapabilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu kılavuz bir Mac bilgisayarda Apple Configurator 2.0 kullandığınızı varsayar.

1.  Henüz yapmadıysanız, Apple Configurator ile kaydedilmiş iOS cihazları için bir cihaz kayıt profili oluşturun. Cihaz kayıt profili cihazlara uygulanan ayarları tanımlar.

    1.  [Microsoft Intune yönetici konsolu](http://manage.microsoft.com)’nda **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle**’yi seçin.

        ![Cihaz kayıt profili oluşturma sayfası](../media/pol-sa-corp-enroll.png)

    2.  Cihaz profillerinin ayrıntılarını girin:

        -   **Adı**: Cihaz kayıt profilinin adı. Kullanıcılar tarafından görülemez.

        -   **Açıklama**: Cihaz kayıt profilinin açıklaması. Kullanıcılar tarafından görülemez.

        -   **Kullanıcı ilişkisi**: Cihazların nasıl kaydedildiğini belirtir. Doğrudan Kayıt için **Kullanıcı benzeşimi yok**’u seçin.

        -   **Cihaz grubu ön ataması**: Bu profile sahip tüm cihazlar başlangıçta bu gruba ait olur. Cihazları kayıttan sonra yeniden atayabilirsiniz.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Profili eklemek için **Profili Kaydet**’i seçin.

5.  iOS cihazlarına dağıtılacak .mobileconfig gibi bir profili dışarı aktarma:

    1.   Oluşturduğunuz cihaz profilini seçin.

    2.   Görev çubuğunda **Dışarı Aktar**’ı seçin.

    3.   **Profili indir**’i seçin ve indirilen .mobileconfig dosyasını kaydedin.

6.  İndirilen .mobileconfig dosyasını bir Mac bilgisayara kopyalayarak dosyayı aktarın.
    > [!NOTE]
    > Kayıt profili URL’si dışarı aktarılmasından sonra iki hafta boyunca geçerlidir. İki hafta sonra, iOS cihazlarını Kurulum Yardımcısı ile kaydetmek için yeni bir kayıt profili URL’sini dışarı aktarmanız gerekir.

7.  Cihazı Apple Configurator ile hazırlayın. iOS cihazlar Mac bilgisayara bağlanır ve mobil cihaz yönetimine kaydedilir.

    1.  Mac bilgisayarda **Apple Configurator 2.0**’ı açın.

    2.  iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. **Fotoğraflar**, **iTunes** ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.

    3.  Apple Configurator’da, bağlı iOS cihazını ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.

    4.  Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir.  Cihaz **Denetimsiz** ise yükleme cihazda kabul etmeyi gerektirir.

8.  Profili iOS cihaza yüklemeye hazırsınız. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır. Kayıt için uygulama dağıtımları gerekiyorsa, uygulama dağıtımları App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektireceğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.

    1.  iOS cihazının kilidini açın.

    2.  **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’yi seçin.

    3.  Gerekirse, **Cihaz Geçiş Kodu** veya **Apple Kimliği** belirtin.

    4.  **Uyarı**’yı kabul edin ve **Yükle**’yi seçin.

    5.  **Uzak Uyarı**’yı kabul edin ve **Güven**’i seçin.

    6.  **Profil Yüklendi** kutusu profilin **Yüklü** olduğunu doğruladığında **Bitti**’yi seçin.

9.  iOS cihazında **Ayarlar**’ı açın ve **Genel** &gt; **Cihaz Yönetimi** &gt; **Yönetim Profili**’ne gidin. Profil yüklemesinin listelendiğini onaylayın, iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakika kadar sürebilir.

10.  Cihazları dağıtın. iOS cihazı Intune’a kaydedilmiştir ve yönetilmektedir.



<!--HONumber=Oct16_HO3-->


