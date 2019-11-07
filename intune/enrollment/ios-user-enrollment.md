---
title: İOS cihazlarını kaydetme-Kullanıcı kaydı
titleSuffix: Microsoft Intune
description: İOS ve ıpados Kullanıcı kaydını ayarlamayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e538204306ce80d6a13739fc981edf2748a622de
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713462"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>İOS ve ıpados Kullanıcı kaydını ayarlama (Önizleme)

Intune 'u, Apple 'ın Kullanıcı kayıt işlemini kullanarak iOS ve ıpados cihazlarını kaydedecek şekilde ayarlayabilirsiniz. Kullanıcı kaydı, yöneticilere diğer kayıt yöntemleriyle karşılaştırıldığında yönetim seçeneklerinin kolaylaştırılmış bir alt kümesini sağlar.

Kullanıcı kaydında kullanılabilen seçenekler hakkında daha fazla bilgi için bkz. [Kullanıcı kaydı desteklenen eylemler, parolalar ve diğer seçenekler](ios-user-enrollment-supported-actions.md).

> [!NOTE]
> Apple 'ın Intune 'da Kullanıcı kaydı desteği şu anda önizlemededir.

## <a name="prerequisites"></a>Önkoşullar
- [Mobil Cihaz Yönetimi (MDM) Yetkilisi](../fundamentals/mdm-authority-set.md)
- [Apple MDM Anında İletme sertifikası](apple-mdm-push-certificate-get.md)
- [Yönetilen Apple kimlikleri](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web).

## <a name="create-a-user-enrollment-profile-in-intune"></a>Intune 'da Kullanıcı kayıt profili oluşturma

Kayıt profili, kayıt sırasında bir cihaz grubuna uygulanan ayarları tanımlar. 

