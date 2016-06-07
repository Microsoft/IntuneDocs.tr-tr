---
# required metadata

title: Mobil cihazları kaydetme ve uygulama yükleme | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobil cihazları kaydetme ve uygulama yükleme
Intune ile mobil cihaz yönetimi ayarlamak için, önce mobil cihaz yönetimi yetkilisini ayarlamanız, cihaz platformları için yönetimi etkinleştirmeniz ve cihazlarınızı şirket portalı uygulamasına kaydetmeniz gerekir. Ardından, 6. adımda yayımladığınız Microsoft Skype uygulamasını dağıtabilirsiniz.

## Cihaz yönetimini etkinleştirme ve cihazları kaydetme

1.  Intune’u, mobil cihaz yönetimi yetkiliniz yapma  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** > **Mobil Cihaz Yönetimi**’nı seçin ve sonra da **Görevler**’in altında **MDM Yetkilisi Ayarla**’yı seçin.
    ![MDM Yetkilisi iletişim kutusunda **Evet**’i seçin. Yönetim konsolu.](./media/mdmAuthority.png)

2.  mdm olarak Intune’u ayarlama Cihaz platformunuz için MDM’yi etkinleştirme

    -   Yönetmek istediğiniz cihaz platformu için mobil cihaz yönetimini etkinleştirin.

    -   Platforma bağlı olarak farklı gereksinimler bulunur:

    -   **iOS ve Mac OS X**: Bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune). **Windows Phone**: Bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

3.  **Android**: Android mobil cihazlar kullanıcıların [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider)’den erişilebilen şirket portalı uygulamasını kullanarak kendi kendilerine kaydolmalarına olanak tanır.

    -   Intune’da ek yapılandırma gerekmez.

    -   **Cihazları kaydetme**: **Android** - [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)’den erişilebilen Microsoft Corporation’ın **Intune Şirket Portalı** uygulamasını yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın.

    -   **iOS ve Mac OS X** - Microsoft Corporation’ın **Microsoft Intune Şirket Portalı** uygulamasını Uygulama Mağazası’ndan yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın.  Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

    -   **Windows Phone 8.1**- Kullanıcılar, Windows Phone mağazasından erişilebilen Microsoft Corporation’ın **Şirket Portalı** uygulamasını yükler ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açar. Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

    **Windows Phone 8.0** - Kullanıcılar **sistem ayarları** &gt; **şirket uygulamaları**’nı seçer ve Intune kullanıcı kimlik bilgileriyle oturum açar.

## Şirket portalı uygulaması, telefonunuza dağıtılır.
**Sunucu adresi**istenirse “manage.microsoft.com” yazın. Kayıtlı cihaza bir uygulama yükleme

Bu hızlı başlangıç kılavuzunun [6. adımında](start-with-a-paid-subscription-to-microsoft-intune-step-6.md), Skype uygulamasını özel Intune Kullanıcıları grubunuza yayımladınız.

Şimdi bu uygulamayı yeni kaydedilen bir cihaza yükleyeceksiniz.


### Kaydedilen mobil cihazda şirket portalını açın, **Uygulamalar**'ı seçin ve ardından **Microsoft Skype**'ı yükleyin.
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanarak mobil cihaz yönetimi hakkında daha fazla bilgi için, bkz. [Microsoft Intune’da cihazları kaydetmeye hazırlanma](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune). Sonraki adımlar Tebrikler!

>*Intune hızlı başlangıç kılavuzunun* son adımını da tamamlamış oldunuz.

>Artık ilk yapılandırmanız tamamlandığına göre, ek MDM işlevselliğini etkinleştirmeyi göz önünde bulundurabilirsiniz.  


<!--HONumber=May16_HO2-->

