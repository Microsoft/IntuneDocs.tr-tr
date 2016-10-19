---
title: "Kullanıcı ve cihazları yönetmek için grupları kullanma | Microsoft Intune"
description: "Gruplar çalışma alanını kullanarak grupları oluşturun ve yönetin."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7c680c43b8c9120755ec3c652cf7ec1cbcc3472
ms.openlocfilehash: b13e2ff2f4822d71ef8cff9d835e32b99cb3e4ab


---
# Microsoft Intune’da kullanıcı ve cihazları yönetmek için grupları kullanma

Bu konu, Intune’da grupların nasıl oluşturulacağını açıklar. Ayrıca grupların yönetiminin önümüzdeki aylarda nasıl değişeceğine ilişkin bilgiler sağlar. *Mevcut* grup yönetimi yaklaşımına ilişkin bilgi edinmek için bkz. [Microsoft Intune ile kullanıcı ve cihazları yönetmek için gruplar oluşturma](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune).

## Yakında gruplar için yönetici deneyiminde yapılacak geliştirmeler hakkında bildirim

Enterprise Mobility + Security genelinde tek bir gruplandırma ve hedefleme deneyimi kullanılabilmesine yönelik geri bildirimleriniz temelinde, Intune Gruplarını Azure Active Directory tabanlı Güvenlik Gruplarına dönüştürüyoruz. Bu, Intune ile Azure Active Directory (Azure AD) genelinde grup yönetimini birleştirecektir. Yeni deneyim, hizmetler arasında grupları çoğaltma gereğini ortadan kaldırır ve PowerShell ile Graph kullanarak genişletilebilirlik özelliği sağlar. 

### Bu şu anda beni nasıl etkiler?
Bu değişiklik şu anda sizi etkilemez ama yakında neler olacağını söyleyebiliriz:

-   Eylül’de, aylık hizmet sürümünden sonra sağlanan yeni hesaplar Intune kullanıcı grupları yerine Azure AD güvenlik gruplarını kullanacaktır.   
-   Ekim’de, aylık hizmet sürümünden sonra sağlanan yeni hesaplar hem kullanıcı hem de cihaz tabanlı grupları Azure AD portalında yönetecektir. Mevcut müşterilere herhangi bir etkisi yoktur
-   Kasım’da, Intune ürün ekibi mevcut müşterileri yeni Azure AD tabanlı grup yönetim deneyimine geçirmeye başlayacaktır. Bugün Intune’da olan tüm kullanıcı ve cihaz grupları Azure AD güvenlik gruplarına geçirilecektir. Geçiş işlemi, Kasım’da başlamak üzere partiler halinde yapılacaktır. Gündelik çalışmalarınız üzerindeki etkisini en aza indirmedikçe geçişleri başlatmayacağız ve son kullanıcıyı herhangi bir şekilde etkilemesini beklemiyoruz. Ayrıca, hesabınızın geçişi öncesinde size bildirim de sağlayacağız.


### Yeni grup deneyimine nasıl ve ne zaman geçeceğim?
Geçerli müşteriler bir süre içinde geçirilecektir. Birkaç hafta içinde bu geçişin zamanlamasını son haline getirecek ve daha fazla ayrıntı sağlamak için bu konuyu güncelleştireceğiz. Geçişiniz yapılmadan önce size bildirim sağlanacaktır. Geçişle ilgili endişeleriniz varsa, lütfen [intunegrps@microsoft.com](intunegrps@microsoft.com) adresinden geçiş ekibimizle iletişim kurun.

### Mevcut kullanıcı ve cihaz gruplarıma ne olacak?
 Oluşturduğunuz tüm kullanıcı ve cihaz grupları Azure AD güvenlik gruplarına geçirilecektir. Geçiş yapıldığı sırada Tüm Kullanıcılar grubu gibi varsayılan Intune gruplarını dağıtımlarda kullanıyorsanız, bunlar da geçirilecektir. Bazı gruplarda geçiş işlemi daha karmaşık olabilir ve geçiş için ek adımların gerekli olması durumunda bunu size bildiririz.

### Hangi yeni özelliklerden yararlanabileceğim?
Sağlanacak yeni işlevler şunlardır:

-    Azure AD Güvenlik Grupları, Intune’da tüm dağıtım türleri için desteklenecektir.
-    Azure AD Güvenlik Grupları, cihazların kullanıcılarla birlikte gruplandırılmasını destekleyecektir.
-    Azure AD Güvenlik Grupları, Intune cihaz öznitelikleriyle dinamik grupları destekleyecektir. Örneğin, cihazları iOS gibi bir platform temelinde dinamik olarak gruplandırabileceksiniz. Bu şekilde, kuruluşunuzda yeni bir iOS cihazı kaydedildiğinde, bu cihaz otomatik olarak iOS dinamik cihaz grubuna eklenecektir.
-    Azure AD ve Intune genelinde grup yönetimi için paylaşılan yönetici deneyimleri.
- Intune’daki hizmet yöneticilerinin Azure AD’de grup yönetimi görevlerini gerçekleştirebilmesini sağlamak için, Azure AD’ye *Intune Hizmet Yöneticisi rolü* eklenecektir.




