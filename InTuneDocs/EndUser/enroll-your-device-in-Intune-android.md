---
# required metadata

title: Android cihazınızı Intune’a kaydetme | Microsoft Itune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Android cihazınızı Intune’a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için Android cihazlarınızı kaydedebilirsiniz. Cihazlarınızı kaydetme, BT departmanınızın bu iş veya okul kaynaklarını yönetmenize ve bunları güvenli halde tutmanıza olanak tanırken, işlerinizi için tamamlamak için, tercih ettiğiniz cihazı kullanma özgürlüğünü sağlar. Kayıt hakkında daha fazla bilgi edinmek için, bkz. [Şirket Portalı uygulamasını yüklediğimde ve cihazımı kaydettiğimde ne olur?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)

Bu kayıt yönergeleri, Samsung Knox Android cihazlar ve "yerel" (Samsung Knox harici) Android cihazları içindir. Cihazınızın Samsung Knox olup olmadığını belirlemek için **Ayarlar** &gt; **Telefon hakkında** seçeneğine gidin. Burada "Knox" kelimesinin listelendiğini görmüyorsanız, yerel bir Android cihazına sahipsinizdir.

Kaydetme öncesinde veya sonrasında cihazı nasıl kullandığınızı en iyi şekilde açıklayan bir kategoriyi seçmeniz istenebilir. BT yöneticiniz hangi uygulamalara erişiminiz olduğunu belirlemeye yardımcı olmak üzere bu kategoriyi kullanır.

Cihazınızı Intune’a kaydetmeye çalışırken bir hata alırsanız [BT yöneticinize kayıt hataları gönderebilirsiniz](send-enrollment-errors-to-your-it-administrator-android.md)

**Android cihazınızı kaydetme**

1.  [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)’den ücretsiz Intune Şirket Portalı uygulamasını yükleyin

2.  Microsoft Intune Şirket Portalı uygulamasını açın.

3.  Şirket Portalı’ndaki **Hoş Geldiniz** ekranında **Oturum aç**’a dokunun ve ardından iş veya okul hesabınızla oturum açın.

    ![android-şirket-portalı-oturum-açma](./media/and-enroll-0-welcome-screen.png)   

4.  BT yöneticiniz şirket hüküm ve koşullarını ayarladıysa, koşulları kabul etmek için **KABUL ET**’e dokunun.

    ![android-şirket-portalı-oturum-açma](./media/and-enroll-3-accept-terms.png)

5.  Android 6.0 veya üzeri kullanıyorsanız, bu adımı uygulayın. Aksi halde, sonraki adıma geçin. 

    BT yöneticiniz belirli ilkeleri ayarladıysa, aşağıdaki iletileri görebilirsiniz:
    -   **Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?**

    ![android-şirket-portalı-oturum-açma](./media/and-enroll-3a-allow-phone-access.png)

    Bu iletiyi görürseniz, **İZİN VER**’e dokunun. **Microsoft hiçbir zaman telefon çağrısı yapmadığından veya telefon çağrılarınızı yönetmediğinden** İZİN VER’e dokunmak güvenlidir! İleti metni Google’ın kontrolündedir ve Microsoft bunu değiştiremez. Erişim izni verdiğinizde tüm yaptığınız, cihazınıza cihaz SD kartına veri günlüklerini yazma izni vermektir, bu da akabinde bu günlükleri bir USB kablosu kullanarak taşımanıza olanak tanır. Şirket Portalı uygulamasını kullanırken bir sorun yaşadığınızda BT yöneticinize günlükler göndermek için bu özelliği kullanmanız gerekebilir. [BT yöneticinize kayıt hataları göndermeyi](send-enrollment-errors-to-your-it-administrator-android.md) öğrenin

    Erişimi reddederseniz Şirket Portalı’nda oturum açtığınız sonraki durumda ileti yeniden görünür, ancak **Bir daha sorma** onay kutusuna dokunarak gelecekteki iletileri kapatabilirsiniz.  Daha sonra erişime izin vermeye karar verirseniz **Ayarlar** &gt; **Uygulamalar** &gt; **Şirket Portalı** &gt; **İzinler** &gt; **Telefon**’a gidin ve izni etkinleştirin.

    -   **Şirket Portalı’nın, kişilerinize erişmesine izin verilsin mi?**

    ![android-şirket-portalı-oturum-açma](./media/and-enroll-3b-allow-contacts-access.png)

    Bu iletiyi görürseniz, **İZİN VER**’e dokunun. **Microsoft hiçbir zaman kişilerinize erişmediğinden** İZİN VER’e dokunmak güvenlidir! İleti metni Google’ın kontrolündedir ve Microsoft bunu değiştiremez. Erişime izin verdiğinizde yalnızca, Şirket Portalı uygulamasının, cihazla ilgili sorunları gidermeye yardımcı olmak üzere veri günlüklerine erişmesine izin verilir.

    Erişimi reddederseniz, **Veri Gönder** öğesine dokunduğunuz sonraki durumda ileti yeniden görünür, ancak **Bir daha sorma** onay kutusuna dokunarak gelecekteki iletileri kapatabilirsiniz. Daha sonra erişime izin vermeye karar verirseniz **Ayarlar** &gt; **Uygulamalar** &gt; **Şirket Portalı** &gt; **İzinler** &gt; **Depolama**’ya gidin ve izni etkinleştirin.

