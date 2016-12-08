---
title: "Azure Active Directory gruplarına geçme | Microsoft Intune"
description: "Gruplarınızı Intune’dan Azure AD’ye geçirme"
keywords: 
author: Mtillman
ms.author: mtillman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: e14bbadc4293b7b963197b35704a7170e4fc29e8


---

## <a name="the-new-admin-experience-for-groups"></a>Gruplar için yeni yönetici deneyimi
    
Enterprise Mobility ve Security genelinde tek bir gruplandırma ve hedefleme deneyimi kullanılabilmesine yönelik geri bildirimleriniz temelinde, Intune Gruplarını Azure Active Directory tabanlı Güvenlik Gruplarına dönüştürüyoruz. Bu, Intune ile Azure Active Directory (Azure AD) genelinde grup yönetimini birleştirecektir. Yeni deneyim, hizmetler arasında grupları çoğaltma gereğini ortadan kaldırır ve PowerShell ile Graph kullanarak genişletilebilirlik özelliği sağlar. 

### <a name="how-and-when-will-i-migrate-to-the-new-groups-experience"></a>Yeni grup deneyimine nasıl ve ne zaman geçeceğim?
Geçerli müşteriler Aralık 2016’dan önce olmamak kaydıyla bir zaman dilimi içinde geçirilecektir. Grupların geçişi yapılmadan önce size bildirim sağlanacaktır. Geçişle ilgili endişeleriniz varsa, lütfen [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com) adresinden geçiş ekibimize başvurun.

### <a name="what-new-features-will-be-available-to-me"></a>Hangi yeni özelliklerden yararlanabileceğim?
Sağlanacak yeni işlevler şunlardır: 
 
-    Azure AD Güvenlik Grupları, Intune’da tüm dağıtım türleri için desteklenecektir. 
-    Azure AD Güvenlik Grupları, cihazların kullanıcılarla birlikte gruplandırılmasını destekleyecektir.
-    Azure AD Güvenlik Grupları, Intune cihaz öznitelikleriyle dinamik grupları destekleyecektir. Örneğin, cihazları iOS gibi bir platform temelinde dinamik olarak gruplandırabileceksiniz. Bu şekilde, kuruluşunuzda yeni bir iOS cihazı kaydedildiğinde, bu cihaz otomatik olarak iOS dinamik cihaz grubuna eklenecektir.
-    Azure AD ve Intune genelinde grup yönetimi için paylaşılan yönetici deneyimleri.
- Intune’daki hizmet yöneticilerinin Azure AD’de grup yönetimi görevlerini gerçekleştirebilmesini sağlamak için, Azure AD’ye *Intune Hizmet Yöneticisi rolü* eklenecektir.

 
### <a name="what-intune-functionality-wont-be-available"></a>Hangi Intune işlevleri kullanılamayacaktır?
Grup deneyimi gelişecek olsa da, geçiş sonrasında kullanılamayacak olan bazı Intune işlevleri vardır.

#### <a name="group-management-functionality"></a>Grup yönetimi işlevleri

