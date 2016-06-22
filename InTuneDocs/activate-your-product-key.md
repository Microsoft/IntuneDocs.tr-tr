---
# required metadata

title: Ürün Anahtarınızı Etkinleştirme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 844c2ca8-2721-4f72-b1dd-be9b1da1f220

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ürün Anahtarınızı Etkinleştirme
Bir abonelik almak veya mevcut bir aboneliğe kullanıcı eklemek için bir ürün anahtarı kullanabilirsiniz. Ürün anahtarı, bir abonelik almak, çevrimiçi hizmetlere erişmek veya yazılım indirmek için gerekli olan 25 karakterli benzersiz bir alfasayısal koddur. Microsoft iş ortaklarından ya da satıcılarından ürün anahtarı satın alabilirsiniz.

## Ürün anahtarınızı kullanın
Ürün anahtarınızı kullanmak için 25 karakterli kodu girin.

-   Bir [!INCLUDE[wit_firstref](./includes/wit_firstref_md.md)] ürün anahtarını etkinleştiriyorsanız [buraya](https://account.manage.microsoft.com/commerce/productkeystart.aspx) gidin.

-   Bir Enterprise Mobility Suite ürün anahtarını etkinleştiriyorsanız [buraya](http://www.microsoft.com/ems/open) gidin.

> [!NOTE] Ürün anahtarınızı kaybederseniz, anahtarı satın aldığınız iş ortağına veya satıcıya başvurun.

## System Center Configuration Manager Yazılımınızı İndirin
System Center Configuration Manager yazılımını indirmek için [Toplu Lisans Hizmet Merkezi](http://go.microsoft.com/fwlink/?LinkID=232300)’ne gidin.

## Ürün anahtarını girerken sorunları giderme

|Hata iletisi|Çözüm|
|-----------------|--------------|
|**Girdiğiniz ürün anahtarı geçerli değil. Yeniden girmeyi deneyin** veya **Bu ürün anahtarı geçerli değil. Lütfen başka bir ürün anahtarı girin**.|Girdiğiniz karakterleri ve sayıları dikkatle gözden geçirin. Karakterler ve rakamlar arasında hata yapılabilir (“O” ve 0, “S” ve 5 gibi). Sorun devam ederse lütfen ürün anahtarınızı satın aldığınız satıcıya başvurun.|
|**Bu ürün anahtarını zaten girdiniz. Farklı bir anahtar girin**.|Anahtarın zaten eklenip eklenmediğini görmek için girilen ürün anahtarlarını denetleyin. Sorun devam ederse lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|
|**Girdiğiniz ürün anahtarının süresi doldu. Farklı bir anahtar girin**.|Lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|
|**Girdiğiniz ürün anahtarı zaten kullanılmış. Lütfen başka bir ürün anahtarı girin**.|Girdiğiniz ürün anahtarı zaten kullanılmış. Anahtarın siz veya kuruluşunuzun bir üyesi tarafından zaten kullanılmadığını doğrulayın. Anahtar önceden kullanılmamışsa lütfen ürün anahtarını satın aldığınız satıcıya başvurun.|
|**Üzgünüz, şu anda isteğinizi işleme koyamıyoruz. Lütfen birkaç dakika bekleyin ve tekrar deneyin**.|Sonraki denemeler de 15 dakikadan uzun bir süre boyunca aynı hata iletisine yol açarsa lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|
|**İstenen abonelik kullanılamıyor. Buna, şunlardan biri neden olmuş olabilir: Teklif yoktur - Hizmet ülkenizde kullanılamıyordur - Aynı denemeyi iki kez kullanmak/seçmek mümkün değildir. Sorun devam ederse, Microsoft desteğine başvurun**.|Lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|
|**Bu teklifin izin verdiğinden daha fazla kullanıcı lisansı eklediniz. En fazla 10000000 kullanıcı lisansı olabilir. Bu ürün anahtarını kaldırın ve daha az kullanıcı lisansı ekleyen bir ürün anahtarı girin**.|Lütfen satıcınıza veya iş ortağınıza başvurun. Bu hesap ile birlikte kullanılabilecek olandan daha fazla lisans satın aldınız.|
|**Bir ürün anahtarını kullanmak için genel yönetici veya faturalama yöneticisi olmanız gerekir**.|İzinlerinizin Fatura yöneticisi veya Genel yönetici olarak ayarlandığından emin olun. Bunu doğrulamak için, Yönetim Konsolu’nda **Yönetim** &gt; **Ayarlar**’a tıklayın.|
|**Üzgünüz, şu an hesabınızı oluşturamıyoruz. Lütfen birkaç dakika bekleyin ve tekrar deneyin**.|Sorun devam ederse lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|
|**Ne yazık ki siparişinizi işleyemiyoruz**.|Kiracı oluşturuldu fakat ürün anahtarları kullanılmadı. Ürün anahtarlarınızı yukarıda verilen bağlantıyla yeniden kullanmayı deneyin. Sorun devam ederse lütfen [Desteğe](http://go.microsoft.com/fwlink/?LinkID=394189) başvurun.|


<!--HONumber=Jun16_HO2-->


