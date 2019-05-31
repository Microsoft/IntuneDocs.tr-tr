---
title: Microsoft Intune - Azure e-posta profilleriyle ilgili sorunları giderme | Microsoft Docs
description: Sık karşılaşılan sorunlar ve çözümleri yinelenen bir e-posta profilleri ve Samsung KNOX Standard Android cihazlarında hatalar dahil olmak üzere Microsoft Intune e-posta profilleriyle bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0fe37deb63457fef869df0f7263970a4e53cb29
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402714"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Genel sorunlar ve çözümleri Microsoft Intune e-posta profilleriyle

Bazı yaygın e-posta profili sorunları ve nasıl giderileceği ve çözüleceği açıklanır gözden geçirin.

## <a name="device-already-has-an-email-profile-installed"></a>Cihazda zaten yüklü bir e-posta profili var

Kullanıcılar Intune'a kaydolmadan e-posta profili oluşturursanız, Intune e-posta profili beklendiği gibi çalışmayabilir:

- **iOS**: Intune, konak adına ve e-posta adresini temel alan bir var olan ve yinelenen e-posta profili olduğunu algılar. Kullanıcı tarafından oluşturulmuş bir e-posta profili Intune tarafından oluşturulan profilin dağıtımını engeller. İOS kullanıcıları genellikle bir e-posta profili oluşturma ardından kaydolduğundan ortak bir sorunu budur. Şirket portalı uygulaması, kullanıcı uyumsuzsa ve e-posta profilini kaldırmak için kullanıcı isteyebilir belirtir.

  Kullanıcı, Intune profilinin dağıtılabilmesi e-posta profillerini kaldırmalısınız. Bu sorunu önlemek için kullanıcılarınızdan kaydetmeye ve Intune'un e-posta profili dağıtmasına izin vermelerini. Ardından, kullanıcılar e-posta profillerini oluşturabilir.

- **Windows**: Intune, konak adına ve e-posta adresini temel alan bir var olan ve yinelenen e-posta profili olduğunu algılar. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

- **Samsung KNOX Standard**: Intune e-posta adresini temel alan bir yinelenen bir e-posta hesabı olduğunu algılar ve bunu Intune profili bunun üzerine yazar. Kullanıcı bu hesabı yapılandırırsa Intune profili tarafından yeniden üzerine yazılır. Bu, hesap yapılandırmasının üzerine yazılan kullanıcı için karışıklığa neden olabilir.

Samsung KNOX, ana bilgisayar adı, profili tanımlamak için kullanmaz. Bunlar birbirinin üzerine yazılacağından, farklı konaklarda aynı e-posta adresine dağıtmak için birden çok e-posta profilleri oluşturmayın öneririz.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>KNOX Standard cihazı için 0x87D1FDE8 hatası

**Sorunu**: Oluşturma ve dağıtma Exchange Active Sync Samsung KNOX Standard için farklı Android cihazlar için e-posta profilini sonra **0x87D1FDE8** veya **düzeltme başarısız** cihazın hatayı gösterir Özellikler > ilke sekmesinde.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmez ve profilinizde bu seçeneğin belirlenmesi olmamalıdır. Cihazların ilkeyi 24 saate kadar işlemek için yeterli zamana sahip olduğunuzdan emin olun.

## <a name="unable-to-send-images-from--email-account"></a>E-posta hesabından resim gönderilemedi

Klasik Azure portalında Intune için geçerlidir.

Otomatik olarak yapılandırılan e-posta hesaplarına sahip kullanıcılar, cihazlarından resim veya görüntü gönderemez. Bu senaryo oluşabilir **üçüncü taraf uygulamalardan gönderilmesine izin ver** etkin değil.

### <a name="intune-solution"></a>Intune çözümü

1. Microsoft Intune yönetim konsolunu açın, **ilke** iş yükü > **yapılandırma İlkesi**.

2. E-posta profilini seçin ve **Düzenle**’yi seçin.

3. **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Intune ile tümleştirilmiş Configuration Manager çözümü

1. Configuration Manager konsolunu açın > **varlıklar ve Uyumluluk**.

2. Genişletin **genel bakış** > **uyumluluk ayarları** > **şirket kaynağına erişim**seçip **e-posta profilleri**.

3. E-posta profiline sağ tıklayın ve **Özellikler**’i açın.

4. **Eşitleme Ayarları** sekmesinde **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Alma [destekleyen Microsoft gelen Yardım](get-support.md), veya [topluluk forumları](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).