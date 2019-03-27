---
title: Microsoft Intune - Azure'da Android cihazlarda Zebra Mobility uzantıları kullanma | Microsoft Docs
description: Zebra Mobility Uzantıları (MX) ile Android çalıştıran Zebra cihazlar yönetip Intune kullanın. Dışarıdan uygulama Şirket portalı uygulamasını yüklediğinizde, cihaz yöneticisi rolünü, StageNow profili ve daha fazlasını oluşturun dahil olmak üzere tüm adımları, bkz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2734247569245794bce7fe1de68c8b20c6091f
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490613"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Zebra Mobility Intune uzantılarında Zebra cihazları yönetme ve kullanın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, özellikleri, uygulamaları yönetme ve cihaz ayarlarını yapılandırma dahil olmak üzere zengin bir özellik kümesi içerir. Bu yerleşik özellikler ve ayarlar "Zebra cihazlar" olarak da bilinen Zebra Technologies tarafından üretilen Android cihazları yönetmek için kullanılır.

Daha fazla Zebra özgü ayarlar eklemek veya özelleştirmek istiyorsanız, ayrıca Zebra kullanabilirsiniz **Mobility Uzantıları (MX)** bu cihazlarda. 

Bu özellik şu platformlarda geçerlidir:

- Android

Şirketiniz Zebra cihazlar, perakende, Fabrika katı ve daha fazlası için kullanabilirsiniz. Örneğin, bir satıcıya işiniz ve ortamınızı Zebra mobil cihazları satış ilişkilendirir tarafından kullanılan binlerce içerir. Intune, mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak bu cihazları yönetmenize yardımcı olabilir.

Intune kullanarak, satır iş kolu uygulamalarınızı cihazlara dağıtmak için Zebra cihazları kaydedebilirsiniz. "Cihaz yapılandırma" profilleri Zebra özgü ayarlarınızı yönetmek için MX profilleri oluşturmanıza olanak tanır.

Bu makalede Microsoft Intune Zebra cihazlarda Zebra Mobility Uzantıları (MX) kullanmayı gösterir.

## <a name="before-you-begin"></a>Başlamadan önce

- Zebra teknolojilerden StageNow Masaüstü uygulamasını en son sürümüne sahip olduğunuzdan emin olun.
- Kontrol ettiğinizden emin olun [Zebra'nın tam MX özellik matrisi](http://techdocs.zebra.com/mx/compatibility) (Zebra'nın web sitesini açar) doğrulamak oluşturduğunuz profilleri cihazın MX sürümü, işletim sistemi sürümü ve modeli ile uyumlu.
- TC20/25 cihazları gibi bazı cihazların tüm kullanılabilir MX Özellikler içinde StageNow desteklemez. Kontrol ettiğinizden emin olun [Zebra'nın özellik matrisi](http://techdocs.zebra.com/mx/tc2x/) (Zebra'nın web sitesini açar) güncelleştirilmiş destek bilgisi için.

## <a name="step-1-install-the-latest-company-portal-app"></a>1. adım: En yeni şirket portalı uygulamasını yükleme

Cihazda Google Play Store'a gidip ve indirin ve Microsoft Intune Şirket portalı uygulamasını yükleyin. Google Play'den yüklendiğinde, Şirket portalı uygulamasını güncelleştirmeleri alır ve otomatik olarak düzeltir.

Google Play kullanılabilir değilse, indirme [Android için Microsoft Intune Şirket portalı](https://www.microsoft.com/download/details.aspx?id=49140) (başka bir Microsoft Web sitesi açılır), ve [dışarıdan yükleme,](#sideload-the-company-portal-app) (Bu makaledeki). Bu şekilde yüklendiğinde, uygulama güncelleştirmelerini almaz veya otomatik olarak düzeltir. Düzenli olarak güncelleştirme ve uygulamayı el ile düzeltmeniz gerekir.

### <a name="sideload-the-company-portal-app"></a>Şirket portalı uygulamasını dışarıdan yükleme

Bir uygulamayı yüklemek için Google Play kullanmadığınızda "Dışarıdan yükleme" dir. Şirket portalı uygulamasını dışarıdan yükleme için StageNow kullanın. 

Aşağıdaki adımlar, genel bir bakış sağlar. Belirli Ayrıntılar için Zebra'nın belgelerine bakın. [StageNow kullanarak bir MDM sistemine kaydetme](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (Zebra'nın web sitesini açar) iyi bir kaynak olabilir.

