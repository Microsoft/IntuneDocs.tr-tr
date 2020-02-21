---
title: Mobil cihaz yönetimi yetkilisini ayarlayın
titleSuffix: Microsoft Intune
description: Intune’da mobil cihaz yönetimi yetkilisini ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b611b2307b7b4f7e789e7db9d070e4b6b3f1350c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514498"
---
# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.

Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir. [MDM yetkilisini Intune konsolundan ayarlama](#set-mdm-authority-to-intune).

- **Intune ortak yönetim** -Intune bulut çözümünün Windows 10 cihazları için Configuration Manager ile tümleştirilmesi. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız. [Cihazların otomatik kaydını Intune 'A yapılandırın](https://docs.microsoft.com/configmgr/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Intune’u Microsoft 365 yönetim merkezinden siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir. Microsoft 365 yönetim merkezinden MDM yetkilisini ayarlayın.

- **Office 365 MDM** birlikte kullanımı Kiracınızda hem Office 365 hem de Intune için MDM 'yi etkinleştirebilir ve kullanabilir ve her bir kullanıcının mobil cihazlarını yönetmek için hangi hizmetin kullanılacağını dikte etmek üzere yönetim yetkilisini her bir kullanıcı için Intune veya Office 365 için MDM olarak ayarlayabilirsiniz. Kullanıcının yönetim yetkilisi, kullanıcıya atanan lisansa göre tanımlanır. Daha fazla bilgi için bkz. [Office 365 IÇIN MDM Ile birlikte bulunma Microsoft Intune](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365)

## <a name="set-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

MDM yetkilisini henüz ayarlamadıysanız, aşağıdaki adımları izleyin.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **mobil cihaz yönetim yetkilisi** ayarını açmak için turuncu başlık ' ı seçin. Turuncu başlık, ancak henüz MDM yetkilisini ayarlamadıysanız görüntülenir.
2. **Mobil Cihaz Yönetimi Yetkilisi** altında, aşağıdakilerden birini MDM yetkiliniz olarak belirtin:
   - **Intune MDM Yetkilisi**
   - **Yok.**

   ![Intune tarafından ayarlı mobil cihaz yönetim yetkilisi ekranının ekran görüntüsü](./media/mdm-authority-set/set-mdm-auth.png)

   MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

### <a name="workflow-of-intune-administration-ui"></a>Intune Yönetim UI’si iş akışı
Android veya Apple cihaz yönetimi etkinleştirildiğinde Intune, ilgili cihazları yönetmek üzere bu üçüncü taraf hizmetleriyle tümleştirmek için cihaz ve kullanıcı bilgilerini gönderir.

Veri pencerelerini paylaşma onayı ekleyen senaryolar şu durumlarda eklenir:
- Android iş profillerini etkinleştirdiğinizde.
- Apple MDM anında iletme sertifikalarını etkinleştirdiğinizde ve karşıya yüklediğinizde.
- Aygıt Kayıt Programı, School Manager ve Volume Purchasing Program gibi Apple hizmetlerinden herhangi birini etkinleştirdiğinizde.

Bu durumların tamamında onay kesinlikle bir mobil cihaz yönetimi hizmetinin çalışmasıyla ilgilidir. Örneğin bir BT yöneticisinin Google veya Apple cihazların kaydını yetkilendirmesini onaylamak gibi. Yeni iş akışları yayınlandığında hangi bilgilerin paylaşıldığına ilişkin belgeler şu konumlarda bulunabilir:
- [Intune’un Google’a gönderdiği veriler](https://aka.ms/Data-intune-sends-to-google)
- [Intune’un Apple’a gönderdiği veriler](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Dikkat Edilmesi Gereken Önemli Noktalar
Yeni MDM yetkilisine geçtikten sonra cihazın iade edilmesi ve hizmetle eşitlenmesi için bir geçiş süresi (sekiz saate kadar) olması olasıdır. Kayıtlı cihazların değişiklikten sonra yönetilmeye ve korumaya devam edecek şekilde emin olmak için yeni MDM yetkilisinde ayarları yapılandırmanız gerekir. 
- Yeni MDM yetkilisinden (tek başına Intune) gelen ayarların cihazdaki mevcut ayarların yerini alması için değişiklik sonrasında cihazların hizmete bağlanması gerekir.
- MDM yetkilisini değiştirdikten sonra önceki MDM yetkilisinden bazı temel ayarlar (örneğin, profiller) en fazla yedi güne kadar veya cihaz hizmete ilk kez bağlanana kadar cihazda kalır. Yeni MDM yetkilisinde uygulama ve ayarları (ilkeler, profiller, uygulamalar vb.) mümkün olan en kısa sürede yapılandırmanız ve ayarı, kayıtlı cihazları olan kullanıcıları içeren Kullanıcı gruplarına dağıtmanız önerilir. MDM yetkilisindeki değişiklikten sonra cihaz hizmete ilk bağlandığı zaman, yeni MDM yetkilisinden yeni ayarları alacaktır, böylece yönetim ve korumada boşluk oluşması önlenecektir.
- İlişkili kullanıcıları olmayan cihazlar (genellikle iOS/ıpados Aygıt Kayıt Programı veya toplu kayıt senaryolarında) yeni MDM yetkilisine geçirilmez. Bu cihazları yeni MDM yetkilisine taşımak için destek ile iletişime geçip yardım almanız gerekir.

## <a name="change-mdm-authority-to-office-365"></a>MDM yetkilisini Office 365 olarak değiştirme

Office 365 MDM 'yi etkinleştirmek için (veya mevcut Intune hizmetinize ek olarak MDM birlikte kullanımını etkinleştirmek için), [https://protection.office.com](https://protection.office.com)gidin, **veri kaybı engellemesini** > **cihaz güvenlik Ilkeleri** > **yönetilen cihazların listesini görüntüle** > **izin ver**' i seçin.

Daha fazla bilgi için bkz. [Office 365’te Mobil Cihaz Yönetimi (MDM) ayarlama](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Son kullanıcıların yalnızca Office 365 MDM tarafından yönetilmesini istiyorsanız Office 365 MDM’yi etkinleştirdikten sonra atanmış tüm Intune ve/veya EMS lisanslarını kaldırın.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.

## <a name="remove-mdm-authority"></a>MDM yetkilisini kaldırma

MDM yetkilisi tekrar Bilinmeyen olarak değiştirilemez. MDM yetkilisi, hizmet tarafından hangi Portal kayıtlı cihazların (Microsoft Intune veya Office 365 MDM) rapor olduğunu tespit etmek için kullanılır.

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>MDM yetkilisini değiştirdikten sonra ne olur

- Intune hizmeti, bir kiracının MDM yetkilisinin değiştiğini algıladığında kayıtlı tüm cihazlara hizmete iade etmeleri ve hizmetle eşitlenmeleri için bir bildirim iletisi gönderir (bu bildirim, düzenli olarak zamanlanmış iadenin dışındadır). Bu nedenle, kiracının MDM yetkilisi tek başına Intune 'dan değiştirildikten sonra, açık ve çevrimiçi olan cihazlar hizmete bağlanır, yeni MDM yetkilisini alır ve yeni MDM yetkilisi tarafından yönetilir. Bu cihazların yönetiminde ve korunmasında bir kesinti olmaz.
- MDM yetkilisindeki değişiklik sırasında (veya hemen sonrasında) açık ve çevrimiçi olan cihazlarda bile, cihazlar yeni MDM yetkilisi altında hizmete kaydolmadan önce sekiz saate kadar (bir sonraki zamanlanmış düzenli iadenin zamanına bağlı olarak) bir gecikme olur.    

  > [!IMPORTANT]    
  > MDM yetkilisini değiştirdiğiniz saat arasında ve yenilenen APNs sertifikası yeni yetkiliye yüklendiğinde, iOS/ıpados cihazları için yeni cihaz kayıtları ve cihaz denetimi başarısız olur. Bu nedenle MDM yetkilisindeki değişiklikten hemen sonra APNs sertifikasını gözden geçirmeniz ve yeni yetkiliye yüklemeniz önemlidir.

- Kullanıcılar, el ile cihazdan hizmete iadeyi başlatarak hızlıca yeni MDM yetkilisine geçebilir. Bu değişikliği Şirket Portalı uygulamasını kullanarak ve bir cihaz uyumluluk denetimi başlatarak kolaylıkla yapabilirler.
- Cihazların, MDM yetkilisindeki değişiklikten sonra iade ettikten ve hizmetle eşitlendikten sonra düzgün çalıştığını doğrulamak için, yeni MDM yetkilisindeki cihazları arayın.
- Cihaz MDM yetkilisindeki değişiklik sırasında çevrimdışı olduğu zaman ile hizmete giriş yaptığı zaman arasında bir ara dönem vardır. Bu ara dönemde cihazın korunduğundan ve işlevsel olduğundan emin olmak için aşağıdaki profiller yedi güne kadar (veya cihaz yeni MDM yetkilisine bağlanıp mevcut ayarları yenileriyle değiştirene kadar) cihazda kalır:
  - E-posta profili
  - VPN profili
  - Sertifika profili
  - Wi-Fi profili
  - Yapılandırma profilleri
- Yeni MDM yetkilisine geçtikten sonra, Microsoft Intune yönetim konsolunda doğru uyumluluk verilerinin gösterilmesi bir haftayı bulabilir. Ancak Azure Active Directory’deki ve cihazdaki uyumluluk durumları doğru olacaktır, böylece cihaz korunmaya devam eder.
- Mevcut ayarların üzerine yazılması amaçlanan yeni ayarların, öncekilerle aynı ada sahip olduğundan emin olun. Aksi takdirde eski ayarların üzerine yazılmaz. Ve cihazlarda gereksiz profiller ve ilkeler ortaya çıkabilir.    

  > [!TIP]    
  > En iyi uygulama olarak, tüm yönetim ayarları ve yapılandırmaları ile dağıtımları, MDM yetkilisindeki değişiklik tamamlandıktan hemen sonra oluşturmalısınız. Böylece, ara dönemde cihazların korunduğundan ve etkin olarak yönetildiğinden emin olursunuz.

- MDM yetkilisini değiştirdikten sonra cihazların yeni yetkiliye başarılı bir şekilde kaydedildiğini doğrulamak için aşağıdaki adımları gerçekleştirin:   
  - Yeni cihaz kaydetme
  - Yeni kaydedilen cihazın yeni MDM yetkilisinde göründüğünden emin olun.
  - Yönetim konsolunu kullanarak cihazda Uzaktan Kilitleme gibi bir eylem gerçekleştirin. Bu eylem başarılı olursa cihaz, yeni MDM yetkilisi tarafından yönetiliyor demektir.
- Belirli cihazlarla sorun yaşıyorsanız bu cihazları kaldırıp yeniden kaydederek cihazların yeni yetkiliye bağlanması ve yönetilmeye devam etmesini sağlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

MDM yetkilisi ayarlandıktan sonra [cihazları kaydetmeye](../enrollment/device-enrollment.md) başlayabilirsiniz.
