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
ms.openlocfilehash: 3bbd90b5a317629bd5b4d87b619d89023053518d
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67884252"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Windows 10 ve üzeri cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profile"></a>Temel profil

- **Wi-Fi türü**: **Temel**’i seçin. 

- **Wi-Fi adı (SSID)** : Hizmet kümesi tanımlayıcısı için kısa. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için Kullanıcı dostu bir ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- Şu **aralıkta olduğunda otomatik olarak bağlan**: Yanıt **Evet**olduğunda, cihazlar bu ağın kapsama alanında olduklarında otomatik olarak bağlanır. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.

  - **Varsa, daha fazla tercih edilen ağa bağlan**: Cihazlar daha tercih edilen ağ aralığı içinde ise, tercih edilen ağı kullanmak için **Evet** ' i seçin. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **SSID yayınlamadığında bile bu ağa bağlan**: Ağ gizli olduğunda bile, ağınıza otomatik olarak bağlanmak için yapılandırma profili için **Evet** ' i seçin (yani SSID yayını herkese açık değildir). Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Tarifeli bağlantı sınırı**: Yönetici, ağın trafiğinin nasıl ölçülmediğini seçebilir. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Kısıtlanmamış**: Varsayılan. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Düzeltildi**: Ağ trafiği için sabit sınır ile yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Ağ trafiği bayt başına ücretlendirilir (bayt başına maliyet) Bu seçenek kullanılır.

- **Kablosuz güvenlik türü**: Ağınızdaki cihazların kimliğini doğrulamak için kullanılan güvenlik protokolünü girin. Seçenekleriniz şunlardır:
  - **Açık (kimlik doğrulaması yok)** : Yalnızca ağ güvenli değilse bu seçeneği kullanın.
  - **WPA/WPA2-Kişisel**: Daha güvenli bir seçenek ve genellikle Wi-Fi bağlantısı için kullanılır. Daha fazla güvenlik için önceden paylaşılan bir anahtar parolası veya ağ anahtarı girebilirsiniz. 

    - **Önceden paylaşılan anahtar** (PSK): İsteğe bağlı. Güvenlik türü olarak **WPA/WPA2-Kişisel**’i seçtiğinizde gösterilir. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin. 8-64 karakter arasında bir dize girin. Parolanız veya ağ anahtarınız 64 karakterden oluşuyorsa, onaltılık karakterler girin.
    
      > [!NOTE]
      > Wi-Fi profilini kaydettiğinizde, girdiğiniz PSK değeri güvenlik nedeniyle gösterilmez. PSK’nin profile kaydedilmesine rağmen önceden paylaşılan filigran **Yapılandırılmadı** olarak görünür. PSK’yi değiştirmek için yeni bir anahtar girin ve profili kaydedin. PSK’yi kaydeder, ilkeyi düzenler ve PSK’yi boş bırakırsanız mevcut PSK kullanılmaya devam eder.

- **Şirket proxy ayarları**: Kuruluşunuzun içindeki proxy ayarlarını kullanmayı seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Yapılandırılmış bir proxy ayarı yok.
  - **El ile yapılandır**: **Proxy sunucu IP adresi** ve **bağlantı noktası numarasını**girin.
  - **Otomatik olarak Yapılandır**: Proxy otomatik yapılandırma (PAC) betiğine işaret eden URL 'YI girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="enterprise-profile"></a>Kurumsal profil

- **Wi-Fi türü**: **Kuruluş**' ı seçin. 

- **Wi-Fi adı (SSID)** : Hizmet kümesi tanımlayıcısı için kısa. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için Kullanıcı dostu bir ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- Şu **aralıkta olduğunda otomatik olarak bağlan**: Yanıt **Evet**olduğunda, cihazlar bu ağın kapsama alanında olduklarında otomatik olarak bağlanır. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.
  - **Varsa, daha fazla tercih edilen ağa bağlan**: Cihazlar daha tercih edilen ağ aralığı içinde ise, tercih edilen ağı kullanmak için **Evet** ' i seçin. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **SSID yayınlamadığında bile bu ağa bağlan**: Ağ gizli olduğunda bile, ağınıza otomatik olarak bağlanmak için yapılandırma profili için **Evet** ' i seçin (yani SSID yayını herkese açık değildir). Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Tarifeli bağlantı sınırı**: Yönetici, ağın trafiğinin nasıl ölçülmediğini seçebilir. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Kısıtlanmamış**: Varsayılan. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Düzeltildi**: Ağ trafiği için sabit sınır ile yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Ağ trafiği bayt başına maliyetli ise bu seçenek kullanılır.

- **Çoklu oturum açma (SSO)** : , Kimlik bilgilerinin bilgisayar ve Wi-Fi ağ oturumu için paylaşıldığı çoklu oturum açmayı (SSO) yapılandırmanıza olanak tanır. Seçenekleriniz şunlardır:
  - **Devre dışı bırak**: SSO davranışını devre dışı bırakır. Kullanıcının ağda ayrıca kimlik doğrulaması yapması gerekir.
  - **Kullanıcı cihazda oturum açmadan önce etkinleştirin**: Kullanıcı oturum açma işleminden hemen önce ağda kimlik doğrulaması yapmak için SSO kullanın.
  - **Kullanıcı cihazda oturum açtıktan sonra Etkinleştir**: Kullanıcı oturum açma işlemi tamamlandıktan hemen sonra ağ kimlik doğrulaması için SSO kullanın.
  - **Zaman aşımından önce kimlik doğrulaması en fazla süre**: 1-120 saniyeden itibaren, ağda kimlik doğrulamadan önce beklenecek en fazla saniye sayısını girin.
  - **Windows 'un kullanıcıdan ek kimlik doğrulama kimlik bilgileri Isteminde bulunmasına Izin ver**: **Evet** seçildiğinde, kimlik doğrulama yöntemi gerektiriyorsa Windows sisteminin kullanıcıdan ek kimlik bilgileri sormasını sağlar. Bu istemleri gizlemek için **Hayır**'ı seçin.

