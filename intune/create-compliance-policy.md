---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Cihaz uyumluluk ilkelerini kullanma, durum ve önem düzeylerine genel bakış, Yetkisizkullanımsüresinde durumunu kullanma, koşullu erişim ile çalışma, cihazları atanmış bir ilke olmadan işleme ve Azure portal ve uyumluluk farklılıkları ile çalışmaya başlama Microsoft Intune 'de klasik Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7519b07b3ac2d40734c32b79466c6d7f4f5d4e8
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "71303953"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Microsoft Intune’da uyumluluk ilkesi oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune’un kuruluşunuzun kaynaklarını korumaya yönelik kullanımında cihaz uyumluluk ilkeleri en önemli özelliklerdendir. Intune’da cihazların uyumlu olarak değerlendirilmesi için uyması gereken minimum işletim sistemi sürümü gibi kurallar ve ayarlar oluşturabilirsiniz. Cihaz uyumlu değilse, [koşullu erişim](conditional-access.md)kullanarak verilere ve kaynaklara erişimi engelleyebilirsiniz.

Ayrıca uyumsuzluğa yönelik olarak kullanıcıya bildirim gönderme gibi önlemler alabilirsiniz. Uyumluluk ilkelerinin işlevleri ve kullanım şekilleri hakkında genel bilgilere için bkz. [Cihaz uyumluluğuna başlama](device-compliance-get-started.md).

Bu makalede:

- Uyumluluk ilkesi oluşturmak için gerekli önkoşullar ve adımlar listelenmiştir.
- İlkeyi kullanıcı ve cihaz gruplarınıza atama adımları gösterilmiştir.
- İlkelerinizi "filtrelemek" için kullanabileceğiniz kapsam etiketleri gibi ek adımlar ve uyumlu olmayan cihazlarda gerçekleştirebileceğiniz işlemler anlatılmıştır.
- Cihazların ilke güncelleştirmelerini aldığı iade yenileme döngüsü süreleri listelenmiştir.

## <a name="before-you-begin"></a>Başlamadan önce

Cihaz uyumluluk ilkelerini kullanmak için aşağıdakilerden emin olun:

