---
title: Microsoft Intune uygulama ile Kurumsal cihaz kaydı | Microsoft Docs
description: Intune kurumsal bir Android cihazı ıntune'a nasıl kaydedildiği açıklanır
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cf384bfcc0782226e363a6527ea47c4140f7faa
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61499813"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Microsoft Intune uygulama ile Kurumsal Cihazınızı kaydetme

Şirket e-posta, uygulamalar ve kuruluşunuzun kullanıma sunduğu diğer verileri güvenli erişim elde etmek için şirkete ait Android Cihazınızı kaydetme. Android 6.0 ve üzeri çalıştıran şirket ait cihazları Microsoft Intune uygulama destekler. Bu otomatik olarak yeni ve Fabrika sıfırlaması cihazlarında kayıt sırasında yüklenir. 

Kaydetmek için dört yolu vardır. Kuruluşunuz hangi seçeneğin kullanılacağını size bildirmek.
 
* Yakın alan iletişimi (NFC)  
* Belirteç  
* QR kodu   
* Google sıfır dokunma  

Kayıt başlamadan önce haberdar olduğunuzdan emin olun hangi seçeneğin uygun adımları izleyebilmeniz kullanmanız gerekir.  

## <a name="enroll-device"></a>Cihaz kaydetme 
Ayarlama ve Cihazınızı kaydetmek için aşağıdaki adımları tamamlayın.  

> [!NOTE]
> Android sürümü veya cihaz üreticisi, bu yordamda kapsamında olmayan ek adımları tamamlaması gerektirebilir. Ekran görüntülerinde de gördüğünüz metin ve renkleri de Cihazınızda farklı görünebilir.  

