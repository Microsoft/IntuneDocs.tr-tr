---
title: Windows iş için Hello ile Microsoft Intune tümleştirme | Microsoft Intune
description: Yönetilen cihazlarda İş İçin Windows Hello kullanımını denetlemeye yönelik bir ilke oluşturmayı öğrenin."
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2bd859dce83dddd430e5c46fd9b669901115059a
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816948"
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>İş için Windows Hello ile Microsoft Intune tümleştirmesi


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

İş için Windows Hello (önceki adıyla İş İçin Microsoft Passport) ile Microsoft Intune’u tümleştirebilirsiniz.

 İş İçin Hello bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek için Active Directory veya bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemidir. Oturum açmak için parola yerine bir *kullanıcı hareketi* kullanmanıza imkan tanır. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

Intune, İş İçin Hello ile iki şekilde tümleşir:

-   **Cihaz kaydı** altında bir Intune ilkesi oluşturulabilir. Bu ilke, tüm kuruluşu hedefler (kiracı genelinde). Windows AutoPilot ilk çalıştırma deneyimini (OOBE) destekler ve bir cihaz kaydedildiğinde uygulanır. 
-  **Cihaz yapılandırması** altında bir kimlik koruma profili oluşturulabilir. Bu profil, atanmış kullanıcı ve cihazları hedefler ve iade etme sırasında uygulanır. 

Tüm kuruluşunuzu hedefleyen bir varsayılan İş İçin Windows Hello ilkesi oluşturmak için bu makaleden yararlanın. Seçili kullanıcı ve cihaz gruplarına uygulanacak bir kimlik koruma profili oluşturmak için bkz. [Kimlik koruma profili oluşturma](identity-protection-configure.md).  

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> Yıldönümü Güncelleştirmesi’nden önceki Windows 10 masaüstü ve mobil sürümlerinde, kaynaklarda kimlik doğrulama için kullanılabilen iki farklı PIN ayarlayabilirsiniz:
> - **Cihaz PIN’i** cihazın kilidini açmak ve bulut kaynaklarına bağlanmak için kullanılabilir.
> - **İş PIN’i** kullanıcının kişisel cihazlarından (KCG) Azure AD kaynaklarına erişmek için kullanılır.
> 
> Yıldönümü Güncelleştirmesi’nde bu iki PIN, tek bir cihaz PIN’inde birleştirilmiştir.
> Cihaz PIN’ini denetlemek için ayarladığınız Intune yapılandırma ilkelerinin yanı sıra, yapılandırmış olduğunuz İş İçin Windows Hello ilkeleri de bu yeni PIN değerine ayarlanmıştır.
> PIN’i denetlemek için iki ilke türünü de ayarladıysanız, İş için Windows Hello ilkesi hem Windows 10 masaüstü cihazlara hem de Windows 10 mobil cihazlara uygulanır.
> İlke çakışmalarının çözümlendiğinden ve PIN ilkesinin düzgün şekilde uygulandığından emin olmak için, İş İçin Windows Hello İlkenizi yapılandırma ilkenizdeki ayarlarla eşleşecek şekilde güncelleştirin ve kullanıcılarınızdan cihazlarını Şifket Portalı uygulamasında eşitlemelerini isteyin.



## <a name="create-a-windows-hello-for-business-policy"></a>İş İçin Windows Hello ilkesi oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler** > **İzleme ve Yönetim** > **Intune**’u seçin.

2. Intune bölmesinde **Cihaz kaydı**’nı ve ardından **Windows kaydı** > **İş İçin Windows Hello**’yu seçin.

3. Açılan bölmede **Varsayılan** ayarları seçin.

4. **Tüm Kullanıcılar** bölmesinde **Özellikler**’e tıklayın, ardından İş İçin Windows Hello ayarları için **Ad** ve isteğe bağlı olarak **Açıklama** girin.

5. **Tüm Kullanıcılar** bölmesinde **Ayarlar**’a tıklayın ve **İş İçin Windows Hello’yu yapılandır** seçeneği için aşağıdakilerden birini seçin:

    - **Devre Dışı**. İş İçin Windows Hello’yu kullanmak istemiyorsanız, bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
    - **Etkin**. İş İçin Windows Hello ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.
    - **Yapılandırılmadı**. Intune’un İş İçin Windows Hello ayarlarını denetlemesini istemiyorsanız bu ayarı seçin. Windows 10 cihazlarında bulunan İş için Windows Hello ayarları değiştirilmez. Bölmedeki diğer ayarlardan hiçbiri kullanılamaz.