-   Yeni grup oluşturduğunuzda üyeleri veya grupları hariç tutamayacaksınız. Bununla birlikte Azure AD dinamik grupları, öznitelikleri kullanarak gelişmiş kurallar oluşturmanıza ve ölçütler temelinde üyeleri dışlamanıza olanak tanıyacaktır. Örneğin, Satış departmanınızda çalışan ancak unvanında “Asistan” kelimesi bulunmayan herkesi bir güvenlik grubuna dahil eden gelişmiş bir kural oluşturabilirsiniz; bunu şu gelişmiş kuralla yapabilirsiniz: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Daha fazla bilgi için bkz. [Gelişmiş kurallar oluşturmak için öznitelik kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** grupları desteklenmeyecektir. Bu gruplar geçirilmeyecektir.

#### <a name="group-dependent-functionality"></a>Grup bağımlılığı işlevleri

-   Hizmet Yöneticisi rolünün **Grupları yönetme** izinleri olmayacaktır.
-   Exchange ActiveSync cihazlarını gruplandıramayacaksınız.  **Tüm EAS Yönetilen Cihazları** grubunuz, gruptan bir rapor görünümüne dönüştürülecektir.
-  Raporlarda gruplarla özetleme kullanılamayacaktır.
-  Bildirim kurallarında özel grubu hedefleme özelliği kullanılamayacaktır.

### <a name="what-should-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmalıyım?
 Bu geçişi sizin için kolaylaştıracak önerilerimiz vardır:
 
- Geçiş öncesinde istemeyen veya gerekmeyen tüm Intune gruplarını temizleyin.
- Gruplarınızda dışlamayı nasıl kullandığınızı değerlendirin ve dışlama kullanmamak veya aynı amaçla gelişmiş kuralları kullanabilmek için gruplarınızı nasıl yeniden tasarlayabileceğinizi düşünün.
-  Azure AD’de grup oluşturma izinleri olmayan yöneticileriniz varsa, Azure AD yöneticinizden onları **Intune Hizmet Yöneticisi** Azure AD rolüne eklemesini isteyin.

Ayrıca Azure AD güvenlik grupları hakkında da daha fazla bilgi alabilirsiniz:
-  Genel bir bakış için bkz. [Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Azure AD grupları oluşturma ve yönetme hakkında daha fazla bilgi için bkz. [Azure Active Directory’de grupları yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Güvenlik gruplarına yönelik gelişmiş kurallar hakkında daha fazla bilgi için bkz. [Gelişmiş kurallar oluşturmak için öznitelik kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Azure AD güvenlik grubu belgelerinde cihazlar için grup oluşturmaktan bahsedilmediğini fark edebilirsiniz. Bu özellik, Intune grup geçiş işlemi başlamadan önce Azure AD'de etkinleştirilecektir.

## <a name="migration-details"></a>Geçiş ayrıntıları
Intune gruplarınızın Azure AD güvenlik gruplarına geçişine ilişkin ayrıntılar burada açıklanmaktadır.

### <a name="migration-of-existing-groups"></a>Mevcut grupların geçişi

| Intune grubu...|...Azure AD güvenlik grubu haline geliyor|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Intune ilkesi tarafından hedeflenen statik kullanıcı grupları|Aynı kullanıcıları içeren statik Azure AD güvenlik grupları|
|Intune ilkesi tarafından hedeflenen dinamik kullanıcı grupları|Bir Azure AD güvenlik grubu hiyerarşisi ile statik Azure AD güvenlik grupları|
|Intune ilkesi tarafından hedeflenen statik cihaz grupları|Cihazlar ile statik Azure AD güvenlik grupları|
|Intune ilkesi tarafından hedeflenen cihaz özniteliklerine sahip dinamik cihaz grupları|Cihaz özniteliklerine sahip dinamik Azure AD güvenlik grupları|
|Dahil etme koşullu bir grup|Bir grup + dahil etme koşulunun Intune’da izin verdiği herhangi bir statik/dinamik üye içeren ayrı bir statik Azure AD güvenlik grubu|
|Dışlama koşullu bir grup|...geçirilmeyecektir. Dışlama koşulları Azure AD'de statik grup oluşturulurken desteklenmez. Azure AD'de dinamik bir grup oluşturulurken bir dışlama koşulu kullanılabilir.|
|Intune ilkesinde kullandığınız varsayılan gruplar **Tüm Kullanıcılar**, **Gruplanmamış Kullanıcılar**, **Tüm Cihazlar**, **Gruplanmamış cihazlar**, **Tüm Bilgisayarlar**, **Tüm Mobil Cihazlar**, **Tüm MDM ile yönetilen cihazlar** ve **Tüm EAS ile yönetilen cihazlar**  |Azure AD güvenlik grupları. Kullanılmayan varsayılan grupların, gerektiğinde dinamik gruplar kullanılarak müşteri tarafından oluşturulması gerekir.|

### <a name="changes-in-hierarchical-views"></a>Hiyerarşik görünümlerdeki değişiklikler
Intune’daki Intune Üst-alt ilişkisindeki grupların hiyerarşik görünümü Üst küme-alt küme ilişkisiydi; Azure AD’de durum farklıdır. Alt, üstte olmayan üyelere sahip olabilir. Gruplar da Azure AD'nin doğası gereği döngüsel olabilir: bir üst grup alt grubun altı olabilir.

### <a name="attribute-conversion-during-migration"></a>Geçiş sırasında öznitelik dönüştürme
Öznitelikler, grupları tanımlamak için kullanılabilen cihaz özellikleridir. Bu tablo, bu ölçütlerin Azure AD güvenlik gruplarına nasıl geçirileceğini açıklar.

| Intune özniteliği|Azure AD özniteliği|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Cihaz grupları için Kuruluş Birimi (OU) özniteliği|Dinamik gruplar için OU özniteliği. Öznitelik değerleri, görüntüleme için kiracı bileşenlerinden biri olarak eklenerek kiracıyla ilgili yönetici tarafından kullanılabilir.|
|Cihaz grupları için etki alanı adı özniteliği|Dinamik gruplar için Etki Alanı Adı özniteliği. Öznitelik değerleri, görüntüleme için kiracı bileşenlerinden biri olarak eklenerek kiracıyla ilgili yönetici tarafından kullanılabilir|
|Kullanıcı grupları için bir öznitelik olarak güvenlik grubu|Azure AD dinamik sorgularda gruplar öznitelik olarak kullanılamaz. Dinamik gruplar yalnızca kullanıcı veya cihaza özel öznitelikler içerebilir.|
|Kullanıcı grupları için yönetici özniteliği|Dinamik gruplarda *yönetici* özniteliği için Gelişmiş Kural|
|Üst kullanıcı grubundan tüm kullanıcılar|O grubun üye olduğu statik grup|
|Üst cihaz grubundaki tüm mobil cihazlar|O grubun üye olduğu statik grup|
|Microsoft Intune Doğrudan Yönetim tarafından yönetilen tüm mobil cihazlar|Dinamik grup için değer olarak ‘MDM’ ile Yönetim Türü özniteliği|
|EAS tarafından yönetilen tüm mobil cihazlar|EAS cihazları Azure AD’de gruplanamaz. **Tüm EAS Yönetilen Cihazları** grubunuz, gruptan bir rapor görünümüne dönüştürülecektir.|
|Statik gruplar içinde iç içe geçmiş gruplar |Statik gruplar içinde iç içe geçmiş gruplar|
|Dinamik gruplar içinde iç içe geçmiş gruplar|Bir iç içe geçme düzeyine sahip dinamik grup|


## <a name="migration-of-policies"></a>İlkelerin geçişi
Grup geçişi gerçekleşirken, ilkelerinizi Intune konsolunda yönetmeye devam edeceksiniz. Intune konsolunda, gruplarınızı yöneteceğiniz Azure yönetim konsoluna bir bağlantı olacaktır. İlkeleriniz eski Intune gruplarınıza paralel olarak geçiş yapılan Azure AD güvenlik gruplarına dağıtılmaya devam edecektir.

Intune’un tüm işlevselliği Azure yönetim portalına geçirildiğinde (yaklaşık olarak 2017’nin ilk çeyreği) ilkelerinizi ve gruplarınızı orada yöneteceksiniz.

     
### <a name="see-also"></a>Ayrıca bkz.
[Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Azure Active Directory'de grupları yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Nov16_HO1-->


