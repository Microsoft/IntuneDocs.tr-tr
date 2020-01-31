---
title: Microsoft Intune 'de BitLocker ilkeleri için sorun giderme ipuçları
titleSuffix: Microsoft Intune
description: Intune ilkesi kullanılarak bir cihazda BitLocker şifrelemesini etkinleştirmeyi ve ilkenizin başarıyla bir cihaza dağıtıldığını doğrulama işlemini açıklar.
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 61b703837598ddbe2c0c44874928b4444466c811
ms.sourcegitcommit: 5ad0ce27a30ee3ef3beefc46d2ee49db6ec0cbe3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76886790"
---
# <a name="troubleshoot-bitlocker-policies-in-microsoft-intune"></a>Microsoft Intune 'de BitLocker ilkeleri sorunlarını giderme

Bu makale, Intune yöneticilerinin Windows 10 cihazlarının Intune ilkesi tabanlı BitLocker 'ı nasıl yapılandırduklarını anlamasına yardımcı olabilir. Bu makalede ayrıca, Intune ile yönettiğiniz cihazlarda BitLocker ayarlarıyla ilgili sorunları gidermeye yönelik yönergeler de sağlanmaktadır.  

## <a name="understanding-bitlocker"></a>BitLocker 'ı anlama

BitLocker Sürücü Şifrelemesi, Microsoft Windows işletim sistemleri tarafından sunulan ve kullanıcıların sabit sürücülerinde verileri şifrelemesine olanak tanıyan bir hizmettir. BitLocker işletim sistemi sürücüleri, çıkarılabilir medya sürücüleri ve sabit veri sürücüleri için şifrelemeyi destekler. BitLocker, hassas verilerin daha iyi korunması için 256 bitlik şifreleme kullanımını da destekler.  

Microsoft Intune, Windows 10 cihazlarda BitLocker 'ı yönetmek için aşağıdaki yöntemleri kullanabilirsiniz:

