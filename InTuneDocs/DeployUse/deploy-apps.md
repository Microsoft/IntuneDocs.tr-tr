---
# required metadata

title: Uygulamaları dağıtma | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile uygulamaları dağıtma

Bu konu başlığı altında, Microsoft Intune’la uygulamaları dağıtmaya başlamadan önce anlamanız gereken bazı kavramlar açıklanır.

## Intune yazılım yayımcısı
**Microsoft Intune Yazılım Yayımcısı**, Microsoft Intune yönetici konsolundan uygulama eklediğinizde veya değiştirdiğinizde başlatılır. Yayımcıyı kullanarak, Intune bulut depolama alanında depolanacak uygulamaları (bilgisayarlar için programlar veya mobil cihazlar için uygulamalar) karşıya yükleyecek veya bir çevrimiçi mağaza ya da web uygulaması ile bağlantı kuracak türde bir yazılım yükleyicisi seçebilir ve yapılandırabilirsiniz.

### Gereksinimler
Microsoft Intune Yazılım Yayımcısı'nı kullanmaya başlamadan önce [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851)'ın tam sürümünü yüklemeniz gerekir. Yüklemeden sonra Yazılım Yayımcısı'nın doğru şekilde açılması için bilgisayarınızı yeniden başlatmanız gerekebilir.

## Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak dağıttığınız tüm uygulamalar paketlenmeli ve Microsoft Intune bulut depolama alanına yüklenmelidir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Ücretli abonelikler 20 GB içerir ve ek depolama alanı satın alma seçeneği de sağlanır.

**Yönetici** çalışma alanının **Depolama Kullanımı** düğümünde ne kadar alan kullandığınızı görebilir ve daha fazla depolama satın alabilirsiniz.

Intune için bulut tabanlı ek depolama alanı satın alma işleminde şu kurallar geçerlidir:

-   Ek depolama alanı satın almak için etkin bir ücretli aboneliğinizin olması gerekir.

-   Yalnızca Microsoft Online Service’inizin faturalama yöneticileri veya genel yöneticileri Office 365 Yönetim Portalı aracılığıyla ek depolama alanı satın alabilir. Bu yöneticileri eklemek, silmek veya yönetmek için bir genel yönetici olmanız ve Office 365 Yönetim Portalı’nda oturum açmış olmanız gerekir.

-   Intune’u veya Microsoft Intune Eklentisini kurumsal anlaşma ile satın almış bir toplu lisans müşterisiyseniz, fiyatlandırma konusunda bilgi edinmek ve ek depolama alanı satın almak için Microsoft Kurumsal Müşteri Yöneticiniz veya Microsoft İş Ortağınız ile iletişim kurun.

#### Bulut depolama alanı gereksinimleri

-   Bir uygulamayla ilişkilendirilmiş tüm dosyalar aynı konumda bulunmalı ve Intune tarafından erişilebilir olmalıdır.

-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.

-   Dosyaları karşıya yükleme için İnternet hızınız en az 768 kb/sn olmalıdır.

## Uygulama dağıtım eylemleri
Uygulamaları dağıtırken aşağıdaki dağıtım eylemlerden birini seçebilirsiniz:

-   **Gerekli yükleme** – Uygulama herhangi bir son kullanıcı müdahalesi gerekmeden cihaza yüklenir.

    > [!TIP] Denetimli modda olmayan iOS cihazları ve tüm Android cihazları için kullanıcı yükleme öncesinde uygulama teklifini kabul etmelidir.
    >
    > Artık iOS 7.1’den önceki işletim sistemlerini çalıştıran iOS cihazlarına yeni uygulama dağıtımları oluşturamazsınız. iOS 7.1’den önceki işletim sistemlerini çalıştıran cihazlara yönelik var olan tüm uygulama dağıtımları çalışmaya ve Intune tarafından yönetilmeye devam edecektir.
    > 
    >  Son kullanıcı gerekli bir yükleme olarak dağıttığınız bir uygulamayı kaldırırsa, Intune normalde 7 günde bir gerçekleştirilen bir sonraki envanter döngüsünden sonra uygulamayı otomatik olarak yeniden yükler.

-   **Kullanılabilir yükleme** – Uygulama şirket portalında gösterilir ve son kullanıcılar tarafından isteğe bağlı olarak yüklenebilir.

-   **Kaldır** – Uygulama cihazdan kaldırılır.

-   **Geçerli değil** – Uygulama şirket portalında gösterilmez ve herhangi bir cihaza yüklenmez.

#### Her yükleme türünde hangi dağıtım eylemlerinin kullanılabildiğini anlama

|Yükleyici türü|Zorunlu yükleme|Kullanılabilir yükleme|Kaldır|Geçerli değil|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows uygulama paketi (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Windows uygulama paketi (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Mobil cihazlar için uygulama paketi (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Mobil cihazlar için uygulama paketi (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Windows Installer (bir kullanıcı grubuna dağıtılır)|Hayır|Evet|Hayır|Evet|
|Windows Installer (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Dış bağlantı (bir kullanıcı grubuna dağıtılır)|Hayır|Evet|Hayır|Evet|
|Dış bağlantı (bir cihaz grubuna dağıtılır)|Hayır|Hayır|Hayır|Hayır|
|Uygulama mağazasından yönetilen iOS uygulaması (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Uygulama mağazasından yönetilen iOS uygulaması (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
> [!TIP] Uygulamaları dağıtırken hem kullanıcı hem de cihaz gruplarını seçerseniz, uygulamayı yalnızca **Kullanılabilir yükleme** olarak dağıtabilirsiniz.

## Dağıtım çakışmaları
Bir cihaz tarafından aynı dağıtım eylemiyle iki dağıtım alındığında aşağıdaki kurallar geçerli olur:

-   Cihaz grubuna yapılan dağıtımlar, kullanıcı grubuna yapılan dağıtımlara göre önceliklidir. Ancak, bir uygulama **Kullanılabilir** dağıtım eylemiyle bir kullanıcı grubuna dağıtılır ve aynı uygulama aynı zamanda **Geçerli Değil**dağıtım eylemiyle bir cihaz grubuna dağıtılırsa, uygulama şirket portalında kullanıcılar tarafından yüklenebilir.

-   BT yöneticisinin amacı, kullanıcıya göre önceliklidir.

-   Yükleme eylemi, kaldırma eylemine göre önceliklidir.

-   Cihaz tarafından hem gerekli yükleme hem de kullanılabilir yükleme alınırsa, eylemler birleştirilir (uygulama hem gerekli hem de kullanılabilir olur).


## Sonraki adımlar

[Microsoft Intune'da uygulamaları dağıtmayı](deploy-apps-in-microsoft-intune.md) öğrenin.

<!--HONumber=Jun16_HO2-->


