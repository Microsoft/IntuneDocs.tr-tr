---
title: Microsoft Intune'da Windows 10 için bilgi noktası ayarları - Azure | Microsoft Docs
description: Windows 10 (ve üzeri) cihazlarınızı, Başlat menüsü özelleştirme, uygulama ekleme, görev çubuğu ve bir web tarayıcısı yapılandırma da dahil olmak üzere tekli uygulama veya çoklu uygulama bilgi noktaları olarak yapılandırın. Ayrıca, Microsoft Intune’da Windows Holographic for Business cihazlarını çoklu uygulama bilgi noktası olarak yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9dd7608981da1454c1f3be29eb6ff40a5d7f3394
ms.sourcegitcommit: 23adbc50191f68c4b66ea845a044da19c659ac84
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45562876"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Intune’da Windows 10 (ve sonrası) için bilgi noktası ayarları

Bilgi noktası profilleri, Windows 10 cihazlarını bir veya birden çok uygulama çalıştıracak şekilde yapılandırmak için kullanılır. Bilgi noktası profilini oluştururken, bir başlat menüsünün gösterilip gösterilmeyeceğini, web tarayıcısının yüklenip yüklenmeyeceğini ve daha fazlasını belirtebilirsiniz.

## <a name="kiosk-settings"></a>Bilgi noktası ayarları

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu isteğe bağlıdır ancak önerilir.
   - **Platform**: **Windows 10 ve üzeri**’ni seçin
   - **Profil türü**: **Bilgi Noktası (Önizleme)** seçin
   
4. **Bilgi Noktası** > **Ekle**’yi seçin.
5. Bilgi noktanız için **Bilgi noktası yapılandırma adı**'nı girin. Bu ad bir uygulama grubunu, bu uygulamaların başlat menüsündeki düzenini ve bu bilgi noktası yapılandırmasına atanan kullanıcıları tanımlar.
6. **Bilgi noktası modu**'nu seçin. **Bilgi noktası modu**, ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

    - **Yapılandırılmamış** (varsayılan): İlke, bilgi noktası modunu etkinleştirmez.
    - **Tekli tam ekran uygulama bilgi noktası**: Profil, cihazın tek bir kullanıcı hesabı gibi davranmasına olanak tanır ve cihazı tek bir Evrensel Windows Platformu (UWP) uygulamasını çalıştıracak şekilde kilitler. Dolayısıyla kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
    - **Çok uygulamalı bilgi noktası**: Profil, cihazın birden çok Evrensel Windows Platformu (UWP) uygulaması veya Win32 uygulaması çalıştırmasına olanak tanır. Ayrıca, farklı kullanıcı hesaplarına farklı uygulamalar atayabilirsiniz. Kullanıcılar yalnızca eklediğiniz uygulamaları kullanabilir. Çok uygulamalı bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak kullanıcılara anlaşılması kolay bir deneyim sunmasıdır. Bir de ihtiyaçları olmayan uygulamaları görünümden kaldırmasıdır.

#### <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Aşağıdaki ayarları girin:

- **Evrensel Windows Platformu (UWP) uygulama tanımlayıcısı**: Bilgi noktası uygulamasının **Uygulama kullanıcı modeli kimliği (AUMID)** değerini girin. Veya [İstemci Uygulamalar](apps-add.md)'ı kullanarak eklediğiniz yönetilen uygulamalardan birini seçin.

    Bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Kullanıcı hesabı türü**: Seçenekleriniz:

  - **Otomatik oturum açma**: Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `AzureAD\user@contoso.com` biçimini kullanın.
  - **Yerel kullanıcı hesabı**: Yerel (cihaz için) kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Azure AD hesap oturum açma bilgilerini girin. Azure AD etki alanlarına katılmış hesapları `domain\username@tenant.org` biçiminde girin.

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları
Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. 

[Çoklu uygulama bilgi noktaları](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune), izin verilen uygulamaları ve diğer ayarları listeleyen bir bilgi noktası yapılandırması kullanır.

Aşağıdaki ayarları girin:

