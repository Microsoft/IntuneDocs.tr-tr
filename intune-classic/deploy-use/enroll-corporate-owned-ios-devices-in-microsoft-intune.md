---
title: Şirketin sahip olduğu iOS cihazlarını kaydetme
description: Şirkete ait iOS cihazlarını Apple Aygıt Kayıt Programı’nı (DEP) veya Apple Configurator’ı kullanarak kaydetme
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93ff84d263c2fe8825d2cf5a86249bbf19cb9173
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-corporate-owned-ios-devices-in-microsoft-intune"></a>Microsoft Intune'a şirketin sahip olduğu iOS cihazları kaydetme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, şirkete ait iOS cihazlarının Apple Aygıt Kayıt Programı (DEP) veya bir Mac bilgisayarında çalışan [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) aracı ile kaydedilmesini destekler.

**Önkoşul:** [Apple Anında İletilen Bildirim hizmeti sertifikası](set-up-ios-and-mac-management-with-microsoft-intune.md)

Şirket tarafından kaydedilen iOS cihazlarınızı şu üç yöntemden birini kullanarak kaydedebilirsiniz:

- Kurulum Yardımcısı veya doğrudan kayıt ile Apple Configurator
- Cihaz kaydı programı
- Şirket Portalı uygulaması

>[!NOTE]
>Apple Configurator ve Cihaz Kaydı Programı kayıt yöntemleri, [cihaz kayıt yöneticisi](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) yöntemiyle birlikte kullanılamaz.

Varsayılan olarak tüm iOS cihazları Intune'a kaydedilebilir. Kişisel veya kurumsal cihazların kaydedilmesini engellemek için yönetici kimlik bilgilerinizle [Microsoft Intune yönetim portalında](https://manage.microsoft.com) oturum açın. **Yönetim** > **Mobil Cihaz Yönetimi** > **Kayıt Kuralları**'nı seçin ve ilgili özelliklerin seçimini kaldırın.

## <a name="use-apple-configurator"></a>Apple Configurator’ı kullanma

iOS cihazlarını bir Kurumsal Kayıt profilini dışarı aktarıp ardından söz konusu mobil cihazları Apple Configurator çalıştıran bir Mac bilgisayara bağlayarak kaydedebilirsiniz. Apple Configurator iki kayıt biçimini destekler:

- **Kurulum Yardımcısı kaydı**: Cihazı fabrika ayarlarına sıfırlar ve yeni kullanıcı tarafından kurulum yapılmaya hazırlar. Bu yöntem, yöneticinin, kaydı önceden yapılandırmak için iOS cihazını USB üzerinden [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) çalıştıran bir Mac bilgisayara bağlamasını gerektirir. Cihazlar daha sonra kullanıcılara dağıtılır, kullanıcılar da Kurulum Yardımcısı işlemini çalıştırır. Bu işlem cihazı kullanıcının iş veya okul kimlik bilgileriyle yapılandırır ve kaydolma işlemini tamamlar. Daha fazla bilgi için bkz. [Apple Configurator’ı ve Kurulum Yardımcısı’nı kullanarak iOS cihazları kaydetme](ios-setup-assistant-enrollment-in-microsoft-intune.md).

