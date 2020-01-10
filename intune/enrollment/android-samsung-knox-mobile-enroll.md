---
title: Otomatik olarak Samsung'ın Knox mobil kaydı'nı kullanarak Android cihazlarını kaydetme
titleSuffix: Microsoft Intune
description: Samsung KME kullanarak Android cihazları kaydetmeyi öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ecb043300578e5eba0613b6fa5f0fb249b1e515c
ms.sourcegitcommit: a66b5916eaab9cb537e483064efc584a6a63a390
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75692156"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme

Bu konu, Samsung Knox Mobil Kayıt (KME) kullanarak Intune’u desteklenen Android cihazları kaydetmek üzere ayarlamanıza yardımcı olur. Intune’u Samsung KME ile birlikte kullanarak son kullanıcılar cihazlarını ilk kez açıp WiFi veya hücresel ağa bağlandıklarında fazla sayıda şirkete ait Android cihazı kaydedebilirsiniz. Ayrıca Knox Dağıtım Uygulaması’nı kullanırken Bluetooth veya NFC yoluyla da cihaz kaydedilebilir.

Samsung KME kullanarak Intune kaydını etkinleştirmek için Intune ve Samsung Knox portallarını şu sırayla kullanabilirsiniz:

1. Knox portalında:
    1. [Bir MDM profili oluşturun](#create-mdm-profile)
    2. [Cihaz ekleyin](#add-devices)
    3. [Cihazlara bir MDM profili atayın](#assign-an-mdm-profile-to-devices)
2. Knox portalında [son kullanıcı oturum açma seçeneğini yapılandırın](#configure-how-end-users-sign-in).
3. [Cihazları dağıtın](#distribute-devices).


Cihazların Knox dağıtım programına katılan yetkili satıcıların satın alınması sırasında cihaz tanımlayıcılarının listesi (seri numaraları ve ımesıs) Knox portalına otomatik olarak eklenir.


## <a name="prerequisites"></a>Prerequisites

KME kullanarak Intune’a kaydolmak için önce şu adımları izleyerek şirketinizi Samsung Knox portalına kaydetmeniz gerekir:
1. [KME ülke/bölgenizde kullanılabilir olduğundan emin olun](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME 55 ülkede/bölgede kullanılabilir. Dağıtım ülkeniz/bölgenizin desteklendiğinden emin olun.

2. [Desteklenen cihazlar](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME, en az Knox 2.4 (Android kaydı için) veya Knox 2.8 (Android Kurumsal kaydı için) sürümüne sahip tüm Samsung cihazlarda kullanılabilir.

3. [Ağ gereksinimleri](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ağınızda gerekli güvenlik duvarı ve ağ erişim kurallarına izin verildiğinden emin olun.

4. [Bir Samsung hesabı açın](https://www2.samsungknox.com/en/user/register): KME’ye kaydolmak, KME’yi etkinleştirmek ve tüm Knox Kurumsal destek haklarını tek bir yerde yönetmek için bir Samsung hesabı gereklidir.

5. Kayıt Incelemesi: profiliniz tamamlanıp gönderildikten sonra, Samsung uygulamanızı gözden geçirir ve bu işlemi hemen onaylar ya da daha fazla izleme için bekleyen bir gözden geçirme durumuna geçirir. Hesabınız onaylandıktan sonra, daha fazla adımlara devam edebilirsiniz.

## <a name="create-mdm-profile"></a>MDM profili oluşturma

Şirketiniz başarıyla kaydolduktan sonra, aşağıdaki bilgileri kullanarak Knox portalında Microsoft Intune için MDM profilinizi oluşturabilirsiniz. Knox portalında hem Android hem de Android Kurumsal için MDM profilleri oluşturabilirsiniz. 

### <a name="for-android-enterprise"></a>Android Kurumsal için

| MDM Profil Alanları| Gerekli mi? | Değerler | 
|-------------------|-----------|-------| 
|MDM Sunucu URI’si     | Hayır        |Burayı boş bırakın. 
|Profil Adı       | Evet       |Tercih ettiğiniz bir profil adı girin. 
|Description        | Hayır        |Profili açıklayan bir metin girin. 
|MDM Aracı APK’sı      | Evet       |https://aka.ms/intune_kme_deviceowner 
|Bu uygulamayı Google Cihaz Sahibi olarak etkinleştir | Evet | Android Kurumsal’a kaydolmak için bu seçeneği belirleyin. 
|Desteklenen MDM      | Evet       |Microsoft Intune 
|Tüm sistem uygulamalarını etkin bırak | Hayır | Tüm uygulamaların profil için etkin ve kullanılabilir olmasını sağlamak için bu seçeneği belirleyin. Bu seçenek seçilmezse, cihazın uygulamalar tepsisinde yalnızca sınırlı bir sistem uygulamaları kümesi görüntülenir. E-posta gibi uygulamalar gizlenir. 
|Özel JSON        | Hayır        |{"com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "Enter Intune enrollment token string"}. [Kayıt profili oluşturma](android-kiosk-enroll.md) hakkında bilgi edinin. 
| Yasal sözleşmeler ekle | Hayır | Burayı boş bırakın. 

### <a name="for-android"></a>Android için

Adım adım yönergeler için, [Samsung 'In profil oluşturma](https://docs.samsungknox.com/KME-Getting-Started/Content/create-profiles.htm) yönergelerine bakın.

| MDM Profil Alanları| Gerekli mi? | Değerler |
|-------------------|-----------|-------|
|MDM Sunucu URI’si     | Hayır        |Burayı boş bırakın.
|Profil Adı       | Evet       |Tercih ettiğiniz bir profil adı girin.
|açıklama        | Hayır        |Profili açıklayan bir metin girin.
|MDM Aracı APK’sı      | Evet       |https://aka.ms/intune_kme
|Bu uygulamayı Google Cihaz Sahibi olarak etkinleştir | Hayır | Android için bu seçeneği belirtmeyin. Bu seçenek yalnızca Android Enterprise için geçerlidir.
|Kurulum sihirbazını atlama  | Hayır        |Son kullanıcıya yönelik standart cihaz kurulum istemlerini atlamak için bu seçeneği belirleyin.
|Son Kullanıcının Kaydı İptal Etmesine İzin Ver | Hayır | Kullanıcıların KME’yi iptal etmesine izin vermek için bunu seçin.
|Özel JSON        | Hayır        |Burayı boş bırakın.
| Yasal sözleşmeler ekle | Hayır | Burayı boş bırakın.
Bu profil ile bir Knox lisansını ilişkilendir | Hayır | Bunu seçmeyin. KME kullanarak Intune 'a kaydolma Knox lisansı gerektirmez.

## <a name="add-devices"></a>Cihazları ekleme

Cihazlara MDM profilleri atamak için aşağıdaki yöntemlerden biri kullanılarak Knox Portalı’na desteklenen Samsung Knox cihazlar eklenmelidir:
- **Samsung onaylı Bayi kullanımı:** Bu yöntemi, Samsung onaylı satıcıların birinden cihaz satın aldıysanız kullanın. Kurumsal bayiler, onaylandığında cihazları sizin için otomatik olarak yükleyebilir. [Kurumsal bayileri nasıl ekleyeceğinizi öğrenmek için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Knox Dağıtım Uygulaması (KDA) kullanarak**: KME kullanarak kaydedilmesi gereken cihazlarınız varsa bu yöntemi kullanın. Bu yöntem ile Knox Portalı’na cihaz eklemek için Bluetooth veya NFC kullanabilirsiniz. [KDA kullanma hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Cihazlara bir MDM profili atama
Eklenen cihazların kaydedilebilmesi için önce Knox Portalı’nda bu cihazlara bir MDM profili atamalısınız. [Cihaz yapılandırması hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Son kullanıcıların nasıl oturum açacağını yapılandırma

Android için KME kullanarak Intune’a kaydedilmiş cihazlarda bir kullanıcının nasıl oturum açacağını aşağıdaki gibi yapılandırabilirsiniz:

- **Kullanıcı adı ilişkisi olmadan:** Knox Portalı’nda **Cihaz ayrıntıları** altında, eklenen cihazlar için **Kullanıcı kimliği** ve **Parola** alanlarını boş bırakın. Bu seçenek, son kullanıcının Intune 'a kaydolurken hem Kullanıcı adı hem de parola girmesini gerektirir.

- **Kullanıcı adı ilişkisi ile:** Knox Portalı’nda **Cihaz ayrıntıları** altında, eklenen cihazlar için bir **Kullanıcı kimliği** (atanmış kullanıcı için bir kullanıcı adı veya [Cihaz Kaydı Yöneticisi](device-enrollment-manager-enroll.md) hesabı gibi) girin. Bu seçenek Kullanıcı adını önceden doldurur ve Intune 'a kaydolurken son kullanıcının bir parola girmesini gerektirir.

> [!NOTE]
>
>Kullanıcı ilişkilendirmesi yalnızca Android Cihaz Yöneticisi kaydı için geçerlidir. Kullanıcı ilişkisi tanımlandığında, cihaz yalnızca ilişkili kullanıcı tarafından KME kullanarak kaydedilebilir. Bu, cihazda fabrika sıfırlaması yapıldıktan sonra bile geçerlidir. Knox portalında kullanıcı ilişkisi tanımlanmadığında ise geçerli bir Intune lisansı olan tüm kullanıcılar KME kullanarak cihazı kaydedebilir.
>Android kurumsal tam olarak yönetilen cihazlar için, Kullanıcı ilişkilendirmesi tanımlansa bile bu cihaz cihaza geçirilmeyecektir veya cihazı kullanıcıya bağlamaktır.
>

## <a name="distribute-devices"></a>Cihazları dağıtma

Intune’da bir MDM profili oluşturup atadıktan, bir kullanıcı adıyla ilişkilendirdikten ve cihazları şirkete ait olarak tanımladıktan sonra cihazları kullanıcılara dağıtabilirsiniz.

Bu bilgiler yardımcı olmadı mı? Tüm [KME Kullanıcı kılavuzuna](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm)göz atın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

- **Cihaz sahibi desteği:** **cihaz sahibi desteğini - :** Intune, adanmış ve tam olarak yönetilen cihazların KME portalını kullanarak kaydedilmesini destekler. Diğer Android Kurumsal cihaz sahibi modları, Intune’da kullanılabilir hale geldikçe desteklenmeye başlayacaktır.

- **İş profili desteği yoktur:** KME Kurumsal cihaz kayıt yöntemi ve Android iş profiline kayıtlı cihazlar emin olun, iş ve kişisel cihazlarda kişisel verileri ayrıdır. Bu nedenle, KME kullanarak iş profiline cihaz kaydı, Intune 'da desteklenen bir senaryo değildir.

- **Android Kurumsal’a kaydolmak için fabrika sıfırlaması**: Önceden ayarlanmış cihazları yeniden amaçlandırıyorsanız Android Kurumsal’a kaydolurken bu cihazlarda fabrika sıfırlaması yapılması gerekir.

- **Google Play hesabı kullanılarak güncelleştirmeler:** Google Play hesap, cihazı Microsoft Intune kaydetmek için gerekli değildir. Ancak, Android Cihaz Yöneticisi kayıtları için Intune Şirket Portalı uygulamasına gelecek güncelleştirmeler cihazda bir Google Play hesabı gerektirebilir. Google cihaz sahibine kaydolurken Google Play hesabı gerekli değildir.

- **"Parola" alanı yoksayıldı:** **Parola** alanı Knox portalındaki **cihaz ayrıntılarında** doldurulmuşsa, Android kaydı sırasında Intune şirket portalı uygulaması tarafından yok sayılır. Cihaz kaydını tamamlamak için kullanıcının cihazda bir parola girmesi gerekir.


## <a name="getting-support"></a>Destek alma
[Samsung KME için destek alma](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm) hakkında daha fazla bilgi edinin.


