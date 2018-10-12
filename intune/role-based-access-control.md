---
title: Microsoft Intune ile RBAC
description: Microsoft Intune’da kimin eylem gerçekleştirebileceğini ve değişiklikler yapabileceğini denetlemeniz için Rol Tabanlı Erişim Denetimi’nin (RBAC) nasıl çalıştığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 5c75bd80e848bbd309051a9c6f3e149abd7a46ed
ms.sourcegitcommit: 378474debffbc85010c54e20151d81b59b7a7828
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028707"
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Microsoft Intune ile rol tabanlı yönetim denetimi (RBAC)

RBAC, kuruluşunuzda çeşitli Intune görevlerini kimin gerçekleştirebileceğini ve bu görevlerin kime uygulanacağını denetlemenize yardımcı olur. Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz. Bir rol, şunlarla tanımlanır:

- **Rol tanımı**: Rolün adı, yönettiği kaynaklar ve her kaynak için verilen izinler.
- **Üyeler**: İzinlerin verildiği kullanıcı grupları.
- **Kapsam**: Üyelerin yönetebileceği kullanıcı veya cihaz grupları.
- **Atama**: Rol; tanım, üyeler ve kapsam yapılandırıldığında atanır.

![Intune RBAC örneği](./media/intune-rbac-1.PNG)

Yeni Azure portalıyla artık **Azure Active Directory (Azure AD)**, Intune ile kullanılabilecek iki Dizin Rolü sağlar. Bu rollere Intune'da tüm etkinlikleri gerçekleştirmek için tam izin verilir:

- **Genel Yönetici:** Bu roldeki kullanıcılar, Azure AD'deki tüm yönetim özelliklerine, ayrıca Azure AD federasyonu kullanan Exchange Online, SharePoint Online ve Skype Kurumsal Çevrimiçi Sürüm gibi tüm hizmetlere erişebilir. Azure AD kiracısı olarak kaydolan kişi genel yönetici olur. Yalnızca genel yöneticiler diğer Azure AD yönetici rollerini atayabilir. Kuruluşunuzda birden fazla genel yönetici olabilir. Genel yöneticiler, tüm kullanıcıların ve diğer tüm yöneticilerin parolalarını sıfırlayabilir.

- **Intune Hizmet Yöneticisi:** Bu roldeki kullanıcıların, hizmet mevcut olduğunda Intune'da genel izinleri vardır. Buna ek olarak, yerini alan tüm Azure kısıtlamalarının dışında, bu rol kullanıcıları ve cihazları yönetme, Intune gruplarını oluşturma ve yönetme olanağı sağlar.

- **Koşullu Erişim Yöneticisi:** Bu roldeki kullanıcıların koşullu erişim ilkelerini yalnızca görüntüleme, oluşturma, değiştirme ve silme izinleri vardır.

    > [!IMPORTANT]
    > Intune Hizmet Yöneticisi rolü Azure AD'nin koşullu erişim ayarlarını yönetme olanağı sağlamaz.
    > Intune rollerinin üyeleri, bir Intune lisansı gerektirir.

    > [!TIP]
    > Intune ayrıca **Kullanıcılar**, **Gruplar**, ve **Koşullu erişim** olmak üzere Azure AD RBAC ile denetlenen üç Azure AD uzantısı gösterir. Bunlara ek olarak, **Kullanıcı Hesabı Yöneticisi** yalnızca AAD kullanıcısı/grubu etkinliklerini gerçekleştirir ve Intune'daki tüm etkinlikleri gerçekleştirme izinlerinin tümüne sahip değildir. Daha fazla ayrıntı için bkz. [Azure AD ile RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-portal"></a>Klasik Intune portalında oluşturulan roller

Yalnızca “Tam” izinlere sahip Intune **Hizmet Yöneticileri** kullanıcıları, klasik Intune portalından Azure portalında Intune’a geçirilir. "Salt Okunur" ve "Yardım Masası" erişimli Intune **Hizmet Yöneticileri** kullanıcılarını Azure portalında Intune rollerine yeniden atamanız ve bunları klasik portaldan kaldırmanız gerekir.

> [!IMPORTANT]
> Yöneticilerinizin bilgisayarları Intune ile yönetmek için hala erişimlerinin olması gerekiyorsa klasik portaldaki Intune Hizmet Yöneticisi erişimini saklamanız gerekebilir.

## <a name="built-in-roles"></a>Yerleşik roller

Aşağıdaki roller Intune'da yerleşiktir ve bunları ek yapılandırma gerekmeden gruplara atayabilirsiniz:

