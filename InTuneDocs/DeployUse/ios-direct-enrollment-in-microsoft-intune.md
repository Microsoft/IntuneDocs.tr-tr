---
title: "iOS cihazları için doğrudan kayıt | Microsoft Intune"
description: "Şirkete ait cihazları Mac bilgisayarına USB ile bağlayarak önceden yapılandırılmış bir ilkeyle doğrudan kaydetmek için, Apple Configurator aracını kullanın."
keywords: 
author: NathBarn
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
ms.sourcegitcommit: aabe68a3621a02b8f3142ab3f593190cc23053dd
ms.openlocfilehash: 17836bc826bc89e3f041f7b369be09c1cce9ea4f


---

# Apple Configurator’ı kullanarak iOS cihazlarını doğrudan kaydetme
Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, **Kullanıcı benzeşimi yok** ayarına sahip cihazlar içindir ve kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanızı gerektirir. iOS cihazlarını doğrudan kaydederken, cihazın seri numarasını almadan kayıt işlemini yapabilirsiniz. Ayrıca Intune kayıt sırasında cihaz adını yakalamadan önce, cihazı tanımlama amacıyla adlandırabilirsiniz. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu kılavuz bir Mac bilgisayarda Apple Configurator 2.0 kullandığınızı varsayar.

1.  **Cihazlar için profil oluşturma** Cihaz kayıt profili, cihazlara uygulanan ayarları tanımlar. Henüz yapmadıysanız, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profili oluşturun.

    1.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle…**’ye tıklayın.

        ![Cihaz kayıt profili oluşturma sayfası](../media/pol-sa-corp-enroll.png)

    2.  Cihaz profillerinin ayrıntılarını girin:

        -   **Adı** – Cihaz kayıt profilinin adı. Kullanıcılar tarafından görülemez.

        -   **Açıklama** - Cihaz kayıt profilinin açıklaması. Kullanıcılar tarafından görülemez.

        -   **Kullanıcı ilişkisi** – Cihazların nasıl kaydedildiğini belirtir. Doğrudan Kayıt için **Kullanıcı benzeşimi yok**’u seçin.

        -   **Cihaz grubu ön ataması** – Bu profili dağıtan tüm cihazlar başlangıçta bu gruba ait olur. Cihazları kayıttan sonra yeniden atayabilirsiniz.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  Profili eklemek için **Profili Kaydet**’i seçin.

5.  **Bir profili iOS cihazlarına dağıtmak için .mobileconfig olarak dışarı aktarma** Oluşturduğunuz cihaz profilini seçin. **Dışarı Aktar...**’ı seçin öğesine tıklayın. **Profili indir**’i seçin ve indirilen .mobileconfig dosyasını kaydedin.

6.  **Dosyayı aktarma** İndirilen .mobileconfig dosyasını bir Mac bilgisayara kopyalayın.
    > [!NOTE]
    > Kayıt profili URL’si dışarı aktarılmasından sonra iki hafta boyunca geçerlidir. İki hafta sonra, iOS cihazlarını Kurulum Yardımcısı ile kaydetmek için yeni bir kayıt profili URL’sini dışarı aktarmanız gerekir.
7.  **Cihazı Apple Configurator ile hazırlama** iOS cihazları Mac bilgisayara bağlanır ve mobil cihaz yönetimine kaydedilir.

    1.  Bir Mac bilgisayarda **Apple Configurator 2.0**'ı başlatın.

    2.  iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın. **Fotoğraflar**, **iTunes** ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın.

    3.  Apple Configurator’da, bağlı iOS cihazına tıklayın ve sonra **Ekle** düğmesini seçin. Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir. **Profiller**’i seçin.

    4.  Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve sonra **Ekle**’yi seçin. Profil cihaza eklenir.  Cihaz **Denetimsiz** ise yükleme cihazda kabul etmeyi gerektirir.

8.  **Profili yükleme** Profili iOS cihazına yüklemeye hazırsınız. Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır.  Kayıt için uygulama dağıtımları gerekiyorsa, uygulama dağıtımları App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektireceğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır.

    1.  iOS cihazının kilidini açın.

    2.  **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’ye dokunun.

    3.  Gerekirse, **Cihaz Geçiş Kodu** veya **Apple Kimliği** belirtin.

    4.  **Uyarı**’yı kabul edin ve **Yükle**’ye dokunun.

    5.  **Uzak Uyarı**’yı kabul edin ve **Güven**’e dokunun.

    6.  **Profil Yüklendi** kutusu profilin **Yüklendiğini** doğruladığında **Bitti**’yi seçin.

9. **Profili doğrulama**
    iOS cihazında **Ayarlar**’ı başlatın ve **Genel** &gt; **Cihaz Yönetimi** &gt; **Yönetim Profili** &gt; seçeneğine gidip profil yüklemesinin listelendiğini doğrulayın, iOS ilke kısıtlamalarını ve yüklü uygulamaları denetleyin. İlke kısıtlamaları ve uygulamaların cihazda görünmesi 10 dakikaya kadar sürebilir.

10. **Cihazları dağıtma** iOS cihazı artık Intune’a kaydedilmiştir ve Intune tarafından yönetilmektedir.



<!--HONumber=Aug16_HO1-->


