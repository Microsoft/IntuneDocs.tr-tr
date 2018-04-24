---
title: Genel sorun giderme ipuçları
description: Intune’la ilgili sorunları çözmeye yardımcı olan genel kaynaklar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/08/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d5d55f6c3efabdde51b5627d5ddd409c2b282f6c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Microsoft Intune için genel sorun giderme ipuçları

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune dağıtıldıktan sonra yapılandırmanızla veya istemci cihazlarıyla ilgili sorunlarla karşılaşabilirsiniz. Sorunu çözebilmeniz için soruna neden olan şeyi bulmanıza yardımcı olması için aşağıdaki kaynakları kullanın.

> [!NOTE]
> Destek isteği oluşturmak veya mevcut isteği görüntülemek için [Office 365 yönetim merkezini ziyaret edin](https://portal.office.com/admin/default.aspx). Destek seçenekleri hakkında daha fazla bilgi için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## <a name="define-the-problem"></a>Sorunu tanımlama

-   Davranış nedir?

-   Bu davranışla kim, hangi platformlarda ve cihazlarda karşılaşıyor?

-   Cihaz daha önce düzgün çalışıyor muydu?

-   Intune veya cihaz yapılandırmasında hangi değişiklikleri yaptınız?

-   Çalıştığınız ortamda yapılandırma değişikliklerinden başka değişiklikler yapıldı mı?

-   Bu sorun ne sıklıkla oluşuyor ve aralıklı mı, sürekli mi?

-   Kullanıcı bir kimlik doğrulama sorunu yaşıyor olabilir mi? Böyle bir olasılık varsa kullanıcının Azure Active Directory kullanan diğer hizmetlerde oturum açıp açamadığını denetleyin. Ayrıca, kullanıcının farklı bir cihazdan oturum açıp açamadığına bakın.

-   Hizmet durumunu denetlediniz mi? [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx) Intune hizmet durumunu izleyebilirsiniz. Sol bölmede **Hizmet Durumu**’nu seçin.

## <a name="collect-available-data"></a>Kullanılabilir verileri topla

- Aşağıdaki kaynaklar cihaz günlüklerini nasıl toplayacağınızı öğrenmenize yardımcı olabilir:
  - [Android tanılama veri günlüklerini USB kablosu kullanarak BT yöneticinize gönderme](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Android kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [iOS kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-errors-to-your-it-admin-ios)

- Örneğin, ilke uygulama sorunlarına yönelik yönetici konsolu verileri için [Microsoft Intune ile kullanıcı ve cihazları yönetmek için grupları kullanma](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) bölümünde açıklandığı gibi amaçlanan ilkeyi ve ilgili ilkenin durumunu inceleyin.

## <a name="research-the-solution"></a>Çözümü arayın

-   Web’de bir çözüm arayın. Örneğin, 0x80073CF0 hatasını alırsanız Web’de **technet intune 0x80073cf0** araması yaparak [Microsoft Intune’da uygulama dağıtım sorunlarını giderme](troubleshoot-app-deployment-problems-in-microsoft-intune.md) makalesini bulabilirsiniz. Bu makale, bu sorunu çözmeye yönelik öneriler sunar.

-   [Intune TechNet Forumu](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)’nda bir yanıt arayın.  Sorun daha önce çözülmemişse topluluğun sunabileceği önerileri görmek için soruyu gönderin.

-   Bir destek isteği açın. Sorunu tanımlayıp kullanılabilir verileri topladıktan sonra Intune Desteği sorunu çözmenize daha iyi yardımcı olabilecektir.

    Destek isteği oluşturmak için [Office 365 yönetim merkezini ziyaret edin](https://portal.office.com/admin/default.aspx). Destek seçenekleri hakkında daha fazla bilgi için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## <a name="find-community-resources"></a>Topluluk kaynakları bulma
Bu topluluk kaynaklarında başka yararlı bilgiler bulabilirsiniz.

-   [Microsoft Intune Hayatta Kalma Kılavuzu](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx), Intune ürününü yapılandırmanıza, korumanıza ve ürünle ilgili sorunları gidermenize yardımcı olabilecek birçok kaynağa bağlantı içerir.

-   [Intune blogu](http://blogs.technet.com/b/windowsintune/)

-   [Intune’u Twitter'da takip edin](https://twitter.com/MSIntune)

-   [Intune forumları](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Sonraki adımlar
Aşağıdaki konular, belirli konular için sorun giderme yardımına sahiptir. Bu bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.

[Microsoft Intune’da Endpoint Protection Sorunlarını Giderme](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Microsoft Intune ile şirket kaynak erişimi sorunlarını giderme](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Microsoft Intune’da uygulama dağıtımı sorunlarını giderme](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Intune’da cihaz kaydı sorunlarını giderme](troubleshoot-device-enrollment-in-intune.md)

[Microsoft Intune’da ilke sorunlarını giderme](troubleshoot-policies-in-microsoft-intune.md)

[Microsoft Intune’da istemci kurulumu sorunlarını giderme](troubleshoot-client-setup-in-microsoft-intune.md)

[Microsoft Intune’da yazılım güncelleştirmesi sorunlarını giderme](troubleshoot-software-updates-in-microsoft-intune.md)
