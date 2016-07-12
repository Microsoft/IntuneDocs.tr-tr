---
title: "Intune'a geçiş | Microsoft Intune"
description: 
keywords: 
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 8c1f4f209c5ec704290882b8f6f71e0b1b01d21c
ms.openlocfilehash: 20394c243b9355cd3f4e30f170dfd00d10e1153f


---

# Intune’a geçiş


Mevcut kurumsal mobil yönetim çözümünüzden Intune’a geçiş, genel olarak aşağıdaki adımları izleyebilir:

![Intune için geçiş adımları](./media/migrate-intune-steps.png)

## Kullanıcılara bildirme

Intune pilot dağıtımının gereksinimlerinizi karşıladığı konusunda içiniz rahat olduğunda, kullanıcılarınızı cihazlarının yakında Intune’a geçirileceği konusunda bilgilendirin. E-posta iletileri, yönergeler ve [posterler](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) beklentileri belirlemeye ve kullanıcıların şirket kaynaklarıyla uygulamalarına kesintisiz bağlantıyı sürdürmek için izlemeleri gereken adımlarla ilgili kayıt ayrıntılarını sağlamaya yardımcı olabilir. Destek ekibinizin geçiş sürecinde kullanıcılara yardım etmeye hazır olmasını sağlayın.

## Mevcut kurumsal mobil yönetim çözümünüzü değiştirme

Mevcut kurumsal mobil yönetim çözümünüzle Intune arasında koşullu erişim ilkelerini nasıl ele almayı planladığınıza bağlı olarak, mevcut koşullu erişim ilkelerinizi devre dışı bırakmanız gerekebilir. Mevcut koşullu erişim ilkelerini devre dışı bırakacak VEYA mevcut koşullu erişim ilkelerinin kapsamını, Intune’a geçirmek üzere olduğunuz kullanıcıları/cihazları içermeyecek şekilde ayarlayacaksınız.  Aynı kullanıcılara/cihazlara hem Intune’un hem de mevcut kurumsal mobil yönetim çözümünüzün koşullu erişim ilkeleri uygulamasına izin vermeyin.

## Intune koşullu erişim ilkesini etkinleştirme (isteğe bağlı)

Geçirilen cihazlar için koşullu erişim ilkelerini hiç bekleme süresi olmadan hemen zorunlu tutmaya karar verdiyseniz, bu adımda Intune’da koşullu erişim ilkelerini etkinleştirin.  Bu kararın kullanıcılarınıza ve yardım masası ekibinize tam olarak iletildiğinden emin olun.  Cihazlar Intune’a kaydolmazsa ve Intune ilkeleriyle uyumlu değilse, kullanıcılar Intune’a kaydolana ve cihazları Intune ilkeleriyle uyumlu hale getirilene kadar şirket kaynaklarına erişemezler.

## Mevcut kurumsal mobil yönetim çözümünüzden cihazların kaydını silme

Cihazlar Intune’a kaydolmadan önce, mevcut kurumsal mobil yönetim çözümünden bu cihazların kaydı silinmelidir. En iyi kullanıcı deneyimi için bizim önerimiz, kullanıcılara kendi cihazlarının kaydını kendileri silmeleri için izin vermektir.  Kullanıcıları ve cihazları platformunuzdan doğru şekilde kaldırdığınızdan emin olmak için çözüm sağlayıcısının kayıt silme yönergelerini izlemeye dikkat edin. Bu şekilde son kullanıcılarınıza mümkün olan en az kesintiyi yaşatırsınız.

## Cihazları Intune'a kaydetme

Geçiş için zamanlanmış kullanıcılar, şirket kaynaklarına, e-postasına ve uygulamalarına yeniden erişim kazanmak veya erişimi kaybetmemek için Intune’a hemen kaydolmalıdır. Koşullu erişim yapılandırdıysanız ve kullanıcıları Intune’a kaydolmadan e-postaya bağlanmayı denerse, erişimleri engellenir ve kayıt e-postasıyla karşılanırlar. Bu e-posta, cihazlarını Intune’a kaydetmeleri için onlara yol gösterecektir.  Alternatif olarak, kullanıcılar Intune Şirke Portalı uygulaması yoluyla veya Windows 8.1 ve Windows 10 Mobile’da işletim sistemi aracılığıyla Intune’da kaydolabilirler. Her platform için kayıt adımlarıyla ilgili diğer yönergeleri, [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md) başlığı altında bulabilirsiniz.

## Intune koşullu erişimini yapılandırma (isteğe bağlı)

Koşullu erişimi zorunlu tutmak için bir bekleme süresi bıraktıysanız, son kullanıcılarınıza bildirdiğiniz bekleme süresi sona erdiğinde ilkenin zorunlu tutulmaya başlamasını sağlamak için Intune’da koşullu erişim ilkelerini etkinleştirin. Bu hemen, tüm cihazların Intune koşullu erişim ilkesinin gereksinimlerini karşılamasını zorunlu tutacaktır.

## Kalan cihazları ve kullanıcıları kaydetme

Artık koşullu erişimi etkinleştirdiğinize göre, şirket kaynaklarına erişim kazanmak için tüm kullanıcıların Intune’a kaydolması ve kuruluşunuzun uyumluluk ilkelerine uyması gerekir. Kullanıcılarınızı, hepsini bir kedere geçirmek yerine aşamalı kayıt yöntemiyle geçirdiyseniz, cihazların ve kullanıcıların tümü Intune’a kaydolana ve Intune tarafından yönetilene kadar yukarıdaki adımları yineleyin.

## Önceki kurumsal mobil yönetim çözümünü devre dışı bırakma

Kullanıcılarınızın ve cihazlarınızın tümünü Intune’a geçirdikten ve Intune’a geçişlerin başarılı olduğunu doğruladıktan sonra, önceki kurumsal mobil yönetim çözümünüzü devre dışı bırakabilir ve/veya hizmet aboneliğinizi iptal edebilirsiniz. İhtiyacınız olmayan tüm altyapı gereksinimlerini doğru bir şekilde kaldırdığınızdan ve tüm abonelikleri/lisansları iptal ettiğinizden emin olmak için, çözüm sağlayıcısının yönergelerini izlemeye özen gösterin.

## Ek geçiş kaynakları

Intune’a geçişinizle ilgili ek yardım gerekiyor mu? Sorunsuz geçiş yapmanıza yardımcı olmak için uzman yardımı seçenekleri sağlıyoruz:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Microsoft Danışmanlık Hizmetleri](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Intune teknik ve teknik olmayan destek](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Microsoft Intune TechNet forumu](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## Bu kılavuzun indirilebilir bir kopyasını alma

Bu kılavuzun tamamının indirilebilir bir kopyasını almak için [TechNet Galerisi](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387)’ni ziyaret edin.



<!--HONumber=Jun16_HO4-->


