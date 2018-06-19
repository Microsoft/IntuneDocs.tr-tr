---
title: Microsoft Intune - Azure’da sertifika profilleri oluşturma | Microsoft Docs
description: Cihazlarınız için, SCEP veya PKCS sertifika ortamını yapılandırarak bir sertifika profili ekleyin veya oluşturun, ortak sertifikayı dışa aktarın, Azure portalında profili oluşturun ve ardından Azure portalında Microsoft Intune'daki sertifika profillerine SCEP veya PKCS atayın
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89f8ddc105787bc7ff4f7cfc1e226d28589ecbbf
ms.sourcegitcommit: 9536300a6211bac4bdc733593a40c1ae47611de3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2018
ms.locfileid: "31771814"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Microsoft Intune'daki cihazlarınız için sertifika profili yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kullanıcılarınıza VPN, Wi-Fi veya e-posta profilleri aracılığıyla şirket kaynaklarına erişim izni verdiğinizde, bu bağlantıların kimlik doğrulamasını sertifika kullanarak yapabilirsiniz. Sertifikaları kullandığınızda, bağlantıların kimlik doğrulamasını yapmak için kullanıcı adı veya parola girmeniz gerekmez

Bu sertifikaları yönettiğiniz cihazlara atamak için Intune'u kullanabilirsiniz. Intune aşağıdaki sertifika türlerini atamayı ve yönetmeyi destekler:

- Basit Sertifika Kayıt Protokolü (SCEP)
- PKCS#12 (veya PFX)

Bu sertifika türlerinden her birinin kendi önkoşulları ve altyapı gereksinimleri vardır.

## <a name="overview"></a>Genel bakış

1. Doğru sertifika altyapısını sağladığınızdan emin olun. [SCEP sertifikalarını](certificates-scep-configure.md) ve [PKCS sertifikalarını](certficates-pfx-configure.md) kullanabilirsiniz.

2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Bunu yapmak için **güvenilen sertifika profili** oluşturun ve atayın. Bu profili atadığınızda Intune ile yönettiğiniz cihazlar kök sertifikayı ister ve alır. Her platform için ayrı profil oluşturmanız gerekir. Aşağıdaki platformlar için güvenilen sertifika profilleri sağlanır:

    - iOS 8.0 ve üzeri
    - macOS 10.11 ve üzeri
    - Android 4.0 ve üzeri
    - Android for Work
    - Windows 8.1 ve üzeri
    - Windows Phone 8.1 ve üzeri
    - Windows 10 ve üzeri

3. Sertifika profilleri oluşturarak cihazların VPN, Wi-Fi ve e-posta erişimi kimlik doğrulaması için kullanılacak bir sertifika istemelerini sağlayın. Aşağıdaki platformları çalıştıran cihazlar için **PKCS** veya **SCEP** sertifika profili oluşturabilir ve atayabilirsiniz:

   - iOS 8.0 ve üzeri
   - Android 4.0 ve üzeri
   - Android for Work
   - Windows 10 (masaüstü ve Mobile) ve üzeri

   Aşağıdaki platformları çalıştıran cihazlar için yalnızca **SCEP** sertifika profili kullanabilirsiniz:

   - macOS 10.9 ve üzeri
   - Windows Phone 8.1 ve üzeri

Her cihaz platformu için ayrı profil oluşturduğunuzdan emin olun. Profili oluştururken daha önce oluşturduğunuz güvenilen kök sertifika profiliyle ilişkilendirin.

### <a name="further-considerations"></a>Dikkat edilecek diğer konular

- Kuruluş Sertifika Yetkiliniz yoksa, oluşturmanız gerekir
- SCEP profillerini kullanıyorsanız, Ağ Cihazı Kayıt Hizmeti (NDES) sunucusu da yapılandırın
- SCEP veya PKCS profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırın


## <a name="step-1-configure-your-certificate-infrastructure"></a>Adım 1: Sertifika altyapınızı yapılandırma

Her sertifika profili türüne yönelik altyapı yapılandırmasına yardımcı olması için aşağıdaki konulardan birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Adım 2: Güvenilen kök CA sertifikanızı dışarı aktarma

Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir ortak sertifika (.cer) olarak dışarı aktarın. Özel anahtarı (.pfx) dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktarırsınız.

## <a name="step-3-create-trusted-certificate-profiles"></a>Adım 3 - Güvenilen sertifika profilleri oluşturma
SCEP veya PKCS sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturun. Her cihaz platformu için bir güvenilen sertifika profili ve SCEP veya PKCS profili gereklidir. Güvenilen sertifikalar oluşturma adımları her cihaz platformunda benzerdir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz yapılandırması** bölmesinde **Yönet** > **Profiller**’i seçin.
3. Profiller bölmesinde **Profil oluştur**’u seçin.
4. **Profil oluştur** bölmesinde, güvenilen sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu güvenilen sertifika için cihaz platformunu seçin. Şu anda, sertifika ayarları için aşağıdaki platformlardan birini seçebilirsiniz:

    - **Android**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

6. **Profil türü** açılan listesinde **Güvenilen sertifika**’yı seçin.
7. 1. görevde kaydettiğiniz sertifikaya gidin ve **Tamam**’a tıklayın.
8. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:
    - **Bilgisayar sertifika deposu - Kök**
    - **Bilgisayar sertifika deposu - Ara**
    - **Kullanıcı sertifika deposu - Ara**
8. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

Android cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir ileti görüntüleyebilir.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Adım 4: SCEP veya PKCS sertifika profilleri oluşturma

Her sertifika profili türünü yapılandırmaya ve atamaya yardımcı olması için aşağıdaki konulardan birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)

Güvenilen sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya PKCS sertifika profillerini oluşturun. SCEP sertifika profilini oluştururken, aynı platform için bir güvenilen sertifika profili girin. Bu adım, iki sertifika profilini birbirine bağlasa da her profili ayrı atamalısınız.

## <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atama hakkındaki genel bilgiler için bkz. [Cihaz profillerini atama](device-profile-assign.md).
