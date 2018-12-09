---
title: macOS cihazların kaydını ayarlama
titlesuffix: Microsoft Intune
description: Intune’da macOS cihazların kaydının nasıl ayarlandığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7a54a72afb6052ed11566c2d2ada596ebde2159b
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112417"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Intune’da macOS cihazların kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, kullanıcılara şirket e-postasına ve uygulamalarına erişim vermek için macOS cihazlarını yönetmenize olanak tanır.

Intune yöneticisi olarak, şirkete ait macOS cihazları ile kişilere ait macOS cihazları ("kendi cihazını getir" veya KCG) için kaydı ayarlayabilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar

macOS cihaz kaydını ayarlamadan önce, aşağıdaki önkoşulları tamamlayın:

- [Etki alanlarını yapılandırma](custom-domain-name-configure.md)
- [MDM Yetkilisini ayarlama](mdm-authority-set.md)
- [Grup oluşturma](groups-add.md)
- [Şirket Portalı’nı yapılandırma](company-portal-app.md)
- [Office 365 portalında](http://go.microsoft.com/fwlink/p/?LinkId=698854) kullanıcı lisanslarını atama
- [Bir MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>Kullanıcıya ait macOS cihazları (KCG)

Kullanıcıların kendi cihazlarını Intune yönetimine kaydetmesine izin verebilirsiniz. Bu, “kendi cihazını getir” veya KCG olarak bilinir. Önkoşulları tamamladıktan ve kullanıcılara lisans atadıktan sonra, kullanıcılarınız cihazlarını kaydetmek için:
- [Şirket Portalı web sitesine](https://portal.manage.microsoft.com) gidebilir veya
- Şirket Portalı uygulamasını indirebilir.
Kullanıcılara, çevrimiçi kaydolma adımlarını gösteren bir bağlantı da gönderebilirsiniz: [macOS cihazınızı Intune’a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [macOS cihazınızı Intune ile kullanma](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Şirkete ait macOS cihazları
Kullanıcılarına cihaz sağlayan kuruluşlar için Intune, aşağıdaki şirkete ait macOS cihazı kayıt yöntemlerini destekler:
- [Apple'ın Aygıt Kayıt Programı (DEP)](device-enrollment-program-enroll-macos.md): Kuruluşlar, Apple’ın Aygıt Kayıt Programı (DEP) aracılığıyla macOS cihazları satın alabilir. DEP, cihazları yönetime kaydetmek için bir kayıt profilini “uzaktan” dağıtmanıza imkan tanır.
- [Cihaz kayıt yöneticisi (DEM)](device-enrollment-manager-enroll.md): En çok 1.000 cihazı kaydetmek için DEM hesabı kullanabilirsiniz.

## <a name="block-macos-enrollment"></a>macOS kaydını engelleme
Varsayılan olarak, Intune macOS cihazlarının kaydına izin verir. macOS cihazlarının kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="enroll-virtual-macos-machines-for-testing"></a>Sanal macOS makineleri sınama için kaydetme

> [!NOTE]
> macOS sanal makinelerin yalnızca sınama desteği vardır. macOS sanal makineleri son kullanıcılarınız için üretim cihazları olarak kullanmamalısınız. 

macOS sanal makineleri, Parallels Desktop veya VMware Fusion kullanarak sınama için kaydedebilirsiniz. 

Parallels Desktop kullanırsanız, Intune’un sanal makineleri tanıyabilmesi için bunların donanım türü ve seri numaralarını ayarlamanız gerekir. Sınama için gerekli ayarları yapmak üzere Parallels’in [donanım türünü](http://kb.parallels.com/123594) ve [seri numarasını ayarlama](http://kb.parallels.com/123455) yönergelerini izleyin. Sanal makineleri çalıştıran cihazın donanım türünü, oluşturduğunuz sanal makinelerin donanım türüyle eşleştirmenizi öneririz. Bu donanım türünü **Apple menüsü** > **Bu Mac hakkında** > **Sistem Raporu** > **Model Tanımlayıcı**’da bulabilirsiniz. 

VMware Fusion kullanırsanız, sanal makinenin donanım türü ve seri numarasını ayarlamak için [.vmx dosyasını düzenlemeniz](https://kb.vmware.com/s/article/1014782) gerekir. Sanal makineleri çalıştıran cihazın donanım türünü, oluşturduğunuz sanal makinelerin donanım türüyle eşleştirmenizi öneririz. Bu donanım türünü **Apple menüsü** > **Bu Mac hakkında** > **Sistem Raporu** > **Model Tanımlayıcı**’da bulabilirsiniz. 

## <a name="user-approved-enrollment"></a>Kullanıcı Onaylı kayıt

Kullanıcı Onaylı MDM kaydı, güvenlik açısından hassas bazı ayarları yönetmek için kullanabileceğiniz bir macOS kayıt türüdür. Daha fazla bilgi için [Apple'ın destek belgelerine](https://support.apple.com/HT208019) bakın.

Kullanıcı onaylı olması için, son kullanıcının macOS Şirket Portalı aracılığıyla kaydettikten sonra Sistem Tercihleri'ni kullanarak el ile onay sağlaması gerekir. Bu işlemi yapma yönergeleri, macOS 10.13.2 veya üzerini kullanan kullanıcılar için macOS Şirket Portalı'nda sağlanır.

Cihazın Kullanıcı Onaylı olup olmadığını öğrenmek için, Intune portalına gidin ve **Cihazlar** > **Tüm cihazlar**> cihaz seçin > **Donanım**'ı seçin. **Kullanıcı Onaylı** alanını işaretleyin.

## <a name="next-steps"></a>Sonraki adımlar

macOS cihazları kaydedildikten sonra, [macOS cihazları için özel ayarlar oluşturabilirsiniz](custom-settings-macos.md).