- **Doğrudan kayıt**: Cihaz hazırlama sırasında kullanılmak üzere Apple Configurator ile uyumlu bir dosya oluşturur. Kaydedilen cihaz fabrika ayarlarına sıfırlanmaz, ancak hiçbir kullanıcıyla ilişkili değildir. Bu yöntem, yöneticinin, iOS cihazını kaydetmek üzere USB üzerinden [Apple Configurator](https://go.microsoft.com/fwlink/?LinkId=518017) çalıştıran bir Mac bilgisayara bağlamasını gerektirir. Daha fazla bilgi için bkz. [Apple Configurator Doğrudan Kurulum kullanarak iOS cihazlarını kaydetme](ios-direct-enrollment-in-microsoft-intune.md).

## <a name="use-the-device-enrollment-program-dep"></a>Aygıt Kayıt Programı’nı (DEP) kullanma
Bu seçenek, DEP aracılığıyla satın alınan cihazlara bir “havadan” kaydolma profili dağıtır. Kullanıcı, cihazda Kurulum Yardımcısı’nı çalıştırdığında, cihaz Intune'a kaydedilir. Daha fazla bilgi için, bkz. [Aygıt Kayıt Programı iOS cihazlarını kaydetme](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>DEP veya Apple Configurator ile kaydedilmiş cihazlarda Şirket Portalı’nı kullanma

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için bir dizi ek adımı tamamlamalıdır.

Aşağıdakileri desteklemek için kullanıcı benzeşimi gereklidir:
  - Mobil uygulama yönetimi (MAM) uygulamaları
  - E-postaya ve şirket verilerine koşullu erişim
  - Şirket Portalı uygulaması

**Kullanıcıların kullanıcı benzeşimi olan şirkete ait iOS cihazları kaydetmesi**
1. Kullanıcılar cihazlarını açtığında, kendilerinden Kurulum Yardımcısı’nı tamamlamaları istenir. Kurulum sırasında kullanıcılardan kimlik bilgileri istenir. Intune abonelikleriyle ilişkili kimlik bilgilerini (yani UPN olarak bilinen benzersiz kişisel adları) kullanmalıdırlar.

2. Kurulum sırasında kullanıcılardan bir Apple Kimliği istenir. Cihazın Şirket Portalı’nı yüklemesine izin vermek için bir Apple ID sağlanmalıdır. Kimlik, kurulum bittikten sonra iOS ayarları menüsünden de sağlanabilir.

3. Kurulum tamamlandıktan sonra iOS cihazı Uygulama Mağazası’ndan Şirket Portalı uygulamasını yüklemelidir.

4. Kullanıcı artık cihazı kurarken kullandığı UPN’yi kullanarak Şirket Portalı’nda oturum açabilir.

5. Oturum açtıktan sonra, kullanıcıdan cihazını kaydetmesi istenir. İlk adım cihazını tanımlamaktır. Uygulama, daha önce şirket için kaydedilmiş ve kullanıcının Intune hesabına atanmış iOS cihazlarının bir listesini sunar. Kullanıcı eşleşen cihazı seçmelidir.

   Bu cihaz daha önce şirkete kaydedilmemişse, kullanıcı, standart kayıt akışına devam etmek için **yeni cihazı** seçmelidir.

6. Kullanıcı, sonraki ekranda yeni cihazın seri numarasını onaylamalıdır. Kullanıcı, seri numarasını doğrulamak üzere Ayarlar uygulamasını kullanma yönergelerini başlatan **Seri Numarasını onaylayın** bağlantısına dokunabilir. Daha sonra kullanıcı, seri numarasının son dört karakterini Şirket Portalı uygulamasına girmelidir.

   Bu adım, cihazın Intune’a kaydedilmiş şirket cihazı olduğunu doğrular. Cihazdaki seri numarası eşleşmezse, yanlış cihaz seçilmiş demektir. Kullanıcı önceki ekrana geri dönmeli ve farklı bir cihaz seçmelidir.

7. Seri numarası doğrulandıktan sonra Şirket Portalı uygulaması, kaydı tamamlamak üzere Şirket Portalı web sitesine yönlendirir. Web sitesi daha sonra kullanıcıdan uygulamaya dönmesini ister.

8. Kayıt tamamlanmıştır. Kullanıcı artık bu cihazı tüm özellikleriyle kullanabilir.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Kullanıcı benzeşimi olmayan şirkete ait yönetilen cihazlar hakkında

Hiçbir kullanıcı benzeşimi olmadan yapılandırılmış cihazlar, Şirket Portalı’nı desteklemez ve uygulamayı yüklememelidir. Şirket Portalı, kurumsal kimlik bilgileri olan ve kişiselleştirilmiş şirket kaynaklarına (ör. e-postaya) erişmesi gereken kullanıcılar için tasarlanmıştır. Hiçbir kullanıcı benzeşimi olmadan kaydedilmiş cihazların özel oturumu olması düşünülmemiştir. Bilgi noktası, satış noktası (POS) veya paylaşılan yardımcı cihazlar, kullanıcı benzeşimi olmadan kaydedilen cihazların tipik kullanım örnekleridir.

Kullanıcı benzeşimi gerekiyorsa, cihazın kaydolma profilinde cihaz kaydedilmeden önce **Kullanıcı Benzeşimi**’nin seçildiğinden emin olun. Bir cihazdaki benzeşim durumunu değiştirmek için cihazı kullanımdan kaldırıp tekrar kaydetmeniz gerekir.



### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)