- **Win32 uygulaması ekle**: Win32 uygulaması, geleneksel bir masaüstü uygulamasıdır. **Uygulama adı**'nı ve **Tanımlayıcı**'yı girin. **Tanımlayıcı**, yürütülebilir dosyanın cihaza göre tam yol adıdır.
- **Yönetilen uygulama ekle**: [Intune'da İstemci Uygulamalar](apps-add.md)'ı kullanarak eklediğiniz yönetilen uygulamalardan birini seçin.
- **AUMID ile uygulama ekle**: [Uygulamanın AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) değerini girin (UWP uygulamaları).
- **Görev Çubuğu**: Bilgi noktasında görev çubuğunu **Etkinleştirmeyi** (göster) veya **Yapılandırılmadı** (gizli) olarak bırakmayı seçebilirsiniz.
- **Başlangıç menüsü düzeni**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girin. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

  [Birden fazla uygulama çalıştıran bir Windows 10 bilgi noktası oluşturma](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), XML dosyaları kullanma ve oluşturma hakkında daha fazla ayrıntı sağlar.

- **Kullanıcı hesap türü**: Eklediğiniz uygulamaları kullanabilecek bir veya birden çok kullanıcı hesabı belirtin. Hesap oturum açtığında, yalnızca yapılandırmada tanımlanmış uygulamalar kullanılabilir durumda olur. Hesap, cihazda yerel bir hesap olabilir veya bilgi noktası uygulamasıyla ilişkili Azure AD hesap oturum açma bilgileri olabilir.

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `domain\user@tenant.com` biçimini kullanın.

## <a name="kiosk-web-browser-settings"></a>Bilgi noktası web tarayıcısı ayarları

Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Bilgi noktasına web tarayıcısı uygulamasını [İstemci Uygulamalar](apps-add.md)'ı kullanarak dağıttığınızdan emin olun.

1. Aşağıdaki ayarları girin:

    - **Varsayılan giriş sayfası URL'si**: Tarayıcı açıldığında veya yeniden başlatıldığında açılan bilgi noktası tarayıcısının varsayılan URL'sini girin.

    - **Giriş düğmesi**: Bilgi noktası tarayıcısının giriş düğmesini gösterin (**İzin ver**) veya gizleyin (**Yapılandırılmadı**). Varsayılan olarak düğme Yapılandırılmamıştır.

    - **Gezinti düğmesi**: İleri ve geri düğmelerini gösterin (**İzin ver**) veya gizleyin (**Yapılandırılmadı**). Varsayılan olarak gezinti düğmeleri Yapılandırılmamıştır.

    - **Oturumu sonlandır düğmesi**: Oturumu sonlandır düğmesini gösterin (**İzin ver**) veya gizleyin (**Yapılandırılmadı**). Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek, vb.) temizler ve varsayılan URL’ye geri gider. Varsayılan olarak düğme Yapılandırılmamıştır. 

    - **Kullanıcı, boşta kalma süresi sınırını aşarsa tarayıcıyı yenile**: Bilgi noktası tarayıcısının temiz bir durumda yeniden başlatılana kadar geçecek olan oturum başka kalma süresini dakika cinsinden girin. Değer tam sayı olarak 1-1440 dakikadır. Varsayılan değer boş veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

    - **Engellenen web siteleri**: Engellenen web sitesi URL'lerinin listesi (joker karakter desteğiyle). Tarayıcının belirli siteleri açmasını engellemek için bu ayarı kullanın. Liste içeren bir .csv dosyasını da **içeri aktarabilirsiniz**. İsterseniz, eklediğiniz siteleri içeren bir .csv dosyası da oluşturabilirsiniz (**Dışarı Aktarma**).

    - **Web sitesi özel durumları**: Engellenen web sitesi URL'leri arasındaki özel durumları listeleyin (joker karakter desteğiyle). Tarayıcının belirli siteleri açmasına izin vermek için bu ayarı kullanın. Bu özel durumlar, engellenen URL'lerin bir alt kümesidir. Bir URL engellenen web sitesi listesinde ve web sitesi özel durum listesinde yer alıyorsa, özel durum geçerlilik kazanır.

    Liste içeren bir .csv dosyasını da **içeri aktarabilirsiniz**. İsterseniz, eklediğiniz siteleri içeren bir .csv dosyası da oluşturabilirsiniz (**Dışarı Aktarma**).

2. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business cihazlarında, bu cihazları tekli uygulama bilgi noktası modunda veya çoklu uygulama bilgi noktası modunda çalıştırılacak şekilde yapılandırabilirsiniz. 

#### <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Aşağıdaki ayarları girin:

- **Evrensel Windows Platformu (UWP) uygulama tanımlayıcısı**: Bilgi noktası uygulamasının **Uygulama kullanıcı modeli kimliği (AUMID)** değerini girin. İsterseniz, [Mobil Uygulamalar](apps-add.md)'ı kullanarak eklediğiniz mevcut yönetilen uygulamalardan birini seçin.

    Kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Kullanıcı hesabı türü**: Yerel (cihaz için) kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Microsoft Hesabı (MSA) hesap oturum açma bilgilerini girmek için **Yerel kullanıcı hesabı**’nı seçin. **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları
Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır.

Aşağıdaki ayarları girin:

- **Yönetilen uygulama ekle**: [Intune'da İstemci Uygulamalar](apps-add.md)'ı kullanarak eklediğiniz yönetilen uygulamalardan birini seçin.
- **AUMID ile uygulama ekle**: [Uygulamanın AUMID](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) değerini girin (UWP uygulamaları).
- **Başlangıç menüsü düzeni**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girin. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens), Windows Holographic for Business cihazları için rehberlik sağlar ve belirli bir XML dosyası içerir.
- **Kullanıcı hesap türü**: Eklediğiniz uygulamaları kullanabilecek bir veya birden çok kullanıcı hesabı belirtin. Desteklenen seçenekler şunlardır: 
  - **HoloLens ziyaretçisi**: Ziyaretçi hesabı, [paylaşılan PC modu kavramlarında](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) anlatıldığı gibi, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir konuk hesabıdır.
  - **Azure AD kullanıcıları**: Cihazda oturum açabilmek için kullanıcı kimlik bilgilerini gerektirir. `domain\user@tenant.com` biçimini kullanın.
  - **Yerel Kullanıcı Hesapları**: Cihazda oturum açabilmek için kullanıcı kimlik bilgilerini gerektirir. 

Hesap oturum açtığında, yalnızca yapılandırmada tanımlanmış uygulamalar kullanılabilir durumda olur.

## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
