---
title: Windows Hello for Business ayarları Microsoft Intune - Azure | Microsoft Docs
description: Tüm PIN, biyometrik ve kimlik koruma profilinde sahtekarlığına karşı koruma ayarlarını kullanmak için Windows Hello iş için Windows 10 cihazlarda Microsoft Intune Yapılandır listesini bakın.
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
ms.openlocfilehash: 1cbf45fc337cbe7d7a45081a3b9e05002ca126d8
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402933"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Windows iş için Hello ıntune'da etkinleştirmek için Windows 10 cihaz ayarları

Bu makale listeler ve Windows Hello for Business ayarları kontrol edebilirsiniz ıntune'da Windows 10 cihazlarında açıklar. Bir Intune Yöneticisi olarak yapılandırabilir ve bu ayarlar Windows 10 cihazları için mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak atayın. 

Bu ayarlar hakkında ek bilgiler bulabilirsiniz [Windows Hello'yu Yapılandır iş İlkesi ayarlarının](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings), Windows Hello belgelerinde.


Intune'da iş profilleri hakkında daha fazla Windows Hello bilgi edinmek için [kimlik Koruması'nı yapılandırma](identity-protection-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir yapılandırma profili oluşturma](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello
- **İş için Windows Hello yapılandırma**:
  - **Yapılandırılmamış** -Intune denetlemek için Windows Hello ayarları için kullanmak istemiyorsanız bu ayarı seçin. Windows 10 cihazlarında bulunan İş için Windows Hello ayarları değiştirilmez. Bölmedeki diğer ayarlardan hiçbiri kullanılamaz.

  - **Devre dışı bırakılmış** - istemiyorsanız iş için Windows Hello'yu kullanma, bu ayarı seçin. Bu durumda, ekrandaki tüm diğer ayarlar kullanılamaz hale gelir.
  - **Etkin** -Windows Hello ayarları için yapılandırmak istiyorsanız bu ayarı seçin.  
  
  **Varsayılan**: Yapılandırılmamış

  Ayarlandığında *etkin*, aşağıdaki ayarlar kullanılabilir:

    - **Minimum PIN uzunluğu**  
     Cihazları, güvenli oturum açma yardımcı olması için en düşük PIN uzunluğunu belirtin. Windows cihaz varsayılanlardır altı karakter, ancak bu ayar, en az dört ile 127 karakter zorunlu kılabilir. 
  
      **Varsayılan**: *Yapılandırılmadı*

    - **Maksimum PIN uzunluğu**  
    Güvenli oturum açma yardımcı aygıtları için bir maksimum PIN uzunluğu belirtin. Windows cihaz varsayılanlardır altı karakter, ancak bu ayar, en az dört ile 127 karakter zorunlu kılabilir.  

      **Varsayılan**: *Yapılandırılmadı*  

    - **PIN kodunda küçük harfler**  
      Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir küçük harf içerir. Seçenekleriniz şunlardır:

      - **İzin** -kullanıcılar PIN kodlarında küçük harf kullanmasını engelleyin. Bu davranış, ayar yapılandırılmazsa da oluşur.
      - **İzin verilen** - kullanıcıların PIN kodunda küçük harf kullanın, ancak gerekli değildir.
      - **Gerekli** -kullanıcılar PIN kodlarına en az bir küçük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

    - **PIN kodunda büyük harfler**  
    Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir büyük harf içermesi. Seçenekleriniz şunlardır:

      - **İzin** -kullanıcıların PIN kodunda büyük harfler kullanarak. Bu davranış, ayar yapılandırılmazsa da oluşur.
      - **İzin verilen** - kullanıcıların PIN kodunda büyük harfler kullanın, ancak gerekli değildir.
      - **Gerekli** -kullanıcılar PIN kodlarına en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

    - **PIN kodunda özel karakterler**  
    Son kullanıcılar isteyerek daha güçlü bir PIN zorunlu kılabilir özel karakterler şunlardır. Özel karakterler şunlardır: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  
 
      Seçenekleriniz şunlardır:
      - **İzin** -kullanıcıların PIN kodunda özel karakterler kullanarak. Bu davranış, ayar yapılandırılmazsa da oluşur.
      - **İzin verilen** - kullanıcıların PIN kodunda büyük harfler kullanın, ancak gerekli değildir.
      - **Gerekli** -kullanıcılar PIN kodlarına en az bir büyük harf içermelidir. Örneğin, en az bir büyük harfin ve bir özel karakterin zorunlu kılınması yaygın bir uygulamadır.

      **Varsayılan**: İzin verilmiyor

  - **PIN süre sonu (gün)**  
      Son kullanıcıların belirli bir süre sonunda PIN’i değiştirmesini zorunlu tutmak için bir PIN kullanım süresi belirtmek iyi bir uygulamadır. Windows cihaz 41 gün varsayılanlardır.

    **Varsayılan**: Yapılandırılmadı

  - **PIN geçmişini anımsa**  
    Daha önce kullanılan PIN'lerin yeniden kullanılmasını kısıtlar. Windows cihazlar için son beş PIN'lerin kullanılmasını önleme varsayılan.  

    **Varsayılan**: Yapılandırılmadı  

  - **PIN kurtarmayı etkinleştir**   
    Windows Hello PIN iş kurtarma hizmeti için kullanacağınız kullanıcı sağlar. 
    
    - **Etkin** - PIN kurtarma parolası, cihazda depolanır ve gerekirse kullanıcı PIN'ini değiştirebilir.  
    - **Devre dışı bırakılmış** -kurtarma parolası oluşturulmuş veya depolanan değil.

    **Varsayılan**: Yapılandırılmamış

  - **Güvenilir Platform Modülü (TPM) kullan**   
    TPM yongası ek bir veri güvenliği katmanı sağlar.  

    - **Etkin** - yalnızca erişilebilir bir TPM'e sahip cihazlar Windows iş için Hello sağlayabilir.
    - **Yapılandırılmamış** -cihazlar ilk bir TPM kullanmayı dener. Bu seçenek mevcut değilse yazılım şifreleme kullanabilirler.
    
    **Varsayılan**: Yapılandırılmamış

  - **Biyometrik kimlik doğrulamasına izin ver**  
     İş İçin Windows Hello için bir PIN koduna alternatif olarak yüz tanıma veya parmak izi gibi biyometrik kimlik doğrulamasını etkinleştirir. Biyometrik kimlik doğrulaması başarısız olsa bile kullanıcılar bir iş PIN kodu yapılandırmalıdır. Aşağıdakilerden birini seçin:

    - **Etkinleştirme** -Windows iş için Hello biyometrik kimlik doğrulamasına izin verir.
    - **Yapılandırılmamış** -Windows iş için Hello biyometrik kimlik doğrulamasını engeller (tüm hesap türleri için).

    **Varsayılan**: Yapılandırılmamış

  - **Gelişmiş yanıltma, kullanılabilir olduğunda kullanın**  
    Windows Hello’nun yanıltmaya karşı koruma özelliklerinin bunu destekleyen cihazlarda kullanılıp kullanılmayacağını yapılandırır (örneğin, gerçek yüz yerine yüzün fotoğrafı olduğunu algılama).  
    - **Etkinleştirme** -Windows, desteklendiğinde yüz özellikleri için yanıltma kullanmak tüm kullanıcıların gerektirir.
    - **Yapılandırılmamış** -Windows cihaz yanıltma yapılandırmalarında geliştirir.

    **Varsayılan**: Yapılandırılmamış

  - **Şirket içi kaynaklar için sertifika**  

    - **Etkinleştirme** -sağlayan Windows iş için Hello kaynakları şirket içi kimlik doğrulaması için sertifikaları kullanmasına izin.
    - **Yapılandırılmamış** -engelleyen Windows Hello kaynakları şirket içi kimlik doğrulaması için sertifikaları kullanarak işletmeler için. Bunun yerine, cihazları varsayılan davranışını kullanın *güven anahtarı şirket içi kimlik doğrulaması*. Daha fazla bilgi için [şirket içi kimlik doğrulaması için kullanıcı sertifikası](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) Windows Hello belgelerinde.  

  **Varsayılan**: Yapılandırılmamış

- **Oturum açma için güvenlik tuşlarını kullanın**  
  Bu ayar, Windows 10 sürüm 1903 veya üzerini çalıştıran cihazlar için kullanılabilir. Oturum açma için Windows Hello güvenlik anahtarları kullanma desteği yönetmek için kullanın.  

  - **Etkin** -kullanıcılar, bilgisayarlar için bir oturum açma kimlik bilgileri Bu ilkeyle hedeflenen gibi bir Windows Hello güvenlik anahtarı kullanabilir. 
  - **Devre dışı** - güvenlik anahtarları devre dışı bırakıldı ve kullanıcılar bunları bilgisayarlara oturum açmak için kullanamazsınız.   

  **Varsayılan**: Yapılandırılmamış

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
