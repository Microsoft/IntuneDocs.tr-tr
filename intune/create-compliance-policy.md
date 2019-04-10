---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Kullanımı cihaz uyumluluk ilkelerini, koşullu erişim, Azure portalında uyumluluk farkları ve atanmış bir ilkesi olmayan cihazları işleme ile çalışma Ingraceperiod durumunu kullanma, durum ve önem derecesi genel bakış kullanmaya başlayın ve Klasik portalda Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: da0aa98774f25bf290391225c6ccae56a3859c22
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59425339"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Microsoft Intune bir uyumluluk ilkesi oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune’un kuruluşunuzun kaynaklarını korumaya yönelik kullanımında cihaz uyumluluk ilkeleri en önemli özelliklerdendir. Intune'da, cihazlarının en az bir işletim sistemi sürümü gibi uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları oluşturabilirsiniz. Cihaz uyumlu değilse [koşullu erişimi](conditional-access.md) kullanarak veri ve kaynaklara erişimi engelleyebilirsiniz.

Ayrıca kullanıcıya bir bildirim e-posta göndererek gibi uyumsuzluk, eylemleri gerçekleştirebilirsiniz. Uyumluluk ilkeleri neler ve bunların nasıl kullanıldığı genel bakış için bkz: [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

Bu makalede:

- Bir uyumluluk ilkesi oluşturmak için adımları ve önkoşulları listeler.
- İlkeyi, kullanıcı ve cihaz gruplarına atamak gösterilmektedir.
- Kapsam etiketleri "ilkeleri ve uyumlu olmayan cihazların atabileceğiniz adımların örneklerini filtrelemek için" gibi ek özellikleri açıklanmaktadır.
- İade yenileme cihazların, ilke güncelleştirmeleri aldığınızda döngü sürelerini listeler.

## <a name="before-you-begin"></a>Başlamadan önce

Cihaz uyumluluk ilkelerini kullanmak için emin olun:

- Aşağıdaki abonelikleri kullanın:

  - Intune
  - Koşullu erişim kullanıyorsanız, Azure Active Directory (AD) Premium sürümü gerekir. [Azure Active Directory fiyatlandırma](https://azure.microsoft.com/pricing/details/active-directory/) farklı sürümleri ile elde edecekleriniz listeler. Intune uyumluluk, Azure AD gerektirmez.

- Desteklenen bir platform kullanın:

  - Android
  - Android Kurumsal
  - iOS
  - macOS (önizleme)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Cihazları ıntune'a (uyumluluk durumunu görmek için gereklidir)

- Bir kullanıcı cihazlarını kaydetme veya birincil kullanıcısı kaydetme. Birden çok kullanıcının kayıtlı cihazlar desteklenmez.

## <a name="create-the-policy"></a>İlke oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz uyumluluğu**'nu seçin. Aşağıdaki seçenekleriniz vardır:

    - **Genel Bakış**: Bir özeti ve değerlendirilmeyen, uyumlu olan cihazların sayısını ve benzeri gösterir. Ayrıca, ilkeleri ve ilkelerinizi tek ayarları listelenir. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) iyi bazı bilgiler sağlar.
    - **Yönetme**: Cihaz ilkeleri oluşturun, gönderin [bildirimleri](quickstart-send-notification.md) uyumlu olmayan cihazlara ve etkinleştirme [ağ çitlemek](use-network-locations.md).
    - **İzleyici**: Cihazlarınızın ve ayarı ve İlkesi düzeyinde uyumluluk durumunu kontrol edin. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) iyi bir kaynaktır. Ayrıca günlükleri görüntülemek ve cihazlarınızı tehdit aracısı durumunu denetleyin.
    - **Kurulum**: Kullanın [yerleşik uyumluluk ilkeleri](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), etkinleştirme [Windows Defender Gelişmiş tehdit Koruması (ATP)](advanced-threat-protection.md), ekleme bir [mobile threat defense Bağlayıcısı](mobile-threat-defense.md)ve [Jamf](conditional-access-integrate-jamf.md).

3. **İlkeler** > **İlke Oluştur**’u seçin. Aşağıdaki özellikleri girin:

    - **Ad**: İlke için açıklayıcı bir ad girin. İlkelerinizi, kolayca daha sonra tanımlayabilmeniz adlandırın. Örneğin, iyi ilke adı olan **iOS jailbreak uygulanmış cihazlar uyumsuz olarak işaretle**.
    - **Açıklama**: İlke için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

    - **Ayarları**: Aşağıdaki makaleleri, listeler ve her platform için ayarları açıklar:

        - [Android](compliance-policy-create-android.md)
        - [Android Kurumsal](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 ve üzeri](compliance-policy-create-windows-8-1.md)
        - [Windows 10 ve üzeri](compliance-policy-create-windows.md)

4. İşiniz bittiğinde seçin **Tamam** > **Oluştur** yaptığınız değişiklikleri kaydedin. İlke oluşturulur ve listede gösterilen. Ardından, ilkeyi gruplarınıza atayın.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

İlke oluşturulduktan sonra sonraki adım, gruplarınıza ilkeyi atamak için içerir:

1. Oluşturduğunuz bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi seçin > **atamaları**. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkenin uygulanmasını istediğiniz kullanıcı gruplarını seçin > Seç **Kaydet** ilkeyi kullanıcılara dağıtmak için.

