---
title: Microsoft Intune - Azure e-posta profilleriyle ilgili sorunları giderme | Microsoft Docs
description: Sık karşılaşılan sorunlar ve çözümleri yinelenen bir e-posta profilleri ve Samsung KNOX Standard Android cihazlarında hatalar dahil olmak üzere Microsoft Intune e-posta profilleriyle bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/17/2019
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
ms.openlocfilehash: 2246e3f6faa853f620327558a7faf4dc9d6a6e85
ms.sourcegitcommit: 43ba5a05b2e1dc1997126d3574884f65cde449c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67197505"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Genel sorunlar ve çözümleri Microsoft Intune e-posta profilleriyle

Bazı yaygın e-posta profili sorunları ve nasıl giderileceği ve çözüleceği açıklanır gözden geçirin.

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- E-posta profilleri, kaydeden kullanıcı için dağıtılır. E-posta profili yapılandırmak için Intune Azure Active Directory (AD) özelliklerini kullanıcının e-posta profilinde kayıt sırasında kullanır. [Cihazlar için e-posta ayarları Ekle](email-settings-configure.md) iyi bir kaynak olabilir.
- Configuration Manager karma tek başına Intune'a geçirdikten sonra Configuration Manager karma e-posta profilinden 7 gün boyunca cihazda kalır. Bu beklenen bir davranıştır. Er kaldırıldı e-posta profili gerekirse başvurun [Intune Destek](get-support.md).
- Android Enterprise için Gmail veya yönetilen Google Play Store kullanarak iş dokuz dağıtın. [Yönetilen Google Play uygulamaları ekleme](apps-add-android-for-work.md) adımları listelenir.
- İOS için Microsoft Outlook ve Android e-posta profillerinin desteklememektedir. Bunun yerine, bir uygulama yapılandırma İlkesi dağıtın. Daha fazla bilgi için [Outlook yapılandırma ayarı](app-configuration-policies-outlook.md).
- E-posta profilleri cihaz gruplarına (değil kullanıcı grupları) hedeflenen cihaza teslim edilemedi. Ardından aygıtın birincil kullanıcıya sahip olduğunda, cihazı hedefleyen çalışması gerekir. E-posta profili kullanıcı sertifikaları içeriyorsa, hedef kullanıcı gruplarına emin olun.
- Kullanıcıların art arda için e-posta profili parolasını girmeniz istenebilir. Bu senaryoda, e-posta profilinde başvurulan tüm sertifikaları kontrol edin. Sertifikalardan birinin bir kullanıcıyı hedef değil, Intune e-posta profili dağıtmak için deneme.

## <a name="device-already-has-an-email-profile-installed"></a>Cihazda zaten yüklü bir e-posta profili var

Kullanıcılar, Intune veya Office 365 MDM kaydetmeden önce bir e-posta profili oluşturursanız, Intune tarafından dağıtılan e-posta profilini beklendiği gibi çalışmayabilir:

- **iOS**: Intune, konak adına ve e-posta adresini temel alan bir var olan ve yinelenen e-posta profili olduğunu algılar. Kullanıcı tarafından oluşturulmuş bir e-posta profili Intune tarafından oluşturulan profilin dağıtımını engeller. İOS kullanıcıları genellikle bir e-posta profili oluşturma ardından kaydolduğundan ortak bir sorunu budur. Şirket portalı uygulaması, kullanıcı uyumsuzsa ve e-posta profilini kaldırmak için kullanıcı isteyebilir belirtir.

  Kullanıcı, Intune profilinin dağıtılabilmesi e-posta profillerini kaldırmalısınız. Bu sorunu önlemek için kullanıcılarınızdan kaydetmeye ve Intune'un e-posta profili dağıtmasına izin vermelerini. Ardından, kullanıcılar e-posta profillerini oluşturabilir.

- **Windows**: Intune, konak adına ve e-posta adresini temel alan bir var olan ve yinelenen e-posta profili olduğunu algılar. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

- **Samsung KNOX Standard**: Intune e-posta adresini temel alan bir yinelenen bir e-posta hesabı olduğunu algılar ve bunu Intune profili bunun üzerine yazar. Kullanıcı bu hesabı yapılandırırsa Intune profili tarafından yeniden üzerine yazılır. Bu, hesap yapılandırmasının üzerine yazılan kullanıcı için karışıklığa neden olabilir.

Samsung KNOX, ana bilgisayar adı, profili tanımlamak için kullanmaz. Bunlar birbirinin üzerine yazılacağından, farklı konaklarda aynı e-posta adresine dağıtmak için birden çok e-posta profilleri oluşturmayın öneririz.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>KNOX Standard cihazı için 0x87D1FDE8 hatası

**Sorunu**: Oluşturma ve dağıtma Exchange Active Sync Samsung KNOX Standard için farklı Android cihazlar için e-posta profilini sonra **0x87D1FDE8** veya **düzeltme başarısız** cihazın hatayı gösterir Özellikler > ilke sekmesinde.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmez ve profilinizde bu seçeneğin belirlenmesi olmamalıdır. Cihazların ilkeyi 24 saate kadar işlemek için yeterli zamana sahip olduğunuzdan emin olun.

## <a name="unable-to-send-images-from--email-account"></a>E-posta hesabından resim gönderilemedi

Otomatik olarak yapılandırılan e-posta hesaplarına sahip kullanıcılar, cihazlarından resim veya görüntü gönderemez. Bu senaryo oluşabilir **üçüncü taraf uygulamalardan gönderilmesine izin ver** etkin değil.

### <a name="intune-solution"></a>Intune çözümü

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Seçin **cihaz Yapılandırması** > **profilleri**.
3. E-posta profili seçin > **özellikleri** > **ayarları**.
4. Ayarlama **üçüncü taraf uygulamalardan gönderilmesine izin ver** ayarını **etkinleştirme**.

### <a name="configuration-manager-hybrid"></a>Configuration Manager karma

1. Configuration Manager konsolunu açın > **varlıklar ve Uyumluluk**.

2. Genişletin **genel bakış** > **uyumluluk ayarları** > **şirket kaynağına erişim**seçip **e-posta profilleri**.

3. E-posta profiline sağ tıklayın ve **Özellikler**’i açın.

4. **Eşitleme Ayarları** sekmesinde **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Alma [destekleyen Microsoft gelen Yardım](get-support.md), veya [topluluk forumları](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
