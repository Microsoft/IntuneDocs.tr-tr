---
title: "iOS cihazlarını kaydetme - Cihaz Kayıt Programı"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Cihaz Kayıt Programı’nı kullanarak şirkete ait iOS cihazlarını kaydetmeyi öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 3e1898441b7576c07793e8b70f3c3f09f1cac534
ms.openlocfilehash: ddeaeb2d532635802c615d09b4625dee0a824919
ms.lasthandoff: 02/23/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune, Aygıt Kayıt Programı (DEP) aracılığıyla “uzaktan” satın alınmış iOS cihazlarını kaydeden bir kayıt profili dağıtabilir. Profil, cihazlara uygulamak istediğiniz yönetim ayarlarını içerir. Kayıt paketi, cihaz için kurulum yardımcısı seçeneklerini içerebilir. DEP üzerinden kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz.

>[!NOTE]
>Bu kayıt yöntemi, [cihaz kaydı yöneticisi](enroll-devices-using-device-enrollment-manager.md) yöntemiyle birlikte kullanılamaz.

Şirkete ait iOS cihazlarının Apple Aygıt Kayıt Programı (DEP) ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir:  [https://deploy.apple.com](https://deploy.apple.com). Programın sağladığı avantajlar arasında, her cihazı bir USB kablosu ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

Şirkete ait iOS cihazlarını DEP ile kaydedebilmeniz için, önce Apple’dan [bir DEP belirteci](get-apple-dep-token.md) almalısınız. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un Kayıt Profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](choose-ios-enrollment-method.md) başlığı altında açıklanır.

## <a name="prerequisites"></a>Önkoşullar

iOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM Yetkilisini ayarlama](set-mdm-authority.md)
- [Grup oluşturma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](get-an-apple-mdm-push-certificate.md)
- [Bir Apple DEP belirteci alma](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Cihazlar için Apple DEP profili oluşturma

Cihaz kayıt profili bir cihaz grubuna uygulanan ayarları tanımlar. Aşağıdaki adımlar, DEP kullanarak kaydedilmiş iOS cihazları için bir cihaz kayıt profilinin nasıl oluşturulacağını gösterir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

3. **Apple Cihaz Kayıt Programı (DEP) Ayarlarını Yönet**’in altında **DEP Profilleri**’ni seçin.

4. **Apple DEP Profilleri** dikey penceresinde **Oluştur**’u seçin.

5. **Kayıt Profili Oluştur** dikey penceresinde, profil için bir ad ve açıklama girin.

6. **Kullanıcı Benzeşimi** için, bu profile sahip cihazların kullanıcı benzeşimiyle mi yoksa kullanıcı benzeşimi olmadan mı kaydedileceğini seçin.

 - **Kullanıcı benzeşimiyle kaydet** - Cihaz ilk kurulum sırasında bir kullanıcıya bağlı olmalıdır. Böylece, cihazın şirket verilerine ve e-postalara erişmesine izin verilebilir. Kullanıcılara ait olan ve uygulamaları yükleme gibi hizmetler için şirket portalını kullanması gereken, DEP ile yönetilen cihazlarda kullanıcı benzeşimini seçin. Multifactor Authentication’ın (MFA) kullanıcı benzeşimi özellikli DEP cihazlarında kayıt sırasında çalışmayacağını unutmayın. Kayıttan sonra MFA bu cihazlar üzerinde beklendiği gibi çalışır. İlk kez oturum açarken parola değiştirmesi istenen yeni kullanıcılara, DEP cihazlarının kaydı sırasında istemde bulunulamaz. Ayrıca, parolalarının süresi dolmuş olan kullanıcılardan DEP kaydı sırasında parolalarını sıfırlamaları istenmez ve farklı bir cihazdan parolayı sıfırlamaları gerekir.

    >[!NOTE]
    >Kullanıcı benzeşimi ile DEP’in kullanıcı belirteci istemesini etkinleştirmek için WS-Trust 1.3 Kullanıcı Adı/Karma uç nokta gerekir.

 - **Kullanıcı benzeşimi olmadan kaydet** - Cihaz bir kullanıcıya bağlı değildir. Bu ilişkiyi, yerel kullanıcı verilerine erişmeden görevleri yerine getiren cihazlar için kullanın. Kullanıcı benzeşimi gerektiren uygulamalar (iş kolu uygulamalarını yüklemek için kullanılan Şirket Portalı uygulaması da dahil) çalışmaz.

7. **Cihaz Yönetim Ayarları**’nı seçin, aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Denetimli** - Daha fazla yönetim seçeneğini etkinleştiren ve varsayılan olarak Etkinleştirme Kilidi’ni devre dışı bırakan yönetim modu. Onay kutusunu boş bırakırsanız, sınırlı yönetim özelliklerine sahip olursunuz.

    - **Kilitli kayıt** - (Yönetim Modu = Denetimli seçimini gerektirir) Yönetim profilini kaldırmaya izin verebilecek iOS ayarlarını devre dışı bırakır. Onay kutusunu boş bırakırsanız, yönetim profilinin Ayarlar menüsünden kaldırılmasına izin verir. Bu öğe etkinleştirme sırasında ayarlanır ve fabrika ayarlarına sıfırlamadan değiştirilemez.

    - **Eşleştirmeye İzin Ver** - iOS cihazlarının bilgisayarlarla eşitlenip eşitlenemeyeceğini belirtir. **Sertifikaya göre Apple Configurator’a izin ver**’i seçerseniz, **Apple Configurator Sertifikaları**’nın altında bir sertifika seçmeniz gerekir.

    - **Apple Configurator Sertifikaları** - **Eşleştirmeye İzin Ver**’in altında **Sertifikaya göre Apple Configurator’a izin ver**’i seçtiyseniz, içeri aktarılacak bir Apple Configurator Sertifikası seçin.

8. **Kurulum Yardımcısı Ayarları**’nı seçin, aşağıdaki profil ayarlarını yapılandırın ve ardından **Kaydet**’i seçin:

    - **Bölüm Adı** - Kullanıcı etkinleştirme sırasında **Yapılandırma Hakkında** öğesine dokunduğunda görüntülenir.

    - **Bölüm Telefonu** - Kullanıcı etkinleştirme sırasında Yardım Gerekli düğmesine tıkladığında görüntülenir.
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
        - **Tanılama Verileri** - Etkinleştirilirse, Kurulum Yardımcısı etkinleştirme sırasında bu hizmeti sorar

9. Profil ayarlarını kaydetmek için, **Kayıt Profili Oluştur** dikey penceresinde **Oluştur**’u seçin.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>MDM sunucunuza Apple DEP seri numaraları atama

1. [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’na (https://deploy.apple.com) gidin ve şirketinizin Apple kimliğiyle oturum açın.

2. **Dağıtım Programı** &gt; **Aygıt Kayıt Programı** &gt; **Cihazları Yönet**’e gidin.

3. **Cihaz Seç** bölümünden cihaz seçim tercihinizi yapın, ardından cihaz bilgilerini sağlayın ve cihazın **Seri Numarası**, **Sipariş Numarası** bilgileriyle veya **CSV Dosyasını Karşıya Yükle** seçeneğiyle cihaz ayrıntılarını belirtin.

4. **Sunucuya Ata**'yı ve Microsoft Intune için belirtilen &lt;ServerName&gt; öğesini belirleyip **Tamam**'ı seçin.

## <a name="synchronize-dep-managed-devices"></a>DEP ile yönetilen cihazları eşitleme

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Azure Portal’ın Intune dikey penceresinde **Cihazları Kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

3. **Apple Cihaz Kayıt Programı (DEP) Ayarlarını Yönet**’in altında **DEP Seri Numaraları**’nı seçin.

4. **Apple DEP Seri Numaraları** dikey penceresinde **Eşitle**’yi seçin.

5. **Eşitle** dikey penceresinde **Eşitleme İste**’yi seçin. İlerleme çubuğu, yeniden Eşitleme istemeden önce beklemeniz gereken süreyi gösterir.

    Apple’ın kabul edilebilir DEP trafiği koşullarına uymak için, Intune aşağıdaki kısıtlamaları getirir:
     -    Tam DEP eşitlemesi en fazla yedi günde bir çalıştırılabilir. Intune tam eşitleme sırasında, Apple’ın Intune’a atadığı her seri numarasını, bu numaranın daha önceden eşitlenmiş olup olmamasına bakılmaksızın yeniler. Önceki tam eşitlemenin üzerinden yedi gün geçmeden bir tam eşitleme girişiminde bulunulursa, Intune yalnızca henüz Intune’da listelenmeyen seri numaralarını yeniler.
     -    Herhangi bir eşitleme isteğinin tamamlanması için 10 dakika verilir. Bu süre boyunca veya istek başarılı olana kadar **Eşitle** düğmesi devre dışı bırakılır.

>[!NOTE]
>Ayrıca, **Apple DEP Seri Numaraları** dikey penceresinde profillere DEP seri numaraları da atayabilirsiniz.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Şirkete ait cihazlarınızı artık kullanıcılara dağıtabilirsiniz. Bir iOS cihazı açıldığında Intune tarafından yönetim için kaydedilir.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Kullanıcıların cihazlarında Şirket Portalı’nı yüklemesi ve kullanması

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için aşağıda açıklanan ek adımları tamamlamalıdır.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Kullanıcı benzeşimi olan şirkete ait iOS cihazları kullanıcılar tarafından kaydetme

1. Kullanıcılar cihazlarını açtığında, kendilerinden Kurulum Yardımcısı’nı tamamlamaları istenir. Kurulum sırasında kullanıcılardan kimlik bilgileri istenir. Intune abonelikleriyle ilişkili kimlik bilgilerini (yani UPN olarak bilinen benzersiz kişisel adları) kullanmaları gerekir.

2. Kurulum sırasında kullanıcılardan bir Apple Kimliği istenir. Cihazın Şirket Portalı’nı yüklemesine izin vermek için bir Apple ID sağlanmalıdır. Kimlik, kurulum bittikten sonra iOS ayarları menüsünden de sağlanabilir.

3. Kurulum tamamlandıktan sonra kullanıcılar Uygulama Mağazası’ndan Şirket Portalı uygulamasını yüklemelidir.

4. Kullanıcılar artık cihazı kurarken kullandıkları UPN’yi kullanarak Şirket Portalı’nda oturum açar.

5. Oturum açtıktan sonra, kullanıcılardan cihazlarını kaydetmeleri istenir. İlk adım cihazını tanımlamaktır. Uygulama, daha önce şirket için kaydedilmiş ve kullanıcının Intune hesabına atanmış iOS cihazlarının bir listesini sunar. Kullanıcı eşleşen cihazı seçmelidir. Bu cihaz daha önce şirkete kaydedilmemişse, kullanıcı standart kayıt akışına devam etmek için yeni cihazı seçmelidir.

6. Kullanıcılar, sonraki ekranda yeni cihazın seri numarasını onaylar. Bunu yapmak için, kullanıcılar görüntülenen bağlantıyı seçer. Bağlantı, Ayarlar uygulamasını başlatır ve ardından kullanıcıların seri numarasını doğrulamasına olanak tanır. Daha sonra kullanıcılar, seri numarasının son dört karakterini Şirket Portalı uygulamasına girmelidir.

   Bu adım, cihazın Intune’a kaydedilmiş şirket cihazı olduğunu doğrular. Cihazdaki seri numarası eşleşmezse, kullanıcı yanlış cihaz seçmiş demektir. Kullanıcı önceki ekrana geri dönmeli ve farklı bir cihaz seçmelidir.

7. Seri numarası doğrulandıktan sonra Şirket Portalı uygulaması, kaydı tamamlamak üzere Şirket Portalı web sitesine yönlendirir. Web sitesi daha sonra kullanıcılardan uygulamaya dönmelerini ister.

Kayıt artık tamamlanmıştır, kullanıcılar şimdi bu cihazı tüm özellikleriyle kullanabilir.

