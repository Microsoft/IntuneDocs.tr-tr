---
title: Otomatik olarak Samsung'ın Knox mobil kaydı'nı kullanarak Android cihazlarını kaydetme
titlesuffix: Microsoft Intune
description: Samsung KME kullanarak Android cihazları kaydetmeyi öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bb2b8c57c8aa3f53a04150ce0ad692b0149dee8
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235964"
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


Knox Dağıtım Programı’nda yer alan yetkili satıcılardan cihaz satın alırken, Knox Portalı’na bir cihaz tanımlayıcıları (seri numaralar ve IMEI’ler) listesi otomatik olarak eklenir.


## <a name="prerequisites"></a>Önkoşullar

KME kullanarak Intune’a kaydolmak için önce şu adımları izleyerek şirketinizi Samsung Knox portalına kaydetmeniz gerekir:
1.  [KME Bölgenizde kullanılabilir olduğundan emin olun](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME üzerinde 55 ülkede kullanılabilir. Dağıtım yapacağınız ülkenin desteklendiğinden emin olun.

2.  [Desteklenen cihazlar](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME tüm Samsung cihazların Knox 2.4 Android kaydı için en az ve en az Knox 2.8 Android Kurumsal kayıt için kullanılabilir.

3.  [Ağ gereksinimleri](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Gerekli güvenlik duvarı ve ağ erişim kuralları, ağınızda izin emin olun.

4.  [Bir Samsung hesabı için kaydolun](https://www2.samsungknox.com/en/user/register): Bir Samsung hesabı kaydetmek ve KME etkinleştirmek ve tüm Knox Kurumsal yetkilendirmeler tek bir yerden yönetmek için gereklidir.

5.  Kayıt gözden geçirin: Profilinizi tamamlandı ve gönderilen sonra uygulamanızın bir gözden geçirme Samsung gerçekleştirir ve hemen onaylar veya daha fazla izleme için bekleyen durum geçirir. Hesabınız onaylandıktan sonra diğer adımlara geçebilirsiniz.

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
|Tüm sistem uygulamalarını etkin bırak | Hayır | Tüm uygulamaların profil için etkin ve kullanılabilir olmasını sağlamak için bu seçeneği belirleyin. Bu seçenek belirlenmezse cihazın uygulamalar tepsisinde yalnızca sınırlı bir grup uygulama görüntülenir. E-posta gibi uygulamalar gizlenir. 
|Özel JSON        | Hayır        |{"com.google.android.apps.work.clouddpc.EXTRA_ENROLLMENT_TOKEN": "Intune kayıt belirteç dizesini girin"}. [Kayıt profili oluşturma](android-kiosk-enroll.md) hakkında bilgi edinin. 
| Yasal sözleşmeler ekle | Hayır | Burayı boş bırakın. 

### <a name="for-android"></a>Android için

Adım adım rehber için [ Samsung Knox Profil Kurulum Sihirbazı](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) yönergelerine bakın.

| MDM Profil Alanları| Gerekli mi? | Değerler |
|-------------------|-----------|-------|
|MDM Sunucu URI’si     | Hayır        |Burayı boş bırakın.
|Profil Adı       | Evet       |Tercih ettiğiniz bir profil adı girin.
|açıklama        | Hayır        |Profili açıklayan bir metin girin.
|MDM Aracı APK’sı      | Evet       |https://aka.ms/intune_kme
|Bu uygulamayı Google Cihaz Sahibi olarak etkinleştir | Hayır | Android için bu seçeneği belirtmeyin. Bu, yalnızca Android Kurumsal için geçerlidir.
|Kurulum sihirbazını atlama  | Hayır        |Son kullanıcı adına standart cihaz kurulum istemlerini atlamak için bunu seçin.
|Son Kullanıcının Kaydı İptal Etmesine İzin Ver | Hayır | Kullanıcıların KME’yi iptal etmesine izin vermek için bunu seçin.
|Özel JSON        | Hayır        |Burayı boş bırakın.
| Yasal sözleşmeler ekle | Hayır | Burayı boş bırakın.
Bu profil ile bir Knox lisansını ilişkilendir | Hayır | Bunu seçmeyin. KME kullanarak Intune’a kaydolurken bir Knox lisansı gerekmez.

## <a name="add-devices"></a>Cihazları ekleme

Cihazlara MDM profilleri atamak için aşağıdaki yöntemlerden biri kullanılarak Knox Portalı’na desteklenen Samsung Knox cihazlar eklenmelidir:
- **Samsung onaylı Reseller(s) kullanma:** Samsung onaylı satıcıları birinden cihazlar satın aldığınız, bu yöntemi kullanın. Kurumsal bayiler, onaylandığında cihazları sizin için otomatik olarak yükleyebilir. [Kurumsal bayileri nasıl ekleyeceğinizi öğrenmek için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Knox dağıtım uygulamasını (KDA) kullanarak:** KME kullanılarak kaydedilmesi gereken mevcut cihazlarınız varsa, bu yöntemi kullanın. Bu yöntem ile Knox Portalı’na cihaz eklemek için Bluetooth veya NFC kullanabilirsiniz. [KDA kullanma hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Cihazlara bir MDM profili atama
Eklenen cihazların kaydedilebilmesi için önce Knox Portalı’nda bu cihazlara bir MDM profili atamalısınız. [Cihaz yapılandırması hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="configure-how-end-users-sign-in"></a>Son kullanıcıların nasıl oturum açacağını yapılandırma

Android için KME kullanarak Intune’a kaydedilmiş cihazlarda bir kullanıcının nasıl oturum açacağını aşağıdaki gibi yapılandırabilirsiniz:

- **Kullanıcı adı ilişkilendirmesi:** Knox portalında altında **cihaz ayrıntıları**, bırakın **kullanıcı kimliği** ve **parola** alanları eklenen cihazlar için boştur. Bu, son kullanıcının Intune’a kaydolurken kullanıcı adı ve parola girmesini gerektirir.

- **Kullanıcı adı ilişkisi ile:** Knox portalında altında **cihaz ayrıntıları**, sağlayan bir **kullanıcı kimliği** (atanmış kullanıcı için bir kullanıcı adı gibi veya [cihaz kayıt Yöneticisi](https://docs.microsoft.com/intune/device-enrollment-manager-enroll) hesabı) eklenen cihazlar için. Bu, kullanıcı adını otomatik olarak doldurur ve son kullanıcının Intune’a kaydolurken parola girmesini gerektirir.

> [!NOTE]
>
>Kullanıcı ilişkisi, yalnızca Android kaydı için geçerlidir. Kullanıcı ilişkisi tanımlandığında, cihaz yalnızca ilişkili kullanıcı tarafından KME kullanarak kaydedilebilir. Bu, cihazda fabrika sıfırlaması yapıldıktan sonra bile geçerlidir. Knox portalında kullanıcı ilişkisi tanımlanmadığında ise geçerli bir Intune lisansı olan tüm kullanıcılar KME kullanarak cihazı kaydedebilir.
>

## <a name="distribute-devices"></a>Cihazları dağıtma

Intune’da bir MDM profili oluşturup atadıktan, bir kullanıcı adıyla ilişkilendirdikten ve cihazları şirkete ait olarak tanımladıktan sonra cihazları kullanıcılara dağıtabilirsiniz.

Bu bilgiler yardımcı olmadı mı? [Knox Mobil Kayıt Kullanıcı Kılavuzu](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm)’na göz atın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

- **Cihaz sahibi desteği:** Intune kullanarak Android kurumsal bilgi noktası modu için hesabından cihazların kaydını destekler. Diğer Android Kurumsal cihaz sahibi modları, Intune’da kullanılabilir hale geldikçe desteklenmeye başlayacaktır.

- **İş profili desteği yok:** KME Kurumsal cihaz kaydı yöntemidir ve Android iş profiline kayıtlı cihazlarda iş emin olun ve kişisel cihazlarda kişisel verileri ayrıdır. Bu nedenle, cihaz kaydı KME kullanarak iş profiline ıntune'da desteklenen bir senaryo değildir.

- **Android kuruluş kaydedilebilmesi için fabrika ayarlarına:** Zaten ayarlanmış cihazları yeniden amaçlandırmayı, cihazların Android kuruluş kaydederken fabrika ayarlarına olmanız gerekir.

- **Google Play hesabını kullanarak güncelleştirir:** Google Play hesabı Intune cihaza kaydetmek için gerekli değildir. Ancak Intune Şirket Portalı’na gelecek güncelleştirmeler, cihazda bir Google Play hesabı gerektirebilir. Google Play hesabı, Google Cihaz Sahibi’ne kaydolurken gerekli değildir.

- **"Parola" alanına göz ardı edilir:** Varsa **parola** alanın doldurulduğundan **cihaz ayrıntıları** Knox portalında Android kayıt sırasında Intune Şirket portalı uygulaması tarafından yoksayılır. Cihaz kaydını tamamlamak için kullanıcının cihazda bir parola girmesi gerekir.


## <a name="getting-support"></a>Destek alma
[Samsung KME için destek alma](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm) hakkında daha fazla bilgi edinin.


