---
title: "Intune ve son kullanıcı uygulamaları arabirimlerinde yapılan güncelleştirmeler"
description: "Son kullanıcı cihazlarında Intune ile çalışan uygulamalar için kullanıcı arabiriminde yapılan değişiklikleri keşfedin."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 33d1f28cd5522ed47c3fdf83b289116728ded12b
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune ve son kullanıcı uygulamaları arabirimlerinde yapılan güncelleştirmeler
Son kullanıcılarınızın Microsoft Intune’un bu sürümünde göreceği uygulamalar için kullanıcı arabiriminde sunulan güncelleştirmeler hakkında bilgi edinin. Bu yenilikler, kullanıcılarınızla iletişim kurmanızı kolaylaştırmanın yanı sıra dağıtımınızı desteklemek için oluşturduğunuz özel belgeler için sunacağınız güncelleştirmeler konusunda size yardımcı olabilir. Bu ayrıca son kullanıcılarınız Şirket Portalını kullanarak destek için yardım masasını ararlarsa, karşılaştıkları sorunları daha iyi nasıl çözebileceğinizi anlamanıza da yardımcı olur.

## <a name="week-of-august-14-2017"></a>14 Ağustos 2017 Haftası

### <a name="updates-to-the-device-details-page-on-the-company-portal-app-for-windows-10"></a>Windows 10 için Şirket Portalı uygulamasının “Cihaz Ayrıntıları”sayfasına güncelleştirmeler

Windows 10 için Şirket Portalı uygulaması, __Kategori__ etiketini başlığın altından __Cihaz Ayrıntıları__ sayfasındaki bir özelliğe taşıyor.

![Windows için Şirket Portalı uygulaması, “Kategoriler” alanını “Cihaz Ayrıntıları” ekranındaki başlığın altında göstermek yerine artık bir özellik olarak gösteriyor.](./media/cp_win10_category_tag_move_after_1708.png)

## <a name="week-of-july-31-2017"></a>31 Temmuz 2017 Haftası

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Tüm platformlar için Şirket Portalı uygulamalarında gelişmiş oturum açma deneyimi <!--User Story 1132123-->

Android, iOS ve Windows için Intune Şirket Portalı uygulamalarında oturum açma deneyimini geliştirecek bir değişikliği önümüzdeki birkaç ay içinde piyasaya süreceğiz. Yeni kullanıcı deneyimi, Azure AD bu değişikliği gerçekleştirdiğinde Şirket Portalına yönelik tüm platformlarda görünecektir. Ayrıca, kullanıcılar artık tek kullanımlık bir kod ile başka bir cihazdan Şirket Portalında oturum açabilir. Bu, özellikle kullanıcıların kimlik bilgileri olmadan oturum açması gerektiğinde faydalıdır.  

Aşağıda önceki oturum açma deneyimini, kimlik bilgileriyle yeni oturum açma deneyimini ve yeni başka bir cihazdan oturum açma deneyimini görebilirsiniz.

__Önceki oturum açma deneyimi__

![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Altındaki ise "Oturum aç" düğmesidir. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](./media/cp_ios_aad_signin_before_1704_001.png)

![Oturum aç düğmesine dokunduktan sonra, kullanıcı, e-posta adresi ve parolasının sorulduğu kimlik bilgilerini bu sayfaya girer ve ayrıca parola hatalarının giderilmesi için kendisine yollar önerilir.](./media/cp_ios_aad_signin_before_1704_002.png)

![Parolasını girdikten sonra, Şirket Portalı uygulaması oturum açar ve bu yükleme çubuğuyla gösterilir.](./media/cp_ios_aad_signin_before_1704_003.png)

__Yeni oturum açma deneyimi__

![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Altındaki ise "Oturum aç" düğmesidir. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](./media/cp_ios_aad_signin_after_1704_001.png)

![Kullanıcı aynı ekranda hem e-posta adresini hem de parolasını girmek yerine yalnızca kendi e-posta adresini girer.](./media/cp_ios_aad_signin_after_1704_002.png)

