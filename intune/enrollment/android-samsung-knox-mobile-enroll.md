---
title: Samsung 's Knox mobil kaydını kullanarak Android cihazlarını otomatik olarak kaydetme
titleSuffix: Microsoft Intune
description: Samsung KME kullanarak Android cihazları kaydetmeyi öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b16dca0b6a73e7228e65c840bfbc91f3577bb59a
ms.sourcegitcommit: 29b1113dc04534c4c87c33c773c5a0e24266e042
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71999294"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Samsung 's Knox mobil kaydını kullanarak Android cihazlarını otomatik olarak kaydetme

Bu konu, Samsung KNOX Mobile kaydı 'nı (KME) kullanarak desteklenen Android cihazlarını kaydetmek için Intune 'U ayarlamanıza yardımcı olur. Samsung KME ile Intune 'u kullanarak, son kullanıcılar cihazlarını ilk kez açıp bir WiFi veya hücresel ağa bağlandıklarında şirkete ait çok sayıda Android cihazı kaydedebilirsiniz. Ayrıca, cihazlar Knox Deployment uygulaması kullanılırken Bluetooth veya NFC kullanılarak kaydedilebilir.

Samsung KME kullanarak Intune kaydını etkinleştirmek için, hem Intune hem de Samsung KNOX portallarını şu sırayla kullanırsınız:

