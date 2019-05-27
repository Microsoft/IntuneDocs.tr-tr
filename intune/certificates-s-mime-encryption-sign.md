---
title: İmzalamak ve şifrelemek S/MIME - Microsoft Intune - Azure'ı kullanarak e-posta | Microsoft Docs
description: E-posta dijital sertifikalar Intune imzalamak ve şifrelemek cihazlarda e-postaları için nasıl kullanılacağını öğrenin. Bu sertifikalar, S/MIME adı verilir ve cihaz yapılandırma profilleri kullanılarak yapılandırılır. İmzalama ve şifreleme sertifikalarını PKCS veya özel sertifikaları kullanın ve sertifikaları içeri aktarmak için bağlayıcı kullanma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/10/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5dba3866df9ce5c779deb18cf13852b3d8af1b8d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048887"
---
# <a name="smime-overview-to-sign-and-encrypt-email-in-intune"></a>Oturum açmak ve e-posta ıntune şifrelemek için S/MIME genel bakış

E-posta sertifikaları, S/MIME sertifikası olarak da bilinen, şifreleme ve şifre çözme kullanarak, e-posta iletişimi için ek güvenlik sağlar. Intune S/MIME sertifikaları imzalamak ve aşağıdaki platformları çalıştıran mobil cihazlar için e-postaları şifrelemek için kullanabilirsiniz:

- Android
- iOS
- Mac OS
- Windows 10 ve üzeri
- Windows Phone

iOS cihazlarında, gelen ve gönderilen e-postaları imzalamak ve şifrelemek için S/MIME ve sertifikaları kullanan, Intune tarafından yönetilen bir e-posta profili oluşturabilirsiniz. Diğer platformlarda S/MIME desteklenmiyor olabilir. Destekleniyorsa, S/MIME imzalama ve şifreleme kullanan sertifikaları yükleyin. Ardından, bir son kullanıcı kendi e-posta uygulamasında S/MIME sağlar.

E-posta S/MIME imzalama ve şifreleme Exchange ile ilgili daha fazla bilgi için bkz. [S/MIME iletisi imzalama ve şifreleme için](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

Bu makalede, oturum ve cihazlarınızı şirket e-postaları şifrelemek için S/MIME sertifikaları kullanarak genel bir bakış sağlar.

## <a name="signing-certificates"></a>İmzalama sertifikaları

İmzalama için kullanılan sertifikalar, istemci e-posta uygulamasının e-posta sunucusuyla güvenli bir iletişim kurmasını sağlar.

İmzalama sertifikaları kullanmak için oturum açmada odaklanan sertifika yetkiliniz (CA) bir şablon oluşturun. Microsoft Active Directory Sertifika Yetkilisinde [Sunucu sertifikası şablonu yapılandırma](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) başlığı altında sertifika şablonları oluşturmak için gerekli adımlar listelenir.

Intune’da imzalama sertifikaları PKCS sertifikalarını kullanır. [PKCS sertifikaları yapılandırma ve kullanma](certficates-pfx-configure.md) başlığı altında, Intune ortamınızda nasıl PKCS sertifikası dağıtıp kullanacağınız açıklanır. Bu adımlar şunları içerir:

- PKCS sertifika isteklerini desteklemek için Microsoft Intune Sertifika Bağlayıcısı'nı indirme ve yükleme.
- Cihazlarınız için bir güvenilen kök sertifika profili oluşturma. Bu adım, sertifika yetkiliniz için güvenilen kökü ve ara sertifikaları kullanma ve ardından profili cihazlara dağıtma işlemlerini içerir.
- Oluşturduğunuz sertifika şablonunu kullanarak PKCS sertifika profili oluşturma. Bu profil imzalama sertifikalarını cihazlara verir ve PKCS sertifika profilini cihazlara dağıtır.

Ayrıca, belirli bir kullanıcı için de imzalama sertifikası içeri aktarabilirsiniz. İmzalama sertifikasının bir kullanıcısının kaydettiği her cihaz arasında dağıtılır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın. E-posta imzalama amacıyla kullanılmak üzere Intune’da içeri aktarılan bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta imzalama sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

## <a name="encryption-certificates"></a>Şifreleme sertifikaları

Şifreleme için kullanılan sertifikalar, şifrelenmiş bir e-postanın şifresinin yalnızca hedeflenen alıcı tarafından çözülebilmesini sağlar. S/MIME şifrelemesi, e-posta iletişiminizde kullanabileceğiniz yeni bir güvenlik katmanıdır.

Başka bir kullanıcıya şifrelenmiş bir e-posta gönderirken o kullanıcının şifreleme sertifikasının ortak anahtarı alınır ve gönderdiğiniz e-postayı şifreler. Alıcı, cihazındaki özel anahtarı kullanarak e-postanın şifresini çözer. Kullanıcılarda e-posta şifreleme için kullanılan sertifikaların geçmişi bulunabilir. E-posta şifrelerinin başarıyla çözülmesi için bu sertifikaların her birinin belirli bir kullanıcının tüm cihazlarına dağıtılması gerekir.

E-posta şifreleme sertifikalarının Intune’da oluşturulmaması önerilir. Intune, şifreleme destekli PKCS sertifikası vermeyi desteklese de cihaz başına benzersiz bir sertifika oluşturur. Cihaz başına benzersiz bir sertifika, şifreleme sertifikasının kullanıcının tüm cihazları arasında paylaşıldığı bir S/MIME şifreleme senaryosu için ideal bir yöntem değildir.

S/MIME sertifikalarını Intune kullanarak dağıtmak için kullanıcının şifreleme sertifikalarının tümünü Intune’a aktarmalısınız. Intune daha sonra tüm sertifikaların bir kullanıcısının kaydettiği her cihaz için dağıtır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın.

E-posta şifreleme amacıyla kullanılan, Intune’a aktarılmış bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta şifreleme sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

 > [!NOTE]
 > İçeri aktarılan S/MIME şifreleme sertifikaları, şirket verileri kaldırıldığında veya kullanıcıların yönetim kaydı silindiğinde Intune’dan kaldırılır. Ancak sertifikalar sertifika yetkilisinde iptal edilmez.

## <a name="smime-email-profiles"></a>S/MIME e-posta profilleri

S/MIME imzalama veya şifreleme sertifikası profillerini oluşturduktan sonra [iOS yerel postası için S/MIME’yi etkinleştirebilirsiniz](email-settings-ios.md).

## <a name="next-steps"></a>Sonraki adımlar

- [SCEP sertifikaları kullan](certificates-scep-configure.md)
- [PKCS sertifikalarını kullanma](certficates-pfx-configure.md)
- [Bir ortak CA kullanın](certificate-authority-add-scep-overview.md)
- [PKCS sertifikaları Symantec PKI manager web hizmeti verme](certificates-symantec-configure.md)
