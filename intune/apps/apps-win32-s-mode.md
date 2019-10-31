---
title: S modundaki cihazlarda Win32 uygulamalarını etkinleştirme
titleSuffix: Microsoft Intune
description: Microsoft Intune kullanarak, S modundaki cihazlarda Win32 uygulamalarının nasıl etkinleştirileceğini öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4a0f9a4cdee992914dfebd9552778c882313718
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182917"
---
# <a name="enable-win32-apps-on-s-mode-devices"></a>S modundaki cihazlarda Win32 uygulamalarını etkinleştirme

[Windows 10 S modu](https://docs.microsoft.com/windows/deployment/s-mode) , yalnızca mağaza uygulamalarını çalıştıran kilitli bir işletim sistemidir. Varsayılan olarak, Windows S modu cihazları Win32 uygulamalarının yüklenmesine ve yürütülmesine izin vermez. Bu cihazlar tek bir *Win 10s temel ilkesi*içerir ve bu, S modu cihazının üzerinde herhangi bir Win32 uygulaması çalıştırmasını kilitler. Ancak, Intune 'da **S modu ek ilkesi** oluşturup kullanarak, Windows 10 S modunda yönetilen cihazlara Win32 uygulamaları yükleyip çalıştırabilirsiniz. [Windows Defender uygulama denetimi (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) PowerShell araçlarını kullanarak, Windows S modu için bir veya daha fazla ek ilke oluşturabilirsiniz. Ek ilkeleri [Device Guard Imzalama hizmeti (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) veya [SignTool. exe](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/signing-policies-with-signtool) Ile imzalamanız ve ardından Intune aracılığıyla ilkeleri karşıya yüklemeniz ve dağıtmanız gerekir. Alternatif olarak, ek ilkeleri kuruluşunuzdan bir kod imzalama sertifikası ile imzalayabilirsiniz, ancak tercih edilen yöntem DGSS 'yi kullanmaktır. Kuruluşunuzdaki kod imzalama sertifikasını kullandığınız örnekte, kod imzalama sertifikası 'nın zincirinin bulunduğu kök sertifika cihazda mevcut olmalıdır.

Intune 'da S modu ek ilkesini atayarak, cihazın, yüklenen ilgili imzalı uygulama kataloğuna izin veren mevcut S modu ilkesinde bir özel durum yapmasını sağlayabilirsiniz. İlke, S modu cihazında kullanılabilecek bir izin verilen uygulamalar listesi (uygulama kataloğu) ayarlar.

<!-- Add WDAC tooling diagram  -->

Win32 uygulamalarının bir Windows 10 cihazında S modunda çalışmasına izin verme adımları şunlardır:

1. Windows 10 S kayıt işleminin bir parçası olarak Intune aracılığıyla S modu cihazlarını etkinleştirin.
2. Win32 uygulamalarına izin vermek için ek bir ilke oluşturun:
   - Ek bir ilke oluşturmak için, [Windows Defender uygulama denetimi (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) araçlarını kullanabilirsiniz. İlke içindeki temel ilke kimliği, S modu temel ilke kimliğiyle (istemcide sabit kodlanmış) eşleşmelidir. Ayrıca, ilke sürümünün önceki sürümden daha yüksek olduğundan emin olun.
   - Ek ilkenizi imzalamak için DGSS 'yi kullanırsınız. Daha fazla bilgi için bkz. [cihaz koruyucu imzalama ile kod bütünlüğü ilkesi imzalama](https://docs.microsoft.com/microsoft-store/sign-code-integrity-policy-with-device-guard-signing).
   - İmzalanmış ek ilkesini, Windows 10 S modu ek ilkesi oluşturarak Intune 'a yüklersiniz (aşağıya bakın).
3. Intune aracılığıyla Win32 uygulama kataloglarına izin verin:
   - Katalog dosyaları (her uygulama için 1) oluşturur ve bunları DGSS veya diğer sertifika altyapısını kullanarak imzalar.
   - İmzalı kataloğu, [Microsoft Win32 Içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730)kullanarak *. ıntunewin* dosyasına paketedersiniz. Daha fazla bilgi için bkz. [Win32 uygulama yönetimi-Win32 uygulama içeriğini karşıya yükleme Için hazırlama](~/apps/apps-win32-app-management.md#prepare-the-win32-app-content-for-upload).
   - Intune, [Intune yönetim uzantısını](~/apps/intune-management-extension.md)kullanarak S modu cihazında Win32 uygulamasını yüklemek için imzalı uygulama kataloğunu uygular.

> [!NOTE]
> Windows 10 S modundaki iş kolu (LOB) `.appx` ve `.appx` demeti Microsoft Store Iş için (MSFB) imzalama aracılığıyla desteklenecektir.
>
> Uygulamalar için **S modu ek ilkesinin** , Intune yönetim uzantısı aracılığıyla teslim edilmesi gerekir.
>
> S modu ilkeleri cihaz düzeyinde zorlanır. Cihazda birden çok hedeflenen ilke birleştirilir. Birleştirilmiş ilke cihazda zorunlu kılınır.

Bir Windows 10 S modu ek ilkesi oluşturmak için aşağıdaki adımları kullanın:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde, **Ilke oluştur** > **istemci uygulamaları** > **S modu ek ilkeleri** ' ni seçin.
3. **İlke dosyasını**eklemeden önce, onu oluşturmanız ve imzalamanız gerekir. Daha fazla bilgi için bkz.:
    - [PowerShell araçlarını kullanarak bir WDAC ilkesi oluşturun ve bunu ikili biçime dönüştürün](https://go.microsoft.com/fwlink/?linkid=2095387)
    - [Device Guard Imzalama hizmeti 'ni kullanmayı imzala](https://go.microsoft.com/fwlink/?linkid=2095629) **(önerilir)**

4. **Temel bilgiler** sayfasında, aşağıdaki değerleri ekleyin:

    | Değer | Description |
    |--------------|------------------------------------------------|
    | İlke dosyası | WDAC ilkesini içeren dosya. |
    | Ad | Bu ilkenin adı. |
    | Description | Seçim Bu ilkenin açıklaması. |

5. Ileri ' ye tıklayın **: kapsam etiketleri**.<br>
   **Kapsam etiketleri** sayfasında, isteğe bağlı olarak, Intune 'da uygulama ilkesini kimlerin görebileceğini belirleyebilmek için kapsam etiketlerini yapılandırabilirsiniz. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).

6. **İleri: atamalar**' a tıklayın.<br>
   **Atamalar** sayfası, ilkeyi kullanıcılara ve cihazlara atamanıza olanak tanır. Cihazın Intune tarafından yönetilip yönetilmediği bir cihaza bir ilke atayabileceğinizi unutmayın.
7. Ileri ' ye tıklayın, profil için girdiğiniz değerleri gözden geçirmek için **+ Oluştur** ' a tıklayın.
8. İşiniz bittiğinde, Intune 'da S modu ek ilkesini oluşturmak için **Oluştur** ' a tıklayın. 

İlke oluşturulduktan sonra, Intune 'da S modu ek ilkeleri listesine eklendiğini görürsünüz. İlke atandıktan sonra, ilke cihazlara dağıtılır. Uygulamayı, ek ilkesiyle aynı güvenlik grubuna dağıtmanız gerektiğini unutmayın. Bu cihazlara uygulama hedefleme ve atamayı başlatabilirsiniz. Bu, son kullanıcılarınızın uygulamaları S modundaki cihazlara yüklemesine ve yürütmelerine olanak tanır.

## <a name="removal-of-s-mode-policy"></a>S mod ilkesinin kaldırılması

Şu anda, S modu ek ilkesini cihazdan kaldırmak için, mevcut S modu ek ilkesinin üzerine yazmak üzere boş bir ilke atamanız ve dağıtmanız gerekir.

## <a name="policy-reporting"></a>İlke raporlama

Cihaz düzeyinde zorlanan S modu ek ilkesi yalnızca cihaz düzeyi raporlamaya sahiptir. Cihaz düzeyi raporlama, sucesss ve hata koşulları için kullanılabilir. 

Intune konsolunda S modu raporlama ilkeleri için gösterilen raporlama değerleri:
- **Başarılı**: S modu ek ilkesi etkin.
- **Bilinmiyor**: S modu ek ilkesinin durumu bilinmiyor.
- **Tokenerror**: S modu ek ilkesi yapısal olarak Tamam ancak belirteci yetkilendirmek için bir hata oluştu.
- **NotAuthorizedByToken**: belirteç bu S modu ek ilkesini yetkilendiremez.
- **Policynotfound**: S modu ek ilkesi bulunamadı.

## <a name="next-steps"></a>Sonraki adımlar

- Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).
- Win32 uygulamaları hakkında daha fazla bilgi için bkz. [Intune Win32 uygulama yönetimi](~/apps/apps-win32-app-management.md).
