---
title: "Şirkete ait iOS cihazlarını kaydetme | Microsoft Intune"
description: "Apple Cihaz Kayıt Programı’nı (DEP) veya Apple Configurator’ı kullanarak şirkete ait iOS cihazlarını kaydetme"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# Microsoft Intune'a şirketin sahip olduğu iOS cihazları kaydetme
Microsoft Intune, Apple Cihaz Kayıt Programı (DEP) veya bir Mac bilgisayarda çalışan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler.

**Ön koşul:**  [Apple Anında İletilen Bildirim hizmeti sertifikası](set-up-ios-and-mac-management-with-microsoft-intune.md)

Şirket tarafından kaydedilen iOS cihazlarını üç yolla kaydedebilirsiniz:

-   **Apple Configurator** - iOS cihazları, bir Kurumsal Kayıt profilini dışarı aktarıp ardından söz konusu mobil cihazları Apple Configurator çalıştıran bir Mac bilgisayara bağlayarak kaydedilebilir. Apple Configurator iki kayıt biçimini destekler:

    - **Kurulum Yardımcısı Kaydı** – Fabrika cihazı sıfırlar ve cihazın yeni kullanıcısı tarafından kurulum yapılması için hazırlar. Bu yöntem, yöneticinin kaydı önceden yapılandırması için iOS cihazını [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) çalıştıran bir Mac bilgisayara USB üzerinden bağlamasını gerektirir. Cihazlar daha sonra kullanıcılara gönderilir, kullanıcılar, Kurulum Yardımcısı sürecini yürüterek cihazı iş veya okul kimlik bilgileriyle yapılandırır ve kaydolma sürecini tamamlar. [Apple Configurator ve Kurulum Yardımcısı'nı kullanarak iOS cihazlarını kaydetme](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Doğrudan Kayıt** – Cihaz hazırlığı sırasında kullanılmak üzere Apple Configurator ile uyumlu bir dosya oluşturur. Kaydedilen cihaz fabrika ayarlı değildir, ancak hiçbir kullanıcı ilişkisi içermez. Bu yöntem, yöneticinin cihazı kaydetmek üzere iOS cihazını [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) çalıştıran bir Mac bilgisayara USB üzerinden bağlamasını gerektirir. [Apple Configurator Doğrudan Kayıt kullanarak iOS cihazlarını kaydetme](ios-direct-enrollment-in-microsoft-intune.md)

-   **Cihaz Kayıt Programı (DEP)** – Apple’ın Cihaz Kaydı Programı üzerinden satın alınan cihazlara “uzaktan” bir kayıt profili dağıtır. Kullanıcı cihazda Kurulum Yardımcısı’nı çalıştırdığında, cihaz Intune'da kaydedilir.  DEP ile kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz. [Cihaz Kayıt Programı iOS cihazlarını kaydetme](ios-device-enrollment-program-in-microsoft-intune.md)

## DEP veya Apple Configurator ile kaydedilen cihazlarda Şirket Portalı’nı kullanma

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar cihazlarını aldıktan sonra, Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için bir dizi ek adımı tamamlamalıdır.

Kullanıcı benzeşimi olan şirkete ait iOS cihazları nasıl kaydedilir
1. Kullanıcılar cihazlarını açtığında, kendilerinden Kurulum Yardımcısı’nı tamamlamaları istenir. Kurulum sırasında kullanıcılardan kimlik bilgileri istenir. Intune abonelikleriyle ilişkili kimlik bilgilerini (yani UPN olarak bilinen benzersiz kişisel adlarını) kullanmalıdırlar.

2. Kurulum sırasında kullanıcılardan bir Apple Kimliği istenir. Cihazın Şirket Portalı’nı yüklemesine izin vermek için bir Apple Kimliği sağlanmalıdır. Apple Kimliği, ayrıca, kurulum tamamlandıktan sonra iOS ayarları menüsünden de girilebilir.

3. Kurulum tamamlandıktan sonra iOS cihazı Uygulama Mağazası’ndan Şirket Portalı uygulamasını yüklemelidir.

4. Kullanıcı artık cihazı kurarken kullanılan UPN’yi kullanarak Şirket Portalı’nda oturum açabilir.

5. Oturum açtıktan sonra, kullanıcıdan cihazını kaydetmesi istenir. İlk adım cihazlarını tanımlamaktır. Uygulama, daha önce şirket için kaydedilmiş ve son kullanıcının Intune hesabına atanmış iOS cihazlarının bir listesini sunar. Eşleşen aygıtı seçin.

  Bu cihaz, zaten şirket için kaydedilmiş değilse, standart kayıt akışına devam etmek için “yeni cihaz”’ı seçin.

6. Sonraki ekranda, kullanıcı yeni cihazın seri numarasını onaylamalıdır. Kullanıcı, seri numarayı doğrulamak üzere Ayarlar uygulamasını başlatmak için “Seri Numarasını onaylayın” bağlantısına dokunabilir. Kullanıcı daha sonra seri numarasının son 4 karakterini Şirket Portalı uygulamasına girmelidir.

  Bu adım, cihazın Intune’a kaydedilmiş şirket cihazı olduğunu doğrular. Cihazdaki seri numarası eşleşmezse, yanlış cihaz seçilmiş demektir. Önceki ekrana geri gidin ve farklı bir cihaz seçin.

7. Seri numarası doğrulandıktan sonra Şirket Portalı uygulaması kaydı tamamlamak için Şirket Portalı web sitesine yönelir ve ardından kullanıcıdan uygulamaya dönmesini ister.

8. Kayıt tamamlanmıştır. Artık bu cihazı tüm özellikleriyle kullanabilirsiniz.

### Kullanıcı benzeşimi olmayan şirkete ait yönetilen cihazlar hakkında

Kullanıcı benzeşimi yok ile yapılandırılmış cihazlar, Şirket Portalı’nı desteklemez ve uygulamayı yüklememelidir. Şirket Portalı, kurumsal kimlik bilgileri olan ve kişiselleştirilmiş şirket kaynaklarına (ör. e-postaya) erişmesi gereken kullanıcılar için tasarlanmıştır. Kullanıcı benzeşimi yok ile kaydedilmiş cihazların özel oturum açma bilgileri olması düşünülmemiştir. Bilgi noktası, satış noktası (POS) veya paylaşılan yardımcı cihazlar, kullanıcı benzeşimi olmadan kaydedilen cihazların tipik kullanım örnekleridir. Kullanıcı benzeşimi gerekiyorsa, cihazın kaydolma profilinde cihaz kaydedilmeden önce Kullanıcı Benzeşimi’nin seçildiğinden emin olun. Bir cihazda benzeşim durumunu değiştirmek için cihazı kullanımdan kaldırıp tekrar kaydetmeniz gerekir.



### Ayrıca bkz:
[Microsoft Intune’da cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