### Hangi Intune işlevleri kullanılamayacaktır?
Grup deneyimi gelişecek olsa da, geçiş sonrasında kullanılamayacak olan bazı Intune işlevleri vardır.

#### Grup yönetimi işlevleri

-   Yeni grup oluşturduğunuzda üyeleri veya grupları hariç tutamayacaksınız. Bununla birlikte Azure AD dinamik grupları, öznitelikleri kullanarak gelişmiş kurallar oluşturmanıza ve ölçütler temelinde üyeleri hariç tutmanıza olanak tanıyacaktır.
-   **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** grupları desteklenmeyecektir. Bu gruplar geçirilmeyecektir.


#### Grup bağımlılığı işlevleri

-   Hizmet Yöneticisi rolünün **Grupları yönetme** izinleri olmayacaktır.
-   Exchange ActiveSync cihazlarını gruplandıramayacaksınız.  **Tüm EAS Yönetilen Cihazları** grubunuz, gruptan bir rapor görünümüne dönüştürülecektir.
-  Raporlarda gruplarla özetleme kullanılamayacaktır.
-  Bildirim kurallarında özel grubu hedefleme özelliği kullanılamayacaktır.

### Bu değişikliğe hazırlanmak için ne yapmalıyım?
 Bu geçişi sizin için kolaylaştıracak önerilerimiz vardır:

- Geçiş öncesinde istemeyen veya gerekmeyen tüm Intune gruplarını temizleyin.
- Gruplarda hariç tutma kullanımınızı değerlendirin ve dışlamayı kullanmanızı gerektirmeyecek şekilde gruplarınızı yeniden tasarlamayı göz önünde bulundurun.
-  Azure AD’de grup oluşturma izinleri olmayan yöneticileriniz varsa, Azure AD yöneticinizden onları **Intune Hizmet Yöneticisi** Azure AD rolüne eklemesini isteyin.


## Microsoft Intune'la kullanıcı ve cihazları yönetmek için gruplar oluşturma

Bu bölümde, Intune yönetim konsolunda Intune gruplarını nasıl oluşturacağınız açıklanır.

Grupları oluşturmak ve yönetmek için, Microsoft Intune yönetim konsolundaki **Gruplar** çalışma alanını kullanın.  **Gruplara Genel Bakış** sayfası dikkat etmeniz gereken sorunları belirlemeniz ve öncelik vermeniz için durum özetleri içerir:

-   Uyarılar
-   Yazılım güncelleştirmeleri
-   Endpoint Protection
-   İlke
-   Yazılım yönetimi

Ayrıca, seçili grubun üyeleri için sorunları tanımlamanıza ve çözmenize yardımcı olmak amacıyla durum özetleriyle birlikte grup hiyerarşiniz de görüntülenir.


> [!TIP]
> Gruplarınızı oluştururken, ilkeyi nasıl uygulayacağınızı göz önünde bulundurun. Örneğin, işletim sistemlerine özgü ilkeleriniz ve kuruluşunuzdaki farklı rollere veya Active Directory’de önceden tanımladığınız Kurumsal Birimlere özgü ilkeleriniz olabilir. iOS, Android ve Windows’a özgü cihaz gruplarının ve her bir kurumsal rol için kullanıcı gruplarının olması yararlı olacaktır.
>
> Büyük ihtimalle şirketinizin temel uyumluluk gereksinimlerini belirlemek için tüm gruplara ve cihazlara uygulanan varsayılan bir ilke oluşturmak istersiniz. Daha sonra, en geniş kullanıcı ve cihaz kategorileri için daha özel ilkler oluşturabilirsiniz; örneğin, cihaz işletim sistemlerinin her biri için e-posta ilkeleri.
>
> İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırmaya dikkat edin. Örneğin, iyi bir açıklayıcı ilke adı **Tüm Şirket için WP E-posta İlkesi**olabilir.
>
> Her kısıtlayıcı ilke oluşturduğunuzda bunu kullanıcılarınıza iletmek istersiniz; bu nedenle daha genel gruplar ve ilkeler oluşturduktan sonra gereksiz iletişimi azaltmak için nasıl daha küçük gruplar oluşturabileceğinize dikkat edin.


## Bir cihaz grubu oluşturma

1.  Intune yönetim konsolunda, **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin.

