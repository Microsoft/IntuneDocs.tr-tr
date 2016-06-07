---
# required metadata

title: Cihazınızın Intune kaydını sildiğinizde ne olur? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Cihazınızın Intune kaydını sildiğinizde ne olur?

Şirket Portalı uygulamasını cihazınızdan kaldırdığınızda, cihazınızın Intune kaydı da kaldırılır. Neler olduğu hakkında ek bilgi için, kullanmakta olduğunuz cihaz türü ile eşleşen bağlantıyı kullanın.

- [Windows 10 mobil, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 veya Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows 8.1 çalıştıran Windows RT veya Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Cihazınız artık Şirket Portalı’nda görünmez ve Şirket Portalı’ndan artık uygulama yükleyemezsiniz.

-   Intune istemci yazılımını yüklediyseniz, bilgisayarınızdan kaldırılır.

-   Intune Endpoint Protection yazılımı bilgisayarınızdan kaldırılır. Bilgisayarınızda başka bir virüsten koruma yazılımı yüklüyse ve yazılım devre dışıysa, Intune Endpoint Protection kaldırıldıktan sonra bu yazılım yeniden etkinleştirilebilir. Şirket Portalı’ndan kaldırdıktan sonra bilgisayarınızı kontrol etmelisinizdir.

    > Diğer bir virüsten koruma yazılımı yeniden etkinleştirilmediyse veya bir virüsten koruma yazılımı yüklü değilse, bilgisayarınız virüs ve kötü amaçlı yazılımlara açık halde olabilir.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak gibi ayarlar geçerliliğini kaybeder.

-   Bilgisayarınız artık Intune hizmetinden otomatik yazılım güncelleştirmeleri veya virüsten koruma yazılımı güncelleştirmeleri almaz. Ancak, bilgisayarınız yapılandırmasına bağlı olarak Windows Server Update Services, Windows Update veya Microsoft Update'den güncelleştirme almaya devam edebilir.

Ayrıca, Windows 8.1 için:

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Windows Mail gibi bazı posta uygulamaları artık cihazınızda depolanan şirket e-postalarına erişemeyecektir.

-   Wi-Fi veya bir Sanal Özel Ağ kullanarak şirket ağınıza bağlanamayabilirsiniz.

-   Dosya paylaşımları veya dahili web siteleri gibi şirket kaynaklarına erişemeyebilirsiniz.

## Windows 10 mobil, Windows Phone 8.1 veya Windows Phone 8

-   Şirket Portalı uygulaması cihazınızdan kaldırılır, bu nedenle cihazınız artık Şirket Portalı’nda görünmez ve Şirket Portalı uygulamasından ya da Şirket Portalı web sitesinden uygulama yükleyemezsiniz.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

    > [!IMPORTANT]
    > Bu durumda geçerli olmaya devam edecek tek özel durum şifreleme ilkesidir. Şirket ilkeniz Windows Phone'unuzun şifrelenmesini gerektiriyorsa, telefonunuzun şifresini kaldırmanın tek yolu Windows Phone cihazınızda **Ayarlar** menüsünü kullanarak telefonunuzu sıfırlamaktır.

## Windows 8.1 çalıştıran Windows RT veya Windows RT

-   Şirket Portalı uygulaması cihazınızdan kaldırılır, bu nedenle cihazınız artık Şirket Portalı’nda görünmez ve Şirket Portalı uygulamasından uygulama yükleyemezsiniz.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.

-   Wi-Fi veya bir Sanal Özel Ağ kullanarak artık şirket ağınıza bağlanamayabilirsiniz.

-   Dosya paylaşımları veya dahili web siteleri gibi şirket kaynaklarına erişemeyebilirsiniz.

-   Windows Mail gibi bazı posta uygulamaları artık cihazınızda depolanan şirket e-postalarına erişemeyecektir.

Windows RT cihazınızı kaldırdığınızda şunlar olur:

-   Şirket Portalı uygulaması cihazınızdan kaldırılır, bu nedenle cihazınız artık Şirket Portalı’nda görünmez ve Şirket Portalı uygulamasından uygulama yükleyemezsiniz.

-   Cihazınızda artık şirket uygulamalarını ve şirket verilerini kullanamazsınız.

-   Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.


### Ayrıca bkz.
[Windows cihazınızı Intune ile kullanma](using-your-windows-device-with-intune.md)

<!--HONumber=May16_HO2-->

