---
title: "Windows AutoPilot Dağıtım Programını kullanarak Windows cihazları kaydetme"
description: "Windows AutoPilot Dağıtım programını kullanarak yeni Windows 10 cihazları kaydetmeyi öğrenin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: dae736aef57489880915c269cb30785371380a52
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Windows AutoPilot Dağıtım Programını kullanarak Windows cihazları kaydetme
Windows AutoPilot Dağıtım Programı, cihaz sağlamayı kolaylaştırır. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve AutoPilot ile özel işletim sistemi görüntülerini derleme, bakım ve uygulama zahmetine katlanmanız gerekmeden son kullanıcılarınıza yeni cihazlar verebilirsiniz. AutoPilot cihazları yönetmek için Intune kullandığınızda cihazlar kaydedildikten sonra ilkeler, profiller, uygulamalar gibi özellikleri yönetebilirsiniz. Faydalar, senaryolar ve önkoşullara genel bir bakış için bkz. [Windows AutoPilot’a Genel Bakış](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot).

## <a name="prerequisites"></a>Önkoşullar
- [Cihazlar kuruluşunuza kayıtlı olmalıdır](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/windows-10-autopilot#device-registration-and-oobe-customization)
- [Windows otomatik kayıt etkin olmalıdır](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği olmalıdır](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>Cihazları eşitleme
Kayıtlı cihazlarınızı yapılandırmak için Intune ile eşitleyin.

1. [Azure](https://portal.azure.com/)’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**'nın altındaki **Windows AutoPilot Dağıtım Programı** bölümünde **Cihazlar**’ı seçin.
5. **Eşitle**’ye tıklayarak kayıtlı cihazlarınızı içeri aktarın. Eşitlemenin sürdüğüne dair bir ileti görüntülenir.
6. Yeni cihazları görmek için görüntüyü yenileyin. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profili oluşturma
AutoPilot dağıtım profilleri, AutoPilot cihazları yapılandırmak için kullanılır.
1. [Azure](https://portal.azure.com/)’da oturum açın. 
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı**'nın altındaki **Windows AutoPilot Dağıtım Programı** bölümünde **Dağıtım Profilleri**’ni seçin.
5. **Profil Oluştur**’a tıklayın ve bir ad ile isteğe bağlı bir açıklama seçin. 
6. **Katılım türü** için **Azure AD katılımlı**’yı seçin.
7. **İlk kez çalıştırma deneyimi (OOBE)** için aşağıdaki seçenekleri yapılandırın ve **Tamam**’a tıklayın: 
   - **Gizlilik ayarları**: Gizlilik ayarlarının kullanıcılara gösterilip gösterilmeyeceğini seçin. 
   - **Son kullanıcı lisans sözleşmesi (EULA)**: EULA’nın kullanıcılara gösterilip gösterilmeyeceğini seçin.
   - **Kullanıcı hesap türü**: Kullanıcı hesabının türünün **Yönetici** mi **Standart** mı olacağını seçin.

     > [!Note]    
     > Bu ayar, Genel Yönetici veya Şirket Yöneticisi hesapları için geçerli değildir. Bu hesaplar, Azure AD’deki tüm yönetim özelliklerine erişebildikleri için standart kullanıcılar olamaz.
8. Profili oluşturmak için **Oluştur**’a tıklayın. AutoPilot dağıtım profili artık cihazlara atanmak üzere hazırdır.
     
> [!Note]    
> Aşağıdaki ayarlar, tüm AutoPilot dağıtım profillerinde yapılandırılır:
> - Skip Cortana, OneDrive ve OEM kayıt kurulum sayfaları
> - İş veya okul için otomatik olarak ayarlama
> - Şirket veya okul markasıyla oturum açma deneyimi    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar  <!-- 163236 -->
Windows AutoPilot’ta atanmamış cihazlar için bir uyarı görüntüleyebilir ve böylece AutoPilot programında kaç tane cihaza AutoPilot dağıtım profili atanmadığını görebilirsiniz. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz. 
1. [Azure](https://portal.azure.com/)’da oturum açın. 
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. Uyarıyı görüntülemek için **Genel Bakış**’ı seçin. Uyarıya tıklayarak AutoPilot cihazların listesine ulaşın.  

## <a name="assign-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profili atama
AutoPilot dağıtım profilleri oluşturduktan sonra bunları seçili cihazlara atayabilirsiniz.

1. [Azure](https://portal.azure.com/)’da oturum açın. 
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune**'un altında **Cihaz kaydı**'nı seçin.
4. **Windows kaydı** dikey penceresinin **Windows AutoPilot Dağıtım Programı** bölümünde **Cihazlar**’ı seçin.
5. Dağıtım profilini atamak istediğiniz cihazları seçin. Atanmış bir profili olmayan cihazları kolayca bulmak için **Durum** sütununda filtreleme yapabilirsiniz. 
6. **Profil ata**’ya tıklayın, AutoPilot dağıtım profilini seçin ve daha sonra **Ata**’ya tıklayın. Atamanın sürdüğüne dair bir ileti görüntülenir.
7. Profilin cihazlara atandığını görmek için görüntüyü yenileyin. Kaç tane cihaz seçtiğinize bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir. 

> [!Note]
> Yeni profil cihaza atanır. Intune'a zaten kaydedilmiş olan cihazlarda, cihaz sıfırlandıktan ve yeniden kaydedildikten sonra profil uygulanır.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Farklı bir AutoPilot dağıtım profili atama
Bir cihaza AutoPilot dağıtım profili atadıktan sonra farklı bir profil atamaya karar verirseniz yeni profili cihaza atayın.  

## <a name="edit-an-autopilot-deployment-profile"></a>Bir AutoPilot dağıtım profilini düzenleme 
Bir AutoPilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   
1. [Azure](https://portal.azure.com/)’da oturum açın. 
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
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

## <a name="next-steps"></a>Sonraki adımlar
Windows AutoPilot’ı kayıtlı Windows 10 cihazlar için yapılandırdıktan sonra bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)