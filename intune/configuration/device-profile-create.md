---
title: Microsoft Intune - Azure’da cihaz profilleri oluşturma | Microsoft Docs
description: Microsoft Intune’da cihaz yapılandırma profili ekleyin veya yapılandırın. Platform türünü seçin, ayarları yapılandırın, bir kapsam etiketi ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1d6b88b2ff6404f6c60a1c27c167c0721fa82bf
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74832586"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili oluşturma

Cihaz profillerini kullanarak ayar ekleyip yapılandırabilir ve daha sonra bu ayarları kuruluşunuzdaki cihazlara gönderebilirsiniz. [Cihaz profillerini kullanarak cihazlarınıza özellik ve ayar uygulama](device-profiles.md) sayfasında yapabileceğiniz işlemlerle ilgili ayrıntılı bilgilere yer verilmiştir.

Bu makalede:

- Profil oluşturma adımları listelenmiştir.
- Profili "filtrelemek" için kapsam etiketi ekleme adımları gösterilmektedir.
- Windows 10 cihazlarında uygulanabilirlik kurallarını açıklar ve bir kuralın nasıl oluşturulacağını gösterir.
- Cihazların profilleri ve profil güncelleştirmelerini aldığı iade yenileme döngüsü süreleri listelenmiştir.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Yapılandırma profillerinin** > **cihazları** ' nı seçin. Aşağıdaki seçenekler mevcuttur:

    - **Genel bakış**: profillerinizin durumunu listeler ve kullanıcılara ve cihazlara atadığınız profiller hakkında ek ayrıntılar sağlar.
    - **Yönetin**: cihaz profilleri oluşturun, profil içinde çalıştırılacak özel [PowerShell betikleri](../apps/intune-management-extension.md) yükleyin ve [esım](esim-device-configuration.md)kullanarak cihazlara veri planları ekleyin.
    - **İzleme**: bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profilinizde günlükleri görüntüleyin.
    - **Kurulum**: bir SCEP veya PFX Sertifika yetkilisi ekleyin ya da profilde [Telekom gider yönetimini](telecom-expenses-monitor.md) etkinleştirin.

3. **Profil oluştur**' u seçin. Aşağıdaki özellikleri girin:

   - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin **Şirketin tamamı için WP e-posta profili** gibi bir profil adı kullanabilirsiniz.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: cihazlarınızın platformunu seçin. Seçenekleriniz şunlardır:  

       - **Outlook Web Access (OWA)**
       - **Android kurumsal**
       - **iOS/ıpados**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

   - **Profil türü**: oluşturmak istediğiniz ayarların türünü seçin. Gösterilen liste, seçtiğiniz **platforma** bağlıdır.
   - **Ayarlar**: aşağıdaki makaleler her profil türü için ayarları anlatmaktadır:

       - [Yönetim şablonları](administrative-templates-windows.md)
       - [Özel](../custom-settings-configure.md)
       - [Teslim iyileştirme](../delivery-optimization-windows.md)
       - [Cihaz özellikleri](../device-features-configure.md)
       - [Cihaz kısıtlamaları](device-restrictions-configure.md)
       - [Sürüm yükseltme ve mod değiştirme](edition-upgrade-configure-windows-10.md)
       - [Eğitim](education-settings-configure.md)
       - [E-posta](email-settings-configure.md)
       - [Uç nokta koruması](../protect/endpoint-protection-configure.md)
       - [Kimlik koruması](../protect/identity-protection-configure.md)  
       - [Bilgi noktası](kiosk-settings.md)
       - [PKCS sertifikası](../protect/certficates-pfx-configure.md)
       - [PKCS içeri aktarılan sertifika](../protect/certificates-imported-pfx-configure.md)
       - [Tercih dosyası](preference-file-settings-macos.md)
       - [SCEP sertifikası](../protect/certificates-scep-configure.md)
       - [Güvenilir sertifika](../protect/certificates-configure.md)
       - [Güncelleştirme ilkeleri](../software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Microsoft Defender ATP](../protect/advanced-threat-protection.md)
       - [Windows Bilgi Koruması](../protect/windows-information-protection-configure.md)

     Örneğin, platform için **iOS/ıpados** ' ı seçerseniz, profil türü seçenekleriniz aşağıdaki profile benzer şekilde görünür:

     ![Intune'da iOS profili oluşturma](./media/device-profile-create/create-device-profile.png)

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin. Profil oluşturulur ve listede gösterilir.

## <a name="scope-tags"></a>Kapsam etiketleri

Profilinize ayar ekledikten sonra bir kapsam etiketi de ekleyebilirsiniz. İK veya Merkez ofis çalışanları gibi belirli gruplara ilke atamak ve filtrelemek kapsam etiketlerini kullanabilirsiniz.

Kapsam etiketleri ve yapabilecekleriniz hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için RBAC ve kapsam etiketlerini kullanma](../fundamentals/scope-tags.md).

