---
# required metadata

title: Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Kurulum Yardımcısı’nı kullanarak Apple Configurator ile iOS cihazlarını kaydetme
Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlar ve şirketin ilkeleri önceden yüklenmiş olarak cihazın yeni kullanıcısı tarafından Kurulum Yardımcısı’nın çalıştırılabilmesi için hazırlar.


## Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı
Apple Configurator ile iOS cihazlarını fabrika ayarlarına sıfırlayabilir ve cihazın yeni kullanıcısı tarafından kuruluma hazırlayabilirsiniz.  Bu yöntem, kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanızı gerektirir ve Apple Configurator 2.0 kullandığınızı varsayar. Çoğu senaryoda, Intune Şirket Portalı uygulamasını etkinleştirmek için iOS cihazına uygulanmış olan ilkenin *kullanıcı benzeşimi* içermesi gerekir.

**Önkoşullar**
* iOS cihazlara fiziksel erişim - Parola koruması olmadan cihaz yapılandırması kaldırılmış olmalıdır (fabrika ayarı)
* Cihaz seri numaraları - [iOS seri numarası alma](https://support.apple.com/en-us/HT204308)
* USB bağlantı kabloları
* [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) içeren Mac bilgisayar


1.  **Mobil cihaz grubu oluşturma** (İsteğe bağlı) Şirketiniz mobil cihaz yönetimine yardımcı olması için cihaz grupları oluşturulmasını gerektiriyorsa, bu grupları oluşturun. [Microsoft Intune ile kullanıcı ve cihazları yönetmek için grupları kullanın](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Cihazlar için profil oluştur** Cihaz kayıt profili, bir cihaz grubuna uygulanan ayarları tanımlar. Henüz yapmadıysanız, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profili oluşturun.

    ###### Bir profil oluşturmak için

    1.  [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Şirkete Ait Cihazlar**’a gidin ve **Ekle…**’ye tıklayın.

    ![Cihaz kayıt profili oluşturma](../media/pol-sa-corp-enroll.png)

    2.  Cihaz profillerinin ayrıntılarını girin:

        -   **Adı** – Cihaz kayıt profilinin adı. (Kullanıcılar tarafından görülemez)

        -   **Açıklama** - Cihaz kayıt profilinin açıklaması. (Kullanıcılar tarafından görülemez)

        -   **Kayıt Ayrıntıları** – Cihazların nasıl kaydedildiğini belirtir.

            -   **Kullanıcı benzeşimi istemi** – iOS cihazı ilk kurulum sırasında bir kullanıcıyla ilişkilendirilebilir ve daha sonra şirket verilerine ve e-postalara bu kullanıcı gibi erişmesine izin verilebilir. Çoğu Kurulum Yardımcısı senaryosu için **Kullanıcı benzeşimi istemi**’ni kullanın.
            Bu mod birkaç senaryoyu destekler:

                -   **Şirketin sahip olduğu kişisel cihaz** – “Kendi Cihazını Seç” (CYOD) Kişinin sahip olduğu veya kişisel cihazlara benzer; ancak yönetici, cihazı silme, sıfırlama, yönetme ve kaydını kaldırma izni dahil belirli ayrıcalıklara sahiptir. Cihazın kullanıcısı uygulama yükleyebilir ve yönetim ilkesi tarafından engellenmeyen diğer birçok cihaz kullanım iznine sahiptir.

                -   **Cihaz kaydı yönetici hesabı** – Cihaz özel bir Intune yönetici hesabı kullanılarak kaydedilir. Özel hesap olarak yönetilebilir, ancak yalnızca yönetici kimlik bilgilerini bilen bir kullanıcı uygulama yükleyebilir, cihazı silebilir, sıfırlayabilir, yönetebilir ve kaydını kaldırabilir. Ortak bir hesap üzerinden çok sayıda kullanıcının paylaştığı bir cihazı kaydetme hakkında bilgi için bkz. [Şirkete ait cihazları Microsoft Intune’da Cihaz Kayıt Yöneticisi ile kaydetme](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

            -   **Kullanıcı benzeşimi yok** – Cihaz kullanıcı içermez. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı ilişkisinin devre dışı bırakılmasını gerektiren uygulamalar devre dışı bırakılır veya çalışmaz.

        -   **Cihaz grubu ön ataması** – Bu profili dağıtan tüm cihazlar başlangıçta bu gruba ait olur. Cihazları kayıttan sonra yeniden atayabilirsiniz.

          -  **Cihaz Kayıt Programı** - Apple Cihaz Kayıt Programı (DEP), Kurulum Yardımcısı kaydıyla birlikte kullanılamaz. Düğmenin **kapalı** olarak ayarlandığından emin olun.

    3.  Profili eklemek için **Profili Kaydet**’i seçin.

3.  **Kaydedilecek iOS cihazlarını Kurulum Yardımcısı ile ekleme** [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirkete Ait Tüm Cihazlar** &gt; **Tüm Cihazlar**’a gidin ve **Cihaz ekle…**’yi seçin. İki yolla cihaz ekleyebilirsiniz:

    ![Cihaz ekle iletişim kutusu](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Seri numaraları içeren bir CSV dosyası yükleme** – Üst bilgi içermeyen iki sütunun virgülle ayrılmış değer (.csv) listesini oluşturun ve csv dosyası başına 5000 cihaz veya 5 MB ile sınırlayın.

        |||
        |-|-|
        |&lt;Seri 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        |&lt;Seri 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|
        Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Cihaz ayrıntılarını el ile ekle** - En fazla beş cihazın seri numarasını ve cihaz ayrıntılarını girin

    > [!NOTE]
    > Şirkete ait cihazları daha sonra Intune yönetiminden kaldırmanız gerekirse, cihaz kaydını devre dışı bırakmak için **Şirkete Ait Önceden Kaydedilmiş cihazlar** altındaki **iOS Seri Numarasına Göre** cihaz grubunda bulunan cihaz seri numarasını Intune’dan kaldırmanız gerekebilir.  Intune, seri numaralarının kaldırıldığı sıralarda olağanüstü durum kurtarma yordamı gerçekleştirirse, o grupta yalnızca etkin cihazların seri numaralarının bulunduğunu doğrulamanız gerekir.

    **İleri**’yi seçin.

4.  **Kaydedilecek cihazları seçme** Kaydedilecek cihazları onaylayın. Zaten kayıtlı olan veya başka yollarla kaydedilmiş seri numaraları içeri aktarılamaz. Devam etmek için **İleri**’yi seçin.

5.  **Profil atama** Kullanılabilir profiller listesinden eklenen cihazlara atanacak profili belirtin, **Kayıt profili ayrıntıları**’nı gözden geçirin ve ardından **Son**’a tıklayın. El ile eklenen cihazlar herhangi bir Kayıt profiline atanabilir.

6.  **iOS cihazlarına dağıtılacak bir profili dışarı aktarma** [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve mobil cihazlara dağıtılacak cihaz profilini seçin. **Dışarı Aktar…**’ı seçin öğesine tıklayın. **Profil URL'si**öğesini kopyalayıp kaydedin. iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için daha sonra Apple Configurator'a yüklemeniz gerekecektir.
    Apple Configurator 2’nin desteklenmesi için, 2.0 Profil URL’sinin düzenlenmesi gerekir. Aşağıdakini
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    bununla değiştirin

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   iOS cihazlarında kullanılan Intune profilini tanımlamak için, aşağıdaki yordamda Apple Configurator kullanarak bu profil URL’sini Apple DEP hizmetine yükleyeceksiniz.



7.  **Cihazı Apple Configurator ile hazırlama** iOS cihazları Mac bilgisayara bağlanır ve mobil cihaz yönetimine kaydedilir.

    1.  Mac bilgisayarda **Apple Configurator 2**'yi açın. Menü çubuğunda **Apple Configurator 2**’yi, sonra **Tercihler**’i seçin.

         > [!WARNING]
         > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. En iyi uygulama olarak cihazı bağladığınızda cihazın **Merhaba** ekranında olması gerekir.

    2. Tercihler bölmesinde **Sunucular**’ı seçin ve MDM Sunucusu sihirbazını başlatmak için sol bölmenin altındaki “+” simgesini seçin. **İleri**’yi seçin.

    3. MDM sunucusu için yukarıda 6. Adımda verilen **Ad** ve **Kayıt URL’si** değerlerini girin. Kayıt URL’si olarak Intune’dan dışarı aktarılan kayıt profili URL’sini girin. **İleri**’yi seçin.  

       Apple TV ile ilgili güven profili gereksinimleri hakkında bir uyarı alırsanız, gri “X” işaretini seçerek **Güven Profili** seçeneğini iptal edebilirsiniz. Ayrıca tüm Anchor sertifika uyarılarını da göz ardı edebilirsiniz. Devam etmek için, sihirbaz tamamlanana kadar **İleri**’yi seçin.

    4.  **Sunucular** bölmesinde, yeni sunucu profilinin yanındaki “Düzenle”yi seçin. Kayıt URL’sinin, Intune’dan dışarı aktarılan URL’yle tam olarak eşleştiğinden emin olun. Bunlar farklıysa özgün URL’yi yeniden girin ve Intune’dan dışarı aktarılan kayıt profilini **kaydedin**.

    5.  iOS mobil cihazları bir USB bağdaştırıcısı ile Apple bilgisayara bağlayın.

        > [!WARNING]
        > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. En iyi yöntem olarak, Kurulum Yardımcısı’nı başlattığınızda cihazlar **Hello** ekranında olmalıdır.

    6.  **Hazırla**’yı seçin. **iOS Cihazını Hazırla** bölmesinde, **El ile**’yi, sonra **İleri**’yi seçin.

    7. **MDM Sunucusuna kaydol** bölmesinde, oluşturduğunuz sunucunun adını, sonra **İleri**’yi seçin.

    8. **Cihazları Denetle** bölmesinde, denetim düzeyini seçin, sonra **İleri**’yi seçin.

    9. **Kuruluş Oluştur** bölmesinde, **Kuruluş**’u seçin veya yeni bir kuruluş oluşturun, sonra **İleri**’yi seçin.

    10. **iOS Kurulum Yardımcısı’nı Yapılandır** bölmesinde, kullanıcıya sunulan adımları seçin, sonra **Hazırla**’yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulaması yapın.  

    11. iOS cihazı hazırlanmayı tamamladığında USB kablosunun bağlantısını kesebilirsiniz.  

8.  **Cihazları dağıtma** Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Cihaz açıldığında Kurulum Yardımcısı başlar.



### Ayrıca bkz.
[Cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