6. Önceki adımda **Etkin**’i seçtiyseniz, tüm kayıtlı Windows 10 ve Windows 10 Mobile cihazlarına uygulanacak olan gerekli ayarları yapılandırın.

   - **Güvenilen Platform Modülü (TPM) kullan**. TPM yongası ek bir veri güvenliği katmanı sağlar.<br>Aşağıdaki değerlerden birini seçin:

     - **Gerekli** (varsayılan). Yalnızca erişilebilir bir TPM’si olan cihazlar İş İçin Windows Hello sağlayabilir.
     - **Tercih edilen**. Cihazlar ilk olarak bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler.

   - **En düşük PIN uzunluğu**/**En yüksek PIN uzunluğu**. Cihazları, güvenli oturum açma için sizin belirttiğiniz minimum ve maksimum PIN uzunluklarını kullanacak şekilde yapılandırır. Varsayılan PIN uzunluğu altı karakterdir, ancak minimum dört karakterlik bir uzunluğu zorunlu tutabilirsiniz. Maksimum PIN uzunluğu 127 karakterdir.

   - **PIN’de küçük harfler**/**PIN’de büyük harfler**/**PIN’de özel karakterler**. PIN’de büyük harf, küçük harf ve özel karakter kullanımını gerekli kılarak daha güçlü PIN zorunluluğu getirebilirsiniz. Aşağıdakilerden birini seçin:

     - **İzin Verildi**. Kullanıcılar PIN kodlarında karakter türü kullanabilir ancak bu zorunlu değildir.

     - **Gerekli**. Kullanıcılar PIN kodlarında karakter türlerinden en az birini bulundurmalıdır. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

     - **İzin verilmiyor** (varsayılan). Kullanıcılar PIN’de bu karakter türlerini kullanmamalıdır. (Ayar yapılandırılmamışsa gerçekleşen davranış da budur.)<br>Özel karakterler şunlardır: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN süre sonu (gün)**. Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür.

   - **PIN geçmişini anımsa**. Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Varsayılan olarak, son 5 PIN yeniden kullanılamaz.

   - **Biyometrik kimlik doğrulamasına izin ver**. İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

     - **Evet**. İş İçin Windows Hello biyometrik kimlik doğrulamasına izin verir.
     - **Hayır**. İş İçin Windows Hello, (tüm hesap türleri için) biyometrik kimlik doğrulamasını engeller.

   - **Varsa, gelişmiş kimlik sahtekarlığına karşı koruma kullan**. Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).<br>Bu **Evet** olarak ayarlanırsa Windows, desteklenen durumlarda yüz özellikleri için tüm kullanıcıların yanıltma koruması kullanmasını gerektirir.

   - **Telefonla oturum açmaya izin ver**. Bu seçenek **Evet** olarak ayarlanırsa, kullanıcılar masaüstü bilgisayar kimlik doğrulaması için bir taşınabilir özel cihaz olarak hizmet verecek bir uzak passport kullanabilir. Masaüstü bilgisayarının Azure Active Directory’ye katılmış ve eşlik eden cihazın bir İş İçin Windows Hello PIN’i ile yapılandırılmış olması gerekir.

## <a name="windows-holographic-for-business-support"></a>Windows 10 Holographic for Business desteği

Windows Holographic for Business, aşağıdaki İş için Windows Hello ayarlarını destekler:

- Güvenilir Platform Modülü (TPM) kullanma
- Minimum PIN uzunluğu
- Maksimum PIN uzunluğu
- PIN kodunda küçük harfler
- PIN kodunda büyük harfler
- PIN kodunda özel karakterler
- PIN süre zaman aşımı (gün)
- PIN geçmişini anımsa

## <a name="further-information"></a>Daha fazla bilgi
Microsoft Passport hakkında daha fazla bilgi için, Windows 10 belgelerinde [kılavuza](https://technet.microsoft.com/library/mt589441.aspx) bakın.
