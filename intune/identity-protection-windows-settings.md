---
title: Windows Hello for Business ayarları Microsoft Intune - Azure | Microsoft Docs
description: Tüm PIN, biyometrik ve kimlik koruma profilinde sahtekarlığına karşı koruma ayarlarını kullanmak için Windows Hello iş için Windows 10 cihazlarda Microsoft Intune Yapılandır listesini bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bbdb56770c154a482ad004f1f3f980809424caf
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848517"
---
# <a name="windows-10-and-newer-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Windows iş için Hello ıntune'da etkinleştirmek için Windows 10 (ve üzeri) cihaz ayarları

Bu makale listeler ve Windows Hello for Business ayarları kontrol edebilirsiniz ıntune'da Windows 10 cihazlarında açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarlar, oturum açmak için bir PIN veya parmak izi kullanmayı ve daha fazlasını kullanın.

Bir Intune Yöneticisi olarak oluşturun ve bu ayarlar Windows 10 ve üzeri cihazlar için atayın.

Intune'da iş profilleri hakkında daha fazla Windows Hello bilgi edinmek için [kimlik Koruması'nı yapılandırma](identity-protection-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir yapılandırma profili oluşturma](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello

- **İş için Windows Hello yapılandırma**: Bu özelliği kullanın ve ayarlarını yapılandırmak için seçin **etkinleştirme**.
- **Minimum PIN uzunluğu**: Cihazlara izin vermek istediğiniz en düşük PIN uzunluğu girin. Varsayılan PIN uzunluğu altı karakterdir. Minimum PIN uzunluğu dört (4) karakterdir.
- **Maksimum PIN uzunluğu**: Cihazlara izin vermek istediğiniz maksimum PIN uzunluğu girin. Varsayılan PIN uzunluğu altı (6) karakter olabilir. Maksimum PIN uzunluğu 127 karakterdir.  
- **PIN kodunda küçük harfler**: Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir küçük harf içerir. Seçenekleriniz şunlardır:

  - **İzin** (varsayılan): Kullanıcılar PIN kodlarında küçük harf kullanmasını engeller. Bu davranış, ayar yapılandırılmazsa da oluşur.
  - **İzin verilen**: Kullanıcıların PIN kodunda küçük harf kullanın, ancak gerekli değildir.
  - **Gerekli**: Kullanıcılar PIN kodlarına en az bir küçük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

- **Pın'de büyük harfler PIN**: Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir büyük harf içermesi. Seçenekleriniz şunlardır:

  - **İzin** (varsayılan): Kullanıcıların PIN kodunda büyük harfler kullanmasını engelleyin. Bu davranış, ayar yapılandırılmazsa da oluşur.
  - **İzin verilen**: Kullanıcıların PIN kodunda büyük harfler kullanın, ancak gerekli değildir.
  - **Gerekli**: Kullanıcılar PIN kodlarına en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

- **PIN kodunda özel karakterler**: Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir özel karakterler şunlardır. Seçenekleriniz şunlardır:

  - **İzin** (varsayılan): PIN kodunda özel karakterler kullanarak kullanıcıların engelleyin. Bu davranış, ayar yapılandırılmazsa da oluşur.
    Özel karakterler şunlardır: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **İzin verilen**: Kullanıcıların PIN kodunda büyük harfler kullanın, ancak gerekli değildir.
  - **Gerekli**: Kullanıcılar PIN kodlarına en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

- **PIN süre sonu (gün)**: Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür.

- **PIN geçmişini anımsa**: Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Varsayılan olarak, son 5 PIN kodunun yeniden kullanılamaz.  
- **PIN kurtarmayı etkinleştir**: Windows Hello için kurtarma hizmeti iş PIN kullanarak kendi PIN'LERİNİ değiştirmesine izin verir.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Güvenilir Platform Modülü (TPM) kullan**: TPM yongası ek bir veri güvenliği katmanı sağlar. Aşağıdaki değerlerden birini seçin:  
  - **Etkinleştirme**: Yalnızca erişilebilir bir TPM’si olan cihazlar İş İçin Windows Hello sağlayabilir.
  - **Yapılandırılmamış**: Kullanılabilir bir TPM olmadığında bile tüm cihazlar İş İçin Windows Hello sağlayabilir. Cihazlar önce bir TPM kullanmayı dener ancak başaramazsa yazılım şifrelemesi kullanır.  

- **Biyometrik kimlik doğrulamasına izin**: İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

  - **Etkinleştirme**: İş İçin Windows Hello biyometrik kimlik doğrulamasına izin verir.
  - **Yapılandırılmamış** (varsayılan): İş İçin Windows Hello, (tüm hesap türleri için) biyometrik kimlik doğrulamasını engeller.

- **Gelişmiş yanıltma, kullanılabilir olduğunda kullanın**: Sahtekarlığına karşı koruma özelliklerinin Windows Hello bunu destekleyen cihazlarda kullanılıp kullanılmadığını seçin. Örneğin, bir yüz yerine gerçek bir resmini algılayın.

  - **Etkinleştirme**: Windows, yüz özellikleri destekleniyorsa bunun için tüm kullanıcıların yanıltmaya karşı koruma kullanmasını gerektirir.  
  - **Yapılandırılmamış** (varsayılan): Windows, cihazdaki yanıltmaya karşı koruma yapılandırmalarını kabul eder.

- **Şirket içi kaynaklar için sertifika**: 

  - **Etkinleştirme**: İş İçin Windows Hello’nun şirket içi kaynaklarda kimlik doğrulaması için sertifika kullanmasına izin verir.
  - **Yapılandırılmamış** (varsayılan): İş İçin Windows Hello’nun şirket içi kaynaklarda kimlik doğrulaması için sertifika kullanmasını önler.  

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
