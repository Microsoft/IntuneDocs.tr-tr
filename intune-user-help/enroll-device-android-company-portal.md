---
title: Android cihazını Intune Şirket Portalı kaydetme | Microsoft Docs
description: Intune Şirket Portalı bir Android cihazının nasıl kaydedileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: e0a2297509d6077d6508adaab96ae6eb3cf9b28f
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856743"
---
# <a name="enroll-your-device-with-company-portal"></a>Cihazınızı Şirket Portalı kaydetme  
Şirket e-postasına, uygulamalarına ve verilerine güvenli erişim sağlamak için kişisel veya şirkete ait Android cihazınızı kaydedin. Şirket Portalı, Android 4,4 ve üstünü çalıştıran Samsung KNOX dahil Android cihazlarını destekler.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung KNOX, belirli Samsung cihazlarının, yerel Android 'in sağladığı her yerde ek koruma için kullandığı bir güvenlik türüdür. Samsung KNOX cihazınız olup olmadığını denetlemek için > **ayarlar** > **cihaz hakkında**bölümüne gidin. Burada listelenen **Knox sürümünü** görmüyorsanız, yerel bir Android cihazınız vardır.

## <a name="enroll-device"></a>Cihaz kaydetme  
[Ücretsiz Intune şirket portalı uygulamasını Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)yüklediğinizden emin olun. 

Kayıt sırasında cihazınızı nasıl kullanacağınızı en iyi açıklayan bir kategori seçmeniz istenebilir. Şirketinizin destek, erişiminiz olan uygulamaları denetlemek için yanıtınızı kullanır.  

1. Şirket Portalı’nı açın ve iş veya okul hesabınızla oturum açın.  

2. Kuruluşunuzun hüküm ve koşullarını kabul etmeniz istenirse **tümünü kabul et**' e dokunun.  

   ![Şirket Portalı, terimler ekranının örnek görüntüsü, "tümünü kabul et" düğmesinin vurgulanması.](./media/accept-terms-1911.png)  


3. Kuruluşunuzun neleri görebileceğini ve neleri görebileceklerini inceleyin. Sonra **devam**' a dokunun.


    ![Örnek görüntü Şirket Portalı, gizlilik ekranınızı, devam düğmesini vurguladık.](./media/android-privacy-screen-1911.png)  
4. Yaklaşan adımlarda nelerin beklendiğini gözden geçirin. Sonra **İleri**' ye dokunun.  

    ![Şirket Portalı örnek görüntüsü, ileri bir sonraki düğme vurgulandığında.](./media/android-whats-next-1911.png)  


5. Android sürümünüze bağlı olarak, cihazınızın belirli bölümlerine erişime izin vermeniz istenebilir. Bu istemler, Google için gereklidir ve Microsoft tarafından denetlenmez.  

    Aşağıdaki izinler için **Izin ver** ' e dokunun:  
    * **Şirket portalı telefon araması yapmasına ve yönetmesine Izin ver**: Bu izin, cihazınızın, kuruluşunuzun cihaz yönetim sağlayıcısı olan uluslararası mobil istasyon ekipman KIMLIĞI (IMEI) numarasını Intune ile paylaşmasını sağlar. Bu izne izin vermek güvenlidir. Microsoft hiçbir şekilde telefon araması yapmayacaktır veya yönetmez.  
    * **Şirket portalı kişilerinize erişmesine Izin ver**: Bu izin, Şirket portalı uygulamanın iş hesabınızı oluşturmasına, kullanmasına ve yönetmesine olanak tanır.  Bu izne izin vermek güvenlidir. Microsoft, kişilerinize hiçbir şekilde erişemez. 

    İzni reddederseniz, Şirket Portalı için bir sonraki oturum açışınızda yeniden girmeniz istenir. Bu iletileri kapatmak için, **tekrar sorma**' yı seçin. Uygulama izinlerini yönetmek için, ayarlar uygulama > **uygulamalar** > **Şirket Portalı** > **izinleri** > **Telefon**' e gidin.  

