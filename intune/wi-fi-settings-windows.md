---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için Wi-Fi ayarları | Microsoft Docs
description: Microsoft Intune'da Windows 10 ve üzeri cihazlar için Wi-Fi ayarlarını kullanarak Wi-Fi yapılandırma profilini ekleme veya oluşturma. Temel ayarları veya kurumsal düzey ayarları yapılandırabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/8/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.reviewer: tycast
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 880a81b49a78e7afd83aca510f85133e91416cf4
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514778"
---
# <a name="add-wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları ekleme

Belirli Wi-Fi ayarları ile bir profil oluşturabilir ve ardından bu profili Windows 10 ve üzeri cihazlarınıza dağıtabilirsiniz. Microsoft Intune; ağınızda kimlik doğrulama, bir önceden paylaşılan anahtar kullanma ve daha fazlası gibi pek çok özellik sunar.

Bu makalede bu ayarlar açıklanır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz profili oluşturma](device-profile-create.md).

## <a name="basic-profile"></a>Temel profil

- **Wi-Fi türü**: **Temel**’i seçin. 

- **Wi-Fi adı (SSID)**: İçin hizmet kümesi tanımlayıcısı. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için kullanımı kolay bir ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- **Aralık içinde olduğunda otomatik olarak bağlan**: Zaman **Evet**, cihazları bağlama otomatik olarak bu ağ aralıkta olduklarında. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.

  - **Varsa, daha tercih edilen bir ağa bağlan**: Cihazlar daha çok tercih edilen ağ aralığında ise ardından **Evet** tercih edilen ağ kullanmak için. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **Bu ağ için bile kendi SSID'si yayınlamadığında Bağlan**: Seçin **Evet** bile ağa (yani, kendi SSID'si değil yayın herkese açık şekilde) olarak gizlendiğinde, ağınıza otomatik olarak bağlanmak yapılandırma profili için. Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Ölçülen bağlantı sınırı**: Bir yönetici, ağ trafiğini nasıl ölçülüp seçebilirsiniz. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Kısıtlanmamış**: Varsayılan. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Sabit**: Ağ trafiği için sabit bir üst sınırı ile yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Bu seçenek, ağ trafiğini bayt (bayt başına maliyeti) başına ücretlendirilir gerektiğinde kullanılır.

- **Kablosuz güvenlik türü**: Ağınızdaki cihazların kimliklerini doğrulamak için kullanılan güvenlik protokolü girin. Seçenekleriniz şunlardır:
  - **Açık (kimlik doğrulamasız)**: Ağ güvenli değilse, yalnızca bu seçeneği kullanın.
  - **WPA/WPA2-Kişisel**: Daha güvenli seçeneği ve Wi-Fi bağlantısı için yaygın olarak kullanılır. Daha fazla güvenlik için önceden paylaşılan bir anahtar parolası veya ağ anahtarı girebilirsiniz. 

    - **Önceden paylaşılan anahtar** (PSK): İsteğe bağlı. Güvenlik türü olarak **WPA/WPA2-Kişisel**’i seçtiğinizde gösterilir. Kuruluşunuzun ağı ayarlandığında veya yapılandırıldığında bir parola veya ağ anahtarı da yapılandırılır. PSK değeri için bu parolayı veya ağ anahtarını girin. 8-64 karakter arasında bir dize girin. Parolanız veya ağ anahtarınız 64 karakterden oluşuyorsa, onaltılık karakterler girin.
    
      > [!NOTE]
      > Wi-Fi profilini kaydettiğinizde, girdiğiniz PSK değeri güvenlik nedeniyle gösterilmez. PSK’nin profile kaydedilmesine rağmen önceden paylaşılan filigran **Yapılandırılmadı** olarak görünür. PSK’yi değiştirmek için yeni bir anahtar girin ve profili kaydedin. PSK’yi kaydeder, ilkeyi düzenler ve PSK’yi boş bırakırsanız mevcut PSK kullanılmaya devam eder.

- **Proxy ayarlarını şirket**: Proxy ayarlarını kuruluşunuz içinde kullanmak bu seçeneği seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir proxy ayarı yapılandırılır.
  - **El ile yapılandırmanız**: Girin **Proxy server IPADDRESS** ve kendi **bağlantı noktası numarası**.
  - **Otomatik olarak yapılandırma**: Bir proxy otomatik yapılandırma (PAC) betiği için işaret eden URL girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="enterprise-profile"></a>Kurumsal profil

- **Wi-Fi türü**: Seçin **Kurumsal**. 

- **Wi-Fi adı (SSID)**: İçin hizmet kümesi tanımlayıcısı. Bu değer, cihazların bağlandığı kablosuz ağın gerçek adıdır. Bununla birlikte, bağlantıyı seçen kullanıcılar yalnızca yapılandırdığınız **Bağlantı adını** görür.

- **Bağlantı adı**: Bu Wi-Fi bağlantısı için kullanımı kolay bir ad girin. Girdiğiniz metin, kullanıcıların cihazlarında kullanılabilir bağlantılara göz attıklarında görecekleri addır.

