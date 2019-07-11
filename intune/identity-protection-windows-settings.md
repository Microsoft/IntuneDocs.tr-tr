---
title: Microsoft Intune-Azure 'da Iş için Windows Hello ayarları | Microsoft Docs
description: Microsoft Intune 'da Windows 10 cihazlarında Iş için Windows Hello 'yu kullanmak ve yapılandırmak üzere bir kimlik koruması profilinde tüm PIN, biyometrik ve korsanlığa karşı koruma ayarlarının listesini görüntüleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 5a8111d2542269441c7305aad0aad0b7c2162037
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735620"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Intune 'da Iş için Windows Hello 'Yu etkinleştirmek için Windows 10 cihaz ayarları

Bu makalede, Intune 'da Windows 10 cihazlarında denetleyebilmeniz için Windows Hello ayarlarını listeler ve açıklanmaktadır. Bir Intune Yöneticisi olarak, mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları yapılandırabilir ve Windows 10 cihazlarına atayabilirsiniz. 

Windows Hello belgelerinde [iş Için Windows Hello ilke ayarlarını yapılandırma](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings)bölümünde bu ayarlarla ilgili ek bilgiler bulabilirsiniz.


Intune 'da Iş için Windows Hello profilleri hakkında daha fazla bilgi edinmek için bkz. [kimlik korumasını yapılandırma](identity-protection-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Yapılandırma profili oluşturun](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello
- **İş Için Windows Hello 'Yu Yapılandır**:
  - **Yapılandırılmadı** -Iş Için Windows Hello ayarlarını denetlemek Için Intune 'u kullanmak istemiyorsanız bu ayarı seçin. Windows 10 cihazlarında bulunan İş için Windows Hello ayarları değiştirilmez. Bölmedeki diğer ayarlardan hiçbiri kullanılamaz.

  - **Devre dışı** -Iş Için Windows Hello 'yu kullanmak istemiyorsanız, bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
  - **Etkin** -Iş Için Windows Hello ayarlarını yapılandırmak istiyorsanız bu ayarı seçin.  
  
  **Varsayılan**: Yapılandırılmamış

  *Etkin*olarak ayarlandığında, aşağıdaki ayarlar kullanılabilir:

  - **Minimum PIN uzunluğu**  
    Oturum açma güvenliğini sağlamaya yardımcı olmak için cihazlar için minimum PIN uzunluğu belirtin. Windows cihaz Varsayılanları altı karakterdir, ancak bu ayar en az dört ile 127 karakter uygulayabilir. 

    **Varsayılan**: *Yapılandırılmadı*

  - **Maksimum PIN uzunluğu**  
  Oturum açma güvenliğini sağlamaya yardımcı olmak için cihazlar için maksimum PIN uzunluğu belirtin. Windows cihaz Varsayılanları altı karakterdir, ancak bu ayar en az dört ile 127 karakter uygulayabilir.  

    **Varsayılan**: *Yapılandırılmadı*  

  - **PIN 'de küçük harfler**  
    Son kullanıcıların küçük harfler içermesini zorunlu kılarak daha güçlü bir PIN uygulayabilirsiniz. Seçenekleriniz şunlardır:

    - **İzin verilmiyor** -kullanıcıların PIN kodunda küçük harf kullanmalarını engelleyin. Bu davranış, ayar yapılandırılmamışsa da oluşur.
    - **Izin verilen** -kullanıcıların PIN kodunda küçük harfler kullanmasına izin verir, ancak bu gerekli değildir.
    - **Gerekli** -kullanıcılar PIN 'e en az bir küçük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

  - **PIN kodunda büyük harfler**  
    Son kullanıcıların büyük harfler içermesini zorunlu kılarak daha güçlü bir PIN uygulayabilirsiniz. Seçenekleriniz şunlardır:

    - **İzin verilmiyor** -kullanıcıların PIN kodunda büyük harf kullanmalarını engelleyin. Bu davranış, ayar yapılandırılmamışsa da oluşur.
    - **Izin verilen** -kullanıcıların PIN kodunda büyük harfler kullanmasına izin verir, ancak bu gerekli değildir.
    - **Gerekli** -kullanıcılar PIN 'e en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

  - **PIN 'de özel karakterler**  
    Son kullanıcıların özel karakterler içermesini isteyerek daha güçlü bir PIN zorlayabilirsiniz. Özel karakterler şunlardır:`! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  

    Seçenekleriniz şunlardır:
    - **İzin verilmiyor** -kullanıcıların PIN 'de özel karakterler kullanmalarını engelleyin. Bu davranış, ayar yapılandırılmamışsa da oluşur.
    - **Izin verilen** -kullanıcıların PIN kodunda büyük harfler kullanmasına izin verir, ancak bu gerekli değildir.
    - **Gerekli** -kullanıcılar PIN 'e en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

    **Varsayılan**: İzin verilmiyor

  - **PIN süre sonu (gün)**  
    Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Windows cihaz Varsayılanları 41 gündür.

    **Varsayılan**: Yapılandırılmadı

  - **PIN geçmişini anımsa**  
    Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Windows cihazlarının son beş PIN 'in yeniden kullanılmasını önlemek için varsayılan değer.  

    **Varsayılan**: Yapılandırılmadı  

  - **PIN kurtarmayı etkinleştir**   
    Kullanıcının Iş için Windows Hello PIN kurtarma hizmetini kullanmasına izin verir. 
    
    - **Etkin** -PIN kurtarma gizli anahtarı cihazda depolanır ve gerekirse Kullanıcı PIN 'ini değiştirebilir.  
    - **Devre dışı** -kurtarma parolası oluşturulmaz veya depolanmaz.

    **Varsayılan**: Yapılandırılmamış

  - **Güvenilir Platform Modülü (TPM) kullanma**   
    TPM yongası ek bir veri güvenliği katmanı sağlar.  

    - **Etkin** -yalnızca erişilebilir TPM 'ye sahip cihazlar Iş Için Windows Hello 'yu sağlayabilir.
    - **Yapılandırılmadı** -cihazlar ilk olarak bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler.
    
    **Varsayılan**: Yapılandırılmamış

  - **Biyometrik kimlik doğrulamasına izin ver**  
     İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

    - **Etkinleştir** -iş Için Windows Hello, biyometrik kimlik doğrulamasına izin verir.
    - **Yapılandırılmadı** -iş Için Windows Hello, biyometrik kimlik doğrulamasını engeller (tüm hesap türleri için).

    **Varsayılan**: Yapılandırılmamış

  - **Kullanılabilir olduğunda gelişmiş yanıltma koruması kullan**  
    Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).  
    - **Etkinleştir** -Windows, desteklendiğinde yüz özellikleri için tüm kullanıcıların yanıltma koruması kullanmasını gerektirir.
    - **Yapılandırılmadı** -Windows cihazda kimlik sahtekarlığı önleme yapılandırmasını alır.

    **Varsayılan**: Yapılandırılmamış

  - **Şirket içi kaynaklar için sertifika**  

    - **Etkinleştir** -Iş Için Windows Hello 'nun şirket içi kaynaklarda kimlik doğrulaması yapmak için sertifikaları kullanmasına izin verir.
    - **Yapılandırılmadı** -Iş Için Windows Hello 'yu, şirket içi kaynaklarda kimlik doğrulaması yapmak için sertifikaları kullanmasını engeller. Bunun yerine, cihazlar *anahtar güveni şirket içi kimlik doğrulamanın*varsayılan davranışını kullanır. Daha fazla bilgi için bkz. Windows Hello belgelerinde Şirket [içi kimlik doğrulaması Için Kullanıcı sertifikası](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) .  

  **Varsayılan**: Yapılandırılmamış

- **Oturum açma için güvenlik anahtarlarını kullan**  
  Bu ayar, Windows 10 sürüm 1903 veya üstünü çalıştıran cihazlar için kullanılabilir. Oturum açmak için Windows Hello güvenlik anahtarlarını kullanma desteğini yönetmek için bunu kullanın.  

  - **Etkin** -kullanıcılar, bu Ilkeyle hedeflenen bilgisayarlar için oturum açma kimlik bilgileri olarak bir Windows Hello güvenlik anahtarı kullanabilir. 
  - **Devre dışı** -güvenlik anahtarları devre dışıdır ve kullanıcılar bilgisayarlarda oturum açmak için bunları kullanamaz.   

  **Varsayılan**: Yapılandırılmamış

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
