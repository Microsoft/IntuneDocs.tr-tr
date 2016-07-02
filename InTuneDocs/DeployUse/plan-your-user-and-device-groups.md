---
title: "Kullanıcı ve cihaz gruplarınızı planlama | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 82ab2dbfada6c0745195da149d5f0dc1948ceb92
ms.openlocfilehash: e89d8384532b994d810649fc07c698237e2f3cec


---

# Kullanıcı ve cihaz gruplarınızı planlama
Intune hizmetindeki gruplar, cihazları ve kullanıcıları yönetmek için büyük esneklik sağlar. Grupları, kuruluş gereksinimlerinize uyacak şekilde aşağıdaki ölçütlere göre ayarlayabilirsiniz:

- coğrafi konum
- bölüm
- donanım özellikleri
- işletim sistemi
- cihazın kullanıcıya mı yoksa şirkete mi ait olduğu


## Intune grupları nasıl çalışır


Intune yönetim konsolundaki Gruplar düğümünün varsayılan görünümü şu şekildedir:

![Intune konsolundaki Gruplar düğümü varsayılan görünümünün ekran görüntüsü](/intune/media/Intune_Planning_Groups_Default_small.png)

İlkeler gruplara dağıtılır, bu nedenle grup hiyerarşisi temel tasarım konularınızdan biridir. Ayrıca, grup oluşturulduktan sonra grubun üst grubu değiştirilemez, bu nedenle gruplarınızın tasarımı Intune hizmetini kullanmaya başladığınız andan itibaren çok önemlidir. Kuruluş gereksinimlerinize göre bir grup hiyerarşisi tasarlamaya yönelik önerilen yöntemlerin bazıları aşağıda açıklanmıştır.

## Grup üyeliği kuralları

1. Bir grup kullanıcılar veya cihazları içerebilir ancak ikisini birden içeremez.

    * **Cihaz grupları** : Bu hem bilgisayarları hem de mobil cihazları içerir. Bir gruba bir bilgisayar ekleyebilmeniz için önce kaydedilmesi gerekir. Bir gruba bir mobil cihaz ekleyebilmeniz için ortamınızın mobil cihazları desteklemek için yapılandırılması ve cihazların kaydedilmesi veya Exchange ActiveSync'ten bulunması gerekir.

    * **Kullanıcı grupları:** Bir grup, Active Directory'den eşitlediğiniz gruplar olan güvenlik gruplarından kullanıcılar içerebilir. Active Directory eşitlemesi kullanmıyorsanız, bu grupları el ile oluşturabilirsiniz.

2. Bir cihaz veya kullanıcı birden fazla gruba ait olabilir.

3. Bir grup aşağıdaki üyelik kurallarına göre üyeleri dahil edebiler veya hariç tutabilir:

    * **Ölçüt Üyeliği:** Bunlar üyeleri dahil etmek veya hariç tutmak için Intune tarafından çalıştırılan dinamik kurallardır. Bu ölçütler yerel Active Directory'nizden (AD) eşitlenen **güvenlik gruplarını** ve diğer bilgileri kullanır. Güvenlik grubu veya veriler değişirse, AD ile eşitleme yaptığınızda grup üyelikleri de değişir.

    * **Doğrudan Üyelik:** Bunlar üyeleri açıkça dahil eden veya hariç tutan statik kurallardır. Üye listesi statiktir.

4. Kullanıcı veya bilgisayarları içeren kullanıcı grupları veya cihaz grupları oluşturmak için Active Directory Etki Alanı Hizmetleri (AD DS) gerekli değildir, ancak cihaz gruplarına mobil cihazları eklemek için ortamınızın mobil cihazları desteklemek için yapılandırılması gerekir.

    Ayrıca, cihazlar bulunmalı ve Intune’a eklenmelidir.

## Grup ilişkisi kuralları

1. Oluşturduğunuz her grubun bir üst grubu olmalıdır ve bir grubu oluşturulduktan sonra grubun üst grubunu değiştiremezsiniz.

2. Kullanıcıları veya cihazları bir alt gruba eklediğinizde:

    * Alt gruplar her zaman üst grubun alt kümeleridir.

    * Bir alt gruba eklediğiniz yeni üyeler otomatik olarak grubun üst grubuna eklenir.

    * Üst gruptan hariç tutulan bir üyeyi bir alt gruba ekleyemezsiniz.

3. Üst grubun üyeliği alt grup için kullanılabilir üyeliği tanımlar.

4. Bir üst grubu sildiğinizde, tüm alt grupları silinir.

5. Alt gruplara dağıtımı hariç tutarak bir üst gruba içerik ve ilke dağıtabilirsiniz.

6. Belirli bir kullanıcı veya cihazı üst grubun bir üyesi olmayan bir alt gruba ekleyebilirsiniz. Bunu yaparsanız, yeni grup üyesi üst gruba eklenir.

    Ancak, üyeyi üst gruptan hariç tutulan bir alt gruba ekleyemezsiniz.

