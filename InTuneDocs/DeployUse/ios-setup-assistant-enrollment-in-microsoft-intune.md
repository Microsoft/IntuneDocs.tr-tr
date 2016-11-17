---
title: "iOS cihazlarını Kurulum Yardımcısı ile kaydetme | Microsoft Intune"
description: "Şirkete ait iOS cihazlarını fabrika ayarlarına sıfırlamak ve Kurulum Yardımcısı’nı çalıştırmaya hazırlamak için Apple Configurator aracını kullanarak kaydedin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: bb94cb21bce5fb25c821b6a01d952ccba2f94834


---

# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a>Kurulum Yardımcısı’nı kullanarak Apple Configurator ile iOS cihazlarını kaydetme
Intune, bir Mac bilgisayarda çalıştırılan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler. Bu işlem cihazı fabrika ayarlarına sıfırlar ve şirketin ilkelerini cihazın yeni kullanıcısı için yükleyerek Kurulum Yardımcısı’nın çalıştırılabilmesi için hazırlar.

## <a name="setup-assistant-enrollment-for-ios-devices-with-microsoft-intune"></a>Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı
Apple Configurator kullanarak, bir iOS cihazını fabrika ayarlarına sıfırlayabilir ve cihazın yeni kullanıcısı için ayarlanmak üzere hazırlayabilirsiniz. Bu yöntem, kurumsal kayıt kurulumu için iOS cihazını USB ile bir Mac bilgisayara bağlamanızı gerektirir ve Apple Configurator 2.0 kullandığınızı varsayar. Çoğu senaryoda, Intune Şirket Portalı uygulamasını etkinleştirmek için iOS cihazına uygulanmış olan ilkenin **kullanıcı benzeşimi** içermesi gerekir.

