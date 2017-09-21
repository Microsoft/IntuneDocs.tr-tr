---
title: "MDM yetkilinizi Configuration Manager olarak değiştirme (karma MDM)"
description: "MDM yetkilisini tek başına Intune’dan Configuration Manager’a (karma MDM) değiştirmeyi öğrenin."
keywords: 
author: dougeby
manager: angrobe
ms.date: 05/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ms.reviewer: 
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 816aa3effc8be66844000394f27eacc4215c1bc2
ms.sourcegitcommit: 94177ee8bc9f2fe448738773757e40d799f71c18
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="change-the-mdm-authority"></a>MDM yetkilisini değiştirme
Configuration Manager’ın 1610 sürümünden başlayarak MDM yetkilinizi, Microsoft Desteği ile iletişim kurmaya ve mevcut yönetilen cihazlarınızın kaydını silip tekrar kaydetmeye gerek kalmadan değiştirebilirsiniz. Bu bölüm, Intune’dan yapılandırılmış ve MDM yetkilisi **Microsoft Intune**’dan (tek başına) **Configuration Manager**’a (karma MDM) ayarlanmış mevcut bir Microsoft Intune kiracısını mevcut yönetilen cihazların kaydını silip yeniden kaydetmeye gerek kalmadan değiştirme adımları sağlar.

> [!Note]    
> Configuration Manager konsolundan (karma) yapılandırılmış ve MDM yetkilisi **Configuration Manager**’dan (karma) tek başına **Microsoft Intune**’a ayarlanmış mevcut bir Microsoft Intune kiracısını mevcut yönetilen cihazların kaydını silip yeniden kaydetmeye gerek kalmadan değiştirmek istiyorsanız bkz. [MDM yetkilisini Configuration Manager’dan (karma MDM) tek başına Intune’a değiştirme](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority). 


### <a name="key-considerations"></a>Dikkat Edilmesi Gereken Önemli Noktalar
Yeni MDM yetkilisine geçtikten sonra cihazın iade edilmesi ve hizmetle eşitlenmesi için bir geçiş süresi (sekiz saate kadar) olması olasıdır. Kayıtlı cihazların değişiklikten sonra yönetilmeye ve korunmaya devam edeceğinden emin olmak için yeni MDM yetkilisinde (karma) ayarları yapılandırmanız gerekecektir. Aşağıdakilere dikkat edin:
- Yeni MDM yetkilisinden (tek başına Intune) gelen ayarların cihazdaki mevcut ayarların yerini alması için değişiklik sonrasında cihazların hizmete bağlanması gerekir.
- MDM yetkilisini değiştirdikten sonra önceki MDM yetkilisine ait (tek başına Intune) bazı temel ayarlar (profiller gibi) 7 güne kadar veya cihaz hizmete ilk kez bağlanana kadar cihazda kalır. Yeni MDM yetkilisinde (karma) uygulama ve ayarları (ilkeler, profiller, uygulamalar vb.) mümkün olduğunca çabuk yapılandırmanız ve mevcut kayıtlı cihazları olan kullanıcıları barındıran gruplara bu ayarları dağıtmanız önerilir. MDM yetkilisindeki değişiklikten sonra cihaz hizmete ilk bağlandığı zaman, yeni MDM yetkilisinden yeni ayarları alacaktır, böylece yönetim ve korumada boşluk oluşması önlenecektir.
- İlişkili kullanıcısı olmayan cihazlar (genellikle iOS Aygıt Kayıt Programı veya toplu kayıt senaryoları kullandığınızda ortaya çıkar), yeni MDM yetkilisine geçirilmez. Bu cihazları yeni MDM yetkilisine taşımak için destek ile iletişime geçip yardım almanız gerekir.