6. Cihaz yönetici uygulamasını etkinleştirin. 

    Şirket Portalı cihazınızı güvenli bir şekilde yönetmek için Cihaz Yöneticisi izinlerine sahip olması gerekir. Uygulamanın etkinleştirilmesi, kuruluşunuzun cihazın kilidini açma girişimi ve uygun şekilde yanıt verme girişimleri gibi olası güvenlik sorunları tanımlamasına olanak sağlar.  

    ![Etkin cihaz Yöneticisini Etkinleştir ekranının örnek görüntüsü, Etkinleştir düğmesini vurgular.](./media/activate-device-administrator-1911.png)  

> [!NOTE]
> Microsoft bu ekranda mesajlaşmayı denetlemez. Bulduklarını biraz daha iyi görünebilir. Şirket Portalı, kuruluşunuza uygun olan kısıtlamaları ve erişimi belirtemez. Kuruluşunuzun uygulamayı nasıl kullandığı hakkında sorularınız varsa BT destek sorumlunuza başvurun. Kuruluşunuzun iletişim bilgilerini bulmak için [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) gidin.  


7. Cihazınız kaydetmeye başlıyor. Samsung KNOX cihazı kullanıyorsanız, önce ağaç Aracısı gizlilik ilkesini gözden geçirmeniz ve onaylaması istenir.   

    ![Kayıt sırasında görüntülenen Samsung KNOX Gizlilik ilkesi ekranının örnek resmi.](./media/and-enroll-7-knox-privacy-policy.png)  

8. **Şirket erişimi kurulumu** ekranında, cihazınızın kayıtlı olduğundan emin olun. Sonra **devam**' a dokunun.  

    ![Şirket Portalı, şirket erişimi kurulumu ekranının örnek görüntüsü, cihazın yönetilip yönetilme işleminin tamamlandığını gösterir.](./media/update-settings-1911.png)  

9. Kuruluşunuz, cihaz ayarlarınızı güncelleştirmenizi gerektirebilir. Bir ayarı ayarlamak için **Çöz** ' e dokunun. Ayarları güncelleştirmeyi tamamladığınızda **devam**' a dokunun.  

   ![Şirket Portalı örnek görüntüsü, cihaz ayarlarını güncelleştirme, Çözümle ve devam etme düğmelerini vurgulama.](./media/resolve-settings-1911.png)  

10. Kurulum tamamlandığında **bitti**' ye dokunun.    

    ![Şirket Portalı, şirket erişimi kurulumu ekranının örnek görüntüsü, tamamlanan kurulum ve vurgulama bitti düğmesini gösterir.](./media/android-enrollment-done-1911.png) 

## <a name="next-steps"></a>Sonraki adımlar  

Okul veya iş uygulamasını yüklemeyi denemeden önce **ayarlar** > **güvenlik**' e gidin ve **Bilinmeyen kaynaklar**' ı açın. Bu seçeneği kullanmazsanız, bir uygulamayı yüklemeye çalıştığınızda şu iletiyi görürsünüz: "Install engellendi. Güvenlik nedeniyle cihazınız bilinmeyen kaynaklardan gelen uygulamaların yüklenmesini engelleyecek şekilde ayarlanmış." iletisini görürsünüz. Doğrudan **Bilinmeyen kaynaklara**gitmek Için iletideki **ayarlara** dokunabilirsiniz.  

> [!Note]
> Kuruluşunuzda telekomünikasyon gider yönetimi yazılımı kullanılıyorsa, cihazınız tam olarak kaydedilmeden önce tamamlamanız gereken ek birkaç adım vardır. Daha fazla bilgiyi [burada](enroll-your-device-with-telecom-expense-management-android.md) bulabilirsiniz.

Cihazınızı Intune 'a kaydetmeyi denerken bir hata alırsanız, [şirketinizin destek 'e e-posta](send-logs-to-your-it-admin-by-email-android.md)gönderebilirsiniz.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  