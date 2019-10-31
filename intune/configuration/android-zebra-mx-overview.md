---
title: Microsoft Intune'da Android cihazlarda Zebra Mobility Uzantılarını kullanma - Azure | Microsoft Docs
description: Zebra Mobility Uzantılarıyla (MX) Android çalıştıran Zebra cihazlarını yönetmek ve kullanmak için Microsoft Intune kullanın. Şirket Portalı uygulamasını yükleme, uygulamayı dışarıdan yükleme, cihaz yöneticisi rolünü atama ve StageNow profilini oluşturma da dahil olmak üzere tüm adımları görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e5804b415d26b07944c500b0158cf84a2d4412c
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182851"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Microsoft Intune'da Zebra Mobility Uzantılarını içeren Zebra cihazlarını kullanma ve yönetme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune uygulamaları yönetme ve cihaz ayarlarını yapılandırma gibi çok zengin özellikler içerir. Bu yerleşik özellikler ve ayarlar, Zeköşeli teknolojiler tarafından üretilen Android cihazlarını, "Zekare cihazları" olarak da bilinen bir şekilde yönetir.

Android cihazlarda, daha fazla zeye özgü ayarı özelleştirmek veya eklemek için Zeköşeli **Mobility uzantıları (MX)** profillerini kullanın.

Bu makalede Microsoft Intune'da Zebra cihazlarında Zebra Mobility Uzantılarının (MX) nasıl kullanılacağı gösterilir.

Bu özellik şu platformlarda geçerlidir:

- Android

Şirketiniz Zebra cihazlarını perakende işlemlerinde, fabrika katında ve daha birçok alanda kullanabilir. Örneğin perakendeci olduğunuzu ve ortamınızda satış elemanları tarafından kullanılan binlerce Zebra mobil cihazı bulunduğunu düşünün. Intune mobil cihaz yönetimi (MDM) çözümünüz kapsamında bu cihazların yönetimine yardımcı olabilir.

Intune'u kullanarak Zebra cihazlarını kaydedip bu cihazlara iş kolu uygulamalarını dağıtabilirsiniz. "Cihaz yapılandırması" profilleri, Zebra'ya özgü ayarlarınızı yönetmek için MX profilleri oluşturmanıza olanak tanır.

