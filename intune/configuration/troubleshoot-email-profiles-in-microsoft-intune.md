---
title: Microsoft Intune-Azure 'da e-posta profillerinin sorunlarını giderme | Microsoft Docs
description: Yinelenen e-posta profilleri ve Samsung KNOX Standard Android cihazlarda hatalar da dahil olmak üzere Microsoft Intune içindeki e-posta profilleriyle ilgili yaygın sorunlar ve çözümleri görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a19830130f992a002b73402f5e13a8f062539917
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512679"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Microsoft Intune 'daki e-posta profilleriyle ilgili yaygın sorunlar ve çözümler

Bazı genel e-posta profili sorunlarını gözden geçirin ve bunları nasıl giderebileceğiniz ve giderebilirim.

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- E-posta profilleri, cihazı kaydeden Kullanıcı için dağıtılır. Intune, e-posta profilini yapılandırmak için kayıt sırasında kullanıcının e-posta profilindeki Azure Active Directory (AD) özelliklerini kullanır. [Cihazlara e-posta ayarları eklemek](email-settings-configure.md) iyi bir kaynak olabilir.
- Android Enterprise için, yönetilen Google Play Store kullanarak Gmail veya dokuz Iş için dağıtım yapın. [Yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md) adımları listeler.
- İOS için Microsoft Outlook/ıpados ve Android e-posta profillerini desteklemez. Bunun yerine, bir uygulama yapılandırma ilkesi dağıtın. Daha fazla bilgi için bkz. [Outlook yapılandırma ayarı](../apps/app-configuration-policies-outlook.md).
- Cihaz gruplarına (Kullanıcı grupları değil) hedeflenmiş e-posta profilleri cihaza teslim edilemeyebilir. Cihazın birincil kullanıcısı varsa, cihaz hedefleme çalışmalıdır. E-posta profili Kullanıcı sertifikaları içeriyorsa, Kullanıcı gruplarını hedeflediğinizden emin olun.
- Kullanıcıların e-posta profili için parolasını girmesi birkaç kez istenebilir. Bu senaryoda, e-posta profilinde başvurulan tüm sertifikaları kontrol edin. Sertifikalardan biri bir kullanıcıya hedeflenmemişse, Intune e-posta profilini dağıtmayı yeniden dener.

## <a name="device-already-has-an-email-profile-installed"></a>Cihazda zaten yüklü bir e-posta profili var

Kullanıcılar Intune veya Office 365 MDM 'ye kaydolmadan önce bir e-posta profili oluşturmazsa, Intune tarafından dağıtılan e-posta profili beklendiği gibi çalışmayabilir:

- **iOS/ıpados**: Intune, ana bilgisayar adı ve e-posta adresine dayalı mevcut, yinelenen bir e-posta profili Kullanıcı tarafından oluşturulan e-posta profili, Intune tarafından oluşturulan profilin dağıtımını engeller. Bu, iOS/ıpados kullanıcılarının tipik olarak bir e-posta profili oluşturması ve ardından kaydedilmesi gibi yaygın bir sorundur. Şirket Portalı uygulama, kullanıcının uyumlu olmadığını ve kullanıcıdan e-posta profilini kaldırmasını isteyebilir.

  Intune profilinin dağıtılması için kullanıcının e-posta profilini kaldırması gerekir. Bu sorunu engellemek için kullanıcılarınıza kaydolmasını ve Intune 'un e-posta profilini dağıtmasına izin vermesini isteyin. Ardından, kullanıcılar e-posta profilini oluşturabilir.

- **Windows**: Intune, konak adına ve e-posta adresine bağlı olarak var olan ve yinelenen bir e-posta profili olduğunu algılar. Intune kullanıcı tarafından oluşturulmuş, var olan e-posta profilinin üzerine yazar.

- **Samsung KNOX Standard**: Intune, e-posta adresini temel alan yinelenen bir e-posta hesabı tanımlar ve Intune profiliyle üzerine yazar. Kullanıcı bu hesabı yapılandırırsa, Intune profili tarafından yeniden yazılır. Bu durum, hesap yapılandırmasının üzerine yazılması durumunda kullanıcıya bazı karışıklık oluşmasına neden olabilir.

Samsung KNOX, profili tanımlamak için konak adı kullanmaz. Farklı konaklarda aynı e-posta adresine dağıtmak üzere birden çok e-posta profili oluşturmanıza gerek kalmaz, birbirlerinin üzerine yazılır.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>KNOX Standard cihazı için 0x87D1FDE8 hatası

**Sorun**: farklı Android cıhazlarda Samsung KNOX Standard için bir Exchange Active Sync e-posta profili oluşturup dağıttıktan sonra, cihazın Özellikler > Ilkesi sekmesinde **0X87d1fde8** veya **düzeltme başarısız** hatası gösterilir.

Samsung KNOX için EAS profili yapılandırmanızı ve kaynak ilkeyi gözden geçirin. Samsung Notes eşitleme seçeneği artık desteklenmiyor ve bu seçenek profilinizde seçilmemelidir. Cihazların ilkeyi işlemek için yeterli zamana sahip olduğundan emin olun, 24 saate kadar.

## <a name="unable-to-send-images-from--email-account"></a>E-posta hesabından resim gönderilemedi

E-posta hesapları otomatik olarak yapılandırılmış kullanıcılar, cihazlarından resim veya resim gönderemez. Bu senaryo, **üçüncü taraf uygulamalardan e-posta gönderilmesine Izin ver** etkinleştirilmemişse gerçekleşebilir.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Yapılandırma profillerinin** > **cihazları** ' nı seçin.
3. E-posta profilinizi > **özellikler** > **Ayarlar**' ı seçin.
4. **Etkinleştirmek**için **üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver** ayarını belirleyin.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft 'un destek yardımına](../fundamentals/get-support.md)ulaşın veya [topluluk forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune)kullanın.
