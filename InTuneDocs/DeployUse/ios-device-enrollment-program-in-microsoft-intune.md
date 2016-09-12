---
title: "iOS cihazları için Apple DEP yönetimi | Microsoft Intune"
description: "Apple cihazlarını yönetmek için, iOS Cihaz Kayıt Programı (DEP) aracılığıyla “uzaktan” satın alınmış iOS cihazlarını kaydeden bir kayıt profili dağıtın."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e0d05a4f229e2a8e72d1d60021b159f12dfa0d1
ms.openlocfilehash: c63badfcbc736476f17b39e09ef189eb4d2c08ef


---

# Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme
Microsoft Intune, Cihaz Kayıt Programı (DEP) aracılığıyla “uzaktan” satın alınmış iOS cihazlarını kaydeden bir kayıt profili dağıtabilir. Kayıt paketi, cihaz için kurulum yardımcısı seçenekleri içerebilir. DEP ile kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz.

## Microsoft Intune ile iOS cihazları için Apple DEP yönetimi
Şirkete ait iOS cihazlarının Apple Cihaz Kaydı Programı (DEP) ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir:  [https://deploy.apple.com](https://deploy.apple.com). Programın sağladığı avantajlar arasında, her cihazı bir USB ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

Şirketin sahi olduğu iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirtecine ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un Kayıt Profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

1.  **Microsoft Intune ile iOS cihazlarını yönetmeye başlama** iOS Cihaz Kaydı Programı (DEP) cihazlarını kaydedebilmeniz için önce Intune için iOS yönetimini etkinleştirmeniz gerekir.

2.  **Şifreleme Anahtarı Alma** Yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**'na gidin ve **Şifreleme Anahtarını İndir**'e tıklayın. Şifreleme anahtarı (.pem) dosyasını yerel olarak kaydedin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

      ![Cihaz kayıt programı belirtecini güncelleştirme](../media/dev-sa-ios-dep.png)

3.  **Cihaz Kayıt Programı belirteci alma** [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. Bu Apple kimliğinin gelecekte DEP belirtecinizi yenilemek için kullanılması gerekir.

    1.  [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**’e gidin ve **MDM Sunucusu Ekle**'ye tıklayın.

    2.   **MDM Sunucu Adı** 'nı girin ve ardından **İleri**'ye tıklayın. Sunucu adı, MDM sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

    3.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesine tıklayarak .pem dosyasını karşıya yükleyin ve ardından **İleri**'ye tıklayın.

    4.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı görüntülenir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'ye tıklayın.

    Bu sertifika (.p7m) dosyası Intune ile Apple'ın Cihaz Kayıt Programı sunucuları arasında bir güven ilişkisi oluşturmak için kullanılır.

4.  **DEP belirtecini Intune'a ekleme** [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**’na gidin ve **DEP Belirtecini Karşıya Yükle**’ye tıklayın. **Sertifika** (.p7m) dosyasına göz atın, **Apple Kimliği**'nizi girin ve **Karşıya Yükle**öğesine tıklayın.

5.  **Kurumsal Cihaz Kayıt İlkesi Ekleme** [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle**'ye tıklayın.

    **Ad** ve **Açıklama** dahil olmak üzere **Genel** ayrıntıları sağlayın, profile atanmış cihazların kullanıcı benzeşimine sahip olduğunu veya bir gruba ait olduğunu belirtin.
      - **Kullanıcı benzeşimi sor**: Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara bu kullanıcı aracılığıyla erişmesine izin verilebilir.  DEP tarafından yönetilen kullanıcılara ait olan ve şirket portalını kullanması gereken (örneğin, uygulama yüklemek için) cihazlarda **kullanıcı benzeşimi** yapılandırılmalıdır.
      - **Kullanıcı benzeşimi yok**: Cihaz bir kullanıcıya bağlı değil. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. İş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da içinde olmak üzere, kullanıcı benzeşimi gerektiren uygulamalar çalışmaz.

    Ayrıca, **Aşağıdaki gruba cihazlar atayabilirsiniz**. Bir grup seçmek için, **Seç...** öğesine tıklayın.

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Ardından, DEP’i desteklemek için **Bu ilke için Cihaz Kayıt Programı ayarlarını yapılandırın** seçeneği etkinleştirin.

      ![Kurulum yardımcısı bölmesi](../media/pol-sa-corp-enroll.png)

     DEP ile yönetilen cihazlar için aşağıdaki ayarlar kullanılabilir:

     - **Bölüm** - Kullanıcı etkinleştirme sırasında "Yapılandırma Hakkında" öğesine dokunduğunda görüntülenir
     - **Destek telefon numarası** - Kullanıcı etkinleştirme sırasında **Yardım Gerekli** düğmesine tıkladığında görüntülenir
     - **Hazırlık modu** - Bu durum bilgisi etkinleştirme sırasında ayarlanır ve cihaz fabrika ayarlarına sıfırlanmadan değiştirilemez:
        - **Denetimsiz** -Sınırlı yönetim yetenekleri
        - **Denetimli** - Varsayılan olarak daha fazla yönetim seçeneğini etkinleştirir ve Etkinleştirme Kilidi’ni devre dışı bırakır
     - **Kayıt profilini cihaza kilitle** - Bu durum bilgisi etkinleştirme sırasında ayarlanır ve fabrika ayarlarına sıfırlamadan değiştirilemez:
        - **Devre dışı bırak** - Yönetim profilinin **Ayarlar** menüsünden kaldırılmasına olanak tanır
        - **Etkinleştir** - (**Hazırlık Modu** = **Denetimli** gerektirir) Yönetim profilinin kaldırılmasına olanak tanıyabilecek iOS ayarlarını devre dışı bırakır
     - **Kurulum Yardımcısı Seçenekleri** - Bu ayarlar isteğe bağlıdır ve daha sonra iOS **Ayarlar** menüsünde yapılandırılabilir
        - **Geçiş kodu** - Etkinleştirme sırasında geçiş kodu ister. Cihaz güvenlik altına alınmayacaksa veya başka bir yolla erişim denetimi sağlanmamışsa (örneğin, cihazı tek uygulamayla sınırlandıran bilgi noktası modu), her zaman geçiş kodu gerektirir.
        - **Konum Hizmetleri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında hizmeti sorar
        - **Geri Yükle** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında iCloud yedeklemesini sorar
        - **Apple Kimliği** - Intune tarafından yüklenenler de içinde olmak üzere, iOS Uygulama Mağazası uygulamalarını indirmek için Apple Kimliği gerekir. Etkinleştirilirse, Intune kimlik girilmeden bir uygulama yüklemeyi denediğinde iOS kullanıcılardan Apple Kimliği ister.
        - **Hüküm ve Koşullar** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister
        - **Touch ID** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple Pay** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Zoom** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Siri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple’a tanılama verileri gönder** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
     -  **Ek Apple Configurator yönetimini etkinleştir** - Dosyaların Apple Configurator üzerinden iTunes ile veya yönetimle eşitlenmesini önlemek için **İzin Verme**olarak ayarlayın. Microsoft, bu ayarı kullanarak sertifikalı veya sertifikasız el ile dağıtıma izin vermek yerine, **İzin Verme** olarak ayarlamanızı, diğer yapılandırmaları Apple Configurator’dan dışarı aktarmanızı ve ardından Intune üzerinden Özel iOS yapılandırma profili olarak dağıtmanızı önerir.
        - **İzin Verme** - Cihazın USB üzerinden iletişim kurmasını önler (eşlemeyi devre dışı bırakır)
        - **İzin Ver** - Herhangi bir PC veya Mac bilgisayar için cihazın USB bağlantısı üzerinden iletişim kurmasına izin verir
        - **Sertifika gerektir** - Kayıt profiline aktarılan bir sertifika kullanılarak Mac bilgisayarla eşlemeye izin verir

6.  **Yönetim için DEP Cihazları Atama** [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. **Dağıtım Programı** &gt; **Cihaz Kayıt Programı** &gt; **Cihazları Yönet**’e gidin.  **Cihaz Seç**bölümünden cihaz tercihinizi yapın, cihaz bilgilerini belirtin ve **Seri Numarası**, **Sipariş Numarası**bilgileriyle veya **CSV Dosyasını Karşıya Yükle**seçeneğiyle cihaz ayrıntılarını belirtin. Ardından, **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;SunucuAdı&gt; öğesini seçip **Tamam**'a tıklayın.

7.  **DEP ile Yönetilen Cihazları Eşitleme** Yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Cihaz Kayıt Programı**’na gidin ve **Şimdi eşitle**'ye tıklayın. Apple'a bir eşitleme isteği gönderilir. Eşitleme sonrasında DEP ile yönetilen cihazları görmek için [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Şirkete Ait Tüm Cihazlar**’a gidin. **Şirkete Ait Cihazlar** çalışma alanında yönetilen cihazlar için **Durum**, cihaz çalıştırılıp cihaz kaydı için Kurulum Yardımcısı çalıştırılana kadar “Bağlantı kurulmadı” olarak gösterilir.

    Apple’ın kabul edilebilir DEP trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -  Tam DEP eşitlemesi 7 günde birden daha sık çalıştırılamaz. Tam eşitleme sırasında, Intune Apple’ın Intune’a atadığı her seri numarasını (bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın) yeniler. Önceki tam eşitlemenin üzerinden 7 gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 10 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar Eşitle düğmesi devre dışı bırakılır.

8.  **Cihazları kullanıcılara dağıtma** Şirketinizin sahip olduğu cihazlar artık kullanıcılara dağıtılabilir. Bir iOS cihazı açıldığında Intune tarafından yönetim için kaydedilir.

## Intune grubu atamalarına değişiklikler

Eylül ayından başlayarak cihaz yönetimi Azure Active Directory’ye taşınacaktır. Azure Active Directory gruplarına geçişten sonra grup ataması **Kurumsal Kayıt Profili** seçeneklerinde görünmeyecektir. Bu değişiklik birkaç ay boyunca sunulacağından, değişikliği hemen göremeyebilirsiniz. Azure Active Directory’de, Kurumsal Kayıt Profili adına göre yeni dinamik cihaz grupları ataması tanımlanabilir. Bu işlem bir cihaz grubuna önceden atanmış cihazların, ilke ve uygulamaları dağıtılmış bir şekilde otomatik olarak gruba kaydolmasını sağlar. [Azure Active Directory grupları hakkında daha fazla bilgi edinin.](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### Ayrıca bkz.
[Cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


