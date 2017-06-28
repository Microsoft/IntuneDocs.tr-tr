---
title: "Kullanıcı ve cihaz gruplarınızı planlama"
description: "Grupları, kurumsal gereksinimlerinizi karşılayacak şekilde planlayın."
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1362c42cb44848d5ab3a88d08b19d8f6aee195b9
ms.contentlocale: tr-tr
ms.lasthandoff: 06/08/2017


---

# <a name="plan-your-user-and-device-groups"></a>Kullanıcı ve cihaz gruplarınızı planlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune’daki gruplar, cihazlarınızı ve kullanıcılarınızı yönetirken büyük esneklik sağlar. Grupları, kuruluş gereksinimlerinize uyacak şekilde aşağıdaki ölçütlere göre ayarlayabilirsiniz:

- coğrafi konum
- bölüm
- donanım özellikleri
- işletim sistemi
- cihazın kullanıcıya mı yoksa şirkete mi ait olduğu


## <a name="how-intune-groups-work"></a>Intune grupları nasıl çalışır


Bu, Intune yönetim konsolundaki **Gruplar** düğümünün varsayılan görünümüdür:

![Intune konsolundaki Gruplar düğümü varsayılan görünümünün ekran görüntüsü](../media/Intune_Planning_Groups_Default_small.png)

İlkeler gruplara dağıtılır, bu nedenle grup hiyerarşisi temel tasarım konularınızdan biridir. Grubu oluşturduktan sonra, grubun üst grubunu değiştiremeyeceğinizi bilmeniz önemlidir. Intune hizmetini kullanmaya başladığınız andan itibaren, gruplarınızı nasıl tasarladığınız kritik önem taşır. Kuruluş gereksinimlerinize göre bir grup hiyerarşisi tasarlamaya yönelik önerilen yöntemlerin bazıları aşağıda açıklanmıştır.

## <a name="group-membership-rules"></a>Grup üyeliği kuralları

- Bir grup kullanıcılar veya cihazları içerebilir ancak ikisini birden içeremez.

    * **Cihaz grupları**. Bu hem bilgisayarları hem de mobil cihazları içerir. Bir gruba bir bilgisayar ekleyebilmeniz için önce kaydedilmesi gerekir. Bir gruba bir mobil cihaz ekleyebilmeniz için ortamınızın mobil cihazları desteklemek için yapılandırılması ve cihazın kaydedilmesi veya Exchange ActiveSync'de bulunması gerekir.

    * **Kullanıcı grupları**. Grupta güvenlik gruplarından kullanıcılar olabilir. Güvenlik grupları Active Directory örneğinizle eşitlenir. Active Directory ile eşitlemezseniz, bu grupları el ile oluşturabilirsiniz.

- Bir cihaz veya kullanıcı birden fazla gruba ait olabilir.

- Bir grup aşağıdaki üyelik kurallarına göre üyeleri dahil edebiler veya hariç tutabilir:

    * **Ölçüt Üyeliği**. Bunlar üyeleri dahil etmek veya hariç tutmak için Intune tarafından çalıştırılan dinamik kurallardır. Bu ölçütlerde yerel Active Directory örneğinizle eşitlenen güvenlik grupları ve diğer bilgiler kullanılır. Güvenlik grubu veya veriler değişirse, ActiveDirectory ile eşitleme yaptığınızda grup üyelikleri de değişir.

    * **Doğrudan Üyelik**. Bunlar üyeleri açıkça dahil eden veya hariç tutan statik kurallardır. Üye listesi statiktir.

-   Kullanıcıların ve bilgisayarların dahil edildiği kullanıcı grupları veya cihaz grupları oluştururken Active Directory Etki Alanı Hizmetleri (AD DS) gerekli değildir. Ancak, cihaz gruplarına mobil cihazları eklemek için ortamınızın mobil cihazları destekleyecek şekilde yapılandırılması gerekir.

    Ayrıca, cihazlar bulunmalı ve Intune’a eklenmelidir.

## <a name="group-relationship-rules"></a>Grup ilişkisi kuralları

- Oluşturduğunuz her grubun bir üst grubu olmalıdır. Grubu oluşturduktan sonra, grubun üst grubunu değiştiremezsiniz.

