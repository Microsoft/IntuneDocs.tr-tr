---
title: Şirket cihazını Microsoft Intune App 'e kaydetme | Microsoft Docs
description: Intune 'da bir şirket Android cihazının nasıl kaydedileceğini açıklar
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
ms.openlocfilehash: b23323766e91e31c48aec6a51dfae971c3a333e8
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735749"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Kurumsal cihazınızı Microsoft Intune uygulamasına kaydetme

Şirket e-postasına, uygulamalarına ve kuruluşunuzun kullanılabilir olduğu diğer verilere güvenli erişim sağlamak için şirkete ait Android cihazınızı kaydedin. Microsoft Intune uygulaması, Android 6,0 ve üzeri sürümleri çalıştıran şirkete ait cihazları destekler. Kayıt sırasında yeni ve fabrika sıfırlaması cihazlarına otomatik olarak yüklenir. 

Kaydolmak için dört yol vardır. Kuruluşunuz hangi seçeneği kullanacağınızı bilmenizi sağlamalıdır.
 
* Yakın alan Iletişimi (NFC)  
* Belirteç  
* QR kodu   
* Google sıfır Touch  

## <a name="enroll-device"></a>Cihazı kaydetme 
Cihazınızı ayarlamak ve kaydetmek için aşağıdaki adımları uygulayın.  

> [!NOTE]
> Android sürümü veya cihaz üreticisi, bu yordamda kapsanmayan ek adımların tamamlanmasını gerektirebilir. Ekran görüntülerinde gördüğünüz renkler ve metin de cihazınızda farklı görünebilir.  

