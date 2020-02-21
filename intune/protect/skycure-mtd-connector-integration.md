---
title: Microsoft Intune ile Symantec tümleştirmesini ayarlama
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Symantec Endpoint Protection Mobile çözümünü ayarlama.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f639c4d2c2bcfa62f828fa18973fe6a513b1a82
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514872"
---
# <a name="set-up-symantec-endpoint-protection-mobile-integration-with-intune"></a>Symantec Endpoint Protection Mobile'ın Intune ile tümleştirmesini ayarlama

Symantec Endpoint Protection Mobile (SEP Mobile) çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın. Çoklu Oturum Açma özelliklerini kullanabilmek için Azure AD’ye SEP Mobile uygulamalarını eklemelisiniz.

> [!NOTE]
> Bu mobil tehdit savunma satıcısı, kayıtlı olmayan cihazlar için desteklenmez.

## <a name="before-you-begin"></a>Başlamadan önce

### <a name="azure-ad-account-used-to-integrate-intune-and-sep-mobile"></a>Intune ile SEP Mobile'ı tümleştirmek için kullanılan Azure AD hesabı

- SEP Mobile Temel kurulum işlemine başlamadan önce, [Symantec Endpoint Protection Mobile Yönetim konsolunda](https://aad.skycure.com) Azure AD hesabınızın düzgün yapılandırıldığından emin olun.
- Tümleştirmeyi gerçekleştirmek için Azure AD hesabının bir genel yönetici hesabı olması gerekir.
### <a name="network-setup"></a>Ağ Kurulumu

[Yüklemeden sonra Sep Manager 'ı yapılandırma](https://support.symantec.com/us/en/article.HOWTO80819.html)adlı Symantec makalesine başvurarak, AĞıNıZıN, Sep Mobil kurulum ile tümleştirme için düzgün şekilde yapılandırıldığından emin olabilirsiniz.

### <a name="full-integration-vs-read-only"></a>Tam tümleştirme ve salt okunurdur

SEP Mobile, Intune ile iki tümleştirme modunu destekler:

- **Salt okunur tümleştirme (Temel kurulum):** Yalnızca Azure Active Directory’den cihazların envanterini çıkarır ve Symantec Endpoint Protection Mobile Yönetim konsolunu bunlarla doldurur.
<br>
  - Symantec Endpoint Protection Mobile Yönetim konsolunda **Cihazların durumunu ve riskini Intune’a raporla** ve **Güvenlik olaylarını da Intune’a raporla** kutuları seçili değilse tümleştirme salt okunur moddadır ve dolayısıyla Intune’da cihazların durumunu (uyumlu veya uyumsuz) asla değiştirmez.
<br></br>
- **Tam tümleştirme:** SEP Mobile'ın riskli cihazları ve güvenlik olayı ayrıntılarını Intune’a raporlamasına olanak tanır; bu da, iki bulut hizmeti arasında çift yönlü bir iletişim oluşturur.

### <a name="how-are-the-sep-mobile-apps-used-with-azure-ad-and-intune"></a>SEP Mobile uygulamaları Azure AD ve Intune ile nasıl kullanılır?

- **iOS uygulaması:** Son kullanıcıların bir iOS/ıpados uygulaması kullanarak Azure AD 'de oturum açmasına olanak tanır.

- **Android uygulaması:** Son kullanıcıların Android uygulaması kullanarak Azure AD’de oturum açmasına olanak tanır.

- **Yönetim uygulaması:** Bu, Intune ile hizmetler arası iletişime olanak tanıyan SEP Mobile Azure AD çok kiracılı uygulamasıdır.

## <a name="to-set-up-the-read-only-integration-between-intune-and-sep-mobile"></a>Intune ile SEP Mobile arasında salt okunur tümleştirme ayarlamak için

> [!IMPORTANT]
> SEP Mobile yönetici kimlik bilgileri, Azure Active Directory’de geçerli bir kullanıcıya ait bir e-postadan oluşmalıdır; aksi takdirde, oturum açılamaz. SEP Mobile, Çoklu Oturum Açma (SSO) kullanarak yöneticisinin kimliğini doğrulamak için Azure Active Directory kullanır.

1. [Symantec Endpoint Protection Mobile Management Console](https://aad.skycure.com)'a gidin.

2. **SEP Mobile yönetici kimlik bilgilerinizi** girin ve **Devam**'ı seçin.

3. **Ayarlar**’a gidin ve **Intune Tümleştirmesi**’nin altında **Temel Kurulum**’u seçin.

4. **iOS Uygulaması**'nın yanında **Active Directory'ye Ekle**'yi seçin.

    ![Symantec Endpoint Protection mobil yönetim konsolunun görüntüsü](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

5. Oturum açma sayfası açıldığında Intune kimlik bilgilerinizi girin ve **Kabul Et**’i seçin.

    ![İOS/ıpados uygulaması Intune oturum açma istemi görüntüsü](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

6. Uygulama Azure AD'ye eklendikten sonra, uygulamanın başarıyla eklendiğine ilişkin bir gösterge görürsünüz.

    ![İOS/ıpados uygulaması tamamlama ekranının görüntüsü](./media/skycure-mtd-connector-integration/symantec-portal-basic-added.png)

7. **SEP Mobile Android** ve **Yönetim** uygulamaları için bu adımları yineleyin.

### <a name="add-an-azure-ad-security-group-into-sep-mobile"></a>SEP Mobile'a Azure AD Güvenlik grubu ekleme

SEP Mobile çalıştıran tüm cihazların yer aldığı Azure AD güvenlik grubunu eklemelisiniz.

- SEP Mobile çalıştıran cihazların tüm güvenlik gruplarını girin ve seçin, ardından değişiklikleri kaydedin.

    ![SEP Mobile uygulamaları için kullanıcı gruplarını gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

SEP Mobile, Mobile Threat Defense hizmetini çalıştıran cihazları Azure AD güvenlik gruplarıyla eşitler.

![SEP mobil yönetim konsolundaki güvenlik grubu yapılandırması görüntüsü](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.png)

## <a name="to-set-up-the-full-integration-between-intune-and-sep-mobile"></a>Intune ile SEP Mobile arasında tam tümleştirmeyi ayarlamak için

### <a name="retrieve-the-directory-id-in-azure-ad"></a>Azure AD'de Dizin Kimliğini alma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.

2. Arama kutusuna "Active Directory" yazın ve ardından **Azure Active Directory**'yi seçin.

3. **Özellikler**’i seçin.

4. **Dizin Kimliği**'nin yanında, kopyala simgesini seçin ve bunu güvenli bir konuma yapıştırın. Bu kimliğe sonraki bir adımda ihtiyacınız olacaktır.

    ![Azure portalında Dizin Kimliğini gösteren resim](./media/skycure-mtd-connector-integration/symantec-azure-portal-directory-ID.png)

### <a name="optional-create-a-dedicated-security-group-for-devices-that-need-to-run-the-sep-mobile-apps"></a>(İsteğe bağlı) SEP Mobile uygulamalarını çalıştırması gereken cihazlar için ayrılmış bir Güvenlik Grubu oluşturma
1. [Azure portalında](https://portal.azure.com), **Yönet**'in altında **Kullanıcılar ve gruplar**'ı ve ardından **Tüm gruplar**'ı seçin.

2. **Ekle** düğmesini seçin. Grup için bir **Ad** yazın. **Üyelik türü**'nün altında **Atanmış** öğesini seçin.

3. **eler** dikey penceresinde grup üyelerini seçin ve sonra da **Seç** düğmesini seçin.

4. **Grup** dikey penceresinde **Oluştur**'u seçin.

### <a name="set-up-the-integration-between-symantec-endpoint-protection-mobile-and-intune"></a>Symantec Endpoint Protection Mobile ile Intune arasında tümleştirmeyi ayarlama

1. [Symantec Endpoint Protection Mobile Management Console](https://aad.skycure.com)'a gidin.

2. **SEP Mobile yönetici kimlik bilgilerinizi** girin ve **Devam**'ı seçin.

3. **Ayarlar** > **Tümleştirmeler** > **Intune** > **EMM Tümleştirme Seçimi** bölümüne gidin.

4. **Dizin Kimliği** kutusunda, önceki bölümde Azure Active Directory'den kopyaladığınız Dizin Kimliğini yapıştırın ve ayarları kaydedin.

    ![SEP Mobile portalında Dizin Kimliğini gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-directory-ID.png)

5. **Ayarlar** > **Tümleştirmeler** > **Intune** > **Temel Kurulum** bölümüne gidin.

6. **iOS Uygulaması**'nın yanında **Active Directory'ye Ekle** düğmesini seçin.

    ![Active Directory iOS/ıpados uygulaması eklemeyi gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

7. Dizini yöneten Office 365 hesabının Azure Active Directory kimlik bilgilerini kullanarak oturum açın.

8. Azure Active Directory için SEP mobil iOS/ıpados uygulamasını eklemek için **kabul et** düğmesini seçin.

    ![Kabul et düğmesini gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

9. **Android uygulaması** ve **Yönetim Uygulaması** için de ayrı işlemi yineleyin.

10. SEP Mobile uygulamalarını çalıştırmasını gereken tüm kullanıcı gruplarını, örneğin daha önce oluşturduğunuz güvenlik grubunu seçin.

    ![SEP Mobile uygulamaları için kullanıcı gruplarını gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

11. SEP Mobile seçili gruplardaki cihazları eşitler ve Intune'a bilgileri raporlamayı başlatır. Tam Tümleştirme bölümünde bu verileri görüntüleyebilirsiniz. **Ayarlar** > **Tümleştirmeler** > **Intune** > **Tam Tümleştirme** bölümüne gidin.

     ![SEP Mobile tam tümleştirmesinin tamamlandığını gösteren resim](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.PNG)
## <a name="next-steps"></a>Sonraki adımlar

[SEP Mobile uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
