---
title: "Intune’da iOS cihazlarını kaydetme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Microsoft Intune’da iOS cihazlarının kaydının nasıl ayarlandığını öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c228601451b33238d0f6929987dcdec3a5e56e8d


---

# <a name="choose-how-to-enroll-ios-devices"></a>iOS cihazlarının nasıl kaydedileceğini belirleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bu konu başlığı altında, iOS cihazlarını kaydetmek için kullanabileceğiniz yöntemler ve kaydın önkoşulları açıklanır.

iOS cihazlarını hangi yöntemle kaydedeceğinize karar verirken aşağıdaki bilgilerden yararlanın. KCG dışında aşağıdaki yöntemlerin tümü, şirkete ait cihazların kaydına yöneliktir.

**Ön koşul:** [Apple Anında İletilen Bildirim hizmeti sertifikası](get-an-apple-mdm-push-certificate.md) gerekir.

## <a name="user-owned-ios-devices-byod"></a>Kullanıcıya ait iOS cihazları (KCG)

Kullanıcılar kendi kişisel, KCG (kendi cihazını getir) cihazlarını kaydetmek istediklerinde, kullanıcılara sağlanan tek kayıt yöntemi Uygulama Mağazası’ndan iOS için Şirket Portalı uygulamasını indirmek ve uygulamadaki kayıt yönergelerini izlemektir. Kaydedildikten sonra, kullanıcılar şirket ağına bağlanabilir, etki alanına veya Azure Active Directory’ye katılabilir ve şirket kaynaklarına erişim sağlayabilir.

## <a name="apple-configurator"></a>Apple Configurator

iOS cihazlarını bir Kurumsal Kayıt profilini dışarı aktarıp ardından söz konusu mobil cihazları [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) çalıştıran bir Mac bilgisayara bağlayarak kaydedebilirsiniz. Apple Configurator iki kayıt biçimini destekler:

- **Kurulum Yardımcısı kaydı**: Cihazı fabrika ayarlarına sıfırlar ve yeni kullanıcı tarafından kurulum yapılmaya hazırlar. Bu yöntem yöneticinin, kaydı önceden yapılandırmak için iOS cihazını USB üzerinden Apple Configurator çalıştıran bir Mac bilgisayara bağlamasını gerektirir. Cihazlar daha sonra kullanıcılara dağıtılır, kullanıcılar da Kurulum Yardımcısı işlemini çalıştırır. Bu işlem cihazı kullanıcıların iş veya okul kimlik bilgileriyle yapılandırır ve kayıt işlemini tamamlar. Daha fazla bilgi için bkz. [Apple Configurator ve Kurulum Yardımcısı ile iOS cihazları kaydetme](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md).

- **Doğrudan kayıt**: Cihaz hazırlama sırasında kullanılmak üzere Apple Configurator ile uyumlu bir dosya oluşturur. Kaydedilen cihaz fabrika ayarlarına sıfırlanmaz ve hiçbir kullanıcıyla ilişkili değildir. Cihazları kaydetmek için, yöneticinin iOS cihazını USB üzerinden Apple Configurator çalıştıran Mac bilgisayarına bağlaması gerekir. Daha fazla bilgi için bkz. [Apple Configurator Doğrudan Kurulum kullanarak iOS cihazlarını kaydetme](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md).

## <a name="use-the-device-enrollment-program-dep"></a>Aygıt Kayıt Programı’nı (DEP) kullanma

Bu seçenek, DEP aracılığıyla satın alınan cihazlara bir “havadan” kaydolma profili dağıtır. Kullanıcı, cihazda Kurulum Yardımcısı’nı çalıştırdığında, cihaz Intune'a kaydedilir. DEP üzerinden kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz. Daha fazla bilgi için, bkz. [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](enroll-ios-devices-using-device-enrollment-program.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Cihaz kayıt yöneticisini (DEM) kullanma
Cihaz kayıt yöneticisi, en çok 1.000 cihazı kaydedebilen ve yönetebilen bir kullanıcı hesabı türüdür. Mevcut kullanıcıları DEM hesabına ekleyerek, onlara bu yetenekleri sağlarsınız. DEM kullanıcısının kaydettiği her cihaz tek bir Intune lisansı kullanır. Daha fazla bilgi için bkz. [Cihaz kayıt yöneticisini kullanarak cihazları kaydetme](enroll-devices-using-device-enrollment-manager.md).



<!--HONumber=Feb17_HO1-->

