---
title: "Intune'u iOS cihazında tekli oturum açma için yapılandırma"
titlesuffix: Azure portal
description: "Intune'u iOS cihazında tekli oturum açma için yapılandırmayı öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff71239a360b09ca831a6e99f5f7a759b08f5d56
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a>Intune'u iOS cihazında tekli oturum açma için yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

İş Kolu (LOB) uygulamalarının çoğunda güvenliği desteklemek için belirli bir düzeyde kullanıcı kimlik doğrulaması gereklidir. Çoğu durumda bu, kullanıcının aynı kimlik bilgilerini birkaç kez yazmasını gerektirir ve kullanıcı açısından can sıkıcı olabilir. Kullanıcı deneyimini geliştirmek için, geliştiriciler çoklu oturum açma kullanan uygulamalar geliştirerek kullanıcının kimlik bilgilerini girme sayısını azaltabilirsiniz.

iOS cihazı Çoklu Oturum Açma özelliğinden yararlanmak için, aşağıdaki koşulları karşılamalısınız:

- iOS cihazındaki çoklu oturum açma yükünde kullanıcı kimlik bilgileri deposunu aramak için kodlanmış bir uygulama.
- Intune'u iOS cihazında çoklu oturum açma için yapılandırma.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Intune'da iOS cihazında çoklu oturum açma yapılandırması için


1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz yapılandırması** dikey penceresinde **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**'u seçin, ad ve açıklama sağlayın, sonra da aşağıdaki ayarları yapılandırın:
   - **Platform**: **iOS** platformunu seçin. 
   - **Profil türü**: **Cihaz özellikleri**'ni seçin.
4. **Cihaz özellikleri** dikey penceresinde **Çoklu Oturum Açma**’yı seçin.

   ![Çoklu Oturum Açma dikey penceresi](./media/sso-blade.png)

2. Aşağıdaki özet tablosunun yardımıyla **Çoklu Oturum Açma** dikey penceresindeki alanları doldurun. Ayrıntılar için, tablodan sonraki bölümlere bakın.
   
   |Alan  |Notlar|
   |---------|---------|
   |**AAD'den kullanıcı adı özniteliği**|Intune'un AAD'deki her kullanıcı için baktığı ve cihaza yüklenen XML yükünü oluşturmadan önce ilgili alanı (UPN gibi) doldurduğu öznitelik.|
   |**Bölge**|URL'nin etki alanı bölümü.|
   |**Çoklu Oturum Açma kullanacak URL ön ekleri**|Kuruluşunuzda kullanıcının çoklu oturum açma kimlik doğrulaması yapmasını gerektiren tüm URL'ler|
   |**Çoklu Oturum Açma kullanan uygulamalar**|Kullanıcının cihazında bulunan ve çoklu oturum açma yükünü kullanan uygulamalar.|
   |**Kimlik bilgileri yenileme sertifikası**|Kimlik doğrulama için sertifika kullanılıyorsa, kullanıcıya kimlik doğrulama sertifikası olarak dağıtılan SCEP veya PFX sertifikasını seçin.|

Aşağıdaki bölümlerde, çoklu oturum açma alanlarının her biri hakkında daha fazla ayrıntı sağlanır.

### <a name="username-attribute-from-aad-and-realm"></a>AAD'den kullanıcı adı özniteliği ve Bölge

- Bu alanda **Kullanıcı Asıl Adı** seçilirse, aşağıdaki şekilde ayrıştırılır:

   ![Kullanıcı adı özniteliği](media/User-name-attribute.png)

   Ayrıca, **Bölge** metin kutusuna yazdığınız metinle bölge değerinin üzerine yazma seçeneğiniz de vardır.

   Örneğin, Contoso'nun Avrupa, Asya ve Kuzey Amerika gibi çeşitli alt bölgeleri olabilir. Asya'daki kullanıcılarının SSO yükünü kullanmasını isteyebilirler ve uygulama *username@asia.contoso.com* biçiminde UPN gerektirir. Bu durumda, **Kullanıcı Asıl Adı**'nı seçerseniz, varsayılan olarak her kullanıcının bölgesi AAD'den alınır ve bu yalnızca *contoso.com* olabilir. Dolayısıyla özellikle Asya'daki kullanıcılar için bu yükü oluşturabilir ve bölgenin üzerine *asya.contoso.com* değerini yazabilirsiniz. Artık son kullanıcının UPN'si *username@contoso.com* değil, *username@asia.contoso.com* olur.