2.  Grup için bir ad ve isteğe bağlı açıklama sağlayın, üst grup olarak bir cihaz grubunu seçin. **İleri**’yi seçin.

3.   **Üyelik Ölçütlerini Tanımla** sayfasında, grubun içereceği cihaz türünü seçin. Grubu yapılandırmak için ek seçenekler, seçtiğiniz cihaz türüne bağlıdır:

    -   **Bilgisayar:** Üst grubun tüm üyelerinin eklenip eklenmeyeceğini, dahil etmek veya hariç tutmak istediğiniz Kurumsal Birimleri (OU) ve dahil etmek veya hariç tutmak istediğiniz etki alanlarını belirtin. Bilgisayarlar için OU ve etki alanı bilgileri envanterden alınır.

    -   **Mobil:** Yalnızca Intune tarafından yönetilen mobil cihazların, Exchange ActiveSync tarafından yönetilenlerin veya her ikisini de dahil edileceğini belirtin.

    -   **Tüm cihazlar:** Bu seçenek, ölçütlere dayalı özel durumlar olmadan tüm cihazları içerir.

4.   **Doğrudan Üyeliği Tanımla** sayfasında, **Gözat**'a tıklayarak belirttiğiniz cihazları dahil edin veya hariç tutun. Belirttiğiniz üst grupta olmayan cihazları seçmek için bu seçeneği kullanırsanız, bu cihazlar otomatik olarak üst gruba eklenir.


5.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin. **Son**’u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Gruplar** listesinde, üst grubun altında bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

## Bir kullanıcı grubu oluşturma

1.  Intune yönetim konsolunda, **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin.

2.  Grup için bir ad ve isteğe bağlı açıklama sağlayın, üst grup olarak bir kullanıcı grubunu seçin. **İleri**’yi seçin.

