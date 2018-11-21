---
title: Microsoft Intune - Azure e-posta profilleriyle ilgili sorunları giderme | Microsoft Docs
description: E-posta profili sorunları, bu sorunları giderme ve çözme.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 480b453aa4f08f8d2a2460e26bfdb5f05466df6e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190107"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Microsoft Intune’da e-posta profilleriyle ilgili sorunları giderme

Bazı yaygın e-posta profili sorunları ve nasıl giderileceği ve çözüleceği açıklanır gözden geçirin.

Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>E-posta hesabından resim gönderilemedi
Klasik Azure portalında Intune için geçerlidir.

Otomatik olarak yapılandırılan e-posta hesaplarına sahip kullanıcılar, cihazlarından resim veya görüntü gönderemiyor. Bu senaryo oluşabilir **üçüncü taraf uygulamalardan gönderilmesine izin ver** etkin değil.

### <a name="intune-solution"></a>Intune çözümü

1. Microsoft Intune yönetim konsolunu açın, **ilke** iş yükü > **yapılandırma İlkesi**.

2. E-posta profilini seçin ve **Düzenle**’yi seçin.

3. **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Intune ile tümleştirilmiş Configuration Manager çözümü

1. Configuration Manager konsolunu açın > **varlıklar ve Uyumluluk**.

2. Genişletin **genel bakış** > **uyumluluk ayarları** > **şirket kaynağına erişim**seçip **e-posta profilleri**.

3. E-posta profiline sağ tıklayın ve **Özellikler**’i açın.

4. **Eşitleme Ayarları** sekmesinde **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

## <a name="device-already-has-an-email-profile-installed"></a>Cihazda zaten yüklü bir e-posta profili var

Kullanıcı bir e-posta profili Intune profilinin provisionining önce yüklediyseniz, Intune e-posta profili dağıtımının sonucu cihaz platformuna bağlıdır:

- **iOS**: Intune, konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğunu algılar. Kullanıcı tarafından oluşturulmuş yinelenen e-posta profili, Intune yöneticisinin oluşturduğu profilin dağıtımını engeller. İOS kullanıcıları genellikle bir e-posta profili oluşturma ardından kaydolduğundan ortak bir sorunu budur. Şirket portalı, kullanıcıların el ile yapılandırılan e-posta profilinden dolayı uyumlu olmayan ve o profili kaldırmasını ister kullanıcı güncelleştirir. Intune profilinin dağıtılabilmesi için kullanıcının e-posta profilini kaldırması gerekir. Bu sorunu önlemek için kullanıcılarınızdan kaydetmeye ve Intune'un profili dağıtmasına izin vermelerini. Ardından, kullanıcı tarafından oluşturulmuş bir e-posta profili yükleyin.

- **Windows**: Intune, konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğunu algılar. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

- **Samsung KNOX Standard**: Intune e-posta adresini temel alan bir yinelenen bir e-posta hesabı olduğunu algılar ve Intune profili bunun üzerine yazılmıştır. Kullanıcı bu hesabı yapılandırırsa Intune profili tarafından yeniden üzerine yazılır. Bu, hesap yapılandırmasının üzerine yazılan kullanıcı için karışıklığa neden olabilir.

Samsung KNOX, ana bilgisayar adı, profili tanımlamak için kullanmaz. Bunlar birbirinin üzerine yazılacağından, farklı konaklarda aynı e-posta adresine dağıtmak için birden çok e-posta profilleri oluşturmayın öneririz.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>KNOX Standard cihazı için 0x87D1FDE8 hatası
**Sorunu**: oluşturma ve dağıtma Exchange Active Sync Samsung KNOX Standard için çeşitli Android cihazlarda, hata e-posta profilini sonra **0x87D1FDE8** veya **düzeltme başarısız** olduğu cihazın özelliklerinde bildirilen > ilke sekmesinde.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmez ve profilinizde bu seçenek belirtilmemelidir. Cihazların ilkeyi 24 saate kadar işlemek için yeterli zamana sahip olduğunuzdan emin olun.

## <a name="next-steps"></a>Sonraki adımlar
Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).