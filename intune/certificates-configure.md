---
title: Microsoft Intune - Azure’da sertifika profilleri oluşturma | Microsoft Docs
description: Cihazlarınız için, SCEP veya PKCS sertifika ortamını yapılandırarak bir sertifika profili ekleyin veya oluşturun, ortak sertifikayı dışa aktarın, Azure portalında profili oluşturun ve ardından Azure portalında Microsoft Intune'daki sertifika profillerine SCEP veya PKCS atayın
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/08/2019
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
ms.openlocfilehash: 37938287cc5ddde6285ec09aa0fffea56f98b3c3
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048949"
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Microsoft Intune'daki cihazlarınız için sertifika profili yapılandırma

Kullanıcılara VPN, Wi-Fi veya e-posta profilleri üzerinden şirket kaynaklarına erişim izni verirsiniz. Sertifikaları kullanarak bu bağlantıların kimliklerini doğrulayabilirsiniz. Sertifikaları kullandığınızda, son kullanıcılarınızın kimlik doğrulaması yapmak için kullanıcı adı veya parola girmeleri gerekmez.

Bu sertifikaları yönettiğiniz cihazlara atamak için Intune'u kullanabilirsiniz. Intune aşağıdaki sertifika türlerini atamayı ve yönetmeyi destekler:

- Basit Sertifika Kayıt Protokolü (SCEP)
- PKCS#12 (veya PFX)

Bu sertifika türlerinden her birinin kendi önkoşulları ve altyapı gereksinimleri vardır.


## <a name="overview"></a>Genel Bakış

1. Doğru sertifika altyapısının ayarlandığından emin olun. [SCEP sertifikalarını](certificates-scep-configure.md) ve [PKCS sertifikalarını](certficates-pfx-configure.md) kullanabilirsiniz.

2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Sertifikayı yüklemek için oluşturma ve atama bir **güvenilen sertifika profili** her aygıt için. Bu profili atadığınızda Intune ile yönetilen cihazlar kök sertifikayı ister ve alır. Her platform için ayrı profil oluşturmanız gerekir. Aşağıdaki platformlar için güvenilen sertifika profilleri sağlanır:

    - iOS 8.0 ve üzeri
    - macOS 10.11 ve üzeri
    - Android 4.0 ve üzeri
    - Android Kurumsal  
    - Windows 8.1 ve üzeri
    - Windows Phone 8.1 ve üzeri
    - Windows 10 ve üzeri

    > [!NOTE]  
    > Çalıştıran cihazlara sertifika profilleri desteklenmez *adanmış cihazlar için Android Kurumsal*.

3. Sertifika profilleri oluşturarak cihazların VPN, Wi-Fi ve e-posta erişimi kimlik doğrulaması için kullanılacak bir sertifika istemelerini sağlayın. Aşağıdaki profil türleri, farklı platformlar için kullanılabilir:  

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


## <a name="step-1-configure-your-certificate-infrastructure"></a>1. adım: Sertifika altyapınızı yapılandırma

Her sertifika profilinin türünü için altyapıyı yapılandırma konusunda yardım için aşağıdaki makalelerden birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>2. adım: Güvenilen kök CA sertifikanızı dışarı aktarma

Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir ortak sertifika (.cer) olarak dışarı aktarın. Özel anahtarı (.pfx) dışarı yok.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktarırsınız.

## <a name="step-3-create-trusted-certificate-profiles"></a>3. adım: Güvenilen sertifika profilleri oluşturma
SCEP veya PKCS sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturun. Her cihaz platformu için bir güvenilen sertifika profili ve SCEP veya PKCS profili gereklidir. Güvenilen sertifikalar oluşturma adımları tüm cihaz platformlarında benzerdir.

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Yönet** > **Profiller** > **Profil oluştur**’u seçin.
4. Güvenilen sertifika profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu güvenilen sertifika için cihaz platformunu seçin. Seçenekleriniz şunlardır:

    - **Android**
    - **Android Kurumsal**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

6. **Profil türü** açılan listesinde **Güvenilen sertifika**’yı seçin.
7. Kaydettiğiniz sertifikaya gidin [2. adım: Güvenilen kök CA sertifikanızı dışarı aktarma](#step-2-export-your-trusted-root-ca-certificate), ardından **Tamam**.
8. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:

    - **Bilgisayar sertifika deposu - Kök**
    - **Bilgisayar sertifika deposu - Ara**
    - **Kullanıcı sertifika deposu - Ara**

9. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

   >[!NOTE]
   > Android cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir ileti görüntüleyebilir.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Adım 4: SCEP veya PKCS sertifika profilleri oluşturma

Yapılandırma ve her sertifika profilinin türünü atama ile ilgili Yardım için aşağıdaki makalelerden birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)

Güvenilen sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya PKCS sertifika profillerini oluşturun. SCEP sertifika profilini oluştururken, aynı platform için bir güvenilen sertifika profili girin. Bu adım, iki sertifika profilini birbirine bağlasa da her profili ayrı atamalısınız.

## <a name="next-steps"></a>Sonraki adımlar
[Cihaz profillerini atama](device-profile-assign.md)  
[E-postaları imzalamak ve şifrelemek için S/MIME kullanma](certificates-s-mime-encryption-sign.md)  
[Üçüncü taraf sertifika yetkilisi kullanma](certificate-authority-add-scep-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[NDES yapılandırması kullanmak Intune sertifika profilleriyle ilgili sorunları giderme](https://support.microsoft.com/help/4459540)

[Microsoft Intune SCEP sertifika profili dağıtımı sorunlarını giderme](https://support.microsoft.com/help/4457481)
