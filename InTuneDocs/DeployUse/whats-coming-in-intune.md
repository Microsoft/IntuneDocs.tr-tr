---
# required metadata

title: Beklenenler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da beklenen özellikler
Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Beklenen yeni güncelleştirmeler için yeniden gelip gözden geçirin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, karma müşteri dağıtımlarında da (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.


## Uygulama yönetimi
- **Windows 10 enterprise veri ilkesinde değişiklikler.** Windows 10 kurumsal veri ilkesindeki uygulama ilkesi geliştirmeleri nedeniyle, uygulama kuralları (önceki adı korumalı uygulamalar) ile yapılandırılmış bir ilkeyi kaydettiğinizde, yapılandırmış olduğunuz mevcut kurallar varsa bunlar kaybolur. Devam etmek için bu uygulama kurallarını yeniden yapılandırmanız gerekir.

- **Tarayıcı için koşullu erişim.** Exchange Online ve SharePoint Online için, bunlara yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebilmesini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **Dynamics CRM Online koşullu erişimi destekler.** Dynamics CRM Online için, müşteriler buna yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebilmesini sağlayacak bir koşullu erişim ilkesi ayarlayabilirler. iOS ve Android’de Dynamics CRM mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS1295358--->

### Xamarin desteği
Microsoft Intune uygulama SDK'sı, artık şu senaryolarda Xamarin uygulamaları destekler:

- Yeni uygulamalar yazma veya Intune SDK’sını kullanarak mevcut iş kolu uygulamalarının kodunda değişiklik yapma. Eklentiyi [Microsoft Intune Github](https://github.com/msintuneappsdk) sayfasından alabilirsiniz.
- Intune uygulama kaydırma aracını kullanarak mevcut iş kolu uygulamalarına MAM desteği ekleme.

Hangi yöntemin kullanılacağını seçerken yardım almak için bkz. [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Şirket Portalı
**iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının Cihazlarım bölmesinde tüm Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.  Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.  Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın.
<!---TFS 1233681--->

## Hizmeti kullanımdan kaldırma
**Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır.** Eylül 2016'den itibaren, Microsoft Intune Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamaları desteğine son verecektir. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

**Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.**
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Yaklaşık 1 Haziran 2016’dan başlayarak, kullanıcı tarafından oluşturulan grupları hedeflemek artık desteklenmeyecektir.

Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
- Haziran 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecekler. Mevcut kiracılar bundan etkilenmez.
- Ağustos 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecekler.
- Ekim 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmeyeceğini umuyoruz.

<!---   TFS 1278864--->
**iOS Şirket Portalı uygulaması desteğindeki değişiklikler.**
Kullanıcıların en son iOS Şirket Portalı uygulamasına güncelleştirme yapmaları gerekir. Gelecek aylarda, iOS için Microsoft Intune Şirket Portalı uygulamasının tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

**Intune Görüntüleyicisi uygulamaları.** Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz. RMS paylaşım uygulaması hakkında daha fazla bilgi edinin (belgelerin bağlantılarıyla).


### Ayrıca bkz.
Son geliştirmelerin ayrıntıları için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).


<!--HONumber=Jun16_HO2-->


