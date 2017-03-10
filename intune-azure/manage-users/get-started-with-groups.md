---
title: "Intune Azure portal önizlemesinde grupları kullanmaya başlama"
titleSuffix: Intune Azure preview
description: "Intune Azure Portal önizlemesinde gruplarla ilgili yenilikleri öğrenin"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0b3ef70a54c5d91922cecbf07f864c94c559061e
ms.lasthandoff: 02/18/2017


---

# <a name="get-started-with-groups"></a>Grupları kullanmaya başlama

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Geri bildirimlerinizi aldık ve Microsoft Intune’da gruplarla çalışma konusunda bazı değişiklikler yaptık.
Intune’u Azure Portal’dan kullanıyorsanız, Intune gruplarınız Azure Active Directory güvenlik gruplarına geçirilmiştir.

Bunun size yararı, artık aynı grup deneyimini tüm Enterprise Mobility + Security ve Azure AD uygulamalarınızda kullanabilecek olmanızdır. Ayrıca, bu yeni işlevi genişletmek ve özelleştirmek için PowerShell ve Grafik API’si kullanmanız mümkün olacaktır.

Azure AD güvenlik grupları hem kullanıcılara hem de cihazlara tüm Intune dağıtımı türlerini destekler. Ayrıca, sağladığınız özniteliklere bağlı olarak otomatik güncelleştirilen Azure AD dinamik gruplarını kullanabilirsiniz. Örneğin, iOS 9 çalıştıran cihazlardan bir grup oluşturabilirsiniz. Ne zaman iOS 9 çalıştıran bir cihaz kaydolursa bu cihaz, otomatik olarak dinamik grupta görünür.

## <a name="what-is-not-available"></a>Neler kullanılamıyor?

Intune gruplarının daha önce kullanıyor olabileceğiniz bazı özellikleri Azure AD’de kullanılamıyor:

- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** Intune grupları artık yoktur.
- Bir gruptan **Belirli üyeleri hariç tut** seçeneği Azure Portal’da bulunmamaktadır. Ancak, bu davranışı tekrarlamak için gelişmiş kurallara sahip bir Azure AD güvenlik grubu kullanabilirsiniz. Örneğin, Satış departmanınızda çalışan herkesi bir güvenlik grubuna dahil eden, ancak unvanında “Asistan” kelimesi bulunanları gruptan dışlayan gelişmiş bir kural oluşturmak için aşağıdaki gelişmiş kuralı kullanabilirsiniz:

  `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Intune konsolundaki **Tüm Exchange ActiveSync Tarafından Yönetilen Cihazlar** grubu Azure AD’ye geçirilmemiştir. Ancak, EAS tarafından yönetilen cihazlar hakkındaki bilgilere Azure portalından erişmeye devam edebilirsiniz.

## <a name="how-to-get-started"></a>Nereden başlayacaksınız?

- Azure AD güvenlik grupları ve nasıl çalıştıkları hakkında bilgi edinmek için aşağıdaki konuları okuyun:
    -  [Azure Active Directory grupları ile kaynaklara erişimi yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Azure Active Directory'de grupları yönetme](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Grup oluşturması gereken yöneticilerin **Intune Hizmet Yöneticisi** Azure AD rolüne eklenmesini sağlayın. Azure AD Hizmet Yöneticisi rolü, **Grubu Yönet** izinlerine sahip değildir.
-  Intune gruplarınız **Belirli üyeleri dışla** seçeneğini kullandıysa, bu grupları dışlamalar olmadan yeniden tasarlama ya da iş gereksinimlerini karşılamak için gelişmiş kurallar kullanma arasında karar verin.


## <a name="what-happened-to-intune-groups"></a>Intune gruplarına ne oldu?
Gruplar, klasik Intune portalından Azure portalında Intune’a geçirilirken aşağıdaki kurallar uygulanır:

| Intune'da Gruplar|Azure AD’de Gruplar|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statik kullanıcı grubu|Statik Azure AD güvenlik grubu|
|Dinamik kullanıcı grubu|Bir Azure AD güvenlik grubu hiyerarşisi ile statik Azure AD güvenlik grupları|
|Statik cihaz grubu|Statik Azure AD güvenlik grubu|
|Dinamik cihaz grubu|Dinamik Azure AD güvenlik grubu|
|Dahil etme koşullu bir grup|Intune’da dahil etme koşulundan herhangi bir statik veya dinamik üye içeren Statik Azure AD güvenlik grubu|
|Dışlama koşullu bir grup|Geçirilmez|
|Yerleşik gruplar:<br>- **Tüm Kullanıcılar**<br>- **Gruplanmamış Kullanıcılar**<br>- **Tüm Cihazlar**<br>- **Gruplanmamış cihazlar**<br>- **Tüm Bilgisayarlar**<br>- **Tüm Mobil Cihazlar**<br>- **MDM tarafından yönetilen tüm cihazlar**<br>- **EAS tarafından yönetilen tüm cihazlar**|Azure AD güvenlik grupları|

## <a name="group-hierarchy"></a>Grup hiyerarşisi

Klasik Intune konsolunda tüm grupların bir üst grubu vardı. Gruplar yalnızca üst gruplarının üyelerini içerebiliyordu. Azure AD’de alt gruplar, üst gruplarında yer almayan üyeler içerebilir.

## <a name="group-attributes"></a>Grup öznitelikleri
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

