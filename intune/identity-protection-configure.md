---
title: Microsoft Intune - Azure’da kimlik koruma ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da Windows 10 cihazlarda İş İçin Windows Hello ayarlarını ayarlamak için bir cihaz profili ekleme
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7012479023ece83ef475431c5cefe150ab2ef342
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43317960"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Microsoft Intune - Azure’da kimlik koruma ayarlarını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kimlik koruma ayarları, yönetilen Windows 10 cihazlarda İş İçin Windows Hello’nun nasıl sağlandığı ve yapılandırıldığını denetler. Bu profili oluşturarak şunları yapılandırabilirsiniz:  
* Cihazlar ve kullanıcılar için İş İçin Windows Hello kullanılabilirliği.
* Cihaz PIN gereksinimleri.
* Kullanıcıların cihazlarında oturum açmak için kullanabileceği ve kullanamayacağı hareketler.  

 Bu profili seçilen kullanıcı ve cihaz gruplarına veya tüm kullanıcılara ve tüm cihazlara atayabilirsiniz. Gruplar, Intune’a iade etme işlemi yaptıktan sonra kimlik koruma profilini alır.    

Bu makaledeki bilgileri kullanarak kimlik koruma profilleri oluşturun. Daha sonra kullanıcı ve cihaz gruplarına [profilinizi atayın](device-profile-assign.md).

Bu özellik şunları çalıştıran cihazlarda geçerlidir:  
- Windows 10 ve üzeri
- Windows 10 Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Kimlik koruma ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Kimlik koruma profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin. İş İçin Windows Hello, yalnızca Windows 10 ve üzeri çalıştıran cihazlarda desteklenir.
6. Açılan **Profil türü** listesinden **Kimlik koruma**’yı seçin.
7. İş İçin Windows Hello bölmesinde İş İçin Windows Hello’yu yapılandır seçeneği için aşağıdakilerden birini seçin:
    * Devre dışı. İş İçin Windows Hello’yu kullanmak istemiyorsanız, bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
    * Etkin. İş İçin Windows Hello ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.  

8. Önceki adımda **Etkin**’i seçtiyseniz, hedeflenen kayıtlı Windows 10 ve Windows 10 Mobile cihazlarına ve kullanıcılarına uygulanacak olan gerekli ayarları yapılandırın.

> [!NOTE]
> Kimlik koruma profillerini yalnızca kullanıcılara atarken cihaz bağlamı varsayılan olarak **Yapılandırılmadı** olur.  

   - **En düşük PIN uzunluğu**/**En yüksek PIN uzunluğu**. Cihazları, güvenli oturum açma için sizin belirttiğiniz minimum ve maksimum PIN uzunluklarını kullanacak şekilde yapılandırır. Varsayılan PIN uzunluğu altı karakterdir, ancak minimum dört karakterlik bir uzunluğu zorunlu tutabilirsiniz. Maksimum PIN uzunluğu 127 karakterdir.  

   - **PIN’de küçük harfler**/**PIN’de büyük harfler**/**PIN’de özel karakterler**. PIN’de büyük harf, küçük harf ve özel karakter kullanımını gerekli kılarak daha güçlü PIN zorunluluğu getirebilirsiniz. Aşağıdakilerden birini seçin:

     - **İzin Verildi**. Kullanıcılar PIN kodlarında karakter türü kullanabilir ancak bu zorunlu değildir.

     - **Gerekli**. Kullanıcılar PIN kodlarında karakter türlerinden en az birini bulundurmalıdır. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

     - **İzin verilmiyor** (varsayılan). Kullanıcılar PIN’de bu karakter türlerini kullanmamalıdır. (Bu davranış, ayar yapılandırılmadığında da ortaya çıkar.)<br>Özel karakterler şunlardır: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **PIN süre sonu (gün)**. Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Varsayılan değer 41 gündür.

   - **PIN geçmişini anımsa**. Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Varsayılan olarak, son 5 PIN yeniden kullanılamaz.  
   - **PIN kurtarmayı etkinleştir**: Kullanıcıların İş İçin Windows Hello PIN kurtarma hizmetini kullanarak PIN’lerini değiştirmelerine izin verir. 
       - **Etkinleştir**. Bulut hizmeti, cihazda depolanmak üzere bir PIN kurtarma gizli dizisi şifreler. Kullanıcı, gerektiğinde PIN’ini değiştirebilir.  
       - **Yapılandırılmadı** (varsayılan). PIN kurtarma gizli dizisi oluşturulmaz veya depolanmaz. Kullanıcı PIN’ini unutursa yeni bir PIN almanın tek yolu geçerli PIN’i silmek ve yenisini oluşturmaktır. Kullanıcının eski PIN ile erişim sağladığı bütün hizmetlere yeniden kaydolması gerekir.  
   
   - **Güvenilen Platform Modülü (TPM) kullan**. TPM yongası ek bir veri güvenliği katmanı sağlar. Aşağıdaki değerlerden birini seçin:  
     - **Etkinleştir**. Yalnızca erişilebilir bir TPM’si olan cihazlar İş İçin Windows Hello sağlayabilir.
     - **Yapılandırılmadı**. Kullanılabilir bir TPM olmadığında bile tüm cihazlar İş İçin Windows Hello sağlayabilir. Cihazlar önce bir TPM kullanmayı dener ancak başaramazsa yazılım şifrelemesi kullanır.  

   - **Biyometrik kimlik doğrulamasına izin ver**. İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

     - **Etkinleştir**. İş İçin Windows Hello biyometrik kimlik doğrulamasına izin verir.
     - **Yapılandırılmadı** (varsayılan). İş İçin Windows Hello, (tüm hesap türleri için) biyometrik kimlik doğrulamasını engeller.

   - **Varsa, gelişmiş kimlik sahtekarlığına karşı koruma kullan**. Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).
       - **Etkinleştir**. Windows, yüz özellikleri destekleniyorsa bunun için tüm kullanıcıların yanıltmaya karşı koruma kullanmasını gerektirir.  
       - **Yapılandırılmadı** (varsayılan). Windows, cihazdaki yanıltmaya karşı koruma yapılandırmalarını kabul eder.

   - **Şirket içi kaynaklar için sertifika**. 
       - **Etkinleştir**. İş İçin Windows Hello’nun şirket içi kaynaklarda kimlik doğrulaması için sertifika kullanmasına izin verir.
       - **Yapılandırılmadı** (varsayılan). İş İçin Windows Hello’nun şirket içi kaynaklarda kimlik doğrulaması için sertifika kullanmasını önler.  
9. Profilinizi kaydetmek için **Tamam**’a tıklayın.  

Profil oluşturulur ve **Cihaz yapılandırması - Profiller** listesinde görünür. Devam ederek bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
