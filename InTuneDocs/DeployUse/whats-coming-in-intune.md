---
title: Beklenenler | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 9b536372623632b609433c49991a8bdc70e6da49


---

# Microsoft Intune’da beklenen özellikler - Temmuz
Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Beklenen yeni güncelleştirmeler için yeniden gelip gözden geçirin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.


## Uygulama yönetimi
### Uygulama sağlama profili güncelleştirme deneyimini geliştirme
Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profiliyle tanımlanan ilkeleri zorunlu tutar.

Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi normalde 3 yıldır. Öte yandan, 1 yıl sonra sağlama profilinin süresi dolar. Bu güncelleştirmeyle Intune size, sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için araçlar sağlayacaktır.
<!--- TFS 1280247--->

### Xamarin desteği
Aşağıdaki senaryolarda Microsoft Intune uygulama SDK’sı, Xamarin uygulamalarını destekleyecek:

- Yeni uygulamalar yazma veya Intune SDK’sını kullanarak mevcut iş kolu uygulamalarının kodunda değişiklik yapma. Eklentiyi [Microsoft Intune Github](https://github.com/msintuneappsdk) sayfasından edinebileceksiniz.
- Intune uygulama kaydırma aracını kullanarak mevcut iş kolu uygulamalarına MAM desteği ekleme.

Hangi yöntemin kullanılacağını seçerken yardım almak için bkz. [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Cihaz yönetimi
### Cihaz kayıt sınırlarında artış
Intune, yapılandırılabilir cihaz kayıt sayısı üst sınırını kullanıcı başına 5 cihazdan 15 cihaza çıkaracaktır.
<!---TFS 1289896 --->

## Grup yönetimi
### Ağustos 2016’nın başında Intune Grupları Azure Active Directory Grupları’na geçiyor
Intune, Intune’daki kullanıcı ve cihaz grupları olarak Azure Active Directory (AAD) güvenlik gruplarının kullanıldığı yeni bir grup yönetim deneyimi oluşturmaktadır. Bu gruplar **yeni Azure tabanlı Intune yönetici portalını kullanıma aldığımızda** tüm grup yönetimi, ilke yönetimi ve profil yönetimi için kullanılacaktır.

Bu yeni deneyim hizmetler arasında yinelenen gruplarınızın olmasını engelleyecek, **yeni bazı Azure Active Directory Premium (AADP) grup özelliklerine erişmenizi sağlayacak**, ayrıca PowerShell ve Graph kullanılarak kapsamı genişletme olanağı sağlayacaktır. Bu deneyim, kurumsal mobil kullanım yönetimi genelinde grup yönetimi deneyimini de birleştirecektir.

Güvenlik Gruplarına geçiş yapabilmek için, **geçerli yönetici konsolunda** bazı değişiklikler yapılacaktır. **Bu değişiklikler ve AAD güvenlik gruplarının kullanımı, Intune belgelerine kaydedilecektir**.

Intune’u yeni kullanmaya başlayan müşteriler, **güvenlik grubu değişikliklerinden bazılarını geçerli kiracılardan önce göreceklerdir**.

Grup yönetimindeki değişikliklere ek olarak, **aşağıdaki işlevler de kullanım dışı kalacaktır**:
- Yeni grup oluşturulurken üyeleri ve grupları dışlama
- Hizmet Yöneticisi rolündeki 'Grupları Yönet' işlevi
- Bildirim Kuralları için özel grup tabanlı uyarılar
- Raporlarda gruplarla özetleme


## Şirket Portalı

### Android için Şirket Portalı’na eklenen 'Bildirimler'
Ağustos’ta kullanıma sunacağımız güncelleştirmeyle Android için Şirket Portalı’nda giriş sayfasına yeni **Bildirimler** simgesi eklenmektedir. Bu simgeye dokunulduğunda **Bildirimler** sayfasına erişim sağlanacak, bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilecektir. iOS Şirket Portalı uygulamasını da kullanıyorsanız, bildirimler deneyimini zaten görmüş olacaksınız. **Bildirimler** sayfası eklendikten sonra, cihazın önceden kaydedilmiş olması koşuluyla Android için Şirket Portalı’nı her başlattığınızda veya sürdürdüğünüzde **Şirket Erişim Kurulumu** sayfasını görmeyeceksiniz. Birçoğunuzun son kullanıcı kılavuzları oluşturduğunu ve kılavuzunuzun/ekran görüntülerinizin güncelleştirilmesi gerektiğinde önceden size bildirilmesini istediğinizi duyuyoruz. Lütfen deneyimdeki yaklaşan değişiklikleri yansıtacak şekilde belgelerinizi güncelleştirin. Güncelleştirilmiş ekran görüntülerini şu adreste bulabilirsiniz: https://aka.ms/androidcpupdate  

### Workplace Join başarısız olduğunda kullanıcıların kayıt sorunlarını çözmesine yardımcı olma
Koşullu erişim kullanırken, Workplace Join (WPJ) hatasıyla karşılaşan son kullanıcılar için Şirket Portalı web sitesindeki Windows 8.1, Windows 10 Masaüstü ve Windows 10 Mobile’ın kayıt adımları basitleştirilmiştir. Daha önce, son kullanıcılar cihazı kaydetmeyi ve WPJ işlemi yapmayı denerken kayıt başarılı olduğunda ancak WPJ başarısız olduğunda, kaydedilen cihaz kullanıcıların belirleyebilmesi için cihaz listesinde gösterilmeyebiliyor ve kullanıcılarda kafa karışıklığına neden oluyordu. Kullanıcılara artık birbirinden ayrı “Cihaz kaydı” ve “Workplace Join” adımları gösterilir. Böylelikle cihazlarının durumunu daha kolay görebilir ve WPJ hatasından sonra işlemi tamamlayabilirler. Ayrı adımların, BT yöneticileri için sorun giderme işlemini basitleştirmesi de beklenmektedir.

### iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler
Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının Cihazlarım bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermeyecektir. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse gösterilir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kayıtlı cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilecektir.  Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir. Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın.
<!---TFS 1233681--->
### Dışarıdan uygulama yüklemelerini kayıtlı Android cihazlarıyla kısıtlama
Android için Intune Şirket Portalı uygulaması kullanılarak Intune’a kaydedilmeyen Android cihazları, artık Şirket Portalı web sitesi üzerinden uygulama yükleyemezler.
<!---TFS 1299082--->

## Hizmeti kullanımdan kaldırma
**Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır.** Eylül 2016'den itibaren, Microsoft Intune Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamaları desteğine son verecektir. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

**Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.**
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Yaklaşık 1 Haziran 2016’dan başlayarak, kullanıcı tarafından oluşturulan grupları hedeflemek artık desteklenmeyecektir.

Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
- Ağustos 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecek. Mevcut kiracılar bundan etkilenmez.
- Eylül 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecek.
- Kasım 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmemesini planlıyoruz.

<!---   TFS 1278864--->

**iOS Şirket Portalı uygulaması desteğindeki değişiklikler.**
Temmuz ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

**Intune Görüntüleyicisi uygulamaları.** Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz. RMS paylaşım uygulaması hakkında daha fazla bilgi edinin (belgelerin bağlantılarıyla).



### Ayrıca bkz.
Son geliştirmelerin ayrıntıları için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).



<!--HONumber=Jul16_HO4-->


