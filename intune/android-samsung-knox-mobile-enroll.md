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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4236b3fd1b7dab25a3450b95b75f3623ec7ba95
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071635"
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


## <a name="prerequisites"></a>Önkoşullar

KME kullanarak Intune’a kaydolmak için önce şu adımları izleyerek şirketinizi Samsung Knox portalına kaydetmeniz gerekir:
1. [KME ülke/bölgenizde kullanılabilir olduğundan emin olun](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME, 55 ülkede/bölgede kullanılabilir. Dağıtım ülkeniz/bölgenizin desteklendiğinden emin olun.

2. [Desteklenen cihazlar](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME, Android kaydı için en az Knox 2,4 olan tüm Samsung cihazlarda kullanılabilir ve Android kurumsal kaydı için en az Knox 2,8 ' dir.

3. [Ağ gereksinimleri](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ağınızda gerekli güvenlik duvarı ve ağ erişim kurallarına izin olduğundan emin olun.

4. [Samsung hesabına kaydolun](https://www2.samsungknox.com/en/user/register): KME 'i kaydettirmek ve etkinleştirmek ve tüm Knox Enterprise yetkilendirmelerini tek bir yerde yönetmek için bir Samsung hesabı gerekir.

5. Kayıt Incelemesi: Profiliniz tamamlanıp gönderildikten sonra, Samsung uygulamanızı gözden geçirir ve hemen onaylar ya da daha fazla izleme için bekleyen bir gözden geçirme durumuna geçirir. Hesabınız onaylandıktan sonra, daha fazla adımlara devam edebilirsiniz.

## <a name="create-mdm-profile"></a>MDM profili oluşturma

Şirketiniz başarıyla kaydolduktan sonra, aşağıdaki bilgileri kullanarak Knox portalında Microsoft Intune için MDM profilinizi oluşturabilirsiniz. Knox portalında hem Android hem de Android Kurumsal için MDM profilleri oluşturabilirsiniz. 

### <a name="for-android-enterprise"></a>Android Kurumsal için

| MDM Profil Alanları| Gerekli mi? | Değerler | 
|-------------------|-----------|-------| 
|MDM Sunucu URI’si     | Hayır        |Burayı boş bırakın. 
|Profil Adı       | Evet       |Tercih ettiğiniz bir profil adı girin. 
|Açıklama        | Hayır        |Profili açıklayan bir metin girin. 
|MDM Aracı APK’sı      | Evet       |https://aka.ms/intune_kme_deviceowner 
|Bu uygulamayı Google Cihaz Sahibi olarak etkinleştir | Evet | Android Kurumsal’a kaydolmak için bu seçeneği belirleyin. 
|Desteklenen MDM      | Evet       |Microsoft Intune 
|Tüm sistem uygulamalarını etkin bırak | Hayır | Tüm uygulamaların profil için etkin ve kullanılabilir olmasını sağlamak için bu seçeneği belirleyin. Bu seçenek seçilmezse, cihazın uygulamalar tepsisinde yalnızca sınırlı bir sistem uygulamaları kümesi görüntülenir. E-posta gibi uygulamalar gizlenir. 
|Özel JSON        | Hayır        |{"com. Google. Android. Apps. Work. clouddpc. EXTRA_ENROLLMENT_TOKEN": "Intune kayıt belirteci dizesini girin"}. [Kayıt profili oluşturma](android-kiosk-enroll.md) hakkında bilgi edinin. 
| Yasal sözleşmeler ekle | Hayır | Burayı boş bırakın. 

### <a name="for-android"></a>Android için

Adım adım yönergeler için bkz. [Samsung KNOX profili Kurulum Sihirbazı](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) yönergeleri.

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

- **Knox dağıtım uygulamasını (KDA) kullanma:** KME kullanılarak kaydedilmesi gereken mevcut cihazlara sahipseniz bu yöntemi kullanın. Bu yöntem ile Knox Portalı’na cihaz eklemek için Bluetooth veya NFC kullanabilirsiniz. [KDA kullanma hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Cihazlara bir MDM profili atama
Eklenen cihazların kaydedilebilmesi için önce Knox Portalı’nda bu cihazlara bir MDM profili atamalısınız. [Cihaz yapılandırması hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Son kullanıcıların nasıl oturum açacağını yapılandırma

Android için KME kullanarak Intune’a kaydedilmiş cihazlarda bir kullanıcının nasıl oturum açacağını aşağıdaki gibi yapılandırabilirsiniz:

- **Kullanıcı adı ilişkilendirmesi olmadan:** Knox portalında **cihaz ayrıntıları**' nın altında, eklenen cihazlar IÇIN **Kullanıcı kimliği** ve **parola** alanlarını boş bırakın. Bu seçenek, son kullanıcının Intune 'a kaydolurken hem Kullanıcı adı hem de parola girmesini gerektirir.

- **Kullanıcı adı ilişkilendirmesi ile:** Knox portalında **cihaz ayrıntıları**' nın altında, eklenen cihazlar Için BIR **Kullanıcı kimliği** (atanan kullanıcı veya [Cihaz Kayıt Yöneticisi](https://docs.microsoft.com/intune/device-enrollment-manager-enroll) hesabı için Kullanıcı adı gibi) sağlayın. Bu seçenek Kullanıcı adını önceden doldurur ve Intune 'a kaydolurken son kullanıcının bir parola girmesini gerektirir.

> [!NOTE]
>
>Kullanıcı ilişkisi, yalnızca Android kaydı için geçerlidir. Kullanıcı ilişkisi tanımlandığında, cihaz yalnızca ilişkili kullanıcı tarafından KME kullanarak kaydedilebilir. Bu, cihazda fabrika sıfırlaması yapıldıktan sonra bile geçerlidir. Knox portalında kullanıcı ilişkisi tanımlanmadığında ise geçerli bir Intune lisansı olan tüm kullanıcılar KME kullanarak cihazı kaydedebilir.
>

## <a name="distribute-devices"></a>Cihazları dağıtma

Intune’da bir MDM profili oluşturup atadıktan, bir kullanıcı adıyla ilişkilendirdikten ve cihazları şirkete ait olarak tanımladıktan sonra cihazları kullanıcılara dağıtabilirsiniz.

Bu bilgiler yardımcı olmadı mı? Tüm [KME Kullanıcı kılavuzuna](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm)göz atın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

- **Cihaz sahibi desteği:**  - **cihaz sahibi desteği:** Intune, KME portalını kullanarak adanmış ve tam olarak yönetilen cihazların kaydedilmesini destekler. Diğer Android Kurumsal cihaz sahibi modları, Intune’da kullanılabilir hale geldikçe desteklenmeye başlayacaktır.

- **İş profili desteği yok:** KME, Android iş profiline kaydedilen bir kurumsal cihaz kayıt yöntemi ve cihazlarıdır. iş ve kişisel verilerin Kişisel cihazlarda ayrı olduğundan emin olun. Bu nedenle, KME kullanarak iş profiline cihaz kaydı, Intune 'da desteklenen bir senaryo değildir.

- **Android Enterprise 'a kaydolmak için fabrika sıfırlaması:** Önceden ayarlanmış cihazları yeniden kullandıysanız, Android Enterprise 'a kaydolurken cihazların fabrika sıfırlaması gerekir.

- **Google Play hesabı kullanılarak güncelleştirmeler:** Google Play hesap, cihazı Microsoft Intune kaydetmek için gerekli değildir. Ancak Intune Şirket Portalı’na gelecek güncelleştirmeler, cihazda bir Google Play hesabı gerektirebilir. Google cihaz sahibine kaydolurken Google Play hesabı gerekli değildir.

- **"Parola" alanı yoksayıldı:** **Parola** alanı Knox portalındaki **cihaz ayrıntılarında** doldurulmuşsa, Android kaydı sırasında Intune şirket portalı uygulaması tarafından yok sayılır. Cihaz kaydını tamamlamak için kullanıcının cihazda bir parola girmesi gerekir.


## <a name="getting-support"></a>Destek alma
[Samsung KME için destek alma](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm) hakkında daha fazla bilgi edinin.


