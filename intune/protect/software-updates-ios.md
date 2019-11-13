---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma - Azure | Microsoft Docs
description: Microsoft Intune ' de, yazılım güncelleştirmelerinin iOS cihazlarına otomatik olarak ne zaman yükleneceğini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f9750603d19d9b19697c7d2660351c4586432f6
ms.sourcegitcommit: a7c35efb31c4efd816bd4aba29240013965aee92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "73984189"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Intune 'A iOS yazılım güncelleştirme ilkeleri ekleme

Yazılım güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. İlke yapılandırırken, cihazların güncelleştirme yüklemesi yapmalarını istemediğiniz gün ve saatleri ekleyebilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- iOS 10,3 ve üzeri (denetimli)

Cihaz, 8 saatte bir Intune’a iade edilir. Bir güncelleştirme varsa, cihaz, kısıtlı zamanlar dışında indirir ve yükler. Güncelleştirme işlemi genellikle herhangi bir kullanıcı etkileşimini kapsamaz, ancak cihazın bir geçiş kodu varsa, bir yazılım güncelleştirmesi başlatmak için kullanıcının bu parolayı girmesi gerekir. Bu, iOS 10,3 ve sonraki sürümleri için geçerlidir. İlke, kullanıcının işletim sistemini el ile güncelleştirmesini engellemez.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Yazılım güncelleştirilmeleri** > **iOS için güncelleştirme ilkeleri** > **Oluştur**’u seçin.
3. **Temel bilgiler** sekmesinde, bu ilke için bir ad belirtin, bir açıklama (isteğe bağlı) belirtin ve ardından **İleri**' yi seçin.

   ![Temel bilgiler sekmesi](./media/software-updates-ios/basics-tab.png) 

