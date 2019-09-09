---
title: Microsoft Intune-Azure 'da cihaz eylemlerinin sorunlarını giderme | Microsoft Docs
description: Cihaz eylemi sorunlarını giderme konusunda yardım alın.
keywords: ''
author: erikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 159e236a079adcd55ba73e8fea6f786c09d08bbd
ms.sourcegitcommit: 73fbecf7cee4fdfc37d3c30ea2007d2a9a6d2d12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2019
ms.locfileid: "68757881"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Intune 'da cihaz eylemlerinin sorunlarını giderme

Microsoft Intune, cihazlarınıza yardımcı olacak çok sayıda eyleme sahiptir. Bu makalede, cihaz eylemleriyle ilgili sorunları gidermenize yardımcı olabilecek bazı yaygın soruların yanıtları sağlanmaktadır.

## <a name="bypass-activation-lock-action"></a>Etkinleştirme Kilidi eylemini atla

### <a name="i-clicked-the-bypass-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>Portalda "Etkinleştirme Kilidi atla" eylemine tıkladım, ancak cihazda hiçbir şey yapılmadı.
Bu beklenen bir değer. Etkinleştirme Kilidi atlama eylemini başlattıktan sonra, Intune Apple 'dan güncelleştirilmiş bir kod istedi. Cihazınız Etkinleştirme Kilidi ekranında olduktan sonra kodu geçiş kodu alanına el ile girersiniz. Bu kod yalnızca 15 gün için geçerlidir. bu nedenle, silme işlemini gerçekleştirmeden önce eyleme tıkladıktan sonra kodu kopyalamanız gerekir.

### <a name="why-dont-i-see-the-bypass-activation-lock-code-in-the-hardware-overview-blade-of-my-ios-device"></a>İOS cihazımın donanımla genel bakış dikey penceresinde atlama Etkinleştirme Kilidi kodunu neden görmüyorum?
En olası nedenler şunlardır:
- Kodun süresi doldu ve hizmetten temizlendi.
- Cihaz, Etkinleştirme Kilidi izin vermek için cihaz kısıtlama Ilkesiyle denetlenmiyor.

Aşağıdaki sorguyla Graph Explorer 'da kodu kontrol edebilirsiniz:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-bypass-activation-lock-action-greyed-out-for-my-ios-device"></a>Kapatma Etkinleştirme Kilidi eylemi, iOS cihazımın neden gri renkte?
En olası nedenler şunlardır: 
- Kodun süresi doldu ve hizmetten temizlendi.
- Cihaz, Etkinleştirme Kilidi izin vermek için cihaz kısıtlama Ilkesiyle denetlenmiyor.

### <a name="is-the-bypass-activation-lock-code-case-sensitive"></a>Atlama Etkinleştirme Kilidi kodu büyük/küçük harfe duyarlıdır mi?
Hayır. Ve kısa çizgileri girmeniz gerekmez.

## <a name="remove-devices-action"></a>Cihazları kaldır eylemi

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Nasıl yaparım? devre dışı bırakmayı/silmeyi kimin başlatdığına söylüyorsunuz?
**Intune** > **cihazlar** cihaz eylemleri ' ne gidin > tarafından başlatılan sütununa bakın. > 
Giriş görmüyorsanız, eylemi başlatan en olası kişi cihazın kullanıcısı olur. Büyük olasılıkla Şirket Portalı uygulamasını veya portal.manage.microsoft.com kullandık.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Uygulamam kullanımdan kaldırıldıktan sonra neden kaldırılamadı?
Yönetilen bir uygulama olarak kabul edilmedi. Bu bağlamda, yönetilen bir uygulama, Intune hizmeti kullanılarak yüklenen bir uygulamadır. Buna aşağıdakiler dahildir:
- Uygulama gerektiği şekilde dağıtıldı
- Uygulama kullanılabilir olarak dağıtıldı ve sonra Şirket Portalı uygulamasının içinden Son Kullanıcı tarafından yüklendi.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Android kurumsal Iş profili cihazlarında neden gri renkte görünüyor?
Bu beklenen bir davranıştır. Google, Iş profili cihazlarının MDM sağlayıcısından fabrika ayarlarına sıfırlamaya izin vermez.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Aygıtım kullanımdan kaldırıldıktan sonra neden Office uygulamalarıma yeniden oturum açamıyorum?
Bir cihazı devre dışı bırakma, erişim belirteçlerini iptal etmez. Bu durumu azaltmak için koşullu erişim ilkelerini kullanabilirsiniz.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Devre dışı bırakma/silme eylemini verildikten sonra nasıl izleyebilirim?
**Intune** > cihazlarcihaz > **eylemleri**' ne gidin.

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Wpes neden bazen süresiz olarak bekliyor olarak gösterilmelidir?
Cihazların durumu, sıfırlama başlatılmadan önce her zaman Intune hizmetine rapor vermez. Bu nedenle, eylem beklemede olarak gösterilir. Eylemi başarıyla onayladıysanız, cihazı hizmetten silin.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>Çevrimdışı bir cihazda ya da bir süredir hizmetle iletişim kurmayan bir cihazda devre dışı bırakma/silme başladığımda ne olur?
MDM sertifikasının süresi dolana kadar cihaz **devre dışı bırakma/silme bekleniyor** durumunda kalır. MDM sertifikası, kayıt sonrasında bir yılda sürer ve her yıl otomatik olarak yenilenir. MDM sertifikasının süresi dolmadan önce cihaz iade ettiğinde, devre dışı bırakılır/silinir. MDM sertifikasının süresi dolmadan önce cihazın iade edilmemesi durumunda hizmet iade edemeyecektir. MDM sertifikasının süresi dolduktan 180 gün sonra cihaz Azure portal otomatik olarak kaldırılır.


## <a name="reset-passcode-action"></a>Geçiş kodunu Sıfırla eylemi

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Android cihaz Yöneticimde kayıtlı cihazımın geçiş kodu sıfırlama eylemi neden gri renkte?
Ransom Ware 'de, Google, Cihaz Yöneticisi API 'sindeki geçiş kodu sıfırlama özelliğini kaldırdı (Android sürüm 7,0 veya üzeri cihazlar için geçerlidir).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Android 8,0 veya sonraki bir Iş profili kayıtlı cihazımın parolasını sıfırlama izni verdiğinizde neden "desteklenmiyor" iletisini alıyorum?
Sıfırlama belirteci cihazda etkinleştirilmediği için. Sıfırlama belirtecini etkinleştirmek için:
1. Yapılandırma Ilkenizde bir Iş profili geçiş kodu gerekir.
2. Son kullanıcının uygun bir Iş profili geçiş kodu ayarlaması gerekir.
3. Son kullanıcının, geçiş kodu sıfırlamasına izin vermek için ikincil istemi kabul etmesi gerekir.
Bu adımlar tamamlandıktan sonra, artık bu yanıtı almamanız gerekir.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-ios-device-when-i-issue-the-remove-passcode-action"></a>Geçiş kodunu kaldır eylemini yayındığımda, neden iOS cihazmda yeni bir geçiş kodu ayarlayacağım?
Uyumluluk ilkelerinizin bir geçiş kodu gerektirdiğinden.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft 'un destek yardımına](get-support.md)ulaşın veya [topluluk forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune)kullanın.