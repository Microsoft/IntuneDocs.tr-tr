---
title: Microsoft Intune-Azure 'da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Cihaz uyumluluk ilkelerini kullanma, durum ve önem düzeylerine genel bakış, Yetkisizkullanımsüresinde durumunu kullanma, koşullu erişim ile çalışma, cihazları atanmış bir ilke olmadan işleme ve Azure portal ve uyumluluk farklılıkları ile çalışmaya başlama Microsoft Intune 'de klasik Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ffd1e120a364be1ecaa98e01ff71ac723672b546
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237188"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Microsoft Intune bir uyumluluk ilkesi oluşturma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Cihaz uyumluluk ilkeleri, kuruluşunuzun kaynaklarını korumak için Intune kullanırken temel bir özelliktir. Intune 'da, cihazların en düşük işletim sistemi sürümü gibi uyumlu kabul edilmesi için uyması gereken kurallar ve ayarlar oluşturabilirsiniz. Cihaz uyumlu değilse, [koşullu erişim](conditional-access.md)kullanarak verilere ve kaynaklara erişimi engelleyebilirsiniz.

Ayrıca, kullanıcıya bir bildirim e-postası gönderilmesi gibi uyumsuzluk için eylemler gerçekleştirebilirsiniz. Uyumluluk ilkelerine ne yaptığını ve bunların nasıl kullanıldığını bir genel bakış için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Bu makale:

- Karmaşık pozisyon ilkesi oluşturmak için önkoşulları ve adımları listeler.
- İlkeyi Kullanıcı ve cihaz gruplarınıza nasıl atayacağınızı gösterir.
- İlkelerine "filtre uygulama" ve uyumlu olmayan cihazlarda uygulayabileceğiniz adımlar dahil olmak üzere ek özellikleri açıklar.
- Cihazların ilke güncelleştirmelerini aldığı sırada iade yenileme döngüsünü listeler.

## <a name="before-you-begin"></a>Başlamadan önce

Cihaz uyumluluk ilkelerini kullanmak için şunları yaptığınızdan emin olun:

