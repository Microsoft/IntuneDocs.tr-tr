---
title: "Microsoft Intune’da hüküm ve koşulları ayarlama"
titleSuffix: Intune Azure preview
description: "Intune Şirket Portalı’nda kullanıcıların göreceği hüküm ve koşulları ayarlayın. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>Kullanıcıların erişim için şirket koşullarını kabul ettiğinden emin olun

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bir Intune yöneticisi olarak, kullanıcıların Şirket Portalı’nı kullanarak cihazlarını kaydedebilmeleri, uygulama ve e-posta gibi şirket kaynaklarına erişebilmeleri için önce şirketin hüküm ve koşullarını kabul etmelerini zorunlu tutabilir. Hüküm ve koşulların yapılandırması isteğe bağlıdır.

Farklı gruplara yönelik olarak, örneğin farklı dillere destek sağlamak için birden çok koşul kümesi oluşturabilirsiniz.

## <a name="create-terms-and-conditions"></a>Hüküm ve koşulları oluşturma
Hüküm ve koşulları oluşturmak için şu adımları tamamlayın. Görüntü adı ve açıklama yönetimin kullanımına yöneliktir; öte yandan, koşul özellikleri Şirket Portalı’nda kullanıcılara görüntülenir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.

3. **Oluştur**’u seçin.
![Hüküm ve koşullar için Oluştur düğmesinin gösterildiği Intune portalının ekran görüntüsü](media/terms-create-terms.png)

4. Genişletilmiş dikey pencerede aşağıdaki bilgileri belirtin:

   - **Görüntü adı**: Intune portalında koşulların adı. Kullanıcılar bu adı görmez.

   - **Açıklama**: Intune portalında koşul kümesini tanımlamanıza yardımcı olacak isteğe bağlı ayrıntılar.

5. Hükümler ve Koşullar dikey penceresini açmak için Kullanım koşullarını tanımla’nın yanındaki oku seçin ve ardından aşağıdaki bilgileri girin:

   ![Son kullanıcı koşulları ve koşul özetlerinin bulunduğu hüküm ve koşulların kabulünü gösteren ekran görüntüsü](./media/terms-summary-create.png)

   - **Başlık**: Kullanıcıların Şirket Portalı’nda gördüğü başlık.

   - **Koşulların Özeti**: Kullanıcılar koşulları kabul ettiğinde bunun ne anlama geldiğini açıklayan metin. Örneğin, "Cihazınızı kaydettiğinizde, Contoso tarafından ayarlanmış kullanım koşullarını kabul etmiş olursunuz. Devam etmeden önce koşulları dikkatle okuyun."

   - **Hüküm ve Koşullar**: Kullanıcılara gösterilen ve kabul etmeleri veya reddetmeleri gereken hüküm ve koşullar.

6. **Tamam**’ı ve ardından **Oluştur**’u seçin.

## <a name="assign-terms-and-conditions"></a>Hüküm ve koşulları atama

Hüküm ve koşulları kullanıcı gruplarına atayabilirsiniz; bu kullanıcıların Şirket Portalı’nı kullanmak için önce bunları kabul etmesi gerekir.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.

3. Hüküm ve koşullar listesinde, atamak istediğiniz koşulları seçin ve sonra da **Atanan Gruplar**’ı seçin.
![Intune portalında hüküm ve koşulların atanması için Grup Seç düğmesinin gösterildiği Grup Ata dikey penceresinin ekran görüntüsü](media/terms-assign-groups.png)

4. **Grup Seç** düğmesini seçin ve **Grup Seç** dikey penceresinde koşulları atamak istediğiniz grupları seçin ve ardından **Seç**’e tıklayın.

5. **Atanan Gruplar** dikey penceresinde **Kaydet**’e tıklayın.  Artık hükümler ve koşullar seçili grupların kullanıcılarına atanır. Bir sonraki Şirket Portalı erişimi sırasında kullanıcılardan koşulları kabul etmeleri istenir.

   ![Son kullanıcı koşulları ve koşul özetlerinin bulunduğu hüküm ve koşulların kabulünü gösteren ekran görüntüsü](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>Hüküm ve koşulları izleme

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihaz kaydı**’nı ve ardından **Hüküm ve Koşullar**’ı seçin.
2. Hüküm ve koşullar listesinde, kabul durumunu görüntülemek istediğiniz koşulları seçin ve sonra da **Kabul Durumları**’nı seçin.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Hüküm ve koşulların birden çok sürümü ile çalışma
Hüküm ve koşullarınızı düzenleyebilir ve bunların sürümlerini yönetebilirsiniz. Hüküm ve koşullarınızda önemli değişiklikler yaptığınızda sürüm numarasını artırmanızı ve kabul şartı koşmanızı öneririz. Örneğin, yazım hatalarını düzeltiyor veya biçimlendirmeyi değiştiriyorsanız geçerli sürüm numarasını kullanmaya devam edin.

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihaz kaydı**’nı seçin, **Hüküm ve Koşullar**’ı seçin, değiştirmek istediğiniz hüküm ve koşulları seçin, sonra da **Özellikler**’i seçin.

4. **Özellikler** dikey penceresinde **Hüküm ve Koşullar**’ı seçin ve ardından **Başlık**, **Koşulların Özeti** ve **Hüküm ve Koşullar**’da gerekli değişiklikleri yapın. Yaptığınız değişiklikler kullanıcıların yeni koşulları yeniden kabul etmesini gerektiriyorsa, **Kullanıcıların yeniden kabul etmesini ve sürüm numarasını {0} olarak artırmasını isteyin** öğesine tıklayın.

4.  **Tamam**’ı ve ardından **Kaydet**’i seçin.

