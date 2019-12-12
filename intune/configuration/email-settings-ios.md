---
title: Microsoft Intune-Azure 'da iOS cihazları için e-posta ayarlarını yapılandırma | Microsoft Docs
description: Exchange sunucularını kullanma ve Azure Active Directory öznitelikleri alma dahil olmak üzere Microsoft Intune ' de iOS cihazlarına yapılandırabileceğiniz ve ekleyebileceğiniz tüm e-posta ayarlarının listesini görüntüleyin. Ayrıca, SSL 'yi etkinleştirebilir, sertifikalar veya Kullanıcı adı/parola ile kullanıcıların kimliğini doğrulayabilir ve Microsoft Intune ' deki cihaz yapılandırma profillerini kullanarak iOS cihazlarındaki e-postaları eşitleyebilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73de0ac94ff02e43fe73ca6357f6008ba71e3b93
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74390829"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune 'de iOS cihazları için e-posta ayarları ekleme

Microsoft Intune, e-posta sunucusuna bağlanmak için e-posta oluşturup yapılandırabilir, kullanıcıların kimliğini nasıl doğrulayacağınızı, şifreleme için S/MIME 'yi kullanmayı ve daha fazlasını yapabilirsiniz.

Bu makalede iOS çalıştıran cihazlar için kullanılabilen tüm e-posta ayarları listelenir ve açıklanmaktadır. Bu e-posta ayarlarını iOS cihazlarınıza göndermek veya dağıtmak için bir cihaz yapılandırma profili oluşturabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](../email-settings-configure.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Exchange ActiveSync hesap ayarları

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **Hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, Intune’un Azure Active Directory’den (AAD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı e-posta adresi biçiminde alır; örneğin `user1@contoso.com`
  - **sAM Hesap Adı**: Etki alanı gerektirir; örneğin `domain\user1`. Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: **AAD** (Azure Active Directory) veya **Özel**’i seçin.
      - **AAD**: Azure AD 'den öznitelikleri alın. Şunları da girin:
        - **AAD 'Den Kullanıcı etki alanı adı özniteliği**: kullanıcının **tam etki alanı adını** (`contoso.com`) veya **NetBIOS adı** (`contoso`) özniteliğini almayı seçin.

      - **Özel**: özel bir etki alanı adından öznitelikleri alın. Şunları da girin:
        - **Kullanılacak özel etki alanı adı**: ıntune 'un `contoso.com` veya `contoso`gibi etki alanı adı için kullandığı bir değer girin.

- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**: `user1@contoso.com` veya `user1`gibi, e-posta adresi olarak tam asıl adı kullanın.
  - **BIRINCIL SMTP adresi**: Exchange 'de oturum açmak için, `user1@contoso.com`gıbı birincil SMTP adresini kullanın.
- **Kimlik doğrulama yöntemi**: kullanıcıların e-posta sunucusunda kimliklerini nasıl doğrulayacağını seçin. Seçenekleriniz şunlardır:
  - **Sertifika**: Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin. Bu seçenek, kullanıcılarınız için en güvenli ve sorunsuz deneyim sağlar.
  - Kullanıcı adı **ve parola**: kullanıcılardan Kullanıcı adını ve parolasını girmesi istenir.
  - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).

  >[!NOTE]
  > Azure çok faktörlü kimlik doğrulaması desteklenmez.
  
- **SSL**: **Etkinleştir** olarak belirlenirse e-posta gönderirken, alırken ve Exchange sunucusuyla iletişim kurulurken Güvenli Yuva Katmanı (SSL) iletişimi kullanılır.
- **OAuth**: **Etkinleştir** olarak belirlenirse e-posta gönderirken, alırken ve Exchange ile iletişim kurulurken Open Authorization (OAuth) iletişimi kullanılır. OAuth sunucunuz sertifika kimlik doğrulaması kullanıyorsa, **Kimlik doğrulama yöntemi** olarak **Sertifika**’yı belirleyin ve sertifikayı profile ekleyin. Diğer durumlarda **Kimlik doğrulama yöntemi** olarak **Kullanıcı adı ve parola**’yı belirleyin. OAuth kullanılırken şunları yaptığınızdan emin olun:

  - Bu profili kullanıcılarınıza hedeflemeden önce e-posta çözümünüzün OAuth standardını desteklediğini onaylayın. Office 365 Exchange Online, OAuth standardını destekler. Şirket içi Exchange ve diğer iş ortağı veya üçüncü taraf çözümler ise OAuth’u desteklemeyebilir. Şirket içi Exchange, Modern Kimlik Doğrulaması için yapılandırılabilir ([Şirket İçi Exchange için Karma Modern Kimlik Doğrulaması Duyurusu](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) blog gönderisine bakın).

    E-posta profili OAuth kullanıyorsa ancak e-posta hizmeti bunu desteklemiyorsa, **Parolayı yeniden gir** seçeneği bozuk görünür. Örneğin kullanıcı Apple’ın cihaz ayarlarında **Parolayı yeniden gir**’i seçerse hiçbir şey olmaz.

  - OAuth etkin olduğunda son kullanıcılar çok faktörlü kimlik doğrulamasını (MFA) destekleyen, farklı bir “Modern Kimlik Doğrulaması” e-posta oturum açma deneyimine sahip olurlar. 

  - Bazı kuruluşlar, son kullanıcının [self servis uygulama erişimi](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access) sağlama becerisini devre dışı bırakır. Bu senaryoda bir Yönetici “iOS Hesapları” kurumsal uygulamasını oluşturup kullanıcıya Azure AD’de uygulama erişimi verene kadar Modern Kimlik Doğrulaması oturum açma denemesi başarısız olabilir.

    Varsayılan eylem, [Uygulama Erişim Paneli](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Uygulama Ekle** özelliğini **iş onayı olmadan** kullanarak uygulama eklemektir. Daha fazla bilgi için bkz. [uygulamalara kullanıcı atama](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > OAuth’u etkinleştirdiğinizde şunlar olur:  
  > 1. Hedeflenmiş cihazlara yeni bir profil verilir.
  > 2. Son kullanıcılardan kimlik bilgilerini yeniden girmeleri istenir.

## <a name="exchange-activesync-profile-configuration"></a>Exchange ActiveSync profili yapılandırması

> [!IMPORTANT]
> Bu ayarları yapılandırmak, var olan bir e-posta profili bu ayarları içerecek şekilde güncellense bile, cihaza yeni bir profil dağıtır. Kullanıcılardan Exchange ActiveSync hesap parolalarını girmesi istenir. Bu ayarlar, parola girildiğinde etkili olur.

- **Eşitlenecek Exchange verileri**: Exchange ActiveSync kullanırken, cihazda eşitlenen Exchange hizmetlerini seçin: Takvim, kişiler, anımsatıcılar, notlar ve e-posta. Seçenekleriniz şunlardır:
  - **Tüm veriler** (varsayılan): eşitleme tüm hizmetler için etkinleştirilmiştir.
  - **Yalnızca e-posta**: eşitleme yalnızca e-posta için etkinleştirilir. Diğer hizmetler için eşitleme devre dışı bırakıldı.
  - **Yalnızca takvim**: eşitleme yalnızca takvim için etkinleştirilmiştir. Diğer hizmetler için eşitleme devre dışı bırakıldı.
  - **Yalnızca takvim ve kişiler**: eşitleme yalnızca takvim ve kişiler için etkindir. Diğer hizmetler için eşitleme devre dışı bırakıldı.
  - **Yalnızca kişiler**: eşitleme yalnızca kişiler için etkinleştirilmiştir. Diğer hizmetler için eşitleme devre dışı bırakıldı.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **Kullanıcıların eşitleme ayarlarını değiştirmesine Izin ver**: kullanıcıların cihazdaki Exchange hizmetleri Için Exchange ActiveSync ayarlarını değiştirip değiştirebir zaman seçin: Takvim, kişiler, anımsatıcılar, notlar ve e-posta. Seçenekleriniz şunlardır:

  - **Evet** (varsayılan): kullanıcılar tüm hizmetlerin eşitleme davranışını değiştirebilir. **Evet** seçildiğinde *Tüm* hizmetlerde değişiklik yapılmasına izin verir.
  - **Hayır**: kullanıcılar tüm hizmetlerin eşitleme ayarlarını değiştiremezler. *Tüm* hizmetlerde **hiçbir** blok değişikliği yapma.

  > [!TIP]
  > **Exchange verilerini eşitleme** ayarını yalnızca bazı hizmetleri eşitlemek üzere yapılandırdıysanız, bu ayar için **Hayır** ' ı seçmeniz önerilir. **Hayır** seçilirse, kullanıcıların eşitlenmiş Exchange hizmetini değiştirmesini engeller.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="exchange-activesync-email-settings"></a>Exchange ActiveSync e-posta ayarları

- **S/MIME**: s/MIME, oturum açma, şifreleme ve şifre çözme yoluyla e-posta iletişimlerinizi ek güvenlik sağlayan e-posta sertifikaları kullanır. S/MIME 'yi bir e-posta iletisiyle birlikte kullandığınızda, gönderenin orijinalliğini ve iletinin bütünlüğünü ve gizliliğini onaylamanız gerekir.

  Seçenekleriniz şunlardır:

  - **S/MIME 'Yi devre dışı bırak** (varsayılan): e-postaları imzalamak, şifrelemek veya şifresini çözmek için s/MIME e-posta sertifikası kullanmaz.
  - **S/MIME 'Yi etkinleştir**: kullanıcıların iOS Native Mail uygulamasında e-postayı imzalayıp/veya şifrelemesine izin verir. Şunları da girin:

    - **S/MIME imzalama etkin**: **devre dışı bırak** (varsayılan), kullanıcıların iletiyi dijital olarak imzalamasına izin vermez. **Etkinleştir** ayarı, kullanıcıların girdiğiniz hesap için giden e-postayı dijital olarak imzalamasını sağlar. İmzalama, ileti alan kullanıcılara iletinin belirli bir gönderenden geldiğini ve gönderenin, gönderici olmaya hazır olmasını sağlar.
      - **Kullanıcının ayarı değiştirmesine Izin ver**: **Etkinleştir** seçeneği, kullanıcıların imzalama seçeneklerini değiştirmesine izin verir. **Devre dışı bırak** (varsayılan), kullanıcıların imzalamayı değiştirmesini engeller ve kullanıcıların yapılandırdığınız imzalamayı kullanmasına zorlar.
      - **İmza sertifikası türü**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu ayarı güncelleştirmez veya değiştirmez.
        - **Hiçbiri**: yönetici olarak, belirli bir sertifikayı zorlarsınız. Kullanıcıların kendi sertifikasını seçebilmeleri için bu seçeneği belirleyin.
        - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).
        - **Sertifikalar**: e-posta iletilerini imzalamak için kullanılan mevcut bir PKCS veya SCEP sertifika profilini seçin.
      - **Kullanıcının ayarı değiştirmesine Izin ver**: **Etkinleştir** ayarı, kullanıcıların imza sertifikasını değiştirmesine izin verir. **Devre dışı bırak** (varsayılan), kullanıcıların imza sertifikasını değiştirmelerini engeller ve yapılandırdığınız sertifikayı kullanmaya zorlar.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 ve üzeri
        - ıpados 12 ve daha yeni

    - **Varsayılan olarak şifreleyin**: **Etkinleştir** ayarı tüm iletileri varsayılan davranış olarak şifreler. **Devre dışı bırak** (varsayılan) tüm iletileri varsayılan davranış olarak şifrelemez.
      - **Kullanıcının ayarı değiştirmesine Izin ver**: **Etkinleştir** ayarı, kullanıcıların varsayılan şifreleme davranışını değiştirmesine izin verir. **Devre dışı bırak ayarı** , kullanıcıların şifreleme varsayılan davranışını değiştirmesini engeller ve kullanıcıların yapılandırdığınız şifrelemeyi kullanmasına zorlar.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 ve üzeri
        - ıpados 12 ve daha yeni

    - **İleti başına şifrelemeyi zorla**: ileti başına şifreleme, kullanıcıların gönderilmeden önce hangi e-postaların şifrelendiğini seçmesine olanak sağlar.

      **Etkinleştir** seçeneği, yeni bir e-posta oluştururken ileti başına şifreleme seçeneğini gösterir. Kullanıcılar daha sonra ileti başına şifrelemeyi kabul edebilir veya devre dışı bırakabilirsiniz. **Varsayılan olarak şifreleyin** ayarı da etkinleştirildiyse, ileti başına şifrelemeyi etkinleştirmek, kullanıcıların ileti başına şifrelemeyi geri almasına izin verir.

      **Devre dışı bırak** (varsayılan) ileti başına şifreleme seçeneğinin gösterilmesini engeller. **Varsayılan olarak şifreleyin** ayarı da devre dışıysa, ileti başına şifrelemeyi etkinleştirme, kullanıcıların ileti başına şifrelemeyi kabul etmesine olanak tanır.

      - **Şifreleme sertifikası türü**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu ayarı güncelleştirmez veya değiştirmez.
        - **Hiçbiri**: yönetici olarak, belirli bir sertifikayı zorlarsınız. Kullanıcıların kendi sertifikasını seçebilmeleri için bu seçeneği belirleyin.
        - **Türetilmiş kimlik bilgileri**: kullanıcının akıllı kartından türetilmiş bir sertifika kullanın. Daha fazla bilgi için bkz. [Microsoft Intune türetilmiş kimlik bilgilerini kullanma](../protect/derived-credentials.md).
        - **Sertifikalar**: e-posta iletilerini imzalamak için kullanılan mevcut bir PKCS veya SCEP sertifika profilini seçin.
      - **Kullanıcının ayarı değiştirmesine Izin ver**: **Enable** kullanıcıların şifreleme sertifikasını değiştirmesine izin ver ' i etkinleştirin. **Devre dışı bırak** (varsayılan), kullanıcıların şifreleme sertifikasını değiştirmelerini engeller ve yapılandırdığınız sertifikayı kullanmaya zorlar.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 ve üzeri
        - ıpados 12 ve daha yeni

- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-posta için gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına Izin ver**: **Etkinleştir** (varsayılan), kullanıcıların cihazlarında yapılandırılan farklı hesaplar arasında e-posta iletilerini taşımasına izin verir.
- **Üçüncü taraf uygulamalardan e-posta gönderilmesine Izin ver**: **Etkinleştir** (varsayılan), kullanıcıların bu profili e-posta göndermek için varsayılan hesap olarak seçmesine izin verir. Üçüncü taraf uygulamaların, örneğin e-postaya dosya eklemek için yerel e-posta uygulamasında e-posta açmasına izin verilir.
- **Son kullanılan e-posta adreslerini Eşitle**: **Etkinleştir** (varsayılan), kullanıcıların cihazda son kullanılan e-posta adresi listesini sunucuyla eşitlemesini sağlar.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](../device-profile-monitor.md).

[Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md)ve [Windows Phone 8,1](email-settings-windows-phone-8-1.md) cihazlarda e-posta ayarlarını yapılandırın.