3.   **Üyelik Ölçütlerini Tanımla** sayfasında, bir üst grubun tüm üyelerini eklemeyi veya boş bir grupla başlamayı belirtin.  [Office 365 yönetici merkezinde](http://go.microsoft.com/fwlink/?LinkId=698854) el ile yapılandırdığınız veya yerel Active Directory'nizden eşitlediğiniz **Güvenlik gruplarını** temel alarak üyeleri dahil edebilir veya hariç tutabilirsiniz. Bir güvenlik grubunun üyeliği değişirse, bu güvenlik grubunu temel alan kullanıcı gruplarının üyeliği de değişebilir.

    > [!IMPORTANT]
    > Şu anda, grubunuz belirli güvenli veya yönetici gruplarından üyeler içeriyorsa ve belirli grupların üyelerini de hariç tutuyorsanız, başlangıçta dahil ettiğiniz üyeler kaldırılır. Hem dahil edilen hem de hariç tutulan üyelerin bulunduğu bir grup oluşturmak için, ilk olarak dahil edilen üyelerle bir üst grup oluşturmanızı ve ardından bu grubun altında hariç tutulan üyeleri listelediğiniz bir alt grup oluşturmanızı öneririz. Bundan sonra, söz konusu alt grubu Intune ilkeleri, profilleri ve uygulama dağıtım için uygun şekilde kullanabilirsiniz.

    > [!NOTE]
    > Azure Yönetim Portalı’nda, kullanıcıların raporladığı yöneticiyi temel alan bir grup oluşturabilirsiniz. Bu dinamik bir grup olur; Azure Active Directory’de söz konusu yöneticinin ekibinde çalışanlar eklendikçe veya kaldırıldıkça değişir. Yöneticiyi temel alan bir Azure grubu oluşturma yordamı, [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) altındaki **Grubu bir “Yönetici” grubu olarak yapılandırmak için** başlıklı bölümde açıklanır.


4.   **Doğrudan Üyeliği Tanımla** sayfasında, **Gözat**'a tıklayarak belirttiğiniz kullanıcıları dahil edin veya hariç tutun. Belirttiğiniz üst grupta olmayan kullanıcıları seçmek için bu seçeneği kullanırsanız, bu cihazlar otomatik olarak üst gruba eklenir. **Üyeleri Seçin** iletişim kutusunun alt kısmında kullanıcıyı el ile ekleme seçeneğini bulacaksınız. Henüz kayıtlı cihazı olmayan bir kullanıcıyı eklemek isterseniz, bu seçenek yararlı olur.


5.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin. **Son**’u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Gruplar** listesinde, üst grubun altında bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

> [!TIP]
> Güvenlik grupları, kullanıcı gruplarını doldurmak için mükemmel bir kaynaktır. Güvenlik gruplarınız kimlerin hangi kaynaklara erişiminin olacağını tanımladığından bu, Intune kullanıcı grupları anlamına gelebilir. Active Directory’den Azure Active Directory’ye eşitlenen veya Office 365 yönetici merkezi ya da Azure Yönetimi portalı aracılığıyla doğrudan Azure Active Directory’de oluşturulan tüm güvenlik gruplarını Intune’da kullanıcı grubu oluşturmak için kullanabilirsiniz.

## Görünümleri yönetici rollerine uyarlama
Filtrelenmiş grup görünümleri, yöneticilerin görebileceği görünümü onun rolüne göre uyarlamanıza ve her BT yöneticisinin yönetebileceği grupları kısıtlamanıza olanak tanır. Bu aşağıdaki durumlarda kullanışlı olabilir:

-   BT yöneticilerinizin yalnızca belirli kullanıcı ve cihazlara öğe dağıtabilmesi gerekiyorsa.

-   Her BT yöneticisine yalnızca ilgili grupları göstermek istiyorsanız.

Intune yönetici konsolunda hizmet yöneticileri için filtrelenen grup görünümlerini yapılandırabilirsiniz. Ayrıntılar için bkz. [Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Bir hizmet yöneticisi için filtrelenen grup görünümlerini yapılandırdığınızda, o yönetici:

-   Yazılım veya ilke dağıtırken ya da raporları kullanırken yalnızca belirttiğiniz grupları görüntüleyebilir ve seçebilir

-   Yönetim konsolunun aşağıdaki sayfalarındaki durum bilgilerini almaz:

    -   **Sisteme Genel Bakış**

    -   **Gruplara Genel Bakış**

    -   **Endpoint Protection'a Genel Bakış**

    -   **Uyarılara Genel Bakış**

    -   **Yazılıma Genel Bakış**

    -   **İlkeye Genel Bakış**

### Filtrelenen grup görünümlerini yapılandırma

1.  Intune yönetim konsolunda, **Yönetici** &gt; **Yönetici Yönetimi** &gt; **Hizmet Yöneticileri**’ni seçin.

2.  Grupları filtrelemek istediğiniz hizmet yöneticisini seçin ve ardından **Grupları Yönet**'e tıklayın.

3.   **Bu hizmet yöneticisi için görünür olacak grupları seçin** iletişim kutusunda, seçili hizmet yöneticisinin erişebileceği grupları ekleyin ve ardından **Tamam**'a tıklayın.

Filtrelenen grup görünümlerini yapılandırdıktan sonra, BT yöneticisi yalnızca seçtiğiniz grupları görebilir ve seçebilir.

## Gruplarınızı yönetme
Gruplarınızı oluşturduktan sonra, bunları kuruluşunuzun gereksinimlerine göre yönetmeye devam edersiniz.

Adını, açıklamasını ve gruba ait olan kişileri değiştirmek için grubunuzu düzenleyebilirsiniz.

Artık kuruluşunuzun gereksinimlerine hizmet etmeyen bir grubu silebilirsiniz. Grup silindiğinde, o gruba ait kullanıcılar silinmez.

## Sonraki adımlar

### Tasarımınızı denetleme
Gruplarınızı ve ilkelerinizi ayarladıktan sonra, **Amaçlanan Değer** ve **Durum** bilgilerini gözden geçirerek tasarımınızın pratik çıkarımlarını denetleyin.

1. Bir cihaz grubundan herhangi bir cihaz seçin ve ekranın en üstündeki bilgi kategorileri arasında gezinin.
2.  **İlke** ‘yi seçin. Android cihazının ilke ayarlarının bu ekran görüntüsüne benzer bir şey görürsünüz.

![Örnek iOS ayarları ilkesi](../media/Intune-Device-Policy-v.2.jpg)

Her ilkenin bir **Amaçlanan Değer** ‘i ve bir de **Durum**‘u vardır. Amaçlanan değer, ilkeyi atarken ne elde etmek istediğinizi belirtir. Durum, cihaza uygulanan tüm ilkeler ve donanım ve işletim sistemi kısıtlamaları ve gereksinimleri birlikte değerlendirildiğinde gerçekten elde ettiğiniz şeydir.  Ekran görüntüsünde iki net örnek görebilirsiniz:

-   **Amaçlanan Değer** sütununda gösterildiği gibi **Basit parolalara izin ver**, **Evet** olarak ayarlanmış, ancak **Durum** ‘u **Uygulanamaz**‘dır. Bunu nedeni, Android cihazlar için basit parolaların desteklenmemesidir.

-   Benzer şekilde, bu cihaz bir Android cihazı olduğundan **iOS cihazları için e-posta ayarları** genişletilmiş ilke öğesi bu cihaza uygulanmaz.

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, gerçekte daha kısıtlayıcı olan ilkenin uygulanacağını unutmayın.



<!--HONumber=Aug16_HO4-->


