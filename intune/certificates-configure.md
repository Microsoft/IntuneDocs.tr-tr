---
title: Microsoft Intune - Azure’da sertifika profilleri oluşturma | Microsoft Docs
description: Cihazlarınız için, SCEP veya PKCS sertifika ortamını yapılandırarak bir sertifika profili ekleyin veya oluşturun, ortak sertifikayı dışa aktarın, Azure portalında profili oluşturun ve ardından Azure portalında Microsoft Intune'daki sertifika profillerine SCEP veya PKCS atayın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f13b5b92ca442f4b5ae05d3567f8385288d92909
ms.sourcegitcommit: 6b5907046f920279bbda3ee6c93e98594624c05c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69582925"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Microsoft Intune'daki cihazlarınız için sertifika profili yapılandırma

Kullanıcılara VPN, Wi-Fi veya e-posta profilleri üzerinden şirket kaynaklarına erişim izni verirsiniz. Sertifikaları kullanarak bu bağlantıların kimliklerini doğrulayabilirsiniz. Sertifikaları kullandığınızda, son kullanıcılarınızın kimlik doğrulaması yapmak için kullanıcı adı veya parola girmeleri gerekmez.

Bu sertifikaları yönettiğiniz cihazlara atamak için Intune'u kullanabilirsiniz. Intune aşağıdaki sertifika türlerini atamayı ve yönetmeyi destekler:

- Basit Sertifika Kayıt Protokolü (SCEP)
- PKCS#12 (veya PFX)

Bu sertifika türlerinden her birinin kendi önkoşulları ve altyapı gereksinimleri vardır.


## <a name="overview"></a>Genel Bakış

1. Doğru sertifika altyapısının ayarlandığından emin olun. [SCEP sertifikalarını](certificates-scep-configure.md) ve [PKCS sertifikalarını](certficates-pfx-configure.md) kullanabilirsiniz.

2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Sertifikayı yüklemek için, her cihaza bir **Güvenilen sertifika profili** oluşturun ve atayın. Bu profili atadığınızda Intune ile yönetilen cihazlar kök sertifikayı ister ve alır. Her platform için ayrı profil oluşturmanız gerekir. Aşağıdaki platformlar için güvenilen sertifika profilleri sağlanır:

    - iOS 8.0 ve üzeri
    - macOS 10.11 ve üzeri
    - Android 4.0 ve üzeri
    - Android Kurumsal  
    - Windows 8.1 ve üzeri
    - Windows Phone 8.1 ve üzeri
    - Windows 10 ve üzeri

    > [!NOTE]  
    > *Adanmış cihazlar Için Android Enterprise*çalıştıran cihazlarda sertifika profilleri desteklenmez.

3. Sertifika profilleri oluşturarak cihazların VPN, Wi-Fi ve e-posta erişimi kimlik doğrulaması için kullanılacak bir sertifika istemelerini sağlayın. Aşağıdaki profil türleri farklı platformlar için kullanılabilir:  

   | Platform     |PKCS sertifikası|SCEP sertifikası| PKCS içeri aktarılmış sertifikası | 
   |--------------|----------------|----------------|-------------------|
   | Android                | Evet    | Evet    | Evet    |
   | Android Kurumsal     | Evet    | Evet    | Evet    |
   | iOS                    | Evet    | Evet    | Evet    |
   | Mac OS                  |        | Evet    | Evet    |
   | Windows Phone 8.1      |        | Evet    | Evet    |
   | Windows 8.1 ve üzeri  |        | Evet    |        |
   | Windows 10 ve üzeri   | Evet    | Evet    | Evet    |

   Her cihaz platformu için ayrı profil oluşturduğunuzdan emin olun. Profili oluştururken daha önce oluşturduğunuz güvenilen kök sertifika profiliyle ilişkilendirin.

### <a name="further-considerations"></a>Dikkat edilecek diğer konular

- Kuruluş Sertifika Yetkiliniz yoksa, oluşturmanız gerekir
- SCEP profillerini kullanıyorsanız, Ağ Cihazı Kayıt Hizmeti (NDES) sunucusu da yapılandırın
- SCEP veya PKCS profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırın


## <a name="step-1-configure-your-certificate-infrastructure"></a>1\. adım: Sertifika altyapınızı yapılandırma

Her sertifika profili türü için altyapıyı yapılandırmaya yardımcı olması için aşağıdaki makalelerden birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>2\. adım: Güvenilen kök CA sertifikanızı dışarı aktarma

Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir ortak sertifika (.cer) olarak dışarı aktarın. Özel anahtarı (. pfx) dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktarırsınız.

## <a name="step-3-create-trusted-certificate-profiles"></a>3\. adım: Güvenilen sertifika profilleri oluşturma

SCEP veya PKCS sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturun. Her cihaz platformu için bir güvenilen sertifika profili ve SCEP veya PKCS profili gereklidir. Güvenilen sertifikalar oluşturma adımları tüm cihaz platformlarında benzerdir.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da **cihaz yapılandırma** > **profilleri** **Yönet** > profillerprofil > **Oluştur**' u seçin.
2. Aşağıdaki özellikleri girin:

    - **Ad**: Profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **Android kurumsal cihaz sahibi cihazları** veya **IOS cihazları için güvenilen sertifika profili**için güvenilen sertifika profilidir.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:

      - **Android**
      - **Yalnızca Android kurumsal** > **cihaz sahibi**
      - **Yalnızca Android kurumsal** > **iş profili**
      - **iOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 ve üzeri**
      - **Windows 10 ve üzeri**

    - **Profil türü**: **Güvenilen sertifika**seçin.

3. 2\. [adımda kaydettiğiniz sertifikaya gidin: Güvenilen kök CA sertifikanızı](#step-2-export-your-trusted-root-ca-certificate)dışarı aktarıp **Tamam**' ı seçin.
4. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:

    - **Bilgisayar sertifika deposu-kök** SCEP
    - **Bilgisayar sertifika deposu-ara** SCEP
    - **Kullanıcı sertifika deposu-ara** (PKCS, SCEP)

5. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

   >[!NOTE]
   > Android cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir ileti görüntüleyebilir.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Adım 4: SCEP veya PKCS sertifika profilleri oluşturma

Her sertifika profili türünü yapılandırma ve atamaya yönelik yardım için aşağıdaki makalelerden birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)

Güvenilen sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya PKCS sertifika profillerini oluşturun. SCEP sertifika profilini oluştururken, aynı platform için bir güvenilen sertifika profili girin. Bu adım, iki sertifika profilini birbirine bağlasa da her profili ayrı atamalısınız.

## <a name="next-steps"></a>Sonraki adımlar

[Cihaz profillerini atama](device-profile-assign.md)  
[E-postaları imzalamak ve şifrelemek için S/MIME kullanma](certificates-s-mime-encryption-sign.md)  
[Üçüncü taraf sertifika yetkilisi kullanma](certificate-authority-add-scep-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune sertifika profilleriyle kullanılmak üzere NDES yapılandırması sorunlarını giderme](https://support.microsoft.com/help/4459540)

[Microsoft Intune SCEP sertifika profili dağıtımı sorunlarını giderme](https://support.microsoft.com/help/4457481)
