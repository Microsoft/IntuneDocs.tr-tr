---
title: "Intune ve son kullanıcı uygulamaları arabirimlerinde yapılan güncelleştirmeler | Microsoft Docs"
description: "Son kullanıcı cihazlarında Intune ile çalışan uygulamalar için kullanıcı arabiriminde yapılan değişiklikleri keşfedin."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 68dbaa2209ad1432279683a291734641e39ff736
ms.contentlocale: tr-tr
ms.lasthandoff: 05/05/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Intune ve son kullanıcı uygulamaları arabirimlerinde yapılan güncelleştirmeler
Son kullanıcılarınızın Microsoft Intune’un bu sürümünde göreceği uygulamalar için kullanıcı arabiriminde sunulan güncelleştirmeler hakkında bilgi edinin. Bu yenilikler, kullanıcılarınızla iletişim kurmanızı kolaylaştırmanın yanı sıra dağıtımınızı desteklemek için oluşturduğunuz özel belgeler için sunacağınız güncelleştirmeler konusunda size yardımcı olabilir. Bu ayrıca son kullanıcılarınız Şirket Portalını kullanarak destek için yardım masasını ararlarsa, karşılaştıkları sorunları daha iyi nasıl çözebileceğinizi anlamanıza da yardımcı olur.

## <a name="coming-soon-in-the-ui"></a>Kullanıcı arabiriminde çok yakında
Bunlar, kullanıcı arabirimimizi güncelleştirerek kullanıcı deneyimini geliştirme yollarımıza yönelik planlardır.

> [!Note]
> Aşağıdaki görüntülerin önizleme sürümüne ait olabileceğini ve duyurulan sürümün farklı olabileceğini lütfen unutmayın.

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

## <a name="april-2017"></a>Nisan 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser ve Şirket Portalı için yeni simgeler <!--918433, 918431-->

Managed Browser uygulamasının hem Android hem de iOS sürümlerinin simgesi güncelleştiriliyor. Yeni simgede Enterprise Mobility + Security (EM+S) paketindeki diğer uygulamalarla tutarlı hale getirmek için güncelleştirilmiş Intune rozeti bulunacak.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Geliştirilmiş Windows 10 Şirket Portalı uygulaması yükleme durumu <!--676495-->
Windows 10 Şirket Portalı uygulaması, artık uygulama ayrıntıları sayfasında bir yükleme durum çubuğu içermektedir. Bu, Windows 10 Yıldönümü Güncelleştirmesi ve üzeri çalıştıran cihazlardaki modern uygulamalar için desteklenir.

__Önce__
  ![Durum olarak sadece “yükleniyor” yazan yükleme ekranının eski sürümünün bir resmi.](./media/cp_win10_install_status_before_1704.png)

__Sonra__
  ![Artık bir yükleme ilerleme durumu gösteren güncelleştirilmiş yükleme ekranı resmi.](./media/cp_win10_install_status_after_1704.png)

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
            <img src="https://docs.microsoft.com/InTune/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Ocak 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980, announced 1701-->
Şubat ayından itibaren Şirket Portalı web sitesi, yönetilen cihazlara sahip olmayan kullanıcıları hedefleyen uygulamaları destekleyecek. Karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" ![Şirket Portalı web sitesinin sol üst köşesine eklenmiş olan hamburger menüsünün küçük resmi](./media/CP_hamburger_menu.png) eklenerek diğer Microsoft ürün ve hizmetleriyle uyumlu hale getirilecek. Kullanıcılara sunulan uygulamaları vurgulayacak şekilde yeniden düzenlenecek olan giriş sayfasında, Öne Çıkan ve Son Güncelleştirilen uygulamaların görüntülendiği döngüler yer alacak.

![Sol tarafta, Uygulamalar, Cihazlarım ve Öne Çıkanlar ve Kategoriler görünümlerinin önceki sürümleriyle Şirket Portalı web sitesinin mevcut sürümünün bir görüntüsü bulunur. Sağ tarafta, yenilenen uygulama döngüsü, En Son Yayımlanan uygulamaların listesi ve güncelleştirilen Kategoriler görünümüyle Şirket Portalı web sitesinin güncelleştirilmiş sürümünün bir görüntüsü bulunur.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure önizlemesindeki yenilikler](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Yenilikler arşivi](whats-new-archive.md)