### <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>MDM yetkilisini Configuration Manager (karma) olarak değiştirmeye hazırlanma
MDM yetkilisindeki değişikliğe hazırlanmak için aşağıdaki bilgileri gözden geçirin:
- MDM yetkilisini değiştirme seçeneğinin açılması için Configuration Manager sürüm 1610 veya üzerine sahip olmanız gerekir.
- Yeni MDM yetkilisine geçtikten sonra bir cihazın hizmete bağlanması sekiz saati bulabilir.
- Configuration Manager konsolunda Intune aboneliğini ayarladığınızda kullanacağınız ve Tek Başına Intune tarafından yönetilen tüm kullanıcıları içeren bir Configuration Manager kullanıcı koleksiyonu oluşturun. Böylece MDM yetkilisindeki değişiklikten sonra kullanıcılar ve cihazlarının kendilerine atanmış bir Configuration Manager lisansı olduğundan ve karma ortamda yönetilebileceklerinden emin olursunuz.
- BT Yöneticisi kullanıcısının da bu koleksiyonda olduğundan emin olun.  
- Değişiklikten önce MDM Yetkilisi, Intune yönetim konsolunda **Microsoft Intune olarak ayarlı** (tek başına) şeklinde görünecektir.
- MDM yetkilisindeki değişiklikten önce MDM Yetkilisi, Microsoft Intune yönetim konsolunda **Microsoft Intune olarak ayarlı** (tek başına kiracı) olarak görüntülenmelidir.
    > [!NOTE]    
    > MDM yetkiliniz **Intune ve Office 365 tarafından yönetiliyor** olarak görünüyorsa MDM yetkilinizi **Configuration Manager** (karma) olarak değiştirdiğinizde, Office 365 tarafından yönetilen MDM cihazlarınız artık yönetilmeyecektir. MDM yetkilisini değiştirmeden önce bu kullanıcılara Intune veya Enterprise Mobility Suite lisansı atamanızı öneririz.   

