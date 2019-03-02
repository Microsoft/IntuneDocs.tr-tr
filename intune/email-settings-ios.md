---
title: Microsoft Intune - Azure’da iOS cihazları için e-posta ayarları | Microsoft Docs
description: Yapılandırmak ve iOS cihazlara Exchange sunucularını kullanarak ve Azure Active Directory öznitelikleri alınırken dahil olmak üzere Microsoft Intune ekleyin tüm e-posta ayarları bir listesini görürsünüz. SSL'yi, sertifikalar veya kullanıcı adı/parola ile kullanıcıların kimliğini doğrulamak ve Intune cihaz yapılandırma profilleri kullanarak iOS cihazlarda e-postaları eşitler.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bc681b017cef5a91e7bc10bbdfbd6e14943e43a
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229097"
---
# <a name="email-profile-settings-for-ios-devices-in-intune"></a>Intune'da iOS cihazları için e-posta profili ayarları

Microsoft Intune oluşturma ve bir e-posta sunucusuna bağlanmak için kullanıcıların kimliklerini nasıl doğrulayacaklarını seçin, e-posta yapılandırma S/MIME şifreleme ve daha fazla bilgi için kullanın.

Bu makale, listeler ve iOS çalıştıran cihazlar için kullanılabilir tüm e-posta ayarlarını açıklar. Anında iletme veya bu e-posta ayarları iOS cihazlarına dağıtmak için bir cihaz yapılandırma profili oluşturabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](email-settings-configure.md#create-a-device-profile).

## <a name="email-settings"></a>E-posta ayarları

- **E-posta sunucusu**: Exchange sunucunuzun konak adı girin.
- **Hesap adı**: E-posta hesabı için görünen ad girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory (AAD gelen) Intune alır özniteliğidir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**: Adı aşağıdaki gibi alır `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı gibi e-posta adresi biçiminde alır `user1@contoso.com`
  - **sAM hesabı adı**: Etki alanı gibi gerektirir `domain\user1`.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: Seçin **AAD** (Azure Active Directory) veya **özel**.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **Kullanıcı etki alanı adı AAD özniteliğinden**: Almak için seçtiğiniz **tam etki alanı adı** veya **NetBIOS adı** kullanıcı özniteliği

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune için etki alanı adı gibi kullanan bir değer girin `contoso.com` veya `contoso`

- **Aad'den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) seçin. Exchange’de oturum açmak için birincil SMTP adresini kullanmak amacıyla **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.
- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin. Azure çok faktörlü kimlik doğrulaması desteklenmez.
  - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılan, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: **Etkinleştirme** e-posta alırken ve Exchange sunucusuyla iletişim kurarken gönderirken, Güvenli Yuva Katmanı (SSL) iletişimini kullanır.
- **OAuth**: **Etkinleştirme** açık yetkilendirme (OAuth) iletişim e-posta alırken ve Exchange ile iletişim kurarken gönderirken kullanır. OAuth sunucunuz sertifika kimlik doğrulaması kullanıyorsa, **Kimlik doğrulama yöntemi** olarak **Sertifika**’yı belirleyin ve sertifikayı profile ekleyin. Diğer durumlarda **Kimlik doğrulama yöntemi** olarak **Kullanıcı adı ve parola**’yı belirleyin. OAuth kullanılırken şunları yaptığınızdan emin olun:

  - Bu profili kullanıcılarınıza hedeflemeden önce e-posta çözümünüzün OAuth standardını desteklediğini onaylayın. Office 365 Exchange Online, OAuth standardını destekler. Şirket içi Exchange ve diğer iş ortağı veya üçüncü taraf çözümler ise OAuth’u desteklemeyebilir. Şirket içi Exchange, Modern Kimlik Doğrulaması için yapılandırılabilir ([Şirket İçi Exchange için Karma Modern Kimlik Doğrulaması Duyurusu](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) blog gönderisine bakın).

    E-posta profili OAuth kullanıyorsa ancak e-posta hizmeti bunu desteklemiyorsa, **Parolayı yeniden gir** seçeneği bozuk görünür. Örneğin kullanıcı Apple’ın cihaz ayarlarında **Parolayı yeniden gir**’i seçerse hiçbir şey olmaz.

  - OAuth etkin olduğunda son kullanıcılar çok faktörlü kimlik doğrulamasını (MFA) destekleyen, farklı bir “Modern Kimlik Doğrulaması” e-posta oturum açma deneyimine sahip olurlar. 

  - Bazı kuruluşlar, son kullanıcının [self servis uygulama erişimi](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access) sağlama becerisini devre dışı bırakır. Bu senaryoda bir Yönetici “iOS Hesapları” kurumsal uygulamasını oluşturup kullanıcıya Azure AD’de uygulama erişimi verene kadar Modern Kimlik Doğrulaması oturum açma denemesi başarısız olabilir.

    Varsayılan eylem, [Uygulama Erişim Paneli](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Uygulama Ekle** özelliğini **iş onayı olmadan** kullanarak uygulama eklemektir. Daha fazla bilgi için bkz. [uygulamalara kullanıcı atama](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > OAuth’u etkinleştirdiğinizde şunlar olur:  
  > 1. Hedeflenmiş cihazlara yeni bir profil verilir.
  > 2. Son kullanıcılardan kimlik bilgilerini yeniden girmeleri istenir.

- **S/MIME**: **S/MIME'yi etkinleştir** kullanıcıların oturum açmak ve/veya iOS yerel posta uygulamasında e-posta şifreleme izin vermek için. 

  S/MIME içeren bir e-posta iletisi kullandığınızda, gönderen ve bütünlüğü güvenilirliğini ve ileti gizliliğini onaylayın.

  - **S/MIME imzalama etkinleştirilmiş**: Seçin **etkinleştirme** dijital olarak giden e-posta girdiğiniz hesap için oturum açmasına izin vermek için. İletileri almasına yardımcı kullanıcılar imzalama ileti belirli gönderen ndan birisi göndereni gibi davranan ve gelen emin olun. **Devre dışı** iletinin dijital olarak oturum açmasına izin vermez.
    - **Kullanıcı ayarı değiştirmek izin**: Seçin **etkinleştirme** S/MIME imzalama davranışını değiştirmek kullanıcıların. **Devre dışı** kullanıcıların yapılandırılmış ayar S/MIME imzalama değiştirmesini engeller. İOS 12 bulunan ve daha yeni.

  - **S/MIME imzalama sertifikası**: E-posta iletileri imzalamak için kullanılan bir varolan PKCS veya SCEP sertifika profilini seçin.
    - **Kullanıcı ayarı değiştirmek izin**: Seçin **etkinleştirme** kullanıcıların imzalama sertifikasını değiştirilecek. **Devre dışı** kullanıcıların imzalama sertifikasının değiştirmelerini engeller ve kullanıcılar, yapılandırdığınız sertifikayı kullanmak için zorlar. İOS 12 bulunan ve daha yeni.

  - **Varsayılan olarak şifreleme**: **Etkinleştirme** varsayılan davranış olarak tüm iletileri şifreler. **Devre dışı** tüm iletileri varsayılan davranış olarak şifrelemez.
    - **Kullanıcı ayarı değiştirmek izin**: Seçin **etkinleştirme** kullanıcıların varsayılan şifreleme davranışını değiştirmesine izin vermek için. **Devre dışı** kullanıcıların varsayılan davranışı şifreleme değiştirmesini engeller ve kullanıcılar, yapılandırdığınız ayarını kullanmak için zorlar. İOS 12 bulunan ve daha yeni.

  - **İleti başına şifrelemeyi zorlama**: İleti başına şifreleme hangi e-postalar gönderilmeden önce şifrelenir seçmelerini sağlar. Seçin **etkinleştirme** oluştururken yeni bir e-posta, ileti başına şifreleme seçeneği gösterilecek. Kullanıcılar, ardından kabul et veya ileti başına şifreleme kullanmamak seçebilirsiniz. **Devre dışı** gösteren ileti başına şifreleme seçeneği engeller.

    Varsa **şifreleme varsayılan olarak** ayarı etkinleştirildiğinde, ileti başına şifreleme etkinleştirilmesi, kullanıcıların her ileti şifreleme dışında iyileştirilmiş sağlar. Varsa **şifreleme varsayılan olarak** ayarı devre dışı, ileti başına şifrelemeyi etkinleştirme şifreleme her ileti kabul etmek kullanıcıların sağlar.

  - **S/MIME şifreleme sertifikası**: E-posta iletileri şifrelemek için kullanılan bir varolan PKCS veya SCEP sertifika profilini seçin.
    - **Kullanıcı ayarı değiştirmek izin**: Seçin **etkinleştirme** kullanıcıların şifreleme sertifikasını değiştirilecek. **Devre dışı** kullanıcıların şifreleme sertifikası değiştirmelerini engeller ve kullanıcılar, yapılandırdığınız sertifikayı kullanmak için zorlar. İOS 12 bulunan ve daha yeni.
- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-postanın gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver**: **Etkinleştirme** kullanıcıların cihazlarında yapılandırılmış kullanıcılar e-posta iletilerini farklı hesaplar arasında taşımasına izin verir.
- **E-postanın üçüncü taraf uygulamalardan gönderilmesine izin ver**: **Etkinleştirme** kullanıcıların bu profili e-posta göndermek için varsayılan hesap olarak seçmesini sağlar. Üçüncü taraf uygulamaların, örneğin e-postaya dosya eklemek için yerel e-posta uygulamasında e-posta açmasına izin verilir.
- **Son kullanılan e-posta adreslerini Eşitle**: **Etkinleştirme** kullanıcıların sunucu ile bir cihazda yakın zamanda kullanılmış e-posta adreslerinin listesini eşitlemek olanak tanır.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

E-posta ayarlarını yapılandırmak [Android](email-settings-android.md), [Windows 10](email-settings-windows-10.md), ve [Windows Phone 8.1](email-settings-windows-phone-8-1.md) cihazlar.