### <a name="add-a-scope-tag"></a>Kapsam etiketi ekleme

1. **Kapsam (Etiketler)** öğesini seçin.
2. **Ekle**'yi seçerek yeni bir kapsam etiketi oluşturun. İsterseniz listedeki kapsam etiketlerinden birini de seçebilirsiniz.
3. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="applicability-rules"></a>Uygulanabilirlik kuralları

Şunlara uygulanır

- Windows 10 ve üzeri

Uygulanabilirlik kuralları, yöneticilerin belirli ölçütlere uyan bir gruptaki cihazları hedeflemesini sağlar. Örneğin, **tüm Windows 10 cihazları** grubuna uygulanan bir cihaz kısıtlama profili oluşturursunuz. Ancak, profili yalnızca Windows 10 Enterprise çalıştıran cihazlara atanmasını istersiniz.

Bu görevi yapmak için bir **uygulanabilirlik kuralı**oluşturun. Bu kurallar aşağıdaki senaryolar için uygundur:

- Windows 10 eğitim (EDU) kullanıyorsunuz. Bellows üniversite 'de, tüm Windows 10 EDU cihazlarını RS3 ve RS4 arasında hedeflemek istiyorsunuz.
- Contoso 'daki Insan kaynakları ' nda tüm kullanıcıları hedeflemek istiyorsunuz, ancak yalnızca Windows 10 Professional veya Kurumsal cihazları istiyorum.

Bu senaryolara yaklaşımak için şunları yapın:

- Bellows üniversite 'deki tüm cihazları içeren bir cihaz grubu oluşturun. Profilde, işletim sistemi en düşük sürümü `16299` ve en yüksek sürüm `17134`, bu nedenle uygulanacak bir uygulanabilirlik kuralı ekleyin. Bu profili Bellows okul cihazları grubuna atayın.

  Atandığında profil, girdiğiniz en düşük ve en yüksek sürüm arasındaki cihazlara uygulanır. Girdiğiniz en düşük ve en yüksek sürümler arasında olmayan cihazlarda, durumları **geçerli değil**olarak gösterilir.

- Contoso 'da Insan kaynakları (HR) içindeki tüm kullanıcıları içeren bir Kullanıcı grubu oluşturun. Profilde, Windows 10 Professional veya Enterprise çalıştıran cihazlara uygulanacak bir uygulanabilirlik kuralı ekleyin. Bu profili HR kullanıcıları grubuna atayın.

  Atandığında, profil Windows 10 Professional veya Enterprise çalıştıran cihazlara uygulanır. Bu sürümleri çalıştırmayan cihazlarda, durumları **geçerli değil**olarak gösterilir.

- Tam olarak aynı ayarlara sahip iki profil varsa, bir uygulanabilirlik kuralı olmayan profil uygulanır. 

  Örneğin, ProfileA, Windows 10 cihazlar grubunu hedefler, BitLocker 'ı etkinleştirmez ve bir uygulanabilirlik kuralına sahip değildir. ProfileB aynı Windows 10 cihazları grubunu hedefler, BitLocker 'ı sağlar ve profili yalnızca Windows 10 Enterprise 'a uygulamak için bir uygulanabilirlik kuralına sahiptir.

  Her iki profil atandığında, bir uygulanabilirlik kuralına sahip olmadığından ProfileA uygulanır. 

Profili gruplara atadığınızda, uygulanabilirlik kuralları bir filtre işlevi görür ve yalnızca ölçütlerinizi karşılayan cihazları hedefleyin.

### <a name="add-a-rule"></a>Kural ekleme

1. **Uygulanabilirlik kuralları**' nı seçin. **Kural**, **özellik**ve **işletim sistemi sürümünü**seçebilirsiniz:

    ![Microsoft Intune cihaz yapılandırma profiline uygulanabilirlik kuralı ekleme](./media/device-profile-create/applicability-rules.png)

2. **Kuralda**, kullanıcıları veya grupları dahil etmek veya dışlamak istediğinizi seçin. Seçenekleriniz şunlardır:

    - **Profil ata**: girdiğiniz ölçütlere uyan kullanıcıları veya grupları içerir.
    - Şu **durumlarda profil atamayın**: girdiğiniz ölçütlere uyan kullanıcıları veya grupları dışlar.

