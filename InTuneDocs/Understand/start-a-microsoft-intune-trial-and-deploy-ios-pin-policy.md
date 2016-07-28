---
title: "Intune denemesi başlatma ve iOS PIN ilkesi dağıtma | Microsoft Intune"
description: "Intune'da iOS PIN ilkesi dağıtma"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: b2b24492693b61a544a4adc3e878b8b212d15a21


---

# Bir Microsoft Intune denemesi başlatma ve iOS PIN ilkesi dağıtma
Bu adım adım yönergeler bir Intune denemesi ayarlamanıza ve iOS cihazları için bir PIN ilkesi yapılandırmanıza yardımcı olur. Deneyebileceğiniz diğer ortak Intune değerlendirme görevlerinin listesi için bkz. [Ortak Microsoft Intune değerlendirme görevleri](common-microsoft-intune-evaluation-tasks.md).



## Bu görevin önkoşullarını gözden geçirme

-   Internet Explorer ile Windows bilgisayar - yönetim görevlerini gerçekleştirmek için

-   Kullanıcı ilkesi doğrulama testi için iOS 7.1 veya sonraki cihaz

-   Deneme hesabına kaydolma sırasında kimliğinizi doğrulamak için telefon

## Ücretsiz bir Intune deneme hesabı oluşturma
> [!NOTE]
> Intune aboneliğiniz zaten varsa bu bölüm atlayın ve sonraki bölüme gidin.