- [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) Cihaz Kayıt Yöneticisi rolünü kaldırın. Ayrıntılar için bkz. [Intune’dan bir cihaz kayıt yöneticisini silme](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Yapılandırılmış tüm cihaz grup eşlemelerini kapatın. Ayrıntılar için bkz. [Microsoft Intune’da cihazları cihaz grubu eşleme ile kategorilere ayırma](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- MDM yetkilisindeki değişiklik sırasında son kullanıcılar etkilenmeyecektir. Ancak, cihazlarının açık olduğundan ve değişiklikten hemen sonra hizmete bağlandıklarından emin olmak için son kullanıcılara bu değişikliği bildirmek isteyebilirsiniz. Böylece, olabildiğince çabuk bir şekilde olabildiğince fazla cihazın değişiklik sonrasında hizmete bağlandığından ve kaydolduğundan emin olursunuz.
- MDM yetkilisindeki değişiklikten önce iOS cihazları yönetmek için tek başına Intune kullanıyorsanız, Intune’da önceden kullanılan bu Apple Anında İletilen Bildirim servisinin (APNs) Configuration Manager’da (karma) yenilendiğinden ve kiracıyı ayarlamak için kullanıldığından emin olmalısınız.    

    > [!IMPORTANT]  
    > Karma için farklı bir APNs kullanılırsa önceden kaydedilen TÜM iOS cihazların kaydı silinir ve bunlar için yeniden kayıt işlemi yapmanız gerekir. MDM yetkilisindeki değişiklikten önce, Intune’da iOS cihazları yönetmek için tam olarak hangi APNs sertifikasının kullanıldığını öğrenin. Apple Anında İletme Sertifikası Portalı’ndaki (https://identity.apple.com) listede aynı sertifikayı bulun, daha sonra asıl APNs sertifikasını oluştururken Apple Kimliği kullanılan kullanıcının belirlendiğinden ve MDM yetkilisindeki değişikliğin parçası olarak bu APNs sertifikasını yenilemek için kullanıcının uygun olduğundan emin olun.  

### <a name="change-the-mdm-authority-to-configuration-manager"></a>MDM yetkilisini Configuration Manager olarak değiştirme
MDM yetkilisini Configuration Manager olarak değiştirme işlemi, aşağıdaki yüksek düzey adımları içerir:  
- Configuration Manager konsolunda Microsoft Intune aboneliğini ekleyin.
- Yenilediğiniz APNs sertifikasını kullanarak Apple APNs sertifikasını yapılandırın.
- Configuration Manager konsolunda yeni MDM yetkilisinden (karma) gelen ayarları ve uygulamaları yapılandırın ve dağıtın.
- Cihazlar hizmete bağlandığı zaman, yeni MDM yetkilisinden yeni ayarlar eşitlenir ve alınır.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>MDM yetkilisini Configuration Manager olarak değiştirmek için
1. Configuration Manager konsolunda **Yönetim** &gt; **Genel Bakış** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve bir Intune aboneliği eklemeyi seçin.
2. Intune’da MDM yetkilisini ayarlarken kullandığınız Intune kiracısında oturum açın ve **İleri**’ye tıklayın.
3. **MDM Yetkilimi Configuration Manager olarak değiştir**’i seçin ve **İleri**’ye tıklayın.
4. Yeni karma MDM yetkilisi tarafından yönetilmeye devam edecek tüm kullanıcıları içerecek şekilde kullanıcı koleksiyonunu ayarlayın.
5. **İleri** 'yi tıklatın ve sihirbazı tamamlayın. Artık MDM yetkilisi, **Configuration Manager** olarak değiştirildi.
6. Aynı Intune kiracısını kullanarak [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) oturum açın ve MDM yetkilisinin **Configuration Manager’a ayarla** şeklinde değiştirildiğini doğrulayın.


### <a name="enable-ios-enrollment"></a>iOS kaydını etkinleştirme
iOS cihazlarınız varsa Configuration Manager’da APNs sertifikalarını yapılandırmanız gerekir.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>iOS kaydını etkinleştirmek ve APNs sertifikasını yapılandırmak için

1. **Sertifika imzalama isteği indirme**

    1. Configuration Manager konsolunda **Yönetim** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Abonelikleri**’ne gidin ve **APNs sertifika isteği oluştur**’u seçerek **Apple Anında İletilen Bildirim Servisi Sertifika İmzalama İsteği İste** iletişim kutusunu açın.  
    2. **Gözat** ile yeni sertifika imzalama isteği (.csr) dosyasını kaydetmek istediğiniz yola gözatın. Sertifika imzalama isteği (.csr) dosyasını yerel olarak kaydedin.  
    3. **İndir**'e tıklayın. Yeni Microsoft Intune .csr dosyası indirilir ve Configuration Manager tarafından kaydedilir.   

    > [!IMPORTANT]
    > Yeni bir sertifika imzalama isteği indirmeniz gerekir. Mevcut bir dosyayı kullanırsanız başarısız olursunuz.  

2.  [Apple Anında İletme Sertifikası Portalı](http://go.microsoft.com/fwlink/?LinkId=269844)’na gidin ve tek başına Intune’da kullandığınız APNs sertifikasını oluşturmak ve yenilemek için kullanılmış **aynı** Apple Kimliği ile oturum açın.

    ![Apple Anında İletme Sertifikaları Portalı oturum açma sayfası](../media/mdm-change-apns-portal.png)

3. Tek başına Intune’da kullandığınız APNs sertifikasını seçin ve daha sonra **Yenile**’ye tıklayın.

    ![APNs Yenile iletişim kutusu](../media/mdm-change-renew-apns.png)

4. Yerel olarak indirdiğiniz APNs sertifika imzalama isteği (.csr) dosyasını seçin ve ardından **Karşıya Yükle**’ye tıklayın.

    ![Apple Anında İletme Sertifikaları Portalı oturum açma sayfası](../media/mdm-change-renew-apns-upload.png)
 
5. Aynı APNs’yi seçin ve ardından **İndir**’e tıklayın. APNs (.pem) sertifikasını indirin ve dosyayı yerel olarak kaydedin.  

    ![Apple Anında İletme Sertifikaları Portalı oturum açma sayfası](../media/mdm-change-renew-apns-download.png)

6. Aynı Apple Kimliğini kullanarak, yenilenmiş APNs sertifikasını karma kiracıya yükleyin.

    1.  Configuration Manager konsolunda **Yönetim** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve **Bulut Platformları** &gt; **iOS**’u seçin.  
    2.  **Microsoft Intune Abonelik Özellikleri** iletişim kutusunda **APNs Sertifikası** sekmesini seçin ve **iOS ve MAC OS X (MDM) kaydını etkinleştir** onay kutusunu seçmek üzere tıklayın.  
    3.  **Gözat**’a tıklayın ve Apple'dan indirilen APN sertifika (.cer) dosyasına gidin. Configuration Manager, APNs sertifikası bilgilerini görüntüler. APNs sertifikasını Intune'a kaydetmek için **Tamam** 'a tıklayın.  

        ![Intune Abonelik özellikleri sayfası - iOS](../media/mdm-change-subscription-properties-ios.png)

### <a name="enable-android-enrollment"></a>Android kaydını etkinleştirme
1. Configuration Manager konsolunda **Yönetim** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve **Bulut Platformları** &gt; **Android**’i seçin.  
2. **Android kaydını etkinleştir**’i seçin ve **Tamam**’a tıklayın.

### <a name="enable-windows-enrollment"></a>Windows kaydını etkinleştirme
1. Configuration Manager konsolunda **Yönetim** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve **Bulut Platformları** &gt; **Windows**’u seçin.  
2. **Windows kaydını etkinleştir**’i seçin ve **Tamam**’a tıklayın.

### <a name="enable-windows-phone-enrollment"></a>Windows Phone kaydını etkinleştirme
1. Configuration Manager konsolunda **Yönetim** &gt; **Bulut Hizmetleri** &gt; **Microsoft Intune Aboneliği**’ne gidin ve **Bulut Platformları** &gt; **Windows Phone**’u seçin.  
2. Etkinleştirmek istediğiniz platformu seçin ve **Tamam**’a tıklayın.


### <a name="next-steps"></a>Sonraki adımlar
MDM yetkilisindeki değişiklik tamamlandıktan sonra aşağıdaki adımları gözden geçirin:
- Intune hizmeti; bir kiracının MDM yetkilisinin değiştiğini algıladığında, kayıtlı tüm cihazlara hizmete giriş yapmaları ve eşitlenmeleri için bir bildirim iletisi gönderir (bu, düzenli olarak zamanlanmış girişin dışındadır). Böylece MDM yetkilisi tek başına Intune’dan karmaya değiştirildikten sonra, açık ve çevrimiçi olan cihazlar hizmete bağlanır, yeni MDM yetkilisini alır ve bundan sonra karma tarafından yönetilmeye başlar. Bu cihazların yönetiminde ve korunmasında bir kesinti olmaz.
- MDM yetkilisindeki değişiklik sırasında (veya hemen sonrasında) açık ve çevrimiçi olan cihazlarda bile, cihazlar yeni MDM yetkilisi altında hizmete kaydolmadan önce sekiz saate kadar (bir sonraki zamanlanmış düzenli iadenin zamanına bağlı olarak) bir gecikme olur.    

  > [!IMPORTANT]    
  > MDM yetkilisini değiştirmeniz ve yeni yetkiliye yenilenmiş APNs sertifikasının yüklenmesi arasında geçen sürede, yeni iOS cihazların kaydı ve iadesi başarısız olacaktır. Bu nedenle, MDM yetkilisindeki değişiklikten hemen sonra APNs sertifikasını gözden geçirmeniz ve yeni yetkiliye yüklemeniz önemlidir.

- Kullanıcılar, el ile cihazdan hizmete iadeyi başlatarak hızlıca yeni MDM yetkilisine geçebilir. Bunu, Şirket Portalı uygulamasını kullanarak ve bir cihaz uyumluluk denetimi başlatarak kolaylıkla yapabilir.
- Cihazlar, MDM yetkilisindeki değişikliği takiben hizmete iade edildikten ve hizmetle eşitlendikten sonra her şeyin düzgün çalıştığını doğrulamak için Configuration Manager konsolunda cihazları arayın. Önceden Intune tarafından yönetilen cihazlar artık Configuration Manager konsolunda yönetilen cihazlar olarak görüntülenecektir.    
- Cihaz MDM yetkilisindeki değişiklik sırasında çevrimdışı olduğu zaman ile hizmete giriş yaptığı zaman arasında bir ara dönem vardır. Bu ara dönemde cihazın korunduğundan ve işlevsel olduğundan emin olmak için aşağıdaki öğeler 7 güne kadar (veya cihaz yeni MDM yetkilisine bağlanıp mevcut ayarları yenileriyle değiştirene kadar) cihazda kalacaktır:
    - E-posta profili
    - VPN profili
    - Sertifika profili
    - Wi-Fi profili
    - Yapılandırma profilleri
- Yeni MDM yetkilisine geçtikten sonra, Microsoft Intune yönetim konsolunda doğru uyumluluk verilerinin gösterilmesi bir haftayı bulabilir. Ancak Azure Active Directory’deki ve cihazdaki uyumluluk durumları doğru olacaktır, böylece cihaz korunmaya devam edecektir.
- Mevcut ayarların üzerine yazılması amaçlanan yeni ayarların, öncekilerle aynı ada sahip olduğundan emin olun. Aksi takdirde eski ayarların üzerine yazılmaz. Ve cihazlarda gereksiz profiller ve ilkeler ortaya çıkabilir.    

  > [!TIP]    
  > En iyi uygulama olarak, tüm yönetim ayarları ve yapılandırmaları ile dağıtımları, MDM yetkilisindeki değişiklik tamamlandıktan hemen sonra oluşturmalısınız. Böylece, ara dönemde cihazların korunduğundan ve etkin olarak yönetildiğinden emin olursunuz.

-  MDM yetkilisini değiştirdikten sonra cihazların yeni yetkiliye başarılı bir şekilde kaydedildiğini doğrulamak için aşağıdaki adımları gerçekleştirin:   
    - Yeni cihaz kaydetme
    - Yeni kaydedilen cihazın Configuration Manager’da görüntülendiğinden emin olun.
    - Yönetim konsolunu kullanarak cihazda Uzaktan Kilitleme gibi bir eylem gerçekleştirin. Bu eylem başarılı olursa cihaz yeni MDM yetkilisi tarafından yönetiliyor demektir.
- Belirli cihazlarla sorun yaşıyorsanız bu cihazları kaldırıp yeniden kaydederek cihazların yeni yetkiliye bağlanması ve yönetilmeye devam etmesini sağlayabilirsiniz.