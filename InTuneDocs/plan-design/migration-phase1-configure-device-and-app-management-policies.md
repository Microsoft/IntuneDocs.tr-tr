---
title: "Bir Intune geçişi sırasında cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırma | Microsoft Docs"
description: "Bu makalenin amacı, bir Intune geçişi sırasında cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırmak için gerekli adımları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 5904b117ccab9046d2afde4a761b4724431a6302
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>1. Aşama: Cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırma

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Intune’a geçiş sırasında asıl amaç tüm cihazların kayıtlı olmasını ve ilkeleri ile uyumlu olmasını sağlamaktır. Cihaz ilkeleri yalnızca şirkete ait tek kullanıcı cihazlarını yönetmeye değil, aynı zamanda bilgi noktaları, satış noktası makineleri, bir sınıfta birden çok öğrenci arasında paylaşılan tabletler veya kullanıcısız cihazlar (yalnızca iOS) gibi kişisel (KCG) ve paylaşılan cihazları yönetmeye yardımcı olmaktadır.

Her cihaz platformu farklı ayarlar sunabilir, ancak Intune cihaz ilkeleri aşağıdaki mobil cihaz yönetimi özelliklerini sağlayarak her cihaz platformu ile çalışır:

-   Her kullanıcının kaydettiği cihaz sayısını düzenlemek.

-   Cihaz ayarlarını yönetmek (örneğin cihaz düzeyinde şifreleme, parola uzunluğu, kamera kullanımı).

-   Uygulama, e-posta profilleri, VPN profilleri vb. sunmak.

-   Güvenlik uyumluluk ilkeleri için cihaz düzeyinde ölçütleri değerlendirmek.

> [!IMPORTANT]
> Cihaz yönetimi ilkeleri doğrudan bağımsız cihazlara veya kullanıcılara atanmaz, bunun yerine kullanıcı gruplarına atanır. Bu ilkeler doğrudan bir kullanıcı grubuna ve dolayısıyla kullanıcı cihazına uygulanabilir veya ilkeler bir cihaz grubuna ve dolayısıyla grup üyelerine uygulanabilir.

## <a name="task-list-for-device-compliance-policies"></a>Cihaz uyumluluk ilkeleri için görev listesi

### <a name="task-1-add-device-groups-optional"></a>1. Görev: Cihaz grupları oluşturma (isteğe bağlı)

