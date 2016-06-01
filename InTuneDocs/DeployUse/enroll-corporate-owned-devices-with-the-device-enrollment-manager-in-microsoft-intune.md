---
# required metadata

title: Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme
Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir.  *Cihaz kayıt yöneticisi* hesabı, beşten fazla cihazı kaydetme izni olan özel bir Intune hesabıdır. Örneğin bir mağaza yöneticisi veya süpervizöre bir cihaz kayıt yöneticisi kullanıcı hesabını atayarak aşağıdakileri yapmasına imkan sağlayabilirsiniz:

-   Intune'a cihaz kaydetme

-   Şirket uygulamalarına erişmek için şirket portalında oturum açma

-   Yazılım yükleme ve kaldırma

-   Şirket verilerine erişimi yapılandırma

Cihaz yöneticisi hesabını yalnızca e-posta almayacak veya belirli bir kullanıcı olarak oturum açmayacak cihazlar için kullanın. Bir cihaz yöneticisi tarafından yönetilen cihazlar, bunlar da kullanıcı başına senaryolar olduğundan koşullu erişimle yapılandırılamaz. Mağaza yöneticisi cihazı şirket portalından sıfırlayamaz.

Cihaz kayıt yöneticisi senaryo örnekleri: Bir restoran, garsonlar için satış noktası tabletleri, mutfak çalışanları içinse sipariş izleyiciler istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya bir kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi bir cihaz kayıt yöneticisi hesabı oluşturur ve bu hesabı kullanarak şirkete ait cihazları kaydeder.

Alternatif olarak, yönetici cihaz kayıt yöneticisi kimlik bilgilerini restoran müdürüne verip cihazları müdürün kaydetmesine ve yönetmesine imkan sağlayabilir. Yönetici veya müdür, restoran cihazlarına role özel uygulamalar dağıtabilir.

> [!NOTE]
> Yönetici ayrıca Intune konsolunda cihazı seçebilir ve yönetim konsolu ile mobil cihaz yönetiminden devre dışı bırakabilir. 20’den fazla cihazın kayıtlı olduğu cihaz kayıt yöneticisi kullanıcı hesapları Şirket Portalı uygulamasını kullanmayla ilgili sorun yaşayabilir.

## Şirket uygulamalarını cihaz kayıt yöneticisiyle yönetilen cihazlara dağıtmak için Şirket Portalı uygulamasını **Gerekli Yükleme** olarak cihaz kayıt yöneticisinin kullanıcı hesabına dağıtın.
Cihaz kayıt yöneticisi hesapları oluşturma Cihaz kayıt yöneticisi hesapları, şirkete ait çok sayıda cihazı kaydetme izni olan kullanıcı hesaplarıdır.

#### Yalnızca Intune konsolundaki kullanıcılar cihaz kayıt yöneticileri olabilir.

1.  Intune'a cihaz kayıt yöneticisi ekleme

2.  [Microsoft Intune hesap portalına](http://go.microsoft.com/fwlink/?LinkId=698854) gidin ve yönetici hesabınızda oturum açın.

3.  **Kullanıcı ekle**’ye tıklayın Bir cihaz kayıt yöneticisi olacak kullanıcı hesabının listelendiğini onaylayın. Aksi durumda, **Yeni** 'ye tıklayıp ve Kullanıcı ekle işlemlerini tamamlayarak kullanıcıyı ekleyin. Hizmet'e erişen her bir kullanıcı için bir abonelik lisansı gereklidir ve *cihaz kayıt yöneticisi* bir Intune yöneticisi olamaz.

4.  Bu özelliği kullanmadan önce daha fazla lisans eklemenizin gerekli olup olmadığını belirleyin.

5.   [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) yönetici hesabınızla oturum açın. Gezinti bölmesinde **Yönetici**'ye tıklayın, **Yönetici Yönetimi** 'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin.

6.  Cihaz Kayıt Yöneticileri sayfası açılır.  **Ekle...**seçeneğine tıklayın.

7.   **Cihaz Kayıt Yöneticisi Ekle** iletişim kutusu açılır. Intune hesabının **Kullanıcı Kimliği** 'ni girin ve ardından **Tamam**'a tıklayın.

8.  Cihaz kayıt yöneticisi olan kullanıcı Intune yöneticisi olamaz.

## Cihaz kayıt yöneticisi artık şirket portalında BYOD senaryosu için son kullanıcıların kendi cihazlarını kaydetmek için kullandığı yordamın aynısını kullanarak mobil cihazları kaydedebilirsiniz.

1.  Delete a device enrollment manager from Intune

2.  [Microsoft Intune yönetici portalında](http://manage.microsoft.com) yönetici hesabınızla oturum açın. Gezinti bölmesinde **Yönetici** 'ye tıklayın, **Yönetici Yönetimi** 'ne gidin ve **Cihaz Kayıt Yöneticisi**'ni seçin.

3.  Cihaz Kayıt Yöneticileri sayfası açılır. Silmek istediğiniz cihaz kayıt yöneticisi **Kullanıcı** 'yı silin ve ardından **Sil**'e tıklayın. Bu kullanıcı Intune'dan silinmez ve bu kullanıcının yönettiği cihazlar Intune'da kayıtlı kalır.

4.  Bir cihaz kayıt yöneticisini silme, bu kullanıcının Intune'a daha fazla cihaz kaydetmesini engeller.

Cihaz kayıt yöneticisini silmek istediğinizi onaylamak için **Evet** 'e tıklayın. Bir cihaz kayıt yöneticisinin silinmesi, kaydedilen cihazları etkilemez.

-   Bir cihaz kayıt yöneticisi silindiğinde:

-   Kaydedilen hiçbir cihaz etkilenmez

-   Kaydedilen cihazlar tam olarak yönetilmeye devam eder.

-   Silinen cihaz kayıt yöneticisinin kimlik bilgileri, şirket portalında oturum açıp uygulama erişmek için geçerli kalır

-   Silinen cihaz kayıt yöneticisi hesabının kimlik bilgileri yine cihazları temizleyemez veya kullanımdan kaldıramaz


<!--HONumber=May16_HO2-->