1. Yeni veya fabrika ayarlarına sıfırlama cihazınızı açın.  
2. **Hoş Geldiniz** ekranında dili seçin.   QR kodu veya NFC ile kayıt yapmanız istenirse, yöntemiyle eşleşen aşağıdaki adımları izleyin.  
     * 'YE Kuruluşunuzun ağına bağlanmak için bir programcı cihazında NFC ile desteklenen cihazınıza dokunun. Ekrandaki istemleri izleyin. Chrome 'un hizmet koşulları ekranına ulaştığınızda, 5. adıma geçin.  

     * QR kodu: [QR kod kaydı](#qr-code-enrollment)'ndaki adımları doldurun.  

     Başka bir yöntem kullanmanız istenirse adım 3 ' e geçin.    

1. Wi-Fi ' e bağlanın ve **İleri**' ye dokunun. Kayıt yönteminiz ile eşleşen adımı izleyin. 

    * Simgesinde Google oturum açma ekranına geldiğinizde, [belirteç kaydı](#token-enrollment)'ndaki adımları doldurun.    
    * Google sıfırı Touch: Wi-Fi ' a Bağlandıktan sonra cihazınız kuruluşunuz tarafından tanınacaktır. 4\. adıma geçin ve kurulum tamamlanana kadar ekrandaki istemleri izleyin.    
 
       ![Google of Touch kullanıyorsanız gördüğünüz Google terimleri ekranının örnek görüntüsü, & devam et ' i vurgulama düğmesi.](./media/google-zero-touch-intune-app-01.png)   
   
4. Google 'ın şartlarını gözden geçirin. Sonra **&AMP; devam et**' e dokunun.  

      ![Google terms ekranının örnek görüntüsü, kabul & devam et düğmesine vurgu.](./media/fully-managed-intune-app-04.png)   

6. Chrome 'un hizmet koşullarını gözden geçirin. Sonra **&AMP; devam et**' e dokunun.  

   ![Chrome hizmet koşulları ekranının örnek görüntüsü, & devam et düğmesine vurgu.](./media/fully-managed-intune-app-06.png)   

7. Oturum açma ekranlarında iş veya okul hesabınızla oturum açın.   

    a. E-postanızı girin ve **İleri**' ye dokunun.      
    b. Parolanızı girin ve **oturum aç**' a dokunun.  

8. Kuruluşunuzun gereksinimlerine bağlı olarak, ekran kilitleme veya şifreleme gibi ayarları güncelleştirmeniz istenebilir. Bu istemler görürseniz **Ayarla** ' ya dokunun ve ekrandaki yönergeleri izleyin.  

   ![İş telefonunuzu ayarlama ekranınızın örnek görüntüsü, küme oluştur düğmesi.](./media/fully-managed-intune-app-10.png)   

9. Cihazınıza iş uygulamaları yüklemek için, **yükler**' e dokunun. Yükleme tamamlandıktan sonra **İleri**' ye dokunun.  

   ![İş telefonunuzu ayarlama ekranınızın örnek görüntüsü, Install düðmesini vurgulaması.](./media/fully-managed-intune-app-11.png)   

10. Cihazınızın hazırlanabileceği iletiyi aldığınızda **bitti**' ye dokunun. 

11. Uygulamalarınıza gidin ve Microsoft Intune uygulamasını açın. **Oturum aç '** ı seçin. 

12. **Kurulum erişimi** ekranında, bekleyen görevlerin bir listesini görürsünüz. **Devam**' a dokunun.  

       ![Microsoft Intune uygulamasının örnek görüntüsü, erişim ekranını ayarlama, bekleyen görevleri gösterir.](./media/fully-managed-intune-app-14.png)   

13. Cihaz kaydı tamamlandığında **devam**' a dokunun. Microsoft Intune ek cihaz ayarlarını güncelleştirmenizi isteyebilir.   

       ![Microsoft Intune uygulamasının örnek görüntüsü, cihaz ayarları güncelleştirme ekranı.](./media/fully-managed-intune-app-15-2.png)   

14. Listedeki tüm öğeler yeşil bir daire gösterayarlandığında Kurulum tamamlanmıştır. Artık şirket kaynaklarına erişebilirsiniz.  

       ![Microsoft Intune uygulamasının örnek görüntüsü, erişim ekranını ayarlama ve Tamamlanan görevleri gösterme.](./media/fully-managed-intune-app-16.png)   


## <a name="qr-code-enrollment"></a>QR kod kaydı  
Bu bölümde, şirketinizin sağladığı QR kodunuzu taracaksınız.  İşiniz bittiğinde cihaz kayıt adımlarına geri yönlendiriyoruz.     
  
1. **Karşılama** EKRANıNDA, QR kodu kurulumu 'nu başlatmak için ekrana beş kez dokunun.  

   ![Cihaz kurulumu hoş geldiniz ekranının örnek görüntüsü, ekrana dokunarak görüntülenecek yönergeleri vurgular.](./media/qr-code-intune-app-01.png)  

2. Wi-Fi ' a bağlanmak için ekrandaki yönergeleri izleyin.  
3. Cihazınızın bir QR kodu tarayıcısı yoksa, kurulum ekranları bir tarayıcı yüklendiği için ilerlemeyi gösterir. Yüklemenin tamamlanmasını bekleyin.  
4. İstendiğinde, kuruluşunuzun size verdiği kayıt profili QR kodunu tarayın.  
5. [Cihaza kaydet](#enroll-device)'e dönün, kuruluma devam etmek için 4. adımı izleyin.  

## <a name="token-enrollment"></a>Belirteç kaydı  
Bu bölümde, şirketinizin sunduğu belirteci girersiniz. İşiniz bittiğinde cihaz kayıt adımlarına geri yönlendiriyoruz.  

1. Google oturum açma ekranında, **e-posta veya telefon** kutusuna **AFW # kurulum**yazın. **İleri**’ye dokunun. 

   ![Google oturum açma ekranının örnek görüntüsü, "AFW # kurulum" ın alana yazılmış olduğunu gösterir.](./media/token-intune-app-01.png)   

2. **Android cihaz ilkesi** uygulaması için **yüklemeyi** seçin. Yükleme işlemine devam edin. Cihazınıza bağlı olarak, ek koşulları gözden geçirmeniz ve kabul etmeniz gerekebilir.    

3. **Bu cihazı kaydet** ekranında **İleri**' yi seçin.  

   ![Bu cihazı kaydetme ekranının örnek görüntüsü. QR kodunun bir resmini gösterir; Ileri vurgu düğmesi.](./media/token-intune-app-02.png)  

4. **Kodu girin**' i seçin.

   ![Etkin bir QR kodu tarayıcısının örnek ekran görüntüsü. Vurgular kod girin düğmesi.](./media/token-intune-app-03.png)  

5. **Tarama veya kod girme** ekranında, kuruluşunuzun size verdiği kodu yazın.  Ardından **İleri**'ye tıklayın.  

   ![Taramanın örnek görüntüsü veya kod girme, Ileri vurgu düğmesi.](./media/token-intune-app-04.png)  

6. [Cihaza kaydet](#enroll-device)'e dönün, kuruluma devam etmek için 4. adımı izleyin.  



## <a name="next-steps"></a>Sonraki adımlar   
Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  
