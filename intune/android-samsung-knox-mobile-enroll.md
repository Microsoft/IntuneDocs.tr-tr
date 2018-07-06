---
title: Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme
titlesuffix: Microsoft Intune
description: Samsung KME kullanarak Android cihazları kaydetmeyi öğrenin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5ac976e07c98fae0941168cc94b5afc5ca09616
ms.sourcegitcommit: 8be5f29107d882c3ecf3dc0ce718a2423f91ce9a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "36964717"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme

Bu konu, Samsung Knox Mobil Kayıt (KME) kullanarak Intune’u desteklenen Android cihazları kaydetmek üzere ayarlamanıza yardımcı olur. Intune’u Samsung KME ile birlikte kullanarak son kullanıcılar cihazlarını ilk kez açıp WiFi veya hücresel ağa bağlandıklarında fazla sayıda şirkete ait Android cihazı kaydedebilirsiniz. Ayrıca Knox Dağıtım Uygulaması’nı kullanırken Bluetooth veya NFC yoluyla da cihaz kaydedilebilir.

Samsung KME kullanarak Intune kaydını etkinleştirmek için Intune ve Samsung Knox portallarını şu sırayla kullanabilirsiniz:

1. Knox portalında:
    1. [Bir MDM profili oluşturun](#create-mdm-profile)
    2. [Cihaz ekleyin](#add-devices)
    3. [Cihazlara bir MDM profili atayın](#assign-an-mdm-profile-to-devices)
2. Azure portalında [cihazları şirkete ait olarak tanımlayın](#identify-devices-as-corporate-owned).
3. Knox portalında [son kullanıcı oturum açma seçeneğini yapılandırın](#configure-how-end-users-sign-in).
4. [Cihazları dağıtın](#distribute-devices).


Knox Dağıtım Programı’nda yer alan yetkili satıcılardan cihaz satın alırken, Knox Portalı’na bir cihaz tanımlayıcıları (seri numaralar ve IMEI’ler) listesi otomatik olarak eklenir.


## <a name="prerequisites"></a>Önkoşullar

KME kullanarak Intune’a kaydolmak için önce şu adımları izleyerek şirketinizi Samsung Knox portalına kaydetmeniz gerekir:
1.  [KME’nin bölgenizde kullanılabilir olduğundan emin olun](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME, 55’ten fazla ülkede kullanılabilir. Dağıtım yapacağınız ülkenin desteklendiğinden emin olun.

2.  [Desteklenen cihazlar](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME, en düşük Knox 2.4 çalıştıran tüm Samsung cihazlarda kullanılabilir.

3.  [Ağ gereksinimleri](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): Ağınızda gerekli güvenlik duvarı ve ağ erişim kurallarına izin verildiğinden emin olun.

4.  [Bir Samsung hesabı açın](https://www2.samsungknox.com/en/user/register): KME’ye kaydolmak, KME’yi etkinleştirmek ve tüm Knox Kurumsal destek haklarını tek bir yerde yönetmek için bir Samsung hesabı gereklidir.

5.  Kayıt Gözden Geçirme: Profiliniz tamamlandıktan ve gönderildikten sonra Samsung, başvurunuzu gözden geçirir ve ya hemen onaylar ya da daha sonra tekrar gözden geçirmek üzere bekleme durumuna alır. Hesabınız onaylandıktan sonra diğer adımlara geçebilirsiniz.

## <a name="create-mdm-profile"></a>MDM profili oluşturma

Şirketiniz başarıyla kaydolduktan sonra, aşağıdaki bilgileri kullanarak Knox Portalı’nda Microsoft Intune için MDM profilinizi oluşturabilirsiniz. Adım adım rehber için [ Samsung Knox Profil Kurulum Sihirbazı](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) yönergelerine bakın.

| MDM Profil Alanları| Gerekli mi? | Değerler |
|-------------------|-----------|-------|
|MDM Sunucu URI’si     | Hayır        |Burayı boş bırakın.
|Profil Adı       | Evet       |Tercih ettiğiniz bir profil adı girin.
|açıklama        | Hayır        |Profili açıklayan bir metin girin.
|MDM Aracı APK’sı      | Evet       |https://aka.ms/intune_kme
|Kurulum sihirbazını atlama  | Hayır        |Son kullanıcı adına standart cihaz kurulum istemlerini atlamak için bunu seçin.
|Son Kullanıcının Kaydı İptal Etmesine İzin Ver | Hayır | Kullanıcıların KME’yi iptal etmesine izin vermek için bunu seçin.
|Özel JSON        | Hayır        |Burayı boş bırakın.
| EULA’lar, Hizmet Koşulları ve Kullanıcı Sözleşmeleri| Hayır | Knox ile ilgili sözleşmeleri kullanıcıların kabulüne sunmak için bunu seçin.
Bu profil ile bir Knox lisansını ilişkilendir | Hayır | Bunu seçmeyin. KME kullanarak Intune’a kaydolurken bir Knox lisansı gerekmez.

## <a name="add-devices"></a>Cihazları ekleme

Cihazlara MDM profilleri atamak için aşağıdaki yöntemlerden biri kullanılarak Knox Portalı’na desteklenen Samsung Knox cihazlar eklenmelidir:
- **Samsung Onaylı Kurumsal Bayiler kullanarak**: Samsung onaylı bir kurumsal bayiden cihaz satın alıyorsanız bu yöntemi kullanın. Kurumsal bayiler, onaylandığında cihazları sizin için otomatik olarak yükleyebilir. [Kurumsal bayileri nasıl ekleyeceğinizi öğrenmek için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **Knox Dağıtım Uygulaması (KDA) kullanarak**: KME kullanarak kaydedilmesi gereken cihazlarınız varsa bu yöntemi kullanın. Bu yöntem ile Knox Portalı’na cihaz eklemek için Bluetooth veya NFC kullanabilirsiniz. [KDA kullanma hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Cihazlara bir MDM profili atama
Eklenen cihazların kaydedilebilmesi için önce Knox Portalı’nda bu cihazlara bir MDM profili atamalısınız. [Cihaz yapılandırması hakkında bilgi için Samsung Knox Kaydı Kullanıcı Kılavuzu’nu ziyaret edin](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="identify-devices-as-corporate-owned"></a>Cihazları şirkete ait olarak tanımlama
Kaydedilen cihazları KME kullanarak şirkete ait olarak tanımlayabilirsiniz. Bu işlem, cihazlar kaydedilmeden önce yapılmalıdır. Böylece ek yönetim görevleri gerçekleştirebilir ve tam telefon numarası ile uygulama envanteri gibi ilave bilgiler toplayabilirsiniz.

Cihazları şirkete ait olarak tanımlamak için şu adımları izleyin:

1. Knox Portalı’ndaki cihazlar listesini CSV dosyası olarak dışarı aktarın.

2. CSV dosyasını [burada](https://docs.microsoft.com/en-us/intune/corporate-identifiers-add#identify-corporate-owned-devices-with-imei-or-serial-number) gösterildiği gibi IMEI veya seri numarası kullanarak biçimlendirin.

3. CSV dosyasını Azure portalında **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** > **Ekle**’ye yükleyin.

Artık kaydedilen tanımlı cihazlar, şirkete ait olarak işaretlenecektir.

> [!NOTE]
>Intune, [Cihaz Kaydı Yöneticisi](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll) hesabıyla kaydedilen cihazlara şirkete ait durumunu otomatik olarak atar.

## <a name="configure-how-end-users-sign-in"></a>Son kullanıcıların nasıl oturum açacağını yapılandırma

Intune’a KME kullanarak kaydedilen cihazlarda son kullanıcıların nasıl oturum açacağını aşağıdaki gibi yapılandırabilirsiniz:

- **Kullanıcı adı ilişkisi olmadan:** Knox Portalı’nda **Cihaz ayrıntıları** altında, eklenen cihazlar için **Kullanıcı kimliği** ve **Parola** alanlarını boş bırakın. Bu, son kullanıcının Intune’a kaydolurken kullanıcı adı ve parola girmesini gerektirir.

- **Kullanıcı adı ilişkisi ile:** Knox Portalı’nda **Cihaz ayrıntıları** altında, eklenen cihazlar için bir **Kullanıcı kimliği** (atanmış kullanıcı için bir kullanıcı adı veya [Cihaz Kaydı Yöneticisi](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll) hesabı gibi) girin. Bu, kullanıcı adını otomatik olarak doldurur ve son kullanıcının Intune’a kaydolurken parola girmesini gerektirir.

> [!NOTE]
>
>Kullanıcı ilişkisi tanımlandığında, cihaz yalnızca ilişkili kullanıcı tarafından KME kullanarak kaydedilebilir. Bu, cihazda fabrika sıfırlaması yapıldıktan sonra bile geçerlidir. Knox Portalı’nda kullanıcı ilişkisi tanımlanmadığında ise geçerli bir Intune lisansı olan tüm kullanıcılar KME kullanarak cihazı kaydedebilir.
>

## <a name="distribute-devices"></a>Cihazları dağıtma

Intune’da bir MDM profili oluşturup atadıktan, bir kullanıcı adıyla ilişkilendirdikten ve cihazları şirkete ait olarak tanımladıktan sonra cihazları kullanıcılara dağıtabilirsiniz.

Bu bilgiler yardımcı olmadı mı? [Knox Mobil Kayıt Kullanıcı Kılavuzu](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm)’na göz atın.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular
- **Google Play Hesabı:** Google Play hesabı, cihazı Microsoft Intune’a kaydetmek için gerekli değildir. Ancak Intune Şirket Portalı’na gelecek güncelleştirmeler, cihazda bir Google Play hesabı gerektirebilir.

- **Google Cihaz Sahibi modu:** KME kullanarak Google Cihaz Sahibi moduna kaydolmak, bu Önizleme’de desteklenmez. Bu senaryo şu anda incelenmektedir.

- **“Parola” alanı yoksayılır:** Knox Portalı’ndaki **Cihaz ayrıntıları**’nda **parola** alanı doldurulursa Intune Şirket Portalı uygulaması bunu yoksayar. Cihaz kaydını tamamlamak için kullanıcının cihazda bir parola girmesi gerekir.

- **"Android Enterprise Kaydı** KME, Android Enterprise Kaydını desteklemez.

## <a name="getting-support"></a>Destek alma
[Samsung KME için destek alma](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm) hakkında daha fazla bilgi edinin.