- Kullanıcıları veya cihazları bir alt gruba eklediğinizde:

    * Alt grup her zaman üst grubun bir alt kümesi olur.

    * Bir alt gruba eklediğiniz yeni üyeler otomatik olarak grubun üst grubuna eklenir.

    * Üst gruptan hariç tutulan bir üyeyi bir alt gruba ekleyemezsiniz.

- Üst grubun üyeliği alt grup için kullanılabilir üyeliği tanımlar.

- Bir üst grubu sildiğinizde, tüm alt grupları silinir.

- Üst gruba içerik ve ilke dağıtabilir, ancak alt gruplara dağıtımı hariç tutabilirsiniz.

- Bir kullanıcı veya cihaz üst grubun üyesi değilse, bunu alt gruba ekleyebilirsiniz. Bunu yaparsanız, alt grubun yeni üyesi üst gruba eklenecektir.

    Öte yandan, üst gruptan hariç tutulan bir üyeyi alt gruba ekleyemezsiniz.

- Grup üyeliği yinelemelidir. Örneğin:

    * **Pat** yalnızca **Dizüstü Kullanıcıları** güvenlik grubunun üyesidir.

    * **Dizüstü Kullanıcıları** grubu **Onaylanan Kullanıcılar** güvenlik grubunun üyesidir.

    * Intune’da dinamik üyelik sorgusu kullanan ve **Onaylanan Kullanıcılar** grubunun üyelerini içeren bir grup oluşturursunuz. Sonuç olarak, Intune kullanıcı grubunuz **Pat**’i içerir.

> [!TIP]
> Gruplarınızı oluştururken, ilkeyi nasıl uygulayacağınızı düşünün. Örneğin, cihaz işletim sistemlerine özgü ilkeleriniz veya Active Directory hizmetinizde zaten tanımlamış olduğunuz farklı rollere veya kuruluş birimlerine özgü ilkeleriniz olabilir. Bazı yöneticiler iOS, Android ve Windows’a özgü cihaz grupları oluşturmayı yararlı bulur. Bunlar, her kuruluş rolü için oluşturulan kullanıcı gruplarına ek olarak oluşturulur.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Yerleşik gruplar
Intune’da düzenleyemeyeceğiniz veya silemeyeceğiniz dokuz yerleşik grup vardır: <!--maybe a screen shot would be best?-->

-   **Tüm Kullanıcılar**
    -   Gruplanmayan Kullanıcılar
-   **Tüm Cihazlar**
    -   Tüm Bilgisayarlar
    -   Tüm Mobil Cihazlar
        -   Tüm Doğrudan Yönetilen Cihazlar
        -   Tüm Exchange ActiveSync Tarafından Yönetilen Cihazlar
    -   Şirkete Ait Tüm Cihazlar
    -   Gruplanmayan Cihazlar

> [!NOTE]
> Sloganınız *basit tut* olsun. Kuruluşunuzun aşağıdaki bölümlerde açıklananlar gibi belirli gereksinimleri yoksa, işleri basit tutun ve varsayılan grup yapısını ve ilkelerini kullanın. Bu, uzun vadede hizmeti daha kolay yönetilebilir hale getirir. Kullanıcılarınız için aynı biçimi kullanabilirseniz bakım işlemi kolaylaşır. Gruba göre farklılıklar az olduğunda, bakımını yapmanız gereken ilkeleriniz de azalır.


### <a name="all-users-and-devices-in-your-organization"></a>Kuruluşunuzdaki tüm kullanıcılar ve cihazlar
Kuruluşunuzdaki tüm kullanıcılar ve cihazlar için bir üst grup tanımlayın. Büyük olasılıkla tümüne uygulanacak ilkeleriniz vardır. Bu amaçla Intune’un varsayılan **Tüm Kullanıcılar** ve **Tüm cihazlar** gruplarını kullanabilirsiniz. Cihazları belirtimlerine göre düzenleyen alt gruplar, örneğin kendi cihazını getir (KCG) cihazları için ve şirkete ait (CO) cihazlar için olan gruplar, **Tüm Kullanıcılar** ve **Tüm cihazlar** üst gruplarının alt grupları olabilir.