> [!NOTE]
> Varsayılan olarak, Zeköşeli MX API 'Leri cihazlarda kilitlenmez. Cihaz Intune 'A kaydedilmeden önce cihazın kötü amaçlı olabilecek bir şekilde tehlikeye girmiş olması mümkündür. Cihaz temiz bir durumda olduğunda, MX API 'Lerini Erişim Yöneticisi (AccessMgr) kullanarak kilitlemenizi öneririz. Örneğin, yalnızca güvendiğiniz Şirket Portalı uygulama ve uygulamaların MX API 'Leri çağırabilmesine izin verileceğini seçebilirsiniz.
>
> Daha fazla bilgi için bkz. Zezeinin Web sitesinde [cihazınızı kilitleme](https://developer.zebra.com/community/home/blog/2017/04/11/locking-down-your-device) .

## <a name="before-you-begin"></a>Başlamadan önce

- Zebra Teknologies'den StageNow masaüstü uygulamasının en son sürümünü aldığınızdan emin olun.
- Oluşturduğunuz profillerin cihazın MX sürümü, işletim sistemi sürümü ve modeliyle uyumlu olduğunu onaylamak için [Zebra'nın tam MX özellik matrisini](http://techdocs.zebra.com/mx/compatibility) (Zebra'nın web sitesini açar) gözden geçirdiğinizden emin olun.
- TC20/25 cihazları gibi bazı cihazlar StageNow'da sağlanan MX özelliklerinin tümünü desteklemez. Güncelleştirilmiş destek bilgileri için [Zebra'nın özellik matrisini](http://techdocs.zebra.com/mx/tc2x/) (Zebra'nın web sitesini açar) gözden geçirdiğinizden emin olun.


## <a name="step-1-install-the-latest-company-portal-app"></a>1\. Adım: en son Şirket Portalı uygulamayı yüklemeyi

Cihazda Google Play Store ' u açın. Microsoft 'tan Intune Şirket Portalı uygulamasını indirin ve yükleyin. Şirket Portalı uygulaması Google Play'den yüklendiğinde güncelleştirmeleri ve düzeltmeleri otomatik olarak alır.

Google Play kullanılamıyorsa, [Android için Microsoft Intune Şirket Portalı](https://www.microsoft.com/download/details.aspx?id=49140)'nı indirin (başka bir Microsoft web sitesi açar) ve [dışarıdan yükleyin](#sideload-the-company-portal-app) (bu makalede). Uygulama bu şekilde yüklendiğinde güncelleştirmeleri veya düzeltmeleri otomatik olarak almaz. Uygulamayı düzenli olarak güncelleştirdiğinizden ve düzeltme ekini el ile değiştirdiğinizden emin olun.

### <a name="sideload-the-company-portal-app"></a>Şirket Portalı uygulamasını dışarıdan yükleme

Uygulamayı yüklemek için Google Play'i kullanmadığınızda bu işleme "dışarıdan yükleme" denir. Şirket Portalı uygulamasını dışarıdan yüklemek için StageNow'ı kullanın. 

Aşağıdaki adımlar işleme genel bir bakış sağlar. Belirli ayrıntılar için Zebra'nın belgelerine bakın. [StageNow kullanarak MDM'ye kaydetme](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (Zebra'nın web sitesini açar) iyi bir kaynak olabilir.

1. StageNow'da **Enroll in an MDM** seçeneği için bir profil oluşturun.
2. **Deployment**'da MDM aracı dosyasını indirmeyi seçin.
3. **Support App** ve **Download Configuration** adımlarını **No** olarak ayarlayın.
4. **Download MDM**'de **Transfer/Copy File** öğesini seçin. Şirket Portalı Android paketinin (APK) kaynağını ve hedefini ekleyin.
5. **Launch MDM** adımında varsayılan değerleri olduğu gibi bırakın. Aşağıdaki ayrıntıları ekleyin:

    - **Package Name**: `com.microsoft.windowsintune.companyportal`
    - **Class Name**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Profili yayımlamaya devam edin ve bunu cihazda StageNow uygulamasıyla kullanın. Şirket Portalı uygulaması yüklenir ve cihazda açılır.

> [!TIP]
> StageNow ile ilgili daha fazla bilgi edinmek ve ne yaptığını öğrenmek için bkz. [StageNow Android cihazı hazırlama](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (Zebra'nın web sitesini açar).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>2\. Adım: Şirket Portalı uygulamasının cihaz yöneticisi rolüne sahip olduğunu onaylayın

Şirket Portalı uygulaması Android cihazlarını yönetmek için Cihaz Yöneticisi gerektirir. Cihaz Yöneticisi rolünü etkinleştirmek için bazı Zebra cihazlarında cihaz üzerinde bir kullanıcı arabirimi (UI) vardır. Cihazda UI varsa, Şirket Portalı uygulaması son kullanıcıdan [kayıt](#step-3-enroll-the-device-in-to-intune) sırasında Cihaz Yöneticisi rolünü vermesini ister (bu makalede).

UI yoksa, Şirket Portalı uygulamasına Cihaz Yöneticisini el ile verecek profili oluşturmak için StageNow'da **DevAdmin Manager**'ı kullanın.

Aşağıdaki adımlar işleme genel bir bakış sağlar. Belirli ayrıntılar için Zebra'nın belgelerine bakın. 
[Cihaz yöneticisi olarak pil değiştirme modunu ayarlama](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (Zebra'nın web sitesini açar) konusu iyi bir kaynak olabilir.

1. StageNow'da profil oluşturun ve **Xpert Mode** öğesini seçin.
2. Profile **DevAdmin Manager** ekleyin.
3. **Device Administration Action** seçeneğini **Turn On as Device Administrator** olarak ayarlayın.
4. **Device Admin Package Name** seçeneğini `com.microsoft.windowsintune.companyportal` olarak ayarlayın.
5. **Device Admin Class Name** seçeneğini `com.microsoft.omadm.client.PolicyManagerReceiver` olarak ayarlayın.

Profili yayımlamaya devam edin ve bunu cihazda StageNow uygulamasıyla kullanın. Şirket Portalı uygulamasına Cihaz Yöneticisi rolü verilir.

## <a name="step-3-enroll-the-device-in-to-intune"></a>3\. Adım: cihazı Intune 'a kaydetme

İlk iki adım tamamlandıktan sonra Şirket Portalı uygulaması cihaza yüklenir. Cihaz Intune'a kaydedilmeye hazırdır.

[Android cihazlarını kaydetme](../enrollment/android-enroll.md) başlığı altında adımlar listelenir. Çok sayıda Zebra cihazınız varsa [cihaz kayıt yöneticisi (DEM) hesabı](../enrollment/device-enrollment-manager-enroll.md) kullanmak isteyebilirsiniz. DEM hesabı kullanıldığında Şirket Portalı uygulamasından kaydı silme seçeneği kaldırılır, dolayısıyla kullanıcılar cihazın kaydını kolayca kaldıramaz.

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>4\. Adım: StageNow 'da cihaz yönetim profili oluşturma

StageNow'u kullanarak cihazda yönetmek istediğiniz ayarları yapılandıran bir profil oluşturun. Belirli ayrıntılar için Zebra'nın belgelerine bakın. [Profiller](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (Zebra'nın web sitesini açar) iyi bir kaynak olabilir.

StageNow'da profil oluştururken, son adımda **Export to MDM** öğesini seçin. Bu adım bir XML dosyası oluşturur. Bu dosyayı kaydedin. Sonraki adımlardan birinde ihtiyacınız olacaktır.

- Profili kuruluşunuzdaki cihazlara dağıtmadan önce test etmeniz önerilir. Test etmek için, bilgisayarınızda StageNow'la profilleri oluştururken son adımda **Test** seçeneklerini kullanın. Ardından StageNow tarafından oluşturulan dosyayı cihazda StageNow uygulamasıyla kullanın.

  Cihazda StageNow uygulaması, siz profili test ederken oluşturulan günlükleri gösterir. [Intune'da Android çalıştıran Zebra cihazlarındaki StageNow günlüklerini kullanma](android-zebra-mx-logs-troubleshoot.md) başlığı altında hataları anlamak için StageNow günlüklerini kullanma hakkında bilgi sağlanır.

- StageNow profilinizde uygulamalara başvurur, paketleri güncelleştirir veya diğer dosyaları güncelleştirirseniz, cihazın bu güncelleştirmeleri almasını istersiniz. Profil uygulandığında cihazın güncelleştirmeleri almak için StageNow dağıtım sunucusuna bağlanması gerekir. 

  Öte yandan bu değişiklikleri almak için Intune'da aşağıdakiler gibi yerleşik özellikler de kullanılabilir:

  - Uygulamaları [eklemek](../apps/apps-add.md), [dağıtmak](../apps/apps-deploy.md), güncelleştirmek ve [izlemek](../apps/apps-monitor.md) için uygulama yönetimi özellikleri.
  - Android Kurumsal çalıştıran cihazlarda [sistem ve uygulama güncelleştirmelerini](device-restrictions-android-for-work.md#device-owner-only) yönetme

Dosyayı test ettiğinizde, sonraki adım Intune'u kullanarak profili cihazlara dağıtmaktır.

- Bir cihaza bir veya birden çok MX profili dağıtabilirsiniz.
- Ayrıca, birden fazla StageNow profilini dışa aktarabilir ve ayarları tek bir XML dosyasında birleştirebilirsiniz. Daha sonra, cihazlarınıza dağıtmak için XML dosyasını Intune 'a yükleyin.

  > [!WARNING]
  > Aynı gruba birden çok MX profili hedeflenirse ve aynı özelliği yapılandırırsanız, cihazda çakışmalar olur.
  >
  > Aynı özellik tek bir MX profilinde birden çok kez yapılandırılmışsa, son yapılandırma kazanır.

## <a name="step-5-create-a-profile-in-intune"></a>5\. Adım: Intune 'da profil oluşturma

Intune'da cihaz yapılandırma profili oluşturun:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android**' i seçin.
    - **Profil türü**: **MX profili seçin (yalnızca zeköşeli)** .

4. **.xml biçiminde MX profili** alanında [StageNow'dan dışarı aktardığınız](#step-4-create-a-device-management-profile-in-stagenow) XML profil dosyasını ekleyin (bu makalede).
5. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. İlke oluşturulur ve listede gösterilir.

    > [!TIP]
    > Güvenlik nedeniyle, profil XML metnini kaydettikten sonra görmezsiniz. Metin şifrelenir ve siz yalnızca yıldız işaretleri (`****`) görürsünüz. MX profillerini Intune'a eklemeden önce, başvurabilmek için bu profillerin kopyalarını kaydetmeniz önerilir.

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

Cihazın yapılandırma güncelleştirmelerini bir sonraki denetleyişinde MX profili cihaza dağıtılır. Cihazlar kaydedildiğinde ve ardından yaklaşık her 8 saatte bir Intune'la eşitlenir. Ayrıca [Intune'da eşitlemeyi zorlayabilirsiniz](../remote-actions/device-sync.md). İsterseniz cihazda **Şirket Portalı uygulaması** > **Ayarlar** > **Eşitle**'yi de açabilirsiniz. 

## <a name="update-a-zebra-mx-configuration-after-its-assigned"></a>Atandıktan sonra Zeköşeli MX yapılandırmasını güncelleştirme

Bir Zeköşeli cihazın MX 'e özgü yapılandırmasını güncelleştirmek için şunları yapabilirsiniz: 

- Güncelleştirilmiş bir StageNow XML dosyası oluşturun, mevcut Intune MX profilini düzenleyin ve yeni StageNow XML dosyasını karşıya yükleyin. Bu yeni dosya profildeki önceki ilkenin üzerine yazar ve önceki yapılandırmanın yerini alır.
- Farklı ayarları yapılandıran yeni bir StageNow XML dosyası oluşturun, yeni bir Intune MX profili oluşturun, yeni StageNow XML dosyasını karşıya yükleyin ve aynı gruba atayın. Birden çok profil dağıtılır. Yeni profil var olan profillerde zaten mevcut olan ayarları yapılandırıyorsa, çakışmalar oluşur.

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
- [Zebra cihazlarının sorunlarını gidermek için StageNow günlüklerini kullanma](android-zebra-mx-logs-troubleshoot.md).
