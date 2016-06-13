---
# required metadata

title: Toplu satın alma programıyla satın aldığınız iOS uygulamalarını yönetme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile toplu satın alma programından satın aldığınız iOS uygulamalarını yönetme
Bazı uygulama depoları, kuruluşunuzda çalıştırmak istediğiniz bir uygulama için birden fazla lisans satın almanıza olanak sağlayabilir. Bu durum, satın alınan uygulamaların birden fazla kopyasın izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

Microsoft Intune lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önleyerek, böyle bir program aracılığıyla satın aldığınız uygulamaları yönetmenize yardımcı olur.

> [!Important]
> Şu anda, Intune iOS VPP uygulama lisanslarını cihazlara değil kullanıcılara atamaktadır. Bu nedenle, son kullanıcıların uygulamayı yüklemek için Apple Kimliği parolalarını girmeleri gerekir.

## iOS cihazları için toplu satın alınan uygulamaları yönetme
[Apple İş için Toplu Satın Alma Programı (VPP)](http://www.apple.com/business/vpp/) ile iOS için birden çok lisans satın alırsınız. Buna Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

## Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve bunu Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdakileri anlamanız gerekir:

* Her kuruluş yalnızca bir VPP hesabına ve belirtecine sahip olabilir.
* Bir Apple VPP hesabını Intune ile ilişkilendirdikten sonra farklı bir hesabı ilişkilendiremezsiniz. Bu nedenle, birden çok kişinin kullandığınız hesaba ilişkin ayrıntıları bilmesi çok önemlidir.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Ancak, dilediğiniz zaman elle eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'a içe aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS VPP kullanmaya başlamadan önce diğer MDM satıcıları ile oluşturulan tüm var olan VPP kullanıcı hesaplarını kaldırın. Intune bu kullanıcı hesaplarını bir güvenlik önlemi olarak Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmetinden verileri eşitler. 

## Apple VPP belirtecini almak ve karşıya yüklemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici** &gt; **iOS ve Mac OS X** &gt; **Toplu Satın Alma Programı**’na tıklayın.

2.  **Apple VPP Hesabı** bağlantısına tıklayın ve henüz yapmadıysanız İş için Toplu Satın Alma Programı’na kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin.

3.  Intune konsolunun **Apple Toplu Satın Alma Programı’nı (VPP) Yönet** sayfasında **VPP belirtecini karşıya yükle**’ye tıklayın.

4.  **VPP belirtecini karşıya yükle** iletişim kutusunda VPP belirtecinin adını ve Apple Kimliğinizi girin veya yapıştırın ve ardından **Karşıya Yükle**’ye tıklayın.

5.  Uyarı iletişim kutusunda daha sonra farklı VPP hesabına geçemeyeceğinizi anladığınızı belirten onay kutusuna ve ardından **Evet**’e tıklayın.

**Toplu Satın Alma Programı** sayfasında bundan böyle Apple VPP hakkında en son ne zaman güncelleştirildiği, ne zaman sona ereceği ve Intune ile en son ne zaman eşitlendiği gibi bilgileri görüntüleyebilirsiniz.

**Şimdi eşitle**’ye tıklayarak, Apple tarafından tutulan verileri Intune’la dilediğiniz zaman eşitleyebilirsiniz.

## Toplu satın alınmış bir uygulamayı dağıtmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Yönetilen Yazılım** &gt; **Toplu Satın Alınan Uygulamalar**’a tıklayın. Bu listede, Apple VPP hizmetinden eşitlenmiş olan tüm uygulamalar gösterilir.

2.  Dağıtmak istediğiniz uygulamayı seçin, **Dağıtımı Yönet**’e tıklayın, ardından uygulamanın karşıya yüklenmesini, oluşturulmasını ve dağıtımını tamamlamak için [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md) konu başlığı altında verilen yönergeleri kullanın.

Uygulamayı **Gerekli** yükleme olarak dağıttığınızda uygulamayı yükleyen her kullanıcı tarafından bir lisans kullanılır.

Bir lisansı geri kazanmak için dağıtım eylemini **Kaldır** olarak değiştirmeniz gerekir. Uygulama kaldırıldıktan sonra lisans geri kazanılır.

Uygun cihaza sahip bir kullanıcı ilk olarak bir VPP uygulaması yüklemeye çalıştığında kullanıcıdan Apple Toplu Satın Alma programına katılması istenir. Uygulama yüklemesi devam etmeden önce bunu yapmaları gerekir.

> [!TIP] Uygulamanın dağıtıldığı her kullanıcının kabul durumunu görmek için **VPP Koşulları Durumu** sütununa bakın.

Başka bir lisans yoksa dağıtım başarısız olur.

## Apple VPP uygulamalarını izlemek için
Hangi VPP uygulamalarının dağıtıldığını ve kaç tane lisansın kullanıldığını **Yönetilen Yazılım** &gt; **Toplu Satın Alma Uygulamaları** düğümündeki **Uygulamalar** çalışma alanından izleyebilirsiniz.

> [!TIP] Her uygulama yüklemesinin durumunu incelemek için uygulama **Filtrelerini** de kullanabilirsiniz.

### Ayrıca Bkz.
[Microsoft Intune'da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md)



<!--HONumber=May16_HO4-->