7. Grup üyeliği yinelemelidir. Örneğin:

    * **Pat** yalnızca **Dizüstü Kullanıcıları** güvenlik grubunun üyesidir.

    *  **Dizüstü Kullanıcıları** grubu **Onaylanan Kullanıcılar** güvenlik grubunun üyesidir.

    * Intune’da dinamik üyelik sorgusu kullanan ve **Onaylanan Kullanıcılar** grubunun üyelerini içeren bir grup oluşturursunuz. Sonuç olarak, Intune kullanıcı grubunuz **Pat**’i içerir.

> [!TIP]
> Gruplarınızı oluştururken, ilkeyi nasıl uygulayacağınızı düşünün. Örneğin, işletim sistemlerine özgü ilkeleriniz ve kuruluşunuzdaki farklı rollere veya Active Directory’de önceden tanımladığınız Kurumsal Birimlere özgü ilkeleriniz olabilir. iOS, Android ve Windows’a özgü cihaz gruplarının ve her bir kurumsal rol için kullanıcı gruplarının olması yararlı olacaktır.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Yerleşik gruplar
Intune, düzenleyemeyeceğiniz veya silemeyeceğiniz dokuz yerleşik grup sağlar: <!--maybe a screen shot would be best?-->

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
> Sloganınız *basit tut* olsun. Kuruluşunuz aşağıda açıklananlar gibi belirli gereksinimlere sahip değilse basit tutmak ve varsayılan grup yapısı ve ilkeleri kullanarak devam etmek hizmeti uzun vadede daha kolay yönetilebilir hale getirir. Gruba göre küçük farklılıklar dışında kullanıcılarınıza eşit davranmanız mümkünse, bakım daha kolay olacak, böylece daha az ilkeyle çalışacaksınız.


### Kuruluşunuzdaki tüm kullanıcılar ve cihazlar
Kuruluşunuzdaki tüm kullanıcılar ve cihazlar için bir üst grup tanımlayın; büyük olasılıkla tümüne uygulanacak ilkeleriniz vardır. Bu amaçla Intune’daki varsayılan **Tüm Kullanıcılar** ve **Tüm cihazlar** gruplarını kullanabilirsiniz. Cihazları belirtimlerine göre düzenleyen alt gruplar, örneğin kendi cihazını getir (KCG) cihazları için ve şirketin sahip olduğu cihazlar (CO) için olan gruplar, **Tüm Kullanıcılar** ve **Tüm cihazlar** üst gruplarının alt grupları olabilir.

## Kuruluşunuz için grupları özelleştirme

### BYOD ve şirkete ait cihazlar
Kuruluşunuzda çalışanların kendi cihazlarını iş için kullanmalarına (KCG) izin veriliyorsa, şirketin sahip olduğu cihazlar (CO) sağlanıyorsa veya her ikisinin bir birleşimi geçerliyse, bu iki cihaz kategorisini temel alan ilkeler uygulamanızı öneririz.

KCG veya karma kullanım durumlarında, gizlilikle ilgili yerel yasal düzenlemeleri ihlal etmeyen ilkeler planlamaya özen gösterin. Kendi cihazlarını getirecek tüm kullanıcılar için bir üst grup oluşturun. Bu grup bu kategorideki tüm kullanıcılar için geçerli olan ilkeleri uygulamak için kullanılabilir.

![KCG üst grubu oluşturma işleminin ekran görüntüsü](/intune/media/Intune_Planning_Groups_BYOD_small.png)

Benzer şekilde, kuruluşunuzdaki CO kullanıcıları için de bir grup oluşturabilirsiniz:

