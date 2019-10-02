---
title: Microsoft Intune için uygulama yapılandırma ilkeleri
titleSuffix: ''
description: Microsoft Intune ile bir iOS veya Android cihazında uygulama yapılandırma ilkelerini nasıl kullanacağınızı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af81552942805bed07e818d6005231e9305b3460
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731453"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Microsoft Intune için uygulama yapılandırma ilkeleri

Uygulama yapılandırma ilkeleri, uygulamayı çalıştırmadan önce son kullanıcılara atanan bir ilkeye yapılandırma ayarlarını atamanıza izin vererek uygulama kurulumu sorunlarını ortadan kaldırmanıza yardımcı olabilir. Bu ayarlar daha sonra uygulama son kullanıcılar cihazında yapılandırıldığında otomatik olarak sağlanır ve son kullanıcıların işlem yapması gerekmez. Yapılandırma ayarları her uygulama için benzersizdir. 

Hem iOS hem de Android uygulamaları için yapılandırma ayarları sağlamak üzere uygulama yapılandırma ilkeleri oluşturabilir ve kullanabilirsiniz. Bu yapılandırma ayarları, uygulamanın uygulama yapılandırması ve Yönetimi kullanılarak özelleştirilbilmesine izin verir. Yapılandırma ilkesi ayarları, uygulama bu ayarları, genellikle uygulamanın ilk çalıştırılışında denetlediğinde kullanılır. 

Örneğin, bir uygulama yapılandırma ayarı aşağıdaki ayrıntıların herhangi birini belirtmenizi gerektirebilir:

- Özel bağlantı noktası numarası
- Dil ayarları
- Güvenlik ayarları
- Bir şirket logosu gibi marka ayarları

Bunun yerine son kullanıcılar bu ayarları giriyorlarsa, bunu yanlış yapabilirler. Uygulama yapılandırma ilkeleri, kuruluş genelinde tutarlılık sağlanmasına yardımcı olabilir ve ayarları kendi başına yapılandırmaya çalışan son kullanıcılardan yardım masası çağrılarını azaltabilir. Uygulama yapılandırma ilkelerini kullanarak yeni uygulamaları benimseme, daha kolay ve daha hızlı olabilir.

Kullanılabilir yapılandırma parametreleri sonunda uygulamanın geliştiricileri tarafından karar verilir. Uygulamanın yapılandırmayı destekleyip desteklemediğini ve hangi yapılandırmaların kullanılabildiğini görmek için uygulama satıcısı belgelerinin gözden geçirilmesi gerekir. Intune, bazı uygulamalarda kullanılabilir yapılandırma ayarlarını dolduracaktır. 

> [!NOTE]
> Yönetilen Google Play Store, yapılandırmayı destekleyen uygulamalar şu şekilde işaretlenir:
> 
> ![Yapılandırılmış uygulamanın ekran görüntüsü](./media/app-configuration-policies-overview/configured-app.png)
>
> Android cihazlar için kayıt türü olarak yönetilen cihazlar ' ı kullanırken, yalnızca [yönetilen Google Play deposundan](https://play.google.com/work)uygulama görürsünüz, [Google Play deposundan](https://play.google.com/store/apps)değil. Android for Work (AfW) ve Android kurumsal olarak da bildiğiniz yönetilen Google Play Store, uygulama yapılandırmasını destekleyen uygulama sürümlerini içeren Iş profilindeki uygulamalardır.

Bir uygulama yapılandırma ilkesini, [ekleme ve dışlama atamalarının](apps-inc-exl-assignments.md)bir birleşimini kullanarak bir son kullanıcı ve cihaz grubuna atayabilirsiniz. Bir uygulama yapılandırma ilkesini ekledikten sonra bu uygulama yapılandırma ilkesi için atamaları ayarlayabilirsiniz. İlke için atamaları ayarladığınızda, ilkenin uygulandığı son kullanıcı [gruplarını](../fundamentals/groups-add.md) dahil etme ve hariç tutma seçeneğini belirleyebilirsiniz. Bir veya daha fazla grubu dahil etmeyi seçtiğinizde, belirli grupları dahil etmeyi veya yerleşik grupları kullanmayı seçebilirsiniz. Yerleşik gruplar, **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklindedir.

Intune ile uygulama yapılandırma ilkelerini kullanmak için iki seçeneğiniz vardır:
- **Yönetilen cihazlar** - Cihaz, mobil cihaz yetkilisi (MDM) sağlayıcısı olarak Intune tarafından yönetilir. Uygulama, uygulama yapılandırmasını destekleyecek şekilde tasarlanmalıdır.
- **Yönetilen uygulamalar** -Intune uygulama SDK 'sını bütünleştirmek için geliştirilmiş bir uygulama. Bu, kayıt olmadan mobil uygulama yönetimi olarak bilinir ([mam-we](app-management.md#mobile-application-management-mam-basics)). Ayrıca, Intune uygulama SDK 'sını uygulamak ve desteklemek için bir uygulamayı sardırabilirsiniz. Bir uygulamayı sarmalama hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri için iş kolu uygulamalarını hazırlama](../developer/apps-prepare-mobile-application-management.md).

    > [!NOTE]
    > Intune tarafından yönetilen uygulamalar, bir Intune Uygulama Koruması Ilkesiyle birlikte dağıtıldığında, Intune uygulama yapılandırma Ilkesi durumu için 30 dakikalık bir zaman aralığı ile iade edilir. Kullanıcıya bir Intune Uygulama Koruması Ilkesi atanmamışsa, Intune uygulama yapılandırma Ilkesi iade aralığı 720 dakikaya ayarlanır.

