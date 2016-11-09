---
title: "Cihazların nasıl yönetileceğini seçme | Microsoft Intune"
description: "Cihazları kaydedebileceğiniz ve yönetebileceğiniz çeşitli yollar hakkında bilgi edinin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 7b5cadfbc759b025fdad995e34040762b15e0d30


---

# <a name="choose-how-to-manage-devices"></a>Cihazların nasıl yönetileceğini seçme

Intune’un sunduğu uygulama yönetimi ve cihaz ayarlarının denetlenmesi gibi pek çok özellikten yararlanmak için cihazlarınızın *yönetilmesi* gerekir. Cihazları nasıl yönettiğiniz, kullanmak istediğiniz Intune özelliklerine bağlıdır.
Bu konu, gereksinimlerinizi karşılayan yöntemi seçmenize yardımcı olur.

iOS, Mac OS X, Android veya Windows Phone çalıştıran cihazları yönetmek için bunları *kaydetmeniz* gerekir.

Windows bilgisayarları yönetmek için iki seçeneğiniz vardır:

1. Cihazı kaydetme **veya**
2. *Intune yazılım istemcisini* yükleme.

## <a name="decide-which-method-to-use"></a>Kullanılacak yönteme karar verme
Cihazlarınızın nasıl yönetileceğine karar vermek için bu karar akışını kullanın.

![Cihazlarınızı yönettirmek için karar akışı.](./media/choose-manage-method.png)

Tam işlevsellik için Windows bilgisayarları kaydedin. Ancak, Intune yazılım istemcisi aşağıdaki durumlarda gereksinimlerinize daha uygun olabilir:

- Bilgisayar Windows 7 çalıştırıyorsa
- Windows yazılım güncelleştirmelerini ve lisans kullanımını yönetmek istiyorsanız
- Endpoint Protection ve Windows Güvenlik Duvarı ile kötü amaçlı yazılımı yönetmek istiyorsanız
- TeamViewer yazılımını kullanan kullanıcılara uzaktan yardım sağlamak istiyorsanız


Her yöntem ile elde edeceğiniz yönetim özelliklerinin ayrıntılı bir listesi için bkz. [Mobil cihaz yönetim özellikleri](mobile-device-management-capabilities-in-microsoft-intune.md) ve [Intune PC yazılım istemcisi özellikleri](windows-pc-management-capabilities-in-microsoft-intune.md).
Intune’un desteklediği cihazlar ve bilgisayarlar hakkında bilgi için bkz. [Desteklenen mobil cihazlar ve bilgisayarlar](/intune/get-started/supported-mobile-devices-and-computers)


## <a name="exchange-activesync-management"></a>Exchange ActiveSync yönetimi
Cihazı kaydetmeye veya Intune yazılım istemcisini yüklemeye ek olarak cihazları [Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) ile de yönetebilirsiniz. Bu yöntem, Exchange Server’a bağlanmak için Şirket İçi Bağlayıcı’yı yüklemenizi veya yerleşik Hizmetten Hizmete Bağlayıcısı’nı kullanmanızı gerektirir.
Cihazları yönetmek için üçüncü seçenek olmasına rağmen, diğer yöntemler ile karşılaştırıldığında sınırlı sayıda yönetim özelliği sunar.


## <a name="next-steps"></a>Sonraki adımlar

- [Mobil cihazların nasıl kaydedileceğini belirleme](/intune/get-started/choose-how-to-enroll-devices1)
- [Intune bilgisayar istemci yazılımıyla Windows bilgisayarlarını yönetme](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)



- [Microsoft Intune ile Exchange ActiveSync mobil cihaz yönetimi](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).




<!--HONumber=Nov16_HO1-->