6.  İş veya okul hesabınızla parolanızı kullanarak Şirket Portalı uygulamasına oturum açın ve **Oturum aç**’a dokunun

    ![android-şirket-portalı-oturum-açma](./media/and-enroll-2-cp-sign-in.png)

7.  **Şirket Erişimi Kurulumu** ekranında **BAŞLA**’ya dokunun

    ![Şirket erişimi kurulum ekranı](./media/and-enroll-4a-comp-access-setup.png)

8.  **Cihazınızı neden kaydetmelisiniz?** ekranında, cihazınızı kaydettiğinizde neler yapabileceğinizi okuyun ve sonra **DEVAM**’a dokunun

    ![Cihazınız neden kaydetmelisiniz ekranı](./media/and-enroll-4b-why-enroll.png)

9.  BT yöneticinizin cihazınızda neleri görebileceğini ve neleri göremeyeceğini içeren listeyi gözden geçirin ve **DEVAM**’a dokunun

    ![Gizlilik ayarları](./media/and-enroll-4c-we-care-privacy.png)

10.  **Sıradaki** ekranında, kayıt sırasında ne olduğunu okuyun ve **KAYDET**’e dokunun

    ![Sıradaki ekranı](./media/and-enroll-4d-what-comes-next.png)

11.  **Cihaz yöneticisini etkinleştirin** ekranında **Etkinleştir**’e dokunun

    ![Cihaz yöneticisini etkinleştirin ekranı](./media/and-enroll-5-activate.png)

12.  Yönergeleri izleyerek PIN’i veya parolayı girin. Bu cihazda zaten bir PIN veya parola ayarladıysanız, bu ekranı görmezsiniz ya da yeni bir PIN veya parola girmeniz gerekmez.

    ![PIN veya parola girin](./media/and-enroll-6-PIN-native.png)

13.  Aşağıda, kullanmakta olduğunuz cihaz türüyle eşleşen yönergeleri izleyin (yerel Android veya Samsung Knox) Cihazınızın Samsung Knox olup olmadığını belirlemek için **Ayarlar** &gt; **Telefon hakkında** seçeneğine gidin. Burada "Knox" kelimesinin listelendiğini görmüyorsanız, yerel bir Android cihazına sahipsinizdir.

    -   Yerel (Samsung Knox harici) cihaz: **Sertifikayı adlandır** ekranında **Tamam**’a dokunarak varsayılan sertifikayı kabul edin.

    ![Sertifikayı adlandır ekranı](./media/and-enroll-7-cert-native.png)

    -   Samsung Knox cihazı: Gizlilik ilkesini kabul edin ve **ONAYLA**’ya dokunun

    ![Samsung KNOX gizlilik ilkesi](./media/and-enroll-7-knox-privacy-policy.png)

    Intune cihazınızı kaydederken, ekranınızda aşağıdaki iletiyi görürsünüz.

    ![Cihazı kaydetme ekranı](./media/and-enroll-8-device-enrolling.png)

14. **Şirket Erişimi Kurulumu** ekranı görüntülendiğinde **DEVAM**’a dokunun. Cihazınızın uyumsuz olduğunu belirten bir ileti görürseniz sorunu düzeltmek için yönergeleri izleyin ve sonra **DEVAM**’a dokunun

    ![Şirket erişimi kurulum ekranı](./media/and-enroll-9-comp-access-setup.png)  

11. **Şirket Erişimi Kurulumu tamamlandı** ekranında **BİTTİ**’ye dokunun. Cihazınız artık kaydedilmiştir.

    ![Şirket erişimi kurulumu tamamlandı ekranı](./media/and-enroll-10-comp-access-setup-complete.png)

Şirket uygulamalarını yüklemeyi denemeden önce, **Ayarlar** &gt; **Güvenlik**‘e gidin ve **Bilinmeyen kaynaklar** seçeneğini açın. Uygulamaları yüklemeyi denemeden önce bu seçeneği açmazsanız "Yükleme engellendi. Güvenlik nedeniyle telefonunuz bilinmeyen kaynaklardan gelen uygulamaların yüklenmesini engelleyecek şekilde ayarlanmış." iletisini görürsünüz. Hata iletişim kutusunda **Ayarlar** öğesine dokunarak **Bilinmeyen kaynaklar** seçeneğine gidin.


### Ayrıca bkz.
[Android cihazınızı Intune ile kullanma](using-your-android-device-with-intune.md)


<!--HONumber=May16_HO2-->