- **Aralık içinde olduğunda otomatik olarak bağlan**: Zaman **Evet**, cihazları bağlama otomatik olarak bu ağ aralıkta olduklarında. **Hayır** olduğunda, cihazlar otomatik olarak bağlanmaz.
  - **Varsa, daha tercih edilen bir ağa bağlan**: Cihazlar daha çok tercih edilen ağ aralığında ise ardından **Evet** tercih edilen ağ kullanmak için. Bu yapılandırma profilindeki Wi-Fi ağını kullanmak için **Hayır**'ı seçin.

    Örneğin, **ContosoCorp** Wi-Fi ağını oluşturduğunuzu ve bu yapılandırma profili içinde **ContosoCorp**'u kullandığınızı varsayalım. Ayrıca, aralık içinde bir de **ContosoGuest** Wi-Fi ağınız olsun. Şirket cihazlarınız aralık içinde olduğunda, bunların otomatik olarak **ContosoCorp**'a bağlanmasını istiyorsunuz. Bu senaryoda, **Mevcutsa daha fazla tercih edilen ağa bağlan** özelliğini **Hayır** olarak ayarlayın.

  - **Bu ağ için bile kendi SSID'si yayınlamadığında Bağlan**: Seçin **Evet** bile ağa (yani, kendi SSID'si değil yayın herkese açık şekilde) olarak gizlendiğinde, ağınıza otomatik olarak bağlanmak yapılandırma profili için. Bu yapılandırma profilinin gizli ağınıza bağlanmasını istemiyorsanız **Hayır**'ı seçin.

- **Ölçülen bağlantı sınırı**: Bir yönetici, ağ trafiğini nasıl ölçülüp seçebilirsiniz. Daha sonra uygulamalar ağ trafiği davranışlarını bu ayara göre ayarlayabilir. Seçenekleriniz şunlardır:

  - **Kısıtlanmamış**: Varsayılan. Bağlantı tarifeli değildir ve trafikte kısıtlama yoktur.
  - **Sabit**: Ağ trafiği için sabit bir üst sınırı ile yapılandırılmışsa bu seçeneği kullanın. Bu sınıra ulaşıldıktan sonra ağ erişimi engellenir.
  - **Değişken**: Bu seçenek, ağ trafiğini, bayt Ücretli gerektiğinde kullanılır.

- **Çoklu oturum açma (SSO)**: Tek oturum için bilgisayar Paylaşılan kimlik bilgilerini ve Wi-Fi ağ oturum açma (SSO) yapılandırmanıza olanak sağlar. Seçenekleriniz şunlardır:
  - **Devre dışı**: SSO davranışı devre dışı bırakır. Kullanıcının ağda ayrıca kimlik doğrulaması yapması gerekir.
  - **Cihazda oturum önce kullanıcı işaretlerini etkinleştirme**: SSO kullanıcı oturum açma işleminin hemen önce ağ kimlik doğrulaması kullanın.
  - **Cihazda kullanıcı işaretinden sonra etkinleştirme**: SSO hemen kullanıcı oturum açma işlemi tamamlandıktan sonra ağ kimlik doğrulaması yapmak için kullanın.
  - **Zaman aşımından önce kimlik doğrulaması için en uzun süreyi**: 1-120 saniye ile ağda kimlik doğrulaması önce beklenecek saniye sayısını girin.
  - **Windows komut istemi kullanıcıdan ek kimlik doğrulama kimlik bilgilerini izin**: Seçme **Evet** Windows kimlik doğrulama yöntemini gerektiriyorsa kullanıcıdan ek kimlik bilgileri için sisteme izin verir. Bu istemleri gizlemek için **Hayır**'ı seçin.

- **Eşli Ana anahtarı (PMK) önbelleğe almayı etkinleştir**: Seçin **Evet** kimlik doğrulamasında kullanılan PMK önbellek için. Bu önbellek normalde ağda kimlik doğrulamasının daha hızlı tamamlanmasını sağlar. Wi-Fi ağına her bağlantıda karşılıklı kimlik doğrulamayı zorlamak için **Hayır**'ı seçin.

  - **Bir PMK önbelleğinde depolanan en uzun süreyi**: Eşli Ana anahtarı (PMK), 5-1440 dakika arasında önbelleğinde depolanan dakika sayısını girin.
  - **PMKs önbellekte depolanan en fazla sayısını**: 1-255 önbellekten içinde depolanan anahtarlar sayısını girin.

- **Ön kimlik doğrulamasını etkinleştirme**: Ön kimlik doğrulama için ağ profilindeki tüm erişim noktalarına bağlanmadan önce kimlik doğrulaması profili sağlar. Erişim noktaları arasında hareket ederken, ön kimlik doğrulaması kullanıcının veya cihazların daha hızlı yeniden bağlanmasını sağlar. Profilin aralık içinde yer alan bu ağın tüm erişim noktalarında kimlik doğrulaması yapması için **Evet**'i seçin. Kullanıcı veya cihazın her erişim noktasında ayrıca kimlik doğrulaması yapmasını gerektirmek için **Hayır**'ı seçin.

  - **En fazla ön kimlik doğrulama denemesi**: 1-16 ' preauthenticate için deneme sayısını girin.

