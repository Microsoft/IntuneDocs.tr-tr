---
title: "Intune hızlı başlangıç kılavuzu | Microsoft Intune"
description: "Intune aboneliğinizi kullanmaya başlamak için gereksinimler ve önkoşullar"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: 2e385a6f1721c7b8acbc1e280b8d8c3277fa00f8


---


# Intune hızlı başlangıç kılavuzu
Bu hızlı başlangıç kılavuzu, kuruluşunuzda kullanılan mobil cihazlar ve Windows bilgisayarları hızla ve kolayca yönetmek için ücretli bir Microsoft Intune aboneliğini ayarlama adımlarında size yol gösterir. Adımları sırayla izleyebilir veya adımlardan biri sizin kendi ortamınıza veya iş gereksinimlerinize uymuyorsa ileri atlayabilirsiniz.

>[!NOTE]
>Bu makale, Intune’u tek başına bir hizmet olarak ayarlamaya odaklanır. Alternatif olarak, şu anda bilgisayarlar ve sunucuları yönetmek için Microsoft System Center Configuration Manager’ı kullanıyorsanız, [Configuration Manager’ın kapsamını mobil cihazları da yönetecek şekilde genişletebilirsiniz](https://technet.microsoft.com/library/jj884158.aspx). Bunu, karma bir mobil cihaz yönetimi (MDM) dağıtımında Intune’a Configuration Manager ile bağlanarak yapabilirsiniz.

Bu hızlı başlangıç kılavuzu, [Intune değerlendirme kılavuzu](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) içinde yer alan birçok adımla aynıdır. Öte yandan, değerlendirmenizi bitirdiğinizde mobil cihazlarınızı yönetmeye başlamak için hazır olduğunuzda, bazı ek gereksinimleri de karşılamanız gerekir:

-   Şirket içi Active Directory hesaplarını Intune ve Azure Active Directory ile eşitleyin.

-   Etki alanı kayıt şirketinizle ortak etki alanını ve DNS hizmet kayıtlarını güncelleştirin.

-   Intune özelliklerini üretim kullanımı için özelleştirin.

>[!TIP]
>Uygun bir planda Microsoft Intune için en az 150 lisans satın aldığınızda *FastTrack Center Avantajı*’ndan yararlanabilirsiniz. Bu hizmet, ortamınızı Intune için hazırlamak üzere Microsoft uzmanlarıyla birlikte çalışmanıza olanak tanır. Bkz. [Microsoft Intune Hizmet Avantajı Açıklaması](https://technet.microsoft.com/library/mt228265.aspx).


## Başlamadan önce
Ücretli bir abonelik kullanmaya başladığınızda ve Intune’u dağıtmaya, mevcut ağ altyapınızda değişiklikler yapmaya hazır olduğunuzda bu kılavuzu kullanın. Bu görevler yalnızca iç ve dış DNS kayıtlarınızı eklemek veya güncelleştirmekten, mevcut Active Directory kullanıcı hesaplarınızı Azure Active Directory’yle eşitlemeye kadar değişiklik gösterebilir. Intune mobil cihaz yönetimi özelliklerinin hangi birleşimine karar verirseniz verin, Intune’un mevcut ağ bileşenleriniz ve hizmetlerinizle nasıl etkileşime gireceğini dikkatle planlamanız gerekir. Özellikle şunları gözden geçirmelisiniz:

-   **Kullanıcı kimliklerini nasıl yöneteceksiniz**: Orta büyüklükte ve büyük kuruluşların çoğu için kullanıcı kimliklerini Intune aracılığıyla yönetmenin en iyi ve en kolay yolu, mevcut dizin hizmetlerini Azure Active Directory aracılığıyla Intune’a bağlamaktır. Bu, Office 365 veya Exchange Online gibi diğer Microsoft bulut hizmetlerini zaten kullanıyorsanız özellikle geçerlidir. [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) kullanarak mevcut kullanıcı hesaplarınızı eşitlemek, şirket içi Active Directory’nizi Azure Active Directory’ye bağlamanın ve kullanıcılarınız için bir çoklu oturum açma kimlik doğrulaması deneyimi yapılandırmanın hızlı ve kolay bir yoludur.

-   **DNS nasıl etkilenecek**: Intune’a ilk kaydolduğunuzda aldığınız varsayılan onmicrosoft.com etki alanı yerine kendi etki alanı adınızı kullanmak istiyorsanız, bazı ortak DNS kaydı güncelleştirmeleri yapmanız gerekir. DNS kaydı güncelleştirmelerinin gerekli olmasının nedeni, mobil cihazların Intune hizmetini bulabilmesini ve aboneliğinizde yönetim hizmetinin kuruluşunuzda kullanılan tüm cihazları doğru bir şekilde yönetebilmesini sağlamaktır.

## Aşağıdaki öğeler elinizin altında olsun
Başlamaya hazır mısınız? Ücretli Intune aboneliğinizi kullanmaya başlarken aşağıdakiler öğeler gerekir:

### Silverlight etkin web tarayıcısı olan bir cihaz
Cihazları, uygulamaları ve ilkeleri yöneteceğiniz Intune yönetim konsoluna erişmek için bu gereklidir. Ayrıca, Şirket Portalı uygulamasına mobil cihazdan erişmediğinizde, web tabanlı Intune Şirket Portalı’na erişmek için de bir web tarayıcısı gerekir. İşleri kolaylaştırmak için, Intune yönetiminde kullandığınız tarayıcının “gizlilik modu” ayarını kullanabilirsiniz (örneğin: Internet Explorer’da **Araçlar** &gt; **InPrivate Gözatma**’ya tıklayabilirsiniz).

>[!TIP]
>Bu gereksinimden dolayı, Intune yönetim konsoluna erişmek için Microsoft Edge tarayıcısının kullanılması desteklenmez.


### Mobil cihazların sertifikaları
Intune ile iOS veya Windows Phone cihazlarını yönetiyorsanız, sertifikalar ve bu sertifikaları almak için hesaplar gerekir. Android cihazlarını yönetmek için ek sertifikaya ihtiyacınız yoktur.

- Şirket Portalı uygulamasını Mağaza’dan yükleyen **Windows Phone 8.1** kullanıcılarına sertifika gerekmez. Öte yandan, **Windows Phone 8.0** için veya Intune kullanarak Şirket Portalı uygulamasını Windows Phone 8.1 cihazlarına dağıtmak için [Symantec kod imzalama sertifikası](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) gerekir.

>[!NOTE]
>Bu hızlı başlangıç kılavuzunda, kullanıcılarınızın Şirket Portalı uygulamasını Windows Phone 8.1 veya üzeri bir cihazda Mağaza’dan aldığı varsayılır. Windows Phone 8.0 desteği hakkında daha fazla bilgi için, bkz. [Microsoft Intune ile Windows Phone 8.0 yönetimini ayarlama](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Windows bilgisayarlarını cihaz olarak kaydederken veya [Microsoft Intune için Windows bilgisayar istemcisini yüklerken](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune), **Windows bilgisayarları** veya **Windows RT cihazları** için sertifika gereksinimi yoktur.

- **iOS** veya **Mac OS X** cihazlarında, [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) yordamının 3. adımında açıklandığı gibi Apple'dan bir Apple Anında İletilen Bildirim Servisi sertifikası isteyin.

## Sonraki adımlar
Intune hızlı başlangıç kılavuzuyla çalışmaya başlamanın tam zamanı!

>[!div class="step-by-step"]
[**Intune'da oturum açma** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Oct16_HO4-->


