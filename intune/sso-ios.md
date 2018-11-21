---
title: Microsoft Intune - Azure’da iOS cihazlar için çoklu oturum açma özelliği ekleme | Microsoft Docs
description: Microsoft Intune’da iOS cihazları, kuruluşunuzun kaynakları ve verileri için kimlik doğrulaması olarak parola yerine çoklu oturum açma (SSO) kullanmak üzere oluşturun, yapılandırın, etkinleştirin veya bunlara izin verin. SSO’yu kullanmak için bir cihaz yapılandırma profili oluşturun ve kullanıcı ile cihazın kimliğini doğrulamak için UPN’i, cihaz kimliğini, uygulamalarınızı ve sertifikayı girin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c4d19807ecfcc33b957d5f6582f095427dbf978e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190209"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Microsoft Intune ile iOS cihazda çoklu oturum açma özelliğini kullanma

İş Kolu (LOB) uygulamalarının çoğunda güvenliği desteklemek için belirli bir düzeyde kullanıcı kimlik doğrulaması gereklidir. Çoğu durumda bu kimlik doğrulaması yöntemi, kullanıcının aynı kimlik bilgilerini birkaç kez yazmasını gerektirir ve bu da can sıkıcı olabilir. Kullanıcı deneyimini geliştirmek için geliştiriciler, çoklu oturum açma (SSO) kullanan uygulamalar geliştirerek kullanıcının kimlik bilgilerini girme sayısını azaltabilirler.

Bu makale, Microsoft Intune’da bir cihaz yapılandırma profili kullanarak iOS cihazlar için çoklu oturum açma özelliğini nasıl açacağınızı gösterir.

## <a name="before-you-begin"></a>Başlamadan önce

iOS cihazdaki çoklu oturum açma yükünde kullanıcı kimlik bilgileri deposunu aramak için kodlanmış bir uygulamanız olduğundan emin olun.

## <a name="create-the-sso-profile"></a>SSO profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için `ios sso profile` gibi bir ad girin.
    - **Açıklama**: Profili listede bulmanıza yardımcı olacak anahtar terimler içeren bir açıklama girin.
    - **Platform**: **iOS** platformunu seçin.
    - **Profil türü**: **Cihaz özellikleri**'ni seçin.

4. **Çoklu Oturum Açma**’yı seçin.

    ![Çoklu Oturum Açma bölmesi](./media/sso-blade.png)