- **EAP türü**: Güvenli kablosuz bağlantıların kimliğini doğrulamak için Genişletilebilir Kimlik Doğrulama Protokolü (EAP) türünü seçin. Seçenekleriniz şunlardır:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **Korumalı PEAP** (PEAP)

    **EAP-TLS, EAP-TTLS ve PEAP ek ayarları**:
    
    > [!NOTE]
    > Şu anda, EAP türünü kullanırken yalnızca SCEP sertifika profilleri destekleniyor. PKCS sertifika profilleri desteklenmiyor. Kullanıcıdan her sertifika girişi istendiğinde, bir SCEP sertifikası seçtiğinizden emin olun.

      - **Sunucu Güveni**  

        **Sertifika sunucu adları**: İle kullanma **EAP-TLS**, **EAP-TTLS**, veya **PEAP** EAP türleri. Güvenilen sertifika yetkiliniz (CA) tarafından verilen sertifikalarda yaygın olarak kullanılan bir veya birden çok ad girin. Bu bilgiyi girerseniz, bu Wi-Fi ağına bağlanırken kullanıcının cihazında görüntülenen dinamik güven iletişim kutusunu atlayabilirsiniz.  

        **Sunucu doğrulaması için kök sertifika**: İle kullanma **EAP-TLS**, **EAP-TTLS**, veya **PEAP** EAP türleri. Bağlantı kimliğini doğrulamak için kullanılan, güvenilen kök sertifika profilini seçin.  

        **Kimlik gizliliği (Dış kimlik)**: İle kullanma **PEAP** EAP türü. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.  

      - **İstemci kimlik doğrulaması**

        **İstemci kimlik doğrulaması (kimlik sertifikası) için istemci sertifikası**: İle kullanma **EAP-TLS** EAP türü. Bağlantı kimliğini doğrulamak için kullanılan sertifika profilini seçin.

        **Kimlik doğrulama yöntemi**: İle kullanma **EAP-TTLS** EAP türü. Bağlantı için kimlik doğrulama yöntemini seçin:  

          - **Sertifikaları**: Sunucuya gösterilen kimlik sertifikası olan istemci sertifikası seçin.
          - **Kullanıcı adı ve parola**: Girin bir **EAP dışı yöntem (iç kimlik)** kimlik doğrulama yöntemi. Seçenekleriniz şunlardır:

            - **Şifrelenmemiş parola (PAP)**
            - **Karşılıklı Kimlik Doğrulama Protokolü (CHAP)**
            - **Microsoft CHAP (MS-CHAP)**
            - **Microsoft CHAP Sürüm 2 (MS-CHAP v2)**

        **Kimlik gizliliği (Dış kimlik)**: İle kullanma **EAP-TTLS** EAP türü. Bir EAP kimlik isteğine yanıt olarak gönderilen metni girin. Bu metin herhangi bir değer olabilir. Kimlik doğrulaması sırasında başlangıçta bu anonim kimlik gönderilir ve ardından güvenli bir tünelde gerçek kimlik gönderilir.

- **Proxy ayarlarını şirket**: Proxy ayarlarını kuruluşunuz içinde kullanmak bu seçeneği seçin. Seçenekleriniz şunlardır:
  - **Hiçbiri**: Hiçbir proxy ayarı yapılandırılır.
  - **El ile yapılandırmanız**: Girin **Proxy server IPADDRESS** ve kendi **bağlantı noktası numarası**.
  - **Otomatik olarak yapılandırma**: Bir proxy otomatik yapılandırma (PAC) betiği için işaret eden URL girin. Örneğin, şunu girin: `http://proxy.contoso.com/proxy.pac`.

- **Wi-Fi profilini Federal Bilgi İşleme Standardı (FIPS ile) uyumlu olmaya zorla**: Seçin **Evet** karşı FIPS 140-2 standardı doğrularken. Bu standart, şifreleme tabanlı güvenlik sistemleri kullanan tüm ABD federal resmi kurumlarında dijital olarak saklanan, hassas fakat gizli olmayan bilgileri korumak için gereklidir. **Hayır**’ı seçerseniz FIPS ile uyumlu olamazsınız.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="use-an-imported-settings-file"></a>İçeri aktarılan ayarlar dosyasını kullanma

Intune'da sağlanmayan tüm ayarlar için, başka bir Windows cihazından Wi-Fi ayarlarını dışarı aktarabilirsiniz. Bu dışarı aktarma, tüm ayarlarıyla birlikte bir XML dosyası oluşturur. Ardından, bu dosyayı Intune'da içeri aktarın ve bunu Wi-Fi profili olarak kullanın. Bkz. [Windows cihazları için Wi-Fi ayarlarını dışarı ve içeri aktarma](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

- [Windows 8.1](wi-fi-settings-import-windows-8-1.md) için kullanılabilir ayarlara göz atın.
- Diğer platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md)
