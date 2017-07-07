---
title: "Bir Intune geçişi sırasında cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırma"
description: "Bu makalenin amacı, bir Intune geçişi sırasında cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırmak için gerekli adımları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e848dda6643a28141a8f5f1d0bdc01f2bd9d390
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a>Cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırma

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

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

Kullanıcı kimliği yerine cihazın kimliğine dayanan çeşitli yönetim görevleri gerçekleştirmeniz gerektiğinde, cihaz grupları oluşturabilirsiniz.

Cihaz grupları, bilgi noktası cihazları veya vardiya işçileri tarafından paylaşılan veya belirli bir konuma atanan cihazlar gibi özel kullanıcıları olmayan cihazları yönetmek için faydalıdır.

Cihaz gruplarını cihaz kaydı öncesinde yapılandırarak, grubun cihaz ilkelerini kayıt sırasında otomatik olarak alacak şekilde otomatik gruplandırması için cihaz kategorilerinden yararlanabilirsiniz. [Grupları kullanmaya başlama](/intune/groups-get-started).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>2. Görev: Kaynak erişim profillerini (Wi-Fi, VPN ve e-posta sertifikaları) kullanma

Kaynak erişim profilleri, sertifikalar sağlar ve kaydedilen cihazların yapılandırmalarına erişir.

Daha önce MDM gereksinimlerini değerlendirme bölümünde açıklandığı gibi sertifika tabanlı kimlik doğrulaması kullanıyorsanız, [sertifikaları yapılandırın](/intune/certificates-configure).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>3. Görev: Cihaz yapılandırma ilkeleri oluşturma ve dağıtma

Cihaz düzeyinde ayarları uygulamak için bir cihaz yapılandırma profili oluşturmanız gerekir, örneğin: Kamerayı devre dışı bırakma, uygulama mağazası, tek uygulama modu yapılandırma, giriş ekranı vb.

- [Cihaz profilleri](/intune/device-profiles) hakkında bilgi edinin.

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>iOS yapılandırma profillerinin doğrudan içeri aktarılması (isteğe bağlı)

-   **Apple Configurator iOS Profilleri (iOS 7.1 ve üzeri):** Mevcut MDM çözümünüz Apple Configurator profilleri (.mobileconfig dosyaları) kullanıyorsa Intune, bunları özel yapılandırma ilkeleri olarak doğrudan içeri aktarabilir.

-   **iOS Mobil Uygulama Yapılandırma ilkeleri:** Mevcut MDM çözümünüz iOS Mobil Uygulama Yapılandırma ilkeleri kullanıyorsa özellik listeleri için Apple'ın belirttiği XML biçimini karşıladıkları sürece Intune bunları doğrudan içeri aktarabilir.

- [iOS](/intune/custom-settings-ios) için özel bir ilke eklemeyi öğrenin

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>4. Görev: Cihaz uyumluluk ilkeleri oluşturma ve dağıtma (isteğe bağlı)

Cihaz uyumluluk ilkeleri güvenliğe yönelik ayarları değerlendirir ve cihazların kurumun standartlarına uyup uymadığını gösteren raporlama sağlar. Cihaz uyumluluk ilkeleri aşağıdaki gibi güvenliğe yönelik faktörleri değerlendirir:

-   PIN uzunluğu

-   Jailbreak uygulanma durumu

-   İşletim Sistemi Sürümü

Cihaz uyumluluk ayarları için ek kaynakları görün:

-   [Cihaz uyumluluk ilkeleri](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) hakkında bilgi edinin.

-   [Cihaz uyumluluk ilkesi oluşturmayı](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) öğrenin.

### <a name="task-5-publish-and-deploy-apps"></a>5. Görev: Uygulamaları yayımlama ve dağıtma

Intune MDM kullanırken, otomatik yükleme gerektirerek veya Şirket Portalında kullanılabilir hale getirerek uygulama sağlayabilirsiniz.

-   [Uygulama eklemeyi](/intune-classic/deploy-use/add-apps) öğrenin.

-   [Uygulama dağıtmayı](/intune-classic/deploy-use/deploy-apps) öğrenin.

### <a name="task-6-enable-device-enrollment"></a>6. Görev: Cihaz kaydını etkinleştirme

Kayıt, cihazda denetim sağlayarak yönetim oluşturur. [Şirkete ait ve kişisel cihazları kaydetmeye nasıl hazırlanılacağını](/intune/device-enrollment) öğrenin.

## <a name="next-steps"></a>Sonraki adımlar 

[Uygulama Koruma İlkelerini Yapılandırma (isteğe bağlı)](migration-guide-app-protection-policies.md)