![KCG ve CO için eşdüzey kullanıcı gruplarının ekran görüntüsü](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Coğrafi bölgeler için gruplar
Kuruluşunuz özel bölgeler için ilkelere ihtiyaç duyarsa, coğrafi bölgeyi temel alan gruplar oluşturabilirsiniz. Bunlar için, zaten Active Directory’de (AD) oluşturmuş olduğunuz bölgesel grupları temel alabilir ve bunları Azure AD’ye eşitleyebilirsiniz. Ayrıca bu grupları doğrudan Azure AD’de de oluşturabilirsiniz.

Bu ekran görüntüleri, şirket içi AD’den eşitlenen gruplara göre Intune grupları oluşturmayı gösterir. Bu örnekte **ABD Kullanıcı Grubu** adlı bir AD güvenlik grubuna sahip olduğunuz varsayılır.

1. İlk olarak genel bilgileri sağlayın.

![Grubu Düzenle alanının ekran görüntüsü](/intune/media/Intune_Planning_Groups_AD_General_small.png)

Üyelik ölçütleri altında, Üyelik kurallarına göre kullanılacak güvenlik grubu için AD’den eşitlenen **ABD Kullanıcı Grubu**’nu seçin.

![Grubu düzenle iletişim kutusu](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Gözden geçirin ve ardından **Son**’u seçerek grubu oluşturmayı tamamlayın.

![Grubu düzenle iletişim kutusu](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

Örneğimizde MEA adlı bir Orta Doğu ve Asya grubu da oluşturulmuştur.

> [!NOTE]
> Grup üyeliği güvenlik grubu üyeliğine göre doldurulmazsa bu üyelere Intune lisansları atayıp atamadığınızı denetleyin.

### Belirli donanımlara yönelik gruplar
Kuruluşunuzda belirli donanım türlerine uygulanacak ilkeler gerekiyorsa, bu gereksinimi temel alan gruplar oluşturabilirsiniz. Bunları, şirket içi AD’nizde önceden oluşturmuş olduğunuz belirli gruplara dayandırabilir ve Azure AD’ye eşitleyebilirsiniz. Ayrıca bu grupları doğrudan Azure AD’de de oluşturabilirsiniz. Bu örnekte **Dizüstü Bilgisayar Kullanıcıları** grubunun üst grubu olarak **ABD Kullanıcı Grubu** kullanılmaktadır.

![Güvenlik grubu seç iletişim kutusu](/intune/media/Intune_Planning_Groups_Laptop_small.png)

Bu noktada, grup hiyerarşisi aşağıda gösterildiği gibi görünmelidir. Gördüğünüz gibi artık **Dizüstü Bilgisayar Kullanıcıları** adlı Intune grubunda üyeler vardır. Bu gruba uygulanan tüm ilkeler şimdi ABD bölgesindeki KCG dizüstü bilgisayar kullanıcılarına uygulanacaktır.

![Dizüstü Bilgisayar Kullanıcıları grubunun görüntüsü](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Belirli işletim sistemlerine yönelik gruplar
Kuruluşunuzda Android, iOS veya Windows gibi belirli işletim sistemlerine uygulanacak ilkeler gerekiyorsa, bu gereksinimi temel alan gruplar oluşturabilirsiniz. Önceki örneklerde olduğu gibi, bunları şirket içi AD’nizde önceden oluşturmuş olduğunuz belirli gruplara dayandırabilir ve Azure AD’ye eşitleyebilirsiniz. Ayrıca, bu grupları doğrudan Azure AD’de de oluşturabilirsiniz.

Önceki örneklerle aynı yöntemi izleyerek, belirli işletim sistemi platformlarını kullanan kullanıcıların <!--devices?--> temel alındığı gruplar oluşturabiliriz.

> [!NOTE]
> Birden çok mobil platform/işletim sistemi kullanan kullanıcılarınız varsa ve kullanıcıları ve Android kullanıcıları, iOS kullanıcıları ya da Windows kullanıcıları kategorilerine ayırmak için otomatik bir yönteminiz yoksa ilkeleri işletim sistemine özel ilke uygulamada daha fazla esneklik sağlayan cihaz düzeyinde uygulamayı düşünün.
>
> Cihazın işletim sistemini dinamik olarak temel alan gruplar sağlayamazsınız. Bunu yapmak için AD veya AAD güvenlik gruplarını kullanın.

![Dizüstü bilgisayar kullanıcıları grubunun görüntüsü](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Tüm Kullanıcı gruplarınız bu kuruluş gereksinimlerine göre doldurulduktan sonra, grup hiyerarşiniz aşağıdaki gibi görünmelidir:

![Grup hiyerarşisi görünümü](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Bu hiyerarşi kuruluşun ilkelerini uygun şekilde uygulamak için kullanılabilir.

### Cihaz grupları
Ayrıca KCG senaryosu için, çalışanlara ait tüm cihazları içeren geniş bir grupla başlayarak, aşağıda gösterildiği gibi cihazlar için benzer gruplar oluşturabilirsiniz:

![Grup Oluştur iletişim kutusu](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Grubun tüm BYO cihazlarını içermesi için **Tüm cihazlar (bilgisayarlar ve mobil)** öğesini seçtiğinizden emin olun:

![Üyelik ölçütlerini tanımla sayfası](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Gözden geçirin ve **Son**’u seçerek KCG grubu oluşturmayı tamamlayın.

![Grup oluştur iletişim kutusu](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Kullanıcı grubu hiyerarşisine benzer bir cihaz grubu hiyerarşisi elde edene kadar cihaz grupları oluşturmaya devam edin. Bu durumda Intune konsolundaki grup düğümünüz şuna benzer görünmelidir:

![Intune grupları hiyerarşisi görünümü](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Grup hiyerarşileri ve adlandırma kuralları
İlke yönetimini kolaylaştırmak için her ilkeyi uygulandığı amaca, platforma ve kapsama göre adlandırmanız önerilir. Bu adlandırma standardı, ilkelerinizi uygulamaya hazırlanırken oluşturduğunuz grup yapısına uygun olmalıdır.

Örneğin, ABD’de, bölgesel düzeyde şirkete ait tüm Android mobil cihazlara uygulanan bir Android ilkesi şu şekilde adlandırılabilir: **CO_US_Mob_Android_General**.

![Android için ilke oluşturma](/intune/media/Intune_planning_policy_android_small.png)

İlkeleri bu şekilde adlandırarak ilkeleri, kullanım amacını ve kapsamını aşağıda gösterildiği gibi konsolun ilkeler düğümünden hızla tanımlayabilirsiniz:

![Intune ilke listesi](/intune/media/Intune_planning_policy_view_small.png)

## Sonraki adımlar
[Grup oluşturma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


