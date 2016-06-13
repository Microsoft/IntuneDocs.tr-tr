---
# required metadata

title: Genel sorun giderme ipuçları | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune için genel sorun giderme ipuçları
Microsoft Intune dağıtıldıktan sonra yapılandırmanızla veya istemcilerinizle ilgili sorunlarla karşılaşabilirsiniz. Aşağıdaki kaynaklar, sorunu çözebilmek amacıyla sorunun nedenini bulmanıza yardımcı olabilir.

> [!NOTE]
> Destek isteği oluşturmak veya mevcut isteği görüntülemek için [Office 365 yönetim merkezini ziyaret edin](https://portal.office.com/admin/default.aspx). Destek seçenekleri hakkında daha fazla bilgi için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).
## Sorunu tanımlama

-   Davranış nedir?

-   Bu davranışla kim, hangi platformlarda ve cihazlarda karşılaşıyor?

-   Cihaz daha önce düzgün çalışıyor muydu?

-   Intune veya cihaz yapılandırmasında hangi değişiklikleri yaptınız?

-   Çalıştığınız ortamda yapılandırma değişikliklerinden başka değişikliklerin yapılıp yapılmadığını düşünün.

-   Bu sorun ne sıklıkla oluşuyor ve aralıklı mı, sürekli mi?

-   Kullanıcı bir kimlik doğrulama sorunu yaşıyor olabilir mi? Böyle bir olasılık varsa kullanıcının Azure Active Directory kullanan diğer hizmetlerde oturum açıp açamadığını denetleyin. Ayrıca, kullanıcının farklı bir cihazdan oturum açıp açamadığına bakın.

-   Hizmet durumunu denetlediniz mi? [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx) Intune hizmet durumunu izleyebilirsiniz. Sol bölmede **Hizmet Durumu**’nu seçin. 

## Kullanılabilir verileri topla

-   Cihaz günlükleri. Cihaz günlüklerinin nasıl toplanacağını öğrenin:
  - [Android tanılama veri günlüklerini USB kablosu kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [BT yöneticinize Android kayıt hatalarını gönderme](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [BT yöneticinize iOS kayıt hataları gönderin](/intune/enduser/send-errors-to-your-it-admin-ios.md)

-   Örneğin, ilke uygulama sorunlarına yönelik yönetici konsolu verileri için [Microsoft Intune ile kullanıcı ve cihazları yönetmek için grupları kullanma](/indune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) bölümünde açıklandığı gibi amaçlanan ilkeyi ve ilgili ilkenin durumunu incelemeniz gerekir.

## Çözümü arayın

-   Web’de bir çözüm arayın. Örneğin, 0x80073CF0 hatasını alırsanız Web’de **technet intune 0x80073cf0** araması yaparak, bu sorunu çözmeye yönelik öneriler sunan [Microsoft Intune’da uygulama dağıtım sorunlarını giderme](troubleshoot-app-deployment-problems-in-microsoft-intune.md) makalesini bulabilirsiniz.

-   [Intune TechNet Forumu](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)’nda bir yanıt arayabilirsiniz.  Sorun daha önce çözülmemişse topluluğun sunabileceği önerileri görmek için soruyu göndermeniz gerekir.

-   Bir destek isteği açabilirsiniz. Sorunu tanımlayıp kullanılabilir verileri topladığınızda Intune Desteği sorunu çözmenize daha iyi yardımcı olabilecektir.

    Destek isteği oluşturmak için [Office 365 yönetim merkezini ziyaret edin](https://portal.office.com/admin/default.aspx). Destek seçenekleri hakkında daha fazla bilgi için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## Topluluk kaynakları
Bu topluluk kaynaklarında başka yararlı bilgiler bulabilirsiniz.

-   [Microsoft Intune Hayatta Kalma Kılavuzu](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx), Intune ürününü yapılandırmanıza, korumanıza ve ürünle ilgili sorunları gidermenize yardımcı olabilecek birçok kaynağa bağlantı içerir.

-   [Intune web günlüğü](http://blogs.technet.com/b/windowsintune/)

-   [Intune’u Twitter'da takip edin](https://twitter.com/MSIntune)

-   [Intune forumları](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### Sonraki adımlar
Aşağıda listelenen konular, belirli konular için sorun giderme yardımına sahiptir. Bu bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Microsoft Intune ile şirket kaynak erişimi sorunlarını giderme](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Microsoft Intune’da uygulama dağıtım sorunlarını giderme](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Intune’da cihaz kaydıyla ilgili sorunları giderme](troubleshoot-device-enrollment-in-intune.md)

[Microsoft Intune’da ilke sorunlarını giderme](troubleshoot-policies-in-microsoft-intune.md)

[Microsoft Intune’da istemci kurulumu sorunlarını giderme](troubleshoot-client-setup-in-microsoft-intune.md)

[Microsoft Intune’da yazılım güncelleştirmesi sorunlarını giderme](troubleshoot-software-updates-in-microsoft-intune.md)


<!--HONumber=May16_HO4-->