![E-posta adresi kabul edildikten sonra kullanıcıdan parolası istenir.](./media/cp_ios_aad_signin_after_1704_003.png)

![Kimlik doğrulama işleminden sonra, Şirket Portalı uygulaması oturum açar ve bunu bir yükleme çubuğuyla belirtir.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Başka bir cihazdan oturum açarken yeni oturum açma deneyimi__

![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Altındaki ise "Oturum aç" düğmesidir. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

__Başka bir cihazdan oturum aç__ bağlantısına dokunun.

![İş bilgisayarınızdan benzersiz bir geçiş kodu ile aka.ms/devicelogin sayfasına gidip oturum açmak için bu kodu kullanmaya ilişkin yönergeler sağlanır.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Bir tarayıcı başlatın ve [https://aka.ms/devicelogin](https://aka.ms/devicelogin) adresine gidin.

![Kullanıcının Şirket Portalı uygulamasındaki tarayıcı yerine iş bilgisayarındaki tarayıcısının bir resmi. Görüntülenen "Cihaz oturum açma" sayfası kullanıcıdan Şirket Portalı uygulamasından aldığı kodu girmesini ister.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Şirket Portalı uygulamasında gördüğünüz kodu girin. __Devam et__’i seçerseniz, akıllı kart gibi şirketiniz tarafından desteklenen herhangi bir yöntemi kullanarak kimlik doğrulaması yapmanız mümkün olacaktır.

![Kullanıcı kendi benzersiz kodunu alana girmiştir ve "Cihaz oturum açma" sitesi Intune Şirket Portalı’nın oturum açmak üzere yetkilendirilecek doğru uygulama olup olmadığının doğrulanmasını istemiştir.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Bir onay sayfası, kullanıcının kendi cihazında Şirket Portalı uygulamasında oturum açtığını ve bu sayfanın artık kapatılabileceğini belirtir.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

Şirket Portalı uygulaması oturum açmaya başlar.

![Kimlik doğrulama işleminden sonra, Şirket Portalı uygulaması oturum açar ve bunu bir yükleme çubuğuyla belirtir.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="week-of-june-12-2017"></a>12 Haziran 2017 haftası

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android için Şirket Portalı uygulamasının artık Uygulama Koruma İlkeleri için yeni bir son kullanıcı deneyimi vardır <!--1305217-->
Müşteri geri bildirimi doğrultusunda, Android için Şirket Portalı uygulamasını bir **Şirket İçeriğine Eriş** düğmesi gösterecek şekilde değiştirdik. Amaç, son kullanıcıların yalnızca, Intune mobil uygulama yönetiminin bir özelliği olan Uygulama Koruma İlkelerini destekleyen uygulamalara erişmek için gereksiz yere kayıt işlemi yapmalarını engellemektir.

Kullanıcı, cihazı kaydetmeye başlamak yerine **Şirket İçeriğine Eriş** düğmesine dokunur.

![Android Şirket Portalı uygulamasının, standart olarak yapıldığı gibi hemen kaydolma seçenekleri sunmak yerine ortada büyük boy "Şirket İçeriğine Eriş" metnini gösteren bir görüntü](./media/and_access_company_content_after_1706.png)

Kullanıcı, uygulamaya kendi cihazında kullanma izni almak için Şirket Portalı web sitesine yönlendirilir, Şirket Portalı web sitesi de kullanıcının kimlik bilgilerini doğrular.

![Şirket Portalı web sitesinin oturum açma doğrulamasını gösteren görüntü.](./media/and_iwp_sign_in_auth_page_after_1706.png)

Cihaz, yine de **eylem** menüsüne dokunularak tam yönetime kaydedilebilir.

![Android için Şirket Portalı uygulamasının, ekranın sağ üst köşesinden cihazı kaydetme seçeneği sunan menüyü gösteren bir görüntüsü.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri <!--676505-->

Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi artık otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek.

![Windows 10 Şirket Portalı uygulamasının Microsoft Word'ü Şirket Portalı uygulama mağazasından indirmenin bekleme durumunda olduğu bir görüntüsü.](./media/w10_download_pending_after_1706.png)

![Windows 10 Şirket Portalı uygulamasının yeni otomatik eşitleme durumunun cihazın eşitlenmekte olduğunu ve uygulamayı indirmenin denendiğini belirten bir durum iletisiyle gösterildiği bir görüntüsü.](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!---1058938--->
Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının adım adım yönlendirildiği bir Intune deneyimi içerecek. Yeni deneyim, kullanıcıya Azure Active Directory kaydı sürecinde (Koşullu Erişim özelliklerinde gereklidir) ve MDM kaydı sürecinde (cihaz yönetim özellikleri için gereklidir) kılavuzluk eden adım adım yönergeler sağlıyor. Kılavuzluk destekli deneyime Şirket Portalı giriş sayfasından erişilebilecek. Kullanıcılar, cihaz kaydettirme ve kaydolma işlemlerini tamamlamasa da uygulamayı kullanmaya devam edebilecek, ancak sınırlı bir işlevsellikleri olacak.

Bu güncelleştirme yalnızca Windows 10 Yıldönümü Güncelleştirmesi (derleme 1607) veya üzerini çalıştıran cihazlarda görünür.

![Windows 10 Şirket Portalı uygulamasının açılış sayfasının, ortada "cihazlar" listesinde bir kullanıcıya kullandıkları cihazın henüz kurumsal kullanım için ayarlanmadığını ve kullanıcının ayarı başlatmak için iletiyi seçmesi gerektiğini söyleyen bir durum iletisiyle görüntüsü.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Windows 10 Şirket Portalı uygulaması ayarlama sayfasının, kullanıcıyı bu cihaza bir kurumsal hesap eklemesi gerektiği, daha sonra cihazı yönetime kaydedebileceği konusunda uyaran bir görüntüsü.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Windows 10 Şirket Portalı uygulaması bu cihaza kurumsal hesap ekleme sayfasının, kullanıcıya Ayarlar uygulamasına gidip kaydı tamamlamak için "Bağlan"ı seçmesini söyleyen bir görüntüsü. Bu işlemden sonra ekran, kullanıcıya kaydı tamamlamak için Şirket Portalı uygulamasına dönmesi gerektiğini söyler.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Windows 10 Şirket Portalı uygulaması yönetime kaydolma ekranının, kullanıcı cihazının artık kayıtlı olduğunu ve devam etmek için 'ileri' düğmesine basması gerektiğini söyleyen bir tamamlanma iletisini gösteren bir görüntüsü.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Windows 10 Şirket Portalı uygulaması tamamlanma ekranının, kullanıcıya ayarlarının tamamlandığını ve cihazın üzerine düzgün olarak eklenmiş bir kurumsal hesap ile kaydedildiğini bildiren bir görüntüsü.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Şirket Portalını kolayca kaldırmak için yeni menü eylemi <!--1164569-->
Kullanıcı geri bildirimi doğrultusunda, Android için Şirket Portalı uygulaması, Şirket Portalını cihazınızdan kaldırmak için yeni bir menü eylemi ekledi. Bu eylem cihazı Intune yönetiminden kaldırır, böylece uygulama cihazdan kullanıcı tarafından kaldırılabilir.

![Android Şirket Portalı uygulamasının bir görüntüsü, eylem menüsüyle birlikte sağ üst köşede açılır. Yeni "şirket portalını kaldır" seçeneği; "profilim" ve "ayarlar" seçeneklerinin altında ve "hüküm ve koşullar", "yardım ve geri bildirim" ve "hakkında" seçeneklerinin üstünde üçüncü bir seçenek olarak bulunur.](./media/android_remove_cp_menu_action_after_1705.png)

![Eylem menüsünden "şirket portalını kaldır" seçeneği işaretlendikten sonra görünen onay iletişim kutusunun bir görüntüsü. İletişim kutusu, kullanıcıyı "şirket portalını kaldırdığınızda, cihazınız artık BT yöneticiniz tarafından yönetilmeyecek ve şirket verilerine, şirket uygulamalarına ve şirket e-postasına erişim kaldırılabilir" metniyle bilgilendirir. Ardından kullanıcıdan Şirket Portalı uygulamasını kaldırmak istediğini "Evet"'i seçerek onaylamasını ister.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>5 Haziran 2017 haftası

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS için Şirket Portalı uygulamasındaki uygulama kutucukları geliştirmeleri
Şirket Portalı için ayarladığınız marka rengini yansıtmak için giriş sayfasındaki uygulama kutucuklarının tasarımı güncelleştirildi.

**Önce**

!["Tüm uygulamalar", "öne çıkan uygulamalar" ve "kategoriler" için önceden belirlenmiş dolgu görüntüleri gösteren, güncelleştirme öncesi iOS için Şirket Portalı uygulamasının görüntüsü.](./media/cp_ios_homepage_before_1705.png)

**Sonra**

![Artık kuruluşunuz için istediğiniz rengi seçmenize izin verme özelliğiyle iOS için Şirket Portalı uygulamasının güncelleştirme sonrası görüntüsü.](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS Şirket Portalı uygulaması için artık hesap seçici kullanılabilir
Kullanıcılar iOS cihazlarında diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesapları kullandıysa Şirket Portalında ilk oturum açışlarında yeni hesap seçiciyi görebilirler.

![Bir sınama kullanıcısı olan “Robin Swanson”un iki e-posta adresinden birini seçmesini gösteren, hesap seçicinin bir görüntüsü. İki adresin altında kullanıcının farklı bir hesapla oturum açmasını sağlayan bir düğme bulunur.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>Nisan 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser ve Şirket Portalı için yeni simgeler <!--918433, 918431-->

Managed Browser uygulamasının hem Android hem de iOS sürümlerinin simgesi güncelleştiriliyor. Yeni simgede Enterprise Mobility + Security (EM+S) paketindeki diğer uygulamalarla tutarlı hale getirmek için güncelleştirilmiş Intune rozeti bulunacak.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Şirket Portalı uygulamasının da Android, iOS ve Windows sürümlerinin simgeleri EM+S paketindeki diğer uygulamalarla daha tutarlı hale getirilmek üzere güncelleştiriliyor. Bu simgeler nisan ayından başlayarak mayıs ayının sonuna kadar kademeli olarak kullanıma sunulacak.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android Şirket Portalı uygulamasında oturum açma ilerleme göstergesi <!--953374-->

Android Şirket Portalı uygulamasında yapılan güncelleştirme ile kullanıcı uygulamayı başlattığında veya sürdürdüğünde oturum açma ilerleme göstergesi görüntüleniyor. Kullanıcının uygulamaya erişmesine izin verilmeden önce göstergede "Bağlanıyor..." ile başlayıp sırasıyla "Oturum açılıyor..." ve "Güvenlik gereksinimleri denetleniyor..."durumları gösteriliyor.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Geliştirilmiş Windows 10 Şirket Portalı uygulaması yükleme durumu <!--676495-->
Windows 10 Şirket Portalı uygulaması, artık uygulama ayrıntıları sayfasında bir yükleme durum çubuğu içermektedir. Bu, Windows 10 Yıldönümü Güncelleştirmesi ve üzeri çalıştıran cihazlardaki modern uygulamalar için desteklenir.

__Önce__ ![Yükleme ekranının önceki sürümünün, durum olarak yalnızca 'yükleniyor' ifadesinin gösterildiği bir görüntüsü.](./media/cp_win10_install_status_before_1704.png)

__Sonra__ ![Yükleme ekranının güncelleştirilmiş sürümünün, şimdi bir yükleme ilerleme çubuğunu gösteren bir görüntüsü.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Şubat 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622, announced 1702-->
Mart ayından itibaren Android Şirket Portalı uygulaması [Material Design kılavuzuna](https://material.io/guidelines/material-design/introduction.html) uygun olarak modern bir tasarıma sahip olacak. Bu gelişmiş kullanıcı deneyimi şunları içeriyor olacak:

* __Renkler__: Sekme başlıklarının renkleri özel renk paletinize göre değiştirilebilir.

![Solda, Android Şirket Portalı uygulamasının güncelleştirme öncesi görüntüsü. Sağda, Android Şirket Portalı uygulamasının güncelleştirme sonrası görüntüsü. Her iki görüntüde de Uygulamalar, Cihazlar ve BT'ye Başvur sekmelerinden Cihazlar sekmesi seçili olarak gösterilmektedir.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Arabirim__: __Uygulamalar__ sekmesindeki __Öne Çıkan Uygulamalar__ ve __Tüm Uygulamalar__ düğmeleri güncelleştirildi. __Arama__ düğmesi artık kayan eylem düğmesi şeklinde.

![Solda, Android Şirket Portalı uygulamasının güncelleştirme öncesi görüntüsü. Sağda, Android Şirket Portalı uygulamasının güncelleştirme sonrası görüntüsü. Her iki görüntüde de Uygulamalar, Cihazlar ve BT'ye Başvur sekmelerinden Uygulamalar sekmesi seçili olarak gösterilmektedir.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Gezinti__: Tüm Uygulamalar sayfasında daha kolay gezinme için __Öne Çıkan Uygulamalar__, __Tüm Uygulamalar__ ve __Kategoriler__ sekmeler halinde görüntüleniyor. __BT'ye Başvur__ sekmesi daha kolay okunur hale getirilmiştir.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Ocak 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980, announced 1701-->
Şubat ayından itibaren Şirket Portalı web sitesi, yönetilen cihazlara sahip olmayan kullanıcıları hedefleyen uygulamaları destekleyecek. Karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" ![Şirket Portalı web sitesinin sol üst köşesine eklenmiş olan hamburger menüsünün küçük resmi](./media/CP_hamburger_menu.png) eklenerek diğer Microsoft ürün ve hizmetleriyle uyumlu hale getirilecek. Kullanıcılara sunulan uygulamaları vurgulayacak şekilde yeniden düzenlenecek olan giriş sayfasında, Öne Çıkan ve Son Güncelleştirilen uygulamaların görüntülendiği döngüler yer alacak.

![Sol tarafta, Uygulamalar, Cihazlarım ve Öne Çıkanlar ve Kategoriler görünümlerinin önceki sürümleriyle Şirket Portalı web sitesinin mevcut sürümünün bir görüntüsü bulunur. Sağ tarafta, yenilenen uygulama döngüsü, En Son Yayımlanan uygulamaların listesi ve güncelleştirilen Kategoriler görünümüyle Şirket Portalı web sitesinin güncelleştirilmiş sürümünün bir görüntüsü bulunur.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>Kullanıcı arabiriminde çok yakında
Bunlar, kullanıcı arabirimimizi güncelleştirerek kullanıcı deneyimini geliştirme yollarımıza yönelik planlardır.

> [!Note]
> Aşağıdaki görüntülerin önizleme sürümüne ait olabileceğini ve duyurulan sürümün farklı olabileceğini lütfen unutmayın.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 2-->

__Öne Çıkan Uygulama Güncelleştirmeleri__ Kullanıcıların öne çıkarmak istediğiniz uygulamalara gözatabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık.

![Uygulamaları gösteren renkli kutucuklar. Bunlar, her uygulamanın altında yer alan büyük, renkli karelerdir ve bu renkler uygulama logosunda bulunan ana renge göre belirlenir. “Öne Çıkan Uygulamalar” bölümü, Şirket Portalı uygulamasının üst kısmında görünür.](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Intune’daki yenilikler](https://docs.microsoft.com/intune/whats-new)
