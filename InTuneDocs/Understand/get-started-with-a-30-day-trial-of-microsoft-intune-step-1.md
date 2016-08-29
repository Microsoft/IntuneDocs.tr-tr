---
title: "Microsoft Intune’un 30 günlük değerlendirmesi için kaydolun | Microsoft Intune"
description: "Intune’un ücretsiz, 30 günlük değerlendirmesine nasıl kaydolabilirsiniz ve kaydolmadan önce hangi noktaları dikkate almanız gerekir"
keywords: 
author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dad88d43-0054-4be6-9e5d-ada5a957dd6c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51fba2b01d8978bc062c50c4388714609be0fdf0
ms.openlocfilehash: 081d396975473cd605e9619498aef78fb2d0e1dd


---

# Microsoft Intune’un 30 günlük değerlendirmesi için kaydolun

Mobil cihazlarınızı ve bilgisayarlarınızı yönetmek için 30 günlük Microsoft Intune değerlendirmesini hızla ve kolayca ayarlayın. Değerlendirme içinde birkaç basit adımla 100’e kadar kullanıcıyı ve cihazı ekleyebilir, gruplar oluşturabilir, uyumluluk ilkelerini yapılandırabilir, mobil cihazları ve bilgisayarları kaydedebilir ve yönetebilirsiniz. Bu konuda, Intune’un özelliklerini ve becerilerini değerlendirebilmeniz için Intune değerlendirmesini çalışır duruma getirmenin temel adımlarını öğrenecek ve hizmet hakkında genel bir bakış edineceksiniz.

## Kaydolmadan önce dikkat etmeniz gereken noktalar

Intune’a kaydolmadan veya Intune'da oturum açmadan önce, aşağıdakileri göz önünde bulundurmanız gerekir:

-   Kuruluşunuzun zaten bir Microsoft Online Services iş veya okul hesabı olup olmadığı

-   Microsoft ile bir Kurumsal Anlaşma veya eşdeğer toplu lisanslama anlaşmanızın olup olmadığı

-   30 günlük değerlendirme süresi bittikten sonra Intune kiracısını kullanmayı planlayıp planlamadığınız

|Aşağıdakilerden biri doğruysa YENİ bir hesap için kaydolun:|Şu durumda İŞ veya OKUL hesabınızla oturum açın:|
|-----------------------------------------------------------------|------------------------------------------------|
|**Bir iş veya okul hesabınız yok.** Bir iş veya okul hesabı Microsoft ile bir toplu lisanslama sözleşmesi imzaladığınızda veya Office 365'e abone olduğunuzda sağlanır. Kurumunuzun Microsoft ile imzaladığı bir Kurumsal Anlaşma veya eşdeğer toplu lisans sözleşmesi yoksa (veya Office 365 hesabı varsa), Microsoft Online Services üzerinde oturum açmak için kullanabileceğiniz bir Microsoft Online Services hesabınız yoktur.<br /><br />**30 günlük değerlendirmeyi tamamladıktan sonra Intune kiracınızı kaldırırsınız.** Intune ücretsiz değerlendirme aboneliğinizi yalnızca değerlendirme amacıyla kullanıyorsanız ve değerlendirmeyi kullandıktan sonra Intune hizmeti kurulumunu ve cihaz sağlamayı yeniden gerçekleştirmeyi düşünüyorsanız yeni bir hesap için kaydolmanız gerekir. Intune ürününü System Center 2012 Configuration Manager ile kullanmayı planlıyorsanız önerilen seçenek budur.<br /><br />Yeni bir hesap için kaydolursanız, daha sonra bu hesabı yönetmek için var olan bir iş veya okul hesabını kullanmaya geçemezsiniz ya da bu hesabı var olan toplu lisans sözleşmeleri ile birleştiremezsiniz.|**Bir toplu lisans sözleşmesi veya Office 365 aboneliğiniz ile sağlanan iş veya okul hesabınız var ve bu değerlendirme sürümünü Intune ürününü değerlendirmek için kullanıyorsunuz.**<br /><br />Intune hizmetinin kurulumunu mevcut bir hesapta yapıyorsanız, bu adımlara devam etmeden önce [Cihazların nasıl yönetileceğini seçin](/intune/get-started/choose-how-to-manage-devices) sayfasını gözden geçirmenizi öneririz.|

## Intune'a kaydolma veya Intune'da oturum açma

1.  İlk olarak, [Intune Kayıt sayfasını ziyaret etmek için buraya tıklayın](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

2.  **Kaydol** sayfasında, iki seçeneğiniz bulunur:

    -   **Microsoft Online Services iş veya okul hesabınızı kullanarak abone olun**: Zaten bir iş veya okul hesabınız varsa ve her iki hizmete abone olmak için aynı hesabı kullanmak istiyorsanız **Oturum aç** 'a tıklayın. Birden fazla hizmet için aynı hesabı kullandığınızda, bu hizmetler aynı Azure AD altyapısını kullanır ve Azure AD kiracılarıdır. Azure AD, Microsoft bulut hizmetleri için çekirdek dizin ve kimlik yönetimi özelliklerini sağlar.

    -   **Yalnızca Intune'a abone olun**: Henüz bir bulut hizmetine abone olmadıysanız, Intune’a abone olmak için kayıt sayfasındaki formu doldurun.

        > [!NOTE]
        > Bu etki alanı adı varsayılan olarak, aboneliğiniz ve Intune hizmetine eklediğiniz kullanıcı hesapları ile ilişkilidir. Abone olduktan sonra, zaten sahip olduğunuz özel bir etki alanı adını ekleyip kullanabilir veya ücretsiz **onmicrosoft.com** etki alanını kullanmaya devam edebilirsiniz.

Kayıt formunu tamamladıktan ve Microsoft Çevrimiçi Abonelik Sözleşmesi'ni kabul ettikten sonra otomatik olarak kiracı yöneticisi hesabı ile Office 365 yönetim merkezi oturumunuz açılır. Ayrıca kayıt sırasında sağladığınız e-posta adresine hesap bilgilerinizi içeren bir e-posta iletisi gönderilir. Bu e-posta, aboneliğinizin etkin olduğunu doğrular.

### Sonraki adımlar
Tebrikler! *Microsoft Intune değerlendirme* gözden geçirmesinin 1. adımını tamamladınız.

>[!div class="step-by-step"]

>[&larr; **Başlarken**](get-started-with-a-30-day-trial-of-microsoft-intune.md)     [**Kullanıcı ekleme** &rarr;](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md)  



<!--HONumber=Aug16_HO2-->


