---
title: Microsoft Intune - Azure'ı kullanarak iOS cihazlarının kilit ekranında özelleştirme | Microsoft Docs
titlesuffix: ''
description: İOS için paylaşılan cihaz yapılandırma ayarları ile iOS cihazı kilit ekranında bilgileri görüntülemek için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203085"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Ekran ve oturum açma penceresinde Intune kullanarak iOS cihazlarını kilitlemek için özel bir ileti ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede iOS cihaz kilit ekranı ve oturum açma penceresinde bilgi göstermek için kullanabileceğiniz Intune ayarlarını gösterir. 

Oturum açma penceresinde ve kilit ekranında bir özel ileti veya metin göstermek için bu ayarları kullanın. Örneğin, "Kaybedildiğinde dönmek..." iletisi girebilirsiniz ve varlık etiketi bilgileri.

Bu ayarlar, iOS 9.3 ve üzerini çalıştıran denetimli cihazları destekler.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalı](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Profil için bir **Ad** ve bir **Açıklama** girin.
4. İçinde **Platform**seçin **iOS**. İçinde **profil türü**seçin **cihaz özellikleri**.
5. İçinde **ayarları**seçin **kilit ekranı iletisi (yalnızca denetimli)**. Aşağıdaki ayarları yapılandırın:

    - **Varlık etiketi bilgileri**: Cihazın varlık etiketi hakkındaki bilgileri girin. Örneğin, şunu girin: `123xyz`.

        Cihaz oturum açma penceresinde ve kilit ekranında girdiğiniz metin gösterilir.

    - **Kilit ekranı dipnotu**: Cihaz kaybolur veya çalınırsa, döndürülen cihaz alınmasına yardımcı olabilecek bir not girin. Alanında istediğiniz herhangi bir metin girebilirsiniz. Örneğin `If found, call Contoso at ...` gibi bir URI girebilirsiniz.

    Cihaz belirteçleri, cihaza özgü bilgiler için bu alanları eklemek için de kullanılabilir. Örneğin, seri numarası göstermek için girin `Serial Number: {{serialnumber}}`. Kilit ekranında, metin benzer gösterir `Serial Number 123456789ABC`. Değişkenleri girerken, süslü ayraçlar kullanmaya özen `{{ }}`. [Uygulama yapılandırma belirteçleri](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) kullanılabilen değişkenleri bir listesini içerir. Ayrıca `deviceName` veya başka bir cihaza özgü değer.

6. İşiniz bittiğinde seçin **Tamam** > **Tamam** > **Oluştur**. Profilinizi listesinde gösterilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).
