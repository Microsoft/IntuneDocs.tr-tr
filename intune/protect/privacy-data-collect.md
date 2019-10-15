---
title: Intune 'da veri toplama
titleSuffix: Microsoft Intune
description: Intune 'da kişisel verilerin nasıl toplandığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd1d0de4b1ae930ebeff07539f9cfa8848f0b7ce
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306902"
---
# <a name="data-collection-in-intune"></a>Intune 'da veri toplama

Kullanıcılar şirket veya kişisel cihazlarını Intune kullanarak kaydettiğinde, Intune bazı kişisel verileri toplar ve paylaşır. Intune, kişisel verileri aşağıdaki kaynaklardan toplar:

- Yöneticinin Azure portal Intune kullanımı.
- Son Kullanıcı cihazları (Intune yönetimine kaydolduklarında ve kullanım sırasında).
- Üçüncü taraf hizmetlerindeki müşteri hesapları (yönetici yönergelerine göre).
- Tanılama, performans ve kullanım bilgileri.

Intune, bu kaynaklardan şu üç kategoride yer alan bilgileri toplar: [tanımlı](#identified-data), [sözde](#pseudonymized-data), ve [toplanmış](#aggregated-data).

> [!NOTE]
> Her nedenden dolayı hizmetimizin tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.

## <a name="identified-data"></a>Tanımlanan veriler

Intune tarafından toplanan kişisel verilerin çoğu tanımlı veri. Bu veriler bir kullanıcıya, cihaza veya uygulamaya bağlanır ve yönetimin doğası açısından önemlidir. Tanımlanan veriler, bir kullanıcının cihazını ve uygulamalarını yönetmek ve Intune hizmetini sağlamak için kullanılır.

Intune tarafından toplanan tanımlanmış veriler şunlar olabilir ancak bunlarla sınırlı değildir: 

- Kullanıcı bilgileri
  - Sahip adı/Kullanıcı görüntüsü (kullanıcının Adzureuserıd tarafından tanımlanan Azure kayıtlı adı)
  - Kullanıcı asıl adı veya e-posta adresi
  - Üçüncü taraf Kullanıcı tanımlar (AppleID gibi)
- Donanım envanteri bilgileri
  - Cihaz adı
  - Üretici
  - İşletim sistemi
  - Seri numarası
  - IMEı numarası
  - IP adresi
  - Wi-Fi MacAddress
  - ICCıD
  - Telefon numarası
- Aşağıdaki etkinliklerle ilgili veriler de dahil olmak üzere denetim günlüğü bilgileri
  - Yönetin
  - Create
  - Güncelleştirme (düzenleme)
  - Sil
  - Ata
  - Uzak görevler
- Destek bilgileri
  - İletişim bilgileri (ad, telefon numarası, e-posta adresi)
  - Microsoft desteği, ürün ve/veya müşteri deneyimi ekip üyeleri ile e-posta tartışmaları
- Erişim denetimi bilgileri (Intune bu verileri, [rol tabanlı Access Control](../fundamentals/role-based-access-control.md)gibi özelliklerle yönetim rollerine ve işlevlerine erişimi yönetmek için kullanır.
  - Statik kimlik doğrulayıcılar (müşterinin parolası)
  - Sertifikalar için Gizlilik anahtarları 
- Yönetici ve hesap bilgileri
  - Yönetici Kullanıcı adı ve soyadı
  - Yönetici Kullanıcı adı
  - UPN (e-posta)
  - Telefon numarası
  - Hesap sahibinin e-posta adresi
  - Her müşterinin yönetici Active Directory KIMLIĞI
  - Müşteri faturalandırması için ödeme verileri
  - Abonelik anahtarı
- Uygulama envanteri, örneğin
  - Uygulama adı
  - version
  - Uygulama KIMLIĞI
  - Boyutla
  - yükleme konumu
  - Uygulama envanteri verileri yalnızca yönetici tarafından şirkete ait bir cihaz olarak işaretlendiğinde veya uyumlu uygulama özelliği açık olduğunda toplanır.  
- Apple KIMLIĞI gibi, müşteri 3. taraf kiracı kimlikleri. 

## <a name="pseudonymized-data"></a>Sözde veriler

Sözde olmayan veriler benzersiz bir tanımlayıcıyla ilişkilendirilir, genellikle sistem tarafından oluşturulan ve kendi kendine tek bir kişiyi tanımlayan, ancak kurumsal Hizmetleri kullanıcılara teslim etmek için kullanılan bir sayıdır. 

Intune tarafından toplanan sahte veriler şunlar olabilir ancak bunlarla sınırlı değildir: 

- Bir kullanıcıya ve/veya cihaza bağlı tanılama, performans ve kullanım verileri
  - Bir özelliğin kaç kez kullanıldığı
  - Özelliği için belirtilen komutlar
  - Hizmetin yanıt süresi
  - Yükleme ve diğer işlemlerin başarı oranları
  - Intune şirket portalı uygulama hataları
  - Kullanıcı ve cihaz tanımlayıcıları
  - Başvuru, bağıntı, yönetim amaçlarıyla ilgili tanımlayıcılar 
- Cihaz verileri bir cihaza veya kullanıcıya bağlı değil (Bu veriler bir cihaza veya kullanıcıya bağlıysa, Intune bunu tanımlanan veri olarak değerlendirir)
  - Intune cihaz KIMLIĞI
  - Azure Active Directory cihaz KIMLIĞI
  - Intune cihaz yönetim KIMLIĞI
  - Kiracı Kimliği
  - Hesap Kimliği
  - EAS cihaz KIMLIĞI
  - Platforma özgü kimlikler
  - İOS cihazları için AppleID
  - Mac cihazları için MAC adresi
  - Windows cihazları için Windows KIMLIĞI
- Yönetilen uygulama bilgileri
  - Yönetilen uygulama KIMLIĞI
  - Yönetilen uygulama cihaz etiketi
  - Intune cihaz yönetim KIMLIĞI
  - Azure Active Directory cihaz KIMLIĞI
  - Şifreleme anahtarları

## <a name="aggregated-data"></a>Toplanan veriler

Toplanan veriler, Intune hizmetini sağlamak ve geliştirmek için kullanılır. 

Intune tarafından toplanan toplanmış veriler şunlar olabilir ancak bunlarla sınırlı değildir: 

- Tüm Intune kiracılarındaki yönetici kullanım verileri (örneğin, yönetim konsoluyla etkileşerek seçilen yönetici denetimleri)
- Kiracı hesabı bilgileri (Bu veriler Intune dikey penceresinden kullanılabilir)
  - Kaydedilen cihaz veya Kullanıcı sayısı
  - Tanımlanan cihaz platformu sayısı  
  - Yüklü cihazların sayısı
  - ınstalyüklenmekte Devicecount: uygulamanın yüklü olduğu cihaz sayısı.
  - notApplicableDeviceCount: uygulamanın geçerli olmadığı cihaz sayısı.
  - Notınstalyüklendevicecount: uygulamanın geçerli olduğu ancak yüklenmediği cihazların sayısı.
  - Pendingınstalldevicecount: uygulamanın geçerli olduğu ve yükleme beklediği cihazların Numberr.

## <a name="next-steps"></a>Sonraki adımlar

Intune 'un kişisel verileri nasıl [depolayıp](privacy-data-store-process.md) işledikleri ve [paylaştığı](privacy-data-secure-share.md) hakkında daha fazla bilgi edinin. 
