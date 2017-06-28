---
title: "Kullanıcı ve cihazları yönetmek için grupları kullanma"
description: "Gruplar çalışma alanını kullanarak grupları oluşturun ve yönetin."
keywords: 
author: Mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 13c8946dd75d6bdede0e2a8941030250c6b12ef6
ms.contentlocale: tr-tr
ms.lasthandoff: 06/08/2017


---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a>Microsoft Intune’da kullanıcı ve cihazları yönetmek için grupları kullanma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu, Intune’da grupların nasıl oluşturulacağını açıklar. Ayrıca grupların yönetiminin önümüzdeki aylarda nasıl değişeceğine ilişkin bilgiler sağlar. 

>[!IMPORTANT]
>
>Intune portalında Gruplar çalışma alanını açar ve Azure Active Directory (Azure AD) portalına bir bağlantı görürseniz [Grupları Azure Active Directory’ye geçirme](migrating-groups-to-azure-active-directory.md) kısmında açıklanan, Intune’daki Azure AD güvenlik gruplarına yönelik *yeni* grup yönetimi yaklaşımını kullanıyorsunuz demektir. Gruplarınızı oluşturmak ve yönetmek için Azure AD portalı bağlantısına tıklayın.
>
>![Azure grup yönetimi bağlantısının ekran görüntüsü](../media/groups-link-azure.png) 
>
>Azure AD portalı bağlantısını görmüyorsanız, hâlâ bu konunun [Microsoft Intune'la kullanıcı ve cihazları yönetmek için gruplar oluşturma](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune) kısmında açıklanan *mevcut* grup yönetimi yaklaşımını kullanıyorsunuz demektir.

Bu konu başlığında, Intune yönetim konsolunda Intune gruplarını nasıl oluşturacağınız açıklanır.

Microsoft Intune yönetim konsolundaki **Gruplar** çalışma alanını kullanarak gruplar oluşturabilir ve yönetebilirsiniz. **Gruplara Genel Bakış** sayfası dikkat etmeniz gereken sorunları belirlemenize ve öncelik vermenize yardımcı olabilecek durum özetleri gösterir. Durum özetleri şu alanları kapsar:

-   Uyarılar
-   Yazılım güncelleştirmeleri
-   Endpoint Protection
-   İlke
-   Yazılım yönetimi

Seçili grubun üyeleri için sorunları tanımlamanıza ve çözmenize yardımcı olmak amacıyla grup hiyerarşinizde durum özetleri de gösterilir.

## <a name="create-groups"></a>Grup oluşturma

> [!TIP]
> Gruplarınızı oluştururken, ilkeleri nasıl uygulayacağınızı düşünün. Örneğin, cihaz işletim sistemine özgü ilkeleriniz veya Active Directory’de zaten tanımlamış olduğunuz kuruluşunuzdaki farklı rollere veya kuruluş birimlerine özgü ilkeleriniz olabilir. iOS, Android ve Windows için ayrı cihaz gruplarına ve her bir kurumsal rol için kullanıcı gruplarına sahip olmak yararlı olabilir.
>
> Ayrıca kuruluşunuzun temel uyumluluk gereksinimlerini belirlemek için tüm gruplara ve cihazlara uygulanan varsayılan bir ilke oluşturmak isteyebilirsiniz. Ardından, en geniş kullanıcı ve cihaz kategorileri için daha özel ilkeler oluşturabilirsiniz. Örneğin, her cihaz işletim sistemi için e-posta ilkeleri oluşturabilirsiniz.
>
> İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırmaya dikkat edin. Örneğin, iyi bir açıklayıcı ilke adı **Tüm Şirket için WP E-posta İlkesi**olabilir.
>
> Her kısıtlayıcı ilke oluşturduğunuzda, bunu kullanıcılarınıza iletmelisiniz. Daha genel gruplar ve ilkeler oluşturduktan sonra gereksiz iletişimi azaltmak için nasıl daha küçük gruplar oluşturabileceğinize dikkat edin.

## <a name="to-create-a-device-group"></a>Bir cihaz grubu oluşturmak için

1.  Intune yönetim konsolunda, **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin.

2.  Grup için bir ad ve açıklama (isteğe bağlı) girin, ardından üst grup olarak bir cihaz grubunu seçin. **İleri**’yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında, grubun içereceği cihaz türünü seçin. Dahil etmeyi seçtiğiniz cihaz türlerine dayalı olarak ek grup yapılandırma seçenekleriniz vardır:

    -   **Bilgisayar**. Üst grubun tüm üyelerinin eklenip eklenmeyeceğini, dahil etmek veya dışlamak istediğiniz kuruluş birimlerini ve dahil etmek veya dışlamak istediğiniz etki alanlarını seçin. Bir bilgisayar için envanterden kuruluş birimi ve etki alanı bilgileri elde edebilirsiniz.

    -   **Mobil**. Yalnızca Intune tarafından yönetilen mobil cihazların, Exchange ActiveSync tarafından yönetilen mobil cihazların veya her ikisinin de dahil edileceğini belirtin.

    -   **Tüm cihazlar**. Bu seçenek, herhangi bir ölçüte dayalı özel durumlar olmadan tüm cihazları içerir.

4.  **Doğrudan Üyeliği Tanımla** sayfasında, **Gözat**'ı seçerek cihazları tek tek dahil edin veya dışlayın. Belirttiğiniz üst grupta olmayan cihazları seçerseniz, Intune bu cihazları otomatik olarak üst gruba ekler.

5.  **Özet** sayfasında, seçimlerinizi gözden geçirin ve **Son**’u seçin.

Yeni oluşturulan grup **Gruplar** çalışma alanının **Gruplar** listesinde, üst grubun altında gösterilir. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

## <a name="to-create-a-user-group"></a>Bir kullanıcı grubu oluşturmak için

1.  Intune yönetim konsolunda, **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin.

2.  Grup için bir ad ve açıklama (isteğe bağlı) girin, ardından üst grup olarak bir kullanıcı grubunu seçin. **İleri**’yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında, bir üst grubun tüm üyelerini eklemeyi veya boş bir grupla başlamayı seçin. Ardından [Office 365 yönetici merkezinde](http://go.microsoft.com/fwlink/?LinkId=698854) el ile yapılandırdığınız veya Active Directory'den eşitlediğiniz güvenlik gruplarını temel alarak üyeleri dahil edebilir veya hariç tutabilirsiniz. Bir güvenlik grubunun üyeliği değişirse, bu güvenlik grubunu temel alan kullanıcı gruplarının üyeliği de değişebilir.

    > [!IMPORTANT]
    > Şu anda, grubunuz belirli güvenlik veya yönetici gruplarından üyeler içeriyorsa ve bazı grupların üyelerini dışlıyorsanız, başlangıçta dahil ettiğiniz üyeler kaldırılır. Hem dahil edilen hem de dışlanan üyeleri olan bir grup oluşturmak için önce dahil edilen üyeleri içeren bir üst grup oluşturmanızı öneririz. Ardından, söz konusu üst grupta bir alt grup oluşturun. Yeni alt grupta dışlanan üyeleri listeleyin. Bundan sonra, Intune ilkeleri, profilleri ve uygulama dağıtımını yönetmek için bu alt grubu kullanın.

    > [!NOTE]
    > Azure portalında kullanıcıların amiri olan yöneticilere göre gruplar oluşturabilirsiniz. Bu, dinamik bir grup türüdür ve Azure Active Directory’de söz konusu yöneticinin ekibine çalışanlar eklendikçe veya ekipten çalışanlar çıkarıldıkça değişir. Yönetici adını temel alan bir Azure grubu oluşturma, [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) altındaki **Grubu bir “Yönetici” grubu olarak yapılandırma** bölümünde açıklanır.

4.  **Doğrudan Üyeliği Tanımla** sayfasında, **Gözat**'ı seçerek kullanıcıları tek tek dahil edin veya dışlayın. Belirttiğiniz üst grupta olmayan kullanıcıları seçerseniz, bu cihazlar otomatik olarak üst gruba eklenir. Kullanıcıyı el ile ekleme seçeneği **Üyeleri Seçin** iletişim kutusunun alt kısmında bulunabilir. Henüz kayıtlı cihazı olmayan bir kullanıcıyı eklemek isterseniz, bu seçenek yararlı olur.

5.  **Özet** sayfasında, seçimlerinizi gözden geçirin ve **Son**’u seçin.

Yeni oluşturulan grup **Gruplar** çalışma alanının **Gruplar** listesinde, üst grubun altında gösterilir. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

> [!TIP]
> Güvenlik grupları, kullanıcı gruplarını doldururken kullanmak için iyi bir kaynaktır. Güvenlik gruplarınız kimlerin hangi kaynaklara erişiminin olacağını tanımladığından, güvenlik grupları iyi bir şekilde Intune kullanıcı gruplarına çevrilebilir. Active Directory’den Azure Active Directory’ye eşitlenen veya Office 365 yönetici merkezi ya da Azure portalı aracılığıyla doğrudan Azure Active Directory’de oluşturduğunuz güvenlik gruplarını Intune’da kullanıcı grubu oluşturmak için kullanabilirsiniz.

## <a name="filter-admin-views-by-role"></a>Yönetici görünümleri role göre filtreleme
Filtrelenen grup görünümlerinde, bir BT yöneticisinin görebileceklerini yöneticinin rolüne bağlı olarak belirleyebilirsiniz. Ayrıca, her bir BT yöneticisinin yönetebileceği grupları kısıtlayabilirsiniz. Bu aşağıdaki durumlarda kullanışlı olabilir:

-   BT yöneticilerinizin yalnızca belirli kullanıcı ve cihazlara öğe dağıtabilmesini istiyorsunuz
-   BT yöneticilerinizin yalnızca o yönetici için uygun olan grupları görmesini istiyorsunuz

Intune yönetici konsolunda hizmet yöneticileri için filtrelenen grup görünümlerini yapılandırabilirsiniz. Ayrıntılar için bkz. [Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](/intune/supported-devices-browsers).

Bir hizmet yöneticisi için filtrelenen grup görünümleri ayarladığınızda, yönetici yazılım veya ilkeler dağıttığında veya rapor hazırladığında, yalnızca belirttiğiniz grupları görüntüleyebilir ve seçebilir. Ayrıca yönetici konsolunun şu sayfalarındaki durum bilgilerini görmez:

-   **Sisteme Genel Bakış**
-   **Gruplara Genel Bakış**
-   **Endpoint Protection'a Genel Bakış**
-   **Uyarılara Genel Bakış**
-   **Yazılıma Genel Bakış**
-   **İlkeye Genel Bakış**

### <a name="to-create-a-filtered-group-view"></a>Bir filtrelenen grup görünümü oluşturmak için

1.  Intune yönetim konsolunda, **Yönetici** &gt; **Yönetici Yönetimi** &gt; **Hizmet Yöneticileri**’ni seçin.

2.  Filtrelenen Grup görünümü oluşturmak istediğiniz hizmet yöneticisini seçin ve ardından **Grupları Yönet**’i seçin.

3.  **Bu hizmet yöneticisinin görebileceği grupları seçin** iletişim kutusunda, hizmet yöneticisinin erişebileceği grupları ekleyin ve ardından **Tamam**'ı seçin.

Filtrelenen grup görünümlerini ayarladıktan sonra, BT yöneticisi yalnızca belirttiğiniz grupları görebilir ve seçebilir.

## <a name="manage-your-groups"></a>Gruplarınızı yönetme
Gruplarınızı oluşturduktan sonra, bunları kuruluşunuzun gereksinimlerine göre yönetmeye devam edebilirsiniz.

Adını veya açıklamasını veya gruba ait olan kişileri değiştirmek için grubunuzu düzenleyebilirsiniz.

Artık kuruluşunuzun gereksinimlerine hizmet etmeyen bir grubu silebilirsiniz. Grup silindiğinde, o gruba ait kullanıcılar silinmez.

## <a name="next-steps"></a>Sonraki adımlar
Gruplarınızı ve ilkelerinizi ayarladıktan sonra, tasarımınızın pratik çıkarımlarını denetlemek için **Amaçlanan Değer** ve **Durum** bilgilerini gözden geçirin.

### <a name="to-check-your-design"></a>Tasarımınızı denetlemek için

1. Bir cihaz grubundan herhangi bir cihaz seçin ve sayfanın en üstündeki bilgi kategorileri arasında gezinin.
2. **İlke**’yi seçin. Android cihazının ilke ayarlarının bu ekran görüntüsüne benzer bir şey görürsünüz.

![Android ayarları ilkesi örneği](../media/Intune-Device-Policy-v.2.jpg)

Her ilkenin bir **Amaçlanan Değer** ‘i ve bir de **Durum**‘u vardır. Amaçlanan değer, ilkeyi atadığınızda ne elde etmeyi amaçladığınızı belirtir. Durum; cihaza uygulanan tüm ilkeler, donanım ve işletim sistemi kısıtlamaları ve gereksinimleri birlikte değerlendirildiğinde elde ettiğiniz şeydir. Bu ekran görüntüsünde iki açık örnek görebilirsiniz:

-   **Amaçlanan Değer** sütununda gösterildiği gibi **Basit parolalara izin ver**, **Evet** olarak ayarlanmış, ancak **Durum** ‘u **Uygulanamaz**‘dır. Bunu nedeni, Android cihazlar için basit parolaların desteklenmemesidir.
-   Benzer şekilde, bu cihaz bir Android cihazı olduğundan **iOS cihazları için e-posta ayarları** genişletilmiş ilke öğesi bu cihaza uygulanmaz.

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, gerçekte daha kısıtlayıcı olan ilkenin uygulanacağını unutmayın.

