---
title: Windows AutoPilot kullanarak cihazları kaydetme
titleSuffix: Microsoft Intune
description: Windows AutoPilot kullanarak Windows 10 cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: a640e6d914da6fead7a64d5235c1cdeac164ac9e
ms.sourcegitcommit: 7c70c3e0fcae7c4fa8c9e108aafb1cebb366332d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44096546"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Windows AutoPilot kullanarak Windows cihazlarını kaydetme
Windows AutoPilot, cihaz sağlamayı kolaylaştırır. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve AutoPilot ile özel işletim sistemi görüntülerini derleme, bakım ve uygulama zahmetine katlanmanız gerekmeden son kullanıcılarınıza yeni cihazlar verebilirsiniz. AutoPilot cihazları yönetmek için Intune kullandığınızda cihazlar kaydedildikten sonra ilkeler, profiller, uygulamalar ve daha fazlasını yönetebilirsiniz. Faydalar, senaryolar ve önkoşullara genel bir bakış için bkz. [Windows AutoPilot’a Genel Bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Önkoşullar
- [Windows otomatik kayıt etkin olmalıdır](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği olmalıdır](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Cihazları ekleme

Bilgilerini içeren CSV dosyasını içeri aktararak Windows AutoPilot cihazlarını ekleyebilirsiniz.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > **İçeri Aktar**’ı seçin.

    ![Windows AutoPilot cihazlarının ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları ekle** altında, eklemek istediğiniz cihazları listeleyen bir CSV dosyasına gözatın. Dosya; seri numaraları, Windows ürün kimlikleri, donanım karmaları ve cihazların isteğe bağlı sipariş kimliklerini barındırmalıdır.

    ![Windows AutoPilot cihazlarını ekleme işleminin ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device2.png)

3. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. İçeri aktarma birkaç dakika sürebilir.

4. İçeri aktarma tamamlandıktan sonra **Cihaz kaydı** > **Windows kaydı** > **Windows AutoPilot** > **Cihazlar** > **Eşitle**’yi seçin. Eşitlemenin sürdüğüne dair bir ileti görüntülenir. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

5. Yeni cihazları görmek için görüntüyü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Bir AutoPilot cihaz grubu oluşturma

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Gruplar**’ı seçin.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması** girin.
    3. **Üyelik türü** olarak **Atanan** veya **Dinamik Cihaz**’ı seçin.
3. Önceki adımda **Üyelik türü** olarak **Atanan**’ı seçtiyseniz, **Gruplar** dikey penceresinde **Üyeler**’i seçin ve gruba AutoPilot cihazları ekleyin.
    Henüz kaydedilmemiş AutoPilot cihazları, adın cihaz seri numarası olduğu cihazlardır.
4. Yukarıda **Üyelik türü** olarak **Dinamik Cihazlar**’ı seçtiyseniz **Gruplar** dikey penceresinde **Dinamik cihaz üyeleri**’ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki kodlardan birini yazın.
    - Tüm AutoPilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")` yazın
    - Belirli sipariş kimliklerine sahip AutoPilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") ` yazın
    - Belirli Satın Alma Sipariş Kimliklerine sahip AutoPilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` yazın
    
    **Gelişmiş kural** kodunu ekledikten sonra **Kaydet**’i seçin.
5. **Oluştur**’u seçin.



## <a name="create-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profili oluşturma
AutoPilot dağıtım profilleri, AutoPilot cihazları yapılandırmak için kullanılır.
1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri** > **Profil Oluştur**’u seçin.
2. Bir **Ad** ve isteğe bağlı olarak bir **Açıklama** girin.
3. **Dağıtım modu** için şu iki seçenekten birini belirtin:
    - **Kullanıcı temelli**: Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkilidir. Cihazın sağlanması için kullanıcı kimlik bilgileri gereklidir.
    - **Kendi kendine dağıtım (önizleme)**: (en son [Windows 10 Insider Önizleme Derlemesini](https://docs.microsoft.com/windows-insider/at-work-pro/) gerektirir) Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkili değildir. Cihazın sağlanması için kullanıcı kimlik bilgileri gerekli değildir.
4. **Azure AD’ye farklı katıl** kutusunda **Azure AD katılımlı**’yı seçin.
5. **İlk kez çalıştırma deneyimi (OOBE)** öğesini seçin, aşağıdaki seçenekleri yapılandırın ve **Kaydet**’e tıklayın:
    - **Dil (Bölge)***: Cihazda kullanılacak dili seçin. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Klavyeyi otomatik olarak yapılandır***: Bir **Dil (Bölge)** seçildiyse, klavye seçimi sayfasını atlamak için **Evet** olarak ayarlayın. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Son kullanıcı lisans sözleşmesi (EULA)**: (Windows 10, sürüm 1709 veya sonrası) EULA’nın kullanıcılara gösterilip gösterilmeyeceğini seçin.
    - **Gizlilik ayarları**: Gizlilik ayarlarının kullanıcılara gösterilip gösterilmeyeceğini seçin.
    - **Hesap değiştirme seçeneklerini gizle (yalnızca Windows Insider)**: Şirket oturum açma ve etki alanı hatası sayfalarında hesap değiştirme seçeneklerinin görüntülenmesini önlemek için **Gizle** olarak ayarlayın. Bu seçenek, [Azure Active Directory’de şirket markasının yapılandırılmasını](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) gerektirir.
    - **Kullanıcı hesap türü**: Kullanıcı hesabının türünün **Yönetici** mi yoksa **Standart** mı olacağını seçin.
    - **Bilgisayar adı şablonunu uygula (yalnızca Windows Insider)**: Sağlama sırasında bir cihazı adlandırırken kullanılacak bir şablon oluşturmak için **Evet** olarak ayarlayın. Adlar en fazla 15 karakter olmalıdır; harf, sayı ve kısa çizgi içerebilir. Ancak tamamen sayıdan oluşamaz. Donanıma özgü seri numarası eklemek için [%SERIAL% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanın. Alternatif olarak, x değerinin eklenecek basamak sayısına karşılık geldiği [%RAND:x% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanarak rastgele bir sayı dizesi ekleyin. 

6. Profili oluşturmak için **Oluştur**’a tıklayın. AutoPilot dağıtım profili artık cihazlara atanmak üzere hazırdır.

*Hem **Dil (Bölge)** hem de **Klavyeyi otomatik olarak yapılandır** seçenekleri, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir (en son [Windows 10 Insider Önizleme Derlemesini](https://docs.microsoft.com/windows-insider/at-work-pro/) gerektirir).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>AutoPilot dağıtım profilini bir cihaz grubuna atama

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**’ni ve daha sonra bir profili seçin.
2. Profile ait dikey pencerede **Atamalar**’ı seçin. 
3. **Grupları seçin**’e tıklayın, daha sonra **Grupları seçin** dikey penceresinde uygulamayı atamak istediğiniz grubu/grupları seçin ve **Seçin**’e tıklayın.

## <a name="edit-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profilini düzenleme
Bir AutoPilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı**’nı seçin.
2. **Windows kaydı** altındaki **Windows AutoPilot** bölümünde **Dağıtım Profilleri**’ni seçin.
3. Düzenlemek istediğiniz profili seçin.
4. Solda bulunan **Özellikler**’e tıklayarak dağıtım profilinin adını veya açıklamasını değiştirin. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.
5. OOBE ayarlarında değişiklik yapmak için **Ayarlar**’a tıklayın. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.

> [!NOTE]
> Profilde yapılan değişiklikler, bu profile atanmış cihazlara uygulanır. Ancak güncelleştirilmiş profil, Intune’a önceden kaydedilmiş cihazlarda cihaz sıfırlanıp yeniden kaydedilene kadar uygulanmaz.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar  <!-- 163236 -->
AutoPilot programından kaç tane cihaza AutoPilot dağıtım profili atanmamış olduğunu gösteren bir uyarı görüntüleyebilirsiniz. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz.

Atanmamış cihazlar için uyarı görmek istiyorsanız [Azure portalında Intune’da](https://aka.ms/intuneportal) **Cihaz kaydı** > **Genel bakış** > **Atanmamış cihazlar**’ı seçin.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Belirli bir Autopilot cihazına kullanıcı atama

Belirli bir Autopilot cihazına kullanıcı atayabilirsiniz. Bu atama, Windows kurulumu sırasında [şirket markalı](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) oturum açma sayfasında Azure Active Directory’den bir kullanıcıyı önceden doldurur. Ayrıca özel bir karşılama adı ayarlamanıza imkan verir. Bu, Windows oturum açmayı önceden doldurmaz veya değiştirmez. Yalnızca lisanslı Intune kullanıcıları bu yolla atanabilir.

Önkoşullar: Yapılandırılmış Azure Active Directory Şirket Portalı ve en son [Windows 10 Insider Önizleme Derlemesi](https://docs.microsoft.com/windows-insider/at-work-pro/).

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > cihazı seçin **Kullanıcı ata**’yı seçin.
    ![Kullanıcı ata ekran görüntüsü](media/enrollment-autopilot/assign-user.png)
2. Intune’u kullanmak için Azure lisanslı bir kullanıcıyı seçin ve **Seç**’e tıklayın.
    ![Kullanıcı seçme ekran görüntüsü](media/enrollment-autopilot/select-user.png)
3. **Kolay Ad** kutusuna kolay bir ad girin veya varsayılanı kabul edin. Bu, kullanıcı Windows kurulumu sırasında oturum açtığında görüntülenen kolay addır.
    ![Kolay ad ekran görüntüsü](media/enrollment-autopilot/friendly-name.png)
4. **Tamam**’ı seçin.


## <a name="delete-autopilot-devices"></a>AutoPilot cihazlarını silme

Kayıtlı olmayan Windows AutoPilot cihazları silebilirsiniz.

1. Cihazlar Intune’a kayıtlıysa önce bunları [Azure Active Directory portalından silmeniz](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal) gerekir.

2. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar**'ı seçin.

3. **Windows AutoPilot cihazları** bölümünde, silmek istediğiniz cihazları seçin ve sonra da **Sil**'i seçin.

4. **Evet**'i seçerek silme işlemini onaylayın. Silme işlemi birkaç dakika sürebilir.

## <a name="using-autopilot-in-other-portals"></a>AutoPilot’ı diğer portallarda kullanma
Mobil cihaz yönetimiyle ilgilenmiyorsanız AutoPilot’ı örneğin İş İçin Microsoft Store’da kullanabilirsiniz. Diğer portalları kullanma seçeneğiniz olsa da, AutoPilot dağıtımlarınızı yönetmek için yalnızca Intune kullanmanızı öneririz. Intune ve başka bir portalı kullanırsanız Intune şunları yapamaz:
- Intune’da oluşturulup başka bir portalda düzenlenmiş profillerdeki değişiklikleri görüntüleme
- Başka bir portalda oluşturulmuş profilleri eşitleme
- Başka bir portalda profil atamalarında yapılmış değişiklikleri görüntüleme
- Başka bir portalda yapılmış profil atamalarını eşitleme
- Başka bir portal üzerinden cihaz listesine yapılmış değişiklikleri görüntüleme

## <a name="next-steps"></a>Sonraki adımlar
Windows AutoPilot’ı kayıtlı Windows 10 cihazlar için yapılandırdıktan sonra bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)
