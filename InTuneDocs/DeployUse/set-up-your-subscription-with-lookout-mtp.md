---
title: "Lookout MTP aboneliğinizi ayarlama | Microsoft Intune"
description: "Bu konu, Lookout MTP’yi nasıl yapılandıracağınıza yönelik ayrıntılar sunar."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2196ff03975df1f8969e1522f7af459343694d
ms.openlocfilehash: 530a34c7c75a4fa73cbb62873e2d28883b91b57e


---

# Lookout mobil tehdit koruması aboneliğinizi ayarlama
Aboneliğinizi Lookout MTP hizmetine hazır hale getirmek için Lookout desteği (enterprisesupport@lookout.com), Azure Active Directory (Azure AD) aboneliğiniz hakkında aşağıdaki bilgilere gerek duyar. 

* **Azure AD Kiracı Kimliği**
* **Tam** Lookout MTP konsol erişimi için **Azure AD Grubu Nesne Kimliği**
* **Kısıtlı** Lookout MTP konsol erişimi için **Azure AD Grubu Nesne Kimliği** (isteğe bağlı)

Lookout destek ekibine vermeniz gereken bilgileri elde etmek için aşağıdaki bölümü kullanın.  

## Azure AD bilgilerinizi alma
### Azure AD kiracı kimliği
[Azure AD yönetim portalında](https://manage.windowsazure.com) oturum açın ve aboneliğinizi seçin. 

![Kiracı adını gösteren Azure AD sayfasının ekran görüntüsü](../media/mtp/aad_tenant_name.png) Aboneliğinizin adını seçtiğinizde karşınıza çıkan URL, abonelik kimliğini içerir.  Abonelik kimliğinizi bulma konusunda herhangi bir sorun yaşarsanız, abonelik kimliğinizi bulma konusundaki ipuçları için bu [Microsoft destek makalesine](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) bakın.   
### Azure AD Grup Kimliğinizi alma
Lookout MTP konsolu 2 erişim düzeyini destekler:  
* **Tam Erişim:** Azure AD yöneticisi, Tam Erişimi olacak kullanıcılar için bir grup oluşturabilir ve isteğe bağlı olarak Sınırlı Erişimi olacak kullanıcılar için bir grup oluşturur.  Yalnızca bu gruplardaki kullanıcılar **Lookout MTP konsolunda** oturum açabilir.
* **Kısıtlı Erişim:** Bu gruptaki kullanıcıların Lookout MTP konsolunun yapılandırma ve kayıtla ilgili çeşitli modüllerine erişimi olmaz; Lookout MTP konsolunun **Güvenlik İlkesi** modülüne kısıtlı erişime sahip olurlar.  

İzinler hakkında daha fazla ayrıntı için Lookout Web sitesindeki [bu makaleyi](https://personal.support.lookout.com/hc/en-us/articles/114094105653) okuyun.

**Grup Nesne Kimliği**, **Azure AD yönetim konsolunda**, grubun **Özellikler** sayfasında bulunur.

![özellikler sayfasının Grup Kimliği alanı vurgulanmış olarak ekran görüntüsü](../media/mtp/aad_group_object_id.png)

Bu bilgileri topladıktan sonra, Lookout desteği ile iletişime geçin (e-posta: enterprisesupport@lookout.com).

Lookout Desteği topladığınız bilgileri kullanarak aboneliğinizi başlatmak ve Lookout MTP Enterprise hesabınızı oluşturmak için birincil ilgili kişiyle çalışır.


## Lookout MTP ile aboneliğinizi yapılandırma
### 1. Adım: MTP’nizi ayarlama
Lookout desteği Lookout MTP Enterprise hesabınızı oluşturduktan sonra, Lookout MTP konsolunda oturum açabilirsiniz.   Oturum açma URL’sini içeren bir e-posta Lookout’tan şirketinizin ilgili kişisine gönderilir: https://aad.lookout.com/les?action=consent

Lookout MTP konsolunda ilk kez oturum açarken Azure AD rolü Genel Yönetici olan bir kullanıcı hesabı kullanmanız gerekir; çünkü Azure AD kiracınızı kaydetmek için Lookout MTP buna gerek duyar.   Bundan sonraki oturum açma işlemleri kullanıcının bu Azure AD ayrıcalık düzeyine sahip olmasını gerektirmez.  Bu ilk oturum açma işleminde, bir onay sayfası görüntülenir. Kaydı tamamlamak için **Kabul Et**’i seçin.

![Lookout MTP konsolunda ilk oturum açma sayfasının ekran görüntüsü](../media/mtp/lookout_mtp_initial_login.png) Kabul ettikten ve onayladıktan sonra, Lookout MTP konsoluna yönlendirilirsiniz. İlk kayıt sonrasındaki oturum açma işlemleri şu URL kullanılarak yapılabilir: https://aad.lookout.com

Oturum açma sorunlarıyla karşılaşırsanız [sorun giderme makalesine](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) göz atın.

Sonraki adımlar, [Lookout MTP Konsolunda](https://aad.lookout.com) Lookout MTP kurulumunu tamamlamak için yerine getirmeniz gereken görevleri özetler.

### 2. Adım: Intune bağlayıcısını yapılandırma

1.  Lookout MTP konsolunda **Sistem** modülüne gidin, **Bağlayıcılar** sekmesine tıklayın ve **Intune**’u seçin.

  ![bağlayıcılar sekmesi açık ve Intune seçeneği vurgulanmış olarak Lookout MTP konsolu ekran görüntüsü](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Bağlantı ayarları seçeneğinde, sinyal sıklığını dakika cinsinden yapılandırın.  Intune bağlayıcınız artık hazırdır.  

  ![bağlantı ayarları sekmesinin sinyal sıklığını gösterecek şekilde yapılandırılmış ekran görüntüsü](../media/mtp/lookout-mtp-connection-settings.png)

### 3. Adım: Kayıt gruplarını yapılandırma
**Kayıt Yönetimi** seçeneğinde, cihazları Lookout’a kaydedilmesi gereken bir kullanıcı grubu tanımlayın. Test etmek ve tümleştirme işleminin nasıl çalıştığına aşina olmak için küçük bir kullanıcı grubuyla başlamak en iyi yöntemdir.  Test sonuçlarınızdan memnun olduğunuzda, kayıt işlemini başka kullanıcı gruplarına genişletebilirsiniz.

Kayıt gruplarıyla başlamak için önce Lookout MTP’ye kaydettirmeye uygun bir ilk kullanıcı grubunu Azure AD güvenlik grubu olarak tanımlayın. Azure AD’de grup oluşturduktan sonra, Lookout MTP konsolundaki **Kayıt Yönetimi** seçeneğine gidin ve kayıt için Azure AD güvenlik grubunun **Görünen Adlarını** ekleyin.

Kullanıcı bir kayıt grubunda olduğunda, Azure AD’de tanımlanan ve desteklenen tüm cihazları kaydedilir ve Lookout MTP’de etkinleştirilmeye uygundur.  Lookout for Work uygulamasını desteklenen cihazlarında her açışlarında, cihaz Lookout MTP’de etkin hale gelir.
![Intune bağlayıcısı kayıt sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-enrollment.png)

Yeni cihazları denetleme aralığı olarak varsayılan değeri (5 dakika) kullanmak en iyi yöntemdir.

>[!IMPORTANT]
> Görünen ad büyük/küçük harfe duyarlıdır.  **Görünen Ad**’ı Azure portalındaki güvenlik grubunun **Özellikler** sayfasında gösterildiği gibi kullanın. Aşağıdaki resimde güvenlik grubunun **Özellikler** sayfasında, Görünen Ad’ın küçük büyük harf kombinasyonuyla yazıldığına dikkat edin.  Ancak başlık tamamen küçük harflerle yazılmıştır ve Lookout MTP konsoluna girmek için kullanılmamalıdır.
>![Azure portalı, Azure Active Directory hizmeti, özellikler sayfasının ekran görüntüsü](../media/mtp/aad-group-display-name.png)

Mevcut sürümde aşağıdaki sınırlamalar bulunmaktadır:  
* Grubun görünen adları için doğrulama yoktur.  Azure AD güvenlik grubunun Azure portalında gösterilen **GÖRÜNEN AD** alanındaki değeri kullandığınızdan emin olun.
* Grup içinde grup oluşturma şu anda desteklenmemektedir.  Belirtilen Azure AD güvenlik grupları yalnızca kullanıcıları içerebilir, iç içe grupları içeremez.


### 4. Adım: Durum eşitlemeyi yapılandırma
**Durum Eşitleme** seçeneğinde, Intune’a gönderilecek veri türünü belirtin.  Şu anda, Lookout Intune tümleştirmesinin düzgün çalışması için hem cihaz durumunu hem de tehdit durumunu etkinleştirmeniz gerekir.  Bunlar varsayılan olarak etkindir.
### 5. Adım: Hata raporu e-posta alıcı bilgilerini yapılandırma
**Hata Yönetimi** seçeneğinde, hata raporlarının gönderileceği e-posta adresini girin.

![Intune bağlayıcısı hata yönetimi sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-connector-error-notifications.png)

### 6. Adım: E-posta bildirimlerini yapılandırma
Tehditler hakkında e-posta uyarıları almak istiyorsanız, bildirimlerin gönderileceği kullanıcı hesabını kullanarak [Lookout MTP konsolunda](https://aad.lookout.com) oturum açın. **Sistem** modülünün **Tercihler** sekmesinde istediğiniz bildirimleri seçin ve bunları **AÇIK** olarak ayarlayın. Yaptığınız değişiklikleri kaydedin.

![Kullanıcı hesabının görüntülendiği tercihler sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-email-notifications.png) Artık e-posta bildirimleri almak istemiyorsanız, bildirimleri **KAPALI** olarak ayarlayın ve değişikliklerinizi kaydedin.
### 7. Adım: Tehdit sınıflandırmasını yapılandırma
Lookout MPT çeşitli türdeki mobil tehditleri sınıflandırır. [Lookout MTP tehdit sınıflandırmaları](http://personal.support.lookout.com/hc/en-us/articles/114094130693) kendileriyle ilişkilendirilmiş varsayılan risk düzeylerine sahiptir. Bunlar, şirket gereksinimlerinize uyacak şekilde herhangi bir zamanda değiştirilebilir.

![tehdit ve sınıflandırmaları gösteren ilke sayfasının ekran görüntüsü](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Burada belirtilen risk düzeyleri, Intune tümleştirmesi çalışma zamanında cihaz uyumluluğunu bu risk düzeylerine göre hesapladığından MTP’nin önemli bir yönünü oluşturur. Diğer bir deyişle, Intune yöneticisi bir cihazın yüksek, orta veya düşük düzeyde etkin bir tehdidi varsa, cihazın uyumlu olmadığını tanımlamak için ilke içinde bir kural koyar. MTP’deki tehdit sınıflandırma ilkesi, Intune’daki cihaz uyumluluk hesaplamasını doğrudan etkiler.

## Kayıt izleme
Kurulum tamamlandıktan sonra, Lookout MTP belirlenen kayıt gruplarına karşılık gelen cihazlar için Azure AD’yi yoklamaya başlar.  Kayıtlı cihazlar hakkındaki bilgileri Cihazlar modülünde bulabilirsiniz.  Cihazların ilk durumu, beklemede olarak gösterilir.  Cihaz durumu Lookout for Work uygulaması cihaza yüklendikten, açıldıktan ve etkinleştirildikten sonra değişir.  Cihaza gönderilen Lookout for Work uygulamasının nasıl alınacağına yönelik ayrıntılar için, [Lookout for Work uygulamalarını yapılandırma ve dağıtma](configure-and-deploy-lookout-for-work-apps.md) konusuna bakın.
## Sonraki adımlar
[Lookout MTP Intune bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO3-->