1. StageNow içinde için profil oluşturma **bir MDM Kaydol**.
2. İçinde **dağıtım**, MDM Aracısı dosyasını indirmek seçin.
3. Ayarlama **destek uygulama** ve **indirme yapılandırma** adımları **Hayır**.
4. İçinde **indirme MDM**seçin **aktarma/kopyalama dosya**. Kaynak ve hedef Android Şirket portalı paketin (APK) ekleyin.
5. İçinde **başlatma MDM**, varsayılan değer olarak bırakın-olduğu. Aşağıdaki ayrıntıları ekleyin:

    - **Paket adı**: `com.microsoft.windowsintune.companyportal`
    - **Sınıf adı**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Yayımlama profilini ve cihazdaki StageNow uygulamasıyla tüketen devam edin. Şirket portalı uygulamasının yüklü ve cihazda açılır.

> [!TIP]
> StageNow ve ne işe yaradığını hakkında daha fazla bilgi için bkz. [StageNow Android cihaz hazırlama](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (Zebra'nın web sitesini açar).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>2. adım: Şirket portalı uygulamasını cihaz Yöneticisi rolüne sahip onaylayın

Cihaz Yöneticisi, Android cihazları yönetmek için Şirket portalı uygulamasını gerektirir. Cihaz yöneticisi rolü etkinleştirmek için cihazda kullanıcı arabirimi (UI) bazı Zebra cihazları içerir. Cihaz bir UI içeriyorsa, Şirket portalı uygulaması son kullanıcının cihaz yöneticiye sırasında ister [kayıt](#step-3-enroll-the-device-in-to-intune) (Bu makaledeki).

Bir kullanıcı Arabirimi kullanılabilir durumda değilse kullanmak **DevAdmin Manager** StageNow el ile şirket portalı uygulamasında cihaz Yöneticisi veren bir profil oluşturmak için de.

Aşağıdaki adımlar, genel bir bakış sağlar. Belirli Ayrıntılar için Zebra'nın belgelerine bakın. 
[Cihaz Yöneticisi olarak pil takas modunu ayarlama](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (Zebra'nın Web sitesi açılır) iyi bir kaynak olabilir.

1. StageNow, bir profil oluşturun ve seçin **Xpert modu**.
2. Ekleme **DevAdmin Manager** profil.
3. Ayarlama **cihaz yönetim eylemi** için **cihaz yönetici olarak açın**.
4. Ayarlama **cihaz Yönetim Paketi adı** için `com.microsoft.windowsintune.companyportal`.
5. Ayarlama **cihaz yönetim sınıfı adı** için `com.microsoft.omadm.client.PolicyManagerReceiver`.

Yayımlama profilini ve cihazdaki StageNow uygulamasıyla tüketen devam edin. Şirket portalı uygulamasını cihaz Yönetici rolü izni verilir.

## <a name="step-3-enroll-the-device-in-to-intune"></a>3. adım: Cihazı ıntune'a kaydetme

İlk iki adım tamamladıktan sonra Şirket portalı uygulaması cihaza yüklenir. Cihazın Intune'a kaydedilmiş hazırdır.

[Android cihazları kaydetmeyi](android-enroll.md) adımları listelenir. Birçok Zebra cihazlarınız varsa, kullanmak istediğiniz bir [cihaz kayıt yöneticisi hesabı](device-enrollment-manager-enroll.md).

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>4. adım: Bir cihaz yönetim profili StageNow içinde oluşturma

StageNow cihazda yönetmek istediğiniz ayarları yapılandıran bir profil oluşturmak için kullanın. Belirli Ayrıntılar için Zebra'nın belgelerine bakın. [Profilleri](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (Zebra'nın Web sitesi açılır) iyi bir kaynak olabilir.

Son adımda StageNow içinde profili oluştururken, seçin **dışarı aktarmak için MDM**. Bu, bir XML dosyası oluşturur. Bu dosyayı kaydedin. Daha sonraki bir adımda ihtiyacınız.

> [!TIP]
> Profil, cihazlara kuruluşunuza dağıtmadan önce test etmek için önerilir. Bilgisayarınızda ile StageNow profillerini oluştururken son adımda test etmek için **Test** seçenekleri. Ardından, cihazdaki StageNow tarafından oluşturulan dosya StageNow uygulamasıyla kullanır. 
> 
> Cihazda StageNow uygulama profili test ettiğinizde oluşturulan günlükleri gösterir. [Intune'da Android çalıştıran Zebra cihazlar kullanım StageNow açtığında](android-zebra-mx-logs-troubleshoot.md) StageNow günlükleri kullanarak hataları anlama hakkında bilgi içeriyor.

> [!NOTE]
> Uygulamaları başvuru güncelleştirme paketleri veya StageNow profilinizdeki diğer dosyaları güncelleştirme, bu güncelleştirmeleri almak için cihaz istersiniz. Cihaz, güncelleştirmeleri almak için profili uygulandığında StageNow dağıtım sunucuya bağlanmanız gerekir. 
> 
> Ya da dahil olmak üzere, bu değişiklikleri almak için Intune'da yerleşik özelliklerini kullanabilirsiniz: 
> - Uygulama Yönetimi özellikleri için [ekleme](apps-add.md), [dağıtma](apps-deploy.md), güncelleştirme ve [İzleyici](apps-monitor.md) uygulamalar.
> - Yönetme [sistem ve uygulama güncelleştirmelerini](device-restrictions-android-for-work.md#device-owner-only) Android Kurumsal cihaz üzerinde çalışan

Dosya test ettikten sonra sonraki adıma Intune kullanarak cihazlara profil dağıtmaktır.

> [!NOTE]
> Her cihaz için bir profil dağıtın. Birden çok StageNow profili cihazlara dağıtmak istediğiniz kullanıyorsanız StageNow profillerini dışarı aktar ve Intune'a eklemeden önce ayarları tek bir XML dosyasına birleştirin. 
> 
> Aynı özellik aynı XML dosyasında yapılandıran iki ayarları istemezsiniz. Cihaz ayarları arasındaki çakışmaları önlemek için hedeftir.

## <a name="step-5-create-a-profile-in-intune"></a>5. adım: Intune'da bir profil oluşturma

Intune'da cihaz yapılandırma profili oluşturun:

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android**’i seçin.
    - **Profil türü**: Seçin **MX profili (yalnızca Zebra)**.

4. İçinde **MX profili .xml biçiminde**, XML profili dosyası ekleme [StageNow ' dışarı aktardığınız](#step-4-create-a-device-management-profile-in-stagenow) (Bu makaledeki).
5. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. İlke oluşturulur ve listede gösterilen.

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

Cihaz denetlediğinde yapılandırma güncelleştirmelerini MX profili cihaza dağıtılır. Cihazları Intune ile cihazları kaydettiğinizde, eşitleme ve yaklaşık 8 saat. Ayrıca [ıntune'da eşitleme işlemi yapılmasını](device-sync.md). Veya cihaz üzerinde açık **Şirket portalı uygulamasını** > **ayarları** > **eşitleme**. 

> [!TIP]
> - Kaydettikten sonra güvenlik nedeniyle, ' % s'profil XML metin görmezsiniz. Metin şifrelenir ve yalnızca yıldız işareti görürsünüz (`****`). Referans olması açısından, bunları Intune'a eklemeniz önce MX profilleri kopyasını kaydetmek için önerilir.
> 
> - Zebra cihazlara atandıktan sonra profil güncelleştirmek için güncelleştirilmiş bir StageNow XML dosyası oluşturun, mevcut Intune profili düzenlemek ve yeni StageNow XML dosyası ekleyin. Bu yeni dosya, profil önceki StageNow ilkesinde üzerine yazar.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[Zebra cihazlarında sorun gidermenize için StageNow günlüklerini kullanma](android-zebra-mx-logs-troubleshoot.md).