1.  Bir Windows PC kullanarak **Internet Explorer** (IE) öğesine sağ tıklayın ve **InPrivate Gözatma**’yı seçin.

    ![InPrivate gözatmayı başlatın](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  [Intune kayıt portalı](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1)’na gidin, istenen bilgileri sağlayın ve **İleri**’ye tıklayın.

    ![Hesap için kaydolun](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Yönetici hesabınız için bir kullanıcı kimliği ve parola girin ve **İleri**’ye tıklayın. Bu kimliği, yönetim görevlerinizi gerçekleştirmek üzere Intune portalında oturum açmak için kullanacaksınız.

    ![Kimlik oluşturun](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Cep telefonu numaranızı girin ve telefon numaranızı doğrulamak için **Bana ileti gönder**’e tıklayın.

    ![Ayrıntılarınızı doğrulayın](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Ekranda gösterilen bilgileri kaydedin ve ardından **Başlamaya hazırsınız...** öğesine tıklayın.

    ![Başlatmaya hazırsınız](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Test kullanıcısı oluşturma

1.  Bir Windows bilgisayar kullanarak **Başlat**’a tıklayıp kullanıcı yönetimi sayfasına gidin.

    ![Kullanıcı yönetimi sayfasına gidin](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Kullanıcı eklemek için **+** düğmesine tıklayın.

    ![Kullanıcı ekleyin](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  **Yeni kullanıcı hesabı oluşturma** sayfasında:

    1.  Test kullanıcısı bilgilerini sağlayın.

    2.  **Parolayı yaz** seçeneğini belirleyin.

    3.  **Bir daha oturum açtığında bu kişinin parola değiştirmesini iste** onay kutusunun işaretini kaldırın.

    4.  **Oluştur**'a tıklayın.

    ![Yeni kullanıcı hesabı oluşturun](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Kullanıcı oluşturma onayı sayfasında **Kapat**’a tıklayın.

    ![Kullanıcı oluşturma onayı sayfası](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Oluşturduğunuz test kullanıcısını görmek için **Yenile** düğmesine tıklayın.

    ![Hesap onaylama](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Test kullanıcısı için bir iOS PIN ilkesi yapılandırma

1.  Bir Windows bilgisayar kullanarak MDM yetkilisini Intune olacak şekilde ayarlayın:

    1.  [Intune Yönetim Konsolu](http://manage.microsoft.com/)’na gidin, yönetici hesabınızla oturum açın ve **Mobil Cihazları Yönetmeyi Başlat**’a tıklayın. Mobil Cihaz Yönetimi yetkilisi sayfası açılır.

        ![Intune konsolunu kullanmaya başlayın](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  **Mobil Cihaz Yönetimi Yetkilisini Ayarla** bağlantısına tıklayın.

        ![Mobil cihaz yönetimi yetkilisini ayarlayın](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  iOS cihazlarının kaydını etkinleştirin. Bu işlem Apple Anında İletilen Bildirim Servisi (APN) ile Intune aboneliğiniz arasında güvenilen bir sertifika ayarlar.

    1.  **iOS ve Mac OS X platformunu etkinleştir** öğesine tıklayın.

        ![iOS ve Mac OS X kaydını etkinleştirin](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  **APNs Sertifika İsteğini İndir** öğesine tıklayın.

        ![APNs sertifikasını indirin](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Sertifika İmzalama İsteği (CSR) için bir dosya adı ve konum belirtin ve ardından **Kaydet**’e tıklayın. Bu dosya Intune aboneliğiniz tarafından tutulan özel bir anahtara karşılık gelen ortak anahtarı saklar.

        ![Sertifika imzalama isteğini belirtin](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  **Apple Push Certificates portalı**’na tıklayarak yeni bir sekme açın.

        ![APNs sertifikaları sayfasına gidin](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Apple kimliği ve parolanızı girin ve **Oturum Aç**’a tıklayın. Bu kimlik iOS cihazınızda iOS App Store'dan uygulama almak için kullandığınız kimlik olabilir.

        ![Apple Push Certificates portalında oturum açın](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  **Sertifika Oluştur**’a tıklayın.

        ![APNs sertifikası oluşturun](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Apple’ın Kullanım Koşulları’nı okuyun, onay kutusunu işaretleyin ve **Kabul Et**’e tıklayın.

        ![Koşulları kabul edin](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  **Gözat**'a tıklayın.

        ![Sertifika kaydettiğiniz yere göz atın](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Daha önce kaydettiğiniz CSR dosyasını seçin ve **Aç**’a tıklayın.

        ![Sertifikayı açın](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. **Karşıya Yükle** düğmesine tıklayın.

        ![Sertifikayı güncelleştirin](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. JSON dosyası indirmeniz istendiğinde **Farklı Kaydet**’e tıklayın.

        ![JSON dosyasını kaydedin](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. JSON dosyanız için bir konum belirtin ve **Kaydet**’e tıklayın.

        ![JSON dosyasının kaydedileceği yeri belirtin](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Sayfanız birkaç saniye sonra otomatik olarak yönlendirmezse **İptal**’e tıklayın.

        ![Sayfa yönlendirilmezse İptal edin](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Yeni oluşturduğunuz sertifikayı almak için **İndir**’e tıklayın.

        ![Sertifikayı indirin](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. PEM dosyası indirmeniz istendiğinde **Farklı Kaydet**’e tıklayın.

        ![PEM dosyasını indirin](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. PEM dosyası için bir konum belirtin ve **Kaydet**’e tıklayın.

        ![PEM dosyasını kaydedin](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Intune Yönetim Konsolu sekmesine geri dönün ve **APN Sertifikalarını Karşıya Yükle** öğesine tıklayın.

        ![APNs sertifikasını karşıya yükleyin](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Apple Kimliğinizi girin ve **Gözat**’a tıklayın.

        ![Apple kimliğinizi girin](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Yeni kaydettiğiniz PEM dosyasını seçin ve **Aç**’a tıklayın.

        ![PEM dosyasını açın](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Tamamlamak için **Karşıya Yükle**.

        ![PEM dosyasını karşıya yükleyin](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        APN sertifikanız artık yapılandırılmıştır.

        ![APNs sertifikasını yapılandırma işlemi tamamlanır](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  İlke hedefleme için bir test kullanıcı grubu oluşturun:

    1.  Sol bölmede **Gruplar**’a tıklayın.

        ![Gruplar’ı açın](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  En sağdaki **Grup Oluştur**’a tıklayın.

        ![Bir grup oluşturun](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Bir grup adı belirtin, üst grup olarak **Tüm Kullanıcılar**’ı seçin ve **İleri**’ye tıklayın.

        ![Üst grup olarak Tüm Kullanıcılar’ı seçin](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  **Şununla grup üyeliği başlat:** alanında **Üst gruptaki Tüm Kullanıcılar**’ı seçin ve **Son**’a tıklayın.

        ![Şu üst grupla grup üyeliği başlatın](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Bir iOS PIN ilkesi oluşturun ve test kullanıcı grubu için hedefleyin:

    1.  Sol bölmede **İlke**’ye tıklayın.

        ![İlke çalışma alanını açın](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  En sağdaki **İlke Ekle**’ye tıklayın.

        ![İlke ekleyin](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  iOS düğümünü genişletin, **Genel Yapılandırma** satırını seçin ve **İlke Oluştur**’a tıklayın.

        ![iOS genel yapılandırma ilkesi oluşturma](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  İlke için bir ad yazın, **Mobil cihazların kilidini açmak için bir parola gerektir** seçeneğini açın ve **En az parola uzunluğu**’nu **4** olarak ayarlayın.

        ![Parola ayarlarını yapılandırın](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  İlkeyi dağıtmak için **Evet**’e tıklayın.

        ![İlkeyi dağıtın](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Daha önce oluşturulan kullanıcı grubuna, **Ekle** ve **Tamam**’a tıklayın.

        ![İlke için grup seçin](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Artık test kullanıcı grubunuzu hedefleyen bir iOS PIN ilkeniz vardır.

        ![İlke kurulumu tamamlanır](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## İlkenin bir iOS cihazına uygulandığını doğrulama

1.  Bir iPad cihazında iOS App Store’u başlatın, ücretsiz **Microsoft Intune Şirket Portalı** uygulamasını yükleyin ve açın.

    ![Şirket portalını yükleyin](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Test kullanıcı hesabı adını ve parolasını girin ve **Oturum Aç**’a dokunun.

    ![Kimlik bilgilerinizi sağlayın](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  **Kaydet**’e dokunarak cihazı Intune’a kaydetmeye başlayın.

    ![Kayda başlayın](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  **Profil Yükle** ekranında **Yükle** öğesine dokunun.

    ![Profil yükleyin](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  **Profil Yükle** iletişim kutusunda **Yükle** öğesine dokunun.

    ![Profil yüklemeye devam edin](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  **Uyarı** ekranında **Yükle** öğesine dokunun.

    ![Uyarı iletisini kabul edin](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  **Uzak Yönetim** iletişim kutusunda **Güven**’e dokunun.

    ![Uzaktan yönetime güvenin](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Yönetim profilini yükleme tamamlandığında **Bitti**’ye dokunun. Kayıt tamamlanmıştır.

    ![Kayıt tamamlanır](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Kayıt tamamlandığında **Tamam**’a dokunun ve ardından Şirket Portalı uygulamasını kapatın.

    ![Şirket Portalı uygulamasını kapatmak için Tamam'a dokunun](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Bir geçiş kodu yapılandırmanız istendiğinde **Devam**’a dokunun.

    ![Geçiş kodu yapılandırma isteğini kabul edin](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Geçiş kodunuzu girin, **Devam**’a dokunun, geçiş kodunuzu tekrar girin ve **Kaydet**’e dokunun.

    ![Geçiş kodu sağlayın](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. iPad cihazınızı kilitlemek için güç düğmesine basın, kilidini açmak için kaydırın ve cihazın kilidini açmak için geçiş kodunuzu girmeniz gerektiğini görün.

### Ayrıca bkz.
[Intune değerlendirme kılavuzu](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