4. **Güncelleştirme ilkesi ayarları** sekmesinde, güncelleştirmeler zorlanmadıkça sınırlı bir zaman dilimi belirtin.  
   - Fazla gece blokları desteklenmez ve çalışmayabilir. Örneğin, bir ilkeyi 8 PM *Başlangıç saati* ve 6 ' nın *bitiş saati* ile yapılandırmayın.
   - 12:00 ' da başlayan ve 12 saat içinde biten bir ilke, 24 saat değil 0 saat olarak değerlendirilir. Bu yapılandırma hiçbir kısıtlama vermez.

   Kısıtlanmış zaman çerçevesini ayarlarken, aşağıdaki ayrıntıları girin:

   - **Gün**: güncelleştirmelerin yüklü olmadığı haftanın gününü seçin. Örneğin, bu günlerde güncelleştirmelerin yüklenmesini engellemek için Pazartesi, Çarşamba ve Cuma ' yı işaretleyin.
   - **Saat dilimi**: bir saat dilimi seçin.
   - **Başlangıç zamanı**: sınırlı zaman çerçevesinin başlangıç saatini seçin. Örneğin, güncelleştirmelerin 5 ' de itibaren yüklenememesi için 5 har girin.
   - **Bitiş zamanı**: sınırlı zaman çerçevesinin bitiş saatini seçin. Örneğin, güncelleştirme 1 ' den başlayarak yüklenebilmeleri için 1 har girin.
  
   > [!IMPORTANT]  
   > *Başlangıç zamanı* ve *bitiş zamanı* 12 ' ye ayarlanmış bir ilke, 24 saat değil 0 saat olarak değerlendirilir. Bu durum hiçbir kısıtlama vermez.  
    
   Denetimli iOS cihazlarınızda yazılım güncelleştirmelerinin görünürlüğünü belirli bir süre boyunca geciktirmek için bu ayarları [cihaz kısıtlamalarında](../configuration/device-restrictions-ios.md#general)yapılandırın. Yazılım güncelleştirme ilkeleri tüm cihaz kısıtlamalarını geçersiz kılar. Yazılım güncelleştirmelerinin görünürlüğünü geciktirmek için hem yazılım güncelleştirme ilkesi hem de kısıtlama ayarladığınızda, cihaz ilke başına bir yazılım güncelleştirmesi zorlar. Kısıtlama, kullanıcıların cihazın kendisini güncelleştirme seçeneğini görmemesi için geçerlidir ve güncelleştirme, iOS güncelleştirme ilkenize göre belirlenen ilk pencerede gönderilir.

   *Güncelleştirme ilkesi ayarlarını*yapılandırdıktan sonra **İleri**' yi seçin. 

5. **Kapsam etiketleri** sekmesinde **+ kapsam etiketlerini Seç** ' i seçerek bunları güncelleştirme Ilkesine uygulamak istiyorsanız *etiketleri Seç* bölmesini açın.
   
   - **Etiketleri seçin** bölmesinde bir veya daha fazla etiket seçin ve ardından **Seç** ' e tıklayarak bunları ilkeye ekleyin ve *kapsam etiketleri* bölmesine dönün.  

   Hazırlandığınızda, *atamalara*devam etmek için **İleri** ' yi seçin.

6. **Atamalar** sekmesinde **+ dahil edilecek grupları seç** ' i seçin ve ardından güncelleştirme ilkesini bir veya daha fazla gruba atayın. Atamanın ince ayar yapmak için **+ Select grupları** kullanın. Hazırlandığınızda, devam etmek için **İleri** ' yi seçin. 

   İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir. Bu ilke kullanıcısı olmayan cihazları da destekler.

7. **Gözden geçir + oluştur** sekmesinde ayarları gözden geçirin ve ardından iOS güncelleştirme ilkenizi kaydetmeye hazırsanız **Oluştur** ' u seçin. Yeni ilkeniz iOS için güncelleştirme ilkeleri listesinde görüntülenir.


Intune destek ekibinin Kılavuzu için bkz. [denetimli cihazlar Için Intune 'da yazılım güncelleştirmeleri gecikmesi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Apple MDM, cihazın güncelleştirmeleri belirli bir saatte veya tarihte yüklemeye zorlanmasına izin vermez.

## <a name="edit-a-policy"></a>Bir ilkeyi düzenleme
Varolan bir ilkeyi, sınırlı zamanları değiştirme dahil olmak üzere düzenleyebilirsiniz:

1. **Yazılım güncelleştirmeleri**' nde **iOS için güncelleştirme ilkeleri** ' ni seçin ve ardından düzenlemek istediğiniz ilkeyi seçin.

2. İlke **özelliklerini**görüntülerken, değiştirmek istediğiniz ilke sayfası için **Düzenle** ' yi seçin.  
   poliie](./media/software-updates-ios/edit-policy.png) ![düzenleme   

3. Bir değişikliği gönderdikten sonra, düzenlemelerinizi kaydetmek için **gözden geçir + kaydet**  > **Kaydet** ' i seçin ve ilkeler *özelliklerine*geri dönün.  
 
> [!NOTE]
> **Başlangıç saati** ve **bitiş saatinin** her ikisi de 12. olarak ayarlandıysa, Intune güncelleştirmelerin ne zaman yükleneceğine ilişkin kısıtlamaları denetlemez. Bu, **güncelleştirme yüklemelerinin yoksayılmasını** ve güncelleştirmelerin herhangi bir zamanda yüklenebilmesini sağlamak için, seçtiğiniz her yapılandırmalardan daha fazla yol gösterir.  


## <a name="monitor-device-installation-failures"></a>Cihaz yükleme hatalarını izleme
<!-- 1352223 -->
İOS cihazları için **yazılım güncelleştirmeleri**  > **yükleme hatalarıyla ilgili** güncelleştirme Ilkesi tarafından hedeflenen Denetlenen iOS cihazlarının bir listesi görüntülenir, güncelleştirme denenir ve güncelleştirilemez. Her cihazda, cihazın otomatik olarak güncelleştirilememesinin nedenini açıklayan bir durum görebilirsiniz. İyi durumda, güncel cihazlar bu listede gösterilmez. “Güncel” cihazlar, cihazın desteklediği en yeni güncelleştirmeyi içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Durumunu izleyin](../configuration/device-profile-monitor.md).
