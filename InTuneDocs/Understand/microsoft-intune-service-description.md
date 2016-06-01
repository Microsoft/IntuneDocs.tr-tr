---
# required metadata

title: Hizmet Açıklaması | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune hizmet açıklaması

Microsoft Intune, Windows bilgisayarlarla iOS, Mac OS X, Android ve Windows mobil cihazları yönetmenize yardımcı olan bulut tabanlı bir hizmettir. Intune, şirket uygulamalarının ve verilerinin korunmasına da yardımcı olur. Intune’un tek başına kullanabilir veya System Center 2012 R2 Configuration Manager ile birleştirerek yönetim özelliklerinizi genişletebilirsiniz.

Microsoft, uygun planlarda uygun hizmetler için Intune Onboarding avantajını sunar. Onboarding avantajı, ortamınızı kullanıma hazır hale getirmek için Microsoft uzmanlarıyla uzaktan çalışmanıza olanak sağlar. Daha fazla bilgi için bkz. [Microsoft Intune Onboarding Avantajı Açıklaması](http://go.microsoft.com/fwlink/?LinkId=619281).

Intune’u 100 kullanıcı lisansı içeren 30 günlük ücretsiz bir denemeyle kullanmaya başlayabilirsiniz. Ücretsiz denemeyi başlatmak için [buraya tıklayarak Intune Kayıt sayfasını ziyaret edin](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/). Kuruluşunuzda bir Kurumsal Anlaşma veya eşdeğer toplu lisans sözleşmesi varsa, lütfen ücretsiz deneme sürümünüzü ayarlamak için Microsoft temsilcinize başvurun.

> [!NOTE]
> Kuruluşunuzda bir Microsoft Online Services iş ya da okul hesabı varsa ve deneme süresi sona erdikten sonra üretimde bu Intune aboneliğiyle devam edecekseniz, ilgili sayfada **Oturum aç** seçeneğine tıklamanız ve kuruluşunuzun Genel Yönetici hesabını kullanarak kimlik doğrulaması yapmanız gerekir. Bu işlem Intune denemenizin mevcut iş veya okul hesabınızla ilişkilendirilmesini sağlar.

Mobil cihazlarda yapılandırabileceğiniz ayarların listesi için bkz.:

-   [Microsoft Intune'da mobil cihaz yönetimi özellikleri](mobile-device-management-capabilities-in-microsoft-intune.md)

-   [Configuration Manager'da Mobil Cihazlar için genel ayarlar](https://technet.microsoft.com/en-us/library/dn376523.aspx)

System Center 2012 R2 Configuration Manager hakkında bilgi için bkz. [System Center 2012 Configuration Manager için Belge Kitaplığı](https://technet.microsoft.com/library/gg682041.aspx)..

## Intune hizmet güncelleştirmelerinin size nasıl etkileyeceğini anlama
Intune çevrimiçi bir hizmet olduğundan Microsoft bu hizmeti düzenli aralıklarla güncelleştirebilir.

Bu hizmet güncelleştirmelerinin sıklığını ve hizmetin kullanımını etkileyebilecek bir güncelleştirme olduğunda size sağladığımız ön bildirimi anlamanıza yardımcı olması için bu konu başlığı altındaki bilgileri kullanın.

Intune hizmetindeki değişiklikler hakkında bilgi edinmek için bkz. [Microsoft Intune’daki yenilikler](/intune/deploy-use/Whats-new-in-microsoft-intune.md). [Microsoft Intune Blogu](http://blogs.technet.com/b/microsoftintune/)’nda da hizmetteki değişiklikler tartışılır ve Intune’dan en iyi şekilde yararlanmanıza olanak tanıyacak yararlı ipuçları sağlanır.

Ayrıca, önemli hizmet güncelleştirmeleri doğrudan Intune konsolundaki bildirim panosundan size duyurulacaktır.

Microsoft’un Intune hizmeti hakkında sağladığı bildirim türleri şunlardır:
-   Hizmet değişikliklerini planlamanıza yardımcı olmak için, değişikliğin etkisine bağlı olarak, hizmet yükseltmesinden en az 30-90 gün önce. Bu, bildirim panosu uyarıları gibi ürün içi iletişim kanalları kullanılarak yapılır. Bu değişiklikler şunlar olabilir:
* Uyumluluğu veya yasal düzenlemeleri etkileyebilecek güncelleştirmeler
* Kullanıcı deneyiminde, kullanıcı arabiriminde ve iş akışlarında yapılan değişiklikler
* Yeni eklenen veya değiştirilen API’ler – Özel uygulamaların geriye dönük uyumluluğundan emin olmak için test yapmanız gerektiği bildirilir
* Sistem gereksinimlerindeki değişiklikler; örneğin, gereken en düşük tarayıcı sürümü
* Özellikte yapılan ve özelliği etkinleştirmek veya hizmet kesintisini önlemek için işlem yapmanızı gerektiren güncelleştirmeler.
-   Microsoft, aylık hizmet güncelleştirmemizdeki yeni özellikler, yeni işlevler ve var olan özelliklerde yapılan iyileştirmeler hakkında bilgi sağlar. Microsoft hizmet güncelleştirmelerini genel olarak her ayın ortalarında dağıtır. Güncelleştirmeler [Microsoft Intune’daki yenilikler](/intune/deploy-use/whats-new-in-microsoft-intune.md) bölümünde açıklanmıştır..
-   Intune hizmetinin devre dışı bırakılması durumunda, 12 ay önce bu durum size bildirilecektir.

## Sizin için uygun olan yönetim çözümünü seçin
Intune’u birkaç yolla yapılandırarak şirketinizin mobil cihazlarını ve bilgisayarlarını (bu belgede **cihazlar** olarak anılır) yönetebilir ve korunmalarına yardımcı olabilirsiniz.

-   **Tek başına Intune yapılandırması.** Kuruluşunuzdaki cihazları yönetmek için Intune’daki web tabanlı yönetim konsolunu kullanın. Intuneherhangi bir şirket içi BT altyapısı olmadan kullanılabilir, ancak Intune’u Active Directory Etki Alanı Hizmetleri ile kullanıyorsanız, Intune ve Etki Alanı Hizmetleri ile yönettiğiniz etki alanı kullanıcı hesaplarını kullanabilirsiniz.

-   **Intune ile System Center Configuration Manager.** Kuruluşunuzdaki bilgisayarları ve mobil cihazları yönetmek için Configuration Manager yönetim konsolunu kullanın. Bu yapılandırma, tek bir konsol ( Configuration Manager Yönetici Konsolu) üzerinden kuruluşunuzun tüm cihazlarını yönetmenize yardımcı olabilir. Configuration Manager, çok fazla sayıda mobil cihazı, sunucuyu ve bilgisayarı destekler. Daha fazla bilgi için [System Center 2012 Configuration Manager için Belge Kitaplığı](https://technet.microsoft.com/library/gg682041.aspx) içinde [Configuration Manager ve Microsoft Intune Kullanarak Mobil Cihazları Yönetme](http://go.microsoft.com/fwlink/?LinkID=271118) bölümüne bakın.  Hangi yaklaşımın size uygun olduğuna karar vermeyle ilgili daha fazla yardım için bkz. [Kurumsal mobil çalışmayı sağlamanın yolları](/intune/plan-design/ways-to-do-enterprise-mobility.md).

-   Office 365 tarafından sağlanan ve [Kurumsal mobil çalışmayı sağlamanın yolları](/intune/plan-design/ways-to-do-enterprise-mobility.md) bölümünde açıklanan mobil cihaz yönetimi.

## Intune hakkında daha fazla bilgi edinin
Intune hakkında daha fazla bilgi edinmek için bu kaynakları kullanın:

-   [Microsoft Intune Güven Merkezi](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/)’nde Intune güvenlik, gizlilik ve uyumluluk uygulamaları hakkında bilgi sağlanır ve Intune sertifikalarından bazıları açıklanır.

-   [Microsoft Intune'da mobil cihaz yönetimi özellikleri](/intune/understand-explore/mobile-device-management-capabilities-in-microsoft-intune.md)

### Ayrıca bkz.
[Microsoft Intune](https://docs.microsoft.com/intune/)
[System Center 2012 Configuration Manager için Belge Kitaplığı](https://technet.microsoft.com/library/gg682041.aspx)

[Microsoft Intune'daki yenilikler](/intune/deploy-use/whats-new-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


