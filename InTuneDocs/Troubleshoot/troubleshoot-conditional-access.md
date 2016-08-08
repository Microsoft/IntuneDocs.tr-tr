---
title: "Koşullu erişim sorunlarını giderme | Microsoft Intune"
description: "Kullanıcıların, kaynaklara Intune koşullu erişimi üzerinden erişemediklerinde ne yapacakları açıklanır."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: f5feb4d660693344cf7df38402f14c60007284b4


---

# Koşullu erişim sorunlarını giderme

Genellikle, bir kullanıcı e-posta veya SharePoint’a erişmeye çalışır ve kaydolmak için bir istem alır. Bu istem, kullanıcıyı şirket portalına götürür.

Bu konuda, kullanıcıların, kaynaklara Intune koşullu erişim üzerinden erişemediklerinde ne yapacakları açıklanmaktadır.


## Koşullu erişimde başarılı olmanın temel unsurları

İşe koşullu erişim sağlamak için, aşağıdaki koşullar gerekir:

-   Cihazın Intune tarafından yönetilmelidir
-   Cihaz Azure Active Directory’ye (AAD) kaydedilmelidir. Normal koşullar altında bu kayıt, Intune kaydı sırasında otomatik olarak gerçekleşir
-   Cihaz, cihazın ve cihazın kullanıcısı için Intune uyumluluk ilkelerinizle uyumlu olmalıdır.  Başka bir uyumluluk ilkesi yoksa, Intune kaydı yeterlidir.
-   Kullanıcı postayı Outlook yerine cihazın yerel posta istemcisi aracılığıyla alıyorsa, cihazda Exchange ActiveSync etkinleştirilmelidir.     Bu iOS, Windows Phone ve Android/KNOX cihazlarında otomatik olarak gerçekleşir.
-   Intune Exchange Connector’ınız düzgün şekilde yapılandırılmalıdır. Daha fazla bilgi için bkz. [Microsoft Intune’da Exchange Connector sorunlarını giderme](troubleshoot-exchange-connector.md).

Bu koşullar, Azure Yönetim Portalı’nda ve cihaz envanter raporunda her cihaz için görüntülenebilir.

## Kayıt sorunları

 -  Cihaz kaydolmamıştır, böylelikle kayıt olunduğunda sorun çözümlenecektir.
 -  Kullanıcı cihazı kaydetmiştir, ancak çalışma alanına katılma başarısız olmuştur. Kullanıcı, şirket portalından kaydı güncelleştirmelidir.

## Uyumluluk sorunları

 -  Cihaz Intune ilkesiyle uyumlu değildir. Şifreleme ve parola gereksinimleri yaygın görülen sorunlardır. Kullanıcı, şirket portalına yönlendirilir ve buradan, cihazını uyumlu olacak şekilde yapılandırabilir.
 -  Uyumluluk bilgilerinin bir cihaz için kaydolması biraz zaman alabilir. Birkaç dakika bekleyin ve tekrar deneyin.
 -  iOS aygıtları için:
     -   Kullanıcı tarafından oluşturulmuş bir e-posta profili, Intune yöneticisinin oluşturduğu bir profili engeller. Bu, iOS kullanıcıları genellikle bir e-posta profili oluşturduğundan, ardından kaydolduğundan, bu yaygın görülen bir sorundur. Şirket portalı, kullanıcıyı, el ile yapılandırılmış e-posta profilleri nedeniyle uyumlu olmadıkları konusunda bilgilendirir ve kullanıcıdan, o profili kaldırmasını ister. Kullanıcı, Intune profilinin dağıtılabilmesi için, e-posta profilini kaldırmalıdır. Sorunu önlemek için, kullanıcılarınızdan bir e-posta profili yüklemeden kayıt olmalarını ve Intune’un profili dağıtmasına izin vermelerini isteyin.
     -   Bir iOS cihazı uyumluluk denetim durumunda takılı kalarak, kullanıcının başka bir giriş yapma işlemi başlatmasını engelleyebilir. Şirket portalını yeniden başlatmak bunu düzeltebilir ve uyumluluk durumu cihazın Intune’daki durumunu yansıtır. Bir cihaz eşitlemesinden tüm veriler toplandıktan sonra, uyumluluk denetimi hızlıdır; ortalama olarak yarım saniyenin altındadır.

        Genelde cihazların bu durumda kalmalarının nedeni, hizmete bağlanmada güçlük çekmeleri veya eşitlemenin uzun sürmesidir.  Sorun farklı ağ yapılandırmalarında (hücresel, Wi-Fi, VPN), cihaz yeniden başlatmalarından sonra ve SSP’nin cihazda güncel olduğu doğrulandıktan sonra da devam ederse, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md)’da anlatıldığı şekilde Microsoft Desteği ile iletişim kurun.

