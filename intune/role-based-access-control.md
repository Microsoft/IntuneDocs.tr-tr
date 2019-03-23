---
title: Microsoft Intune ile RBAC
description: Microsoft Intune’da kimin eylem gerçekleştirebileceğini ve değişiklikler yapabileceğini denetlemeniz için Rol Tabanlı Erişim Denetimi’nin (RBAC) nasıl çalıştığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ecc315bfcccc5d3b71107e80720d39e675d42d19
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394660"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)

RBAC, kuruluşunuzda çeşitli Intune görevlerini kimin gerçekleştirebileceğini ve bu görevlerin kime uygulanacağını denetlemenize yardımcı olur. Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz. Bir rol, şunlarla tanımlanır:

- **Rol tanımı**: Bir rol, yönettiği kaynaklar ve her bir kaynak için verilen izinler adı.
- **Üyeleri**: İzinlerin verildiği kullanıcı grupları.
- **Kapsam (gruplar)**: Üyelerin yönetebileceği kullanıcı veya cihaz grupları.
- **[Kapsam (etiketler)](https://docs.microsoft.com/intune/scope-tags)**: Rol ataması burada geçerli etiketler.
- **Atama**: Tanım, üyeler ve kapsam yapılandırıldığında, rol atanır.

![Intune RBAC örneği](./media/intune-rbac-1.PNG)

## <a name="azure-active-directory-roles-with-intune-access"></a>Intune erişimi olan Azure Active Directory rolleri

| Azure Active Directory rol | Tüm Intune verileri | Intune denetim verileri |
| --- | :---: | :---: |
| Genel Yönetici | Okuma/yazma | Okuma/yazma |
| Intune hizmeti Aministrator | Okuma/yazma | Okuma/yazma |
| Koşullu Erişim Yöneticisi | Yok. | Yok. |
| Güvenlik Yöneticisi | Salt okunur | Salt okunur |
| Güvenlik işleci | Salt okunur | Salt okunur |
| Güvenlik okuyucusu | Salt okunur | Salt okunur |
| Genel okuyucusu | Salt okunur | Salt okunur |
| Uyumluluk Yöneticisi | Yok. | Salt okunur |
| Uyumluluk veri Yöneticisi | Yok. | Salt okunur |

**Azure Active Directory (Azure AD)** Intune ile kullanılabilecek iki dizin rolü sağlar. Bu rollere Intune'da tüm etkinlikleri gerçekleştirmek için tam izin verilir:

- **Genel yönetici:** Bu role sahip olan kullanıcılar Azure AD'deki tüm yönetim özelliklerine erişimi, hem de çevrimiçi Exchange Online, SharePoint Online ve Skype gibi Azure AD Federasyonu kullanan Hizmetleri. Azure AD kiracısı olarak kaydolan kişi genel yönetici olur. Yalnızca genel yöneticiler diğer Azure AD yönetici rollerini atayabilir. Kuruluşunuzda birden fazla genel yönetici olabilir. Genel yöneticiler, tüm kullanıcıların ve diğer tüm yöneticilerin parolalarını sıfırlayabilir.

- **Intune Hizmet Yöneticisi:** Bu role sahip kullanıcılar, hizmet mevcut olduğunda Intune'da genel izinleri sahip. Buna ek olarak, yerini alan tüm Azure kısıtlamalarının dışında, bu rol kullanıcıları ve cihazları yönetme, Intune gruplarını oluşturma ve yönetme olanağı sağlar.

- **Koşullu Erişim Yöneticisi:** Bu role sahip kullanıcılar, yalnızca görüntülemek, oluşturmak, değiştirmek ve koşullu erişim ilkeleri silmek için izinlere sahip.

    > [!IMPORTANT]
    > Intune Hizmet Yöneticisi rolü Azure AD'nin koşullu erişim ayarlarını yönetme olanağı sağlamaz.
    >
    > Bir Intune rolü atanmış için kullanıcının bir Intune lisansı olması gerekir.

    > [!TIP]
    > Intune ayrıca üç Azure AD uzantısı gösterir: **Kullanıcılar**, **grupları**, ve **koşullu erişim**, olmak üzere Azure AD RBAC ile denetlenen. Bunlara ek olarak, **Kullanıcı Hesabı Yöneticisi** yalnızca AAD kullanıcısı/grubu etkinliklerini gerçekleştirir ve Intune'daki tüm etkinlikleri gerçekleştirme izinlerinin tümüne sahip değildir. Daha fazla bilgi için [Azure AD ile RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).

## <a name="roles-created-in-the-intune-classic-portal"></a>Klasik Intune portalında oluşturulan roller

Yalnızca “Tam” izinlere sahip Intune **Hizmet Yöneticileri** kullanıcıları, klasik Intune portalından Azure portalında Intune’a geçirilir. Intune atamalıdır **hizmet yöneticileri** "Salt okunur" veya "Yardım Masası" olan kullanıcılar Azure portalında Intune rollerine erişme ve bunları Klasik portaldan kaldırmanız.

> [!IMPORTANT]
> Yöneticilerinizin bilgisayarları Intune kullanarak yönetmek için erişim yine de gerekliyse Klasik portalda Intune Hizmet Yöneticisi erişimini tutmanız gerekebilir.

## <a name="built-in-roles"></a>Yerleşik roller

Daha fazla yapılandırma olmadan grupları için yerleşik roller atayabilirsiniz. Silemez veya yerleşik bir rol düzenleyin.

- **Yardım Masası operatörü**: Kullanıcılar ve cihazlar üzerinde uzak görevler gerçekleştirir ve kullanıcılara veya cihazlara uygulama veya ilke atayabilirsiniz.
- **İlke ve Profil Yöneticisi**: Uyumluluk İlkesi, yapılandırma profillerini, Apple kayıt, Kurumsal cihaz tanımlayıcıları ve güvenlik temellerini yönetir.
- **Salt okunur operatör**: Görünümleri kullanıcı, cihaz, kayıt, yapılandırma ve uygulama bilgileri. Intune'da değişiklik yapamaz.
- **Uygulama Yöneticisi**: Mobil ve yönetilen uygulamaları yönetir, cihaz bilgilerini okuyabilir ve cihaz yapılandırma profillerini görüntüleyebilirsiniz.
- **Intune Rol Yöneticisi**: Özel Intune rolleri yönetir ve yerleşik Intune rol atamalarını ekler. Bu, yöneticilere izin atamanıza yalnızca Intune rolüdür.
- **Okul Yöneticisi**: Windows 10 cihazları yönetir [eğitim için Intune](introduction-intune-education.md)ve aşağıdaki eylemleri gerçekleştirebilirsiniz: 

    |İzin|İşlem|
    |---|---|
    |Veri Denetleme|Okuma|
    |DeviceConfigurations|Atama, Oluşturma, Silme, Okuma, Güncelleştirme|
    |Cihaz Kayıt Yöneticileri|Okuma, Güncelleştirme|
    |Yönetilen Cihazlar|Okuma, Güncelleştirme<!--, Delete [To be added in 1803]-->|
    |Mobil uygulamalar|Atama, Oluşturma, Silme, Okuma, Güncelleştirme|
    |Raporlar|Okuma|
    |Uzak Eylemler|Bilgisayar Temizleme, Yeniden Başlatma, Uzak Kilit, Devre Dışı Bırakma, Cihaz Eşitleme, Silme|
    |Kuruluş|Okuma|

### <a name="to-assign-a-built-in-role"></a>Yerleşik bir rol atamak için

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. Üzerinde **Intune** dikey penceresinde, seçin **rolleri** > **tüm rolleri**.
4. Üzerinde **Intune rolleri - tüm roller** dikey penceresinde, atamak istediğiniz yerleşik rolü seçin.

5. Üzerinde <*rol adı*>- **genel bakış** dikey penceresinde, seçin **Yönet** > **atamaları**.

6. Özel rol dikey penceresinde, **Ata**'yı seçin.

7. Üzerinde **rol atamaları** dikey penceresinde girin bir **atama adı** ve isteğe bağlı **atama açıklaması** atama.

8. İçin **üyeler (gruplar)**, izinleri vermek istediğiniz kullanıcıyı içeren grubu seçin.

9. İçin **kapsam (gruplar)**, yukarıda seçilen üyenin yönetmek için izin verilecek kullanıcıları içeren bir grubu seçin.

10. İçin **kapsam (etiketler)**, bu rol ataması burada uygulanacak etiketleri seçin.

11. İşiniz bittiğinde **Tamam**’ı seçin. Yeni atama, atamalar listesinde görüntülenir.

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

3. Seçin **Intune** > **rolleri** > **tüm rolleri** > **Ekle**.

4. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin. Hangi izinleri uygulamak istediğinize karar vermenize yardımcı olması için [Intune RBAC tablosunu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) kullanın.

6. Üzerinde **kapsam (etiketler)** dikey penceresinde, bu özel rolü burada uygulanacak etiketleri seçin.

7. İşiniz bittiğinde **Tamam**’ı seçin.

7. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. Yeni rol listesinde görüntülenen **Intune rolleri - tüm roller** dikey penceresi.

### <a name="to-assign-a-custom-role"></a>Özel bir rol atamak için

Aynı adımları izleyerek [yerleşik bir rol atamak için](https://docs.microsoft.com/intune/role-based-access-control#to-assign-a-built-in-role) ve özel rolü seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Sorun giderme portalında Intune Yardım Masası Operatörü rolünü kullanma](help-desk-operators.md)



## <a name="see-also"></a>Ayrıca bkz.

- [Azure AD kullanarak roller atama](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
- Hakkında bilgi edinin [ıntune rol tabanlı erişim için Microsoft Graph API desteği](https://docs.microsoft.com/graph/api/resources/intune-rbac-roledefinition?view=graph-rest-1.0)
- Alma [Intune Graph API'si için PowerShell SDK'sı](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10)