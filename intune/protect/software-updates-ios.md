---
title: Microsoft Intune-Azure 'da iOS/ıpados yazılım güncelleştirme ilkelerini yapılandırma | Microsoft Docs
description: Microsoft Intune içinde, yazılım güncelleştirmelerinin iOS/ıpados cihazlarına otomatik olarak ne zaman yükleneceğini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77d4a90bb2eaa8434ff9c05362dcb0d7cb270651
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576160"
---
# <a name="add-iosipados-software-update-policies-in-intune"></a>Intune 'da iOS/ıpados yazılım güncelleştirme ilkeleri ekleme

Yazılım güncelleştirme ilkeleri, denetimli iOS/ıpados cihazlarını otomatik olarak işletim sistemi güncelleştirmelerini yüklemeye zorlamanıza olanak sağlar. Denetimli cihazlar, Apple Business Manager veya Apple Okul Yöneticisi kullanılarak kaydolmuş olanlardır. Güncelleştirmeleri dağıtmak üzere bir ilke yapılandırırken şunları yapabilirsiniz:

- En *son güncelleştirmeyi* dağıtmayı seçin veya en son güncelleştirmeyi dağıtmak istemiyorsanız, güncelleştirme sürüm numarasıyla daha eski bir güncelleştirme dağıtmayı seçin. Daha eski bir güncelleştirmeyi dağıtmayı seçerseniz, yazılım güncelleştirmelerinin görünürlüğünü kısıtlamak için bir cihaz yapılandırma ilkesi de ayarlamanız gerekir.
- Güncelleştirmenin ne zaman yüklenip yüklenmeyeceğini belirleyen bir zamanlama belirtin. Zamanlamalar, cihazın bir sonraki denetlediğinde güncelleştirmeleri yüklemek ya da güncelleştirmelerin yüklenebileceği veya yüklenmesi engellenen tarih ve saat aralıkları oluşturmak kadar kolay olabilir.

Bu özellik şu platformlarda geçerlidir:

- iOS 10,3 ve üzeri (denetimli)

Varsayılan olarak, cihazlar, her 8 saatte bir Intune ile oturum iade ediyor. Güncelleştirme ilkesi aracılığıyla bir güncelleştirme varsa, cihaz güncelleştirmeyi indirir. Daha sonra cihaz, güncelleştirmeleri zamanlama yapılandırmanızın sonraki iadeye yükleme sırasında yüklenir. Güncelleştirme işlemi genellikle herhangi bir kullanıcı etkileşimini kapsamaz, ancak cihazın bir geçiş kodu varsa, yazılım güncelleştirmesini başlatmak için kullanıcının parolayı girmesi gerekir. Profiller, kullanıcıların işletim sistemini el ile güncelleştirmesine engel olmaz. Yazılım güncelleştirmelerinin görünürlüğünü kısıtlamak için, kullanıcıların işletim sistemini bir cihaz yapılandırma ilkesiyle el ile güncelleştirmelerini engellemiş olabilir.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Cihaz** seçin > **IOS/ıpados** > **Profil oluştur**' a tıklayın.
3. **Temel bilgiler** sekmesinde, bu ilke için bir ad belirtin, bir açıklama (isteğe bağlı) belirtin ve ardından **İleri**' yi seçin.

   ![Temel bilgiler sekmesi](./media/software-updates-ios/basics-tab.png)

