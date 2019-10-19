---
title: Microsoft Intune-Azure 'da iOS cihazları için e-posta ayarlarını yapılandırma | Microsoft Docs
description: Exchange sunucularını kullanma ve Azure Active Directory öznitelikleri alma dahil olmak üzere Microsoft Intune ' de iOS cihazlarına yapılandırabileceğiniz ve ekleyebileceğiniz tüm e-posta ayarlarının listesini görüntüleyin. Ayrıca, SSL 'yi etkinleştirebilir, sertifikalar veya Kullanıcı adı/parola ile kullanıcıların kimliğini doğrulayabilir ve Microsoft Intune ' deki cihaz yapılandırma profillerini kullanarak iOS cihazlarındaki e-postaları eşitleyebilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4cbf9c29a1e694726b1b42f7072eea859f812751
ms.sourcegitcommit: 8c25aeefb7cbc6444a8596af22fccd1c5426877a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72593804"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune 'de iOS cihazları için e-posta ayarları ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune, e-posta sunucusuna bağlanmak için e-posta oluşturup yapılandırabilir, kullanıcıların kimliğini nasıl doğrulayacağınızı, şifreleme için S/MIME 'yi kullanmayı ve daha fazlasını yapabilirsiniz.

Bu makalede iOS çalıştıran cihazlar için kullanılabilen tüm e-posta ayarları listelenir ve açıklanmaktadır. Bu e-posta ayarlarını iOS cihazlarınıza göndermek veya dağıtmak için bir cihaz yapılandırma profili oluşturabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturun](../email-settings-configure.md).

> [!NOTE]
> Bu ayarlar tüm kayıt türleri için kullanılabilir. Kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](../ios-enroll.md).

## <a name="email-settings"></a>E-posta ayarları

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **Hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, Intune’un Azure Active Directory’den (AAD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı e-posta adresi biçiminde alır; örneğin `user1@contoso.com`
  - **sAM Hesap Adı**: Etki alanı gerektirir; örneğin `domain\user1`.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: **AAD** (Azure Active Directory) veya **Özel**’i seçin.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **AAD’den kullanıcı etki alanı adı**: Kullanıcının **Tam etki alanı adı** veya **NetBIOS adı** özniteliğini alma arasında seçim yapın

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune’un etki alanı adı olarak kullanacağı bir değer seçin; örneğin `contoso.com` veya `contoso`

- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) seçin. Exchange’de oturum açmak için birincil SMTP adresini kullanmak amacıyla **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.
- **Kimlik doğrulama yöntemi**: e-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı adı ve parola**, **sertifika**ya da **türetilmiş kimlik bilgilerini** seçin. Azure çok faktörlü kimlik doğrulaması desteklenmez.
  - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılan, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
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

