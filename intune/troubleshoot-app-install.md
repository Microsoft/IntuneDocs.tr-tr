---
title: Uygulama yükleme sorunlarını giderme
titlesuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138688"
---
# <a name="troubleshoot-app-installation-issues"></a>Uygulama yükleme sorunlarını giderme

Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Microsoft Intune, kullanıcı yardım isteklerini ele almak yardım masası operatörleri ve Intune yöneticilerinin uygulama bilgilerini görüntülemek için uygulama yükleme hatası ayrıntıları sağlar. Intune içindeki sorun giderme bölmesi, kullanıcının cihazında yönetilen uygulamalar dahil hata ayrıntılarını sağlar. Bir uygulamanın uçtan uca yaşam döngüsü hakkındaki ayrıntıları, **Yönetilen Uygulamalar** bölmesinde her bir cihaz altında sağlanır. Uygulamanın ne zaman yüklendiği, değiştirildiği, hedeflendiği ve bir cihaza teslim edildiği gibi yükleme sorunlarını görüntüleyebilirsiniz. 

## <a name="to-review-app-troubleshooting-details"></a>Uygulama sorun giderme ayrıntılarını gözden geçirmek için

Intune, belirli bir kullanıcının cihazında yüklü uygulamalar temelinde sorun giderme ayrıntıları sağlar.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Sorun gider**’i seçin.
4. Sorun gidermek üzere bir kullanıcı belirlemek için **Seçin**’e tıklayın. **Seçili kullanıcılar** bölmesi görüntülenir.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. Bölmenin altındaki **Seçin**’e tıklayın. Kullanıcı için sorun giderme bilgileri, **Sorun Giderme** bölmesinde görüntülenir. 
6. **Cihazlar** listesinden sorun gidermek istediğiniz cihazı seçin.
    ![Intune Sorun Giderme bölmesi.](media/troubleshoot-app-install-01.png)
7. Seçili cihaz bölmesinden **Yönetilen Uygulamalar**’ı seçin. Yönetilen uygulamaların bir listesi görüntülenir.
    ![Intune tarafından yönetilen belirli bir cihazın ayrıntıları.](media/troubleshoot-app-install-02.png)
8. Listeden **Yükleme Durumu**’nun hata gösterdiği bir uygulamayı seçin.
    ![Yükleme hatası ayrıntıları gösteren seçili bir uygulama.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Aynı uygulama, birden çok gruba atanabilir ancak uygulama için amaçlanan farklı eylemleri (amaçları) olmalıdır. Örneğin uygulama ataması sırasında bir kullanıcı için uygulama dışlandıysa uygulama için çözümlenen amaç **dışlandı** olarak görüntülenecektir. Daha fazla bilgi için bkz. [Uygulama amaçları arasındaki çakışmalar nasıl çözümlenir](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Şu anda Intune, işletim sistemi platformunu temel alan uygulamaları filtrelemez.

Uygulama yükleme hatası ayrıntıları, sorunu gösterecektir. Sorunu çözmek için yapılacak en iyi eylemi belirlemek üzere bu ayrıntıları kullanabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [Uygulama Yükleme Sorunlarını Gidermek İçin Hata Kodları](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](known-issues.md).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](get-support.md).
