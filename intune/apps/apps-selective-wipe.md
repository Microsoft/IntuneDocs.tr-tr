---
title: Uygulamalardan yalnızca şirket verilerini temizleme
titleSuffix: Microsoft Intune
description: Learn how to selectively wipe only corporate data from Intune-managed apps with Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0fafe7c17c698a5eb4e5ad6825bee0ae3fe874c2
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199246"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Cihaz kaybolduğunda veya çalındığında ya da çalışan şirketten ayrıldığında, şirket uygulama verilerinin cihazdan kaldırıldığından emin olmak istersiniz. Ancak özellikle cihaz çalışana aitse kişisel verilerin kaldırılmasını istemeyebilirsiniz.

>[!NOTE]
> The iOS, Android, and Windows 10 platforms are the only platforms currently supported for wiping corporate data from Intune managed apps. Intune managed apps are applications that include the Intune APP SDK and have a licensed user account for your organization. Deployment of Application Protection Policies are not required to enable app selective wipe.

Şirket uygulaması verilerini seçmeli olarak silmek için bu konu başlığındaki adımları kullanarak bir silme isteği oluşturun. İstek tamamlandıktan sonra, uygulama cihaz üzerinde ilk kez çalıştığında şirket verileri uygulamadan kaldırılır. Silme isteğine ek olarak, Uygulama Koruma İlkeleri (APP) Erişim ayarlarının koşullarına uyulmadığında yeni bir eylem olarak kuruluşunuzun verilerinin seçmeli silinmesini yapılandırabilirsiniz. Bu özellik, önceden yapılandırılmış ölçütler temelinde hassas kuruluş verilerini otomatik olarak korumanıza ve uygulamalardan kaldırmanıza yardımcı olur.

>[!IMPORTANT]
> Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Deployed WIP policies without user enrollment
Windows Information Protection (WIP) policies can be deployed without requiring MDM users to enroll their Windows 10 device. Bu yapılandırma, kullanıcıların Windows cihazlarının yönetimini sürdürmesini sağlarken şirketlerin de kurumsal belgelerini WIP yapılandırmasına göre korumasını sağlar. Belgeler bir kez bir WIP ilkesiyle korunduktan sonra korumalı veriler bir Intune yöneticisi tarafından seçmeli olarak silinebilir. Kullanıcı ve cihaz seçilerek ve bir silme isteği gönderilerek WIP İlkesi aracılığıyla korunan tüm veriler kullanılamaz hale getirilir. From the Intune in the Azure portal, select **Client app** > **App selective wipe**. Daha fazla bilgi için bkz. [Intune ile Windows Bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Temizleme isteği oluşturma

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. In the Intune pane, select **Client apps** > **App selective wipe** > **Create wipe request**.<br>
   The **Create wipe request** pane is displayed.
3. Click **Select the user**, choose the user whose app data you want to wipe, and click **Select** at the bottom of the **User** pane.
4. Click **Select the device**, choose the device, and click **Select** at the bottom of the **Select Device** pane.
5. Click **Create** to make a wipe request.

Hizmet, cihazdaki korunan her uygulama için ayrı bir silme isteği oluşturur ve bu isteklerle temizleme isteği ile ilişkilendirilmiş kullanıcıyı izler.

## <a name="monitor-your-wipe-requests"></a>Silme isteklerinizi izleme

Temizleme isteğinin genel durumunu gösteren ve bekleyen isteklerle hataların sayısını içeren bir özet raporunuz olabilir. Daha fazla bilgi almak için şu adımları izleyin:

1. **İstemci Uygulamalar - Uygulama seçmeli silme** bölmesinde, isteklerinizin kullanıcılara göre gruplandırılmış listesini görebilirsiniz. Sistem, cihazda çalışan her korumalı uygulama için bir temizleme isteği oluşturduğundan, bir kullanıcı için birden çok istek görebilirsiniz. Durum, temizleme isteğinin **bekliyor**, **başarısız** veya **başarılı** olup olmadığını gösterir.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği durumunun ekran görüntüsü](./media/apps-selective-wipe/wipe-request-status-1.png)

Buna ek olarak, cihaz adını ve cihaz türünü görebilirsiniz; bunlar raporları okurken yararlı olabilir.

>[!IMPORTANT]
> Silmenin gerçekleşmesi için kullanıcı uygulamayı açmalıdır ve silme işlemi, istekte bulunulduktan sonra 30 dakikaya kadar zaman alabilir.

## <a name="delete-a-wipe-request"></a>Temizleme isteğini silme

Bekleme durumundaki silmeler, siz bunları elle silinceye kadar görüntülenir. Temizleme isteğini el ile silmek için:

1. **İstemci Uygulamalar - Uygulama seçmeli silme** bölmesinde.

2. Listede silmek istediğiniz temizleme isteğine sağ tıklayın ve **Temizleme isteğini sil**’i seçin.

    ![Uygulama seçmeli silme bölmesinde temizleme isteği listesinin ekran görüntüsü](./media/apps-selective-wipe/delete-wipe-request.png)

3. Silme işlemini onaylamanız istenir; **Evet** veya **Hayır**’ı seçin, sonra da **Tamam**’a tıklayın.

## <a name="see-also"></a>Ayrıca bkz:
[Uygulama koruma ilkesi nedir](app-protection-policy.md)

[Uygulama yönetimi nedir](app-management.md)
