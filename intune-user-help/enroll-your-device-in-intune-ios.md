---
title: Şirket kaynaklarına iOS cihaz erişimini ayarlama | Microsoft Docs
description: IOS cihazınızı Intune tarafından nasıl yönetileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: bd9fd38fdc244bc48333496c2f266ff039e55585
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75855572"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Şirket kaynaklarınıza iOS cihaz erişimi ayarlayın  

iOS cihazınızı Intune Şirket Portalı uygulamasına kaydederek kuruluşunuzun e-postası, dosyaları ve uygulamalarına güvenli erişim sağlayabilirsiniz.

Cihazınız kaydedildikten sonra, *yönetilen*hale gelir. Kuruluşunuz, Intune gibi bir mobil cihaz yönetimi (MDM) sağlayıcısı aracılığıyla cihaza ilkeler ve uygulamalar atayabilir.  

> [!NOTE]
> Her nedenden dolayı hizmetimizin tarafından toplanan herhangi bir veriyi üçüncü taraflardan satmayacağız.  

Cihazınızdaki iş veya okul bilgilerine erişimi sürdürmek için cihazınızı kuruluşunuzun tercih ettiğiniz ayarlarla eşleşecek şekilde yapılandırmanız gerekir. Bu makalede, cihazınızı kaydetmek ve kuruluşunuzun ayar gereksinimlerini korumak için Şirket Portalı nasıl kullanılacağı açıklanır.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Mail uygulamasında şirket e-postasına erişmeyi denediğinizde cihazınızı yönettirmeniz istendiyse, doğru yere geldiniz. iOS cihazınızda e-posta ve diğer şirket kaynaklarına erişmek için aşağıdaki yönergeleri izleyin.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Şirket Portalı uygulamasından bekleyebilecekleriniz  

### <a name="security"></a>Güvenlik  
İlk kurulum sırasında uygulama, kuruluşunuzda kimlik doğrulamanızı gerektirir. Daha sonra güncelleştirmeniz gereken bazı cihaz ayarları varsa bunları size gösterir. Örneğin kuruluşlar genellikle uymanız gereken en düşük veya en yüksek karakterli parola gereksinimleri ayarlar.

### <a name="protection"></a>Protection  
Cihazınız kaydolduktan sonra Şirket Portalı uygulaması, cihazın koruma altında kalmasını sağlar. Örneğin güvenilmeyen bir kaynaktan uygulama yüklerseniz uygulama sizi uyarır, hatta bazen şirket verilerine erişiminizi iptal edebilir. Bu tür bir ilke kuruluşlarda yaygındır ve genellikle, erişimi yeniden kazanabilmeniz için güvenilmeyen uygulamayı kaldırmanızı gerektirir.  

### <a name="setting-notifications"></a>Bildirimleri ayarlama  
Kayıttan sonra kuruluşunuz, çok faktörlü kimlik doğrulaması gibi yeni bir güvenlik gereksinimi zorlarsa Şirket Portalı size bildirim gönderir. Cihazınızla çalışmaya devam edebilmek için bazı değişiklikler yapmaya vaktiniz olur.  

Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios).  

## <a name="enroll-your-ios-device"></a>İOS cihazınızı kaydetme  

[Intune şirket portalı uygulamasını](install-and-sign-in-to-the-intune-company-portal-app-ios.md) cihazınıza indirip yüklemek için App Store 'a gidin. Ayrıca, bir Wi-Fi bağlantısı sürdürmenize ve kayıt sırasında Safari 'ye erişiminizin olması gerekir. 

Kayıt sırasında birkaç dakikadan uzun bir süre durakladığında uygulamanın kurulum 'u kapatması veya sonlandırmasına neden olabilir. Bu durumda Şirket Portalı uygulamasını açın ve yeniden deneyin.  

1. Şirket Portalı açın ve iş veya okul hesabınızla oturum açın.  

2. Şirket Portalı bildirimleri almanız istendiğinde, **Izin ver** ' e dokunun. Şirket Portalı, örneğin cihaz ayarlarınızın güncellenmesi gerekiyorsa sizi uyarmak için bildirimleri kullanır.  