4. **İlke ayarlarını Güncelleştir** sekmesinde aşağıdakileri yapılandırın:

   1. **Yüklenecek sürümü seçin**. Şunlar arasından seçim yapabilirsiniz:

      - *En son güncelleştirme*: Bu, IOS/ıpados için en son yayınlanan güncelleştirmeyi dağıtır.
      - Açılan kutuda bulunan önceki tüm sürümleri. Önceki bir sürümü seçerseniz, yazılım güncelleştirmelerinin görünürlüğünü geciktirmek için bir cihaz yapılandırma ilkesi de dağıtmanız gerekir.

   2. **Zamanlama türü**: Bu ilke için zamanlamayı yapılandırın:

      - *Sonraki Iadede Güncelleştir*: güncelleştirme, Intune 'a bir dahaki sefer iade ettiğinde cihaza yüklenir. Bu en basit seçenektir ve ek yapılandırmalara sahip değildir.
      - *Zamanlanan süre sırasında Güncelleştir*: güncelleştirmenin iadeden sonra yükleneceği bir veya daha fazla zaman penceresi yapılandırırsınız.
      - *Zamanlanan süre dışında Güncelleştir*: güncelleştirmelerin iadeden sonra yüklenemeyeceği bir veya daha fazla zaman penceresi yapılandırırsınız.

   3. **Haftalık zamanlama**: *sonraki iadede Update*dışında bir zamanlama türü seçerseniz, aşağıdaki seçenekleri yapılandırın:

      ![Zamanlanan süre içinde güncelleştirme seçme örneği](./media/software-updates-ios/scheduled-time.png)

      - **Saat dilimi**: bir saat dilimi seçin.
      - **Zaman penceresi**: güncelleştirmelerin ne zaman yükleneceğini kısıtlayan bir veya daha fazla zaman bloğunu tanımlayın. Aşağıdaki seçeneklerin etkisi, seçtiğiniz zamanlama türüne bağlıdır. Başlangıç günü ve bitiş günü kullanarak, fazla gece blokları desteklenir. Şu seçenekler mevcuttur:

        - **Başlangıç günü**: zamanlama penceresinin başladığı günü seçin.
        - **Başlangıç zamanı**: zamanlama penceresinin başladığı saat gününü seçin. Örneğin, 5 saat ' i seçerseniz ve *zamanlanan süre içinde*bir zamanlama türünde güncelleştirme varsa, güncelleştirmelerin yüklenmeye başlayaabileceği zaman 5 ' i olur. *Zamanlanan bir süre dışında güncelleştirme*zamanlama türünü seçerseniz, güncelleştirmelerin yüklenemeyecek bir süre başlangıcı 5 ÖÖ olur.
        - **Bitiş günü**: zamanlama penceresinin bitiş gününü seçin.
        - **Bitiş zamanı**: zamanlama penceresinin durduğu günün saatini seçin. Örneğin, 1 saat ' i seçerseniz ve *zamanlanan süre içinde*bir zamanlama türünde güncelleştirme varsa, güncelleştirmelerin artık yüklenememesi için 1 saat olur. *Zamanlanan bir süre dışında güncelleştirme*zamanlama türünü seçerseniz, 1 saat, güncelleştirmelerin yükleyebileceği sürenin başlangıcı olur.

       Başlangıç veya bitiş için zaman yapılandırmak istemiyorsanız, yapılandırma hiçbir zaman herhangi bir kısıtlama ve güncelleştirme yüklemeye neden olur.  

       > [!NOTE]
       > Denetimli iOS/ıpados cihazlarınızda belirli bir süre için yazılım güncelleştirmelerinin görünürlüğünü geciktirmek için bu ayarları [cihaz kısıtlamalarında](../configuration/device-restrictions-ios.md#general)yapılandırın. Yazılım güncelleştirme ilkeleri tüm cihaz kısıtlamalarını geçersiz kılar. Yazılım güncelleştirmelerinin görünürlüğünü geciktirmek için hem yazılım güncelleştirme ilkesi hem de kısıtlama ayarladığınızda, cihaz ilke başına bir yazılım güncelleştirmesi zorlar. Kısıtlama, kullanıcıların cihazın kendilerini güncelleştirme seçeneğini görmemesi ve güncelleştirme iOS güncelleştirme ilkenize göre belirlenen şekilde itilmesi için geçerlidir.

   *Güncelleştirme ilkesi ayarlarını*yapılandırdıktan sonra **İleri**' yi seçin.

5. **Kapsam etiketleri** sekmesinde **+ kapsam etiketlerini Seç** ' i seçerek bunları güncelleştirme Ilkesine uygulamak istiyorsanız *etiketleri Seç* bölmesini açın.

   - **Etiketleri seçin** bölmesinde bir veya daha fazla etiket seçin ve ardından **Seç** ' e tıklayarak bunları ilkeye ekleyin ve *kapsam etiketleri* bölmesine dönün.

   Hazırlandığınızda, *atamalara*devam etmek için **İleri** ' yi seçin.

6. **Atamalar** sekmesinde **+ dahil edilecek grupları seç** ' i seçin ve ardından güncelleştirme ilkesini bir veya daha fazla gruba atayın. Atamanın ince ayar yapmak için **+ Select grupları** kullanın. Hazırlandığınızda, devam etmek için **İleri** ' yi seçin.

   İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir. Bu ilke kullanıcısı olmayan cihazları da destekler.

7. **Gözden geçir + oluştur** sekmesinde ayarları gözden geçirin ve ardından IOS/ıpados güncelleştirme ilkenizi kaydetmeye hazırsanız **Oluştur** ' u seçin. Yeni ilkeniz iOS/ıpados güncelleştirme ilkeleri listesinde görüntülenir.

Intune destek ekibinin Kılavuzu için bkz. [denetimli cihazlar Için Intune 'da yazılım güncelleştirmeleri gecikmesi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Apple MDM, cihazın güncelleştirmeleri belirli bir saatte veya tarihte yüklemeye zorlanmasına izin vermez. Intune yazılım güncelleştirme ilkelerini, bir cihazdaki işletim sistemi sürümünün indirgenmesini sağlamak için kullanamazsınız.

## <a name="edit-a-policy"></a>Bir ilkeyi düzenleme

Varolan bir ilkeyi, sınırlı zamanları değiştirme dahil olmak üzere düzenleyebilirsiniz:

1. **İOS Için güncelleştirme ilkelerini** > **cihazlar** ' ı seçin. Düzenlemek istediğiniz ilkeyi seçin.

2. İlke **özelliklerini**görüntülerken, değiştirmek istediğiniz ilke sayfası için **Düzenle** ' yi seçin.

   ![Bir ilkeyi düzenleme](./media/software-updates-ios/edit-policy.png)

3. Bir değişikliği gönderdikten sonra, düzenlemelerinizi kaydetmek için **gözden geçir + kaydet** > **Kaydet** ' i seçin ve ilkeler *özelliklerine*geri dönün.

> [!NOTE]
> **Başlangıç saati** ve **bitiş saatinin** her ikisi de 12. olarak ayarlandıysa, Intune güncelleştirmelerin ne zaman yükleneceğine ilişkin kısıtlamaları denetlemez. Bu, **güncelleştirme yüklemelerinin yoksayılmasını** ve güncelleştirmelerin herhangi bir zamanda yüklenebilmesini sağlamak için, seçtiğiniz her yapılandırmalardan daha fazla yol gösterir.

## <a name="monitor-device-installation-failures"></a>Cihaz yükleme hatalarını izleme

<!-- 1352223 -->
İOS cihazları için **yazılım güncelleştirmeleri** > **yükleme hatalarıyla ilgili** güncelleştirme Ilkesi tarafından hedeflenen Denetlenen iOS/ıpados cihazlarının bir listesini gösterir, güncelleştirme denenir ve güncelleştirilemez. Her cihazda, cihazın otomatik olarak güncelleştirilememesinin nedenini açıklayan bir durum görebilirsiniz. İyi durumda, güncel cihazlar bu listede gösterilmez. “Güncel” cihazlar, cihazın desteklediği en yeni güncelleştirmeyi içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Durumunu izleyin](../configuration/device-profile-monitor.md).