- **Yardım Masası Operatörü**: Kullanıcılar ve cihazlar üzerinde uzak görevler gerçekleştirir, kullanıcılara ve cihazlara uygulama veya ilke atayabilir.
- **İlke ve Profil Yöneticisi**: Uyumluluk ilkesini, yapılandırma profillerini, Apple kaydını ve kurumsal cihaz tanımlayıcılarını yönetir.
- **Salt Okuma Operatörü**: Kullanıcı, cihaz, kayıt, yapılandırma ve uygulama bilgilerini görüntüler. Intune’da değişiklik yapamaz.
- **Uygulama Yöneticisi**: Mobil uygulamalar ve yönetilen uygulamaları yönetir, cihaz bilgilerini okuyabilir ve cihaz yapılandırma profillerini görüntüleyebilir.
- **Intune Rol Yöneticisi**: Özel Intune rollerini yönetir ve yerleşik Intune rolleri için atamalar ekleyebilir. Yöneticilere izin atayabilen tek Intune rolü budur.
- **Okul Yöneticisi**: [Eğitim için Intune](introduction-intune-education.md)’da Windows 10 cihazları yönetir ve aşağıdaki eylemleri gerçekleştirebilir: 

|İzin|İşlem|
|---|---|
|Veri Denetleme|Okuma|
|DeviceConfigurations|Atama, Oluşturma, Silme, Okuma, Güncelleştirme|
|Cihaz Kayıt Yöneticileri|Okuma, Güncelleştirme|
|Yönetilen Cihazlar|Okuma, Güncelleştirme<!--, Delete [To be added in 1803]-->|
|Mobil uygulamalar|Atama, Oluşturma, Silme, Okuma, Güncelleştirme|
|Reports|Okuma|
|Uzak Eylemler|Bilgisayar Temizleme, Yeniden Başlatma, Uzak Kilit, Devre Dışı Bırakma, Cihaz Eşitleme, Silme|
|Kuruluş|Okuma|

### <a name="to-assign-a-built-in-role"></a>Yerleşik bir rol atamak için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Roller** > **Tüm roller**’i seçin.
1. **Intune rolleri - Tüm roller** bölmesinde atamak istediğiniz yerleşik rolü seçin.

2. <*Rol adı*> - **Genel bakış** bölmesinde **Yönet**'i, ardından **Atamalar**'ı seçin.

    > [!NOTE]
    > Yerleşik rolleri silemez ve düzenleyemezsiniz

3. Özel rol bölmesinde **Ata**'yı seçin.

4. **Rol Atamaları** bölmesinde, atama için **Ad** ve isteğe bağlı olarak **Açıklama** girin, sonra da aşağıdakileri seçin:
    - **Üyeler** - İzinleri vermek istediğiniz kullanıcıyı içeren grubu seçin.
    - **Kapsam** - Yukarıda seçilen üyenin yönetmesine izin verilecek kullanıcıları içeren grubu seçin.
<br></br>
5. Bitirdiğinizde, **Tamam**’a tıklayın. Yeni atama, atamalar listesinde görüntülenir.

### <a name="intune-rbac-table"></a>Intune RBAC tablosu

- Her rolün yapabileceklerini daha ayrıntılı olarak görmek için, [Intune RBAC tablosu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a)'nu indirin.

## <a name="custom-roles"></a>Özel roller

Belirli bir işi yapmak için gereken izinleri içeren özel bir rol oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz.

> [!IMPORTANT]
> Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
> - **Genel Yönetici**
> - **Intune Hizmet Yöneticisi**

### <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune** > **Roller** > **Tüm roller** > **Özel rol ekle**’yi seçin.

4. **Özel Rol Ekle** bölmesinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** bölmesinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin. Hangi izinleri uygulamak istediğinize karar vermenize yardımcı olması için [Intune RBAC tablosunu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) kullanın.

6. İşiniz bittiğinde **Tamam**’ı seçin.

7. **Özel Rol Ekle** bölmesinde **Oluştur**’a tıklayın. Yeni rol, **Intune rolleri - Tüm roller** bölmesindeki listede görüntülenir.

### <a name="to-assign-a-custom-role"></a>Özel bir rol atamak için

1. **Intune rolleri - Tüm roller** bölmesinde, atamak istediğiniz özel rolü seçin.

2. <*Rol adı*> - **Genel bakış** bölmesinde **Yönet**'i, ardından **Atamalar**'ı seçin. Ayrıca bu bölmede var olan rolleri düzenleyebilir veya silebilirsiniz.

3. Özel rol bölmesinde **Ata**'yı seçin.

4. **Rol Atamaları** bölmesinde, atama için **Ad** ve isteğe bağlı olarak **Açıklama** girin, sonra da aşağıdakileri seçin:
    - **Üyeler** - İzinleri vermek istediğiniz kullanıcıyı içeren grubu seçin.
    - **Kapsam** - Yukarıda seçilen üyenin yönetmesine izin verilecek kullanıcıları içeren grubu seçin.
<br></br>
5. Bitirdiğinizde, **Tamam**’a tıklayın. Yeni atama, atamalar listesinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

[Sorun giderme portalında Intune Yardım Masası Operatörü rolünü kullanma](help-desk-operators.md)

## <a name="see-also"></a>Ayrıca bkz:

[Azure AD kullanarak roller atama](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