## İlke sorunları

Bir uyumluluk ilkesi oluşturduğunuzda ve onu bir e-posta ilkesine bağladığınızda, her iki ilkenin aynı kullanıcıya dağıtılması gerekir, bu nedenle, hangi ilkelerin hangi gruplara dağıtıldığını planlamada dikkatli olun. Yalnızca bir ilke uygulanmış kullanıcılar, olasılıkla, cihazların uyumlu olmadığını anlayacaktır.


## Exchange ActiveSync sorunları

### Uyumlu Android cihazı, karantina bildirimi alıyor
- Kayıtlı ve uyumlu bir Android cihaz, şirket kaynaklarına erişmeye çalışırken yine de karantina bildirimi alabilir. **Başlat** bağlantısını seçmeden önce, kullanıcı, kaynaklara erişmeye çalıştıklarında şirket portalının açık olmamasını sağlamalıdır. Kullanıcılar, şirket portalını kapatmalı, kaynaklara yeniden erişmeye çalışmalı ve ardından **Başlat** bağlantısını kapatmalıdır.

### Kullanımdan kaldırılmış cihaz, erişmeye devam ediyor.
- Exchange Online kullanılırken, kullanımdan kaldırılmış bir cihaz kullanımdan kaldırıldıktan sonra birkaç saat erişmeye devam edebilir. Bunun nedeni, Exchange’in, erişim haklarını 6 saat boyunca önbelleğe almasıdır. Bu senaryoda, kullanımdan kaldırılan cihazlardaki verileri korumanın başka yöntemlerini göz önünde bulundurun.

### Cihaz uyumlu ve AAD’ye kayıtlı ancak hala engelleniyor
- Bazen Exchange ActiveSync Kimliği’nin (EASID) AAD’ye sağlanması gecikir. Bu sorunun temel nedeni azaltmadır, bu yüzden, birkaç dakika bekleyin ve yeniden deneyin.

### Cihaz engelleniyor

Cihaz, bir etkinleştirme e-postası almadan Koşullu Erişim’den engellenmiş olabilir.

- Cihazları karantinaya alan veya engelleyen varsayılan bir Exchange kuralı var mı? Varsayılan bir kural cihazları engelliyor veya karantinaya alıyorsa, cihazlar Exchange Connector’dan etkinleştirme e-postası alamaz. Bu, bilinçli olarak böyle tasarlanmıştır.
- Bildirim hesabı Temel yapılandırma’da anlatıldığı şekilde düzgün yapılandırılmış mı?
- Cihaz, Intune yönetim konsolunda bir Exchange ActiveSync cihazı olarak mevcut mu? Değilse, cihaz olası bir Exchange Connector eşitleme sorunu nedeniyle bulunamıyor olabilir. Exchange’dan bulunamayan Exchange ActiveSync cihazına bakın.
- Sendemail etkinliği için Exchange Connector günlüklerine bakın ve hata arayın. Aranacak komuta bir örnek, bildirim hesabından kullanıcı e-postasına SendEmail işlemidir.
- Exchange Connector cihazı engellemeden önce etkinleştirme e-postasını gönderir. Cihaz çevrimdışıysa, etkinleştirme e-postasını almayabilir. Ayrıca, kullanıcının e-postayı kaçırmasına neden olabileceğinden cihazın e-posta alımının Poll yerine Push kullanılarak mı yapıldığını da denetleyin. Poll yöntemine geçip cihazın e-postayı alıp almadığına bakın.

## Uyumsuz cihaz engellenmiyor

Uyumlu olmayan ancak erişimi olan bir cihazla karşılaşırsanız, aşağıdaki adımları uygulayın.

- Hedef ve Dışlama gruplarını gözden geçirin. Kullanıcı doğru hedef grupta değilse veya dışlama grubundaysa, engellenmez. Yalnızca Hedef grupta olan kullanıcıların cihazlarında uyumluluk denetimi yapılır.
- Cihazın bulunabildiğinden emin olun. Exchange Connector bir Exchange 2010 CAS’ine, buna karşın kullanıcı bir Exchange 2013 sunucusuna mı işaret ediyor? Bu durumda, varsayılan Exchange kuralı İzin Ver ise, kullanıcı Hedef grupta olsa bile Intune cihazın Exchange’a bağlandığının farkında olamaz.
- Exchange’de Cihazın Varlığı/Erişim Durumu’nu kontrol edin:
    - Bir posta kutusunun tüm mobil cihazlarının listesini almak için şu PowerShell cmdlet’ini kullanın: "Get-ActiveSyncDeviceStatistics -mailbox mbx'. Cihaz listelenmiyorsa, Exchange’e erişmiyordur.
    - Cihaz listeleniyorsa, erişim durumu hakkında ayrıntılı bilgi almak için Get-CASmailbox -identity:’upn’ | fl cmdlet’ini kullanın ve bu bilgileri Microsoft Desteği’ne verin.