- **Cihaz yapılandırma ilkeleri** -Endpoint Protection 'ı yönetmek üzere bir cihaz yapılandırma profili oluşturduğunuzda Intune 'da belirli yerleşik ilke seçenekleri mevcuttur. Bu seçenekleri bulmak için, [Endpoint Protection için bir cihaz profili oluşturun](endpoint-protection-configure.md#create-a-device-profile-containing-endpoint-protection-settings), *Platform*için **Windows 10 ve üzeri** ' i seçin ve ardından *Ayarlar*için **Windows şifreleme** kategorisi ' ni seçin. 

   Kullanılabilir seçenekler ve özellikler hakkında buradan bilgi edinebilirsiniz: [Windows şifrelemesi](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption).

- **Güvenlik temelleri - güvenlik** [temelleri,](security-baselines.md) Windows cihazlarının güvenli hale getirilmesine yardımcı olmak için ilgili güvenlik ekibinin önerdiği bilinen ayar grupları ve varsayılan değerlerdir. *MDM güvenlik temeli* veya *Microsoft Defender ATP temeli* gibi farklı temel kaynaklar aynı ayarları ve birbirinden farklı ayarları yönetebilir. Ayrıca, cihaz yapılandırma ilkeleriyle yönettiğiniz ayarların aynısını yönetebilirler. 

Intune 'a ek olarak, BitLocker ayarlarının grup ilkesi gibi başka yollarla yönetilmesi veya bir cihaz kullanıcısı tarafından el ile ayarlanması mümkündür.

Ayarların cihaza uygulanma biçimi ne olduğuna bakılmaksızın, BitLocker ilkeleri cihazda şifrelemeyi yapılandırmak için [BITLOCKER CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) 'yi kullanır. BitLocker CSP, Windows 'da yerleşiktir ve Intune atanan bir cihaza bir BitLocker ilkesi dağıttığında, ilkeden gelen ayarların etkili olabilmesi için Windows kayıt defterine uygun değerleri yazan cihazdaki BitLocker CSP 'dir.

BitLocker hakkında daha fazla bilgi edinmek istiyorsanız, aşağıdaki kaynaklara bakın:

- [BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [BitLocker genel bakış ve gereksinimler SSS](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq)

Bu ilkelerin ne yaptığını ve bunların nasıl çalıştığını genel olarak anlayadığınıza göre, BitLocker ayarlarının bir Windows istemcisine başarıyla uygulandığını nasıl doğrulayabileceğinize göz atın.

## <a name="verify-the-source-of-bitlocker-settings"></a>BitLocker ayarları kaynağını doğrulama

Bir Windows 10 cihazında BitLocker sorununu araştırdığınızda, öncelikle sorunun Intune ile ilgili mi yoksa Windows ile ilgili mi olduğunu anlamak önemlidir. Hatanın olası bir kaynağı bilindikten sonra, sorun giderme çabalarınızı doğru yere odakladıktan sonra, gerekirse doğru takımdan destek alabilirsiniz.  

İlk adım olarak, Intune ilkesinin hedef cihaza başarıyla dağıtılıp dağıtılmadığını saptayın. Aşağıdaki örnekte gösterildiği gibi Windows şifreleme (BitLocker) ayarlarını dağıtan bir cihaz yapılandırma ilkesine sahipsiniz:

![Ayarlarla Windows şifreleme cihaz yapılandırma ilkesi](./media/troubleshooting-bitlocker-policies/settings.png)

Ayarların hedeflenen cihaza uygulandığını nasıl doğrulayabilirim? Bunu yapmak için birkaç yol aşağıda verilmiştir.

### <a name="device-configuration-policy-device-status"></a>Cihaz yapılandırma ilkesi cihaz durumu  

BitLocker 'ı yapılandırmak için cihaz yapılandırma ilkesi kullandığınızda, Intune portalında ilkenin durumunu denetleyebilirsiniz.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Yapılandırma profilleri** > **cihazlar** ' ı seçin ve ardından BitLocker ayarlarını içeren profili seçin.

3. Görüntülemek istediğiniz profili seçtikten sonra **cihaz durumu**' nu seçin. Profile atanan cihazlar listelenir ve *cihaz durumu* sütunu, bir cihazın profili başarıyla dağıtmadığını gösterir.

Bir BitLocker ilkesi alan bir cihaz ve sürücünün tamamen şifrelendiğinden bir gecikme olabileceğini unutmayın.  

### <a name="use-control-panel-on-the-client"></a>İstemcide denetim masası 'nı kullanma  

BitLocker 'ı etkinleştirilen ve bir sürücüyü şifrelenen bir cihazda, BitLocker durumunu bir cihazlar denetim masasından görüntüleyebilirsiniz. Cihazda, **sistem ve güvenlik** > **BitLocker Sürücü Şifrelemesi** > **Denetim Masası** 'nı açın. Onay aşağıdaki görüntüde görüldüğü gibi görünür.  

![BitLocker, Denetim Masası 'nda açıktır](./media/troubleshooting-bitlocker-policies/control-panel.png)

### <a name="use-a-command-prompt"></a>Komut istemi kullanın  

BitLocker 'ı etkinleştirilmiş ve bir sürücüyü şifrelenen bir cihazda, yönetici kimlik bilgileriyle komut Istemi ' ni başlatın ve ardından `manage-bde -status`çalıştırın. Sonuçlar aşağıdaki örneğe benzemelidir:  
durum komutunun sonucunu ![](./media/troubleshooting-bitlocker-policies/command.png)

Örnekte:

- **BitLocker koruması** **Açık**
- **Şifreleme yüzdesi** **%100**
- **Şifreleme yöntemi** **XTS-AES 256**

Ayrıca, aşağıdaki komutu çalıştırarak **anahtar koruyucularını** denetleyebilirsiniz:

```cmd
Manage-bde -protectors -get c:
```

Veya PowerShell ile:

```powershell
Confirm-SecureBootUEFI
```

### <a name="review-the-devices-registry-key-configuration"></a>Cihazlar kayıt defteri anahtarı yapılandırmasını gözden geçirin

BitLocker ilkesi bir cihaza başarıyla dağıtıldıktan sonra, cihazda BitLocker ayarlarının yapılandırmasını gözden geçirebileceğiniz aşağıdaki kayıt defteri anahtarını görüntüleyin: *HKEY_LOCAL_MACHINE \Software\microsoft\policymanager\current\devıcebitlocker*. Örnek:

![BitLocker kayıt defteri anahtarı](./media/troubleshooting-bitlocker-policies/registry.png)

Bu değerler BitLocker CSP tarafından yapılandırılır. Anahtarların değerlerinin, Intune Windows şifreleme ilkenizin kaynağında belirtilen ayarlarla eşleştiğinden emin olun. Bu ayarların her biri hakkında daha fazla bilgi için bkz. [BITLOCKER CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp).

> [!NOTE]
> Windows Olay Görüntüleyicisi, BitLocker ile ilgili çeşitli bilgileri de içerir. Burada listelemek için çok fazla yer vardır ancak **BitLocker API 'sine** yönelik arama size çok sayıda faydalı bilgi sağlayacaktır.

### <a name="check-the-mdm-diagnostics-report"></a>MDM Tanılama raporunu denetleme

BitLocker 'ı etkinleştirilen bir cihazda, BitLocker ilkesinin mevcut olduğunu doğrulamak için hedeflenen cihazdan bir MDM tanılama raporu oluşturabilir ve görüntüleyebilirsiniz. İlke ayarlarını raporda görebiliyorsanız, ilkenin başarıyla dağıtıldığını gösteren bir bildirim vardır. *Microsoft* , aşağıdaki bağlantıda, bir Windows CIHAZıNDAN MDM Tanılama raporunun nasıl yakalanacağını açıklar.

> [!VIDEO https://www.youtube.com/embed/WKxlcjV4TNE]

MDM Tanılama raporunu çözümlediğinizde, içerik ilk olarak biraz kafa karıştırıcı görünebilir. Aşağıda, rapordaki ayarlarla ilgili olarak bir ilkedeki ayarlarla nasıl bağıntı yapılacağı gösterilmektedir:

![MDM tanılama raporu örneği](./media/troubleshooting-bitlocker-policies/report.png)

Çıktı sonucu, BitLocker ilkenizin değerlerine karşılık gelen değerleri gösterir:

![Çıktı sonucu değerleri gösterir ](./media/troubleshooting-bitlocker-policies/output.png)

MDM tanılama çıkış sonuçları:

```asciidoc
EncryptionMethodWithXtsOsDropDown: 7 (The value 7 refers to the 256 bit encryption)
EncryptionMethodWithXtsFdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
EncryptionMethodWithXtsRdvDropDown: 6 (The value 6 refers to the 128 bit encryption)
```

Her bir değerin ne anlama geldiğini görmek için [BITLOCKER CSP belgelerine](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) başvurabilirsiniz. Bu örnekte, bir kod parçacığı aşağıdaki görüntüde paylaşılır.

![Değerlerin amaçları](./media/troubleshooting-bitlocker-policies/shared-example.png)

Benzer şekilde, tüm değerleri görebilir ve bunları BitLocker CSP bağlantısından doğrulayabilirsiniz.

> [!TIP]
> MDM Tanılama raporunun birincil amacı, sorun giderirken Microsoft Desteği yardımcı olur. Intune için bir destek durumu açarsanız ve sorun Windows istemcileri içeriyorsa, bu raporu toplamak ve destek isteğinize eklemek her zaman iyi bir fikirdir.

## <a name="troubleshooting-bitlocker-policy"></a>BitLocker Ilkesi sorunlarını giderme

Artık, BitLocker 'ın WIndows 'daki BitLocker CSP 'ye yapılandırılması için BitLocker ilkesinin Intune tarafından başarıyla dağıtıldığını nasıl doğrulayabileceğiniz konusunda iyi bir fikir sahibi olmanız gerekir.

Intune ilkeniz herhangi bir kapasitede mevcut olmadığında **, ilke cihaza ulaşamamalıdır** :

- **Cihaz Microsoft Intune 'e doğru kaydolmuş mi?** Aksi takdirde, ilkeye özgü herhangi bir şeyi gidermeye başlamadan önce bu sorunu ele almanız gerekir. Windows kayıt sorunlarını gidermeyle ilgili Yardım [burada](../enrollment/troubleshoot-windows-enrollment-errors.md)bulunabilir.

- **Cihazda etkin bir ağ bağlantısı var mı?** Cihaz uçak modundayken veya kapatılmışsa veya Kullanıcı cihazı hizmet olmadan bir konumda içeriyorsa, ağ bağlantısı geri yüklenene kadar ilke teslim edilene veya uygulanmaz.

- **BitLocker ilkesi doğru Kullanıcı veya cihaz grubuna dağıtıldı mı?** Doğru Kullanıcı veya cihazın hedeflediğiniz grupların bir üyesi olup olmadığını denetleyin.

**İlke var ancak tüm ayarlar başarıyla yapılandırılmadı** -Intune ilkeniz cihaza ulaştığında, ancak tüm konfigürasyonlar ayarlanmadı:

- **Tüm ilkenin dağıtımı başarısız mi veya yalnızca uygulanan belirli ayarlar mı?** Kendinizi yalnızca bazı ilke ayarlarının uygulandığı bir senaryoya göre görürseniz, aşağıdaki noktalara dikkat edin:

  1. Tüm **Windows sürümlerinde tüm BitLocker ayarları desteklenmez**.
     İlke tek bir birim olarak bir cihaza gelir. bu nedenle, bazı ayarlar uygulanır ve diğerleri yoksa, ilkenin kendine ait alındığından emin olabilirsiniz. Bu senaryoda, cihazdaki Windows sürümü sorunlu ayarları desteklemiyor olabilir. Her bir ayarın sürüm gereksinimleriyle ilgili ayrıntılar için bkz. Windows belgelerindeki [BITLOCKER CSP](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) .

  2. **BitLocker tüm donanımlar üzerinde desteklenmez**.
     Windows 'un doğru sürümüne sahip olsanız bile, temeldeki cihaz donanımının BitLocker şifrelemesi gereksinimlerini karşılamamanız mümkündür. Windows belgelerindeki [BitLocker için sistem gereksinimlerini](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements) bulabilirsiniz, ancak denetlenecek ana şey, cihazın uyumlu bir TPM yongasına (1,2 veya üzeri) ve Trusted COMPUTING Group (TCG) uyumlu bir BIOS veya UEFI bellenimine sahip olması olabilir.

**Örnek araştırma**

- Bir Windows 10 cihazına BitLocker ilkesi dağıtırsınız ve **cihazları şifreleyin** ayarı portalda **hata** durumunu gösterir.

- Adından da anlaşılacağı gibi, bu ayar yöneticinin *BitLocker > cihaz şifrelemesini*kullanarak şifrelemeyi açmasına izin verir. Daha önce bahsedilen sorun giderme ipuçlarını kullanarak, önce MDM Tanılama raporunu kontrol edersiniz. Rapor, cihazda doğru ilkenin dağıtıldığını onaylar:

  ![Rapor, cihazda doğru ilkenin dağıtıldığını doğrular](./media/troubleshooting-bitlocker-policies/mdm-report.png)

- Ayrıca, kayıt defterindeki başarıyı doğrularsınız:

  ![RequiredDeviceEncryption kayıt defteri değeri 1 gösterir](./media/troubleshooting-bitlocker-policies/registry-confirm.png)

- Daha sonra, PowerShell kullanarak TPM 'nin durumunu kontrol edersiniz ve TPM 'nin cihazda kullanılabilir olmadığını göreceksiniz:

  ![PowerShell kullanılarak denetlenen TPM durumu](./media/troubleshooting-bitlocker-policies/tpm-command.png)

- BitLocker TPM 'yi kullandığından, Intune veya ilkeyle ilgili bir sorun nedeniyle BitLocker 'ın başarısız olmaması, ancak cihazın bir TPM yongasına sahip olmaması veya BIOS 'ta TPM 'nin devre dışı bırakılması olabilir.

  Ek bir ipucu olarak, **Microsoft** > **WINDOWS** > **BitLocker API** > **uygulamalar ve hizmetler günlüğü** altında Windows Olay Görüntüleyicisi 'de aynısını doğrulayabilirsiniz. **BITLOCKER API** olay günlüğünde TPM 'nin kullanılamadığı anlamına gelen BIR olay kimliği 853 bulacaksınız:

  ![Olay KIMLIĞI 853](./media/troubleshooting-bitlocker-policies/event-error.png)

  > [!NOTE]
  > Ayrıca, cihazda **TPM. msc** çalıştırarak TPM durumunu da denetleyebilirsiniz.

## <a name="summary"></a>Özet

Intune ile BitLocker ilke sorunlarını giderirken ve bu ilkenin amaçlanan cihaza ulaştığını doğrulayabileceği takdirde, sorunun doğrudan Intune ile ilgili olmadığını varsaymak güvenlidir. Sorun, Windows işletim sistemi veya donanımla ilgili bir sorun olabilir. Bu durumda, TPM yapılandırması veya UEFı ve güvenli önyükleme gibi diğer alanlara bakmaya başlayın.

## <a name="next-steps"></a>Sonraki adımlar  

BitLocker ile çalışırken size yardımcı olabilecek daha fazla kaynak aşağıda verilmiştir:

- [BitLocker ürün belgeleri](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
- [BitLocker sistem gereksinimleri](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview#system-requirements)
- [BitLocker hakkında sık sorulan sorular](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)
- [BitLocker CSP belgeleri](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)
- [Intune Windows şifreleme ilkesi ayarları](https://docs.microsoft.com/intune/endpoint-protection-windows-10#windows-encryption)
- [AAD/MDM kullanan donanımdan bağımsız otomatik BitLocker şifrelemesi](https://blogs.technet.microsoft.com/home_is_where_i_lay_my_head/2017/06/07/hardware-independent-automatic-bitlocker-encryption-using-aadmdm/)
- [Otomatik pilot cihazlarda BitLocker şifrelemesi için CSP Ilkesi](https://techcommunity.microsoft.com/t5/Windows-10-security/CSP-policy-for-bitLocker-encryption-on-autopilot-devices/m-p/284537)
- [Intune ile BitLocker ilkesi oluşturma ve dağıtma ile ilgili izlenecek yol](https://blogs.technet.microsoft.com/cbernier/2017/07/11/windows-10-intune-windows-bitlocker-management-yes/)