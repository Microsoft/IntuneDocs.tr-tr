---
title: "Mobil cihazları kaydetme ve uygulama yükleme | Microsoft Intune"
description: "Mobil cihazları kaydetme ve Intune’a kayıtlı bir cihaza uygulama yükleme işlemleri açıklanır"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3306d772b074ddcfd1bfcf7178b32f9b371321e7
ms.openlocfilehash: f57728bb41b750f53b021bed532de18187e764a0


---

# Mobil cihazları kaydetme ve uygulama yükleme
Intune ile mobil cihaz yönetimi ayarlamak için, önce mobil cihaz yönetimi yetkilisini ayarlamanız, cihaz platformları için yönetimi etkinleştirmeniz ve cihazlarınızı Şirket Portalı uygulamasına kaydetmeniz gerekir. Ardından, 6. adımda yayımladığınız Microsoft Skype uygulamasını dağıtabilirsiniz.

## Cihaz yönetimini etkinleştirme ve cihazları kaydetme

1.  **Intune’u mobil cihaz yönetimi yetkiliniz yapma** [Intune yönetim konsolunda](https://manage.microsoft.com/) **Yönetim** > **Mobil Cihaz Yönetimi**’ni seçin ve ardından **Görevler** altında **MDM Yetkilisini Ayarla**’yı seçin.  MDM Yetkilisi iletişim kutusunda **Evet**’i seçin.
    ![Yönetim konsolu. mdm olarak Intune’u ayarlama](./media/mdmAuthority.png)

2.  **Cihaz platformunuz için MDM’yi etkinleştirme** Yönetmek istediğiniz cihaz platformu için mobil cihaz yönetimini etkinleştirin. Platforma bağlı olarak farklı gereksinimler bulunur:

    -   **iOS ve Mac OS X**: Bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: Bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: Android mobil cihazlar kullanıcıların [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider)’den erişilebilen Şirket Portalı uygulamasını kullanarak kendi kendilerine kaydolmalarına olanak tanır. Intune’da ek yapılandırma gerekmez.

3.  **Cihazları kaydetme**:

    -   **Android** - [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612)’den erişilebilen Microsoft Corporation’ın **Intune Şirket Portalı** uygulamasını yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın.

    -   **iOS ve Mac OS X** - Microsoft Corporation’ın **Microsoft Intune Şirket Portalı** uygulamasını Uygulama Mağazası’ndan yükleyin ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açın. Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

    -   **Windows Phone 8.1**- Kullanıcılar, Windows Phone mağazasından erişilebilen Microsoft Corporation’ın **Şirket Portalı** uygulamasını yükler ve yukarıya eklenen Intune kullanıcı kimlik bilgileriyle oturum açar.  Cihazınızı eklemek için **Kayıtlı cihazlar** ’ı görüntüleyin.

    -   **Windows Phone 8.0** - Kullanıcılar **sistem ayarları** &gt; **şirket uygulamaları**’nı seçer ve Intune kullanıcı kimlik bilgileriyle oturum açar. Şirket Portalı uygulaması, telefonunuza dağıtılır.

    **Sunucu adresi**istenirse “manage.microsoft.com” yazın.

## Kayıtlı cihaza bir uygulama yükleme
Bu hızlı başlangıç kılavuzunun [6. adımında](start-with-a-paid-subscription-to-microsoft-intune-step-6.md), Skype uygulamasını özel Intune Kullanıcıları grubunuza yayımladınız. Şimdi bu uygulamayı yeni kaydedilen bir cihaza yükleyeceksiniz.

Kaydedilen mobil cihazda Şirket Portalı’nı açın, **Uygulamalar**'ı seçin ve ardından **Microsoft Skype**'ı yükleyin.

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanarak mobil cihaz yönetimi hakkında daha fazla bilgi için bkz. [Microsoft Intune’da cihazları kaydetmenin önkoşulları](/intune/deploy-use/prerequisites-for-enrollment).


### Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* son adımını da tamamlamış oldunuz. Artık ilk yapılandırmanız tamamlandığına göre, ek MDM işlevselliğini etkinleştirmeyi göz önünde bulundurabilirsiniz.

>[!div class="step-by-step"]

>[&larr; **Cihazları kaydetme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Yapılandırma sonrası görevler** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Oct16_HO3-->