## <a name="apps-that-support-app-configuration"></a>Uygulama yapılandırmasını destekleyen uygulamalar

### <a name="managed-devices"></a>Yönetilen cihazlar
Uygulama yapılandırma ilkelerini, onu destekleyen uygulamalar için kullanabilirsiniz. Intune 'da uygulama yapılandırmasını desteklemek için uygulamalar, işletim sistemi tarafından tanımlanan uygulama yapılandırmalarının kullanımını desteklemek üzere yazılmalıdır. Destekledikleri uygulama yapılandırma anahtarlarının ayrıntıları için uygulama satıcınıza başvurun.

### <a name="managed-apps"></a>Yönetilen uygulamalar
[Intune uygulama SDK 'sını](../developer/app-sdk.md) uygulamaya ekleyerek veya [Intune uygulaması sarmalama aracı](../developer/apps-prepare-mobile-application-management.md)kullanılarak geliştirildikten sonra uygulamayı sarmalayarak iş kolu uygulamalarınızı hazırlayabilirsiniz. Intune uygulama SDK 'Sı, uygulama geliştiricisinden gereken kod değişikliği miktarını en aza indirir. Daha fazla bilgi için bkz. [Intune Uygulama SDK’sına genel bakış](../developer/app-sdk.md). Intune uygulama SDK 'Sı ile Intune uygulama sarmalama aracı arasında bir karşılaştırma için bkz. [iş kolu uygulamalarını uygulama koruma ilkeleri Için hazırlama](../developer/apps-prepare-mobile-application-management.md#feature-comparison).

**Cihaz kayıt türü** olarak **yönetilen uygulamalar** , cihaz yönetimine kayıtlı olmayan bir cihazda Intune yapılandırma ilkeleri tarafından yapılandırılan uygulamalara başvurur, ancak **yönetilen cihazlar** dağıtılan uygulamalar için geçerli olur MDM kanalı aracılığıyla Intune tarafından yönetilir. Bu açıklamalara göre uygun seçimi seçin. 

![Cihaz kayıt türü](./media/app-configuration-policies-overview/device-enrollment-type.png)

> [!NOTE]
> Microsoft Outlook gibi çok kimlikli uygulamalarda Kullanıcı tercihleri göz önünde bulundurulmayabilir. Odaklanmış gelen kutusu, örneğin, Kullanıcı ayarına göre değişir ve yapılandırmayı değiştirmez. Diğer parametreler, bir kullanıcının ayarı değiştiremeyeceğini veya değiştiremeyeceğini denetlemenize olanak tanır. Daha fazla bilgi için bkz. [iOS Için Outlook dağıtımı ve Android uygulama yapılandırma ayarları](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

## <a name="validate-the-applied-app-configuration-policy"></a>Uygulanan uygulama yapılandırma ilkesini doğrulama

Aşağıdaki üç yöntemi kullanarak uygulama yapılandırma ilkesini doğrulayabilirsiniz:

   1. Cihaz üzerinde görünür. Hedeflenen uygulama, uygulama yapılandırma ilkesinde uygulanan davranışı kullanıyor mu?
   2. Tanılama günlükleri aracılığıyla (aşağıdaki tanılama günlükleri bölümüne bakın).
   3. Intune portalında. Bir ilkenin **izleme** bölümü ilgili durumu verebilir:

      ![Cihaz yüklemesi durumunun ilk ekran görüntüsü](./media/app-configuration-policies-overview/device-install-status-1.png)

      ![Cihaz yüklemesi durumunun ikinci ekran görüntüsü](./media/app-configuration-policies-overview/device-install-status-2.png)

      Ek olarak, **ıntune** -> **cihaz**altında, ekranın sol tarafındaki**tüm cihazlar** @no__t, **uygulama yapılandırma** seçeneği atanan tüm ilkeleri ve bunların durumlarını görüntüler:

      ![Uygulama yapılandırması ekran görüntüsü](./media/app-configuration-policies-overview/app-configuration.png)

## <a name="graph-api-support-for-app-configuration"></a>Uygulama yapılandırması için Graph API desteği

Graph API, uygulama yapılandırma görevlerini gerçekleştirmek için kullanabilirsiniz. Ayrıntılar için bkz. [Graph API’si Başvurusu MAM Hedefli Yapılandırma](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="troubleshooting"></a>Sorun giderme

### <a name="using-logs-to-show-a-configuration-parameter"></a>Bir yapılandırma parametresini göstermek için günlükleri kullanma
Günlükler, uygulanması onaylanan bir yapılandırma parametresi gösterip işe yaramazsa, uygulama geliştiricisi tarafından yapılandırma uygulamasıyla ilgili bir sorun olabilir. Önce bu uygulama geliştiricisine ulaşmak veya bilgi bankalarını denetlemek size Microsoft ile destek çağrısı kazandırabilir. Yapılandırma bir uygulama içinde nasıl ele alındığı ile ilgili bir sorun ise, bu uygulamanın gelecekte güncelleştirilmiş bir sürümünde ele alınmalıdır.

## <a name="next-steps"></a>Sonraki adımlar

### <a name="managed-devices"></a>Yönetilen cihazlar

- iOS cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [yönetilen iOS cihazları için uygulama yapılandırma Ilkeleri ekleme](app-configuration-policies-use-ios.md).
- Android cihazlarınızla uygulama yapılandırmasını kullanma hakkında bilgi edinin.  Bkz. [Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Yönetilen uygulamalar

- Yönetilen uygulamalarla uygulama yapılandırmasını kullanma hakkında bilgi edinin. Bkz. [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-managed-app.md).
