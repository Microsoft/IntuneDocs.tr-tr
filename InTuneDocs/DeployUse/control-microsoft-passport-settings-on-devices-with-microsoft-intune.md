---
title: "Cihazlarda Microsoft Passport ayarlarını denetleme | Microsoft Intune"
description: "Intune’un parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Active Directory veya bir Azure Active Directory hesabının kullanıldığı alternatif bir oturum açma yöntemi olan İş için Microsoft Passport ile nasıl tümleşik çalıştığını öğrenin."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 822264b7af87c0241e1d345544b8e9892f9e8c51
ms.openlocfilehash: c05929f3c4032bf8e252f4b2087b23dfdecf846b


---

# Microsoft Intune ile cihazlarda Microsoft Passport ayarlarını denetleme
Microsoft Intune bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Active Directory veya bir Azure Active Directory hesabının kullanıldığı alternatif bir oturum açma yöntemi olan İş için Microsoft Passport ile tümleşir.

Passport, oturum açmak için parola yerine bir *kullanıcı hareketi* kullanmanıza imkan tanır. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

>[!TIP]
>İş için Microsoft Passport artık İş için Windows Hello olarak adlandırılıyor. Intune konsolu henüz bu değişikliği yansıtmamaktadır.

Intune, İş için Passport ile iki şekilde tümleştirilir:

-   Kullanıcıların oturum açarken hangi hareketleri kullanabileceğini ve kullanamayacağını denetlemek için bir Intune ilkesi kullanabilirsiniz.

-   Kimlik doğrulama sertifikalarını İş için Passport anahtar depolama sağlayıcısına (KSP) depolayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).

## İş için Passport ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows** &gt; **İş için Passport**’u seçerek İş için Passport sayfasını açın.

    ![İş için Passport sayfası](../media/passport.png)

2.  Aşağıdaki ayarlardan birini seçin:
    - **Kayıtlı cihazlarda İş İçin Passport’u devre dışı bırak**. Windows 10 cihazlarında İş için Passport’u kullanmak istemiyorsanız bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
    - **Kayıtlı cihazlarda İş İçin Passport’u etkinleştir**. Tüm Windows 10 cihazlarında İş için Passport ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.
    - **Yapılandırılmadı**. İş için Passport ayarlarını denetlemek için Intune’u kullanmak istemiyorsanız bu ayarı seçin. Windows 10 cihazlarındaki mevcut İş için Passport ayarlarının hiçbiri değiştirilmez. Ekrandaki diğer hiçbir ayarlar kullanılamaz.
3.  **Kayıtlı cihazlarda İş için Passport’u etkinleştir** ayarını seçtiyseniz, tüm kayıtlı Windows 10 ve Windows 10 Mobile cihazlarına uygulanması gereken ayarları yapılandırın.
4.  İşiniz bittiğinde **Kaydet**’i seçin.

## İş İçin Passport: PIN ayarları


- **Minimum PIN uzunluğunu gerekli kıl**/**Maksimum PIN uzunluğunu gerekli kıl**. Cihazları, güvenli oturum açma için sizin belirttiğiniz minimum ve maksimum PIN uzunluklarını kullanacak şekilde yapılandırır. Varsayılan PIN uzunluğu 6 karakterdir, ancak minimum 4 karakterlik bir uzunluğu zorunlu tutabilirsiniz. Maksimum PIN uzunluğu 127 karakterdir.
- **PIN’de küçük harf kullanımını gerekli kıl**/**PIN’de büyük harf kullanımını gerekli kıl**/**PIN’de özel karakter kullanımını gerekli kıl**. PIN’de büyük harf, küçük harf ve özel karakter kullanımını gerekli kılarak daha güçlü PIN zorunluluğu getirebilirsiniz. Aşağıdakilerden birini seçin:
    - **İzin Verildi**. Kullanıcılar PIN kodlarında karakter türü kullanabilir ancak bu zorunlu değildir.
    - **Gerekli**. Kullanıcılar PIN kodlarında karakter türlerinden en az birini bulundurmalıdır. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.
    - **İzin verilmiyor** (varsayılan). Kullanıcılar PIN’de bu karakter türlerini kullanmamalıdır. (Ayar yapılandırılmamışsa gerçekleşen davranış da budur.)
    > [!TIP]
    > Özel karakterler şunlardır: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **PIN süre sonu (gün)**. Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür.
- **PIN geçmişini anımsa**. Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Varsayılan olarak, son 5 PIN yeniden kullanılamaz.


## İş İçin Passport: Diğer ayarlar

- **Güvenilen Platform Modülü (TPM) kullan**. TPM yongası ek bir veri güvenliği katmanı sağlar.<br>Aşağıdaki değerlerden birini seçin:
    - **Gerekli** (varsayılan). Yalnızca erişilebilir bir TPM’ye sahip cihazlar İş için Passport sağlayabilir.
    - **Tercih edilen**. Cihazlar ilk olarak bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler.
- **Biyometrik kimlik doğrulamasına izin ver**. İş için Passport, PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:
    - **Evet**. İş için Passport, biyometrik kimlik doğrulamasına izin verir.
    - **Hayır**. İş için Passport, biyometrik kimlik doğrulamasını engeller (tüm hesap türleri için).
- **Varsa, gelişmiş kimlik sahtekarlığına karşı koruma kullan**. Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).<br>Bu **Evet** olarak ayarlanırsa Windows, desteklenen durumlarda yüz özellikleri için tüm kullanıcıların yanıltma koruması kullanmasını gerektirir.
- **Uzak Passport kullan**. Bu seçenek **Evet** olarak ayarlanırsa, kullanıcılar masaüstü bilgisayar kimlik doğrulaması için bir taşınabilir özel cihaz olarak hizmet verecek bir uzak passport kullanabilir. Masaüstü bilgisayarı Azure Active Directory’e katılmış olmalıdır ve özel cihaz bir İş için Passport PIN kodu ile yapılandırılmalıdır.

## Daha fazla bilgi
Microsoft Passport hakkında daha fazla bilgi için, Windows 10 belgelerinde [kılavuza](https://technet.microsoft.com/library/mt589441.aspx) bakın.



<!--HONumber=Aug16_HO1-->