1. [Microsoft Uç Nokta Yöneticisi Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **cihaz kaydı** ** >  > ** **kayıt türleri (Önizleme)**  > **Profil oluştur** > **iOS**' u seçin. Bu profil, iOS ve ıpados son kullanıcılarınızın kurumsal bir Apple yöntemiyle kaydolmayan cihazlarda sahip olacağı kayıt deneyimini belirtebileceğiniz yerdir. Değişiklik yapmak isterseniz, bu profili oluşturduktan sonra düzenleyebilirsiniz.

    ![Apple kayıt profili oluştur](./media/ios-user-enrollment/create-profile.png)

2. **Temel bilgiler** sayfasında, yönetim amaçları için profil Için bir **ad** ve **Açıklama** girin. Kullanıcılar bu ayrıntıları göremez. Azure Active Directory’de dinamik bir grup oluşturmak için **Ad** alanını kullanabilirsiniz. enrollmentProfileName parametresini, bu kayıt profiliyle cihazlara atamak amacıyla tanımlamak için profil adını kullanın. [Azure Active Directory dinamik grupları](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices) hakkında daha fazla bilgi edinin.

    ![Temel bilgiler sayfası](./media/ios-user-enrollment/basics-page.png)


3. **İleri**'yi seçin.

4. **Ayarlar** sayfasında, kullanıcılara hangi kayıt türünün kullanılacağını tercih edebilirsiniz. Alternatif olarak, varsayılan ayar yapabilirsiniz.

    ![Ayarlar sayfası](./media/ios-user-enrollment/settings-page.png)

    - Bu profildeki tüm kullanıcıların kullanıcı kaydını kullanmasını istiyorsanız aşağıdaki adımları izleyin:
        1. **Kullanıcının cihaz türünü seçmesini iste**için, **Yapılandırılmadı**' yı seçin.
        2. **Varsayılan kayıt türü**Için **Kullanıcı kaydı**' nı seçin.
    - Bu profildeki tüm kullanıcıların cihaz kaydını kullanmasını istiyorsanız aşağıdaki adımları izleyin:
        1. **Kullanıcının cihaz türünü seçmesini iste**için, **Yapılandırılmadı**' yı seçin.
        2. **Varsayılan kayıt türü**Için **cihaz kaydı**' nı seçin.
    - Bu gruptaki tüm kullanıcılara hangi kayıt türünün kullanılacağını tercih etmek istiyorsanız, **kullanıcının cihaz türünü seçmesini iste**için **gerekli** ' yi seçin. Kullanıcılar cihazlarını kaydettiğinde, bu cihaz ve **(Şirket) bu cihazın sahibi** **olduğumu** arasında seçim yapmak için bu seçenek sunulur. Bunlar, eski ' yi seçtiyse, cihaz Kullanıcı kaydı kullanılarak kaydedilir. İkincisini seçtiyse cihaz, cihaz kaydı kullanılarak kaydedilir. Kullanıcı **Bu cihaza sahip olduğumu**seçerse, tüm cihazı güvenli hale getirmek veya yalnızca iş ile ilgili uygulamaları ve verileri güvenli hale getirmek için başka bir seçenek alırlar. Son kullanıcının cihazın sahip olup olmadığı seçimi yalnızca cihazlarına hangi kayıt türünün uygulandığını belirler. Bu Kullanıcı seçeneği, Intune 'daki cihaz sahipliği özniteliğinde yansıtılmaz. Kullanıcı deneyimi hakkında daha fazla bilgi edinmek için bkz. [Şirket KAYNAKLARıNıZA IOS cihaz erişimini ayarlama](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).
    
    > [!NOTE]
    > Aşağıdaki bildirim yanlış ve kullanıcı arabiriminden kaldırılacak.
    > "Kullanıcı kaydıyla hedeflenen cihazlarda çalışmaya yönelik koşullu erişim için, çoklu oturum açma ve Workplace Join etkinleştirmek üzere Azure Authenticator uygulamasını bu kullanıcı grubu için gerekli bir uygulama olarak göndermeniz gerekir."
    > Yönetici olarak, kimlik doğrulayıcı uygulamasını kullanıcılarınıza göndermek için herhangi bir işlem yapmanız gerekmez. Kullanıcılarınıza, bu senaryoların düzgün çalışmasını sağlamak üzere Kullanıcı kayıt işlemini gerçekleştirmek üzere kimlik doğrulayıcı uygulamasını yüklemek için Şirket Portalı içinde talimat alınacaktır.

5. **İleri**'yi seçin.

6. **Atamalar** sayfasında, bu profilin atanmasını istediğiniz kullanıcıları içeren Kullanıcı gruplarını seçin. Profili tüm kullanıcılara veya belirli gruplara atamayı seçebilirsiniz. Seçili gruplardaki tüm kullanıcılar, yukarıda seçilen kayıt türünü kullanır. Özellik, cihazlar yerine Kullanıcı kimliklerini temel aldığı için, Kullanıcı kayıt senaryolarında cihaz grupları desteklenmez. Profili tüm kullanıcılara veya belirli gruplara atamayı seçebilirsiniz.

    ![Atamalar sayfası](./media/ios-user-enrollment/assignments-page.png)

7. **İleri**'yi seçin.

8. **İnceleme ve oluşturma** sayfasında, seçimlerinizi gözden geçirin ve ardından profili kullanıcılara atamak için **Oluştur** ' u seçin.

    ![Atamalar sayfası](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Profil önceliği

Birden fazla kayıt türü profili oluşturduktan sonra, uygulandıkları öncelik sırasını değiştirebilirsiniz.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **cihaz kaydı** > **Apple kaydı** > **kayıt türleri (Önizleme)** öğesini seçin.
2. Listedeki profilleri, uygulanmasını istediğiniz sırada sürükleyip bırakın.

Herhangi bir kullanıcının profilleri arasındaki çakışmalar söz konusu olduğunda, Kullanıcı için daha yüksek öncelikli profil uygulanır.


