---
title: Microsoft Intune kullanarak macOS cihazlarına Microsoft Defender ATP ekleme
titleSuffix: ''
description: Microsoft Intune kullanarak macOS cihazlarına Microsoft Defender ATP ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ae6e8a621b10ec969fa3fcfb2dfeabb8d5a7bdd
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569906"
---
# <a name="add-microsoft-defender-atp-to-macos-devices-using-microsoft-intune"></a>Microsoft Intune kullanarak macOS cihazlarına Microsoft Defender ATP ekleme

Uygulamaları dağıtmadan, yapılandırmadan, izleyebilmeniz veya koruyabilmeniz için önce bunları Intune 'a eklemeniz gerekir. Kullanılabilir [uygulama türlerinden](~/apps/apps-add.md#app-types-in-microsoft-intune) biri Microsoft Defender Gelişmiş tehdit KORUMASı (ATP). Intune 'da bu uygulama türünü seçerek, Microsoft Defender ATP 'yi yönettiğiniz cihazlara macOS Çalıştır ' ı atayabilir ve yükleyebilirsiniz. Bu uygulama türü, macOS uygulaması sarmalama aracı 'nı kullanmanıza gerek kalmadan, macOS cihazlarına Microsoft Defender ATP 'yi atamanızı kolaylaştırır. Uygulamalar daha güvenli ve güncel tutmaya yardımcı olmak için, uygulama Microsoft otomatik güncelleştirme (MAU) ile birlikte gelir.

## <a name="prerequisites"></a>Önkoşullar
- MacOS cihazının macOS 10,13 veya sonraki bir sürümü çalıştırması gerekir.
- MacOS cihazında en az 650 MB disk alanı olmalıdır.
- Intune 'da çekirdek uzantısı dağıtın. Daha fazla bilgi için bkz. [Intune 'Da macOS çekirdek uzantıları ekleme](~/configuration/kernel-extensions-overview-macos.md).

> [!IMPORTANT]
> Çekirdek uzantısı yalnızca, cihazda Microsoft Defender ATP uygulaması yüklenmeden önce varsa otomatik olarak onaylanabilir. Aksi takdirde, kullanıcılar, Mac 'te "sistem uzantısı engellendi" iletisini görür ve güvenlik **tercihleri** ' ne ve **sistem tercihleri** > **Güvenlik & gizliliği** ' ne giderek ve ardından **izin ver**' i seçerek uzantıyı onaylaması gerekir. Daha fazla bilgi için bkz. [Mac Için Microsoft Defender ATP içindeki çekirdek uzantısı sorunlarını giderme](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-support-kext).

## <a name="add-microsoft-defender-atp-to-intune"></a>Microsoft Defender ATP 'yi Intune 'a ekleme
Aşağıdaki adımları kullanarak Microsoft Defender ATP 'yi Intune 'a ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Microsoft Defender ATP**altındaki **uygulama türü** listesinde **MacOS**' u seçin.

## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma
Bu adımda, bu uygulama dağıtımı hakkında bilgi sağlarsınız. Bu bilgiler, uygulamayı Intune 'da tanımanıza yardımcı olur ve kullanıcıların uygulamayı şirket portalı 'nda bulmasına yardımcı olur.

1. **Uygulama bilgileri bölmesini göstermek** için **uygulama bilgileri** ' ne tıklayın.
2. **Uygulama bilgileri** bölmesinde, bu uygulama dağıtımı hakkında bilgi sağlarsınız. Bu bilgiler, uygulamayı Intune 'da tanımanıza yardımcı olur ve kullanıcıların uygulamayı şirket portalı 'nda bulmasına yardımcı olur.
    - **Ad**: uygulamanın şirket portalında görüntülenecek olan adını girin. Tüm adların benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Örneğin, açıklamada hedeflenen kullanıcıları listeleyebilirsiniz.
    - **Yayımcı**: Yayımcı olarak Microsoft gösterilir.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Bu ayar, kullanıcıların şirket portalına gözatarken uygulamayı bulmasını kolaylaştırır.
    - **Bunu şirket portalı öne çıkan uygulama olarak görüntüle**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde göstermek için bu seçeneği belirleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: Geliştirici olarak Microsoft gösterilir.
    - **Sahip**: Sahip olarak Microsoft gösterilir.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
3. **Tamam**’ı seçin.

## <a name="select-scope-tags-optional"></a>Kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma.
1.  **Ekle** > **kapsam (Etiketler)** seçin.
2.  Kapsam etiketlerini aramak için **Seç** kutusunu kullanın.
3.  Bu uygulamaya atamak istediğiniz kapsam etiketlerinin yanındaki onay kutusunu işaretleyin.
4.  **Tamam** > **Seç** ' e tıklayın.

## <a name="add-the-app"></a>Uygulama ekleme
Yapılandırmayı tamamladıktan sonra **uygulama uygulaması** bölmesinden **Ekle** ' yi seçin. 

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

> [!NOTE]
> Şu anda Apple, bir Intune 'un macOS cihazlarında Microsoft Defender ATP 'yi kaldırması için bir yol sağlamıyor.

## <a name="next-steps"></a>Sonraki adımlar
- MacOS cihazlarında Microsoft Defender ATP 'yi yapılandırma hakkında bilgi edinmek için bkz. [macOS cihazlarında Microsoft Defender ATP 'Yi yapılandırma](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-preferences).
- Kullanıcı gruplarında uygulama atamalarını dahil etme ve dışlama hakkında bilgi edinmek için, bkz. [Uygulama atamalarını dahil etme ve dışlama](~/apps/apps-inc-exl-assignments.md).
- [Gruplara uygulama ekleme](~/apps/apps-deploy.md)

