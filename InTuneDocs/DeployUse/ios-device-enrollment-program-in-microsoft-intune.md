---
# required metadata

title: Microsoft Intune ile iOS cihazları için Apple DEP yönetimi | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme
Microsoft Intune, Cihaz Kayıt Programı (DEP) aracılığıyla satın alınmış iOS cihazlarını “uzaktan” kaydeden bir kayıt profili dağıtabilir. Kayıt paketi, cihaz için kurulum yardımcısı seçenekleri içerebilir. DEP ile kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz.

## Microsoft Intune ile iOS cihazları için Apple DEP yönetimi
Şirkete ait iOS cihazlarının Apple Cihaz Kaydı Programı (DEP) ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir:  [https://deploy.apple.com](https://deploy.apple.com). Programın sağladığı avantajlar arasında, her cihazı bir USB ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

Şirketin sahi olduğu iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirtecine ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un Kayıt Profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

1.  **Microsoft Intune'la iOS cihazları yönetmeye başlama**
    iOS Cihaz Kaydı Programı (DEP) cihazlarını kaydedebilmeniz için önce Intune için iOS yönetimini etkinleştirmeniz gerekir.

2.  **Şifreleme Anahtarı Alma**
    Yönetici olan bir kullanıcı olarak, [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com)açın, **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**’na gidin ve **Şifreleme Anahtarını İndir**’e tıklayın. Şifreleme anahtarı (.pem) dosyasını yerel olarak kaydedin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

      ![Cihaz kayıt programı belirtecini güncelleştirme](../media/dev-sa-ios-dep.png)

3.  **Bir Cihaz Kayıt Programı belirteci edinme**
    [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. Bu Apple kimliğinin gelecekte DEP belirtecinizi yenilemek için kullanılması gerekir.

    1.  [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**’e gidin ve **MDM Sunucusu Ekle**'ye tıklayın..

    2.   **MDM Sunucu Adı** 'nı girin ve ardından **İleri**'ye tıklayın. Sunucu adı, MDM sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

    3.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesine tıklayarak .pem dosyasını karşıya yükleyin ve ardından **İleri**'ye tıklayın..

    4.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı görüntülenir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**’ye tıklayın..

    Bu sertifika (.p7m) dosyası Intune ile Apple'ın Cihaz Kayıt Programı sunucuları arasında bir güven ilişkisi oluşturmak için kullanılır.

4.  **DEP belirtecini Intune'a ekleme**
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**’na gidin, **DEP Belirtecini Karşıya Yükle**. **Gözat**’a tıklayarak sertifika (.p7m) dosyasına göz atın, **Apple Kimliğinizi** girin ve **Karşıya Yükle**’ye tıklayın..

5.  **Kurumsal Cihaz Kaydı İlkesi Ekleme**
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle**’ye tıklayın.  **Ad** ve **Açıklama** dahil olmak üzere **Genel**ayrıntıları verin, profile atanmış cihazların kullanıcı benzeşimine sahip olduğunu veya bir gruba ait olduğunu belirtin ve ardından DEP desteği için **Bu ilke için Cihaz Kayıt Programı ayarlarını yapılandırın** seçeneğini etkinleştirin.  **Kurulum yardımcısı bölmeleri** , kurulum sırasında yapılandırılan iOS cihaz ayarlarını tanımlar.

      ![Kurulum yardımcısı bölmesi](../media/pol-sa-corp-enroll.png)

6.  **Yönetim için DEP Cihazları Atama**
    [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. **Dağıtım Programı** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**’e gidin.  **Cihaz Seç**bölümünden cihaz tercihinizi yapın, cihaz bilgilerini belirtin ve **Seri Numarası**, **Sipariş Numarası**bilgileriyle veya **CSV Dosyasını Karşıya Yükle**seçeneğiyle cihaz ayrıntılarını belirtin. Ardından, **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;SunucuAdı&gt; öğesini seçip **Tamam**'a tıklayın..

7.  **DEP ile Yönetilen Cihazları Eşitleme**
    Yönetici olan bir kullanıcı olarak, [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com)açın, **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**’na gidin ve **Şimdi eşitle**’ye tıklayın. Apple'a bir eşitleme isteği gönderilir. DEP ile yönetilen cihazları eşitlemeden sonra görmek için [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Şirkete Ait Tüm Cihazlar**’a gidin. **Şirkete Ait Cihazlar** çalışma alanında yönetilen cihazlar için **Durum**, cihaz çalıştırılıp cihaz kaydı için Kurulum Yardımcısı çalıştırılana kadar “Bağlantı kurulmadı” olarak gösterilir.

    Apple’ın kabul edilebilir DEP trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -  Tam DEP eşitlemesi 7 günde birden daha sık çalıştırılamaz. Tam eşitleme sırasında, Intune Apple’ın Intune’a atadığı her seri numarasını (bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın) yeniler. Önceki tam eşitlemenin üzerinden 7 gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 10 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar Eşitle düğmesi devre dışı bırakılır.

8.  **Cihazları kullanıcılara dağıtma**
    Şirketinizin sahip olduğu cihazlar artık kullanıcılara dağıtılabilir. Bir iOS cihazı açıldığında Intune tarafından yönetim için kaydedilir.



### Ayrıca bkz.
[Cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


