---
title: Bir Intune geçişi sırasında cihaz ve uygulama uyumluluğunu yapılandırma
titleSuffix: Microsoft Intune
description: Bu makale, bir Microsoft Intune geçişi sırasında cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırmak için gerekli adımları sağlar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 76c6000c375c3128c0832f3dd6b40fe1ed4cf34b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508236"
---
# <a name="configure-device-compliance-and-app-management-policies-when-migrating-to-microsoft-intune"></a>Microsoft Intune’a geçerken cihaz uyumluluk ve uygulama yönetimi ilkelerini yapılandırma

Intune’a geçiş sırasında asıl amaç, tüm cihazların Intune’a kaydedilmesini ve Intune ilkeleri ile uyumlu olmasını sağlamaktır. Cihaz ilkeleri yalnızca şirkete ait tek kullanıcılı cihazları yönetmeye değil, aynı zamanda bilgi noktaları, satış noktası makineleri, bir sınıfta birden çok öğrenci arasında paylaşılan tabletler veya kullanıcısız cihazlar (yalnızca iOS) gibi kişisel (KCG) ve paylaşılan cihazları yönetmeye yardımcı olur.

Her cihaz platformu farklı ayarlar sunabilir, ancak Intune cihaz ilkeleri aşağıdaki mobil cihaz yönetimi özelliklerini sağlayarak her cihaz platformu ile çalışır:

-   Her kullanıcının kaydettiği cihaz sayısını düzenlemek.

-   Cihaz ayarlarını (cihaz düzeyinde şifreleme, parola uzunluğu, kamera kullanımı gibi) yönetme.

-   Uygulama, e-posta profilleri, VPN profilleri vb. sunma.

-   Güvenlik uyumluluk ilkeleri için cihaz düzeyinde ölçütleri değerlendirmek.

> [!IMPORTANT]
> Cihaz yönetimi ilkeleri doğrudan bağımsız cihazlara veya kullanıcılara atanmaz, bunun yerine kullanıcı gruplarına atanır. Bu ilkeler doğrudan bir kullanıcı grubuna ve dolayısıyla kullanıcı cihazına uygulanabilir veya ilkeler bir cihaz grubuna ve dolayısıyla grup üyelerine uygulanabilir.

## <a name="task-list-for-device-compliance-policies"></a>Cihaz uyumluluk ilkeleri için görev listesi

### <a name="task-1-add-device-groups-optional"></a>1. Görev: (İsteğe bağlı) cihaz gruplarına Ekle

Kullanıcı kimliği yerine cihaz kimliğine dayanan yönetim görevleri gerçekleştirmeniz gerektiğinde, cihaz grupları oluşturabilirsiniz.

Cihaz grupları; bilgi noktası cihazları, vardiya işçileri tarafından paylaşılan cihazlar veya belirli bir konuma atanan cihazlar gibi belirli kullanıcıları olmayan cihazları yönetmek için kullanılır.

Cihaz kaydından önce cihaz gruplarını yapılandırırsanız cihaz kategorilerini kullanabilir ve cihazların kayıttan sonra otomatik olarak gruplara katılmasını sağlayabilirsiniz. Böylece bu cihazlar, gruplarının cihaz ilkelerini otomatik olarak alır. [Grupları kullanmaya başlama](groups-get-started.md).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>2. Görev: Kaynak erişim profillerini (Wi-Fi, VPN ve e-posta sertifikaları) kullanma

Kaynak erişim profilleri, sertifikalar sağlar ve kaydedilen cihazların yapılandırmalarına erişir. Sertifika tabanlı kimlik doğrulaması kullanıyorsanız [sertifikaları yapılandırın](certificates-configure.md).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>3. Görev: Cihaz yapılandırma profilleri oluşturabilir ve dağıtabilirsiniz

Cihaz düzeyinde ayarları uygulamak için bir cihaz yapılandırma profili oluşturmanız gerekir, örneğin kamerayı devre dışı bırakma, uygulama mağazası, tek uygulama modu yapılandırma, giriş ekranı vb. [Cihaz profilleri](device-profiles.md) hakkında bilgi edinin.

####  <a name="directly-import-ios-configuration-profiles-optional"></a>iOS yapılandırma profillerini doğrudan içeri aktarma (isteğe bağlı)

-   **Apple Configurator iOS profilleri (iOS 7.1 ve üzeri):** Mevcut MDM çözümünüz Apple Configurator profilleri (.mobileconfig dosyaları) kullanıyorsa Intune bunları doğrudan özel yapılandırma ilkeleri olarak içeri aktarabilir.

-   **iOS mobil uygulama yapılandırma ilkeleri:** Mevcut MDM çözümünüz iOS mobil uygulama yapılandırma ilkeleri kullanıyorsa özellik listeleri için Apple'nın belirttiği XML biçimini karşıladıkları sürece Intune bunları doğrudan içeri aktarabilir.

- [iOS](custom-settings-ios.md) için özel bir ilke eklemeyi öğrenin.

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Görev 4: (İsteğe bağlı) cihaz uyumluluk ilkeleri oluşturma ve dağıtma

Cihaz uyumluluk ilkeleri, güvenliğe yönelik ayarları değerlendirir ve cihazların kuruluş standartlarına uyup uymadığını gösteren raporlar sağlar. Bu ayarlar şunlardır:

-   PIN uzunluğu

-   Jailbreak uygulanma durumu

-   İşletim sistemi sürümü

Cihaz uyumluluk ayarları için ek kaynakları görün:

-   [Cihaz uyumluluk ilkeleri](device-compliance.md) hakkında bilgi edinin.

-   [Cihaz uyumluluk ilkesi oluşturmayı](device-compliance-get-started.md) öğrenin.

### <a name="task-5-publish-and-deploy-apps"></a>Görev 5: Uygulamalarını yayımlama ve dağıtma

Intune MDM kullanırken, uygulamaların otomatik yüklenmesini gerektirerek veya bunları Şirket Portalı’nda sunarak uygulama sağlayabilirsiniz.

-   [Uygulama ekleme](apps-add.md).

-   [Uygulama dağıtma](apps-deploy.md).

### <a name="task-6-enable-device-enrollment"></a>6. Görev: Cihaz kaydını etkinleştirme

Cihazı yönetmek için cihaz kaydı gereklidir. [Şirkete ait ve kişisel cihazları kaydetmeye nasıl hazırlanılacağını](device-enrollment.md) öğrenin.

## <a name="next-steps"></a>Sonraki adımlar

[Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)](migration-guide-app-protection-policies.md).
