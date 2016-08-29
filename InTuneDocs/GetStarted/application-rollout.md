---
title: "Uygulama dağıtımı | Microsoft Intune"
description: "Microsoft Intune’da aşamalı uygulama dağıtımına yönelik öneriler."
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2427768c0ca73d20140462946ba2984b7999d864
ms.openlocfilehash: d72247936a0dec8e2e00d107c0d52c1568a92c03


---

# Uygulama dağıtımı
Bu konu başlığı altında, Microsoft Intune’da uygulamaların aşamalı dağıtımına yönelik belirli öneriler sağlanır. Dağıtım aşamaları hakkında genel bilgi için bkz. [Microsoft Intune dağıtımı için dağıtım aşamaları](rollout-phases-for-microsoft-intune-deployment.md).

### Uygulama dağıtımı aşamaları
Uygulama dağıtımının aşamaları şunlardır:

-   Proje kapsamı

-   Kavram kanıtı

-   Pilot

-   Kurumsal dağıtım

-   İşlemler ve bakım

## Proje kapsamı
Aşağıdakileri göz önünde bulundurun:

-   Uygulamanın etkinleştirmesi beklenen kullanıcı görevi.

-   Uygulamanın kullanıcılarınıza ve onların cihazlarına uygunluğu (kullanılma olasılığı olan tüm işletim sistemleri).

-   Seçtiğiniz uygulamanın yükleyicisinin, [Microsoft Intune’la uygulamaları ekleme](/intune/deploy-use/add-apps) konusunda açıklandığı gibi Intune uygulama dağıtımı tarafından desteklenip desteklenmediğini denetleyin.

-   Uygulama dağıtımı önkoşullarının yüklü olduğundan emin olun. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Uygulama türünün Intune tarafından desteklenip desteklenmediğini saptayın.

-   Uygulamayı karşıya yüklemek için yeterli bulut depolama alanınız olup olmadığını denetleyin. Ek depolama alanı satın alma yönergeleri [Microsoft Intune’la uygulamaları ekleme](/intune/deploy-use/add-apps) konu başlığı altında sağlanmıştır.

> [!NOTE]           
> Sunum sürecinize yardımcı olması için, mobil uygulamalara yönelik bu [planlama şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59).

## Kavram kanıtı
Kavram kanıtı aşamasında, uygulama dağıtımınızı laboratuvar ortamında, tam olarak test amacıyla yapılandırdığınız cihazlar ve kullanıcılarda test edin.

-   Pilot ve üretim dağıtımı sırasında ortaya çıkabilecek sorunları öğrenmek için, bu aşamaya yardım masanızın da katılmasını sağlayın. Sorun giderme bilgilerini, [Microsoft Intune’da uygulama dağıtım sorunlarını giderme](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune) konusunda bulabilirsiniz.

-   İşlemin bu noktasında, pilot ve üretim aşaması kullanıcıları için iletişim planları geliştirmelisiniz. Plan en azından hangi uygulamanın dağıtıldığını, kullanıcıların bunu nasıl ve ne zaman alacağını, dağıtımın iş açısından amacını ve sorunlarla karşılaşmaları durumunda ne yapacaklarını (hem kendi kendine yardım bilgileri, hem de yardım masasına başvurma bilgileri) içermelidir.

## Pilot
Pilot aşamasında, uygulamayı test kullanıcıları ve cihazlarından oluşan küçük bir gruba dağıtırsınız. Aşağıdakileri göz önünde bulundurun:

-   Test grubunun, üretim dağıtımı sonrasında uygulamayı kullanacak olan kullanıcıları ve cihazları temsil eder nitelikte olduğundan emin olun.

-   Uygulama dağıtımıyla ilgili olarak yardım masasını eğitin ve test grubundaki kullanıcılara yardım etmeye hazır olduklarından emin olun.

-   Uygulamayı tipik kullanımına göre kullanacak ve sorunları pilot yöneticilerine güvenilir bir şekilde raporlayacak test kullanıcıları seçin.

-   Pilot kullanıcısı iletişim planınızı etkinleştirin.

## Kurumsal dağıtım

-   Pilot sonuçlarını kullanarak kurumsal dağıtımınızda ayarlamalar yapın.

-   Uygulama dağıtımı zamanlamasını yardım masanıza bildirin. Yardım isteklerini yanıtlamak ve dağıtımda gerekli ayarlamaları yapmak için mekanizmaları oluşturun.

-   Dağıtımda sorunlar çıkması durumunda sorun gidermeye hazır olun.

-   Üretim kullanıcısı iletişim planınızı etkinleştirin.

-   Uygulamaların dağıtımında aşamalı bir yaklaşım kullanın ve dağıtımın sorunsuz ilerlediğinden emin olmak için grupları artımlı olarak ekleyin.

## İşlemler ve bakım
**İşlemler:** Intune konsolunuzda uyarıları ve kullanıcı veya cihaz sorunlarını izleyin, uygulama dağıtımının tasarımınıza uygun çalışıp çalışmadığını denetleyin.

**Yardım masası:** Yardım masanızın, uygulama kullanılabilirliğinde ortaya çıkabilecek ve destek isteklerine neden olabilecek tüm değişikliklerin farkında olmasını sağlayın.

### Ayrıca bkz.
[Uygulama dağıtma](/intune/deploy-use/deploy-apps)

[Microsoft Intune’da uygulama dağıtım sorunlarını giderme](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Jul16_HO3-->


