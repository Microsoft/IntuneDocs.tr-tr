---
title: "Intune ile sertifikaları yapılandırma | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Wi-Fi, VPN ve diğer bağlantıların güvenliğini sağlamaya yardımcı olan sertifikaları oluşturmak ve atamak için Intune kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: ecb6a806e7870fd2b1986c4247607c9374431151
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Microsoft Intune’da sertifika yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kullanıcılarınıza VPN, Wi-Fi veya e-posta profilleri aracılığıyla şirket kaynaklarına erişim izni verdiğinizde, bu bağlantıların kimlik doğrulamasını sertifika kullanarak yapabilirsiniz. Bunlar, bağlantıların kimlik doğrulamasını yapmak için kullanıcı adı veya parola girme gereksinimini ortadan kaldırır.

Bu sertifikaları yönettiğiniz cihazlara atamak için Intune'u kullanabilirsiniz. Intune aşağıdaki sertifika türlerini atamayı ve yönetmeyi destekler:

- Basit Sertifika Kayıt Protokolü (SCEP)
- PKCS#12 (veya PFX)

Bu sertifika türlerinin her birinin kendi önkoşulları ve altyapı gereksinimleri vardır.

## <a name="general-workflow"></a>Genel iş akışı

1. Doğru sertifika altyapısını sağladığınızdan emin olun. [SCEP sertifikalarını](configure-certificate-infrastructure-for-scep.md) ve [PKCS sertifikalarını](configure-certificate-infrastructure-for-pfx.md) kullanabilirsiniz.
2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Bunu yapmak için **güvenilen sertifika profili** oluşturun ve atayın. Bu profili atadığınızda Intune ile yönettiğiniz cihazlar kök sertifikayı ister ve alır. Her platform için ayrı bir profil oluşturmanız gerekir. Şu platformlar için güvenilen sertifika profilleri sağlanır:
    - iOS 8.0 ve üzeri
    - macOS 10.9 ve üzeri
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

    Aşağıdaki platformlarla yalnızca SCEP sertifika profilini kullanabilirsiniz:

-     macOS 10.9 ve üzeri
-     Windows Phone 8.1 ve üzeri

Her cihaz platformu için ayrı profil oluşturmanız gerekir. Profili oluştururken daha önce oluşturduğunuz güvenilen kök sertifika profiliyle ilişkilendirin.

### <a name="further-considerations"></a>Dikkat edilecek diğer konular

- Kuruluş Sertifika Yetkiliniz yoksa oluşturmanız gerekir.
- Cihaz platformlarınıza bağlı olarak Basitleştirilmiş Sertifika Kayıt Protokolü (SCEP) profili kullanmaya karar verirseniz ayrıca bir Ağ Cihazı Kayıt Hizmeti (NDES) sunucusunu yapılandırmanız gerekir.
- SCEP veya PKCS profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırmanız gerekir.


## <a name="step-1--configure-your-certificate-infrastructure"></a>Adım 1 - Sertifika altyapınızı yapılandırma

Her sertifika profili türüne yönelik altyapı yapılandırmasına yardımcı olması için aşağıdaki konulardan birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](configure-certificate-infrastructure-for-scep.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](configure-certificate-infrastructure-for-pfx.md)


## <a name="step-2---export-your-trusted-root-ca-certificate"></a>Adım 2 - Güvenilen kök CA sertifikanızı dışarı aktarma

Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın. Özel anahtarı dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktaracaksınız.

## <a name="step-3-create-trusted-certificate-profiles"></a>Adım 3 - Güvenilen sertifika profilleri oluşturma
SCEP veya PKCS sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturmanız gerekir. Her cihaz platformu için bir güvenilen sertifika profiline ve SCEP veya PKCS profiline ihtiyacınız vardır. Güvenilen sertifikalar oluşturma akışı her cihaz platformunda benzerdir.

### <a name="to-create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturmak için

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, güvenilen sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu güvenilen sertifika için cihaz platformunu seçin. Şu anda, sertifika ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
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
8. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).


> [!Note]
> Android cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir bildirim görüntüler.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Adım 4: SCEP veya PKCS sertifika profilleri oluşturma

Her sertifika profili türünü yapılandırmaya ve atamaya yardımcı olması için aşağıdaki konulardan birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](configure-certificate-infrastructure-for-scep.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](configure-certificate-infrastructure-for-pfx.md)

Güvenilen sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya PKCS sertifika profillerini oluşturun. SCEP sertifika profilini oluştururken, aynı platform için bir güvenilen sertifika profili belirtmeniz gerekir. Bu, iki sertifika profilini birbirine bağlasa da her profili ayrı atamalısınız.


## <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atama hakkındaki genel bilgiler için bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).

