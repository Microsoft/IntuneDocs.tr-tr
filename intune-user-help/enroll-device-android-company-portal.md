---
title: Android cihazını Intune Şirket Portalı kaydetme | Microsoft Docs
description: Intune Şirket Portalı bir Android cihazının nasıl kaydedileceğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1670ddf9299d12312f09d188e4410d14ac40fbe7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506326"
---
# <a name="enroll-your-device-with-company-portal"></a>Cihazınızı Şirket Portalı kaydetme  
Şirket e-postasına, uygulamalarına ve verilerine güvenli erişim sağlamak için kişisel veya şirkete ait Android cihazınızı kaydedin. Şirket Portalı, Android 4,4 ve üstünü çalıştıran Samsung KNOX dahil Android cihazlarını destekler.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung KNOX, belirli Samsung cihazlarının, yerel Android 'in sağladığı her yerde ek koruma için kullandığı bir güvenlik türüdür. Samsung KNOX cihazınız olup olmadığını denetlemek için > **ayarlar** > **cihaz hakkında**' ya gidin. Burada listelenen **Knox sürümünü** görmüyorsanız, yerel bir Android cihazınız vardır.

## <a name="enroll-device"></a>Cihazı kaydetme  
[Ücretsiz Intune şirket portalı uygulamasını Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)yüklediğinizden emin olun. 

Kayıt sırasında cihazınızı nasıl kullanacağınızı en iyi açıklayan bir kategori seçmeniz istenebilir. Şirketinizin destek, erişiminiz olan uygulamaları denetlemek için yanıtınızı kullanır.  

1. Şirket Portalı uygulamasını açın.  

3. Şirket Portalı’ndaki **Hoş Geldiniz** ekranında **Oturum aç**’a dokunun ve ardından iş veya okul hesabınızla oturum açın.

   ![Kullanıcıdan gerekli iş veya okul hesabıyla oturum açmasını isteyen Android için Şirket Portalı uygulaması hoş geldiniz ekranı. Microsoft hesapları ve diğer kişisel hesapların kabul edilmediği konusunda da uyarmaktadır.](./media/and-enroll-0-welcome-screen.png)   

4. Kuruluşunuzun hüküm ve koşullarını kabul etmeniz istenirse **kabul et**' e dokunun. Bu ekran aşağıdaki örnek ekran görüntüsünden biraz farklı olabilir. 

   ![android-şirket-portalı-oturum-açma](./media/and-enroll-3-accept-terms.png)

5. İş veya okul hesabınızla parolanızı kullanarak Şirket Portalı uygulamasına oturum açıp **Oturum aç**’a dokunun.

   ![android-şirket-portalı-oturum-açma](./media/and-enroll-2-cp-sign-in.png)

6. **Şirket Erişimi Kurulumu** ekranında, **DEVAM**’a dokunun.

   ![Şirket erişimi kurulum ekranı](/intune/media/android_cp_enroll_01_1709_new.png)

   > [!NOTE]
   > Sarı üçgenler herhangi bir hata olduğu anlamına gelmez. Bu simgeler, kayıt işleminde hala tamamlanması gereken adımlar olduğunu gösterir.

7. Şirketinizin destek biriminin cihazınızda neleri görüp göremeyeceğini içeren listeyi gözden geçirin ve ardından **DEVAM**’a dokunun.

   ![Gizlilik ayarları](/intune/media/android_cp_enroll_02_after_1710.png)

8. **Sırada ne var?** ekranında, kayıt sırasında ne olduğunu okuyun ve **KAYDET**’e dokunun.

   ![Sıradaki ekranı](/intune/media/android_cp_enroll_03_after_1710.png)

9. Android 6.0 veya üzeri kullanıyorsanız, bu adımı uygulayın. Aksi halde, sonraki adıma geçin.

   Şirketinizin destek birimi belirli ilkeler ayarladıysa, aşağıdaki iletileri görebilirsiniz:
   - **Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?**

     ![android-şirket-portalı-oturum-açma](./media/and-enroll-3a-allow-phone-access.png)

   Bu iletiyi görürseniz, **İZİN VER**’e dokunun. İZİN VER’e dokunmak güvenlidir, çünkü **Microsoft hiçbir zaman telefon çağrısı yapmaz veya telefon çağrılarınızı yönetmez**! İleti metni Google’ın kontrolündedir ve Microsoft bunu değiştiremez. Erişime izin verdiğinizde, tüm yaptığınız cihazınızın uluslararası mobil cihaz kodunu (IMEI) Intune'a göndermesine izin vermektir. IMEI, seri numarası gibi, bir mobil cihazı benzersiz şekilde tanımlayan bir numaradır.

   Erişimi reddederseniz, Şirket Portalı bir sonraki oturum açışınızda ileti tekrar görünür. Gelecek iletileri kapatmak için **hiçbir zaman sorma**' yı seçin. Erişim iznini tersine çevirmek için **ayarlar** > **uygulamalar** > **Şirket Portalı** > **Telefon** **@no__t ve**sonra izni açın.  

   - **Şirket Portalı’nın, kişilerinize erişmesine izin verilsin mi?**

     ![android-şirket-portalı-oturum-açma](./media/and-enroll-3b-allow-contacts-access.png)

     Bu iletiyi görürseniz, **İZİN VER**’e dokunun. İZİN VER’e dokunmak güvenlidir, çünkü **Microsoft kişilerinize hiçbir zaman erişmez!** İleti metni Google’ın kontrolündedir ve Microsoft bunu değiştiremez. Erişim izni verdiğinizde Şirket Portalı uygulamasının yalnızca iş hesabınızı oluşturmasına, kullanmasına ve yönetmesine izin verilir.

     Erişimi reddederseniz Şirket Portalı’nda oturum açtığınız sonraki durumda ileti yeniden görünür, ancak **Bir daha sorma** kutusuna dokunarak gelecekteki iletileri kapatabilirsiniz. Daha sonra erişime izin vermeye karar verirseniz, **Ayarlar** &gt; **Uygulamalar** &gt; **Şirket Portalı** &gt; **İzinler** &gt; **Telefon** giderek izni açın.