3. **Özellik**' de filtrenizi seçin. Seçenekleriniz şunlardır: 

    - **Işletim sistemi sürümü**: listede, kuralınıza dahil etmek istediğiniz Windows 10 sürümlerini (veya hariç tutmak) denetleyin.
    - **Işletim sistemi sürümü**: kuralınıza dahil etmek (veya dışlamak) istediğiniz **En düşük** ve **en yüksek** Windows 10 sürüm numaralarını girin. Her iki değer de gereklidir.

      Örneğin, en yüksek sürüm için en düşük sürüm ve `10.0.17134.0` (RS4 veya 1803) için `10.0.16299.0` (RS3 veya 1709) girebilirsiniz. Ya da daha ayrıntılı olabilir ve en yüksek sürüm için en düşük sürüm ve `10.0.17134.319` `10.0.16299.001` girebilirsiniz.

4. Değişikliklerinizi kaydetmek için **Ekle** ' yi seçin.

## <a name="refresh-cycle-times"></a>Yenileme döngü süreleri

Intune, yapılandırma profillerinin güncelleştirmelerini denetlemek için farklı yenileme döngüleri kullanır. Cihaz yakın zamanda kaydedildiyse, iade etme daha sık çalışır. [İlke ve profil yenileme döngüleri](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) tahmini yenileme zamanlarını listeler.

Kullanıcılar profil güncelleştirmelerini istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

## <a name="recommendations"></a>Öneriler

Profiller oluştururken aşağıdaki önerileri göz önünde bulundurun:

- İlkelerine ne olduğunu ve ne yaptığını bilmek için ilkelerinizi adlandırın. Tüm [uyumluluk ilkeleri](../protect/create-compliance-policy.md) ve [yapılandırma profillerinin](../configuration/device-profile-create.md) isteğe bağlı bir **Açıklama** özelliği vardır. **Açıklama**' da, özel olarak, diğerlerinin ilkenin ne yaptığını bilmesi için bilgi ekleyin.

  Bazı yapılandırma profili örnekleri şunları içerir:

  **Profil adı**: yönetici şablonu-tüm Windows 10 kullanıcıları için OneDrive yapılandırma profili  
  **Profil açıklaması**: tüm Windows 10 kullanıcıları için en düşük ve temel ayarları içeren OneDrive yönetici şablonu profili. Kullanıcıların kurumsal verileri kişisel OneDrive hesaplarına paylaşmasını engellemek için user@contoso.com tarafından oluşturulur.

  **Profil adı**: tüm iOS kullanıcıları için VPN profili  
  **Profil açıklaması**: Tüm IOS KULLANıCıLARıNıN contoso VPN 'ye bağlanması için en düşük ve temel ayarları içeren VPN profili. Kullanıcıların Kullanıcı adı ve parola istemek yerine VPN 'de otomatik olarak kimlik doğrulaması yaptığı için user@contoso.com tarafından oluşturulur.

- Microsoft Edge ayarlarını yapılandırma, Microsoft Defender Anti-Virus ayarlarını etkinleştirme, iOS jailbreak uygulanmış cihazlarını engelleme vb. gibi kendi görevine göre profilinizi oluşturun.

- Pazarlama, satış, BT yöneticileri veya konuma veya okul sistemine göre belirli gruplar için uygulanan Profiller oluşturun.

- Kullanıcı ilkelerini cihaz ilkelerinden ayırın.

  Örneğin, [Intune 'da Yönetim Şablonları](administrative-templates-windows.md) yüzlerce ADMX ayarı vardır. Bu şablonlar, bir ayarların kullanıcılar veya cihazlar için geçerli olup olmadığını gösterir. Yönetici şablonları oluştururken, kullanıcı ayarlarınızı bir kullanıcılar grubuna atayın ve cihaz ayarlarınızı bir cihaz grubuna atayın.

  Aşağıdaki görüntüde kullanıcılara uygulanabilecek ve/veya cihazlara uygulanabilecek bir ayarın örneği gösterilmektedir:

  ![Kullanıcı ve cihazlar için geçerli olan Intune yönetici şablonu](./media/device-profile-create/setting-applies-to-user-and-device.png)

- Her kısıtlayıcı ilke oluşturduğunuzda, bu değişikliği kullanıcılarınıza iletişim kurun. Örneğin, geçiş kodu gereksinimini 4 karakterden 6 karaktere değiştiriyorsanız, ilke atamadan önce kullanıcılarınızın bunu bilmesini sağlayın.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