- Aşağıdaki abonelikleri kullanın:

  - Intune
  - Koşullu erişim kullanıyorsanız, Azure Active Directory (AD) Premium sürümü gerekir. [Azure Active Directory fiyatlandırması](https://azure.microsoft.com/pricing/details/active-directory/) sayfasında farklı sürümlerde sunulan özelliklere yer verilmiştir. Intune uyumluluğu için Azure AD gerekli değildir.

- Desteklenen bir platform kullanın:

  - Android
  - Android Kurumsal
  - iOS
  - macOS (önizleme)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Cihazları Intune'a kaydetme (uyumluluk durumunu görmek için gereklidir)

- Cihazları bir kullanıcıya kaydedin veya birincil kullanıcı olmadan kaydedin. Cihazların birden çok kullanıcıya kaydedilmesi desteklenmez.

## <a name="create-the-policy"></a>İlkeyi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu**'nu seçin. Aşağıdaki seçenekleriniz vardır:

    - **Genel Bakış**: Özet bilgilerin yanı sıra uyumlu olan, değerlendirilmeyen ve diğer cihazların sayısı gibi bilgiler gösterilir. Ayrıca ilkeleriniz ve ilkelerinizdeki ayarlar da listelenir. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) sayfasında faydalı bilgiler yer almaktadır.
    - **Yönetim**: Cihaz ilkeleri oluşturabilir, uyumlu olmayan cihazlara [bildirim](quickstart-send-notification.md) gönderebilir ve [ağ yalıtımı](use-network-locations.md) uygulayabilirsiniz.
    - **İzle**: Cihazlarınızın uyumluluk durumunun yanı sıra ayar ve ilke düzeyini denetleyebilirsiniz. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) bu konuda faydalı bir kaynaktır. Ayrıca günlükleri görüntüleyebilir ve cihazlarınızın tehdit aracısı durumunu denetleyebilirsiniz.
    - **Kurulum**: [Yerleşik uyumluluk ilkelerini](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)kullanın, [Microsoft Defender Gelişmiş tehdit KORUMASı 'nı (ATP)](advanced-threat-protection.md)etkinleştirin, bir [Mobil tehdit savunma Bağlayıcısı](mobile-threat-defense.md)ekleyin ve [JAMF](conditional-access-integrate-jamf.md)kullanın.

3. **İlkeler** > **İlke Oluştur**’u seçin. Aşağıdaki özellikleri girin:

    - **Ad**: İlke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. **Jailbreak uygulanmış iOS cihazlarını uyumlu değil olarak işaretle** iyi bir ilke adı örneğidir.
    - **Açıklama**: İlke için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

    - **Ayarları**: Aşağıdaki makalelerde her bir platformla ilgili ayarlar listelenmekte ve açıklanmaktadır:

        - [Android](compliance-policy-create-android.md)
        - [Android Kurumsal](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 ve üzeri](compliance-policy-create-windows-8-1.md)
        - [Windows 10 ve üzeri](compliance-policy-create-windows.md)

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin. İlke oluşturulur ve listede gösterilir. Şimdi ilkeyi gruplarınıza atayın.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

İlke oluşturulduktan sonra yapmanız gereken bunu gruplarınıza atamaktır:

1. Oluşturduğunuz ilkelerden birini seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi ve ardından **Atamalar**'ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için değerlendirilir.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirme

İlkeyi atadıktan sonra etkilenen kullanıcı sayısını da **değerlendirebilirsiniz**. Bu özellik, cihaz değil kullanıcı sayısını hesaplar.

1. Intune’da **Cihaz uyumluluğu** > **İlkeler**'i seçin.
2. Bir ilke seçip **Atamalar** > **Değerlendir** yolunu izleyin. Bu ilkenin kaç kullanıcıyı hedeflediğini gösteren bir ileti görüntülenir.

**Değerlendir** düğmesi gri gösteriliyorsa, ilkenin bir veya birden fazla gruba atandığından emin olun.

## <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler

Uyumluluk ilkelerinizi karşılamayan cihazlara otomatik olarak ve sırayla uygulanacak eylemler belirleyebilirsiniz. Cihazın uyumsuz olarak işaretlenme zamanlamasını değiştirebilirsiniz (örneğin, bir gün sonra olarak). Ayrıca, cihaz uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

[Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) makalesinde, kullanıcılarınıza e-posta ile gönderilecek bir bildirim oluşturma da dahil olmak üzere daha fazla bilgi sağlanmıştır.

Örneğin Konumlar özelliğini kullanıyor ve uyumluluk ilkesinde bir konum ekliyorsunuz. En az bir konum seçtiğinizde uyumsuzluk için varsayılan eylem uygulanır. Cihaz, seçili konumlara bağlı değilse hemen uyumsuz olarak değerlendirilir. Kullanıcılarınıza bir gün gibi bir yetkisiz kullanım süresi tanıyabilirsiniz.

## <a name="scope-tags"></a>Kapsam etiketleri

Satış, İK, Merkez ofis çalışanları gibi belirli gruplara ilke atamanın ve filtrelemenin ideal bir yolu olarak kapsam etiketlerini kullanabilirsiniz. Uyumluluk ilkelerinize ayar ekledikten sonra bir kapsam etiketi de ekleyebilirsiniz. [İlke filtrelemek için kapsam etiketleri kullanma](scope-tags.md) sayfası bu konuda faydalı bir kaynaktır.

## <a name="refresh-cycle-times"></a>Yenileme döngüsü süreleri

Intune, uyumluluk ilkelerine yönelik güncelleştirmeleri denetlemek için farklı yenileme döngüleri kullanır. Cihaz yakın zamanda kaydedildiyse, iade etme daha sık çalışır. [İlke ve profil yenileme döngüleri](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) tahmini yenileme zamanlarını listeler.

Herhangi bir zamanda, kullanıcılar Şirket Portalı uygulamayı açabilir ve cihaz güncelleştirmelerini anında denetlemek için cihazı eşitleyebilir.

### <a name="assign-an-ingraceperiod-status"></a>InGracePeriod durumu atama

InGracePeriod durumu, uyumluluk ilkesi için bir değerdir. Bu değer, cihazın yetkisiz kullanım süresi ile bu uyumluluk ilkesi için asıl cihaz durumunun bir bileşimi ile belirlenir.

Yani bir cihazın atanmış bir uyumluluk ilkesi için Uyumsuz durumu varsa ve:

- Cihaza atanmış bir yetkisiz kullanım süresi yoksa, uyumluluk ilkesi için atanan değer uyumsuz
- Cihazda süresi geçen bir yetkisiz kullanım süresi varsa, uyumluluk ilkesi için atanan değer uyumsuz olur
- Cihazda daha sonra bir yetkisiz kullanım süresi varsa, uyumluluk ilkesi için atanan değer Yetkisizkullanımsüresinde olur

Aşağıdaki tabloda bu noktalar özetlenmektedir:

|Asıl uyumluluk durumu|Atanmış yetkisiz kullanım süresi değeri|Geçerli uyumluluk durumu|
|---------|---------|---------|
|Uyumsuz |Bir yetkisiz kullanım süresi atanmamış |Uyumsuz |
|Uyumsuz |Önceki günün tarihi|Uyumsuz|
|Uyumsuz |Sonraki günün tarihi|YetkisizKullanımSüresinde|

Cihaz uyumluluk ilkelerini izleme hakkında daha fazla bilgi için bkz. [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Tek bir uyumluluk ilkesi durumu atama

Bir cihazda birden fazla uyumluluk ilkesi varsa ve cihazın bu atanmış uyumluluk ilkelerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, cihaza tek bir uyumluluk durumu atanır. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir:

|Durum  |severity  |
|---------|---------|
|Bilinmiyor     |1\.|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi varsa, bu ilkelerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri InGracePeriod durumunda (önem derecesi = 4). InGracePeriod durumu en yüksek önem düzeyine sahiptir. Bu nedenle üç ilke de InGracePeriod uyumluluk durumuna sahip olur.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).