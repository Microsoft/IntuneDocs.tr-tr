---
title: "Şirket Portalı uygulamasını yüklerseniz ve Windows cihazınızı Intune’a kaydederseniz ne olur? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: 840d985fd2c4771831f722cdff214026a383f606


---


# Şirket Portalı uygulamasını yüklerseniz ve Windows cihazınızı Intune’a kaydederseniz ne olur?

Şirket Portalı uygulamasını yüklediğinizde ve bu uygulamayı kullanarak Windows veya Windows Phone cihazınızı kaydettiğinizde, aşağıda Windows 10’dan önceki cihazlar için açıklandığı gibi, BT yöneticinizin şirket veya okul verilerinin güvenliğini sağlamak üzere cihazınızı yönetmesine olanak tanımış olursunuz. Windows 10 cihazları hakkında bilgi için [bu sayfaya](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md) bakın.

## Kayıttan sonra tüm Windows cihazlarına ne olur?
Windows veya Windows Phone cihazınızı Intune’a kaydettiğinizde:

-   Şirket ağına, e-postalarınıza ve iş dosyalarınıza erişebilirsiniz

-   Şirket Portalı üzerinden şirket uygulamalarını alabilirsiniz (Windows 7 ve Vista için, şirket uygulamalarını yalnızca Şirket Portalı web sitesinden alabilirsiniz)

-   Şirket veya okul e-posta hesabınızı otomatik olarak yapılandırabilirsiniz

-   Telefonunuz kaybolur veya çalınırsa fabrika ayarlarına sıfırlayabilirsiniz

Cihazınızı kaydettiğinizde, BT yöneticinize şu tür işlemleri yapma izni vermiş olursunuz:

-   Cihazınızı üretici varsayılan ayarlarına geri döndürebilir. Cihaz çalındıysa veya kaybolduysa bu yararlıdır.

-   Şirketle ilgili tüm verileri ve yüklü iş uygulamalarını kaldırabilir. Kişisel ayarlarınız ve verileriniz kaldırılmaz.

-   BT yöneticiniz, kişisel olarak yüklediğiniz yazılımlar dahil olmak üzere bilgisayarda yüklü tüm yazılımların bir envanterini alabilir.

-   Çok sayıda hatalı parola girişi yapıldığında, sizi bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu belirlemeye veya verilerin silinmesini göze alıp cihazı tekrar üreticinin varsayılan ayarlarına sıfırlamaya zorlayabilir.

-   Cihazdaki tüm verileri şifrelemeyi zorunlu tutabilir ve bu da cihaz kaybolur veya çalınırsa verileri korumaya yardımcı olur.

-   Hüküm ve koşulları kabul etmenizi gerektirir.

-   BT yöneticiniz bilgisayarınızda ilkelerin uygulanmasını şart koşabilir. Örneğin, çok sayıda hatalı parola girişi yapıldığında, bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu ayarlamanız veya bilgisayarınızın sabit sürücüsündeki tüm bilgileri silmeniz gerekebilir.

-   SD kartı devre dışı bırakabilir.

## Kayıttan sonra tüm Windows bilgisayarlarına ne olur?

-  BT yöneticinizin bilgisayarı yönetmesine olanak tanımak, böylelikle uygulamalar ve destek bilgileri gibi şirket kaynaklarını almanızı sağlamak için, bilgisayarınıza yazılım yüklenir. BT yöneticiniz bu yazılımı otomatik olarak güncelleştirebilir.

-  Intune Endpoint Protection bilgisayarınızda yüklü olabilir. Bu, bilgisayarı virüs ve kötü amaçlı yazılımlara karşı denetleyen yazılımdır.

-  BT yöneticiniz, kişisel olarak yüklediğiniz yazılımlar dahil olmak üzere bilgisayarda yüklü tüm yazılımların bir envanterini alabilir.

-  Hüküm ve koşulları kabul etmeniz gerekebilir.

-  BT yöneticiniz bilgisayarınızın sabit sürücüsünden veri toplayabilir veya onları silebilir. BT yöneticiniz sabit sürücünün tamamını da silebilir.

-  BT yöneticiniz aynı zamanda bilgisayarınıza uygulama ve güncelleştirme de yükleyebilir.

-  BT yöneticiniz bilgisayarınızda ilkelerin uygulanmasını şart koşabilir. Örneğin, çok sayıda hatalı parola girişi yapıldığında, bilgisayardan çıkmanıza yol açabilecek bir parola veya PIN kodu ayarlamanız veya bilgisayarınızın sabit sürücüsündeki tüm bilgileri silmeniz gerekebilir.


## Cihaz kaydından sonra her sekiz saatte bir ne olur?
Yaklaşık her sekiz saatte bir, kayıtlı cihazlarda aşağıdakiler yapılır:

-   BT yöneticinizin kullanılabilir hale getirdiği ilke veya uygulama güncelleştirmeleri indirilir.

-   Tüm donanım envanteri güncelleştirmeleri gönderilir.

-   Tüm şirket uygulaması envanteri güncelleştirmeleri gönderilir.

Kaydetme adımları için bkz. [Windows cihazınızı Intune’a kaydetme](enroll-your-device-in-intune-windows.md). BT yöneticinizin cihazınızda neleri görebileceğini öğrenmek için, bkz. [Cihazımı Intune’a kaydettiğimde BT yöneticim neleri görebilir?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Sorularınız varsa BT yöneticinizle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

### Ayrıca bkz.
[Windows cihazınızı Intune ile kullanma](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


