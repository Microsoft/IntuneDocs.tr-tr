---
title: Android ve Microsoft Intune - Azure'da Android Kurumsal e-posta ayarları | Microsoft Docs
description: Bir cihaz Exchange sunucularının kullandığı yapılandırma e-posta profilleri oluşturma ve Azure Active Directory öznitelikleri alınamıyor. SSL veya SMIME etkinleştirmek, sertifikalar veya kullanıcı adı/parola ile kullanıcıların kimliğini doğrulamak ve e-posta ve zamanlamaları eşitlemek üzerinde Android ve Android iş profili cihazları Intune kullanma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: b96363d679a6f09327bf9a1b46421e786d1956a8
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316891"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android ve Android Kurumsal cihaz ayarları Intune'da e-posta, kimlik doğrulama ve eşitlemeyi yapılandırma

Bu makalede, listeler ve Android ve Android Kurumsal cihazlarda kontrol edebilir farklı bir e-posta ayarları açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları ve e-postaları şifrelemek için SSL kullanmak, bir e-posta sunucusu yapılandırmak için kullanın.

Bir Intune yöneticisi olarak, e-posta ayarları oluşturup bunları aşağıdaki Android cihazlarına atayabilirsiniz:

- Android Samsung Knox Standard
- Android Kurumsal

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-posta sunucusu**: Exchange sunucunuzun konak adı girin.
- **Hesap adı**: E-posta hesabı için görünen ad girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory (AAD gelen) Intune alır özniteliğidir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**: Adı aşağıdaki gibi alır `user1` veya `user1@contoso.com`
  - **Kullanıcı adı**: Ad yalnızca aşağıdaki gibi alır `user1`
  - **sAM hesabı adı**: Etki alanı gibi gerektirir `domain\user1`. sAM hesap adı yalnızca Android cihazlar ile kullanılabilir. Android Kurumsal desteklenmez.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: Seçin **AAD** (Azure Active Directory) veya **özel**.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **Kullanıcı etki alanı adı AAD özniteliğinden**: Almak için seçtiğiniz **tam etki alanı adı** veya **NetBIOS adı** kullanıcı özniteliği

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune için etki alanı adı gibi kullanan bir değer girin `contoso.com` veya `contoso`

- **Aad'den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) veya Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.

- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="security-settings"></a>Güvenlik ayarları

- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME**: S/MIME şifrelemesi kullanarak giden e-posta gönderin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı**: E-posta eşitleme veya seçmek istediğiniz gün sayısını seçin **sınırsız** tüm kullanılabilir e-postayı eşitleyin.
- **Eşitleme zamanlaması**: Cihazların Exchange Server'dan verileri eşitlemek için zamanlamayı seçin. Ayrıca, verileri geldiğinde eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.

### <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**: Cihazlara eşitlemek istediğiniz içerik türlerini seçin. **Yapılandırılmamış** bu ayarı devre dışı bırakır. Ayarlandığında **yapılandırılmadı**, cihazı Intune ile eşitlenen ilke güçlendirilmiş gibi bir son kullanıcı etkinleştirir eşitleme eşitleme cihazı tekrar devre dışı bırakılır. 

  Aşağıdaki içeriğe eşitleyebilirsiniz: 
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="android-enterprise"></a>Android Kurumsal

- **E-posta uygulaması**: Şunlardan birini seçin **Gmail** veya **dokuz çalışma**
- **E-posta sunucusu**: Exchange sunucunuzun konak adı.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Active Directory (AD) veya bu e-posta profili için kullanıcı adını oluşturmak için kullanılan Azure AD özniteliğidir. **Birincil SMTP Adresi** olarak user1@contoso.com gibi bir değer seçin ya da **Kullanıcı Asıl Adı**’nı (kullanıcı1 veya user1@contoso.com gibi) belirtin.
- **Aad'den e-posta adresi özniteliği**: E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**'nı veya **Kullanıcı adı**'nı seçin.
- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
  - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **Eşitlenecek e-posta miktarı**: E-posta eşitleme veya seçmek istediğiniz gün sayısını seçin **sınırsız** tüm kullanılabilir e-postayı eşitleyin.
- **Eşitlenecek içerik türü** (yalnızca Nine Work): Cihazlara eşitlemek istediğiniz içerik türlerini seçin. **Yapılandırılmamış** bu ayarı devre dışı bırakır. Ayarlandığında **yapılandırılmadı**, cihazı Intune ile eşitlenen ilke güçlendirilmiş gibi bir son kullanıcı etkinleştirir eşitleme eşitleme cihazı tekrar devre dışı bırakılır. 

  Aşağıdaki içeriğe eşitleyebilirsiniz: 
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)