1. Knox portalında:
    1. [MDM profili oluşturma](#create-mdm-profile)
    2. [Cihaz Ekle](#add-devices)
    3. [Cihazlara MDM profili atama](#assign-an-mdm-profile-to-devices)
2. Knox Portal 'da [Son Kullanıcı oturum açma 'yı yapılandırın](#configure-how-end-users-sign-in).
3. [Cihazları dağıtın](#distribute-devices).


Cihazların Knox dağıtım programına katılan yetkili satıcıların satın alınması sırasında cihaz tanımlayıcılarının listesi (seri numaraları ve ımesıs) Knox portalına otomatik olarak eklenir.


## <a name="prerequisites"></a>Prerequisites

KME kullanarak Intune 'a kaydolmak için, önce aşağıdaki adımları izleyerek şirketinizi Samsung KNOX portalında kaydetmeniz gerekir:
1. [KME ülke/bölgenizde kullanılabilir olduğundan emin olun](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME 55 ülkede/bölgede kullanılabilir. Dağıtım ülkeniz/bölgenizin desteklendiğinden emin olun.

2. [Desteklenen cihazlar](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME Android kaydı için en az Knox 2,4 ve Android Enterprise kaydı için en az Knox 2,8 olan tüm Samsung cihazlarda kullanılabilir.

3. [Ağ gereksinimleri](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): ağınızda gerekli güvenlik duvarı ve ağ erişim kurallarına izin olduğundan emin olun.

4. [Bir Samsung hesabına kaydolun](https://www2.samsungknox.com/en/user/register): KME ve etkinleştirmek ve tüm Knox Enterprise yetkilendirmelerini tek bir yerde yönetmek Için bir Samsung hesabı gerekir.

5. Kayıt Incelemesi: profiliniz tamamlanıp gönderildikten sonra, Samsung uygulamanızı gözden geçirir ve bu işlemi hemen onaylar ya da daha fazla izleme için bekleyen bir gözden geçirme durumuna geçirir. Hesabınız onaylandıktan sonra, daha fazla adımlara devam edebilirsiniz.

## <a name="create-mdm-profile"></a>MDM profili oluştur

Şirketiniz başarıyla kaydedildiğinde, aşağıdaki bilgileri kullanarak Knox portalında Microsoft Intune için MDM profilinizi oluşturabilirsiniz. Knox portalında hem Android hem de Android Enterprise için MDM profilleri oluşturabilirsiniz. 

### <a name="for-android-enterprise"></a>Android Enterprise için

| MDM profili alanları| Gerekli mi? | Değerler | 
|-------------------|-----------|-------| 
|MDM sunucusu URI 'SI     | Hayır        |Bu alanı boş bırakın. 
|Profil adı       | Evet       |Seçtiğiniz bir profil adı girin. 
|Açıklama        | Hayır        |Profili açıklayan metni girin. 
|MDM Aracısı APK      | Evet       |https://aka.ms/intune_kme_deviceowner 
|Bu uygulamayı bir Google cihaz sahibi olarak etkinleştir | Evet | Android Enterprise 'a kaydolmak için bu seçeneği belirleyin. 
|Desteklenen MDM      | Evet       |Microsoft Intune 
|Tüm sistem uygulamalarını etkin bırak | Hayır | Tüm uygulamaların etkinleştirildiğinden ve profilde kullanılabilir olduğundan emin olmak için bu seçeneği belirleyin. Bu seçenek seçilmezse, cihazın uygulamalar tepsisinde yalnızca sınırlı bir sistem uygulamaları kümesi görüntülenir. E-posta uygulaması gibi uygulamalar gizli kalır. 
|Özel JSON        | Hayır        |{"com. Google. Android. Apps. Work. clouddpc. EXTRA_ENROLLMENT_TOKEN": "Intune kayıt belirteci dizesi girin"}. [Kayıt profili oluşturmayı](android-kiosk-enroll.md)öğrenin. 
| Yasal anlaşmalar ekleme | Hayır | Bu alanı boş bırakın. 

### <a name="for-android"></a>Android için

Adım adım yönergeler için bkz. [Samsung KNOX profili Kurulum Sihirbazı](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) yönergeleri.

| MDM profili alanları| Gerekli mi? | Değerler |
|-------------------|-----------|-------|
|MDM sunucusu URI 'SI     | Hayır        |Bu alanı boş bırakın.
|Profil adı       | Evet       |Seçtiğiniz bir profil adı girin.
|açıklama        | Hayır        |Profili açıklayan metni girin.
|MDM Aracısı APK      | Evet       |https://aka.ms/intune_kme
|Bu uygulamayı bir Google cihaz sahibi olarak etkinleştir | Hayır | Android için bu seçeneği seçilmemiş olarak bırakın. Bu seçenek yalnızca Android Enterprise için geçerlidir.
|Kurulum sihirbazını atla  | Hayır        |Son kullanıcıya yönelik standart cihaz kurulum istemlerini atlamak için bu seçeneği belirleyin.
|Son kullanıcının kaydı Iptal edebilmesini sağla | Hayır | Kullanıcıların KME iptal edebilmesini sağlamak için bu seçeneği belirleyin.
|Özel JSON        | Hayır        |Bu alanı boş bırakın.
| Yasal anlaşmalar ekleme | Hayır | Bu alanı boş bırakın.
Knox lisansını bu profille ilişkilendir | Hayır | Bu seçeneği seçilmemiş olarak bırakın. KME kullanarak Intune 'a kaydolma Knox lisansı gerektirmez.

## <a name="add-devices"></a>Cihaz Ekle

Cihazlara MDM profilleri atamak için aşağıdaki yöntemlerden biri kullanılarak Knox portalına desteklenen Samsung KNOX cihazları eklenmelidir:
- **Samsung onaylı Bayi kullanımı:** Bu yöntemi, Samsung onaylı satıcıların birinden cihaz satın aldıysanız kullanın. Satıcılar, onaylandığında cihazları sizin için otomatik olarak karşıya yükleyebilir. [Satıcıların nasıl ekleneceğini öğrenmek Için Samsung KNOX kayıt kullanıcı kılavuzunu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Knox dağıtım uygulamasını (KDA) kullanma:** KME kullanılarak kaydedilmesi gereken mevcut cihazlara sahipseniz bu yöntemi kullanın. Bu yöntemi kullanarak Knox portalına cihaz eklemek için Bluetooth veya NFC kullanabilirsiniz. [KDa kullanma hakkında bilgi edinmek Için Samsung KNOX kayıt kullanıcı kılavuzunu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Cihazlara MDM profili atama
Kaydolmadan önce Knox portalında eklenen cihazlara bir MDM profili atamanız gerekir. [Cihaz yapılandırması hakkında bilgi edinmek Için Samsung KNOX kayıt kullanıcı kılavuzunu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Son kullanıcıların oturum açmasını yapılandırma

Android için KME kullanılarak Intune 'A kaydedilmiş cihazlarda, son kullanıcının nasıl oturum açduğunu aşağıdaki gibi yapılandırabilirsiniz:

- **Kullanıcı adı Ilişkilendirmesi olmadan:** Knox portalında **cihaz ayrıntıları**' nın altında, eklenen cihazlar IÇIN **Kullanıcı kimliği** ve **parola** alanlarını boş bırakın. Bu seçenek, son kullanıcının Intune 'a kaydolurken hem Kullanıcı adı hem de parola girmesini gerektirir.

- **Kullanıcı adı Ilişkilendirmesi ile:** Knox portalında **cihaz ayrıntıları**' nın altında, eklenen cihazlar Için BIR **Kullanıcı kimliği** (atanan kullanıcı veya [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı için Kullanıcı adı gibi) sağlayın. Bu seçenek Kullanıcı adını önceden doldurur ve Intune 'a kaydolurken son kullanıcının bir parola girmesini gerektirir.

> [!NOTE]
>
>Kullanıcı ilişkilendirmesi yalnızca Android Cihaz Yöneticisi kaydı için geçerlidir. Kullanıcı ilişkilendirmesi tanımlandığında, yalnızca ilişkili Kullanıcı KME kullanarak cihazı kaydedebilir. Bu, cihazın fabrika sıfırlamasının ardından bile geçerlidir. Knox portalında hiçbir Kullanıcı ilişkilendirmesi tanımlanmadığında, geçerli bir Intune lisansı olan tüm kullanıcılar cihazı KME kullanarak kaydedebilir.
>Android kurumsal tam olarak yönetilen cihazlar için, Kullanıcı ilişkilendirmesi tanımlansa bile bu cihaz cihaza geçirilmeyecektir veya cihazı kullanıcıya bağlamaktır.
>

## <a name="distribute-devices"></a>Cihazları dağıtma

Bir MDM profili oluşturup atadıktan sonra, bir kullanıcı adını ilişkilendirdikten ve cihazları Intune 'da şirkete ait olarak tanımlayarak, cihazları kullanıcılara dağıtabilirsiniz.

Hala yardıma mı ihtiyacınız var? Tüm [KME Kullanıcı kılavuzuna](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm)göz atın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

- **Cihaz sahibi desteği:**  - **cihaz sahibi desteği:** Intune, KME portalını kullanarak adanmış ve tam olarak yönetilen cihazların kaydedilmesini destekler. Intune 'da kullanılabilir hale geldiğinde diğer Android kurumsal cihaz sahibi modları desteklenecektir.

- **İş profili desteği yok:** KME, Android iş profiline kaydedilen bir kurumsal cihaz kayıt yöntemi ve cihazlarıdır. iş ve kişisel verilerin Kişisel cihazlarda ayrı olduğundan emin olun. Bu nedenle, KME kullanarak iş profiline cihaz kaydı, Intune 'da desteklenen bir senaryo değildir.

- **Android Enterprise 'a kaydolmak Için fabrika sıfırlaması:** Önceden ayarlanmış cihazları yeniden kullandıysanız, Android Enterprise 'a kaydolurken cihazların fabrika sıfırlaması gerekir.

- **Google Play hesabı kullanılarak güncelleştirmeler:** Google Play hesap, cihazı Microsoft Intune kaydetmek için gerekli değildir. Ancak, Android Cihaz Yöneticisi kayıtları için Intune Şirket Portalı uygulamasına gelecek güncelleştirmeler cihazda bir Google Play hesabı gerektirebilir. Google cihaz sahibine kaydolurken Google Play hesabı gerekli değildir.

- **"Parola" alanı yoksayıldı:** **Parola** alanı Knox portalındaki **cihaz ayrıntılarında** doldurulmuşsa, Android kaydı sırasında Intune şirket portalı uygulaması tarafından yok sayılır. Son kullanıcının cihaz kaydını tamamlaması için cihazda bir parola girmesi gerekir.


## <a name="getting-support"></a>Destek alma
[Samsung KME için destek alma](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm)hakkında daha fazla bilgi edinin.


