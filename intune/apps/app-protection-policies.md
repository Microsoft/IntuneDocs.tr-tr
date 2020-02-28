---
title: Uygulama koruma ilkelerini oluşturma ve dağıtma
titleSuffix: Microsoft Intune
description: Bu konu başlığında Microsoft Intune uygulama koruma ilkelerini oluşturma ve atama adımları anlatılmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 662c60b8eb5295997f3c37a02ea23771cf1abaa9
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781310"
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Uygulama koruma ilkelerini oluşturma ve atama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kuruluşunuzun kullanıcıları için Microsoft Intune uygulama koruma ilkeleri (uygulama) oluşturmayı ve atamayı öğrenin. Bu konu, mevcut ilkelerde nasıl değişiklik yapılacağını da açıklar.

## <a name="before-you-begin"></a>Başlamadan önce

Uygulama koruma ilkeleri, Intune tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir. Uygulama koruma ilkelerinin çalışması ve Intune uygulama koruma ilkeleri tarafından desteklenen senaryolar ile ilgili daha ayrıntılı bir açıklama için bkz. [Microsoft Intune uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

MAM destekli uygulamalar listesi arıyorsanız bkz. [MAM uygulamaları listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

Kuruluşunuzun iş kolu (LOB) uygulamalarını uygulama koruma ilkelerine hazırlamak üzere Microsoft Intune'a ekleme hakkında bilgi için bkz. [Uygulamaları Microsoft Intune'a ekleme](apps-add.md).

## <a name="app-protection-policies-for-iosipados-and-android-apps"></a>İOS/ıpados ve Android uygulamaları için uygulama koruma ilkeleri

İOS/ıpados ve Android uygulamaları için bir uygulama koruma ilkesi oluşturduğunuzda, yeni bir uygulama koruma ilkesine neden olan modern bir Intune işlem akışını takip edersiniz.

### <a name="create-an-iosipados-or-android-app-protection-policy"></a>İOS/ıpados veya Android uygulama koruma ilkesi oluşturma
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. Intune portalında **uygulamalar** > **Uygulama koruma ilkeleri**' ni seçin. Bu seçim, yeni ilkeler oluşturacağınız ve mevcut ilkeleri düzenleyeceğiniz **Uygulama koruma ilkeleri** ayrıntılarını açar.
3. **Ilke oluştur** ' u seçin ve **IOS/ıpados** ya da **Android**' i seçin. **Ilke oluştur** bölmesi görüntülenir.
4. **Temel bilgiler** sayfasında, aşağıdaki değerleri ekleyin:

    | Değer | Açıklama |
    |--------------|------------------------------------------------|
    | Ad | Bu uygulama koruma ilkesinin adı. |
    | Açıklama | Seçim Bu uygulama koruma ilkesinin açıklaması. |


    **Platform** değeri, yukarıdaki seçeneğe göre ayarlanır.

    ![İlke oluştur bölmesinin temel bilgiler sayfasının ekran görüntüsü](~/apps/media/app-protection-policies/app-protection-add-policies-01.png)

5. **İleri** ' ye tıklayarak **uygulamalar** sayfasını görüntüleyin.<br>
    **Uygulamalar** sayfası, bu ilkeyi farklı cihazlardaki uygulamalara nasıl uygulamak istediğinizi seçmenizi sağlar. En az bir uygulama eklemeniz gerekir.<p>
    
    | Değer/seçenek | Açıklama |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Tüm cihaz türlerindeki uygulamalar için hedef | İlkenizi herhangi bir yönetim durumundaki cihazlarda uygulamalara hedeflemek için bu seçeneği kullanın. Belirli cihaz türlerindeki uygulamaları hedeflemek için **Hayır** ' ı seçin. Bilgi için bkz. [cihaz yönetim durumuna bağlı olarak hedef uygulama koruma ilkeleri](#target-app-protection-policies-based-on-device-management-state) |
    |     Cihaz türleri | Bu ilkenin MDM yönetilen cihazlara veya yönetilmeyen cihazlara uygulanıp uygulanmayacağını belirtmek için bu seçeneği kullanın. İOS/ıpados uygulama ilkeleri için **yönetilmeyen** ve **yönetilen** cihazlar arasından seçim yapın. Android uygulama ilkeleri için **yönetilmeyen**, **Android Cihaz Yöneticisi**ve **Android kurumsal**' i seçin.  |
    | Genel uygulamalar | Hedeflenecek uygulamaları seçmek için **ortak uygulamaları seç** ' e tıklayın. |
    | Özel uygulamalar | Bir paket KIMLIĞINE göre hedeflemek üzere özel uygulamalar seçmek için **özel uygulamalar Seç** ' e tıklayın. |
    
    Seçtiğiniz uygulamalar ortak ve özel uygulamalar listesinde görünür. 
6. **İleri** ' ye tıklayarak **veri koruma** sayfasını görüntüleyin.<br>
    Bu sayfa, kesme, kopyalama, yapıştırma ve farklı kaydet kısıtlamaları dahil olmak üzere veri kaybı önleme (DLP) denetimleri için ayarlar sağlar. Bu ayarlar, kullanıcıların bu uygulama koruma ilkesinin uygulandığı uygulamalardaki verilerle nasıl etkileşime gireceğini tespit ediyor.

    **Veri koruma ayarları**:<br>
    - **iOS/ıpados veri koruma** -bilgi için bkz. [IOS/ıpados uygulama koruma Ilkesi ayarları-veri koruma](~/apps/app-protection-policy-settings-ios.md#data-protection).
    - **Android veri koruma** -bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-veri koruma](~/apps/app-protection-policy-settings-android.md#data-protection).

7. **İleri** ' ye tıklayarak **erişim gereksinimleri** sayfasını görüntüleyin.<br>
    Bu sayfa, kullanıcıların bir iş bağlamındaki uygulamalara erişmek için karşılaması gereken PIN ve kimlik bilgisi gereksinimlerini yapılandırmanıza izin veren ayarları sağlar. 
 
    **Erişim gereksinimleri ayarları**:<br>
    - **iOS/ıpados erişim gereksinimleri** -bilgi için bkz. [IOS/ıpados uygulama koruma Ilkesi ayarları-erişim gereksinimleri](~/apps/app-protection-policy-settings-ios.md#access-requirements).
    - **Android erişim gereksinimleri** -daha fazla bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-erişim gereksinimleri](~/apps/app-protection-policy-settings-android.md#access-requirements).

8. **Koşullu başlatma** sayfasını göstermek için **İleri** ' ye tıklayın.<br>
    Bu sayfa, uygulama koruma ilkeniz için oturum açma güvenlik gereksinimlerini ayarlamaya yönelik ayarları sağlar. Bir **Ayar** seçin ve kullanıcıların şirket uygulamanızda oturum açması için karşılaması gereken bir **Değer** girin. Ardından, kullanıcılar gereksinimlerinizi karşılamıyorsa gerçekleştirmek istediğiniz **eylemi** seçin. Bazı durumlarda tek bir ayar için birden çok eylem yapılandırılabilir.

    **Koşullu başlatma ayarları**:<br>
    - **iOS/ıpados koşullu başlatma** -bilgi için bkz. [IOS/ıpados uygulama koruma Ilkesi ayarları-koşullu başlatma](~/apps/app-protection-policy-settings-ios.md#conditional-launch).
    - **Android koşullu başlatma** -bilgi için bkz. [Android uygulama koruma Ilkesi ayarları-koşullu başlatma](~/apps/app-protection-policy-settings-android.md#conditional-launch).

9. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.<br>
   **Atamalar** sayfası, uygulama koruma ilkesini Kullanıcı gruplarına atamanıza olanak tanır.

10. **İleri** ' ye tıklayın ve bu uygulama koruma ilkesi için girdiğiniz değerleri ve ayarları gözden geçirin.

11. İşiniz bittiğinde, Intune 'da uygulama koruma ilkesini oluşturmak için **Oluştur** ' a tıklayın. 

    > [!TIP]
    > Bu ilke ayarları, yalnızca uygulamalar iş bağlamında kullanılırken uygulanır. Son kullanıcı, uygulamayı kişisel bir görev için kullanırken bu ilkelerden etkilenmez. Yeni bir dosya oluşturduğunuzda bunun kişisel bir dosya olarak kabul edildiğini unutmayın. 

Son kullanıcılar uygulamaları App Store veya Google Play’den indirebilir. Daha fazla bilgi için bkz.:
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [İOS/ıpados uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)

## <a name="change-existing-policies"></a>Mevcut ilkeleri değiştirme
Mevcut ilkeyi düzenleyebilir ve bunu hedeflenen kullanıcılara uygulayabilirsiniz. Bununla birlikte, mevcut ilkeleri değiştirdiğinizde uygulamalarda oturum açmış olan kullanıcılar bu değişiklikleri sekiz saat boyunca görmez.

Değişikliklerin etkisini hemen görmek için, son kullanıcının uygulama oturumunu kapatması ve yeniden oturum açması gerekir.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>İlkeyle ilişkili uygulamalar listesini değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde **Özellikler**' i seçin.

3. *Uygulamalar*başlıklı bölümün yanında **Düzenle**' yi seçin.

4. **Uygulamalar** sayfası, bu ilkeyi farklı cihazlardaki uygulamalara nasıl uygulamak istediğinizi seçmenizi sağlar. En az bir uygulama eklemeniz gerekir.<p>
    
    | Değer/seçenek | Açıklama |
    |-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Tüm cihaz türlerindeki uygulamalar için hedef | İlkenizi herhangi bir yönetim durumundaki cihazlarda uygulamalara hedeflemek için bu seçeneği kullanın. Belirli cihaz türlerindeki uygulamaları hedeflemek için **Hayır** ' ı seçin. Bilgi için bkz. [cihaz yönetim durumuna bağlı olarak hedef uygulama koruma ilkeleri](#target-app-protection-policies-based-on-device-management-state) |
    |     Cihaz türleri | Bu ilkenin MDM yönetilen cihazlara veya yönetilmeyen cihazlara uygulanıp uygulanmayacağını belirtmek için bu seçeneği kullanın. İOS/ıpados uygulama ilkeleri için **yönetilmeyen** ve **yönetilen** cihazlar arasından seçim yapın. Android uygulama ilkeleri için **yönetilmeyen**, **Android Cihaz Yöneticisi**ve **Android kurumsal**' i seçin.  |
    | Genel uygulamalar | Hedeflenecek uygulamaları seçmek için **ortak uygulamaları seç** ' e tıklayın. |
    | Özel uygulamalar | Bir paket KIMLIĞINE göre hedeflemek üzere özel uygulamalar seçmek için **özel uygulamalar Seç** ' e tıklayın. |

    Seçtiğiniz uygulamalar ortak ve özel uygulamalar listesinde görünür. 

5. Bu ilke için seçilen uygulamaları gözden geçirmek için **gözden geçir + oluştur** ' a tıklayın.

6. İşiniz bittiğinde, uygulama koruma ilkesini güncelleştirmek için **Kaydet** ' e tıklayın.
 
#### <a name="to-change-the-list-of-user-groups"></a>Kullanıcı grupları listesini değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde **Özellikler**' i seçin.

3. *Atamalar*başlıklı bölümün yanında **Düzenle**' yi seçin.

4. İlkeye yeni bir kullanıcı grubu eklemek için, *Dahil Et* sekmesinde **Dahil edilecek grupları seç**’i ve kullanıcı grubunu seçin. Gruba eklemek için **Seç**'i belirleyin. 

5. Bir kullanıcı grubunu dışlamak için, *Dışla* sekmesinde **Dışlanacak grupları seç**’i ve kullanıcı grubunu seçin. Kullanıcı grubunu kaldırmak için **Seç**’i seçin.  

6. Önceden eklenen grupları silmek için *Ekle* veya *Dışla* sekmesinde üç noktayı (...) ve ardından **Sil**'i seçin.

7. Bu ilke için seçilen kullanıcı gruplarını gözden geçirmek için **gözden geçir + oluştur** ' a tıklayın.

8. Atamalarda yaptığınız değişiklikler hazır duruma geldiğinde **Kaydet**'i seçerek yapılandırmayı kaydedebilir ve ilkeyi yeni kullanıcı grubuna dağıtabilirsiniz. Yapılandırmanızı kaydetmeden önce **iptal** ' i seçerseniz, *dahil etme* ve *hariç tutma* sekmelerinde yaptığınız tüm değişiklikleri atlayacak.

### <a name="to-change-policy-settings"></a>İlke ayarlarını değiştirmek için

1. **Uygulama koruma ilkeleri** bölmesinde değiştirmek istediğiniz ilkeyi seçin.

2. *Intune uygulama koruması* bölmesinde **Özellikler**' i seçin.

3. Değiştirmek istediğiniz ayarlara karşılık gelen bölümün yanında **Düzenle**' yi seçin. Ardından ayarları yeni değerlerle değiştirin.

7. Bu ilkenin güncelleştirilmiş ayarlarını gözden geçirmek için **gözden geçir + oluştur** ' a tıklayın.

4. Değişikliklerinizi kaydetmek için **Kaydet** ' i seçin. Tüm değişiklikleriniz tamamlanana kadar bir ayarlar alanı seçmek ve ardından değişikliklerinizi kaydetmek için işlemi yineleyin. Ardından *Intune Uygulama Koruması - Özellikler* bölmesini kapatabilirsiniz. 

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme
Pek çok kuruluşta son kullanıcıların Intune Mobil Cihaz Yönetimi (MDM) ile yönetilen cihazları (şirkete ait cihazlar gibi) ve yalnızca Intune uygulama koruma ilkeleriyle korunan yönetilmeyen cihazları kullanmalarına izin verilir. Yönetilmeyen cihazlar genellikle Kendi Cihazını Getir (KCG) cihazları olarak bilinir.

Intune uygulama koruma ilkeleri, bir kullanıcının kimliğini hedeflendiği için kullanıcı koruma ayarları hem kaydedilmiş (MDM ile yönetilen) hem de kaydedilmemiş (MDM’siz) cihazlara uygulanabilir. Bu nedenle, Intune 'a kayıtlı veya kayıtlı olmayan iOS/ıpados ve Android cihazlar için bir Intune uygulama koruma ilkesini hedefleyebilirsiniz. Kesin veri kaybı önleme (DLP) denetimlerinin yerinde olduğu yönetilmeyen cihazlar için bir koruma ilkenize ve MDM ile yönetilen cihazlar için DLP denetimlerinin çok daha gevşek olabileceği ayrı bir koruma ilkesine sahip olabilirsiniz. Bunun kişisel Android kurumsal cihazlarda nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri ve iş profilleri](android-deployment-scenarios-app-protection-work-profiles.md).

Bu ilkeleri oluşturmak için Intune konsolundaki **uygulamalar** > **Uygulama koruma ilkeleri** ' ne gidin ve ardından **ilke oluştur**' u seçin. Mevcut bir koruma ilkesini de düzenleyebilirsiniz. Uygulama koruma ilkesinin hem yönetilen hem de yönetilmeyen cihazlara uygulanmasını sağlamak için, **uygulamalar** sayfasına gidin ve **tüm cihaz türlerindeki uygulamalar hedefinin** , varsayılan değer olan **Evet**olarak ayarlandığını onaylayın. Yönetim durumuna göre daha fazla **atama yapmak istiyorsanız**, **hedefi tüm cihaz türlerindeki uygulamalar olarak** ayarlayın. 

### <a name="device-types"></a>Cihaz türleri

- **Yönetilmeyen**: yönetilmeyen cihazlar, Intune MDM yönetiminin algılanmadığı cihazlardır. Bu, üçüncü taraf MDM satıcıları tarafından yönetilen cihazları içerir.
- **Intune tarafından yönetilen cihazlar**: yönetilen cihazlar, Intune MDM tarafından yönetilir.
- **Android Cihaz Yöneticisi**: Android CIHAZ yönetim API 'sini kullanan Intune tarafından yönetilen cihazlar.
- **Android Enterprise**: Android kurumsal iş profilleri veya Android kurumsal tam cihaz yönetimi kullanan Intune tarafından yönetilen cihazlar.

> [!NOTE]
> Android cihazlar, hangi cihaz türünün seçildiğine bakılmaksızın Intune Şirket Portalı uygulamasını yüklemek isteyip istecektir. Örneğin, ' Android Enterprise ' seçeneğini belirlerseniz, yönetilmeyen Android cihazlara sahip olan kullanıcılara yine de sorulur.

İOS/ıpados için, Intune kayıtlı cihazlarındaki uygulamalara Uygulama koruma ilkesi (uygulama) ayarlarını hedeflemek üzere ek uygulama yapılandırma ayarları gereklidir:

- MDM ile yönetilen tüm uygulamalarda **IntuneMAMUPN** yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune Içindeki iOS/ıpados uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).
- **Intunemamdeviceıd** , tüm üçüncü taraf ve Iş kolu MDM ile yönetilen uygulamalar için yapılandırılmalıdır. **IntuneMAMDeviceID**, cihaz kimliği belirtecinde yapılandırılmalıdır. Örneğin, `key=IntuneMAMDeviceID, value={{deviceID}}`. Daha fazla bilgi için bkz. [yönetilen iOS/ıpados cihazları için uygulama yapılandırma Ilkeleri ekleme](app-configuration-policies-use-ios.md).
- Yalnızca **IntuneMAMDeviceID** yapılandırıldığında Intune uygulaması cihazı yönetilmeyen cihaz olarak görür.

> [!NOTE]
> Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hakkında belirli iOS/ıpados destek bilgileri için, bkz. [Yönetim durumuna göre hedeflenen mam koruma ilkeleri](../fundamentals/whats-new-archive.md#mam-protection-policies-targeted-based-on-management-state).

## <a name="policy-settings"></a>İlke ayarları
İOS/ıpados ve Android ilke ayarlarının tam listesini görmek için, aşağıdaki bağlantılardan birini seçin:

- [iOS/ıpados ilkeleri](app-protection-policy-settings-ios.md)
- [Android ilkeleri](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Sonraki adımlar
[Uyumluluğu ve kullanıcı durumunu izleme](app-protection-policies-monitor.md)

## <a name="see-also"></a>Ayrıca bkz.
* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
* [İOS/ıpados uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
