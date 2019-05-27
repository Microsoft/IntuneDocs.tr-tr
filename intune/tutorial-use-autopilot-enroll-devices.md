---
title: Öğretici - Intune’a cihaz kaydetmek için Autopilot kullanma
titleSuffix: Microsoft Intune
description: Bu öğreticide Intune'a cihaz kaydetmek için Windows Autopilot’ı ayarlayacaksınız.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2018
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ee353e5e6c39c3b402c0b4f039bb02efcfa4532
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044520"
---
# <a name="tutorial-use-autopilot-to-enroll-windows-devices-in-intune"></a>Öğretici: Intune'da Windows cihazları kaydetmeye AutoPilot'ı kullanın
Windows Autopilot, cihaz kaydını basitleştirir. Microsoft Intune ve Autopilot ile özel işletim sistemi görüntüleri oluşturmanıza, bu görüntüleri cihazlara uygulamanıza ve bunların bakımını yapmanıza gerek kalmadan son kullanıcılarınıza yeni cihazlar verebilirsiniz. 

Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:
> [!div class="checklist"]
> * Intune’a cihaz ekleme
> * Bir Autopilot cihaz grubu oluşturma
> * Bir Autopilot dağıtım profili oluşturma
> * Autopilot dağıtım profilini cihaz grubuna atama
> * Kullanıcılara Windows cihazlar dağıtma

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

Autopilot faydalarına, senaryolarına ve önkoşullarına genel bir bakış için bkz. [Windows Autopilot’a genel bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Önkoşullar
- [Windows otomatik kaydını ayarlama](quickstart-setup-auto-enrollment.md)
- [Azure Active Directory Premium aboneliği](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## <a name="add-devices"></a>Cihazları ekleme

Windows Autopilot’ı ayarlamanın ilk adımı, Windows cihazları Intune’a eklemektir. Tek yapmanız gereken, bir CSV dosyası oluşturmak ve bunu Intune’a aktarmaktır.

1. Herhangi bir metin düzenleyicide Windows cihazları belirleyen, virgülle ayrılmış değerler (CSV) listesi oluşturun. Aşağıdaki biçimi kullanın:
    
    *seri numarası*, *windows ürün kimliği*, *donanım karması*, *grubu etiketi isteğe bağlı*
    
    İlk üç öğe gerekiyor, ancak Grup (önceden "order ID" bilinen) etiket isteğe bağlıdır.

2. CSV dosyasını kaydedin.

3. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > **İçeri Aktar**’ı seçin.

    ![Windows Autopilot cihazlarının ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device.png)

4. **Windows Autopilot cihazlar ekle** altında kaydettiğiniz CSV dosyasına göz atın.

    ![Windows Autopilot cihazları ekleme ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device2.png)

5. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. İçeri aktarma birkaç dakika sürebilir.

4. İçeri aktarma tamamlandıktan sonra **Cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **Cihazlar** > **Eşitle**’yi seçin. Eşitlemenin sürdüğüne dair bir ileti görüntülenir. Kaç tane cihaz eşitlediğinize bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

5. Yeni cihazları görmek için görüntüyü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Bir Autopilot cihaz grubu oluşturma

Daha sonra bir cihaz grubu oluşturacak ve az önce yüklediğiniz Autopilot cihazları buraya koyacaksınız.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Gruplar** > **Yeni grup**’u seçin.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. **Grup adı** olarak *Autopilot Grubu* yazın. **Grup açıklaması** olarak *Autopilot cihazlar için test grubu* yazın.
    3. **Üyelik türü** olarak **Atanan**’ı seçin.
3. **Grup** dikey penceresinde **Üyeler**’i seçin ve Autopilot cihazları gruba ekleyin. Henüz kaydedilmemiş Autopilot cihazları, adın cihaz seri numarası olduğu cihazlardır.
4. **Oluştur**’u seçin.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma

Bir cihaz grubu oluşturduktan sonra, Autopilot cihazları yapılandırabilmek için bir dağıtım profili oluşturmalısınız.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri** > **Profil Oluştur**’u seçin.
2. Üzerinde **Temelleri** sayfasında, tor **adı**, girin *Autopilot profili*. **Açıklama** olarak *Autopilot cihazlar için test profili* yazın.
3. **Tüm hedeflenen cihazları Autopilot’a dönüştür** ayarını **Evet** olarak seçin. Bu ayar, listedeki tüm cihazların Autopilot dağıtım hizmetine kaydolmasını sağlar. Kaydın işlenmesi için 48 saat kadar bekleyin.
4. **İleri**’yi seçin.
5. Üzerinde **ilk çalıştırma deneyimi (OOBE)** sayfası için **dağıtım modu**, seçin **kullanıcı temelli**. Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkilidir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekir.
6. **Azure AD’ye farklı katıl** kutusunda **Azure AD katılımlı**’yı seçin.
7. Aşağıdaki seçenekleri yapılandırın ve diğerleri Varsayılana Ayarla bırakın:
    - **Son Kullanıcı Lisans Sözleşmesi (EULA)**: **Gizle**
    - **Gizlilik ayarları**: **Show**
    - **Kullanıcı hesabı türü**: **Standart**
8. **İleri**’yi seçin.
9. Üzerinde **atamaları** sayfasında **seçilen grupları** için **atama**.
10. Seçin **dahil edilecek grupları seçin**, seçin **Autopilot grubu**.
11. **İleri**’yi seçin.
12. Üzerinde **gözden geçir + Oluştur** sayfasında **Oluştur** profili oluşturmak için.

## <a name="distribute-devices-to-users"></a>Cihazları kullanıcılara dağıtma

Artık kullanıcılara Windows cihazları dağıtabilirsiniz. Kullanıcılar ilk oturum açtığında, Autopilot sistemi cihazları otomatik olarak kaydedecek ve yapılandıracaktır. 

## <a name="clean-up-resources"></a>Kaynakları temizleme

Autopilot cihazları artık kullanmak istemiyorsanız, bunları silebilir.

1. Cihazlar Intune’a kayıtlıysa önce bunları [Azure Active Directory portalından silmeniz](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal) gerekir.

2. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar**'ı seçin.

3. **Windows Autopilot cihazları** bölümünde silmek istediğiniz cihazları, sonra da **Sil**’i seçin.

4. **Evet**'i seçerek silme işlemini onaylayın. Silme işlemi birkaç dakika sürebilir.

## <a name="next-steps"></a>Sonraki adımlar

Windows Autopilot için kullanılabilir diğer seçenekler hakkında daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Ayrıntılı Autopilot kaydı makalesi](enrollment-autopilot.md)


