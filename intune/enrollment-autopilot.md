---
title: Windows AutoPilot Dağıtım Programını kullanarak cihazları kaydetme
titleSuffix: Microsoft Intune
description: Windows AutoPilot Dağıtım programını kullanarak Windows 10 cihazları kaydetmeyi öğrenin.
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
ms.openlocfilehash: 934b80d1c174c25d37e30695f46afc88c8d8bfc3
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot-deployment-program"></a>Windows AutoPilot Dağıtım Programını kullanarak Windows cihazlarını kaydetme
Windows AutoPilot Dağıtım Programı, cihaz sağlamayı kolaylaştırır. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve AutoPilot ile özel işletim sistemi görüntülerini derleme, bakım ve uygulama zahmetine katlanmanız gerekmeden son kullanıcılarınıza yeni cihazlar verebilirsiniz. AutoPilot cihazları yönetmek için Intune kullandığınızda cihazlar kaydedildikten sonra ilkeler, profiller, uygulamalar gibi özellikleri yönetebilirsiniz. Faydalar, senaryolar ve önkoşullara genel bir bakış için bkz. [Windows AutoPilot’a Genel Bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Önkoşullar
- [Windows otomatik kayıt etkin olmalıdır](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği olmalıdır](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Cihazları ekleme

Bilgilerini içeren CSV dosyasını içeri aktararak Windows AutoPilot cihazlarını ekleyebilirsiniz.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > **İçeri Aktar**'ı seçin.

    ![Windows AutoPilot cihazlarının ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları ekleme** bölümünde, eklemek istediğiniz cihazların seri numaralarını, Windows ürün kimliklerini ve donanım karma değerlerini içeren CSV dosyasına gidin.

    ![Windows AutoPilot cihazlarını ekleme işleminin ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device2.png)

3. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. Bu işlem birkaç dakika sürebilir.

## <a name="synchronize-devices"></a>Cihazları eşitleme
Kayıtlı cihazlarınızı yapılandırmak için Intune ile eşitleyin.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**’nı seçin ve **Windows AutoPilot Dağıtım Programı** bölümünde, **Cihazlar**’ı seçin.
5. **Eşitle**’ye tıklayarak kayıtlı cihazlarınızı içeri aktarın. Eşitlemenin sürdüğüne dair bir ileti görüntülenir.
6. Yeni cihazları görmek için görüntüyü yenileyin. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profili oluşturma
AutoPilot dağıtım profilleri, AutoPilot cihazları yapılandırmak için kullanılır.
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**’nı seçin ve **Windows AutoPilot Dağıtım Programı** bölümünde, **Dağıtım Profilleri**’ni seçin.
5. **Profil Oluştur**’u ve bir ad ile isteğe bağlı bir açıklama seçin.
6. **Azure AD’ye katılım türü** için **Azure AD katılımlı**’yı seçin.
7. **İlk kez çalıştırma deneyimi (OOBE)** için aşağıdaki seçenekleri yapılandırın ve **Kaydet**’e tıklayın:

   - **Son kullanıcı lisans sözleşmesi (EULA)**: EULA’nın kullanıcılara gösterilip gösterilmeyeceğini seçin.
   - **Gizlilik ayarları**: Gizlilik ayarlarının kullanıcılara gösterilip gösterilmeyeceğini seçin.
   - **Kullanıcı hesap türü**: Kullanıcı hesabının türünün **Yönetici** mi **Standart** mı olacağını seçin.

     > [!Note]    
     > Bu ayar, Genel Yönetici veya Şirket Yöneticisi hesapları için geçerli değildir. Bu hesaplar, Azure AD’deki tüm yönetim özelliklerine erişebildikleri için standart kullanıcılar olamaz.


6. Profili oluşturmak için **Oluştur**’a tıklayın. AutoPilot dağıtım profili artık cihazlara atanmak üzere hazırdır.

> [!Note]    
> Aşağıdaki ayarlar, tüm AutoPilot dağıtım profillerinde yapılandırılır:
> - Skip Cortana, OneDrive ve OEM kayıt kurulum sayfaları
> - İş veya okul için otomatik olarak ayarlama
> - Şirket veya okul markasıyla oturum açma deneyimi    

## <a name="assign-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profili atama
AutoPilot dağıtım profilleri oluşturduktan sonra bunları seçili cihazlara atayabilirsiniz.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**’nı seçin ve **Windows AutoPilot Dağıtım Programı** bölümünde, **Cihazlar**’ı seçin.
5. Dağıtım profilini atamak istediğiniz cihazları seçin. Atanmış bir profili olmayan cihazları kolayca bulmak için **Profil Durumu** sütununda filtreleme yapabilirsiniz.
6. **Profil ata**’ya tıklayın, AutoPilot dağıtım profilini seçin ve daha sonra **Ata**’ya tıklayın. Atamanın sürdüğüne dair bir ileti görüntülenir.
7. Profilin cihazlara atandığını görmek için görüntüyü yenileyin. Kaç tane cihaz seçtiğinize bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

> [!Note]
> Yeni profil cihaza atanır. Intune'a zaten kaydedilmiş olan cihazlarda, cihaz sıfırlandıktan ve yeniden kaydedildikten sonra profil uygulanır.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Farklı bir AutoPilot dağıtım profili atama
Bir cihaza AutoPilot dağıtım profili atadıktan sonra farklı bir profil atamaya karar verirseniz yeni profili cihaza atayın.  

## <a name="edit-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profilini düzenleme
Bir AutoPilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**'nın altındaki **Windows AutoPilot Dağıtım Programı** bölümünde **Dağıtım Profilleri**’ni seçin.
5. Düzenlemek istediğiniz profili seçin.
6. Solda bulunan **Özellikler**’e tıklayarak dağıtım profilinin adını veya açıklamasını değiştirin. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.
7. OOBE ayarlarında değişiklik yapmak için **Ayarlar**’a tıklayın. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.

> [!NOTE]
> Güncelleştirilmiş profil cihazlara atanır. Ancak güncelleştirilmiş profil, Intune’a önceden kaydedilmiş cihazlarda cihaz sıfırlanıp yeniden kaydedilene kadar uygulanmaz.

## <a name="using-autopilot-in-other-portals"></a>AutoPilot’ı diğer portallarda kullanma
Mobil cihaz yönetimiyle ilgilenmiyorsanız AutoPilot’ı İş İçin Microsoft Mağazası gibi bir uygulamada kullanma şansınız vardır. Diğer portalları kullanma seçeneğiniz olsa da, AutoPilot dağıtımlarınızı yönetmek için yalnızca Intune kullanmanızı öneririz. Intune ve başka bir portalı kullanırsanız Intune şunları yapamaz:
- Intune’da oluşturulup başka bir portalda düzenlenmiş profillerdeki değişiklikleri görüntüleme
- Başka bir portalda oluşturulmuş profilleri eşitleme
- Başka bir portalda profil atamalarında yapılmış değişiklikleri görüntüleme
- Başka bir portalda yapılmış profil atamalarını eşitleme
- Başka bir portal üzerinden cihaz listesine yapılmış değişiklikleri görüntüleme

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar  <!-- 163236 -->
Windows AutoPilot’ta atanmamış cihazlar için bir uyarı görüntüleyebilir ve böylece AutoPilot programında kaç tane cihaza AutoPilot dağıtım profili atanmadığını görebilirsiniz. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. Uyarıyı görüntülemek için **Genel Bakış**’ı seçin. Uyarıya tıklayarak AutoPilot cihazların listesine ulaşın.  

## <a name="delete-autopilot-devices"></a>AutoPilot cihazlarını silme

Kayıtlı olmayan Windows AutoPilot cihazlarını silebilirsiniz. Cihazların kaydını kaldırabilir ve ardından bunları silebilirsiniz.

1. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar**'ı seçin.

2. **Windows AutoPilot cihazları** bölümünde, silmek istediğiniz cihazları seçin ve sonra da **Sil**'i seçin.

3. **Evet**'i seçerek silme işlemini onaylayın. Silme işlemi birkaç dakika sürebilir.


## <a name="next-steps"></a>Sonraki adımlar
Windows AutoPilot’ı kayıtlı Windows 10 cihazlar için yapılandırdıktan sonra bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)
