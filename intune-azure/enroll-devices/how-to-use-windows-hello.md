---
title: "İş İçin Windows Hello’yu kullanma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Yönetilen cihazlarda İş İçin Windows Hello kullanımını denetlemeye yönelik bir ilke oluşturmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 541be8b8-8668-41be-afce-3f3e08c12191
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 1844cf87ae51c7d0832e3ba6315efde734ff56cc
ms.lasthandoff: 02/18/2017


---

# <a name="use-windows-hello-for-business"></a>İş İçin Windows Hello’yu kullanma


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek için Active Directory veya bir Azure Active Directory hesabını kullanıldığı alternatif bir oturum açma yöntemi olan İş İçin Windows Hello (eskiden İş için Microsoft Passport) ile tümleşir.

İş İçin Hello, oturum açmak için parola yerine bir *kullanıcı hareketi* kullanmanıza izin verir. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

Intune, İş İçin Hello ile iki şekilde tümleşir:

-   Kullanıcıların oturum açarken hangi hareketleri kullanabileceğini ve kullanamayacağını denetlemek için bir Intune ilkesi kullanabilirsiniz.

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> Yıldönümü Güncelleştirmesi’nden önceki Windows 10 masaüstü ve mobil sürümlerinde, kaynaklarda kimlik doğrulama için kullanılabilen iki farklı PIN ayarlayabilirsiniz:
- **Cihaz PIN’i** cihazın kilidini açmak ve bulut kaynaklarına bağlanmak için kullanılabilir.
- **İş PIN’i** kullanıcının kişisel cihazlarından (KCG) Azure AD kaynaklarına erişmek için kullanılır.

>Yıldönümü Güncelleştirmesi’nde bu iki PIN, tek bir cihaz PIN’inde birleştirilmiştir.
Cihaz PIN’ini denetlemek için ayarladığınız Intune yapılandırma ilkelerinin yanı sıra, yapılandırmış olduğunuz İş İçin Windows Hello ilkeleri de bu yeni PIN değerine ayarlanmıştır.
PIN’i denetlemek için iki ilke türünü de ayarladıysanız, İş İçin Windows Hello ilkesi hem Windows 10 masaüstü cihazlarına hem de Windows 10 mobil cihazlara uygulanır.
İlke çakışmalarının çözümlendiğinden ve PIN ilkesinin düzgün şekilde uygulandığından emin olmak için, İş İçin Windows Hello İlkenizi yapılandırma ilkenizdeki ayarlarla eşleşecek şekilde güncelleştirin ve kullanıcılarınızdan cihazlarını Şifket Portalı uygulamasında eşitlemelerini isteyin.



## <a name="create-a-windows-hello-for-business-policy"></a>İş İçin Windows Hello ilkesi oluşturma

1.  Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2.  Intune dikey penceresinde **Cihazları kaydet**’i seçin ve sonra da **Yönet** > **İş İçin Windows Hello**’yu seçin.

3.  Açılan dikey pencerede **Varsayılan** ayarları seçin.

4.  **Tüm Kullanıcılar** dikey penceresinde **Özellikler**’e tıklayın, ardından İş İçin Windows Hello ayarları için **Ad** ve isteğe bağlı olarak **Açıklama** girin.

5. **Tüm Kullanıcılar** dikey penceresinde **Ayarlar**’a tıklayın ve **İş İçin Windows Hello’yu yapılandır** seçeneği için aşağıdakilerden birini seçin:

    - **Devre Dışı**. İş İçin Windows Hello’yu kullanmak istemiyorsanız, bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
    - **Etkin**. İş İçin Windows Hello ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.
    - **Yapılandırılmadı**. Intune’un İş İçin Windows Hello ayarlarını denetlemesini istemiyorsanız bu ayarı seçin. Windows 10 cihazlarında bulunan İş İçin Windows Hello ayarları değiştirilmez. Dikey penceredeki diğer ayarlardan hiçbiri kullanılamaz.

6.  Önceki adımda **Etkin**’i seçtiyseniz, tüm kayıtlı Windows 10 ve Windows 10 Mobile cihazlarına uygulanacak olan gerekli ayarları yapılandırın.

 - **Güvenilen Platform Modülü (TPM) kullan**. TPM yongası ek bir veri güvenliği katmanı sağlar.<br>Aşağıdaki değerlerden birini seçin:

     - **Gerekli** (varsayılan). Yalnızca erişilebilir bir TPM’si olan cihazlar İş İçin Windows Hello sağlayabilir.
     - **Tercih edilen**. Cihazlar ilk olarak bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler.

 - **Minimum PIN uzunluğunu gerekli kıl**/**Maksimum PIN uzunluğunu gerekli kıl**. Cihazları, güvenli oturum açma için sizin belirttiğiniz minimum ve maksimum PIN uzunluklarını kullanacak şekilde yapılandırır. Varsayılan PIN uzunluğu 6 karakterdir, ancak minimum 4 karakterlik bir uzunluğu zorunlu tutabilirsiniz. Maksimum PIN uzunluğu 127 karakterdir.

 - **PIN’de küçük harf kullanımını gerekli kıl**/**PIN’de büyük harf kullanımını gerekli kıl**/**PIN’de özel karakter kullanımını gerekli kıl**. PIN’de büyük harf, küçük harf ve özel karakter kullanımını gerekli kılarak daha güçlü PIN zorunluluğu getirebilirsiniz. Aşağıdakilerden birini seçin:

     - **İzin Verildi**. Kullanıcılar PIN kodlarında karakter türü kullanabilir ancak bu zorunlu değildir.
    
     - **Gerekli**. Kullanıcılar PIN kodlarında karakter türlerinden en az birini bulundurmalıdır. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

     - **İzin verilmiyor** (varsayılan). Kullanıcılar PIN’de bu karakter türlerini kullanmamalıdır. (Ayar yapılandırılmamışsa gerçekleşen davranış da budur.)<br>Özel karakterler şunlardır: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

 - **PIN süre sonu (gün)**. Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür.

 - **PIN geçmişini anımsa**. Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Varsayılan olarak, son 5 PIN yeniden kullanılamaz.

 - **Biyometrik kimlik doğrulamasına izin ver**. İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

     - **Evet**. İş İçin Windows Hello biyometrik kimlik doğrulamasına izin verir.
     - **Hayır**. İş İçin Windows Hello, (tüm hesap türleri için) biyometrik kimlik doğrulamasını engeller.

 - **Varsa, gelişmiş kimlik sahtekarlığına karşı koruma kullan**. Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).<br>Bu **Evet** olarak ayarlanırsa Windows, desteklenen durumlarda yüz özellikleri için tüm kullanıcıların yanıltma koruması kullanmasını gerektirir.

 - **Telefonla oturum açma kullanın**. Bu seçenek **Evet** olarak ayarlanırsa, kullanıcılar masaüstü bilgisayar kimlik doğrulaması için bir taşınabilir özel cihaz olarak hizmet verecek bir uzak passport kullanabilir. Masaüstü bilgisayarının Azure Active Directory’ye katılmış ve eşlik eden cihazın bir İş İçin Windows Hello PIN’i ile yapılandırılmış olması gerekir.


## <a name="further-information"></a>Daha fazla bilgi
Microsoft Passport hakkında daha fazla bilgi için, Windows 10 belgelerinde [kılavuza](https://technet.microsoft.com/library/mt589441.aspx) bakın.

