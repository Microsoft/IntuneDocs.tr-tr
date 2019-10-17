---
title: Microsoft Intune-Azure 'da cihaz uyumluluk ilkeleri oluşturma | Microsoft Docs
description: Yetkisizkullanımsüresinde durumunu, koşullu erişimle çalışma, atanmış bir ilke olmadan cihazları işleme ve Azure portal ile klasik portalda uyumluluk farklarını kullanarak cihaz uyumluluk ilkeleri oluşturun, durum ve önem düzeylerine genel bakış yapın. Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15ac42f34d440c32026d39aca577bd8e3b1f62ea
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504547"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Microsoft Intune’da uyumluluk ilkesi oluşturma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

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
  - WVPN profillerinidows Phone 8.1

- Cihazları Intune'a kaydetme (uyumluluk durumunu görmek için gereklidir)

- Cihazları bir kullanıcıya kaydedin veya birincil kullanıcı olmadan kaydedin. Cihazların birden çok kullanıcıya kaydedilmesi desteklenmez.

## <a name="create-the-policy"></a>İlkeyi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu**'nu seçin. Aşağıdaki seçenekleriniz vardır:

    - **Genel bakış**: uyumlu ve hesaplanmayan cihazların bir özetini ve sayısını gösterir. Ayrıca ilkeleriniz ve ilkelerinizdeki ayarlar da listelenir. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) sayfasında faydalı bilgiler yer almaktadır.
    - **Yönetin**: cihaz ilkeleri oluşturun, uyumsuz cihazlara [bildirim](quickstart-send-notification.md) gönderin ve [ağ](use-network-locations.md)oluşturma özelliğini etkinleştirin.
    - **İzleme**: cihazlarınızın uyumluluk durumunu ve ayar ve ilke düzeyinde kontrol edin. [Intune cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md) bu konuda faydalı bir kaynaktır. Ayrıca günlükleri görüntüleyebilir ve cihazlarınızın tehdit aracısı durumunu denetleyebilirsiniz.
    - **Kurulum**: [yerleşik uyumluluk Ilkelerini](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)kullanın, [Microsoft Defender GELIŞMIŞ tehdit koruması 'nı (ATP)](advanced-threat-protection.md)etkinleştirin, bir [Mobil tehdit savunma Bağlayıcısı](mobile-threat-defense.md)ekleyin ve [JAMF](conditional-access-integrate-jamf.md)kullanın.

3. **İlkeler** > **İlke Oluştur**’u seçin. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. **Jailbreak uygulanmış iOS cihazlarını uyumlu değil olarak işaretle** iyi bir ilke adı örneğidir.
    - **Açıklama**: ilke için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: cihazlarınızın platformunu seçin. Seçenekleriniz şunlardır:  

       - **Outlook Web Access (OWA)**
       - **Android kurumsal**
       - **Android**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

    - **Ayarlar**: aşağıdaki makaleler her platformun ayarlarını listeler ve anlatmaktadır:

        - [Outlook Web Access (OWA)](compliance-policy-create-android.md)
        - [Android Kurumsal](compliance-policy-create-android-for-work.md)
        - [Android](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 ve üzeri](compliance-policy-create-windows-8-1.md)
        - [Windows 10 ve üzeri](compliance-policy-create-windows.md)

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin. İlke oluşturulur ve listede gösterilir. Şimdi ilkeyi gruplarınıza atayın.

## <a name="assign-the-policy"></a>İlke atama

İlke oluşturulduktan sonra yapmanız gereken bunu gruplarınıza atamaktır:

1. Oluşturduğunuz ilkelerden birini seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi ve ardından **Atamalar**'ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkenin uygulanmasını istediğiniz grupları seçin > ilkeyi dağıtmak için **Kaydet** ' i seçin.

İlkenize göre hedeflenen kullanıcı veya cihazlar, Intune ile iade edildiğinde uyumluluk için değerlendirilir.

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

Satış, İK, Merkez ofis çalışanları gibi belirli gruplara ilke atamanın ve filtrelemenin ideal bir yolu olarak kapsam etiketlerini kullanabilirsiniz. Uyumluluk ilkelerinize ayar ekledikten sonra bir kapsam etiketi de ekleyebilirsiniz. [İlke filtrelemek için kapsam etiketleri kullanma](../fundamentals/scope-tags.md) sayfası bu konuda faydalı bir kaynaktır.

## <a name="refresh-cycle-times"></a>Yenileme döngü süreleri

Intune, uyumluluk ilkelerine yönelik güncelleştirmeleri denetlemek için farklı yenileme döngüleri kullanır. Cihaz yakın zamanda kaydedildiyse, iade etme daha sık çalışır. [İlke ve profil yenileme döngüleri](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) tahmini yenileme zamanlarını listeler.

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

|Durum  |Önem Derecesi  |
|---------|---------|
|Bilinmiyor     |1|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi varsa, bu ilkelerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri InGracePeriod durumunda (önem derecesi = 4). InGracePeriod durumu en yüksek önem düzeyine sahiptir. Bu nedenle üç ilke de InGracePeriod uyumluluk durumuna sahip olur.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).
