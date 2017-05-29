---
title: "Azure Active Directory gruplarına geçme | Microsoft Docs"
description: "Gruplarınızı Intune’dan Azure AD’ye geçirme"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2296490a8c3984e79eeeb553d90591048ed46711
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="a-new-way-of-using-groups-in-intune"></a>Intune'da grupları kullanmanın yeni bir yolu

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Geri bildirimlerinizi aldık ve Microsoft Intune’da gruplarla çalışma konusunda bazı değişiklikler yapıyoruz.
Tüm müşterilerimizin Intune gruplarını Azure Active Directory güvenlik gruplarına geçirme aşamasındayız.

Bunun yararı, aynı grup deneyimini tüm Enterprise Mobility + Security ve Azure AD uygulamalarında kullanabilecek olmanızdır. Ayrıca, bu yeni işlevi genişletmek ve özelleştirmek için PowerShell ve Grafik API’si kullanmanız mümkün olacaktır.

Azure AD güvenlik grupları hem kullanıcılara hem de cihazlara tüm Intune dağıtımı türlerini destekler. Ayrıca, sağladığınız özniteliklere bağlı olarak otomatik güncelleştirilen Azure AD dinamik gruplarını kullanabilirsiniz. Örneğin, iOS 9 çalıştıran cihazlardan bir grup oluşturabilirsiniz. iOS 9 çalıştıran yeni bir cihaz kaydedildiğinde dinamik gruba otomatik olarak eklenir.

## <a name="when-is-this-happening"></a>Bu ne zaman gerçekleşecek?

Geçiş işlemi şu anda yapılıyor. Geçişiniz yapılmadan önce size bildirilecektir.
Geçişiniz zaten yapıldıysa gruplara klasik Intune konsolundan erişmeyi denediğinizde şuna benzer bir ileti görürsünüz:

![Grupları gösterme iletisi geçirildi.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>Neler kullanılamayacak?

Intune gruplarının varolan bazı özellikleri Azure AD'de kullanılamaz:

- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** Intune grupları geçirilmeyecektir.
- Şu anda Intune konsolunda bulunan bir gruptan **Belirli üyeleri hariç tut** seçeneği Azure portalında bulunmamaktadır. Ancak bu davranışı çoğaltmak için gelişmiş kurallarla birlikte bir Azure AD güvenlik grubu kullanabilirsiniz. Örneğin, Satış departmanınızda çalışan ancak unvanında “Asistan” kelimesi bulunmayan herkesi bir güvenlik grubuna dahil eden gelişmiş bir kural oluşturabilirsiniz; bunu şu gelişmiş kuralı kullanarak yapabilirsiniz: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Intune konsolunda yerleşik olan **Tüm Exchange ActiveSync Tarafından Yönetilen Cihazlar** grubu Azure AD’ye geçirilmeyecektir. Ancak EAS tarafından yönetilen cihazlar hakkındaki bilgilere Azure portalından erişmeye devam edebilirsiniz.
- Klasik Intune konsolunda raporlara gruplara göre filtre uygulamanız mümkün olmayacaktır.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Nasıl hazırlanmalı?

- Azure AD güvenlik grupları ve nasıl çalıştıkları hakkında bilgi edinmek için aşağıdaki Azure AD konularını okuyun:
    -  [Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Azure Active Directory'de grupları yönetme](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Geçişten önce artık kullanmadığınız tüm Intune gruplarını kaldırabilirsiniz.
-  Grup oluşturması gereken tüm yöneticilerin **Intune Hizmet Yöneticisi** Azure AD rolüne eklendiğinden emin olun. Azure AD Hizmet Yöneticisi rolünün **Grubu Yönet** izinlerine sahip olmadığını unutmayın.
-  Grupları **Belirli üyeleri hariç tut** seçeneği ile kullanırsanız bu grupları hariç tutma işlemine gerek kalmayacak şekilde yeniden tasarlayıp tasarlayamayacağınızı veya aynı sonuca ulaşmak için Azure AD sorgunuzda gelişmiş kurallar kullanıp kullanamayacağınızı düşünün.


## <a name="what-happens-to-intune-groups"></a>Intune gruplarına ne olur?

| Intune'da Gruplar|Azure AD’de Gruplar|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statik kullanıcı grubu|Statik Azure AD güvenlik grubu|
|Dinamik kullanıcı grubu|Bir Azure AD güvenlik grubu hiyerarşisi ile statik Azure AD güvenlik grupları|
|Statik cihaz grubu|Statik Azure AD güvenlik grubu|
|Dinamik cihaz grubu|Dinamik Azure AD güvenlik grubu|
|Dahil etme koşullu bir grup|Intune’da dahil etme koşulundan herhangi bir statik veya dinamik üye içeren Statik Azure AD güvenlik grubu.|
|Dışlama koşullu bir grup|Geçirilmez|
|Yerleşik gruplar, **Tüm Kullanıcılar**, **Gruplanmamış Kullanıcılar**, **Tüm Cihazlar**, **Gruplanmamış cihazlar**, **Tüm Bilgisayarlar**, **Tüm Mobil Cihazlar**, **Tüm MDM ile yönetilen cihazlar** ve **Tüm EAS ile yönetilen cihazlar**|Azure AD güvenlik grupları.|

Intune’da tüm grupların bir üst grubu olması gerekir. Gruplar yalnızca üst gruplarından üyeler içerebilir. Azure AD’de alt gruplar üst grupların sahip olmadığı üyeler içerebilir.

Öznitelikler, grupları tanımlamak için kullanılabilen cihaz özellikleridir. Bu tablo, bu ölçütlerin Azure AD güvenlik gruplarına nasıl geçirileceğini açıklar.

| Intune'da Öznitelik|Azure AD’de Öznitelik|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Cihaz grupları için Kuruluş Birimi (OU) özniteliği|Dinamik gruplar için OU özniteliği.|
|Cihaz grupları için etki alanı adı özniteliği|Dinamik gruplar için Etki Alanı Adı özniteliği.|
|Kullanıcı grupları için bir öznitelik olarak güvenlik grubu|Azure AD dinamik sorgularda gruplar öznitelik olarak kullanılamaz. Dinamik gruplar yalnızca kullanıcı veya cihaza özel öznitelikler içerebilir.|
|Kullanıcı grupları için yönetici özniteliği|Dinamik gruplarda *yönetici* özniteliği için Gelişmiş Kural|
|Üst kullanıcı grubundan tüm kullanıcılar|O grubun üye olduğu statik grup|
|Üst cihaz grubundaki tüm mobil cihazlar|O grubun üye olduğu statik grup|
|Intune tarafından yönetilen tüm mobil cihazlar|Dinamik grup için değer olarak ‘MDM’ ile Yönetim Türü özniteliği|
|Statik gruplar içinde iç içe geçmiş gruplar |Statik gruplar içinde iç içe geçmiş gruplar|
|Dinamik gruplar içinde iç içe geçmiş gruplar|Bir iç içe geçme düzeyine sahip dinamik grup|

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>Zaten dağıtmış olduğunuz ilkelere ve uygulamalara ne olur?

İlkeler ve uygulamalar daha önce olduğu gibi gruplara dağıtılmaya devam edilecektir. Ancak artık bu grupları klasik Intune konsolu yerine Azure portalından yöneteceksiniz.
 