5. Aşağıdaki ayarları girin: 

    - **AAD’den kullanıcı adı özniteliği**: Intune, Azure AD’deki her kullanıcı için bu özniteliği arar. Daha sonra, cihaza yüklenecek XML yükünü oluşturmadan önce ilgili alanı (UPN gibi) doldurur. Seçenekleriniz şunlardır:
    
        - **Kullanıcı Asıl Adı**: UPN, aşağıdaki gibi ayrıştırılır:

            ![Kullanıcı adı özniteliği](media/User-name-attribute.png)

            Ayrıca, **Bölge** metin kutusuna girdiğiniz metinle bölge değerinin üzerine yazabilirsiniz.

            Örneğin, Contoso'nun Avrupa, Asya ve Kuzey Amerika gibi çeşitli alt bölgeleri olabilir. Asya’daki kullanıcılarının SSO yükünü kullanmasını isteyebilirler ve uygulama, `username@asia.contoso.com` biçiminde UPN gerektirir. Bu durumda, **Kullanıcı Asıl Adı**’nı seçerseniz varsayılan olarak her kullanıcının bölgesi Azure AD’den alınır. Bu, *contoso.com* olabilir. Dolayısıyla özellikle Asya'daki kullanıcılar için bu yükü oluşturabilir ve bölgenin üzerine *asya.contoso.com* değerini yazabilirsiniz. Artık son kullanıcının UPN’si username@contoso.com yerine username@asia.contoso.com olur.

        - **Intune Cihaz Kimliği**: Intune, Intune Cihaz Kimliğini otomatik olarak seçer. 

            Varsayılan olarak, uygulamaların yalnızca cihaz kimliğini kullanması gerekir. Ancak uygulamanız bölge *ve* cihaz kimliği kullanıyorsa **Bölge** metin kutusuna bölgeyi yazabilirsiniz.

            > [!NOTE]
            > Varsayılan olarak, cihaz kimliğini kullanıyorsanız bölgeyi boş bırakın.

    - **Bölge**: URL’nin etki alanı bölümü.
    
    - **Çoklu Oturum Açma kullanacak URL ön ekleri**: Kuruluşunuzda kullanıcının çoklu oturum açma kimlik doğrulaması yapmasını gerektiren tüm URL’leri **ekleyin**. 

        Örneğin, kullanıcı bu sitelerden birine bağlandığında iOS cihaz çoklu oturum açma kimlik bilgilerini kullanır. Kullanıcının başka kimlik bilgisi girmesi gerekmez. Öte yandan çok faktörlü kimlik doğrulamasını etkinleştirdiyseniz, kullanıcıların ikinci kimlik doğrulamasını girmesi gerekir.

        > [!NOTE]
        > Bu URL'ler düzgün biçimlendirilmiş FQDN'ler olmalıdır. Apple, bu URL’lerin `http://<yourURL.domain>` biçiminde olmasını gerektirir.

        URL eşleştirme desenleri `http://` veya `https://` ile başlamalıdır. Basit dize eşleştirmesi kullanılır; dolayısıyla `http://www.contoso.com/` URL ön eki, `http://www.contoso.com:80/` ile eşleşmez. Öte yandan iOS 10.0 veya üzeri sürümlerde tüm eşleşen değerleri girmek için tek bir joker karakter (\*) kullanılabilir. Örneğin, `http://*.contoso.com/` hem `http://store.contoso.com/` hem de `http://www.contoso.com` ile eşleşir.

        `http://.com` ve `https://.com` desenleri sırasıyla tüm HTTP ve HTTPS URL'leriyle eşleşir.
    
    - **Çoklu Oturum Açma kullanan uygulamalar**: Son kullanıcıların cihazlarına çoklu oturum açma kullanabilecek uygulamalar **ekleyin**. 

        `AppIdentifierMatches` dizisi, uygulama paketi grubu kimlikleriyle eşleşen dizeler içermelidir. Bu dizeler tam eşleşme (`com.contoso.myapp` gibi) olabileceği gibi, \* joker karakterini kullanarak paket kimliğinde ön ek eşleştirmesi de girebilir. Joker karakterin nokta karakterinden (.) sonra kullanılması gerekir ve dizenin sonunda tek bir kez görünebilir (örneğin: `com.contoso.*`). Joker karakter eklendiğinde, paket kimlikleri bu ön ekle başlayan tüm uygulamaların hesaba erişimine izin verilir.

        **Uygulama Adı**’nı kullanarak paket kimliğini ayırt etmenize yardımcı olacak bir kolay ad ekleyin.
    
    - **Kimlik bilgileri yenileme sertifikası**: Kimlik doğrulama için parola yerine sertifika kullanılıyorsa kullanıcıya kimlik doğrulama sertifikası olarak dağıtılan SCEP veya PFX sertifikasını seçin. Normalde bu, kullanıcıya VPN, Wi-Fi veya e-posta gibi diğer profiller için dağıtılan sertifikayla aynı sertifikadır.

6. **Tamam** > **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin ve profili oluşturun. Profiliniz oluşturulduğunda **Cihaz yapılandırması - Profiller** listesinde görünür. 

## <a name="next-steps"></a>Sonraki adımlar

Diğer cihaz özelliği yapılandırma bilgileri için bkz. [Microsoft Intune’da cihaz özelliği ayarlarını yapılandırma](device-features-configure.md).

[Bu profili iOS cihazlarınıza atayın](device-profile-assign.md).
