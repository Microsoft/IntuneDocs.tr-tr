---
title: "Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e52ebdd62ca68f1d9226def654961075400184a8
ms.openlocfilehash: e2da1f39d0cfe05bb0ea1c149c91e5ff82312c01


---


# Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur?

Şirket Portalı uygulamasını yüklediğinizde ve cihazınızı kaydettiğinizde ne olacağını öğrenmek için, yukarıdaki “Bu Makalede” bölümünde gösterilen ve kullandığınız cihazla eşleşen bağlantıyı kullanın. Windows 10 cihazları hakkında bilgi için [bu sayfaya](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md) bakın.

## Windows 8.1 ve Windows RT
Şirket Portalı uygulamasını yüklediğinizde ve sonra da uygulamayı kullanarak Windows 8.1 Enterprise veya Professional ya da Windows RT cihazınızı Intune’a kaydettiğinizde, Şirket Portalı uygulamasını kullanarak şunları yapabilirsiniz:

-   Şirket ağına, e-postalarınıza ve iş dosyalarınıza erişebilirsiniz

-   Şirket Portalı üzerinden şirket uygulamalarını alabilirsiniz

-   Şirket e-posta hesabınızı otomatik olarak yapılandırabilirsiniz

-   Telefonunuz kaybolur veya çalınırsa fabrika ayarlarına sıfırlayabilirsiniz