3. **Erişim ayarla** ekranında, Başlat ' ı seçin **.**   

    ![Şirket Portalı, "erişim ayarlama" ekranının örnek ekran görüntüsü.](./media/ios-enrollment-checklist-1909.PNG)  

4. **Cihaz ve kayıt türü seçin** ekranı görünür ve cihaz türü için sorar.  
    * Cihazınızı kuruluşunuzdan aldıysanız, **Bu cihazın sahibi olan (kuruluş)** seçeneğine dokunun. Daha sonra bu makaledeki [cihazın tamamını güvenli hale](###secure-entire-device) getirmek için atla bölümüne atlayın.  
    * Evden aldığınız kişisel bir cihaz kullanıyorsanız, **Bu cihaza sahip** olana kadar dokunun. Ardından sonraki adıma geçin.  

    Bu ekranı görmüyorsanız, kurulumun bitmesini sağlamak için [Tüm cihazın güvenliğini](enroll-your-device-in-intune-ios.md#secure-entire-device) atlayın.  
    
    ![Örnek ekran görüntüsü Şirket Portalı, "cihaz ve kayıt türünü seçin" ekranının, cihaz türü seçeneklerinin bir listesi.](./media/ios-device-type-1909.PNG)  


5. Kaydolduktan sonra cihazınızdaki verilerin nasıl korunacağını seçin.  
    * Cihazdaki tüm uygulama ve verilerin güvenliğini sağlamak için tüm **cihaz güvenli** ' e dokunun. Ardından, kurulum 'u sona erdirmeyi sağlamak için [Tüm cihazın güvenliğini sağlayın](enroll-your-device-in-intune-ios.md#secure-entire-device) .
    * Yalnızca iş hesabınızla erişebileceğiniz uygulamaların ve verilerin güvenliğini sağlamak için **iş ile ilgili uygulamaları ve verileri güvenli hale** getirin. Daha sonra [iş ile Ilgili güvenli uygulamalar ve veriler](enroll-your-device-in-intune-ios.md#secure-work-related-apps-and-data)bölümüne gidin.  

    ![Örnek ekran görüntüsü, "cihaz ve kayıt türü seç" ekranının, kayıt türü seçeneklerinin Şirket Portalı.](./media/ios-enrollment-type-1909.PNG)  


### <a name="secure-entire-device"></a>Tüm cihazın güvenliğini sağlama  

1. **Cihaz yönetimi ve gizlilik** ekranında, kuruluşunuzun görebileceği cihaz bilgileri listesini okuyun. Sonra **devam**' a dokunun.  


 > [!IMPORTANT]
> Bu sonraki adımlar ve ekranlar, iOS sürümünüze bağlı olarak farklılık gösterir. İOS sürümünüz için adımları izleyin. 

2. Safari, cihazınızda Şirket Portalı Web sitesini açar. Yapılandırma profilini indirmeniz istendiğinde, **Izin ver**' e dokunun. Çalıştıran bir cihazımız varsa:  
    * iOS 12,2 ve üzeri: İndirme tamamlandığında **Kapat**' a dokunun. Ardından adım 3 ' e geçin.  
    * iOS 12,1 ve önceki sürümler: İndirme tamamlandığında, otomatik olarak ayarlar uygulamasına yönlendirilirsiniz. 4\. adıma atlayın.  
 
    Yanlışlıkla **Yoksay**' a dokunmanız durumunda sayfayı yenileyin. Şirket Portalı uygulamasını açmanız istenir. Buradan sonra **İndir**' e dokunun.

  > [!NOTE]
  > Yönetim profilini, bir sonraki adımlarda 8 dakika içinde açıklandığı gibi yüklemeniz gerekir. Aksi takdirde, profil kaldırılır ve kayıt işlemini yeniden başlatmanız gerekir.  

3. Şirket Portalı açmanız istendiğinde **Aç**' a dokunun. **Yönetim profilini nasıl yükleyeceğiniz** hakkında bilgi edinmek için bkz.  

4. Ayarlar uygulamasına gidin ve **< kuruluş adı >** veya **profil indirilerek**Kaydet ' e dokunun.  

    ![Ayarlar uygulamasının örnek ekran görüntüsü, kuruluşa kaydolma seçeneği.](./media/enroll-in-organization-ios-1909.PNG)  

   Seçeneklerden hiçbiri görünmezse, **genel** > **profiller & cihaz yönetimi**> **Yönetim profili**' ne gidin. Hala bir yönetim profili görmüyorsanız, yeniden indirmeniz gerekebilir.  

5. **Yükle**’ye dokunun.  
    
6. Cihaz parolanızı girin. Ardından **Install**' a dokunun.    

7. Sonraki ekran, cihaz yönetimiyle ilgili standart sistem uyarısına sahiptir. Yüklemeye devam etmek için, **yükleme**' ye dokunun. Uzaktan yönetime güvenmesi istenirse **güven**' e dokunun.  

8. Yükleme tamamlandıktan sonra **bitti**' ye dokunun. Profilin yüklendiğini doğrulamak için, **cihaz yönetimi ayarları & profiller** ' e gidin. **Mobil cihaz yönetimi**altında listelenen profili görmeniz gerekir.   

    ![Ayarlar uygulamasının, yönetim profilini gösteren cihaz yönetimi ayarlarının &, profil ekran görüntüsü örneği.](./media/ios-12-cp-enroll-1904.PNG)  

9. Şirket Portalı uygulamasına geri dönün. Şirket Portalı, cihazınızı eşitlemeye ve ayarlamaya başlayacaktır. Şirket Portalı ek cihaz ayarlarını güncelleştirmenizi isteyebilir. Varsa, **devam**' a dokunun.  

10. Listedeki tüm öğeler yeşil onay işareti gösterdiğinizde kurulumun tamamlandığını bilirsiniz. **Bitti**’ye dokunun.   

> [!Note]
> Kuruluşunuz ses ve veri sınırlarını izliyor veya size şirkete ait bir cihaz sağlıyorsa, birkaç adım daha doldurmanız gerekebilir. **Datalert** uygulamasını yüklemek isteyip istemediğiniz sorulursa, bkz. [cihazınızı Telekom gider yönetimine kaydetme](enroll-your-device-with-telecom-expense-management-ios.md). Kuruluşunuz Apple Aygıt Kayıt Programı bir parçasıysa [şirkete ait cihazınızı nasıl kaydedebileceğinizi](enroll-your-device-dep-ios.md)öğrenin.  

### <a name="secure-work-related-apps-and-data"></a>İş ile ilgili uygulamaları ve verileri güvenli hale getirme  
1. **Microsoft Authenticator indir** ekranı görünür (zaten Authenticator varsa, 2. adıma atlayın) bu ekranı görmezsiniz.  
    1. **App Store 'Dan indir**' e dokunun.
    2. Uygulama Mağazası açıldığında uygulamayı yükler. 
    3. Şirket Portalı dönün ve **devam**' a dokunun.    
    
   Microsoft Authenticator yükledikten sonra uygulamayla başka bir şey yapmanız gerekmez. Yalnızca cihazınızda mevcut olması gerekir. 

   ![Şirket Portalı, "Microsoft Authenticator Indir" ekranının örnek ekran görüntüsü.](./media/download-ms-authenticator-1909.PNG)  

2. **Cihaz yönetimi ve gizlilik** ekranında, kuruluşunuzun görebileceği cihaz bilgileri listesini okuyun. Sonra **devam**' a dokunun.  


 > [!IMPORTANT]
> Bu sonraki adımlar ve ekranlar, iOS sürümünüze bağlı olarak farklılık gösterir. İOS sürümünüz için adımları izleyin. 

3. Safari, cihazınızda Şirket Portalı Web sitesini açar. Yapılandırma profilini indirmeniz istendiğinde, **Izin ver**' e dokunun. Çalıştıran bir cihazımız varsa:  
    * iOS 12,2 ve üzeri: İndirme tamamlandığında **Kapat**' a dokunun. Ardından 4. adıma geçin.  
    * iOS 12,1 ve önceki sürümler: İndirme tamamlandığında, otomatik olarak ayarlar uygulamasına yönlendirilirsiniz. 5\. adıma atlayın.  
 
    Yanlışlıkla **Yoksay**' a dokunmanız durumunda sayfayı yenileyin. Şirket Portalı uygulamasını açmanız istenir. Uygulamadan **tekrar indir**' e dokunabilirsiniz.

  > [!NOTE]
  > Yönetim profilini, bir sonraki adımlarda 8 dakika içinde açıklandığı gibi yüklemeniz gerekir. Aksi takdirde, profil kaldırılır ve kayıt işlemini yeniden başlatmanız gerekir.  

4. Şirket Portalı açmanız istendiğinde **Aç**' a dokunun. **Yönetim profilini nasıl yükleyeceğiniz** hakkında bilgi edinmek için bkz. 

5. Ayarlar uygulamasına gidin ve **< kuruluş adı >** veya **profil indirilerek**Kaydet ' e dokunun.  

    ![Ayarlar uygulamasının örnek ekran görüntüsü, kuruluşa kaydolma seçeneği.](./media/enroll-in-organization-ios-1909.PNG)  

   Seçeneklerden hiçbiri görünmezse, **genel** > **profiller & cihaz yönetimi**> **Yönetim profili**' ne gidin. Hala bir yönetim profili görmüyorsanız, yeniden indirmeniz gerekebilir.   


6. **Kullanıcı kaydı** ekranında, **IPhone 'umu kaydet**' e dokunun.  

    ![Ayarlar uygulamasının, Kullanıcı kaydı ekranının, Kaydet düğmesini vurgulayan örnek ekran görüntüsü.](./media/user-enrollment-information-1909.PNG)  

7. Cihaz parolasını girin. Ardından **Install**' a dokunun.  

8. **Oturum açma** ekranında, YÖNETILEN Apple Kimliğiniz için parolayı girin. Çoğu durumda bu kimlik bilgileri, kuruluşunuz sizin için farklı bir kimlik bilgileri kümesi sağladıkça iş veya okul hesabınızda oturum açmak için kullandığınız verilerle aynı olacaktır. 
9. **Oturum aç**’a dokunun.  
10. Bir başarı iletisi, profil yüklendikten kısa bir süre sonra ekranda görüntülenir. Profilin yüklendiğini doğrulamak için, profil **& cihaz yönetimi** ayarları ' na gidin.  **Mobil cihaz yönetimi** altında listelenen profili görmeniz gerekir.  

    ![Ayarlar uygulamasının, yönetim profilini gösteren cihaz yönetimi ayarlarının &, profil ekran görüntüsü örneği.](./media/ios-12-cp-enroll-1904.PNG)  

11. Şirket Portalı uygulamasına geri dönün. Şirket Portalı, cihazınızı eşitlemeye ve ayarlamaya başlayacaktır. Şirket Portalı ek cihaz ayarlarını güncelleştirmenizi isteyebilir. Varsa, **devam**' a dokunun.    

12. Listedeki tüm öğeler yeşil onay işareti gösterdiğinizde kurulumun tamamlandığını bilirsiniz.  **Bitti**' ye dokunun.  

## <a name="it-administrator-support"></a>BT yöneticisi desteği  
BT yöneticisiyseniz ve cihazları kaydederken sorun yaşıyorsanız, bkz. [Microsoft Intune iOS cihaz kaydı sorunlarını giderme](https://support.microsoft.com/en-us/help/4039809). Bu makalede, sık karşılaşılan hatalar, nedenler ve bunları çözmeye yönelik adımlar listelenir.  

## <a name="next-steps"></a>Sonraki adımlar  
İş veya okul işlerinde size yardımcı olacak uygulamalar bulun. Uygulamaları Şirket Portalı aracılığıyla [nasıl kullanabileceğiniz hakkında](use-managed-apps-on-your-device-ios.md) bilgi edinin.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://go.microsoft.com/fwlink/?linkid=2010980) ulaşabilirsiniz.  