[Klasik Intune portalı](https://manage.microsoft.com/), çeşitli yönetim görevlerini kullanıcı kimliği yerine cihaz kimliği tabanlı olarak gerçekleştirmeniz gerektiğinde cihaz grupları oluşturma becerisi sunar.

Cihaz grupları, bilgi noktası cihazları veya vardiya işçileri tarafından paylaşılan veya belirli bir konuma atanan cihazlar gibi özel kullanıcıları olmayan cihazları yönetmek için faydalıdır.

Cihaz gruplarını cihaz kaydı öncesinde yapılandırarak, grubun cihaz ilkelerini kayıt sırasında otomatik olarak alacak şekilde otomatik gruplandırması için cihaz kategorilerinden yararlanabilirsiniz.

-   [Cihaz grupları eklemeyi](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5) öğrenin.

-   [Cihaz kategorilerini yapılandırmayı](https://docs.microsoft.com/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) öğrenin.

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>2. Görev: Kaynak erişim profillerini (Wi-Fi, VPN ve e-posta sertifikaları) kullanma

Kaynak erişim profilleri, sertifikalar sağlar ve kaydedilen cihazların yapılandırmalarına erişir.

MDM Değerlendirme gereksinimleri bölümünde daha önce bahsedildiği gibi, sertifika tabanlı kimlik doğrulaması kullanıyorsanız VPN, Wi-Fi ve e-posta sertifikaları dağıtmak için bir [PKI altyapısına sahip olmanız](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) gerekir.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Kaynak erişim profillerinin doğrudan içeri aktarılması (isteğe bağlı)

Mevcut MDM çözümünüz e-posta, Wi-Fi ve VPN profillerini XML biçiminde dışarı aktarmanıza olanak tanıyan bir mekanizma sağlıyorsa iOS, Android ve Windows cihazlar için özel profiller oluşturmak üzere OMA-URI kullanarak XML dosyasını Intune’a içeri aktarabilirsiniz.

-   [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune), [Android](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune) ve [Windows](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) cihazlar için özel ilke eklemeyi öğrenin.

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>3. Görev: Cihaz yapılandırma ilkeleri oluşturma ve dağıtma

Cihaz düzeyinde ayarları uygulamak için bir cihaz yapılandırma profili oluşturmanız gerekir, örneğin: Kamerayı devre dışı bırakma, uygulama mağazası, tek uygulama modu yapılandırma, giriş ekranı vb.

- [Cihaz yapılandırma ilkeleri](https://docs.microsoft.com/intune-azure/configure-devices/how-to-create-device-profiles) hakkında bilgi edinin.

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>iOS yapılandırma profillerinin doğrudan içeri aktarılması (isteğe bağlı)

-   **Apple Configurator iOS Profilleri (iOS 7.1 ve üzeri):** Mevcut MDM çözümünüz Apple Configurator profilleri (.mobileconfig dosyaları) kullanıyorsa Intune, bunları özel yapılandırma ilkeleri olarak doğrudan içeri aktarabilir.

-   **iOS Mobil Uygulama Yapılandırma ilkeleri:** Mevcut MDM çözümünüz iOS Mobil Uygulama Yapılandırma ilkeleri kullanıyorsa özellik listeleri için Apple'ın belirttiği XML biçimini karşıladıkları sürece Intune bunları doğrudan içeri aktarabilir.

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings) için özel bir ilke eklemeyi öğrenin

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>4. Görev: Cihaz uyumluluk ilkeleri oluşturma ve dağıtma (isteğe bağlı)

Cihaz uyumluluk ilkeleri güvenliğe yönelik ayarları değerlendirir ve cihazların kurumun standartlarına uyup uymadığını gösteren raporlama sağlar. Cihaz uyumluluk ilkeleri aşağıdaki gibi güvenliğe yönelik faktörleri değerlendirir:

-   PIN uzunluğu

-   Jailbreak uygulanma durumu

-   İşletim Sistemi Sürümü

Cihaz uyumluluk ayarları için ek kaynakları görün:

-   [Cihaz uyumluluk ilkeleri](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) hakkında bilgi edinin.

-   [Cihaz uyumluluk ilkesi oluşturmayı](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) öğrenin.

### <a name="task-5-publish-and-deploy-apps"></a>5. Görev: Uygulamaları yayımlama ve dağıtma

Intune MDM kullanırken, otomatik yükleme gerektirerek veya Şirket Portalında kullanılabilir hale getirerek uygulama sağlayabilirsiniz.

-   [Uygulama eklemeyi](https://docs.microsoft.com/intune/deploy-use/add-apps) öğrenin.

-   [Uygulama dağıtmayı](https://docs.microsoft.com/intune/deploy-use/deploy-apps) öğrenin.

### <a name="task-6-enable-device-enrollment"></a>6. Görev: Cihaz kaydını etkinleştirme

Kayıt, cihazda denetim sağlayarak yönetim oluşturur.

-   [Şirkete ait ve kişisel cihazları kaydetmeye nasıl hazırlanılacağını](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune) öğrenin.

-   [Şirkete ait cihazları kaydetmeyi](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) öğrenin.

Paylaşılan veya kullanıcısız cihazları kaydetmeniz gerekirse bir [cihaz kayıt yöneticisi (DEM) hesabı](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) kullanabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar 

[1. Aşama: Uygulama Koruma İlkelerini Yapılandırma (isteğe bağlı)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

