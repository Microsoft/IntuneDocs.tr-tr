---
title: S/MIME-Microsoft Intune-Azure kullanarak e-posta imzalama ve şifreleme | Microsoft Docs
description: Cihazlarda e-postaları imzalamak ve şifrelemek için Microsoft Intune 'da e-posta dijital sertifikalarını nasıl kullanacağınızı öğrenin. Bu sertifikalara S/MIME denir ve cihaz yapılandırma profilleri kullanılarak yapılandırılır. İmzalama ve şifreleme sertifikaları PKCS veya özel sertifikalar kullanır ve sertifikaları içeri aktarmak için bir bağlayıcı kullanır.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/10/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: adea17c0e013d922c0bc3ccf06ed590828bd79dd
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801484"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Intune 'da e-posta imzalama ve şifreleme için S/MIME 'ye Genel Bakış

S/MIME sertifikası olarak da bilinen e-posta sertifikaları, şifreleme ve şifre çözme kullanarak e-posta iletişimlerinizi ek güvenlik sağlar. Microsoft Intune, aşağıdaki platformları çalıştıran mobil cihazlarda e-postaları imzalamak ve şifrelemek için S/MIME sertifikaları kullanabilir:

- Android
- iOS
- Mac OS
- Windows 10 ve üzeri
- Windows Phone

iOS cihazlarında, gelen ve gönderilen e-postaları imzalamak ve şifrelemek için S/MIME ve sertifikaları kullanan, Intune tarafından yönetilen bir e-posta profili oluşturabilirsiniz. Diğer platformlarda S/MIME desteklenmiyor olabilir. Destekleniyorsa, S/MIME imzalama ve şifreleme kullanan sertifikaları yükler. Ardından, son kullanıcı e-posta uygulamasında S/MIME 'yi etkinleştirmesine izin vermez.

S/MIME e-posta imzalama ve Exchange ile şifreleme hakkında daha fazla bilgi için bkz. [s/MIME, ileti imzalama ve şifreleme için](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

Bu makalede, cihazlarınızdaki e-postaları imzalamak ve şifrelemek için S/MIME sertifikaları kullanma hakkında genel bakış sunulmaktadır.

## <a name="signing-certificates"></a>İmzalama sertifikaları

İmzalama için kullanılan sertifikalar, istemci e-posta uygulamasının e-posta sunucusuyla güvenli bir iletişim kurmasını sağlar.

İmzalama sertifikalarını kullanmak için, sertifika yetkiliniz (CA) üzerinde imzalamaya odaklanan bir şablon oluşturun. Microsoft Active Directory Sertifika Yetkilisinde [Sunucu sertifikası şablonu yapılandırma](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) başlığı altında sertifika şablonları oluşturmak için gerekli adımlar listelenir.

Intune’da imzalama sertifikaları PKCS sertifikalarını kullanır. [PKCS sertifikaları yapılandırma ve kullanma](certficates-pfx-configure.md) başlığı altında, Intune ortamınızda nasıl PKCS sertifikası dağıtıp kullanacağınız açıklanır. Bu adımlar şunları içerir:

- PKCS sertifika isteklerini desteklemek için Microsoft Intune Sertifika Bağlayıcısı'nı indirme ve yükleme.
- Cihazlarınız için bir güvenilen kök sertifika profili oluşturma. Bu adım, sertifika yetkiliniz için güvenilen kökü ve ara sertifikaları kullanma ve ardından profili cihazlara dağıtma işlemlerini içerir.
- Oluşturduğunuz sertifika şablonunu kullanarak PKCS sertifika profili oluşturma. Bu profil imzalama sertifikalarını cihazlara verir ve PKCS sertifika profilini cihazlara dağıtır.

Ayrıca, belirli bir kullanıcı için de imzalama sertifikası içeri aktarabilirsiniz. İmzalama sertifikası, kullanıcının kaydettiği tüm cihazlarda dağıtılır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın. E-posta imzalama amacıyla kullanılmak üzere Intune’da içeri aktarılan bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta imzalama sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

## <a name="encryption-certificates"></a>Şifreleme sertifikaları

Şifreleme için kullanılan sertifikalar, şifrelenmiş bir e-postanın şifresinin yalnızca hedeflenen alıcı tarafından çözülebilmesini sağlar. S/MIME şifrelemesi, e-posta iletişiminizde kullanabileceğiniz yeni bir güvenlik katmanıdır.

Başka bir kullanıcıya şifrelenmiş bir e-posta gönderirken o kullanıcının şifreleme sertifikasının ortak anahtarı alınır ve gönderdiğiniz e-postayı şifreler. Alıcı, cihazındaki özel anahtarı kullanarak e-postanın şifresini çözer. Kullanıcılarda e-posta şifreleme için kullanılan sertifikaların geçmişi bulunabilir. E-posta şifrelerinin başarıyla çözülmesi için bu sertifikaların her birinin belirli bir kullanıcının tüm cihazlarına dağıtılması gerekir.

E-posta şifreleme sertifikalarının Intune’da oluşturulmaması önerilir. Intune, şifreleme destekli PKCS sertifikası vermeyi desteklese de cihaz başına benzersiz bir sertifika oluşturur. Cihaz başına benzersiz bir sertifika, şifreleme sertifikasının kullanıcının tüm cihazları arasında paylaşıldığı bir S/MIME şifreleme senaryosu için ideal bir yöntem değildir.

S/MIME sertifikalarını Intune kullanarak dağıtmak için kullanıcının şifreleme sertifikalarının tümünü Intune’a aktarmalısınız. Ardından Intune, bu sertifikaların tümünü kullanıcının kaydettiği her cihaza dağıtır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın.

E-posta şifreleme amacıyla kullanılan, Intune’a aktarılmış bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta şifreleme sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

 > [!NOTE]
 > İçeri aktarılan S/MIME şifreleme sertifikaları, şirket verileri kaldırıldığında veya kullanıcıların yönetim kaydı silindiğinde Intune’dan kaldırılır. Ancak sertifikalar sertifika yetkilisinde iptal edilmez.

## <a name="smime-email-profiles"></a>S/MIME e-posta profilleri

S/MIME imzalama veya şifreleme sertifikası profillerini oluşturduktan sonra [iOS yerel postası için S/MIME’yi etkinleştirebilirsiniz](../configuration/email-settings-ios.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Sertifikalar için SCEP kullanma](certificates-scep-configure.md)
- [PKCS sertifikalarını kullanma](certficates-pfx-configure.md)
- [İş ortağı CA 'sını kullanma](certificate-authority-add-scep-overview.md)
- [Symantec PKI Manager Web hizmetinden PKCS sertifikaları verme](certificates-digicert-configure.md)
