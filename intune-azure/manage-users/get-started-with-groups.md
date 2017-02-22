---
title: "Intune Azure Portal önizlemesinde grupları kullanmaya başlama | Microsoft Docs"
description: "Intune Azure Portal önizlemesinde gruplarla ilgili yenilikleri öğrenin"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Grupları kullanmaya başlama

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Geri bildirimlerinizi aldık ve Microsoft Intune’da gruplarla çalışma konusunda bazı değişiklikler yaptık.
Intune’u Azure Portal’dan kullanıyorsanız, Intune gruplarınız Azure Active Directory güvenlik gruplarına geçirilmiştir.

Bunun yararı, aynı grup deneyimini tüm Enterprise Mobility + Security ve Azure AD uygulamalarında kullanabilecek olmanızdır. Ayrıca, bu yeni işlevi genişletmek ve özelleştirmek için PowerShell ve Grafik API’si kullanmanız mümkün olacaktır.

Azure AD güvenlik grupları hem kullanıcılara hem de cihazlara tüm Intune dağıtımı türlerini destekler. Ayrıca, sağladığınız özniteliklere bağlı olarak otomatik güncelleştirilen Azure AD dinamik gruplarını kullanabilirsiniz. Örneğin, iOS 9 çalıştıran cihazlardan bir grup oluşturabilirsiniz. iOS 9 çalıştıran yeni bir cihaz kaydedildiğinde dinamik gruba otomatik olarak eklenir.

## <a name="what-is-not-available"></a>Neler kullanılamıyor?

Intune gruplarının daha önce kullanıyor olabileceğiniz bazı özellikleri Azure AD’de kullanılamıyor:

- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** Intune grupları artık yoktur.
- Bir gruptan **Belirli üyeleri hariç tut** seçeneği Azure Portal’da bulunmamaktadır. Ancak bu davranışı çoğaltmak için gelişmiş kurallarla birlikte bir Azure AD güvenlik grubu kullanabilirsiniz. Örneğin, Satış departmanınızda çalışan ancak unvanında “Asistan” kelimesi bulunmayan herkesi bir güvenlik grubuna dahil eden gelişmiş bir kural oluşturabilirsiniz; bunu şu gelişmiş kuralı kullanarak yapabilirsiniz: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Intune konsolunda yerleşik olan **Tüm Exchange ActiveSync Tarafından Yönetilen Cihazlar** grubu Azure AD’ye geçirilmemiştir. Ancak EAS tarafından yönetilen cihazlar hakkındaki bilgilere Azure portalından erişmeye devam edebilirsiniz.


## <a name="how-to-get-started"></a>Nereden başlayacaksınız?

- Azure AD güvenlik grupları ve nasıl çalıştıkları hakkında bilgi edinmek için aşağıdaki Azure AD konularını okuyun:
    -  [Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Azure Active Directory'de grupları yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Grup oluşturması gereken tüm yöneticilerin **Intune Hizmet Yöneticisi** Azure AD rolüne eklendiğinden emin olun. Azure AD Hizmet Yöneticisi rolünün **Grubu Yönet** izinlerine sahip olmadığını unutmayın.
-  Grupları **Belirli üyeleri hariç tut** seçeneği ile kullandıysanız, bu grupları hariç tutma işlemine gerek kalmayacak şekilde yeniden tasarlayıp tasarlayamayacağınızı veya aynı sonuca ulaşmak için Azure AD sorgunuzda gelişmiş kurallar kullanıp kullanamayacağınızı düşünün.


## <a name="what-happened-to-intune-groups"></a>Intune gruplarına ne oldu?

| Intune'da Gruplar|Azure AD’de Gruplar|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statik kullanıcı grubu|Statik Azure AD güvenlik grubu|
|Dinamik kullanıcı grubu|Bir Azure AD güvenlik grubu hiyerarşisi ile statik Azure AD güvenlik grupları|
|Statik cihaz grubu|Statik Azure AD güvenlik grubu|
|Dinamik cihaz grubu|Dinamik Azure AD güvenlik grubu|
|Dahil etme koşullu bir grup|Intune’da dahil etme koşulundan herhangi bir statik veya dinamik üye içeren Statik Azure AD güvenlik grubu|
|Dışlama koşullu bir grup|Geçirilmez|
|Yerleşik gruplar, **Tüm Kullanıcılar**, **Gruplanmamış Kullanıcılar**, **Tüm Cihazlar**, **Gruplanmamış cihazlar**, **Tüm Bilgisayarlar**, **Tüm Mobil Cihazlar**, **Tüm MDM ile yönetilen cihazlar** ve **Tüm EAS ile yönetilen cihazlar**|Azure AD güvenlik grupları|

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

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Daha önce dağıtmış olduğunuz ilkelere ve uygulamalara ne olur?

İlkeler ve uygulamalar daha önce olduğu gibi gruplara dağıtılmaya devam edilecektir. Ancak artık bu grupları klasik Intune konsolu yerine Azure portalından yöneteceksiniz.



<!--HONumber=Feb17_HO1-->