- **Cihaz Kimliği**'ni seçerseniz, Intune tarafından otomatik olarak Intune Cihaz Kimliği seçilir.

   Varsayılan olarak, uygulamaların yalnızca cihaz kimliğini kullanması gerekir. Ancak uygulamanız cihaz kimliğine ek olarak bölgeyi de kullanıyorsa, bölgeyi **Bölge** metin kutusuna yazabilirsiniz.

   > [!NOTE]
   > Varsayılan olarak, cihaz kimliğini kullanıyorsanız bölgeyi boş bırakın.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Çoklu Oturum Açma kullanacak URL ön ekleri

Kuruluşunuzda bulunan ve kullanıcı kimlik doğrulaması gerektiren tüm URL'leri buraya yazın.

Örneğin, kullanıcı bu sitelerden birine bağlandığında iOS cihazı çoklu oturum açma kimlik bilgilerini kullanır ve kullanıcının başka kimlik bilgisi girmesi gerekmez. Öte yandan çok faktörlü kimlik doğrulamasını etkinleştirdiyseniz, kullanıcıların ikinci kimlik doğrulamasını girmesi gerekir.

> [!NOTE]
> Bu URL'ler düzgün biçimlendirilmiş FQDN'ler olmalıdır. Apple bunların `http://<yourURL.domain>` biçiminde olmasını gerektirir.

URL eşleştirme desenleri `http://` veya `https://` ile başlamalıdır. Basit dize eşleştirmesi kullanılır; dolayısıyla `http://www.contoso.com/` URL ön eki `http://www.contoso.com:80/` ile eşleşmez. Öte yandan iOS 9.0 veya üstünde, tüm eşleşen değerleri belirtmek için tek bir * joker karakteri kullanılabilir. Örneğin, `http://*.contoso.com/` hem `http://store.contoso.com/` hem de `http://www.contoso.com` ile eşleşir.
`http://.com` ve `https://.com` desenleri sırasıyla tüm HTTP ve HTTPS URL'leriyle eşleşir.

### <a name="apps-that-will-use-single-sign-on"></a>Çoklu Oturum Açma kullanan uygulamalar

Son kullanıcının cihazında bulunan ve Çoklu Oturum Açma yükünü kullanılabilecek uygulamaları gösterir.

`AppIdentifierMatches` dizisi, uygulama paketi grubu kimlikleriyle eşleşen dizeler içermelidir. Bu dizeler tam eşleşme (örneğin: `com.contoso.myapp`) olabileceği gibi, * joker karakterini kullanarak paket kimliğinde ön ek eşleştirmesi de belirtebilir. Joker karakterin nokta karakterinden (.) sonra kullanılması gerekir ve dizenin sonunda tek bir kez görünebilir (örneğin: `com.contoso.*`). Joker karakter eklendiğinde, paket kimlikleri bu ön ekle başlayan tüm uygulamaların hesaba erişimine izin verilir.

**Uygulama Adı** alanı, paket kimliğini tanımlamanıza yardımcı olacak bir kolay ad eklemek için kullanılır.

### <a name="credential-renewal-certificate"></a>Kimlik bilgileri yenileme sertifikası

Son kullanıcılarınızın kimliğini parola yerine sertifikayla doğruluyorsanız, bu alanı kullanıcıya kimlik doğrulama sertifikası olarak dağıtılmış olan SCEP veya PFX sertifikasını seçmek için kullanın. Normalde bu, kullanıcıya VPN, WiFi veya E-posta gibi diğer profiller için dağıtılan sertifikayla aynı sertifikadır.

## <a name="next-steps"></a>Sonraki adımlar

Diğer cihaz özelliği yapılandırma bilgileri için bkz. [Microsoft Intune’da cihaz özelliği ayarlarını yapılandırma](device-features-configure.md).