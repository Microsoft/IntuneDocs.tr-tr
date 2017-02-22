---
title: "İşleri halletmek için yönetilen cihazları kullanma | Microsoft Docs"
description: "Şirket Portalı hakkında daha fazla bilgi edinin."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 523caa6b-d792-4bb6-bddb-24b2479932d8
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 1ca19828902585bf6011713ab214619b7f8c12c5


---

# <a name="using-managed-devices-to-get-work-done"></a>İşleri halletmek için yönetilen cihazları kullanma
Microsoft Intune, kuruluşların cihazları (akıllı telefonlar, tabletler ve bilgisayarlar gibi), uygulamaları ve e-posta gibi diğer şirket kaynaklarını yönetmesine olanak tanıyan bir yazılım parçasıdır. Bu yazılım, çalışanların hemen her yerden ve hemen her cihazdan çalışma bilgilerine erişmesini sağlarken, kurumsal bilgilerin güvenliğini korumaya da yardımcı olur.

Cihazlarınızı Intune ile yönetilmek üzere kaydettiğinizde, BT departmanınız bu iş veya okul kaynaklarını yönetebilir, cihazın güvenli kalmasını sağlayabilir ve siz çalışanlara işlerinizi halletmek için tercih ettiğiniz cihazı kullanma özgürlüğünü tanıyabilir. Bunu yapmanın birincil yolu, Şirket Portalı aracılığıyla cihazı yönetime kaydetmektir.

Şirket Portalı’nı iki farklı yolla alabilirsiniz:

- Cihazınıza Şirket Portalı uygulamasını yükleyerek. Normalde Şirket Portalı uygulamasını cihazınızda uygulama mağazasına giderek alabilirsiniz, ama BT yöneticiniz de Şirket Portalı uygulamasını sizin için yükleyebilir.
- BT yöneticinizin kurduğu [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) giderek.

## <a name="whats-the-difference-between-the-app-and-the-website"></a>Uygulamayla web sitesi arasındaki fark nedir?
Şirket Portalı uygulamasıyla Şirket Portalı web sitesi arasında birkaç küçük fark vardır, ama aynı görevleri çoğunlukla her ikisinde de gerçekleştirebilirsiniz. Gerçekleştirebileceğiniz görevlerden bazıları:

- Cihazlarınızı yönetime kaydetme
- Cihazlarınızın durumuna bakma
- Kuruluşunuz için önerilen ve gerekli olan uygulamaları indirme
- Cihazınızı yeniden adlandırma
- Cihazınızın PIN'ini veya parolasını sıfırlama
- Yardım için BT bölümünüze başvurma

Şirket Portalı web sitesiyle yapabileceklerinizi cihazınızdaki Şirket Portalı uygulamasını kullanarak yapabileceklerinizle karşılaştırmak için aşağıdaki bağlantılardan birini seçin:

- [Android cihazınızı kullanma](using-your-android-device-with-intune.md)
- [iOS veya macOS cihazınızı kullanma](using-your-ios-or-macOS-device-with-intune.md)
- [Windows cihazınızı kullanma](using-your-windows-device-with-intune.md)
- [Şirket portalı web sitesini kullanma](using-the-intune-company-portal-website.md)

## <a name="what-happens-when-you-add-a-computer-or-device-to-the-company-portal"></a>Şirket Portalı’na bir bilgisayar veya cihaz eklediğinizde ne olur?
Şirket Portalı’na bir bilgisayar veya cihaz eklediğinizde bazı yazılımlar yüklenebilir ya da bir uygulama indirilebilir (cihaza bağlı olarak). Aynı zamanda, BT yöneticinize cihazınızdaki şirket bilgilerinin korunmasına yardımcı olmak için cihazınızı yönetme izni vermiş olursunuz.

BT yöneticinizin cihazınızda neleri görebileceğini, neleri göremeyeceğini öğrenmek için, kullanmakta olduğunuz cihaz türüyle eşleşen bağlantıyı kullanın:

- [Android için Şirket Portalı uygulamasını yükleme](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-android.md)
- [iOS ve macOS için Şirket Portalı uygulamasını yükleme](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)
- [Windows için Şirket Portalı uygulamasını yükleme](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md)

## <a name="what-kind-of-computers-or-devices-can-you-add-to-the-company-portal"></a>Şirket Portalı’na ne tür bilgisayarları veya cihazları ekleyebilirsiniz?
-   iOS kullanan Apple cihazları (iPhone ve iPad gibi) ve macOS (MacBook ve iMac gibi)
-   Android cihazlar
-   Windows cihazları
    -   Windows 10 Mobile
    -   Windows 10 Masaüstü
    -   Windows Phone 8.1
    -   Windows 8.1

## <a name="can-you-remove-a-computer-or-device-from-the-company-portal"></a>Bir bilgisayarı veya cihazı Şirket Portalı’ndan kaldırabilir misiniz?
Bir bilgisayarı veya cihazı Şirket Portalı’ndan kaldırabilir ya da sıfırlayabilirsiniz. **Kaldırma** ile **sıfırlama** işlemi birbirinden farklıdır.

Bir bilgisayarı veya cihazı *kaldırdığınızda*, cihazınızın Intune kaydını kaldırmış olursunuz. Kaydını kaldırdıktan sonra, Şirket Portalı’na artık bu cihazdan erişemezsiniz ve bazı şirket verileri cihazınızdan kaldırılabilir. Cihazınızı Şirket Portalı’ndan nasıl kaldıracağınızı görmek için, aşağıdaki bağlantılardan birini seçin:

- [Android cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-android.md)
- [iOS veya macOS cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-ios.md)
- [Windows cihazınızın kaydını kaldırma](unenroll-your-device-from-intune-windows.md)

Bilgisayarı veya cihazı *sıfırladığınızda* Şirket Portalı bilgisayarınızı veya cihazınızı üreticinin varsayılan ayarlarına geri döndürmeye çalışır. Cihazınız sıfırlandığında, tüm şirket verileriyle kişisel veriler cihazdan kaldırılır! Cihazınızı kaybettiyseniz, cihazı Şirket Portalı web sitesinden uzaktan da sıfırlayabilirsiniz.

Cihazınızı nasıl sıfırlayacağınızı görmek için, aşağıdaki bağlantılardan birini seçin:

- [Android cihazınızı sıfırlama (silme)](reset-erase-your-lost-or-stolen-device-android.md)
- [iOS veya macOS cihazınızı sıfırlama (silme)](reset-erase-your-lost-or-stolen-device-ios.md)
- [Windows cihazınızı sıfırlama](reset-erase-your-lost-or-stolen-device-windows.md)
- [Şirket Portalı web sitesinden cihazınızı sıfırlama](reset-your-device-cpwebsite.md)

## <a name="what-if-i-cant-see-my-device-in-the-company-portal"></a>Cihazımı Şirket Portalında göremiyorsam ne yapmam gerekir?
Bir cihazı görebilmeniz için önce Şirket Portalı’na eklenmesi gerekir. Yöneticinizin önerdiği Şirket Portalı’na gidin ve cihazınıza yönelik adımları izleyin. Ayrıca, sahibi ve yönetimi şirketinize ait olan cihazları görmezsiniz.

## <a name="if-you-have-questions-contact-your-it-admin"></a>Sorularınız varsa BT yöneticinizle iletişime geçin
Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Feb17_HO2-->


