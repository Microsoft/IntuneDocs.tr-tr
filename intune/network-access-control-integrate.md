---
title: Ağ erişim denetimini Microsoft Intune - Azure ile tümleştirme | Microsoft Docs
description: Ağ erişim denetimi (NAC) çözümleri, Intune kullanan cihazlarda kayıt ve uyumluluğu denetler. NAC, belirli davranışları içerir ve koşullu erişim ile çalışır. Çözümü eklemek için adımlara bakın ve ortak çözümlerin bir listesini alın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9663691053d8ecd204ad899805153d0bfb25e6f
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041565"
---
# <a name="network-access-control-nac-integration-with-intune"></a>Ağ erişim denetimini (NAC) Intune ile tümleştirme

Intune, cihazlar şirket içi kaynaklara erişmeye çalıştığında kuruluşların şirket verilerini güvenlik altına almasına yardımcı olmak için ağ erişim denetimi iş ortakları ile tümleştirilebilir.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Intune ve NAC çözümleri kuruluş kaynaklarınızı korumaya nasıl yardımcı olur?

NAC çözümleri, erişim denetimi kararları vermek için cihaz kaydını ve Intune ile uyumluluk durumunu kontrol eder. Cihaz kayıtlı değilse veya kayıtlı ama Intune cihaz uyumluluk ilkeleriyle uyumlu değilse bu cihazın kayıt veya cihaz uyumluluk denetimi için yeniden Intune’a yönlendirilmesi gerekir.

### <a name="example"></a>Örnek

Cihaz kayıtlı ve Intune ile uyumlu ise NAC çözümü, cihazın şirket kaynaklarına erişmesine izin verecektir. Örneğin kullanıcılar şirketin Wi-Fi veya VPN kaynaklarına erişmeye çalışırken erişimlerine izin verilebilir veya erişimleri engellenebilir.

## <a name="feature-behaviors"></a>Özellik davranışları

Intune’la etkin olarak eşitleme yapan cihazlar **Uyumlu** / **Uyumsuz**’dan **Eşitlenmedi** (veya **Bilinmiyor**) durumuna taşınamaz. Yeni kaydedilmiş ve uyumluluğu henüz değerlendirilmemiş cihazlar için **Bilinmiyor** durumu korunur.

Kaynaklara erişimi engellenmiş cihazlar için, engelleme hizmetinin tüm kullanıcıları cihazın neden engellendiğini belirlemek üzere [yönetim portalına](https://portal.manage.microsoft.com) yönlendirmesi gerekir.  Kullanıcılar bu sayfayı ziyaret ederse, cihazları zaman uyumlu olarak uyumluluk için yeniden değerlendirilir.

## <a name="nac-and-conditional-access"></a>NAC ve koşullu erişim

NAC, erişim denetimi kararları sağlamak için koşullu erişimle birlikte çalışır. Daha fazla bilgi için bkz. [Intune ile koşullu erişimi kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>NAC tümleştirmesi nasıl çalışır?

Aşağıdaki listede, Intune ile tümleştirildiğinde NAC tümleştirmesinin nasıl çalıştığına genel bir bakış sağlanır. İlk üç adımda (1-3), ekleme işlemi açıklanır. 4-9. adımlar, NAC çözümü ile Intune tümleştirildiğinde devam eden işlemi açıklamaktadır.

![NAC, Intune ile nasıl çalışır kavramsal resmi](./media/ca-intune-common-ways-2.png)

1. NAC iş ortağı çözümünü Azure Active Directory (AAD) ile kaydedin ve Intune NAC API’sine temsilci izinleri verin.
2. NAC iş ortağı çözümünü, Intune bulma URL’si de dahil olmak üzere uygun ayarlarla yapılandırın.
3. NAC iş ortağı çözümünü, sertifika kimlik doğrulaması için yapılandırın.
4. Kullanıcı, şirket Wi-Fi erişim noktasına bağlanır veya bir VPN bağlantısı isteği yapar.
5. NAC iş ortağı çözümü, cihaz bilgilerini Intune’a iletir ve cihaz kaydı ve uyumluluk durumunu Intune’a sorar.
6. Cihaz uyumlu veya kayıtlı değilse NAC iş ortağı çözümü kullanıcıya kaydolmasını veya cihaz uyumluluğunu sağlamasını söyler.
7. Cihaz, uygun olduğunda uyumluluk ve kayıt durumunu yeniden doğrulamayı dener.
8. Cihaz kayıtlı ve uyumlu hale geldikten sonra NAC iş ortağı çözümü, durumu Intune’dan alır.
9. Bağlantı başarılı bir şekilde kurulur ve böylece cihazın şirket kaynaklarına erişimi sağlanır.

## <a name="use-nac-for-vpn-on-your-ios-devices"></a>NAC iOS cihazlarınızdaki VPN için kullanın.  

- NAC VPN profilinde NAC etkinleştirmeden aşağıdaki VPN üzerinde kullanılabilir:

  - NAC Cisco eski AnyConnect
  - F5'e Erişim eski
  - Citrix VPN

- NAC, ayrıca Citrix SSO ve F5'e erişimi için kullanılabilir. NAC için Citrix SSO'yu etkinleştirmek için:

  - Citrix ağ geçidi 12.0.59 kullanın veya daha yüksek.  
  - Kullanıcılar, Citrix SSO 1.1.6 olmalıdır veya sonraki bir sürümü yüklü.
  - [NetScaler NAC için Intune ile tümleştirme](https://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html) Citrix ürün belgelerinde açıklandığı gibi.
  - VPN profilinde seçin **temel ayarları** > **etkinleştirme ağ erişim denetimi (NAC)** > seçin **kabul ediyorum**.

  Güvenlik nedenleriyle 24 saatte VPN bağlantısı kesilir. VPN hemen yeniden.

- NAC için F5'e erişimi etkinleştirmek üzere:

  - F5 BIG-IP 13.1.1.5 kullanın. BIG-IP 14 desteklenmez.
  - BIG-IP NAC için Intune ile tümleştirme. [Genel bakış: APM yapılandırma cihaz duruşu için uç nokta yönetim sistemleri ile denetler](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) F5 Kılavuzu adımları listeler.
  - VPN profilinde seçin **temel ayarları** > **etkinleştirme ağ erişim denetimi (NAC)** > seçin **kabul ediyorum**.

  Güvenlik nedenleriyle 24 saatte VPN bağlantısı kesilir. VPN hemen yeniden.

- Ağ erişim denetimi aşağıdaki iOS VPN istemcisi için desteklenmiyor:
  - Cisco AnyConnect

NAC çözümü için daha yeni bu istemcilerden serbest bırakmak için iş ortaklarımızla çalışıyoruz. Bu makalede, çözümleri hazır olduğunuzda, ek bilgilerle güncelleştirilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Cisco ISE’yi Intune ile tümleştirme](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)
- [Citrix NetScaler’ı Intune ile tümleştirme](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)
- [F5 BIG-IP Erişim İlkesi Yöneticisi Intune ile tümleştirme](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-13-0-0/6.html)
- [HP Aruba ClearPass’i Intune ile tümleştirme](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=31271)
- [Squadra güvenlik Çıkarılabilir Medya Yöneticisi’ni (secRMM) Intune ile tümleştirme](http://www.squadratechnologies.com/StaticContent/ProductDownload/secRMM/9.9.0.0/secRMMIntuneAccessControlSetupGuide.pdf)
