---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için Wi-Fi ayarları | Microsoft Docs
description: Microsoft Intune'da Windows 10 ve üzeri cihazlar için Wi-Fi ayarlarını kullanarak Wi-Fi yapılandırma profilini ekleme veya oluşturma. Temel ayarları veya kurumsal düzey ayarları yapılandırabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 666e39aa427a10e54ea63b5fc133766335ac09c7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730381"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Windows 10 ve üzeri cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profile"></a>Temel profil

- **Wi-Fi türü**: **Temel**’i seçin. 

- **Wi-Fi adı (SSID)** : Hizmet kümesi tanımlayıcısının kısaltması. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için bir kolay ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- **Aralığa girdiğinde otomatik bağlan**: **Evet** olduğunda, bu ağın aralığına giren cihazlar otomatik olarak bağlanır. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.

  - **Mevcutsa daha fazla tercih edilen ağa bağlan**: Cihazlar tercih edilen birden çok ağın aralığında yer alıyorsa, tercih edilen ağı kullanmak için **Evet**'i seçin. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **SSID'sini yayınlamıyor olsa bile bu ağa bağlanın**: Ağınız gizli (SSID'si herkese açık şekilde yayınlanmıyor) olduğunda bile, ağınıza otomatik olarak bağlanmak üzere yapılandırma profili için **Evet**'i seçin. Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Tarifeli Bağlantı Sınırı**: Bir yönetici, ağ trafiğinin nasıl tarifelendirileceğini belirleyebilir. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Sınırsız**: Varsayılan ayar. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Sabit**: Ağ, ağ trafiği için sabit sınırla yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Ağ trafiği bayt başına ücretlendiriliyorsa (bayt başına maliyet) bu seçeneği kullanın.

- **Kablosuz Güvenlik Türü**: Ağınızda cihazların kimliğini doğrulamak için kullanılan güvenlik protokolünü girin. Seçenekleriniz şunlardır:
  - **Açık (kimlik doğrulamasız)** : Bu seçeneği yalnızca ağ güvenlik altına alınmamış olduğunda kullanın.
  - **WPA/WPA2-Kişisel**: Daha güvenli bir seçenektir ve genellikle Wi-Fi bağlantısı için kullanılır. Daha fazla güvenlik için önceden paylaşılan bir anahtar parolası veya ağ anahtarı girebilirsiniz.

    - **Önceden paylaşılan anahtar** (PSK): İsteğe bağlıdır. Güvenlik türü olarak **WPA/WPA2-Kişisel**’i seçtiğinizde gösterilir. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin. 8-64 karakter arasında bir dize girin. Parolanız veya ağ anahtarınız 64 karakterden oluşuyorsa, onaltılık karakterler girin.

      > [!NOTE]
      > Wi-Fi profilini kaydettiğinizde, girdiğiniz PSK değeri güvenlik nedeniyle gösterilmez. PSK’nin profile kaydedilmesine rağmen önceden paylaşılan filigran **Yapılandırılmadı** olarak görünür. PSK’yi değiştirmek için yeni bir anahtar girin ve profili kaydedin. PSK’yi kaydeder, ilkeyi düzenler ve PSK’yi boş bırakırsanız mevcut PSK kullanılmaya devam eder.
      > [!IMPORTANT]
      > PSK, profili hedeflediğiniz tüm cihazlar için aynıdır. Anahtar tehlikeye girerse, Wi-Fi ağına bağlanmak için herhangi bir cihaz tarafından kullanılabilir. Yetkisiz erişimin olmaması için PSKs 'i güvende tutun.

- **Şirket ara sunucu ayarları**: Kuruluşunuz içinde ara sunucu ayarlarını kullanmak için seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile yapılandır**: **Ara sunucu IP adresini** ve onun **Bağlantı noktası numarasını** girin.
  - **Otomatik olarak yapılandır**: Proxy otomatik yapılandırma (PAC) betiğine işaret eden URL’yi girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="enterprise-profile"></a>Kurumsal profil

- **Wi-Fi türü**: **Kurumsal**’ı seçin.

- **Wi-Fi adı (SSID)** : Hizmet kümesi tanımlayıcısının kısaltması. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için bir kolay ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- **Aralığa girdiğinde otomatik bağlan**: **Evet** olduğunda, bu ağın aralığına giren cihazlar otomatik olarak bağlanır. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.
  - **Mevcutsa daha fazla tercih edilen ağa bağlan**: Cihazlar tercih edilen birden çok ağın aralığında yer alıyorsa, tercih edilen ağı kullanmak için **Evet**'i seçin. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **SSID'sini yayınlamıyor olsa bile bu ağa bağlanın**: Ağınız gizli (SSID'si herkese açık şekilde yayınlanmıyor) olduğunda bile, ağınıza otomatik olarak bağlanmak üzere yapılandırma profili için **Evet**'i seçin. Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Tarifeli Bağlantı Sınırı**: Bir yönetici, ağ trafiğinin nasıl tarifelendirileceğini belirleyebilir. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Sınırsız**: Varsayılan ayar. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Sabit**: Ağ, ağ trafiği için sabit sınırla yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Ağ trafiği bayt başına ücretlendiriliyorsa bu seçeneği kullanın.

- **Çoklu oturum açma (SSO)** : Kimlik bilgilerinin bilgisayar ve Wi-Fi ağı oturum açma işleminde paylaşıldığı çoklu oturum açmayı (SSO) yapılandırmanıza olanak tanır. Seçenekleriniz şunlardır:
  - **Devre dışı bırak**: SSO davranışını devre dışı bırakır. Kullanıcının ağda ayrıca kimlik doğrulaması yapması gerekir.
  - **Kullanıcı cihazda oturum açmadan önce etkinleştir**: Kullanıcı oturum açma işleminden hemen önce ağda kimlik doğrulaması yapmak için SSO kullanın.
  - **Kullanıcı cihazda oturum açtıktan sonra etkinleştir**: Kullanıcı oturum açma işlemini tamamlandıktan hemen sonra ağda kimlik doğrulaması yapmak için SSO kullanın.
  - **Zaman aşımından önce kimlik doğrulanması gereken en uzun süre**: Ağda kimlik doğrulaması yapmadan önce beklenecek saniye sayısı üst sınırını (1-120 saniye arası) girin.
  - **Windows'un kullanıcıdan ek kimlik doğrulama kimlik bilgileri istemesine izin ver**: **Evet** seçildiğinde, kimlik doğrulama yöntemi gerektiriyorsa Windows sisteminin kullanıcıdan ek kimlik bilgileri istemesine izin verilir. Bu istemleri gizlemek için **Hayır**'ı seçin.

- **İkili ana anahtar önbelleğe almayı etkinleştir**: Kimlik doğrulamasında kullanılan PMK'yi önbelleğe almak için **Evet**'i seçin. Bu önbellek normalde ağda kimlik doğrulamasının daha hızlı tamamlanmasını sağlar. Wi-Fi ağına her bağlantıda karşılıklı kimlik doğrulamayı zorlamak için **Hayır**'ı seçin.

  - **Bir PMK'nin önbellekte depolanacağı en uzun süre**: İkili ana anahtarın (PMK) önbellekte depolanacağı dakika sayısını (5-1440 dakika arası) girin.
  - **Önbellekte depolanacak en fazla PMK sayısı**: Önbellekte depolanacak anahtar sayısını (1-255 arası) girin.

- **Ön kimlik doğrulamasını etkinleştir**: Ön kimlik doğrulaması profilin bağlantı öncesinde profildeki ağ için tüm erişim noktalarında kimlik doğrulaması yapmasını sağlar. Erişim noktaları arasında hareket ederken, ön kimlik doğrulaması kullanıcının veya cihazların daha hızlı yeniden bağlanmasını sağlar. Profilin aralık içinde yer alan bu ağın tüm erişim noktalarında kimlik doğrulaması yapması için **Evet**'i seçin. Kullanıcı veya cihazın her erişim noktasında ayrıca kimlik doğrulaması yapmasını gerektirmek için **Hayır**'ı seçin.

  - **En yüksek ön kimlik doğrulaması denemesi**: Ön kimlik doğrulaması için yapılacak deneme sayısını (1-16 arası) girin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için kullanılacak Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Korumalı PEAP** (PEAP)

    **EAP-TLS, EAP-TTLS ve PEAP ek ayarları**:
    
    > [!NOTE]
    > Şu anda, EAP türünü kullanırken yalnızca SCEP sertifika profilleri destekleniyor. PKCS sertifika profilleri desteklenmiyor. Kullanıcıdan her sertifika girişi istendiğinde, bir SCEP sertifikası seçtiğinizden emin olun.

    - **Sunucu Güveni**  

      **Sertifika sunucu adları**: **EAP-TLS**, **EAP-TTLS** veya **PEAP** EAP türleri ile kullanın. Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad girin. Bu bilgiyi girerseniz, bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.  

      **Sertifika doğrulaması için kök sertifika**: **EAP-TLS**, **EAP-TTLS** veya **PEAP** EAP türleri ile kullanın. Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin.  

      **Kimlik gizliliği (dış kimlik)** : **PEAP** EAP türü ile kullanın. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.  

    - **İstemci Kimlik Doğrulaması**

      **İstemci kimlik doğrulaması için istemci sertifikası (Kimlik sertifikası)** : **EAP-TLS** EAP türü ile kullanın. Bağlantı kimliğini doğrulamak için kullanılan sertifika profilini seçin.

      **Kimlik doğrulama yöntemi**: **EAP-TTLS** EAP türü ile kullanın. Bağlantı için kimlik doğrulama yöntemini seçin:  

      - **Sertifikalar**: Sunucuya gösterilen kimlik sertifikası olan istemci sertifikasını seçin.
      - **Kullanıcı Adı ve Parola**: Kimlik doğrulaması için bir **EAP dışı yöntem (iç kimlik)** girin. Seçenekleriniz şunlardır:

        - **Şifrelenmemiş parola (PAP)**
        - **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**
        - **Microsoft CHAP (MS-CHAP)**
        - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      **Kimlik gizliliği (dış kimlik)** : **EAP-TTLS** EAP türü ile kullanın. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Şirket ara sunucu ayarları**: Kuruluşunuz içinde ara sunucu ayarlarını kullanmak için seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir ara sunucu ayarı yapılandırılmaz.
  - **El ile yapılandır**: **Ara sunucu IP adresini** ve onun **Bağlantı noktası numarasını** girin.
  - **Otomatik olarak yapılandır**: Ara sunucu otomatik yapılandırma (PAC) betiğine işaret eden URL'yi girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

- **Wi-Fi profilinin Federal Bilgi İşleme Standardı (FIPS) ile uyumlu olmasını zorla** FIPS 140-2 standardıyla doğrulama yaparken bunu **Evet** olarak ayarlayın. Bu standart, şifreleme tabanlı güvenlik sistemleri kullanan tüm ABD federal resmi kurumlarında dijital olarak saklanan, hassas fakat gizli olmayan bilgileri korumak için gereklidir. **Hayır**’ı seçerseniz FIPS ile uyumlu olamazsınız.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="use-an-imported-settings-file"></a>İçeri aktarılan ayarlar dosyasını kullanma

Intune'da sağlanmayan tüm ayarlar için, başka bir Windows cihazından Wi-Fi ayarlarını dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm ayarlarıyla birlikte bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'da içeri aktarın ve bunu Wi-Fi profili olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- [Windows 8.1](wi-fi-settings-import-windows-8-1.md) için kullanılabilir ayarlara göz atın.
- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).