- **S/MIME**: kullanıcıların iOS yerel posta uygulamasında e-postayı imzalayıp/veya şifrelemesine izin vermek için **s/MIME 'yi etkinleştirin** . 

  S/MIME 'yi bir e-posta iletisiyle birlikte kullandığınızda, gönderenin orijinalliğini ve iletinin bütünlüğünü ve gizliliğini onaylamanız gerekir.

  - **S/MIME imzalama etkin**: kullanıcıların, girdiğiniz hesap için giden e-postayı dijital olarak imzalamasını sağlamak için **Etkinleştir** ' i seçin. İmzalama, ileti alan kullanıcılara iletinin belirli bir gönderenden geldiğini ve gönderenin, gönderici olmaya hazır olmasını sağlar. **Devre dışı bırak ayarı** , kullanıcıların iletiyi dijital olarak imzalamasına izin vermez.
    - **Kullanıcının ayarı değiştirmesine Izin ver**: kullanıcıların S/MIME imzalama davranışını değiştirmesine izin vermek için **Etkinleştir** ' i seçin. **Devre dışı bırak** ayarı, kullanıcıların yapılandırdığınız S/MIME imzalama ayarını değiştirmelerini engeller. İOS 12 ve daha yeni sürümlerde kullanılabilir.

  - **S/MIME Imzalama sertifikası**: e-posta iletilerini imzalama için kullanılan mevcut bir PKCS veya SCEP sertifika profilini seçin.
    - **Kullanıcının ayarı değiştirmesine Izin ver**: kullanıcıların imzalama sertifikasını değiştirmesine izin vermek için **Etkinleştir** ' i seçin. **Devre dışı bırak ayarı** , kullanıcıların imza sertifikasını değiştirmesini önler ve kullanıcıların yapılandırdığınız sertifikayı kullanmasına zorlar. İOS 12 ve daha yeni sürümlerde kullanılabilir.

  - **Varsayılan olarak şifreleyin**: **Etkinleştir** ayarı tüm iletileri varsayılan davranış olarak şifreler. **Disable** , tüm iletileri varsayılan davranış olarak şifrelemez.
    - **Kullanıcının ayarı değiştirmesine Izin ver**: kullanıcıların varsayılan şifreleme davranışını değiştirmesine izin vermek için **Etkinleştir** ' i seçin. **Devre dışı bırak** ayarı, kullanıcıların şifreleme varsayılan davranışını değiştirmesini engeller ve kullanıcıları yapılandırdığınız ayarı kullanmaya zorlar. İOS 12 ve daha yeni sürümlerde kullanılabilir.

  - **İleti başına şifrelemeyi zorla**: ileti başına şifreleme, kullanıcıların gönderilmeden önce hangi e-postaların şifrelendiğini seçmesine olanak sağlar. Yeni bir e-posta oluştururken ileti başına şifreleme seçeneğini göstermek için **Etkinleştir** ' i seçin. Kullanıcılar daha sonra ileti başına şifrelemeyi kabul veya devre dışı bırakabilirsiniz. **Disable** , ileti başına şifreleme seçeneğinin gösterilmesini engeller.

    **Varsayılan olarak şifreleyin** ayarı etkinse, ileti başına şifrelemeyi etkinleştirme, kullanıcıların ileti başına şifrelemeyi geri almasına izin verir. **Varsayılan olarak şifreleyin** ayarı devre dışıysa, ileti başına şifrelemeyi etkinleştirme, kullanıcıların ileti başına şifrelemeyi kabul etmesine olanak tanır.

  - **S/MIME şifreleme sertifikası**: e-posta iletilerini şifrelemek için kullanılan mevcut bir PKCS veya SCEP sertifika profilini seçin.
    - **Kullanıcının ayarı değiştirmesine Izin ver**: kullanıcıların şifreleme sertifikasını değiştirmesine izin vermek için **Etkinleştir** ' i seçin. **Devre dışı bırak ayarı** , kullanıcıların şifreleme sertifikasını değiştirmesini engeller ve kullanıcıların yapılandırdığınız sertifikayı kullanmasına zorlar. İOS 12 ve daha yeni sürümlerde kullanılabilir.
- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-posta için gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver**: **Etkinleştir** olarak belirlenirse, kullanıcıların e-posta iletilerini cihazlarında yapılandırdıkları farklı hesaplara taşımalarına izin verilir.
- **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**: **Etkinleştir** olarak belirlenirse, kullanıcıların e-posta göndermek için varsayılan hesap olarak bu profili seçmelerine izin verilir. Üçüncü taraf uygulamaların, örneğin e-postaya dosya eklemek için yerel e-posta uygulamasında e-posta açmasına izin verilir.
- **Son kullanılan e-posta adreslerini eşitle**: **Etkinleştir** seçeneği, kullanıcıların cihazda son kullanılan e-posta adreslerinin listesini sunucuyla eşitlemelerine olanak tanır.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](../device-profile-monitor.md).

[Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md)ve [Windows Phone 8,1](email-settings-windows-phone-8-1.md) cihazlarda e-posta ayarlarını yapılandırın.