- **İkili ana anahtar (PMK) önbelleğe almayı etkinleştir**: Kimlik doğrulamasında kullanılan PMK önbelleğini önbelleğe almak için **Evet** ' i seçin. Bu önbellek normalde ağda kimlik doğrulamasının daha hızlı tamamlanmasını sağlar. Wi-Fi ağına her bağlantıda karşılıklı kimlik doğrulamayı zorlamak için **Hayır**'ı seçin.

  - **BIR PMK 'nın önbellekte depolandığı en uzun süre**: Bir ikili ana anahtarın (PMK) önbellekte depolandığı dakika sayısını 5-1440 dakikadan itibaren girin.
  - **Önbellekte depolanan en fazla PMKs sayısı**: 1-255 adresinden önbellekte depolanan anahtarların sayısını girin.

- **Ön kimlik doğrulamayı etkinleştir**: Ön kimlik doğrulaması, profilin bağlanmadan önce profildeki ağ için tüm erişim noktalarında kimlik doğrulaması yapmasına izin verir. Erişim noktaları arasında hareket ederken, ön kimlik doğrulaması kullanıcının veya cihazların daha hızlı yeniden bağlanmasını sağlar. Profilin aralık içinde yer alan bu ağın tüm erişim noktalarında kimlik doğrulaması yapması için **Evet**'i seçin. Kullanıcı veya cihazın her erişim noktasında ayrıca kimlik doğrulaması yapmasını gerektirmek için **Hayır**'ı seçin.

  - **En fazla ön kimlik doğrulama denemesi**: 1-16 adresinden ön kimlik doğrulaması yapmaya yönelik denek sayısını girin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Korumalı PEAP** (PEAP)

    **EAP-TLS, EAP-TTLS ve PEAP ek ayarları**:
    
    > [!NOTE]
    > Şu anda, EAP türünü kullanırken yalnızca SCEP sertifika profilleri destekleniyor. PKCS sertifika profilleri desteklenmiyor. Kullanıcıdan her sertifika girişi istendiğinde, bir SCEP sertifikası seçtiğinizden emin olun.

    - **Sunucu Güveni**  

      **Sertifika sunucusu adları**: **EAP-TLS**, **EAP-TTLS**veya **PEAP** EAP türleriyle kullanın. Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad girin. Bu bilgiyi girerseniz, bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.  

      **Sunucu doğrulaması Için kök sertifika**: **EAP-TLS**, **EAP-TTLS**veya **PEAP** EAP türleriyle kullanın. Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin.  

      **Kimlik gizliliği (dış kimlik)** : **PEAP** EAP türüyle kullanın. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.  

    - **İstemci kimlik doğrulaması**

      **İstemci kimlik doğrulaması Için istemci sertifikası (kimlik sertifikası)** : **EAP-TLS** EAP türüyle kullanın. Bağlantı kimliğini doğrulamak için kullanılan sertifika profilini seçin.

      **Kimlik doğrulama yöntemi**: **EAP-TTLS** EAP türüyle kullanın. Bağlantı için kimlik doğrulama yöntemini seçin:  

      - **Sertifikalar**: Sunucuya sunulan kimlik sertifikası olan istemci sertifikasını seçin.
      - **Kullanıcı adı ve parola**: Kimlik doğrulaması için **EAP olmayan bir Yöntem (iç kimlik)** yöntemi girin. Seçenekleriniz şunlardır:

        - **Şifrelenmemiş parola (PAP)**
        - **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**
        - **Microsoft CHAP (MS-CHAP)**
        - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

      **Kimlik gizliliği (dış kimlik)** : **EAP-TTLS** EAP türüyle kullanın. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Şirket proxy ayarları**: Kuruluşunuzun içindeki proxy ayarlarını kullanmayı seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Yapılandırılmış bir proxy ayarı yok.
  - **El ile yapılandır**: **Proxy sunucu IP adresi** ve **bağlantı noktası numarasını**girin.
  - **Otomatik olarak Yapılandır**: Proxy otomatik yapılandırma (PAC) betiğine işaret eden URL 'YI girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

- **Wi-Fi profilini Federal bilgi Işleme standardı (FIPS) ile uyumlu olacak şekilde zorlayın**: FIPS 140-2 standardına göre doğrularken **Evet** ' i seçin. Bu standart, şifreleme tabanlı güvenlik sistemleri kullanan tüm ABD federal resmi kurumlarında dijital olarak saklanan, hassas fakat gizli olmayan bilgileri korumak için gereklidir. **Hayır**’ı seçerseniz FIPS ile uyumlu olamazsınız.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="use-an-imported-settings-file"></a>İçeri aktarılan ayarlar dosyasını kullanma

Intune'da sağlanmayan tüm ayarlar için, başka bir Windows cihazından Wi-Fi ayarlarını dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm ayarlarıyla birlikte bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'da içeri aktarın ve bunu Wi-Fi profili olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- [Windows 8.1](wi-fi-settings-import-windows-8-1.md) için kullanılabilir ayarlara göz atın.
- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md)
