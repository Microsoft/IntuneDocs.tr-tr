---
title: "iOS cihazları için Apple DEP yönetimi | Microsoft Docs"
description: "Apple cihazlarını yönetmek için iOS Aygıt Kayıt Programı (DEP) aracılığıyla “uzaktan” satın alınmış iOS cihazlarını kaydeden bir kayıt profili dağıtın."
keywords: 
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 12/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8063b933a767740a7951fa69a918a8677b664d02
ms.openlocfilehash: e8a21ace32b5668f8158b9a383b882b7c2f524df


---

# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>Şirkete ait Cihaz Kayıt Programı iOS cihazlarını kaydetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Aygıt Kayıt Programı (DEP) aracılığıyla “uzaktan” satın alınmış iOS cihazlarını kaydeden bir kayıt profili dağıtabilir. Kayıt paketi, cihaz için kurulum yardımcısı seçenekleri içerebilir. DEP üzerinden kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz.

## <a name="apple-dep-management-for-ios-devices-with-microsoft-intune"></a>Microsoft Intune ile iOS cihazları için Apple DEP yönetimi
Şirkete ait iOS cihazlarının Apple Aygıt Kayıt Programı (DEP) ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir:  [https://deploy.apple.com](https://deploy.apple.com). Programın sağladığı avantajlar arasında, her cihazı bir USB kablosu ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

Şirketin sahibi olduğu iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirtecine ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un Kayıt Profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

1.  **Microsoft Intune ile iOS cihazlarını yönetmeye başlama**</br>
    iOS Aygıt Kayıt Programı (DEP) cihazlarını kaydedebilmeniz için önce Intune için iOS yönetimini etkinleştirmeniz gerekir.

2.  **Şifreleme Anahtarı Alma**</br>
    Yönetici kullanıcı olarak, [Microsoft Intune yönetici konsolunu](http://manage.microsoft.com) açın, **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Aygıt Kayıt Programı**’na gidin ve **Şifreleme Anahtarını İndir**’i seçin. Şifreleme anahtarı (.pem) dosyasını yerel olarak kaydedin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

      ![Cihaz kayıt programı belirtecini güncelleştirme](../media/dev-sa-ios-dep.png)

3.  **Aygıt Kayıt Programı belirteci edinme**</br>
    [Aygıt Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. Bu Apple kimliğinin daha sonra DEP belirtecinizi yenilemek için kullanılması gerekir.

    1.  [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**’e gidin ve **MDM Sunucusu Ekle**'ye tıklayın.

    2.  **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

    3.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

    4.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı gösterilir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'yi seçin.

    Bu sertifika (.p7m) dosyası Intune ile Apple'ın Cihaz Kayıt Programı sunucuları arasında bir güven ilişkisi oluşturmak için kullanılır.

4.  **DEP belirtecini Intune'a ekleme**</br>
    [Microsoft Intune yönetici konsolu](http://manage.microsoft.com)’nda **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Aygıt Kayıt Programı**’na gidin ve **DEP Belirtecini Karşıya Yükle**’yi seçin. Sertifika (.p7m) dosyasına **göz atın**, **Apple Kimliği**'nizi girin ve **Karşıya Yükle**’yi seçin.

5.  **Kurumsal Cihaz Kaydı İlkesini Ekleme**</br>
    [Microsoft Intune yönetici konsolu](http://manage.microsoft.com)’nda **İlke** &gt; **Kurumsal Cihaz Kaydı**’na gidin ve **Ekle**’yi seçin.

    **Ad** ve **Açıklama** dahil olmak üzere **Genel** ayrıntıları sağlayın ve profile atanmış cihazların kullanıcı benzeşimine sahip olduğunu veya bir gruba ait olduğunu belirtin.
      - **Kullanıcı benzeşimi istemi**: Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Cihazın şirket verilerine ve e-postalara bu kullanıcı aracılığıyla erişmesine izin verilmesi için bu gereklidir. DEP tarafından yönetilen kullanıcılara ait olan ve şirket portalını kullanması gereken (uygulama yüklemek için) cihazlarda **kullanıcı benzeşimi** ayarlanmalıdır. Multifactor authentication (MFA) kullanıcı benzeşimi özellikli DEP cihazlarında kayıt sırasında çalışmaz. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır. 

      > [!NOTE]
      > Kullanıcı benzeşimi ile DEP’in kullanıcı belirteci istemesini etkinleştirmek için WS-Trust 1.3 Kullanıcı Adı/Karma uç nokta gerekir.

      - **Kullanıcı benzeşimi yok**: Cihaz bir kullanıcıya bağlı değil. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri gerçekleştiren cihazlar için kullanın. İş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil olmak üzere, kullanıcı benzeşimi gerektiren uygulamalar çalışmaz.

    Ayrıca, **Aşağıdaki gruba cihazlar atayabilirsiniz**. Bir grup seçmek için **Seç...** öğesini belirleyin.

    [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    Ardından, DEP’i desteklemek için **Bu ilke için Cihaz Kayıt Programı ayarlarını yapılandırın** seçeneği etkinleştirin.

      ![Kurulum yardımcısı bölmesi](../media/pol-sa-corp-enroll.png)

     DEP ile yönetilen cihazlar için aşağıdaki ayarlar kullanılabilir:

     - **Bölüm** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir
     - **Destek telefon numarası** - Kullanıcı etkinleştirme sırasında **Yardım Gerekli** düğmesine tıkladığında görünür
     - **Hazırlık modu** - Etkinleştirme sırasında ayarlanır ve cihaz fabrika ayarlarına sıfırlanmadan değiştirilemez:
        - **Denetimsiz** -Sınırlı yönetim yetenekleri
        - **Denetimli** - Varsayılan olarak daha fazla yönetim seçeneğini etkinleştirir ve Etkinleştirme Kilidi’ni devre dışı bırakır
     - **Kayıt profilini cihaza kilitle** - Etkinleştirme sırasında ayarlanır ve fabrika ayarlarına sıfırlamadan değiştirilemez
        - **Devre dışı bırak** - Yönetim profilinin **Ayarlar** menüsünden kaldırılmasına olanak tanır
        - **Etkinleştir** - (**Hazırlık Modu** = **Denetimli** gerektirir) Yönetim profilinin kaldırılmasına olanak tanıyabilecek iOS ayarlarını devre dışı bırakır
     - **Kurulum Yardımcısı Seçenekleri** - Bu isteğe bağlı ayarlar daha sonra iOS **Ayarlar** menüsünden ayarlanabilir.
        - **Geçiş kodu** - Etkinleştirme sırasında geçiş kodu ister. Cihaz güvenlik altına alınmayacaksa veya başka bir yolla erişim denetimi sağlanmamışsa (cihazı tek uygulamayla sınırlandıran bilgi noktası modu), her zaman geçiş kodu gerektirir.
        - **Konum Hizmetleri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında hizmeti sorar
        - **Geri Yükle** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında iCloud yedeklemesini sorar
        - **Apple kimliği** - Etkinleştirilirse, Intune kimlik girilmeden bir uygulama yüklemeyi denediğinde iOS kullanıcılardan Apple kimliği ister. Intune tarafından yüklenenler de dahil olmak üzere, iOS Uygulama Mağazası uygulamalarını indirmek için Apple Kimliği gerekir.
        - **Hüküm ve Koşullar** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında kullanıcılardan Apple’ın hüküm ve koşullarını kabul etmelerini ister
        - **Touch ID** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple Pay** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Zoom** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Siri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
        - **Apple’a tanılama verileri gönder** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar
     -  **Ek Apple Configurator yönetimini etkinleştir** - Dosyaların Apple Configurator üzerinden iTunes ile veya yönetimle eşitlenmesini önlemek için **İzin Verme**olarak ayarlayın. Bu ayarı kullanarak sertifikalı veya sertifikasız el ile dağıtıma izin vermek yerine, **İzin Verme** seçeneğini belirlemek, diğer yapılandırmaları Apple Configurator’dan dışarı aktarmak ve ardından Intune üzerinden Özel iOS yapılandırma profili olarak dağıtmak iyi bir fikirdir.
        - **İzin Verme** - Cihazın USB üzerinden iletişim kurmasını önler (eşlemeyi devre dışı bırakır)
        - **İzin Ver** - Herhangi bir PC veya Mac bilgisayar için bir cihazın USB bağlantısı üzerinden iletişim kurmasına izin verir
        - **Sertifika gerektir** - Kayıt profiline aktarılan bir sertifika kullanılarak Mac bilgisayarla eşlemeye izin verir

6.  **Yönetim için DEP Cihazları Atama** [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın. **Dağıtım Programı** &gt; **Aygıt Kayıt Programı** &gt; **Cihazları Yönet**’e gidin. **Cihaz Seç**bölümünden cihaz tercihinizi yapın, cihaz bilgilerini belirtin ve **Seri Numarası**, **Sipariş Numarası**bilgileriyle veya **CSV Dosyasını Karşıya Yükle**seçeneğiyle cihaz ayrıntılarını belirtin. Ardından, **Sunucuya Ata**’yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

7.  **DEP ile Yönetilen Cihazları Eşitleme** Yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS** &gt; **Aygıt Kayıt Programı**’na gidin ve **Şimdi eşitle**'yi seçin. Apple'a bir eşitleme isteği gönderilir. Eşitleme sonrasında DEP ile yönetilen cihazları görmek için [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Şirketin Önceden Kayıtlı Cihazları** &gt; **iOS Seri Numarasına Göre**’ye gidin. **iOS Seri Numarasına Göre** çalışma alanında yönetilen cihazlar için **Durum**, cihaz çalıştırılıp kayıt için Kurulum Yardımcısı çalıştırılana kadar “Bağlantı kurulmadı” olarak gösterilir.

    Apple’ın kabul edilebilir DEP trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -  Tam DEP eşitlemesi en fazla yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -  Herhangi bir eşitleme isteğinin tamamlanması için 10 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

8.  **Cihazları kullanıcılara dağıtma** Şirketinizin sahip olduğu cihazlar artık kullanıcılara dağıtılabilir. Bir iOS cihazı açıldığında Intune tarafından yönetim için kaydedilir.

## <a name="changes-to-intune-group-assignments"></a>Intune grubu atamalarına değişiklikler

2016 Aralık ayından başlayarak cihaz grup yönetimi Azure Active Directory’ye taşınıyor. Azure Active Directory gruplarına geçişten sonra grup ataması **Kurumsal Kayıt Profili** seçeneklerinde görünmeyecektir. Bu değişiklik birkaç ay boyunca sunulacağından, değişikliği hemen göremeyebilirsiniz. Yeni portala geçildikten sonra, Kurumsal Kayıt Profili adlarını temel alan dinamik cihaz grubu atamaları tanımlanabilir. Bu işlem bir cihaz grubuna atanmış cihazların, ilke ve uygulamaları dağıtılmış bir şekilde otomatik olarak gruba kaydolmasını sağlar. [Azure Active Directory grupları hakkında daha fazla bilgi edinin](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/)

### <a name="see-also"></a>Ayrıca bkz.
[Cihaz kaydetme önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO1-->