İlkeyi kullanıcılara geçerli. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için değerlendirilir.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirin

İlkeyi atadığınızda, ayrıca **değerlendir** kaç kullanıcının etkilendiğini. Bu özellik, kullanıcıları hesaplar; Bu cihazları hesaplamaz.

1. Intune'da seçin **cihaz uyumluluğu** > **ilkeleri**.
2. Bir ilke seçin > **atamaları** > **değerlendir**. Bir ileti, bu ilke tarafından kaç kullanıcının hedeflendiğini gösterir.

Varsa **değerlendir** düğmesi gri, ilkeyi bir veya daha fazla gruba atanmış olduğundan emin olun.

## <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler

Uyumluluk ilkelerini sağlamayan cihazlarda bir dizi otomatik olarak uygulanacak eylem ekleyebilirsiniz. Cihazın uyumsuz olarak işaretlenme zamanlamasını değiştirebilirsiniz (örneğin, bir gün sonra olarak). Ayrıca, cihaz uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

[Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) makalesinde, kullanıcılarınıza e-posta ile gönderilecek bir bildirim oluşturma da dahil olmak üzere daha fazla bilgi sağlanmıştır.

Örneğin Konumlar özelliğini kullanıyor ve uyumluluk ilkesinde bir konum ekliyorsunuz. En az bir konum seçtiğinizde uyumsuzluk için varsayılan eylem uygulanır. Cihaz, seçili konumlara bağlı değilse hemen uyumsuz olarak değerlendirilir. Kullanıcılarınıza bir gün gibi bir yetkisiz kullanım süresi tanıyabilirsiniz.

## <a name="scope-tags"></a>Kapsam etiketleri

Kapsam etiketleri atamak ve ilkeleri satışları, ik, tüm ABD NC çalışanlar, belirli gruplara filtre ve benzeri için harika bir yoludur. Ayarları ekledikten sonra bir kapsam etiketi uyumluluk ilkelerinize ekleyebilirsiniz. [Kapsam etiketleri filtresi ilkeleri](scope-tags.md) iyi bir kaynaktır.

## <a name="refresh-cycle-times"></a>Döngü sürelerini Yenile

Uyumluluk denetimi, Intune yapılandırma profili aynı yenileme döngüsü kullanır. Genel olarak, zamanları şunlardır:

| Platform | Yenileme döngüsü|
| --- | --- |
| iOS | 6 saatte bir |
| Mac OS | 6 saatte bir |
| Android | 8 saatte bir |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir |
| Windows Phone | 8 saatte bir |
| Windows 8.1 | 8 saatte bir |

Son olarak cihazın kayıtlı, uyumluluk iade daha sık çalışır:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows 8.1 | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 

İstediğiniz zaman, kullanıcılar Şirket portalı uygulamasını açın ve hemen bir ilkeyi denetlemek için cihazı eşitleyebilir.

### <a name="assign-an-ingraceperiod-status"></a>InGracePeriod durumu atama

InGracePeriod durumu, uyumluluk ilkesi için bir değerdir. Bu değer, cihazın yetkisiz kullanım süresi ile bu uyumluluk ilkesi için asıl cihaz durumunun bir bileşimi ile belirlenir.

Yani bir cihazın atanmış bir uyumluluk ilkesi için Uyumsuz durumu varsa ve:

- kendisine atanmış bir yetkisiz kullanım süresi yoksa, uyumluluk ilkesi için atanan değer NonCompliant olur
- kendisine atanmış yetkisiz kullanım süresi dolmuşsa, uyumluluk ilkesi için atanan değer NonCompliant olur
- kendisine atanmış yetkisiz kullanım süresi henüz dolmamışsa, uyumluluk ilkesi için atanan değer InGracePeriod olur

Aşağıdaki tabloda bu noktalar özetlenmektedir:

|Asıl uyumluluk durumu|Atanmış yetkisiz kullanım süresi değeri|Geçerli uyumluluk durumu|
|---------|---------|---------|
|Uyumsuz |Bir yetkisiz kullanım süresi atanmamış |Uyumsuz |
|Uyumsuz |Önceki günün tarihi|Uyumsuz|
|Uyumsuz |Sonraki günün tarihi|YetkisizKullanımSüresinde|

Cihaz uyumluluk ilkelerini izleme hakkında daha fazla bilgi için bkz. [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Tek bir uyumluluk ilkesi durumu atama

Bir cihazda birden fazla uyumluluk ilkesi varsa ve cihazın bu atanmış uyumluluk ilkelerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, cihaza tek bir uyumluluk durumu atanır. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir:

|Durum  |Severity  |
|---------|---------|
|Bilinmiyor     |1|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi varsa, bu ilkelerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin, bir cihaz kendisine atanan üç uyumluluk ilkeleri vardır: biri bilinmiyor durumunda (önem derecesi = 1), biri uyumlu durumunda (önem derecesi = 3) ve biri Yetkisizkullanımsüresinde durumunda (önem derecesi = 4). Ingraceperiod durumu en yüksek önem derecesine sahip. Bu nedenle, tüm üç ilke Ingraceperiod uyumluluk durumu gerekir.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).