10. **Cihaz yöneticisini etkinleştir** ekranında **Etkinleştir**’e dokunun.

    ![Cihaz yöneticisini etkinleştirin ekranı](./media/and-enroll-5-activate.png)

    Cihaz yöneticisi rolü, Şirket Portalı’na cihazınızı yönetmesi için gereken roldür. Yöneticinizin bazı öğeleri (ekranınızın kilidini açmayı kaç kez denediğiniz gibi) görmesine ve bazı önlemler almasına olanak tanır.    

    Bu ileti Microsoft’un denetiminde değildir ve iletide kullanılan ifadenin biraz sert göründüğünün farkındayız. Şirket Portalı’nın yalnızca kuruluşunuzla ilgili olan kısıtlamaları ve erişimi göstermesinin bir yolu yoktur. Bunların tümü, bu ekranda aynı anda verilir. Kendi kuruluşunuzun kullanımına özgü sorularınız varsa, daha fazla bilgi edinmek için [Şirket Portalı web sitesindeki](https://go.microsoft.com/fwlink/?linkid=2010980) iletişim bilgilerini kullanarak şirketinizin destek birimiyle bağlantı kurun.  

11. Yönergeleri izleyerek PIN’i veya parolayı girin. Bu cihazda zaten bir PIN veya parola ayarladıysanız, bu ekranı görmezsiniz ya da yeni bir PIN veya parola girmeniz gerekmez.  

    ![PIN veya parola girin](./media/and-enroll-6-PIN-native.png)

12. Bir Samsung Knox cihazı kullanıyorsanız **Onayla**’ya dokunduğunuzda cihazınızın kaydedildiğini belirten bir ileti görürsünüz. Yerel bir Android cihaz kullanıyorsanız cihazınızın kaydedildiğini gösteren alttaki ekranı fark etmeniz yeterlidir.

    ![Samsung Knox gizlilik ilkesi](./media/and-enroll-7-knox-privacy-policy.png)

    Bu ekran, cihazınızın kaydedilmekte olduğunu gösterir.

    ![Cihazı kaydetme ekranı](./media/and-enroll-8-device-enrolling.png)

13. **Şirket Erişimi Kurulumu** ekranı görüntülendiğinde **DEVAM**’a dokunun. Cihazınızın uyumsuz olduğunu belirten bir ileti görürseniz sorunu düzeltmek için yönergeleri izleyin ve sonra **DEVAM**’a dokunun.

    ![Cihaz uyumlu değil ancak kaydedildi](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Çözümlenmesi gereken cihaz uyumluluk sorunlarını göründü](/intune/media/android_cp_enroll_03_post_1709.png)

    Sorunlara dokunarak bunlar hakkında daha fazla bilgi edinebilirsiniz.

    ![Cihaz uyumluluk sorunları genişletildi](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Şirket erişimi kurulum ekranı](./media/and-enroll-9d-comp-access-setup.png)  

14. **Şirket Erişimi Kurulumu tamamlandı** ekranında **BİTTİ**’ye dokunun. Cihazınız artık kaydedilmiştir.

    ![Şirket erişimi kurulumu tamamlandı ekranı](./media/and-enroll-10-comp-access-setup-complete.png)

## <a name="next-steps"></a>Sonraki adımlar  

Şirket uygulamalarını yüklemeyi denemeden önce **ayarlar** > **güvenlik**' e gidin ve **Bilinmeyen kaynaklar**' ı açın. Uygulamaları yüklemeyi denemeden önce bu seçeneği açmazsanız "Yükleme engellendi. Güvenlik nedeniyle cihazınız bilinmeyen kaynaklardan gelen uygulamaların yüklenmesini engelleyecek şekilde ayarlanmış." iletisini görürsünüz. Hata iletişim kutusunda **Ayarlar** öğesine dokunarak **Bilinmeyen kaynaklar** seçeneğine gidin.  

> [!Note]
> Kuruluşunuzda telekomünikasyon gider yönetimi yazılımı kullanılıyorsa, cihazınız tam olarak kaydedilmeden önce tamamlamanız gereken ek birkaç adım vardır. Daha fazla bilgiyi [burada](enroll-your-device-with-telecom-expense-management-android.md) bulabilirsiniz.

Cihazınızı Intune 'a kaydetmeyi denerken bir hata alırsanız, [şirketinizin destek 'e e-posta](send-logs-to-your-it-admin-by-email-android.md)gönderebilirsiniz.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.
