---
# required metadata

title: Microsoft Intune ile iOS cihazları için doğrudan kayıt | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apple Configurator’ı kullanarak iOS cihazlarını doğrudan kaydetme
Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, **Kullanıcı benzeşimi yok** ayarına sahip cihazlar içindir ve kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanızı gerektirir. Şirket Portalı uygulaması doğrudan kayıtlı cihazlar için desteklenmez. Bu kılavuz bir Mac bilgisayarda Apple Configurator 2.0 kullandığınızı varsayar.

1.  Cihazlar için profil oluşturma Cihaz kayıt profili cihazlara uygulanan ayarları tanımlar.

    #### Henüz yapmadıysanız, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profili oluşturun.

    1.  Bir profil oluşturmak için

        ![[Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle…** düğmesine tıklayın.](../media/pol-sa-corp-enroll.png)

    2.  Cihaz kayıt profili oluşturma sayfası

        -   Cihaz profillerinin ayrıntılarını girin: **Adı** – Cihaz kayıt profilinin adı.

        -   Kullanıcılar tarafından görülemez. **Açıklama** - Cihaz kayıt profilinin açıklaması.

        -   Kullanıcılar tarafından görülemez. **Kullanıcı ilişkisi** – Cihazların nasıl kaydedildiğini belirtir.

        -   Doğrudan Kayıt için **Kullanıcı benzeşimi yok**’u seçin. **Cihaz grubu ön ataması** – Bu profili dağıtan tüm cihazlar başlangıçta bu gruba ait olur.

    3.  Cihazları kayıttan sonra yeniden atayabilirsiniz.

2.  Profili eklemek için **Profili Kaydet** öğesine tıklayın.

    ![Apple Configurator ile kaydedilecek iOS cihazları ekleme](../media/pol-SA-enroll-iOS-SetupAssistant.png)

      [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Kurumsal ön kayıtlı cihazlar** &gt; **iOS seri numarasına göre**’ye gidin ve **Cihaz ekle…** düğmesine tıklayın.

    -   iOS kurulum yardımcısı

        |||
        |-|-|
        |&lt;İki yolla cihaz ekleyebilirsiniz:&gt;|&lt;**Seri numaraları içeren bir CSV dosyası yükleme** – Üst bilgi içermeyen iki sütunun virgülle ayrılmış değer (.csv) listesini oluşturun ve csv dosyası başına 5000 cihaz veya 5 MB ile sınırlayın.&gt;|
        |&lt;Seri 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        Seri 2

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   Cihaz 2 Ayrıntıları

    > [!NOTE]
    > Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:  **Cihaz ayrıntılarını el ile ekle** - En fazla beş cihazın seri numarasını ve cihaz ayrıntılarını girin ve ardından **İleri**’ye tıklayın.

3.  Şirkete ait cihazları daha sonra Intune yönetiminden kaldırmanız gerekirse, cihaz kaydını devre dışı bırakmak için Intune’daki **Şirkete ait cihazlar** grubundan cihaz seri numarasını kaldırmanız gerekir. Intune, seri numaralarının kaldırıldığı sıralarda olağanüstü durum kurtarma yordamı gerçekleştirirse, o grupta yalnızca etkin cihazların seri numaralarının bulunduğunu doğrulamanız gerekir. Kaydedilecek cihazları seçme

4.  Kaydedilecek cihazları onaylayın. Zaten kayıtlı olan veya başka yollarla kaydedilmiş seri numaraları içeri aktarılamaz.

5.  Devam etmek için **İleri** 'ye tıklayın. Profil atama Kullanılabilir profiller listesinden eklenen cihazlara atanacak profili belirtin, **Kayıt profili ayrıntıları**’e gidin ve **Son**. El ile eklenen cihazlar herhangi bir Kayıt profiline atanabilir. iOS cihazlarına dağıtılacak bir profil seçme

6.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve mobil cihazlara dağıtılacak cihaz profilini seçin.
    > [!NOTE]
    > Bu profil, önceki adımda dağıtmak için atadığınız profilin aynısı olmalıdır. Görev çubuğundaki **Dışarı Aktar...**
7.  öğesine tıklayın.

    1.  **Profili indir**’e tıklayın ve indirilen .mobileconfig dosyasını kaydedin.

    2.  Dosyayı aktarma İndirilen .mobileconfig dosyasını bir Mac bilgisayara kopyalayın.

    3.  Kayıt profili URL’si dışarı aktarılmasından sonra iki hafta boyunca geçerlidir. İki hafta sonra, iOS cihazlarını Kurulum Yardımcısı ile kaydetmek için yeni bir kayıt profili URL’sini dışarı aktarmanız gerekir. Cihazı Apple Configurator ile hazırlama

    4.  iOS cihazlar Mac bilgisayara bağlanır ve mobil cihaz yönetimine kaydedilir. Mac bilgisayarda **Apple Configurator 2.0**'ı başlatın.  iOS cihazını bir USB kablosu ile Mac bilgisayara bağlayın.

8.  **Fotoğraflar**, **iTunes** ve cihaz algılandığında cihaz için açık olan diğer uygulamaları kapatın. Apple Configurator'da bağlı iOS cihazına tek tıklayın ve ardından **Ekle** düğmesine tıklayın.  Cihaza eklenebilen seçenekler aşağı açılan listede görüntülenir.

    ###### **Profiller**’e tıklayın.

    1.  Intune’dan dışarı aktardığınız .mobileconfig dosyasını seçmek için dosya seçiciyi kullanın ve ardından **Ekle**’ye tıklayın.

    2.  Profil cihaza eklenir.

    3.  Cihaz **Denetimsiz** ise yükleme cihazda kabul etmeyi gerektirir.

    4.  Profili yükleme

    5.  Profili iOS cihaza yüklemeye hazırsınız.

    6.  Cihaz, Kurulum Yardımcısı’nı zaten tamamlamış ve hazır olmalıdır.

9. Kayıt için uygulama dağıtımları gerekiyorsa, uygulama dağıtımları App Store için imzalanmış bir Apple Kimliğiniz olmasını gerektireceğinden cihazda bir Apple Kimliği ayarlanmış olmalıdır. Denetimsiz iOS cihazlar için profil kabulünü tamamlama

10. iOS cihazının kilidini açın.


### **Yönetim profili**’nin **Profili yükle** iletişim kutusunda **Yükle**’ye dokunun.
[Gerekirse, **Cihaz Geçiş Kodu** veya **Apple Kimliği** belirtin.](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


