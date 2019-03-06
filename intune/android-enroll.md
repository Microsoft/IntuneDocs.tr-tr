---
title: Intune’da Android cihazları kaydetme
titlesuffix: Microsoft Intune
description: Intune’da Android cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/31/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 486b5295d6ab4241cae90ef6ce0274fc93e0085e
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393248"
---
# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak, aşağıdaki Android cihazları yönetebilirsiniz:
- Samsung Knox Standard cihazlar dahil olmak üzere Android cihazlar.
- Dahil olmak üzere android Kurumsal cihaz:
    - **Android kurumsal iş profili cihazları**: Kişisel cihazlarından Kurumsal verilere erişim izni verildi. Yöneticileri, iş hesapları, uygulamaları ve verileri yönetebilir. Cihazdaki kişisel verileri iş verilerinizden ayrı tutulur ve yöneticileri, kişisel ayarlar veya veri denetim yok. 
    - **Android Kurumsal adanmış cihazlar**: Dijital Tabela gibi şirketin sahip olduğu ve tek kullanım cihazları yazdırma bilet veya Stok yönetim. Yöneticiler bir cihazın kullanımını sınırlı sayıda uygulama ve web bağlantısına indirger. Ayrıca kullanıcılar başka uygulama ekleyemez veya farklı eylemler gerçekleştiremez.
    - **Android Kurumsal tam olarak yönetilen cihazlar**: Şirketin sahip olduğu, tek kullanıcı cihazlarını iş için özel olarak kullanılan ve değil kişisel kullanın. Yöneticileri tüm cihazı yönetebilir ve zorunlu ilke denetimleri iş profilleri kullanılamıyor. 

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlayabilirsiniz.

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak izin verir. Önkoşulu sağladıktan sonra yöneticilerin yapacağı tek şey [kullanıcılarına cihazlarını nasıl kaydedeceklerini anlatmak](/intune-user-help/enroll-your-device-in-intune-android) olacaktır.

Bir kullanıcı kaydolduktan sonra [uyumluluk ilkeleri atama](compliance-policy-create-android.md), [uygulamaları yönetme](app-management.md) ve daha fazlası dahil olmak üzere kullanıcının cihazlarını Intune’da yönetmeye başlayabilirsiniz.

Diğer kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="set-up-android-enterprise-enrollment"></a>Android Kurumsal kaydını ayarlama

Android Kurumsal kullanıcılara en güncel ve güvenli özelliklerle sağlamak kayıt seçenekleri kümesi sunar. Android Kurumsal kayıt seçenekleri iş profili, tam olarak yönetilen ve ayrılmış cihazları içerir.

- [Android kurumsal iş profili kayıtları ayarlayın](android-work-profile-enroll.md)
- [Ayrılmış Android Kurumsal cihaz kayıtlarını ayarlayın](android-kiosk-enroll.md)
- [Tam olarak yönetilen Android Enterprise kayıtları ayarlayın](android-fully-managed-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Bir Samsung Knox cihazı kaydederken son kullanıcı deneyimi

Samsung Knox Standard cihazları için birden çok kullanıcı yönetimi, Intune tarafından desteklenir. Yani son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da merkezi olarak yönetilir. Son kullanıcılar oturum açtıklarında, uygulamalara erişir ve ek olarak kendilerine uygulanan ilkeler varsa bunları alırlar. Kullanıcılar oturum açtığınızda tüm uygulama verileri kaldırılır.

Samsung Knox cihazları kaydederken göz önünde bulundurulması gereken birkaç nokta vardır:
-   Hiçbir ilke PIN gerektirmiyorsa bile cihazın kaydedilebilmesi için en az dört basamaklı bir PIN’i olmalıdır. Cihazın PIN’i yoksa, kullanıcıdan bir PIN oluşturması istenir.
-   Workplace Join Sertifikaları (WPJ) için kullanıcı etkileşimi yoktur.
-   Kullanıcıya Hizmet Kaydı bilgileri ve uygulamanın yapabilecekleri anlatılır.
-   Kullanıcıya Knox Kaydı bilgileri ve Knox’un yapabilecekleri anlatılır.
-   Bir Şifreleme İlkesi zorlanmışsa, kullanıcıların cihaz geçiş kodu olarak altı karakterlik karmaşık parola ayarlamaları gereklidir.
-   Şirket Kaynağı Erişimi için bir hizmet tarafından gönderilen sertifikaların yüklenmesi için başka kullanıcı istemi yoktur.
- Bazı eski Knox cihazlar, kullanıcıdan Şirket Kaynağı Erişimi için kullanılan ek sertifikalar isteyebilir.
- Bir Samsung Mini cihaz, **Sertifika Bulunamadı** veya **Cihaz Kaydedilemedi** hataları ile WPJ’yi yükleyemezse, en son Samsung Üretici Yazılımı Güncelleştirmelerini yükleyin.

## <a name="next-steps"></a>Sonraki adımlar

- [Android kurumsal iş profili kayıtları ayarlayın](android-work-profile-enroll.md)
- [Ayrılmış Android Kurumsal cihaz kayıtlarını ayarlayın](android-kiosk-enroll.md)
- [Tam olarak yönetilen Android Enterprise kayıtları ayarlayın](android-fully-managed-enroll.md)
