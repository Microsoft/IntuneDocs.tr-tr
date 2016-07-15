---
title: "İlke dağıtımı | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d82d0ae4820d2e2141848235b8741abccaec3bc6
ms.openlocfilehash: 8935fbc42d7b406a5bcdbfc4353209b4447ae413


---

# İlke dağıtımı
Bu konu başlığı altında, Microsoft Intune’da ilkelerin aşamalı dağıtımına yönelik belirli öneriler sağlanır. Bu yaklaşım, yeni Intune dağıtımına uyguladığınız ilk ilkeler veya mevcut dağıtıma eklediğiniz ilkeler için geçerlidir.

Dağıtım aşamaları hakkında genel bilgi için bkz. [Microsoft Intune dağıtımı için dağıtım aşamaları](rollout-phases-for-microsoft-intune-deployment.md).

### İlke dağıtımının aşamaları
İlke dağıtımının aşamaları şunlardır:

-   Proje kapsamı

-   Kavram kanıtı

-   Pilot

-   Kurumsal dağıtım

-   İşlemler ve bakım

## Proje kapsamı
Intune ilkesi dağıtımınızın kapsamını tanımlayın:

-   Yeni bir uygulamada, bu aşama ilke kümenizle oluşturmak istediğiniz tüm cihaz davranışlarının ve güvenlik gereksinimlerinin tanımlanmasını gerektirir.

-   Bu ilkelerden hangi kullanıcıların ve cihazların etkilenmesini istediğinize karar verir.

-   Yeni ilkeleri düzgün uygulayabilmenizi sağlamak için kullanıcı ve cihaz gruplarınızı tasarlayın.

-   Her işletim sistemiyle ilişkili olarak, ilkenizin amacını etkileyebilecek sınırlandırmalar veya gereksinimler olup olmadığını saptayın.

-   Kullanılacak ilke türü ve şablon gibi ilke tasarımı özelliklerini göz önüne alın.

-   Hem ilk ilke kümenizi başlatırken hem de mevcut ilke kümesine yeni ilkeler eklerken, çeşitli ilkeler arasındaki etkileşimi ve cihaz davranışının nasıl olabileceğini göz önüne alın. İlke etkileşimleri ve çakışmalarıyla ilgili sorunlar Pilot aşamasında keşfedilebilir; ancak ilke çakışmalarının planlamanın erken bir aşamasında yakalanması, Pilot aşamasının yürütülmesini basitleştirecektir.

## Kavram kanıtı
Kavram kanıtı aşamasında, ilke dağıtımınızı laboratuvar ortamında, tam olarak test amacıyla yapılandırdığınız cihazlar ve kullanıcılarda test edin.

-   Pilot ve üretim dağıtımı sırasında ortaya çıkabilecek sorunları öğrenmek için, bu aşamaya yardım masanızın da katılmasını sağlayın. Sorun giderme bilgilerini, [Microsoft Intune’da ilke sorunlarını giderme](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune) konusunda bulabilirsiniz.

-   İşlemin bu noktasında, pilot ve üretim aşaması kullanıcıları için iletişim planları geliştirmelisiniz. Plan en azından hangi cihaz davranışlarının ve ne zaman değişeceğini, işletme açısından değişikliğin amacını ve kullanıcıların veya BT personelinin sorunlarla karşılaşması durumunda ne yapacaklarını (hem kendi kendine yardım bilgileri, hem de yardım masasına başvurma bilgileri) içermelidir.

## Pilot
Pilot aşamasında, ilkeyi test kullanıcıları ve cihazlarından oluşan küçük bir gruba dağıtırsınız. Intune’da pilot ilke uygulaması için dikkate alınacak belirli noktalar vardır:

-   Test grubunun, ilkenin üretim dağıtımında uygulanacağı grubu temsil eder nitelikte olması gerekir.

-   İlkedeki değişikliklerle ilgili olarak yardım masasını eğitin ve test grubundaki kullanıcılara yardım etmeye hazır olduklarından emin olun.

-   Pilot kullanıcısı iletişim planınızı etkinleştirin.

-   Pilot uygulaması başlangıçta, cihazın çakışmalara ve beklenmedik davranışlara neden olabilecek başka ilkelere maruz kalmadığı, yalıtılmış bir modda yapılabilir.

-   Son testte, yeni ilke ve aynı cihaza uygulanacak tüm mevcut ilkelere dikkate alınmalıdır.

## Kurumsal dağıtım

-   Pilot aşamasının sonuçlarına göre, planlanan ilkenizi ilke çakışmalarını ve istenmeyen davranışları düzeltmek için ayarlayın.

-   Kurumsal dağıtım zamanlamasını yardım masanıza bildirin. Yardım isteklerini yanıtlamak ve dağıtımda gerekli ayarlamaları yapmak için mekanizmaları oluşturun.

-   İlkede sorunlar çıkması durumunda sorun gidermeye hazır olun.

-   Üretim kullanıcısı iletişim planınızı etkinleştirin.

-   İlkeleri diğer gruplara artımlı olarak uygulayın. Bu arada etkilenen cihazlar için ilkenin durumunu izleyin ve yeni ilkeyle ilgili olabilecek yardım masası isteklerini izleyin.

## İşlemler ve bakım
**İşlemler:** Intune konsolunuzda uyarıları ve kullanıcı veya cihaz sorunlarını izleyin, ilkelerin tasarımınıza uygun çalışıp çalışmadığını denetleyin.

**Yardım masası:** Yardım masanızın, ilkelerde yapılan ve kullanıcı deneyimini etkileyebilecek değişikliklerin farkında olduğundan emin olun çünkü bunlar destek isteklerine neden olabilir.


### Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkelerini yapılandırmak için hazırlama](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Microsoft Intune’da ilke sorunlarını giderme](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)



<!--HONumber=Jun16_HO4-->