## <a name="customize-groups-for-your-organization"></a>Kuruluşunuz için grupları özelleştirme

### <a name="byod-and-corporate-owned-devices"></a>KCG ve şirkete ait cihazlar
Kuruluşunuzda çalışanların kendi cihazlarını kullanmalarına izin veriliyorsa, şirketin sahip olduğu cihazlar sağlanıyorsa veya her ikisinin bir birleşimi geçerliyse, bu cihaz kategorileri için ayrı ilkeler uygulamanızı öneririz.

KCG veya karma kullanım durumlarında, gizlilikle ilgili yerel yasal düzenlemeleri ihlal etmeyen ilkeler planlamaya özen gösterin. Kendi cihazlarını getirecek tüm kullanıcılar için bir üst grup oluşturun. Bu kategorideki tüm kullanıcılara uygulanabilecek ilkeleri uygulamak için bu grubu kullanın.

![KCG üst grubu oluşturma](../media/Intune_Planning_Groups_BYOD_small.png)

Benzer şekilde, kuruluşunuzdaki CO cihazı kullanıcıları için de bir grup oluşturabilirsiniz:

![KCG ve CO cihazları için eşdüzey kullanıcı grupları](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Coğrafi bölgeler için gruplar
Kuruluşunuz özel bölgeler için ilkelere ihtiyaç duyarsa, coğrafi bölgeyi temel alan gruplar oluşturabilirsiniz. Bu gruplarda, Active Directory örneğinizde zaten oluşturmuş olduğunuz bölgesel grupları temel alabilir ve bunları Azure Active Directory hizmetinizle eşitleyebilirsiniz. Ayrıca, bölgesel grupları doğrudan Azure Active Directory’de de oluşturabilirsiniz.

Aşağıdaki ekran görüntülerinde, şirket içi Active Directory örneğinizle eşitlenmiş grupları temel alarak Intune gruplarının nasıl oluşturulduğu gösterilir. Bu örneklerde **ABD Kullanıcı Grubu** adlı bir Active Directory güvenlik grubunuz olduğu varsayılır.

İlk olarak genel bilgileri sağlayın.

![Grubu Düzenle alanının ekran görüntüsü](../media/Intune_Planning_Groups_AD_General_small.png)

**Üyelik ölçütleri** altında, üyelik kurallarına göre kullanılacak güvenlik grubu olarak Active Directory ile eşitlenen **ABD Kullanıcı Grubu**’nu seçin.

![Grubu Düzenle iletişim kutusunun ekran görüntüsü](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Girdilerinizi gözden geçirin ve sonra grubu oluşturmak için **Son**’u seçin.

![Grubu Düzenle iletişim kutusunun ekran görüntüsü](../media/Intune_Planning_Groups_AD_Summary_small.png)

Örneğimizde, Orta Doğu ve Asya için **MEA** adında bir grup da oluşturduk.

> [!NOTE]
> Grup üyeliği güvenlik grubu üyeliğine göre doldurulmazsa, grup üyelerine Intune lisansları atadığınızdan emin olun.

### <a name="groups-for-specific-hardware"></a>Belirli donanımlara yönelik gruplar
Kuruluşunuzda belirli donanım türlerine uygulanacak ilkeler gerekiyorsa, bu gereksinimi temel alan gruplar oluşturabilirsiniz. İlkelerde, şirket içi Active Directory örneğinizde zaten oluşturmuş olduğunuz güvenlik gruplarını temel alabilir ve ardından bunları Azure Active Directory ile eşitleyebilirsiniz. Ayrıca, grupları doğrudan Azure Active Directory’de de oluşturabilirsiniz. Bu örnekte **Dizüstü Bilgisayar Kullanıcıları** grubunun üst grubu olarak **ABD Kullanıcı Grubu** kullanılmaktadır.

![Güvenlik Grubu Seç iletişim kutusu](../media/Intune_Planning_Groups_Laptop_small.png)

Bu noktada, grubunuzun hiyerarşisi aşağıdaki ekran görüntüsüne benzer olmalıdır. Artık **Dizüstü Bilgisayar Kullanıcıları** adlı Intune grubunda üyeler bulunduğunu görebilirsiniz. Bu gruba uygulanan tüm ilkeler ABD bölgesindeki KCG dizüstü bilgisayar kullanıcılarına uygulanacaktır.

![Dizüstü Bilgisayar Kullanıcıları grubunun görüntüsü](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Belirli işletim sistemlerine yönelik gruplar
Kuruluşunuza Android, iOS veya Windows gibi belirli işletim sistemlerine uygulanacak ilkeler gerekiyorsa, bu gereksinimi temel alan gruplar oluşturabilirsiniz. Önceki örneklerde olduğu gibi, bunlarda şirket içi Active Directory örneğinizde zaten oluşturmuş olduğunuz işletim sistemine özgü grupları temel alabilir ve bunları Azure Active Directory ile eşitleyebilirsiniz. Ayrıca, bunları doğrudan Azure Active Directory örneğinizde de oluşturabilirsiniz.

Önceki örneklerle aynı yöntemi izleyerek, belirli işletim sistemi platformlarını kullanan kullanıcıların <!--devices?-->ını temel alan gruplar oluşturabilirsiniz.

> [!NOTE]
> Birden çok mobil platform veya işletim sistemi kullanan kullanıcılarınız varsa ve bu kullanıcıları, Android kullanıcıları, iOS kullanıcıları ya da Windows kullanıcıları kategorilerine ayırmak için otomatik bir yönteminiz yoksa ilkeleri cihaz düzeyinde uygulamayı düşünün. Bu size, bir işletim sistemine özgü ilkeleri uygularken daha fazla esneklik getirir.
>
> Cihazın işletim sistemini dinamik olarak temel alan gruplar sağlayamazsınız. Bunu yapmak için Active Directory veya Azure Active Directory güvenlik gruplarını kullanın.

![Dizüstü bilgisayar kullanıcıları grubu](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Tüm kullanıcı gruplarınız kuruluş gereksinimlerinize göre doldurulduktan sonra, grup hiyerarşiniz aşağıdaki gibi görünmelidir:

![Grup hiyerarşisi görünümü](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Kuruluşun ilkelerini uygulamak için bu hiyerarşiyi kullanabilirsiniz.

### <a name="device-groups"></a>Cihaz grupları
Ayrıca KCG senaryosu için, çalışanlara ait tüm cihazları içeren geniş bir grupla başlayarak, burada gösterildiği gibi cihazlar için benzer gruplar oluşturabilirsiniz.

![Grup Oluştur iletişim kutusu](../media/Intune_Planning_Groups_Device_General_small.png)

Grubun tüm KCG cihazlarını içermesi için **Tüm cihazlar (bilgisayarlar ve mobil cihazlar)** öğesini seçtiğinizden emin olun:

![Üyelik ölçütlerini tanımla sayfası](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Girdilerinizi gözden geçirin ve sonra KCG grubunu oluşturmak için **Son**’u seçin.

![Grup Oluştur iletişim kutusu](../media/Intune_Planning_Groups_Device_Summary_small.png)

Kullanıcı grubu hiyerarşisine benzer bir cihaz grubu hiyerarşisi elde edene kadar, cihaz grupları oluşturmaya devam edin. Intune konsolundaki grup düğümünüz şuna benzer görünecektir:

![Intune grupları hiyerarşisi görünümü](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Grup hiyerarşileri ve adlandırma kuralları
İlke yönetimini kolaylaştırmak için her ilkeyi uygulayacağınız amaca, platforma ve kapsama göre adlandırmanız önerilir. İlkelerinizi uygulamak üzere hazırlarken oluşturduğunuz grup yapısına uygun bir adlandırma standardı kullanın.

Örneğin, ABD’de bölgesel düzeyde şirkete ait tüm Android mobil cihazlara uygulanan bir Android ilkesini **Şti_ABD_Mob_Android_Genel** olarak adlandırabilirsiniz.

![Android için ilke oluşturma](../media/Intune_planning_policy_android_small.png)

İlkelerinizi bu şekilde adlandırdığınızda, ilkeleri, bunların kullanım amacını ve kapsamını **İlkeler** düğümünde aşağıda gösterildiği gibi hızla belirleyebilirsiniz:

![Intune ilke listesi](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Sonraki adımlar
[Grup oluşturma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

