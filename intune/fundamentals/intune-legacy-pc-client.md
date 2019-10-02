---
title: Azure 'da eski Intune PC istemcisi ve Intune
description: Azure'de Intune'u kuruluşunuzdaki Windows cihazlarını yönetmek için kullanırken dikkat edilecek hususlar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: fe6b5967a5980304ba2f6c9af75491463dae1b4b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732053"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Azure konsolu ve eski Intune PC istemcisinde Intune

Intune, Azure tabanlı SaaS uygulama hizmeti mimarisini kullanır. Azure, ölçek, kapasite ve performans açısından önemli gelişmeler sağlar. Bu, Azure portal gelişmiş Intune yönetim deneyimleri ve iyileştirilmiş iş akışları sunar. 

Kuruluşunuzun Windows aygıtlarını yönetmek için Azure'de Intune kullanırken, aşağıdaki noktaları göz önünde bulundurun:

## <a name="manage-windows-10-devices-by-using-mdm"></a>MDM kullanarak Windows 10 cihazları yönetme

Eski Intune PC istemcisini kullanmak yerine Windows 10 cihazlarınızı yönetmek için [Mobil Cihaz Yönetimi'ni (MDM)](../configuration/device-restrictions-windows-10.md) kullanmanızı öneririz. MDM aracılığıyla Windows 10'u yönetme olanağı Intune on Azure portalında bulunur. Windows 10 MDM, eski Intune PC istemcisi aracılığıyla bulunmayan pek çok yeni yönetim ve güvenlik özelliği sunar.

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Eski PC İstemcisi özellikleri yalnızca Silverlight konsolunda bulunur

Intune PC İstemci yönetimi iş akışları, [Silverlight tabanlı Intune Yönetici Konsolu](https://manage.microsoft.com/)'nu kullanır; bu da aşağıdaki sonuçları doğurur:

- Intune bilgisayar istemcisini kullanarak tüm gruplandırma olmayan yönetim görevleri için Silverlight konsolunu kullanmanız gerekir.
- Grupları yönetirken [Intune on Azure portal](https://portal.azure.com/)'ı kullanmalısınız. Bu gereklilik, Intune artık eski Intune Grupları yerine Azure AD Gruplarını kullandığı için ortaya çıkar. 

Azure AD Gruplarına geçiş nedeniyle, Silverlight konsolu gösterge panosu görünümlerinde "grup tabanlı" filtreleme biraz değişti. Güncelleştirilmiş Silverlight Arabiriminde filtre uygulamak için şu adımları izleyin:

1. Bir görünüm seçin.
2. **Filtreler** kutusuna filtrelemek istediğiniz grubun adını girin ve enter tuşuna basın. Bu liste görünümü belirli bu gruptaki cihazlar için filtre uygular.

   ![Seçili olmayan filtre açılan girişi](./media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Intune PC Client'ı kullanarak Windows 7'yi yönetmeye devam etme

MDM kullanarak yönetilemeyen Windows 7 için yalnızca var olan Silverlight konsolundaki Intune PC Client özelliklerini desteklemeye devam edeceğiz. Windows 10'a yükselttiğinizde MDM yönetimine geçmeyi düşünün.

## <a name="mdm-capabilities"></a>MDM Özellikleri

PC İstemcisi ve MDM özellikleri arasında ayrıntılı bir karşılaştırma için bkz. [Windows PC'leri bilgisayarlar veya mobil cihazlar olarak yönetmeyi karşılaştırma](pc-management-comparison.md). MDM güncellemeleri, Win 32 uygulamaları için seçenekler de dahil olmak üzere MDM'ye kaydolan Windows 10 cihazlarına yeni yönetim özellikleri getirmeye devam edecektir. Hizmete en son sürüm eklemeleri için [Yenilikler](whats-new.md)'i görüntüleyin.

## <a name="switch-from-pc-client-to-mdm"></a>PC istemciden MDM’ye geçiş yapmak için

Intune PC İstemcisi ile Windows 10 cihazlarını yönetmekten MDM ile yönetime geçiş yapmak için şu adımları izleyin:

1. Silverlight konsolunda, cihazın kaydını PC İstemcisi'nden kaldırmak için bir **Seçmeli silme** gerçekleştirin.
  ' cihaz seçmeli olarak sil ' radyo düğmesi seçili @ no__t-1 ' i ![Warning açılır penceresi
2. [MDM (ve/veya Azure AD Join)](../enrollment/windows-enroll.md)'i kullanarak cihazı yeniden kaydedin.

## <a name="next-steps"></a>Sonraki adımlar
[Windows cihazlarını kaydetme](../enrollment/windows-enroll.md)