Kaydetme adımları için bkz. [Windows cihazınızı Intune’a kaydetme](enroll-your-device-in-intune-windows.md). BT yöneticinizin cihazınızda neleri görebileceğini öğrenmek için, bkz. [Cihazımı Intune’a kaydettiğimde BT yöneticim neleri görebilir?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Bir bilgisayarı eklediğinizde:

-   BT yöneticinizin bilgisayarı yönetmesine olanak tanımak, böylelikle uygulamalar ve destek bilgileri gibi şirket kaynaklarını almanızı sağlamak için, bilgisayarınıza yazılım yüklenir. BT yöneticiniz bu yazılımı otomatik olarak güncelleştirebilir.

-   Intune Endpoint Protection bilgisayarınızda yüklü olabilir. Bu, bilgisayarı virüs ve kötü amaçlı yazılımlara karşı denetleyen yazılımdır.

-   BT yöneticiniz, kişisel olarak yüklediğiniz yazılımlar dahil olmak üzere bilgisayarda yüklü tüm yazılımların bir envanterini alabilir.

-   Hüküm ve koşulları kabul etmeniz gerekebilir.

-   BT yöneticiniz bilgisayarınızın sabit sürücüsünden veri toplayabilir veya onları silebilir. BT yöneticiniz sabit sürücünün tamamını da silebilir.

-   BT yöneticiniz aynı zamanda bilgisayarınıza uygulama ve güncelleştirme de yükleyebilir.

-   BT yöneticiniz bilgisayarınızda ilkelerin uygulanmasını şart koşabilir. Örneğin, çok sayıda hatalı parola girişi yapıldığında, bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu ayarlamanız veya bilgisayarınızın sabit sürücüsündeki tüm bilgileri silmeniz gerekebilir.

## Windows Phone 8.1 ve Windows Phone 8
Şirket Portalı uygulamasını yüklediğinizde ve sonra da uygulamayı kullanarak Windows Phone 8.1 veya Windows Phone 8 cihazınızı Intune’a kaydettiğinizde, Şirket Portalı uygulamasını kullanarak şunları yapabilirsiniz:

-   Şirket ağına, e-postalarınıza ve iş dosyalarınıza erişebilirsiniz

-   Şirket Portalı üzerinden şirket uygulamalarını alabilirsiniz

-   Şirket e-posta hesabınızı otomatik olarak yapılandırabilirsiniz

-   Telefonunuz kaybolur veya çalınırsa fabrika ayarlarına sıfırlayabilirsiniz

Kaydetme adımları için bkz. [Windows cihazınızı Intune’a kaydetme](enroll-your-device-in-intune-windows.md). BT yöneticinizin cihazınızda neleri görebileceğini öğrenmek için, bkz. [Cihazımı Intune’a kaydettiğimde BT yöneticim neleri görebilir?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Windows Phone cihazınızı eklediğinizde, BT yöneticinize cihazınıza erişim hakkı vermiş olursunuz. Yönetici cihazda şu gibi şeyler yapabilir:

-   Cihazınızı üretici varsayılan ayarlarına geri döndürebilir. Cihaz çalındıysa veya kaybolduysa bu yararlıdır.

-   Şirketle ilgili tüm verileri ve yüklü iş uygulamalarını kaldırabilir. Kişisel ayarlarınız ve verileriniz kaldırılmaz.

-   Çok sayıda hatalı parola girişi yapıldığında, sizi bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu belirlemeye veya verilerin silinmesini göze alıp cihazı tekrar üreticinin varsayılan ayarlarına sıfırlamaya zorlayabilir.

-   Cihazdaki tüme verilerin şifrelenmesini şart koşabilir. Cihaz çalındıysa veya kaybolduysa, verilerin korunmasında yardımcı olur.

-   Hüküm ve koşulları kabul etmenizi gerektirir.

-   SD kartı devre dışı bırakabilir.

-   Cihazınıza uygulama güncelleştirmelerini yükleyebilir. Bu yalnızca güncelleştirmeler için geçerlidir. BT yöneticiniz sizi cihazınıza yeni uygulama yüklemeye zorlayamaz, ancak isterseniz şirket portalında gördüğünüz uygulamaları yükleyebilirsiniz.

-   Cihazınız şirket portalına eklendikten sonra, yaklaşık 8 saat içinde:

    -   BT yöneticinizin kullanılabilir hale getirdiği ilke veya uygulama güncelleştirmeleri indirilir.

    -   Tüm donanım envanteri güncelleştirmeleri gönderilir.

    -   Tüm şirket uygulaması envanteri güncelleştirmeleri gönderilir.

## Windows 7 ve Vista
Şirket Portalı uygulamasını yüklediğinizde ve sonra da uygulamayı kullanarak Windows 7 veya Vista cihazınızı Intune’a kaydettiğinizde, Şirket Portalı uygulamasını kullanarak şunları yapabilirsiniz:

-   Şirket ağına, e-postalarınıza ve iş dosyalarınıza erişebilirsiniz

-   Şirket Portalı üzerinden şirket uygulamalarını alabilirsiniz

-   Şirket e-posta hesabınızı otomatik olarak yapılandırabilirsiniz

-   Telefonunuz kaybolur veya çalınırsa fabrika ayarlarına sıfırlayabilirsiniz

BT yöneticinizin cihazınızda neleri görebileceğini öğrenmek için, bkz. [Cihazımı Intune’a kaydettiğimde BT yöneticim neleri görebilir?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Bir bilgisayarı eklediğinizde:

-   BT yöneticinizin bilgisayarı yönetmesine olanak tanımak, böylelikle uygulamalar ve destek bilgileri gibi şirket kaynaklarını almanızı sağlamak için, bilgisayarınıza yazılım yüklenir. BT yöneticiniz bu yazılımı otomatik olarak güncelleştirebilir.

-   Intune Endpoint Protection bilgisayarınızda yüklü olabilir. Bu, bilgisayarı virüs ve kötü amaçlı yazılımlara karşı denetleyen yazılımdır.

-   BT yöneticiniz, kişisel olarak yüklediğiniz yazılımlar dahil olmak üzere bilgisayarda yüklü tüm yazılımların bir envanterini alabilir.

-   Hüküm ve koşulları kabul etmeniz gerekebilir.

-   BT yöneticiniz bilgisayarınızın sabit sürücüsünden veri toplayabilir veya onları silebilir. BT yöneticiniz sabit sürücünün tamamını da silebilir.

-   BT yöneticiniz aynı zamanda bilgisayarınıza uygulama ve güncelleştirme de yükleyebilir.

-   BT yöneticiniz bilgisayarınızda ilkelerin uygulanmasını şart koşabilir. Örneğin, çok sayıda hatalı parola girişi yapıldığında, bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu ayarlamanız veya bilgisayarınızın sabit sürücüsündeki tüm bilgileri silmeniz gerekebilir.

Sorularınız varsa BT yöneticinizle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

### Ayrıca bkz.
[Windows cihazınızı Intune ile kullanma](using-your-windows-device-with-intune.md)



<!--HONumber=Jun16_HO4-->


