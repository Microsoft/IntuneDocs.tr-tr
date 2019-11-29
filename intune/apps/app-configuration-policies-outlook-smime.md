---
title: Microsoft Intune 'de iOS için Outlook ile S/MIME yapılandırma
description: Microsoft Intune 'de iOS için Outlook ile S/MIME anlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lance
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 348d1fe2fd236a2af11f7e58dc11530a5ce397bc
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564199"
---
# <a name="configure-smime-with-outlook-for-ios"></a>İOS için Outlook ile S/MIME yapılandırma

Güvenli/çok amaçlı Internet posta uzantıları (S/MIME), bir Exchange ActiveSync (EAS) hesabına ve bu hesaptan gönderilen e-posta için ek bir güvenlik katmanı sağlar. [Microsoft Outlook](https://aka.ms/omsmime) , kullanıcıların hem giden iletileri hem de ekleri şifrelemesine olanak tanımak için S/MIME kullanabilir ve Office 365 hesaplarını kullanırken yalnızca amaçlanan alıcının ileti içeriğini okuyabilmesini ve erişebilmesini sağlar. Kullanıcılar ayrıca bir iletiyi dijital olarak imzalayabilir ve bu da alıcıların, gönderenin kimliğini doğrulamasını ve iletinin kurcalanmadığını onaylamasını sağlar. Bu yetenek, sertifikalar kullanılarak mümkündür. Daha fazla bilgi için bkz. [S/MIME anlama](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)?redirectedfrom=MSDN).

> [!NOTE]
> Bu konu başlığı altında, güvenilen kök sertifikalarının [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)aracılığıyla nasıl dağıtılacağı açıklanmaktadır. Microsoft Uç Nokta Yöneticisi, tüm uç noktalarınızı yönetmek için tek ve tümleşik bir uç nokta yönetim platformudur. Bu Microsoft Endpoint Manager Yönetim Merkezi ConfigMgr ve Microsoft Intune tümleştirir.

## <a name="about-message-encryption"></a>İleti şifreleme hakkında
Kullanıcılar, şifreleme sertifikalarının ortak bir bölümüne sahip olmaları durumunda kuruluşlarındaki kişilere ve kuruluşlarındaki kişilere şifreli ileti gönderebilir. Şifreleme sertifikalarıyla ilişkili özel anahtarların her zaman şifrelenmiş ileti alıcısı tarafından korunması ve güvenliği sağlanmalıdır. Şifreleme sertifikasının özel anahtarı, alıcı tarafından iletinin şifresini çözmek için kullanılır.

Şifrelenmiş iletiler yalnızca iletiyi şifreleyen birine karşılık gelen sertifikaya sahip alıcılar tarafından okunabilir. Şifreleme sertifikası kullanılamayan alıcılara şifreli bir ileti göndermeye çalışırsanız, uygulama e-postayı göndermeden önce bu alıcıları kaldırmanızı ister.

## <a name="about-digital-signatures"></a>Dijital imzalar hakkında
Dijital olarak imzalanmış bir ileti, iletinin kurcalanmadığını ve gönderenin kimliğinin gerçek olduğunu reassures. Alıcılar yalnızca S/MIME destekleyen bir e-posta istemcisi kullanıyorsa dijital imzayı doğrulayabilirler.

## <a name="prerequisites"></a>Önkoşullar
- İOS için Outlook yalnızca Office 365 hesaplarında S/MIME 'yi destekler.
- Office 365 için S/MIME yapılandırılmış olmalıdır. Daha fazla bilgi için bkz. [Office 365 ' de S/MIME yapılandırma](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/How-to-Configure-S-MIME-in-Office-365/ba-p/584516).
- İmzalama ve şifreleme için kullanılabilecek sertifikalar veren bir sertifika yetkiliniz olmalıdır.
- Endpoint Manager aracılığıyla güvenilen kök sertifikaları dağıtın. Daha fazla bilgi için bkz. [Güvenilen sertifika profilleri oluşturma](~/protect/certificates-configure.md#create-trusted-certificate-profiles).
- Şifreleme sertifikaları Endpoint Manager 'a aktarılmalıdır. Daha fazla bilgi için bkz. [Intune ile içeri AKTARıLAN PKCS sertifikalarını yapılandırma ve kullanma](~/protect/certificates-imported-pfx-configure.md).
- Microsoft Intune için PFX bağlayıcısını yükleyip yapılandırın. Daha fazla bilgi için bkz. [Microsoft Intune IÇIN PFX Sertifika bağlayıcısını indirme, yükleme ve yapılandırma](~/protect/certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
- Cihazların Endpoint Manager 'dan otomatik olarak güvenilen kök ve S/MIME sertifikaları alması için MDM kaydı yapılmalıdır.

> [!IMPORTANT]
> İOS için Outlook ile S/MIME şifreleme sertifikaları kullanmak üzere Microsoft Intune için güncelleştirilmiş PFX bağlayıcısını (sürüm 6.1911.11.0 veya üzeri) indirmeniz ve kurmanız gerekir.

## <a name="smime-support-in-outlook-for-ios"></a>İOS için Outlook 'ta S/MIME desteği
İOS için Outlook, sertifikaları kullanarak iletilerin S/MIME imzalamayı ve şifrelemesini destekler. Birçok müşterinin, hem imzalama hem de şifrelemeyi destekleyen tek bir sertifikaya sahip olmanın aksine, farklı imzalama ve şifreleme sertifikaları vardır. İmzalama sertifikaları genellikle bireysel bir kullanıcının kayıtlı cihazlarında benzersizdir, ancak şifreleme sertifikaları ayrı bir kullanıcının kayıtlı cihazlarında paylaşılır. Genellikle, kullanıcılar S/MIME 'yi yıllarca kullanacaktır ve sertifikalar yenilendiğinde zaman içinde farklı şifreleme sertifikaları kullanacaktır. Özel anahtarları dahil olmak üzere şifreleme sertifikası geçmişlerini kullanıcının cihazında mevcut olmalıdır, böylece geçmişte bu sertifikalarla şifrelenmiş olabilecek e-posta okunabilir. İmzalama ve şifrelemeyi destekleyen tek bir sertifikaya sahip olmak da mümkündür.

İOS için Outlook, S/MIME için kullanılabilmesi amacıyla cihazlara sertifika tesliminde iki yolu destekler:

- **Kullanıcılar** , kendi kendilerine e-posta sertifikaları gönderebilir ve bunları mobil cihazlarındaki IOS Için Outlook 'taki eklere yükleyebilir.
- **Yöneticiler** , herhangi bir sertifika yetkilisinden bulunan şifreleme sertifikası geçmişlerini Endpoint Manager 'a aktarabilir. Endpoint Manager, bu sertifikaları kullanıcının kaydettiği herhangi bir cihaza otomatik olarak teslim eder. Genellikle, Basit Sertifika Kayıt Protokolü (SCEP) sertifikaları imzalamak için kullanılır. SCEP ile, özel anahtar oluşturulur ve kayıtlı cihazda depolanır ve kullanıcının kaydettiği her cihaza (örneğin, Red olmayan bir sertifika) gönderilir. Yöneticiler, kullanıcıları için şifreleme sertifikası geçmişlerini Endpoint Manager 'a aktarır ve böylece kullanıcının tüm şifreleme sertifikalarını kaydoldukları herhangi bir cihaza teslim eder. Son olarak, uç nokta Yöneticisi NıST 800-157 standardına destek gerektiren müşteriler için türetilmiş kimlik bilgilerini destekler. İOS 'ta Şirket Portalı, Intune 'dan imzalama ve şifreleme sertifikalarını almak için kullanılır.

## <a name="configuring-outlook-for-ios-smime-in-endpoint-manager"></a>Endpoint Manager 'da iOS S/MIME için Outlook 'U yapılandırma
Endpoint Manager 'da iOS S/MIME için Outlook 'u, iOS 'un kullanabileceği S/MIME sertifikalarını otomatik olarak teslim etmek de dahil olmak üzere yapılandırmak için aşağıdaki adımları kullanın:

### <a name="add-the-microsoft-outlook-app"></a>Microsoft Outlook uygulamasını ekleme
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. İOS için Microsoft Outlook uygulamasını App Store 'dan Endpoint Manager 'a ekleyin veya iOS için Outlook 'U Apple Volume Purchase Program 'tan eşitleyin. Daha fazla bilgi için bkz. [Microsoft Intune iOS Mağazası uygulamaları ekleme](~/apps/store-apps-ios.md) veya [Microsoft Intune ile Apple Volume Purchase program aracılığıyla satın alınan IOS ve MacOS uygulamalarını yönetme](~/apps/vpp-apps-ios.md).

### <a name="create-the-outlook-for-ios-smime-configuration-policy"></a>İOS S/MIME yapılandırma ilkesi için Outlook oluşturma

Aşağıdaki adımlar, Endpoint Manager 'da iOS için Outlook/MIME ilkesini oluşturmanıza ve yapılandırmanıza olanak tanır. Bu ayarlar, imzalama ve şifreleme sertifikalarının otomatik olarak teslimini sağlar.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **ekle** > **uygulamalar > ** **uygulama yapılandırma ilkeleri** ' ni seçin.<br>
**Yapılandırma Ilkesi Ekle** bölmesi görüntülenir.
2. Yapılandırma ilkesinin **adını** ve **açıklamasını** girin.
3. **Cihaz kayıt türü**olarak **yönetilen cihazlar** ' ı seçin.
4. **Platform**olarak **IOS/ıpados** ' ı seçin.
5. Daha önce eklediğiniz iOS için Microsoft Outlook uygulamasını bulmak ve ilişkilendirmek için **gerekli uygulamayı Seç** ' e tıklayın. 
6. Yapılandırma ayarlarını eklemek için **yapılandırma ayarları** ' na tıklayın. 
    - Yapılandırma **ayarları biçimi** ' nin yanında **yapılandırma tasarımcısını kullan** ' ı seçin ve varsayılan ayarları kabul edin. Daha fazla bilgi için bkz. [Microsoft Outlook yapılandırma ayarları](~/apps/app-configuration-policies-outlook.md).
7. **Outlook s/MIME ayarlarını**göstermek için **s/MIME** ' ye tıklayın.

    ![İOS S/MIME ayarları için Outlook ekran görüntüsü](./media/app-configuration-policies-outlook-smime/app-configuration-policies-outlook-smime-01.png)

8. **S/MIME 'Yi etkinleştir** ayarını **Evet**olarak belirleyin.
9. **Intune 'dan/MIME sertifikalarını** **Evet**olarak ayarlayın.
10. **Sertifika profili türü**' nün yanındaki **sertifikaları imzalama** altında, aşağıdaki seçeneklerden birini belirleyin:
    - **SCEP** – Microsoft Outlook tarafından imzalanmak üzere kullanılabilecek cihaz ve Kullanıcı için benzersiz olan bir sertifika oluşturur. İlgili bilgiler için bkz. [Intune Ile SCEP desteklemek için altyapıyı yapılandırma](~/protect/certificates-scep-configure.md) ve [bir SCEP sertifika profili oluşturma](~/protect/certificates-profile-scep.md#create-a-scep-certificate-profile). 
    - **PKCS içeri aktarılan sertifikalar** – Kullanıcı için benzersiz olan bir sertifika kullanır, ancak cihazlarda paylaşılabilir ve Kullanıcı adına yönetici tarafından Endpoint Manager 'a içeri aktarılmıştır. Sertifika, kullanıcının kaydettiği herhangi bir cihaza teslim edilir. Endpoint Manager, kayıtlı kullanıcıya karşılık gelen cihaza teslim etmek üzere imzalamayı destekleyen içeri aktarılan sertifikayı otomatik olarak seçer.
    - **Türetilmiş kimlik bilgileri** – imzalama için kullanılabilecek zaten cihazda olan bir sertifika kullanır. Sertifika, Intune 'daki türetilmiş kimlik bilgileri akışlarını kullanarak cihazda alınmalıdır.
11. **Sertifika profili türü**' nün yanındaki **şifreleme sertifikaları** ' nın altında, aşağıdaki seçeneklerden birini seçin:
    - **PKCS içeri aktarılan sertifikalar** : herhangi bir cihazda yönetici tarafından Endpoint Manager 'a aktarılmış tüm şifreleme sertifikaları sağlar. bir kullanıcının kaydettiği Endpoint Manager, içeri aktarılan sertifikayı veya kayıtlı kullanıcıya karşılık gelen cihaza teslim etmek üzere şifrelemeyi destekleyen sertifikaları otomatik olarak seçer.
    - **Türetilmiş kimlik bilgileri** – imzalama için kullanılabilecek zaten cihazda olan bir sertifika kullanır. Sertifika, Intune 'daki türetilmiş kimlik bilgileri akışlarını kullanarak cihazda alınmalıdır.
12. **Son Kullanıcı bildirimleri**' nin yanında, IOS için Outlook için S/MIME sertifikaları almak üzere **Şirket portalı** veya **e-posta** seçerek son kullanıcılara bildir ' i seçin.

    İOS 'ta, kullanıcıların S/MIME sertifikalarını almak için Şirket Portalı uygulamasını kullanmaları gerekir. Endpoint Manager, kullanıcıya Şirket Portalı, bir anında iletme bildirimi ve/veya bir e-posta ile ilgili bildirimler bölümü aracılığıyla S/MIME sertifikalarını almak için Şirket Portalı başlatması gerektiğini bildirir. Bildirimlerden birine tıkladığınızda, Kullanıcı sertifikaları alma işleminin ilerlemesini bildiren bir giriş sayfasına gönderilir. Sertifikalar alındıktan sonra Kullanıcı, e-postayı imzalamak ve şifrelemek için iOS için Microsoft Outlook içinden S/MIME kullanabilir.
    
    Son Kullanıcı bildirimleri aşağıdaki seçenekleri içerir:
       - **Şirket portalı** – seçilirse, kullanıcılar cihazında bir anında iletme bildirimi alır ve bu, bunları S/MIME sertifikalarının alınacağı Şirket Portalı giriş sayfasına götürür.
        - **E-posta** – son kullanıcıya bir e-posta gönderir ve bunların S/MIME sertifikalarını almak için şirket portalı başlatması gerektiğini bildiren bir e-posta gönderir. Kullanıcı, e-postadaki bağlantıya tıkladıklarında kayıtlı iOS cihazlarıyla çalışıyorsa, sertifikalarını almak için Şirket Portalı yeniden yönlendirilir.
    
13. Uygulama yapılandırma ilkesini Azure AD gruplarına atamak için **atamalar** ' ı seçin. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](~/apps/apps-deploy.md).

## <a name="next-steps"></a>Sonraki adımlar

- Daha fazla bilgi için bkz. [Microsoft Intune Için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
