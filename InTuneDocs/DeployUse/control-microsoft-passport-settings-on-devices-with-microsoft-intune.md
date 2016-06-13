---
# required metadata

title: Cihazlarda Microsoft Passport ayarlarını denetleme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile cihazlarda Microsoft Passport ayarlarını denetleme
Microsoft Intune bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Active Directory veya bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemi olan **İş için Microsoft Passport** ile tümleştirmenize olanak sağlar.

Passport oturum açmak için parola yerine **kullanıcı hareketi** kullanmanıza imkan tanır. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

Intune, İş için Passport ile iki şekilde tümleştirilir:

-   Kullanıcıların oturum açarken hangi hareketleri kullanabileceğini ve kullanamayacağını denetlemek için Intune ilkesini kullanabilirsiniz.

-   Kimlik doğrulama sertifikalarını İş için Passport anahtar depolama sağlayıcısına (KSP) depolayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).

## İş için Passport ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows** &gt; **İş için Passport**’a tıklayarak aşağıda gösterildiği gibi İş için Passport’u açın.

    ![İş İçin Passport Sayfası](../media/passport.png)

2.  Aşağıdaki ayarlardan birini seçin:
    - **Kayıtlı cihazlarda İş için Passport'u devre dışı bırak** - Windows 10 cihazlarında İş için Passport’u kullanmak istemiyorsanız bu ayarı seçin. Ekrandaki tüm diğer ayarlar devre dışı bırakılır.
    - **Kayıtlı cihazlarda İş için Passport’u etkinleştir** - Tüm Windows 10 cihazlarında İş için Passport ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.
    - **Yapılandırılmadı** - İş için Passport ayarlarını denetlemek için Intune’u kullanmak istemiyorsanız bu ayarı seçin. Windows 10 cihazlarındaki mevcut İş için Passport ayarlarının hiçbiri değiştirilmez. Ekrandaki tüm diğer ayarlar devre dışı bırakılır.
3.  **Kayıtlı cihazlarda İş için Passport’u etkinleştir** ayarını seçtiyseniz, tüm kayıtlı Windows 10 ve Windows 10 Mobile cihazlarına uygulanması gereken ayarları yapılandırın.
3.  İşiniz bittiğinde **Kaydet**’e tıklayın.

## İş İçin Passport: PIN ayarları

  
- **Minimum PIN uzunluğunu gerekli kıl**/**Maksimum PIN uzunluğunu gerekli kıl** - Cihazları, güvenli oturum açma için sizin belirttiğiniz minimum ve maksimum PIN uzunluklarını kullanacak şekilde yapılandırır. Varsayılan PIN uzunluğu 6 karakterdir, ancak minimum 4 karakterlik bir uzunluğu zorunlu tutabilirsiniz. Maksimum PIN uzunluğu 127 karakterdir.
- **PIN kodunda küçük harfleri gerektir**/**PIN kodunda büyük harfleri gerektir**/**PIN kodunda özel karakterleri gerektir** - Buna ek olarak, PIN’de büyük harf, küçük harf ve özel karakter kullanılmasını isteyerek daha güçlü bir PIN kullanımını zorunlu tutabilirsiniz. Aşağıdakilerden birini seçin:
    - **İzin verildi** - Kullanıcılar PIN kodlarında karakter türü kullanabilir ancak bu zorunlu değildir.
    - **Gerekli** - Kullanıcılar PIN kodlarında karakter türlerinden en az birini bulundurmalıdır. Örneğin, yaygın uygulama en az bir büyük harfin ve bir özel karakterin zorunlu olmasıdır.
    - **İzin verilmedi** (varsayılan) - Kullanıcılar PIN kodlarında bu karakter türlerini kullanmamalıdır (ayar yapılandırılmadığında da bu davranış geçerli olur).
    > [!TIP] Özel karakterler şunlardır: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **PIN süre sonu (gün)** - Sonrasında kullanıcıların PIN’i değiştirmesini zorunlu tutmak için PIN’e bir süre sonu belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür. 
- **PIN geçmişini anımsa** - Daha önce kullanılan PIN kodlarının yeniden kullanımını kısıtlamak için bu ayarı kullanın. Varsayılan olarak, kullanılan son 5 PIN kodunun yeniden kullanılamaz.


## İş İçin Passport: Diğer ayarlar

- **Güvenilir Platform Modülü (TPM) kullan** - Güvenilir Platform Modülü (TPM) yongası ek bir veri güvenliği katmanı sağlar.<br>Aşağıdaki değerlerden birini seçin:
    - **Gerekli** (varsayılan) - Yalnızca erişilebilir bir TPM’ye sahip cihazlar İş için Passport'a erişim sağlayabilir.
    - **Tercih edilen** - Cihazlar ilk olarak bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler
- **Biyometrik kimlik doğrulamasına izin ver** - İş için Passport PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:
    - **Evet** - İş için Passport biyometrik kimlik doğrulamasına izin verir.
    - **Hayır** - İş için Passport biyometrik kimlik doğrulamasını engeller (tüm hesap türleri için).
- **Varsa, gelişmiş kimlik sahtekarlığına karşı koruma kullan** - Windows Hello’nun sahtekarlığa karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).<br>**Evet** olarak ayarlanırsa Windows, desteklendiğinde yüz özellikleri için tüm kullanıcıların yanıltma koruması kullanmasını gerektirir.
- **Uzak Passport kullan** - Bu seçenek **Evet** olarak ayarlanırsa, kullanıcılar masaüstü bilgisayar kimlik doğrulaması için bir taşınabilir özel cihaz olarak hizmet verecek bir uzak Passport kullanabilir. Masaüstü bilgisayarı Azure Active Directory’e katılmış olmalıdır ve özel cihaz bir İş için Passport PIN kodu ile yapılandırılmalıdır.

## Daha fazla bilgi
Microsoft Passport hakkında daha fazla bilgi için, Windows 10 belgelerinde [kılavuza](https://technet.microsoft.com/library/mt589441.aspx) bakın.




<!--HONumber=May16_HO2-->