## Bir destek bileti açmadan önce
Bu sorun giderme yordamları sorununuzu çözmüyorsa, Microsoft Desteği, OWA posta kutusu günlükleri veya Exchange Connector günlükleri gibi bilgileri isteyebilir.

### OWA posta kutusu günlüklerini toplama

1. OWA aracılığıyla oturum açın ve sağ üst köşedeki adınızın yanındaki ayarları (dişli) simgesini seçin.
2. **Seçenekler**’i seçin
3. Sol taraftaki sütunda **Telefon** (**Mobil Cihazlar** olarak gözükebilir) seçin.
4. Üstteki menüden, **Mobil Cihazlar**’ı seçin.
5. Listeden cihazınızı seçin ve ardından **Günlüğü Başlat**’ı seçin.
6. İstendiğinde, açılan iletişimde **Evet**’i seçin.
7. Soruna neden olan eylemi gerçekleştirin, böylelikle onu yeniden oluşturabilirsiniz.
8. 1-2 dakika bekleyin, sonra OWA’daki telefon listesine dönün. Telefonunuzun listede seçildiğinden emin olun, sonra en üst menüden **Günlüğü Al**’ı seçin.
9. Kendinizden bir ek dosyası olan bir e-posta almanız gerekir. Bir destek bileti açtığınızda, e-posta içeriğini Microsoft Destek’e sağlayın.

### Exchange Connector günlükleri

#### Genel günlük bilgileri
Exchange Connector günlüklerini görüntülemek için [Sunucu İzleme Görüntüleme Aracı](server trace viewer tool (https://msdn.microsoft.com/en-us/library/ms732023(v=vs.110).aspx') kullanın. Bu araç, Windows Server SDK’yı indirmenizi gerektirir.

>[!NOTE]
>Günlükler C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs konumundadır. Günlükler, *Connector0.log* ile başlayıp *Connector29.log* ile biten bir dizi 30 günlük dosyası içindedir. Günlükler, bir günlükte 10 MB veri biriktikten sonra birinden diğerine geçer. Günlükler Connector29’a vardıktan sonra yeniden Connector0’dan başlayarak önceki günlük dosyalarının üzerine yazılır.

#### Eşitleme günlüklerinin konumunu bulma

-    Günlüklerde bir tam eşitlemenin konumunu **tam eşitleme** ifadesini arayarak bulun. Tam eşitlemenin başlangıcında şu metin bulunur:

    'İşleme komutu: Zaman filtresi (tam eşitleme) olmadan <number> kullanıcının mobil cihaz listesi alınıyor`

    Tam eşitleme günlüğünün sonu şu şekildedir:

    Zaman filtresi (tam eşitleme) olmadan 4 kullanıcının mobil cihaz listesini alma başarıyla tamamlandı. Ayrıntılar: Envanter komutu sonucu - Eşitlenen cihazlar: 0 Komut Kimliği: commandIDGUID' Exchange sistem durumu: 'Sunucu sistem durumu 'Adı: 'PowerShellExchangeServer: <Name=mymailservername>' Durum: Bağlı','

-   Hızlı (delta) eşitlemeyi günlüklerde **hızlı eşitleme** ifadesini arayarak bulun.

##### Get next command özel durumları
**Get next command** özel durumları için Exchange Connector günlüklerine bakın ve bunları Microsoft Desteği’ne verin.

#### Ayrıntılı günlük kaydı

Ayrıntılı günlük kaydını etkinleştirmek için:

1.  Exchange Connector izleme yapılandırma dosyasını açın. Dosya şu konumdadır: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.  Anahtarı şu olan TraceSourceLine’ı (izleme kaynak satırı) bulun: OnPremisesExchangeConnectorService
3.  **SourceLevel** düğüm değerini, aşağıda gösterildiği gibi **Warning ActivityTracing** (varsayılan) yerine **Verbose ActivityTracing** olarak değiştirin.

    <TraceSourceLine>
          <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key>
          <Value xsi:type="TraceSource">
            <SourceLevel>All</SourceLevel>
            <Listeners>
              <Listener>
                <ListenerType>CircularTraceListener</ListenerType>
                <SourceLevel>Verbose ActivityTracing</SourceLevel>
                <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes>
                <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName>
                <FileQuota>30</FileQuota>
              </Listener>
            </Listeners>
          </Value>
    </TraceSourceLine>



### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Jul16_HO4-->


