---
title: "Ağ erişim denetimini Intune ile tümleştirme"
titleSuffix: Intune on Azure
description: "Ağ erişim denetimini (NAC) Intune ile tümleştirme"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15651b3f03959fd96edf1a585d0075204e35e61b
ms.sourcegitcommit: ce49a5c50e0d1e377ecb94185c4e6ac450e4701d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Ağ erişim denetimini (NAC) Intune ile tümleştirme

Intune, cihazlar şirket içi kaynaklara erişmeye çalıştığında kuruluşların şirket verilerini güvenlik altına almasına yardımcı olmak için ağ erişim denetimi iş ortakları ile tümleştirilebilir.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Intune ve NAC çözümleri kuruluş kaynaklarınızı korumaya nasıl yardımcı olur?

NAC çözümleri, erişim denetimi kararları vermek için cihaz kaydı ve Intune ile uyumluluk durumunu kontrol etmekten sorumludur. Cihaz kayıtlı değilse veya kayıtlı ama Intune cihaz uyumluluk ilkeleriyle uyumlu değilse bu cihazın kayıt ve/veya cihaz uyumluluk denetimi için yeniden Intune’a yönlendirilmesi gerekir.

### <a name="example"></a>Örnek

Cihaz kayıtlı ve Intune ile uyumlu ise NAC çözümü, cihazın şirket kaynaklarına erişmesine izin verecektir. Örneğin kullanıcılar şirketin Wi-Fi veya VPN kaynaklarına erişmeye çalışırken erişimlerine izin verilebilir veya erişimleri engellenebilir.

## <a name="nac-and-conditional-access"></a>NAC ve koşullu erişim

NAC, erişim denetimi kararları sağlamak için koşullu erişim ile birlikte çalışır.

- Daha fazla ayrıntı için bkz. [Intune ile koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>NAC tümleştirmesi nasıl çalışır?

Aşağıda, NAC ile Intune tümleştirmesinin nasıl çalıştığı konusunda genel bir fikir edinebilirsiniz. İlk üç adım, ekleme sürecini açıklamaktadır. 4.-9. adımlar, NAC çözümü ile Intune tümleştirildiğinde devam eden işlemi açıklamaktadır.

![NAC, Intune ile nasıl çalışır?](./media/ca-intune-common-ways-2.png)

1.  NAC iş ortağı çözümünü Azure Active Directory (AAD) ile kaydedin ve Intune NAC API’sine temsilci izinleri verin.

2.  NAC iş ortağı çözümünü, Intune bulma URL’si de dahil olmak üzere uygun ayarlarla yapılandırın.

3.  NAC iş ortağı çözümünü, sertifika kimlik doğrulaması için yapılandırın.

4.  Kullanıcı, şirket Wi-Fi erişim noktasına bağlanır veya bir VPN bağlantısı isteği yapar.

5.  NAC iş ortağı çözümü, cihaz bilgilerini Intune’a iletir ve cihaz kaydı ve uyumluluk durumunu Intune’a sorar.

6.  Cihaz uyumlu veya kayıtlı değilse NAC iş ortağı çözümü kullanıcıya kaydolmasını veya cihaz uyumluluğunu sağlamasını söyler.

7.  Cihaz, uyumluluk ve/veya kayıt durumunu yeniden doğrulamayı dener.

8.  Cihaz kayıtlı ve uyumlu hale geldikten sonra NAC iş ortağı çözümü, durumu Intune’dan alır.

9.  Bağlantı başarılı bir şekilde kurulur ve böylece cihazın şirket kaynaklarına erişimi sağlanır.

## <a name="next-steps"></a>Sonraki adımlar

-   [Cisco ISE’yi Intune ile tümleştirme](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Citrix NetScaler’ı Intune ile tümleştirme](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [HP Aruba Clear Pass’i Intune ile tümleştirme](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