- Aşağıdaki abonelikleri kullanın:

  - Intune
  - Koşullu erişim kullanıyorsanız, Azure Active Directory (AD) Premium sürümü gerekir. [Azure Active Directory fiyatlandırması](https://azure.microsoft.com/pricing/details/active-directory/) , farklı sürümlerle ne olduğunu listeler. Intune uyumluluğu Azure AD gerektirmez.

- Desteklenen bir platform kullanın:

  - Android
  - Android kurumsal
  - iOS
  - macOS (Önizleme)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Cihazları Intune 'A kaydetme (uyumluluk durumunu görmek için gereklidir)

- Cihazları bir kullanıcıya kaydetme veya birincil kullanıcı olmadan kaydetme. Birden çok kullanıcıya kayıtlı cihazlar desteklenmez.

## <a name="create-the-policy"></a>İlkeyi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluğu**' nu seçin. Şu seçenekleriniz vardır:

    - **Genel bakış**: uyumlu ve hesaplanmayan cihazların bir özetini ve sayısını gösterir. Ayrıca ilkelerinizin ilkelerini ve ayrı ayarlarını listeler. [Intune cihaz uyumluluk Ilkelerini izleme](compliance-policy-monitor.md) , bazı iyi bilgiler sağlar.
    - **Yönetin**: cihaz ilkeleri oluşturun, uyumsuz cihazlara [bildirim](quickstart-send-notification.md) gönderin ve [ağ](use-network-locations.md)oluşturma özelliğini etkinleştirin.
    - **İzleme**: cihazlarınızın uyumluluk durumunu ve ayar ve ilke düzeyinde kontrol edin. [Intune cihaz uyumluluk Ilkelerini izleme](compliance-policy-monitor.md) iyi bir kaynaktır. Ayrıca, günlükleri görüntüleyin ve cihazlarınızın tehdit Aracısı durumunu denetleyin.
    - **Kurulum**: [yerleşik uyumluluk Ilkelerini](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)kullanın, [Microsoft Defender GELIŞMIŞ tehdit koruması 'nı (ATP)](advanced-threat-protection.md)etkinleştirin, bir [Mobil tehdit savunma Bağlayıcısı](mobile-threat-defense.md)ekleyin ve [JAMF](conditional-access-integrate-jamf.md)kullanın.

3. @No__t **ilkeleri**seçin-1**ilke oluştur**. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. Daha sonra kolayca tanımlayabilmeniz için ilkelerinizi adlandırın. Örneğin, iyi bir ilke adı **iOS jailbreak uygulanmış cihazlarını uyumlu değil olarak işaretler**.
    - **Açıklama**: ilke için bir açıklama girin. Bu ayar isteğe bağlıdır, ancak önerilir.
    - **Platform**: cihazlarınızın platformunu seçin. Seçenekleriniz:  

       - **Outlook Web Access (OWA)**
       - **Android kurumsal**
       - **Android**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

    - **Ayarlar**: aşağıdaki makaleler her platformun ayarlarını listeler ve anlatmaktadır:

        - [Outlook Web Access (OWA)](compliance-policy-create-android.md)
        - [Android kurumsal](compliance-policy-create-android-for-work.md)
        - [Android](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8,1, Windows 8.1 ve üzeri](compliance-policy-create-windows-8-1.md)
        - [Windows 10 ve üzeri](compliance-policy-create-windows.md)

4. İşiniz bittiğinde, değişikliklerinizi kaydetmek için **tamam** > **Oluştur** ' u seçin. İlke oluşturulur ve listede gösterilir. Ardından, ilkeyi gruplarınızı atayın.

## <a name="assign-the-policy"></a>İlkeyi ata

Bir ilke oluşturulduktan sonra, bir sonraki adım ilkeyi gruplarınızı atamak için kullanılır:

1. Oluşturduğunuz bir ilkeyi seçin. Mevcut ilkeler **cihaz uyumluluk** > **ilkelerdir**.
2. **Atamaları**> ilke ' yi seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya dışlayabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar** ' ı seçin. Bu ilkenin uygulanmasını istediğiniz grupları seçin > ilkeyi dağıtmak için **Kaydet** ' i seçin.

İlkenize göre hedeflenen kullanıcı veya cihazlar, Intune ile iade edildiğinde uyumluluk için değerlendirilir.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflenmekte olduğunu değerlendirin

İlkeyi atadığınızda, kaç kullanıcının etkilendiğini de **değerlendirebilirsiniz** . Bu özellik kullanıcıları hesaplar; cihazları hesaplamaz.

1. Intune 'da **cihaz uyumluluk** > **ilkeleri**' ni seçin.
2. Bir ilke > **atamaları** > **değerlendir**' i seçin. Bu ilke tarafından kaç kullanıcının hedeflendiğinden bir ileti gösterilir.

**Değerlendir** düğmesi gri ise, ilkenin bir veya daha fazla gruba atandığından emin olun.

## <a name="actions-for-noncompliance"></a>Uyumsuzluk için Eylemler

Uyumluluk ilkelerinizi karşılamayan cihazlarda otomatik olarak uygulanacak bir dizi eylem ekleyebilirsiniz. Cihaz uyumsuz olarak işaretlendiğinde (bir gün sonra) zamanlamayı değiştirebilirsiniz. Ayrıca, cihaz uyumlu olmadığında kullanıcıya bir e-posta gönderen ikinci bir eylem da yapılandırabilirsiniz.

[Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) , kullanıcılarınıza bir bildirim e-postası oluşturma da dahil olmak üzere daha fazla bilgi sağlar.

Örneğin, konumlar özelliğini kullanıyorsunuz ve uyumluluk ilkesinde bir konum eklersiniz. En az bir konum seçtiğinizde uyumsuzluk için varsayılan eylem geçerlidir. Cihaz seçilen konumlara bağlı değilse, bu, hemen uyumlu değil olarak kabul edilir. Kullanıcılarınıza bir gün gibi yetkisiz kullanım süresi verebilirsiniz.

## <a name="scope-tags"></a>Kapsam etiketleri

Kapsam etiketleri; Sales, HR, tüm ABD-NC çalışanları vb. gibi belirli gruplara ilke atamak ve filtrelemek için harika bir yoldur. Ayarları ekledikten sonra, uyumluluk ilkelerinize bir kapsam etiketi de ekleyebilirsiniz. [İlkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md) iyi bir kaynaktır.

## <a name="refresh-cycle-times"></a>Yenileme döngüsünü Yenile

Intune, uyumluluk ilkelerine yönelik güncelleştirmeleri denetlemek için farklı yenileme döngüleri kullanır. Cihaz yakın zamanda kaydedildiyse, iade etme daha sık çalışır. [İlke ve profil yenileme döngüleri](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) tahmini yenileme zamanlarını listeler.

Herhangi bir zamanda, kullanıcılar Şirket Portalı uygulamayı açabilir ve cihaz güncelleştirmelerini anında denetlemek için cihazı eşitleyebilir.

### <a name="assign-an-ingraceperiod-status"></a>Yetkisizkullanımsüresinde durumu atama

Bir uyumluluk ilkesinin Yetkisizkullanımsüresinde durumu bir değerdir. Bu değer, bir cihazın yetkisiz kullanım süresinin ve bu uyumluluk ilkesi için bir cihazın gerçek durumunun birleşimiyle belirlenir.

Özellikle, bir cihazın atanmış uyumluluk ilkesi için uyumsuz bir durumu varsa ve:

- Cihaza atanmış bir yetkisiz kullanım süresi yoksa, uyumluluk ilkesi için atanan değer uyumsuz
- Cihazda süresi geçen bir yetkisiz kullanım süresi varsa, uyumluluk ilkesi için atanan değer uyumsuz olur
- Cihazda daha sonra bir yetkisiz kullanım süresi varsa, uyumluluk ilkesi için atanan değer Yetkisizkullanımsüresinde olur

Aşağıdaki tabloda bu noktaları özetlenmektedir:

|Gerçek uyumluluk durumu|Atanan yetkisiz kullanım süresi değeri|Etkili uyumluluk durumu|
|---------|---------|---------|
|Izde |Hiçbir yetkisiz kullanım süresi atanmadı |Izde |
|Izde |Dünün tarihi|Izde|
|Izde |Yarının tarihi|Yetkisizkullanımsüresinde|

Cihaz uyumluluk ilkelerini izleme hakkında daha fazla bilgi için bkz. [Intune cihaz uyumluluk Ilkelerini izleme](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Sonuç olarak bir uyumluluk ilkesi durumu atama

Bir cihazda birden fazla uyumluluk ilkesi varsa ve cihazın bu atanmış uyumluluk ilkelerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, tek bir sonuç uyumluluk durumu atanır. Bu atama, her uyumluluk durumuna atanan kavramsal önem derecesini temel alır. Her uyumluluk durumu aşağıdaki önem düzeyine sahiptir:

|Durum  |Önem Derecesi  |
|---------|---------|
|Bilinmiyor     |1\.|
|Notapplıcable     |2|
|uyumlu|3|
|Yetkisizkullanımsüresinde|4|
|Izde|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi olduğunda, tüm ilkelerin en yüksek önem derecesi bu cihaza atanır.

Örneğin, bir cihaza atanmış üç uyumluluk ilkesi vardır: bir bilinmeyen durum (önem derecesi = 1), bir uyumluluk durumu (önem derecesi = 3) ve bir Yetkisizkullanımsüresinde durumu (önem derecesi = 4). Yetkisizkullanımsüresinde durumu en yüksek önem düzeyine sahiptir. Bu nedenle, üç ilkenin tümünde Yetkisizkullanımsüresinde uyumluluk durumu vardır.

## <a name="next-steps"></a>Sonraki adımlar

[Ilkelerinizi izleyin](compliance-policy-monitor.md).
