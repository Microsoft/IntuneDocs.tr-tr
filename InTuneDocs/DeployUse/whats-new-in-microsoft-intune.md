---
title: Yenilikler | Microsoft Intune
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 65e53ad6a74fbf0e9249c367f517ab52ea0efa80


---

# Microsoft Intune'daki yenilikler
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

Bu sürümdeki yenilikler aşağıdaki gibidir. Windows Defender ilke ayarı güncelleştirmesi hariç, tüm bu özellikler karma müşterilerin dağıtımları için de desteklenir (Intune ile Configuration Manager). Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.

## Haziran 2016
### Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri Office 365 yönetim portalında, Hizmet Durumu’nun altında bulabilirsiniz. Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

## Uygulama yönetimi
- **Geliştirilmiş Windows 10 kurumsal veri ilkesi yapılandırma deneyimi.** Windows 10 kurumsal veri koruma ilkesi yapılandırma deneyiminde, uygulama kuralları oluşturma, ağ sınırı tanımını belirtme ve diğer kurumsal veri koruma ayarları ile ilgili geliştirmeler yapıldı. Daha fazla bilgi için bkz: [Microsoft Intune kullanarak kurumsal veri koruma (EDP) ilkesi oluşturma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


## Cihaz yönetimi
- **Olası istenmeyen uygulamalara karşı koruma sağlayan Windows Defender ilke ayarı.** Windows 10 Desktop ve Mobile için genel yapılandırma ilkesine **İstenmeyebilecek Uygulama Algılama** adlı yeni bir Windows Defender ayarı eklendi. Bu ayarı kullanarak kayıtlı Windows masaüstü bilgisayarlarını, Windows Defender tarafından istenmeyebilecek yazılım olarak sınıflandırılan yazılımları çalıştırmaya karşı koruyabilirsiniz. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune’da Windows 10 ilke ayarları](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

## Koşullu erişim
- **Intune için Cisco ISE ağ erişimi denetim ilkesi.**  Cisco Identity Service Engine (ISE) 2.1 ile birlikte Microsoft Intune’u kullanan müşteriler, ISE’de bir ağ erişimi denetim ilkesi ayarlayabilir.

    Bu ilke kullandığında, ağa WiFi veya VPN ile erişmeye çalışan cihazlara erişim izni verilmesi için cihazların aşağıdaki koşulları karşılaması gerekir:

    * Intune tarafından yönetiliyor olmalıdır
    * Dağıtılmış tüm Intune uyumluluk ilkeleriyle uyumlu olmalıdır

 Uyumsuz cihazları kullanan son kullanıcıların erişim elde etmek için kaydolması ve uyumluluk sorunlarını gidermesi istenir.
- **Tarayıcı için koşullu erişim.** [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) ve [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazlarında desteklenen web tarayıcılarından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **Dynamics CRM Online koşullu erişimi destekler.** [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazları tarafından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Dynamics CRM mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS1295358--->

## Şirket portalı güncelleştirmeleri

### Android Şirket Portalı uygulaması

- BT yöneticileri yeni "Cihazların bilinmeyen kaynaklardan uygulama yüklemesine izin vermemesini sağla (Android 4.0 +)" ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, "Bilinmeyen kaynaklardan yükleme devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Güvenlik** kısmına gitmesi ve **Bilinmeyen kaynaklar**’ı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) almasını sağlar.

- BT yöneticileri yeni "Cihazların, güvenlik tehditleri için uygulamaların taranmasını etkinleştirmiş olmasını gerektir (Android 4.0 +)” ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, “Cihazı güvenlik tehditleri için tara” iletisini görür. Kullanıcıların, **Ayarlar** > **Google** > **Güvenlik** kısmına gitmesi ve **Cihazı güvenlik tehditleri için tara**’yı açması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden açmaları gerektiği hakkında daha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını sağlar.

- BT yöneticileri yeni "USB hata ayıklamanın devre dışı olmasını gerektir (Android 4.2 +)" ilkesini uyguladığında, Android 4.2 veya üstü cihazlara sahip son kullanıcılar, "USB hata ayıklama devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Geliştirici seçenekleri** kısmına gitmesi ve “**USB hata ayıklama**”yı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) almasını sağlar.

- BT yöneticileri yeni "Minimum Android güvenlik düzeltme eki düzeyi (Android 6.0 +)" ilkesini uyguladığında, Android 6.0 veya üstü cihazlara sahip son kullanıcılar, "Bu cihaz, en düşük Android güvenlik düzeltme eki düzeyini karşılamıyor" iletisini görür. Kullanıcıların, gerekli güvenlik düzeltme ekini yüklemesi gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların gerekli güvenlik düzeltme ekini nasıl yükleneceği hakkında [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını ve mevcut durumda kendilerinde hangi güvenlik düzeltme ekinin yüklü olduğunu görmesini sağlar.

### iOS Şirket Portalı uygulaması

- Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [iOS cihazınızı el ile eşitleme](/Intune/EndUser/sync-your-device-manually-ios).

- iOS için Microsoft Intune Şirket Portalı uygulaması, iOS 8.0 ve sonraki sürümleri desteklemek için güncelleştirildi. Bu güncelleştirme, yalnızca cihaz iOS 8.0 veya sonraki sürümleri çalışıyorsa son kullanıcıların Şirket Portalı uygulamasını yükleyebileceği ve Intune’a yeni cihazları kaydedebileceği anlamına gelir. Desteklenmeyen bir iOS sürümünü çalıştıran, önceden kayıtlı cihazları olan kullanıcılar, cihazlarında Şirket Portalı uygulamasını kullanmaya devam edebilir.


## Yakında

### Bulut yol haritası
[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun.

### Hizmeti kullanımdan kaldırma
- **Intune Görüntüleyicisi uygulamaları.** Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
    - Intune AV Görüntüleyicisi
    - Intune PDF Görüntüleyicisi
    - Google Play’den Android için Intune Resim Görüntüleyicisi

  Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz.

- **Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.**
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Yaklaşık 1 Haziran 2016’dan başlayarak, kullanıcı tarafından oluşturulan grupları hedeflemek artık desteklenmeyecektir.

    Bugün, bir bildirim kuralıyla Microsoft Intune yönetim konsolundan oluşturduğunuz bir grubu hedeflemek için aşağıdaki adımları izleyebilirsiniz:

    **Yönetici** çalışma alanında **Bildirim Kuralları** > **Yeni Kural Oluştur**’a tıklayın

    Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımında, kuralın hedefleyeceği cihaz gruplarını seçin. Bu “cihaz gruplarını seçme” adımı, Intune Konsolu’ndan kaldırılıyor.

    Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
    - Ağustos 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecek. Mevcut kiracılar bundan etkilenmez.
    - Eylül 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecek.
    - Kasım 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmemesini planlıyoruz.


- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**. Temmuz ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.





## Önceki Intune sürümleri
Son altı ay içinde Intune'da neler yayınlandığını görmek istiyorsanız, bunlar [Önceki Intune yayınları](previous-intune-releases.md) makalesinde listelenmektedir.



### Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO1-->


