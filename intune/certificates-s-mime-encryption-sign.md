---
title: S/MIME e-posta imzalama ve şifreleme - Azure | Micrososft Docs
description: Microsoft Intune’da e-postaları imzalamak ve şifrelemek için S/MIME'yi kullanma veya etkinleştirme
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a31a43cfe45060891c30a7f159123a30b43173d
ms.sourcegitcommit: 488be75cbee88455b33c68a3ec2acb864d461bf8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "41910675"
---
# <a name="smime-email-signing-and-encryption-in-intune"></a>Intune’da S/MIME e-posta imzalama ve şifreleme

> [!IMPORTANT]
> S/MIME özelliğinde, bu makalede açıklanan bazı geliştirmeler yapıyoruz. Bunun sonucu olarak, S/MIME özelliği Intune'da geçici olarak kaldırıldı. Özellik kullanıma sunulduğunda bu notu kaldıracağız.

S/MIME, şifreleme ve şifre çözme yordamlarını kullanarak e-posta iletişimleriniz için yeni bir güvenlik katmanı sağlar. Microsoft Intune; iOS, Windows, Windows Phone, Android, ve macOS çalıştıran mobil cihazlara gönderilen e-postaları imzalamak veya şifrelemek için S/MIME kullanabilir.

iOS cihazlarında, gelen ve gönderilen e-postaları imzalamak ve şifrelemek için S/MIME ve sertifikaları kullanan, Intune tarafından yönetilen bir e-posta profili oluşturabilirsiniz. Diğer platformlarda S/MIME desteklenmiyor olabilir. Destekleniyorsa, S/MIME imzalama ve şifreleme kullanan sertifikaları yükleyebilirsiniz. Ardından, son kullanıcı e-posta uygulaması için S/MIME’yi etkinleştirebilir.

S/MIME e-posta imzalama ve şifreleme hakkında daha fazla bilgi için bkz. [İleti imzalama ve şifreleme için S/MIME](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).

## <a name="signing-certificates"></a>İmzalama sertifikaları

İmzalama için kullanılan sertifikalar, istemci e-posta uygulamasının e-posta sunucusuyla güvenli bir iletişim kurmasını sağlar.

İmzalama sertifikalarını kullanmak için sertifika yetkilinizde imzalamaya odaklanan bir şablon oluşturun. Microsoft Active Directory Sertifika Yetkilisinde [Sunucu sertifikası şablonu yapılandırma](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) başlığı altında sertifika şablonları oluşturmak için gerekli adımlar listelenir.

Intune’da imzalama sertifikaları PKCS sertifikalarını kullanır. [PKCS sertifikaları yapılandırma ve kullanma](certficates-pfx-configure.md) başlığı altında, Intune ortamınızda nasıl PKCS sertifikası dağıtıp kullanacağınız açıklanır. Bu adımlar şunları içerir:

- PKCS sertifika isteklerini desteklemek için Microsoft Intune Sertifika Bağlayıcısı'nı indirme ve yükleme.
- Cihazlarınız için bir güvenilen kök sertifika profili oluşturma. Bu adım, sertifika yetkiliniz için güvenilen kökü ve ara sertifikaları kullanma ve ardından profili cihazlara dağıtma işlemlerini içerir.
- Oluşturduğunuz sertifika şablonunu kullanarak PKCS sertifika profili oluşturma. Bu profil imzalama sertifikalarını cihazlara verir ve PKCS sertifika profilini cihazlara dağıtır.

Ayrıca, belirli bir kullanıcı için de imzalama sertifikası içeri aktarabilirsiniz. İmzalama sertifikası kullanıcının kaydettiği tüm cihazlara dağıtılır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın. E-posta imzalama amacıyla kullanılmak üzere Intune’da içeri aktarılan bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta imzalama sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

## <a name="encryption-certificates"></a>Şifreleme sertifikaları

Şifreleme için kullanılan sertifikalar, şifrelenmiş bir e-postanın şifresinin yalnızca hedeflenen alıcı tarafından çözülebilmesini sağlar. S/MIME şifrelemesi, e-posta iletişiminizde kullanabileceğiniz yeni bir güvenlik katmanıdır.

Başka bir kullanıcıya şifrelenmiş bir e-posta gönderirken o kullanıcının şifreleme sertifikasının ortak anahtarı alınır ve gönderdiğiniz e-postayı şifreler. Alıcı, cihazındaki özel anahtarı kullanarak e-postanın şifresini çözer. Kullanıcılarda e-posta şifreleme için kullanılan sertifikaların geçmişi bulunabilir. E-posta şifrelerinin başarıyla çözülmesi için bu sertifikaların her birinin belirli bir kullanıcının tüm cihazlarına dağıtılması gerekir.

E-posta şifreleme sertifikalarının Intune’da oluşturulmaması önerilir. Intune, şifreleme destekli PKCS sertifikası vermeyi desteklese de cihaz başına benzersiz bir sertifika oluşturur. Cihaz başına benzersiz bir sertifika, şifreleme sertifikasının kullanıcının tüm cihazları arasında paylaşıldığı bir S/MIME şifreleme senaryosu için ideal bir yöntem değildir.

S/MIME sertifikalarını Intune kullanarak dağıtmak için kullanıcının şifreleme sertifikalarının tümünü Intune’a aktarmalısınız. Intune daha sonra bu sertifikaların tümünü kullanıcının kaydettiği her cihaza dağıtır. Intune’a sertifika aktarmak için [GitHub’daki PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanın.

E-posta şifreleme amacıyla kullanılan, Intune’a aktarılmış bir PKCS sertifikasını dağıtmak için [Intune ile PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md) bölümündeki adımları izleyin. Bu adımlar şunları içerir:

- Microsoft Intune için PFX Sertifika Bağlayıcısı'nı indirin ve yükleyin. Bu bağlayıcı, içeri aktarılan PKCS sertifikalarını cihazlara verir.
- S/MIME e-posta şifreleme sertifikalarını Intune’a aktarın.
- PKCS içeri aktarılan sertifika profili oluşturun. Bu profil, içeri aktarılan PKCS sertifikalarını uygun kullanıcının cihazlarına verir.

 > [!NOTE]
 > İçeri aktarılan S/MIME şifreleme sertifikaları, şirket verileri kaldırıldığında veya kullanıcıların yönetim kaydı silindiğinde Intune’dan kaldırılır. Ancak sertifikalar sertifika yetkilisinde iptal edilmez.

## <a name="smime-email-profiles"></a>S/MIME e-posta profilleri

S/MIME imzalama veya şifreleme sertifikası profillerini oluşturduktan sonra [iOS yerel postası için S/MIME’yi etkinleştirebilirsiniz](email-settings-ios.md).