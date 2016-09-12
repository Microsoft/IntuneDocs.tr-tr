---
title: "Cihazların nasıl yönetileceğini seçme | Microsoft Intune"
description: "Cihazları kaydedebileceğiniz ve yönetebileceğiniz çeşitli yollar hakkında bilgi edinin."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Cihazların nasıl yönetileceğini seçme
Intune bir dizi cihazı hizmete *kaydederek* yönetmenize olanak tanır. Bundan sonra kullanıcılar, *şirket portalını* kullanarak cihazlarını kaydetme, uygulamalara göz atma, uygulamaları yükleme, cihazlarının şirket ilkeleriyle uyumlu olduğundan emin olma ve BT desteğine başvurma gibi çeşitli işlemler yapabilirler.

## Mobil cihazları yönetmenin yolları
Intune aşağıdaki cihaz platformlarını yönetebilir:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> iOS’un desteklenen sürümünden önceki bir sürümünü çalıştıran cihazları daha önce kaydettiyseniz, bu cihazlar kayıtlı kalır. Özelliğin iOS’un bu sürümünü desteklediğini onaylamak için belgeleri gözden geçirin.

Intune kullanıcıların cihazlarını yönetebilir. Bu özellik "kendi cihazını getir" (KCG) olarak bilinir. Ayrıca şirketin, kullanıcıların istediği cihazı seçebileceği bir liste sağladığı ve "kendi cihazını seç" (CYOD) olarak bilinen senaryolar da dahil olmak üzere, şirkete ait cihazları da yönetebilir.

### Cihazları yönetime kaydetme
iOS, Android ve Windows Phone gibi mobil cihaz işletim sistemlerinde, her zaman cihazları kaydetmeniz gerekir. Cihazları nasıl kaydedeceğiniz kuruluşunuzun gereksinimlerine bağlıdır:

|Kayıt türü|BYOD|CYOD|Yönetici hesabıyla paylaşılan cihaz|Kullanıcı hesabı olmadan paylaşılan cihaz|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Açıklama**|Microsoft Intune kullanılarak kaydedilen kişisel cihaz|Tek kullanıcı için şirketin sahip olduğu cihaz|Birden çok kullanıcı tarafından paylaşılan bir yönetici hesabıyla yönetilen, şirketin sahip olduğu cihaz|Birden çok kullanıcı tarafından kullanılan, şirketin sahip olduğu kullanıcısız cihaz.|
|**Cihazın kullanıcısı**|Sahip|Atanan kullanıcı|Kullanıcıya özgü olmayan hesap|Belirli bir kullanıcı yok|
|**Kim kaydeder?**|Sahip|Yönetici|Cihaz Yöneticisi|Herkes|
|**Kaydını kim siler?**|Sahip veya yönetici|Platform |Yönetici veya kullanıcı|Yönetici veya kullanıcı|
|**Kim sıfırlayabilir?**|Sahip veya yönetici|Yönetici|Yönetici|Yönetici|

Ek yönergeler için bkz. [Mobil cihazların nasıl kaydedileceğini seçme](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Cihazları kaydetmenin size sağladığı özelliklerin tam listesi için bkz. [Mobil cihaz yönetim özellikleri](mobile-device-management-capabilities-in-microsoft-intune.md).

## Windows bilgisayarlarını yönetmenin yolları
Intune, Windows Vista ve üstü Windows bilgisayarlarını Intune bilgisayar istemcisini kullanarak yönetebilir. Bununla birlikte Windows bilgisayarları için, bunları kaydetme ile cihaz kaydıyla sağlanmayan birkaç özellik sunan Intune bilgisayar istemci yazılımını yükleme arasında seçim yapabilirsiniz. Çoğu senaryoda, Windows cihazlarınızı Intune’a kaydedersiniz ve bu da bilgisayar istemcisinden daha büyük bir özellik kümesi sağlar.

Aşağıdakileri yapmak istediğinizde Intune bilgisayar istemcisini kullanmayı göz önünde bulundurun:

- Windows bilgisayarlarınızı yönetirken Microsoft Intune bilgisayar istemcisiyle etkinleştirilen özelliklerden birini kullanma
- Kayıt için desteklenmeyen bir işletim sisteminin çalıştırıldığı bir Windows bilgisayarını yönetme

> [!NOTE]
> Desteklenen Windows bilgisayarlarında Intune bilgisayar istemcisini yüklemenin getirdiği özelliklerin tam listesi için bkz. [Windows bilgisayarı yönetim özellikleri](windows-pc-management-capabilities-in-microsoft-intune.md).

## Exchange ActiveSync yönetimi
Cihazları Exchange ActiveSync kullanarak da yönetebilirsiniz. Bunun için Şirket İçi Bağlayıcı'yı yüklemeniz ya da yerleşik Hizmetten Hizmete Bağlayıcı'yı kullanarak Exchange Server'a bağlanmanız gerekir.

Şirket İçi Bağlayıcı'yı yüklemeye ilişkin donanım ve yazılım gereksinimlerini öğrenmek için bkz. [Şirket İçi Bağlayıcı Gereksinimleri](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

Şirket İçi Bağlayıcı veya Hizmetten Hizmete Bağlayıcı’yı Exchange ile kullanma hakkında bilgi edinmek için bkz. [Exchange ActiveSync ve Microsoft Intune ile mobil cihaz yönetimi](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Sonraki adımlar
Artık cihazlarınızı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydettiğinizde kullanabileceğiniz özelliklerden bazılarını keşfettiniz. Bundan sonra, [cihazlarınızı kaydetmelisiniz](/intune/deploy-use/enroll-devices-in-microsoft-intune). Cihazlarınızı kaydettikten sonra, bu konu başlığı altında okuduğunuz tüm özelliklerden yararlanabilirsiniz. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->