1. Yeni veya fabrika ayarlarına sıfırlama cihazı açın.  
2. **Hoş Geldiniz** ekranında dili seçin.   Bir QR kodu veya NFC ile kayıt talimatı alındıktan yöntem eşleşen aşağıdaki adımları izleyin.  
     * NFC: NFC desteklenen cihazınızın, kuruluşunuzun ağa bağlanmak için programcı cihaz karşı dokunun. Ekrandaki yönergeleri izleyin. Chrome'nın hizmet kullanım koşulları için ekran ulaştığında, 5. adımından devam edin.  

      * QR kodu: Bölümündeki adımları tamamlamanız [QR kodu kayıt](#qr-code-enrollment).  

      Başka bir yöntem kullanmak talimatı alındıktan, 3. adıma geçin.    

1. Wi-Fi ve dokunun bağlanma **sonraki**. Kayıt yönteminizi eşleşen adımı izleyin. 

    * belirteci: Google oturum açma ekranına aldığınızda bölümünde bulunan adımları tamamladığınızdan [belirteç kayıt](#token-enrollment).    
    * Google sıfır dokunma: Wi-Fi'a bağlandıktan sonra Cihazınızı kuruluşunuz tarafından tanınır. 4. adıma devam etmek ve Kurulum işlemi tamamlanana kadar ekrandaki yönergeleri izleyin.    
 
       ![Örnek Google kabul et ve devam et düğmesi vurgulama sıfır dokunma, kullanıyorsanız bkz Google koşulları ekran görüntüsü.](./media/google-zero-touch-intune-app-01.png)   
   
4. Google'nın koşullarını gözden geçirin. Ardından dokunun **kabul et ve devam et**.  

      ![Örnek kabul et ve devam et düğmesi vurgulama Google koşulları ekran görüntüsü.](./media/fully-managed-intune-app-04.png)   

6. Hizmet, Chrome'un koşullarını gözden geçirin. Ardından dokunun **kabul et ve devam et**.  

   ![Kabul et ve devam et düğmesi vurgulama, Chrome hizmet kullanım koşulları ekran görüntüsü örnek.](./media/fully-managed-intune-app-06.png)   

7. Oturum açma ekranları, iş veya Okul hesabınızla oturum açın.   

    a. E-postanızı girin ve dokunun **sonraki**.      
    b. Parolanızı girin ve dokunun **oturum**.  

8. Kuruluşunuzun gereksinimlerine bağlı olarak, ekran kilitleme veya şifreleme gibi ayarları güncelleştirmek için istenebilir. Bu komut istemlerini görürseniz dokunun **AYARLAMAK** ve ekrandaki yönergeleri izleyin.  

   ![Ayarla düğmesi vurgulama iş telefon ekran kümesi görüntüyü örnek.](./media/fully-managed-intune-app-10.png)   

9. Cihazınızda iş uygulamaları yüklemek için dokunun **yükleme**. Yükleme tamamlandıktan sonra dokunun **sonraki**.  

   ![Yükle düğmesine vurgulama iş telefon ekran kümesi görüntüyü örnek.](./media/fully-managed-intune-app-11.png)   

10. Cihazınızın hazır olduğunu iletisini aldığınızda, dokunun **BİTTİ**. 

11. Uygulamalarınıza gidin ve Microsoft Intune uygulamasını açın. Seçin **oturum**. 

12. Üzerinde **Kurulum erişim** ekran, bekleyen görevlerin bir listesini görürsünüz. Dokunun **devam**.  

       ![Örnek Intune uygulamasının görüntüsü erişim ekran, Bekleyen Görevler gösteren ayarlayın.](./media/fully-managed-intune-app-14.png)   

13. Cihaz kaydı tamamlandığında dokunun **devam**. Microsoft Intune ek cihaz ayarları güncelleştirmek için isteyebilir.   

       ![Örnek Intune uygulama, güncelleştirmeyi cihaz ayarları ekran görüntüsü.](./media/fully-managed-intune-app-15-2.png)   

14. Listedeki tüm öğeler yeşil bir daire gösterdiğinizde Kurulumu tamamlanır. Artık şirket kaynaklarına erişim sağlayabilir.  

       ![Örnek Intune uygulama, tamamlanan gösteren kurma erişim ekranını görevleri görüntüsü.](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>QR kodu kayıt  
Bu bölümde, şirket tarafından sağlanan QR kodunu tarayın.  İşiniz bittiğinde size cihaz kayıt adımlarını yeniden yönlendirmeniz.     
  
1. Üzerinde **Hoş Geldiniz** ekranında, ekran beş kez için QR Kodu Kurulumu Başlat'a dokunun.  

   ![Örnek ekrana dokunmanız yönergeleri vurgulama cihaz Kurulumu Hoş Geldiniz ekranının görüntüsü.](./media/qr-code-intune-app-01.png)  

2. Wi-Fi bağlanmak için ekrandaki yönergeleri izleyin.  
3. Cihazınızı bir QR kodu tarayıcısını yoksa, Kurulum ekranlarını tarayıcı yüklü olarak ilerleme durumunu gösterir. Yüklemenin tamamlanmasını bekleyin.  
4. İstendiğinde, kayıt profilini kuruluşunuz verdiğiniz QR kodunu tarayın.  
5. Geri dönüp [kaydetme cihaz](#enroll-device), Kuruluma devam etmek için 4. adım.  

## <a name="token-enrollment"></a>Belirteç kayıt  
Bu bölümde, şirket tarafından sağlanan belirtecinizi girmenizi isteriz. İşiniz bittiğinde size cihaz kayıt adımlarını yeniden yönlendirmeniz.  

1. Google oturum açma ekranında içinde **e-posta veya telefon** kutusuna **afw #setup**. **İleri**’ye dokunun. 

   !["Afw #setup" alanına girilen olduğunu gösteren Google oturum açma ekranında, örnek görüntüsü.](./media/token-intune-app-01.png)   

2. Seçin **yükleme** için **Android cihaz İlkesi** uygulama. Yükleme işlemine devam edin. Cihazınıza bağlı olarak gözden geçirin ve ek koşullarını kabul gerekebilir.    

3. Üzerinde **bu cihazı Kaydet** ekranındayken **sonraki**.  

   ![Örnek kaydetme bu cihazın ekran görüntüsü. QR kodu gösterimi gösterir. İleri düğmesine vurgular.](./media/token-intune-app-02.png)  

4. Seçin **kodu girin**.

   ![Etkin bir QR kodu tarayıcısını örnek ekran görüntüsü. ENTER kodu düğmesine vurgular.](./media/token-intune-app-03.png)  

5. Üzerinde **tarama veya kod girin** ekran, kuruluşunuzun verdiğiniz kod yazın.  Ardından **İleri**'ye tıklayın.  

   ![Örnek görüntü tarama veya kod ekranında, İleri düğmesine vurgulama girin.](./media/token-intune-app-04.png)  

6. Geri dönüp [kaydetme cihaz](#enroll-device), Kuruluma devam etmek için 4. adım.  



## <a name="next-steps"></a>Sonraki adımlar   
Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  
