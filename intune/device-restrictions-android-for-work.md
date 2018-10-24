---
title: Microsoft Intune - Azure’da Android iş profili cihaz kısıtlamaları | Microsoft Docs
description: Android Kurumsal profili cihazlarda kopyalama ve yapıştırma, bildirim gösterme, uygulama izinleri, veri paylaşımı, parola uzunluğu, oturum açma hataları, kilidi açmak için parmak izi kullanma, parolaları yeniden kullanma ve iş kişileriyle Bluetooth paylaşımını etkinleştirme gibi bazı ayarları kısıtlayabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6a633b73856b5f9f50ffe0b9993713b888b969b
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828151"
---
# <a name="work-device-restriction-settings-in-intune"></a>Intune'da Work cihaz kısıtlama ayarları

Bu makalede, Android Kurumsal profilli cihazlar için yapılandırabileceğiniz Microsoft Intune cihaz kısıtlama ayarları listelenmektedir.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>İş profili ayarları

### <a name="general-settings"></a>Genel Ayarlar

- **İş profilleri ve kişisel profiller arasında kopyalama ve yapıştırma**: İş uygulamaları ve kişisel uygulamalar arasında kopyalama ve yapıştırma işlemlerini denetler. Engellemeyi etkinleştirmek için **Engelle**’yi seçin. Engellemeyi devre dışı bırakmak için **Yapılandırılmadı**’yı seçin.
- **İş ve kişisel profiller arasında veri paylaşımı**: İş profilindeki uygulamaların kişisel profildeki uygulamalarla paylaşıp paylaşamayacağını denetleyin. Bu ayar, örneğin Chrome tarayıcı uygulamasındaki **Paylaş…** seçeneği gibi uygulamalardaki paylaşma eylemlerini denetler. Bu ayar, kopyala/yapıştır pano davranışında geçerli değildir. [Uygulama koruma ilkesi ayarlarından](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) farklı olarak, cihaz kısıtlama ayarları Intune portalından yönetilir ve yönetilen uygulamaları yalıtmak için Android iş profili bölümünü kullanır. Aşağıdakilerden birini seçin:
  - **Varsayılan paylaşım kısıtlamaları**: Cihazın, Android sürümüne göre farklılık gösteren varsayılan paylaşım davranışı. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Sürüm 6.0 ve üzerini çalıştıran cihazlarda Google kişisel profilden iş profiline paylaşımı engellemez.
  - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir**: Kişisel profilden iş profiline paylaşıma izin veren yerleşik Android özelliğini etkinleştirir. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
  - **Sınırlar arası paylaşıma izin ver**: İş profili sınırının ötesinde her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar iş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmındaki uygulamalarla paylaşmasına izin verir. Bu nedenle bu ayarı dikkatli kullanın.

- **Cihaz kilitliyken iş profili bildirimleri**: İş profilindeki uygulamaların cihaz kilitliyken bildirimlerde veri gösterip gösteremeyeceğini denetler.
- **Varsayılan uygulama izinleri**: İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilkeyi istem kullanmadan otomatik olarak izinler vermek, izin vermeyi reddetmek veya kararı kullanıcıya bırakmak için kullanabilirsiniz. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Sor**
  - **Otomatik olarak izin ver**
  - **Otomatik olarak reddet**

    Ayrıca tek tek uygulamalara izinler vermek için bir Uygulama Yapılandırma ilkesi de kullanabilirsiniz (**İstemci Uygulamaları** > **Uygulama yapılandırma ilkeleri**).

- **Hesap ekleme ve kaldırma**

   Son kullanıcıların iş profiline el ile hesap eklemesini veya profilden hesap kaldırmasını önler.

   Örneğin, Gmail uygulamasını bir Android iş profiline dağıttığınızda, son kullanıcıların bu iş profiline hesap eklemesini veya buradan kaldırmasını engelleyebilirsiniz.

- **Bluetooth ile kişi paylaşımı**: Bluetooth kullanarak eşleştirilmiş bir cihazdan, örneğin araba, iş kişilerine erişime izin verir. Bu ayar varsayılan olarak yapılandırılmamıştır ve iş profili kişileri gösterilmez. Bu paylaşıma izin verip iş profili kişilerini görüntülemek için **Etkinleştir**’i seçin. Bu ayar, Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları için geçerlidir. Bu ayarı etkinleştirmek, bazı Bluetooth cihazlarının ilk bağlantı sırasında iş kişilerini önbelleğe almasına izin verebilir. İlk eşleme/eşitleme sonrasına bunu devre dışı bırakmak ise Bluetooth cihazından iş kişilerini kaldırmayabilir.

- **Ekran yakalama**: İş profili olan cihazlarda ekran yakalamayı engeller. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller.

- **Kişisel profilde iş kişisi arayan kimliğini görüntüle**: Etkinleştirildiğinde (Yapılandırılmadı), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Engellendiğinde ise iş kişisi arayan numarası kişisel profilde görüntülenmez. Android işletim sistemi v6.0 ve daha yeni sürümlerde geçerlidir.

- **Kamera**: İş profili olan cihazda kamerayı engeller. Kişisel taraftaki kamera, bu ayardan etkilenmez.

### <a name="work-profile-password"></a>İş profili parolası

- **İş Profili Parolası Gerektir**: İş profilinin etkinleştirildiği Android 7.0 ve üzerine uygulanır. Yalnızca iş profilindeki uygulamalar için geçerli olacak bir geçiş kodu ilkesi tanımlayın. Varsayılan olarak, son kullanıcı birbirinden ayrı tanımlanmış iki PIN kullanabilir veya PIN’leri iki PIN'den daha güçlü olanın altında birleştirmeyi seçebilir.
- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**16** arasından belirtin.
- **İş profili kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: İş profili kilitlenmeden önce geçmesi gereken süreyi seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: İş profili cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)**: Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle**: Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak iziyle kilit açma**: Son kullanıcıların cihaz kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını engeller.
- **Akıllı Kilit ve diğer güven aracıları**: Uyumlu cihazlarda Akıllı Kilit özelliğini denetleyin. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdaysa iş profili parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

## <a name="device-password"></a>Cihaz parolası

- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**14** arasından belirtin.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçmesi gereken süreyi seçin
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Tüm veriler cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin
- **Parola kullanım süresi sonu (gün)**: Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası)
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle**: Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak iziyle kilit açma**: Son kullanıcının cihaz kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını engeller.
- **Akıllı Kilit ve diğer güven aracıları**: Uyumlu cihazlarda Akıllı Kilit özelliğini denetleyin. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

## <a name="system-security"></a>Sistem güvenliği

- **Uygulamalarda tehdit taraması**: İş profillerinde ve kişisel profillerde **Uygulamaları Doğrula** ayarının açık olmasını zorunlu tutar.

   > [!Note]
   > Bu ayar yalnızca Android O ve üstü cihazlarda çalışır.

## <a name="connectivity"></a>Bağlantı

- **Her Zaman Açık VPN**: Bir VPN istemcisini VPN'ye otomatik olarak bağlanmak ve yeniden bağlanmak üzere ayarlamak için **Etkinleştir**'i seçin. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin. 

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: Her Zaman Açık'ı destekleyen bir VPN istemcisini seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play mağazasına uygulamanın paket kimliğini girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

    > [!IMPORTANT]
    >  - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
    >  - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.

- **Kilitleme modu**: Tüm ağ trafiğini VPN tünelini kullanmaya zorlamak için **Etkinleştir**'i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="next-step"></a>Sonraki adım

Kullanıcılara ve cihazlara [profiller atama](device-profile-assign.md).
