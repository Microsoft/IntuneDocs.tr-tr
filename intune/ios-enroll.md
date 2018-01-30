---
title: "Intune’da Windows cihazları nasıl yükleyeceğinizi seçme"
titlesuffix: Azure portal
description: "Microsoft Intune’da Windows cihazların kaydını nasıl ayarlayacağınızı öğrenin.”"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f36e579282f7aeaec74c3e80d866e52dfa508d3d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-ios-devices-in-intune"></a>Intune’da iOS cihazları kaydetme

Intune, kullanıcılara şirket e-postası ve uygulamalarına erişim vermek amacıyla iPad ve iPhone’lar için mobil cihaz yönetimi (MDM) sağlar.

Bir Intune yöneticisi olarak, iOS cihazları için kaydı etkinleştirebilirsiniz. Kullanıcıların kişisel cihazlarını kaydetmelerine izin verebilirsiniz, bu işlem “kendi cihazını getir” (KCG) kaydı olarak bilinir. Şirkete ait cihazların kaydını da etkinleştirebilirsiniz.

## <a name="prerequisites-for-ios-enrollment"></a>iOS kaydı için önkoşullar
iOS cihazları etkinleştirmeden önce aşağıdaki adımları tamamlayın:
- [Intune’u ayarlama](setup-steps.md) - Bu adımlar, Intune altyapınızı ayarlar. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir.
- [Bir Apple MDM Anında İletme sertifikası alma](apple-mdm-push-certificate-get.md) - Apple, iOS ve macOS cihazların yönetimini etkinleştirmek için bir sertifika gerektirir.

## <a name="user-owned-ios-devices-byod"></a>Kullanıcıya ait iOS cihazları (KCG)

Kullanıcıların kendi cihazlarını Intune yönetimine kaydetmesine izin verebilirsiniz. Bu, “kendi cihazını getir” veya KCG olarak bilinir. Siz önkoşulları tamamlayıp kullanıcılara lisans atadıktan sonra kullanıcılar, App Store’dan iOS Şirket Portalı’nı indirip uygulamadaki kayıt yönergelerini izleyebilir.

## <a name="company-owned-ios-devices"></a>Şirkete ait iOS cihazlar
Kullanıcılarına cihaz sağlayan kuruluşlar için Intune, aşağıdaki iOS şirkete ait cihaz kayıt yöntemlerini destekler:

- Apple’ın Aygıt Kayıt Programı (DEP)
- Apple School Manager
- Apple Configurator Kurulum Yardımcısı kaydı
- Apple Configurator ile doğrudan kayıt

Şirkete ait iOS cihazları bir [cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabıyla da kaydedebilirsiniz.

## <a name="device-enrollment-program"></a>Cihaz Kaydı Programı
Kuruluşlar, Apple’ın Aygıt Kayıt Programı (DEP) aracılığıyla iOS cihazlar satın alabilir. DEP, cihazları yönetime kaydetmek için bir kayıt profilini “uzaktan” dağıtmanıza imkan tanır. [Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager, okullar için oluşturulmuş bir cihaz satın alma ve kayıt programıdır. DEP’te olduğu gibi cihazları yönetime kaydetmek için bir profil dağıtabilirsiniz. [Apple School Manager](apple-school-manager-set-up-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-configurator"></a>Apple Configurator
Bir Mac bilgisayarda çalışan Apple Configurator ile iOS cihazları kaydedebilirsiniz. Cihazları hazırlamak için USB ile bağlayıp onlara bir kayıt profili yüklersiniz. Cihazları Apple Configurator ile iki şekilde kaydedebilirsiniz:
- Kurulum Yardımcısı kaydı - Cihazı fabrika ayarlarına sıfırlar, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler.
- Doğrudan kayıt - Cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, kullanıcı benzeşimi olmayan cihazlar içindir.

[Apple Configurator kaydı](apple-configurator-setup-assistant-enroll-ios.md) hakkında daha fazla bilgi edinin.

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

