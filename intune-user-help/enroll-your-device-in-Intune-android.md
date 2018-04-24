---
title: Android cihazınızı Intune’a kaydetme | Microsoft Docs
description: Android cihazının Intune’a nasıl kaydedildiği açıklanır
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7230f14ae9481555f457a8a8700d588c4170b39b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-your-android-device-in-intune"></a>Android cihazınızı Intune’a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için Android cihazlarınızı kaydedebilirsiniz. Cihazlarınızı kaydettiğinizde, BT departmanınız bu iş veya okul kaynaklarını yönetebilir, bunların güvenli kalmasını sağlayabilir ve size işlerinizi tamamlamak için tercih ettiğiniz cihazı kullanma özgürlüğünü tanıyabilir. Kayıt hakkında daha fazla bilgi edinmek için, bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

Bu kayıt yönergeleri, yerel ve Samsung Knox Android cihazlarına yöneliktir. Samsung Knox, bazı Samsung cihazlarının yerel Android tarafından sağlanan korumanın dışında ek koruma sağlamak için kullandığı bir güvenlik türüdür. Samsung Knox cihazınız olup olmadığını denetlemek için **Ayarlar** > **Telefon hakkında** kısmına gidin. Bu listede "Knox sürümü" ifadesini görmüyorsanız yerel bir Android cihazına sahipsinizdir.

Kaydetme öncesinde veya sonrasında cihazı nasıl kullandığınızı en iyi şekilde açıklayan bir kategoriyi seçmeniz istenebilir. Şirketinizin destek birimi, erişiminiz olan uygulamaları denetlemek için bu kategoriyi kullanır.

**Android cihazınızı kaydetmek için:**

1. [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)’den ücretsiz Intune Şirket Portalı uygulamasını yükleyin.

2. Şirket Portalı uygulamasını açın.

3. Şirket Portalı’ndaki **Hoş Geldiniz** ekranında **Oturum aç**’a dokunun ve ardından iş veya okul hesabınızla oturum açın.

   ![Kullanıcıdan gerekli iş veya okul hesabıyla oturum açmasını isteyen Android için Şirket Portalı uygulaması hoş geldiniz ekranı. Microsoft hesapları ve diğer kişisel hesapların kabul edilmediği konusunda da uyarmaktadır.](./media/and-enroll-0-welcome-screen.png)   

4. Şirketinizin destek birimi şirket hüküm ve koşulları ayarladıysa, koşulları kabul etmek için **KABUL ET**’e dokunun. Kullanmakta olduğunuz Android sürümüne bağlı olarak bu ekran aşağıdaki görüntüden biraz farklı olabilir.

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

   Erişimi reddederseniz Şirket Portalı’nda oturum açtığınız sonraki durumda ileti yeniden görünür, ancak **Bir daha sorma** kutusuna dokunarak gelecekteki iletileri kapatabilirsiniz. Daha sonra erişime izin vermeye karar verirseniz, **Ayarlar** &gt; **Uygulamalar** &gt; **Şirket Portalı** &gt; **İzinler** &gt; **Telefon** giderek izni açın.

   - **Şirket Portalı’nın, kişilerinize erişmesine izin verilsin mi?**

     ![android-şirket-portalı-oturum-açma](./media/and-enroll-3b-allow-contacts-access.png)

     Bu iletiyi görürseniz, **İZİN VER**’e dokunun. İZİN VER’e dokunmak güvenlidir, çünkü **Microsoft kişilerinize hiçbir zaman erişmez!** İleti metni Google’ın kontrolündedir ve Microsoft bunu değiştiremez. Erişim izni verdiğinizde Şirket Portalı uygulamasının yalnızca iş hesabınızı oluşturmasına, kullanmasına ve yönetmesine izin verilir.

     Erişimi reddederseniz Şirket Portalı’nda oturum açtığınız sonraki durumda ileti yeniden görünür, ancak **Bir daha sorma** kutusuna dokunarak gelecekteki iletileri kapatabilirsiniz. Daha sonra erişime izin vermeye karar verirseniz, **Ayarlar** &gt; **Uygulamalar** &gt; **Şirket Portalı** &gt; **İzinler** &gt; **Telefon** giderek izni açın.

10. **Cihaz yöneticisini etkinleştir** ekranında **Etkinleştir**’e dokunun.

    ![Cihaz yöneticisini etkinleştirin ekranı](./media/and-enroll-5-activate.png)

    Cihaz yöneticisi rolü, Şirket Portalı’na cihazınızı yönetmesi için gereken roldür. Yöneticinizin bazı öğeleri (ekranınızın kilidini açmayı kaç kez denediğiniz gibi) görmesine ve bazı önlemler almasına olanak tanır.

    Anımsanması gereken önemli nokta, bunların güvenlik adına alınan önlemler olduğudur. Şirketinizin destek birimi gizliliğinizi ihlal etmeye ve hiç nedensiz bilgilerinizi silmeye çalışmaz; ancak şirket verilerinin güvenlik altında olduğundan emin olmak ister.

    Bu ileti Microsoft’un denetiminde değildir ve iletide kullanılan ifadenin biraz sert göründüğünün farkındayız. Şirket Portalı’nın yalnızca kuruluşunuzla ilgili olan kısıtlamaları ve erişimi göstermesinin bir yolu yoktur. Bunların tümü, bu ekranda aynı anda verilir. Kendi kuruluşunuzun kullanımına özgü sorularınız varsa, daha fazla bilgi edinmek için [Şirket Portalı web sitesindeki](https://portal.manage.microsoft.com#HelpDeskDialog) iletişim bilgilerini kullanarak şirketinizin destek birimiyle bağlantı kurun.

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

Şirket uygulamalarını yüklemeyi denemeden önce **Ayarlar** &gt; **Güvenlik**’e gidin ve **Bilinmeyen kaynaklar** seçeneğini açın. Uygulamaları yüklemeyi denemeden önce bu seçeneği açmazsanız "Yükleme engellendi. Güvenlik nedeniyle cihazınız bilinmeyen kaynaklardan gelen uygulamaların yüklenmesini engelleyecek şekilde ayarlanmış." iletisini görürsünüz. Hata iletişim kutusunda **Ayarlar** öğesine dokunarak **Bilinmeyen kaynaklar** seçeneğine gidin.

> [!Note]
> Kuruluşunuzda telekomünikasyon gider yönetimi yazılımı kullanılıyorsa, cihazınız tam olarak kaydedilmeden önce tamamlamanız gereken ek birkaç adım vardır. Daha fazla bilgiyi [burada](enroll-your-device-with-telecom-expense-management-android.md) bulabilirsiniz.

Cihazınızı Intune’a kaydetmeye çalışırken bir hata alırsanız [şirketinizin destek birimine kayıt hataları gönderebilirsiniz](send-enrollment-errors-to-your-it-admin-android.md).

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.