**Önkoşullar**
* APNs sertifikası yüklenerek [iOS kaydı etkinleştirilir](set-up-ios-and-mac-management-with-microsoft-intune.md)
* iOS cihazlara fiziksel erişim&mdash;cihazlar parola koruması olmadan fabrika ayarlarına sıfırlanmış olmalıdır
* Cihaz seri numaraları&mdash;bkz. [iOS seri numarası alma](https://support.apple.com/en-us/HT204308)
* USB bağlantı kabloları
* [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) içeren Mac bilgisayar


1.  **Mobil cihaz grupları oluşturma** (isteğe bağlı).
    İşiniz mobil cihazların yönetimine yardımcı olmak için cihaz gruplarının oluşturulmasını gerektiriyorsa, bu grupları oluşturun. Daha fazla bilgi edinmek için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

2.  **Cihazlar için profil oluşturma**.
    Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımları, Apple Configurator kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

    1.  [Microsoft Intune yönetici konsolu](http://manage.microsoft.com)’nda **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle**’yi seçin.
    ![Cihaz kayıt profili oluşturma](../media/pol-sa-corp-enroll.png)

    2.  Cihaz profillerinin ayrıntılarını girin:

        -   **Ad**&mdash;Cihaz kayıt profilinin adı (kullanıcılara gösterilmez).

        -   **Açıklama**&mdash; Cihaz kayıt profilinin açıklaması (kullanıcılara gösterilmez).

        -   **Kayıt Ayrıntıları**&mdash; Cihazların nasıl kaydedildiğini belirtir.

            -   **Kullanıcı benzeşimi istemi**&mdash; Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. DEP tarafından yönetilen kullanıcılara ait olan ve uygulama yüklemek gibi hizmetler için şirket portalını kullanması gereken cihazlarda **kullanıcı benzeşimi** ayarlanmalıdır.

            -   **Kullanıcı benzeşimi yok**&mdash; Cihaz bir kullanıcıya bağlı değil. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

        -   **Cihaz grubu ön ataması**&mdash; Bu profille dağıtılan tüm cihazlar başlangıçta bu gruba ait olur. Cihazları kayıttan sonra yeniden atayabilirsiniz.

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

        -  **Cihaz Kayıt Programı**&mdash; Apple Cihaz Kayıt Programı (DEP), Kurulum Yardımcısı kaydıyla birlikte kullanılamaz. Düğmenin **kapalı** olarak ayarlandığından emin olun.

    3.  Profili eklemek için **Profili Kaydet**’i seçin.

3.  **Kurulum Yardımcısı ile kaydedilecek iOS cihazları ekleyin**.
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirkete Ait Tüm Cihazlar** &gt; **Tüm Cihazlar**’a gidin ve **Cihaz ekle**’yi seçin. İki yolla cihaz ekleyebilirsiniz:

    ![Cihaz ekle iletişim kutusu](../media/pol-SA-enroll-iOS-SetupAssistant.png)

    -   **Seri numaraları içeren bir CSV dosyası yükleme**&mdash;Üst bilgi içermeyen iki sütunun virgülle ayrılmış değer (.csv) listesini oluşturun ve csv dosyası başına 5,000 cihaz veya 5 MB ile sınırlayın.

        |||
        |-|-|
        |&lt;Seri 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        |&lt;Seri 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|
        Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

        ```
        0000000,PO 1234
        111111111,PO 1234
        ```

    -   **Cihaz ayrıntılarını el ile ekle**&mdash; En fazla beş cihazın seri numarasını ve cihaz ayrıntılarını girin.

    > [!NOTE]
    > Şirkete ait cihazları daha sonra Intune yönetiminden kaldırmanız gerekirse, cihaz kaydını devre dışı bırakmak için **Şirkete Ait Önceden Kaydedilmiş cihazlar** altındaki **iOS Seri Numarasına Göre** cihaz grubunda bulunan cihaz seri numarasını Intune’dan kaldırmanız gerekebilir. Intune, seri numaralarını kaldırdığınız sıralarda olağanüstü durum kurtarma yordamı gerçekleştirirse, o grupta yalnızca etkin cihazların seri numaralarının bulunduğunu doğrulamanız gerekir.

    **İleri**’yi seçin.

4.  **Kaydedilecek cihazları seçin**.
    Kaydedilecek cihazları onaylayın. Zaten kayıtlı olan veya başka yollarla kaydedilmiş seri numaraları içeri aktarılamaz. Devam etmek için **İleri**’yi seçin.

5.  **Profil atayın**.
    Kullanılabilir profiller listesinden eklenen cihazlara atanacak profili belirtin, **Kayıt profili ayrıntıları**’e gidin ve **Son**’a tıklayın. El ile eklenen cihazlar herhangi bir kayıt profiline atanabilir.

6.  **iOS cihazlarına dağıtılacak bir profili dışarı aktarın**.
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com), **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve mobil cihazlara dağıtılacak cihaz profilini seçin. Görev çubuğunda **Dışarı Aktar**’ı seçin. **Profil URL'si**öğesini kopyalayıp kaydedin. iOS cihazlar tarafından kullanılan Intune profilini tanımlamak için daha sonra Apple Configurator'a yüklemeniz gerekecektir.
    Apple Configurator 2’nin desteklenmesi için, 2.0 Profil URL’sinin düzenlenmesi gerekir. Bunu yapmak için şu kodu değiştirin:
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Bu kod ile:

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   iOS cihazlarında kullanılan Intune profilini tanımlamak için, aşağıdaki yordamda Apple Configurator kullanarak bu profil URL’sini Apple DEP hizmetine yükleyeceksiniz.



7.  **Cihazı Apple Configurator ile hazırlayın**.
    iOS cihazlar Mac bilgisayara bağlanır ve mobil cihaz yönetimine kaydedilir.

    1.  Mac bilgisayarda **Apple Configurator 2**'yi açın. Menü çubuğunda **Apple Configurator 2**’yi, sonra **Tercihler**’i seçin.

         > [!WARNING]
         > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Cihazı bağladığınızda cihazın **Merhaba** ekranında olması gerekir.

    2. Tercihler bölmesinde **Sunucular**’ı seçin ve MDM Sunucusu sihirbazını başlatmak için (+) artı simgesini seçin. **İleri**’yi seçin.

    3. Microsoft Intune ile iOS cihazları için Kurulum Yardımcısı kaydı altındaki 6. adımdan MDM sunucusunun **Adı** ve **Kayıt URL'sini** girin. Kayıt URL’si olarak Intune’dan dışarı aktarılan kayıt profili URL’sini girin. **İleri**’yi seçin.  

       “Sunucu URL'si doğrulanmadı” uyarısı alırsanız göz ardı edebilirsiniz. Devam etmek için sihirbaz tamamlanana kadar **İleri**’yi seçin.

    4.  iOS mobil cihazları bir USB bağdaştırıcısı ile Mac bilgisayara bağlayın.

        > [!WARNING]
        > Cihazlar kayıt işlemi sırasında fabrika yapılandırmalarına sıfırlanır. En iyi uygulama olarak cihazı sıfırlayın ve açın. Kurulum Yardımcısı’nı başlattığınızda cihazlar **Merhaba** ekranında olmalıdır.

    5.  **Hazırla**’yı seçin. iOS Cihazı Hazırla bölmesinde, **El ile**’yi, sonra **İleri**’yi seçin.

    6. MDM Sunucusuna Kaydol bölmesinde, oluşturduğunuz sunucunun adını, sonra **İleri**’yi seçin.

    7. Cihazları Denetle bölmesinde, denetim düzeyini seçin, sonra **İleri**’yi seçin.

    8. Kuruluş Oluştur bölmesinde **Kuruluş**’u seçin veya yeni bir kuruluş oluşturun, sonra **İleri**’yi seçin.

    9. iOS Kurulum Yardımcısı’nı Yapılandır bölmesinde, kullanıcıya sunulan adımları, sonra da **Hazırla**’yı seçin. İstenirse, güven ayarlarını güncelleştirmek için kimlik doğrulaması yapın.  

    10. iOS cihazı hazırlanmayı tamamladığında USB kablosunun bağlantısını kesin.  

8.  **Cihazları dağıtın**.
    Cihazlar artık kurumsal kayıt için hazırdır. Cihazları kapatın ve kullanıcılara dağıtın. Kullanıcılar cihazlarını açtığında Kurulum Yardımcısı başlatılır.



### <a name="see-also"></a>Ayrıca bkz.
[Cihaz kaydetme önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO1-->


