---
title: "Toplu satın alınan iOS uygulamalarını yönetme"
description: "Apple’dan toplu satın aldığınız uygulamaları Intune kullanarak yönetebilirsiniz. Lisans bilgilerini uygulama deposundan içeri aktarabilirsiniz, kaç lisans kullandığınızı izleyebilirsiniz ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önlenir."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5da29dceb5308eab72e5b24e220586aa739982ea
ms.sourcegitcommit: 1afff0fd464ece84ffea6bc0c71c78215d59e696
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2017
---
# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile toplu satın alma programından satın aldığınız iOS uygulamalarını yönetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Bu durum, satın alınan uygulamaların birden fazla kopyasın izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

Microsoft Intune lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önleyerek, bu program aracılığıyla satın aldığınız uygulamaları yönetmenize yardımcı olur.

> [!Important]
> Intune, şu anda iOS İş için Toplu Satın Alma Programı (VPP) uygulama lisanslarını cihazlara değil kullanıcılara atamaktadır. Bu nedenle, kullanıcıların uygulamayı yüklemek için Apple Kimliği parolalarını girmeleri gerekir.
> Eğitim için Apple Volume Purchase Program ve B2B uygulamaları, bu sürümde desteklenmiyor.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS cihazları için toplu satın alınan uygulamaları yönetme
[Apple İş için Toplu Satın Alma Programı](http://www.apple.com/business/vpp/) ile iOS için birden çok lisans satın alırsınız. Buna Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve bunu Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdakileri anlamanız gerekir:

* Intune, 256’ya kadar VPP belirtecinin eklenmesini destekler.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS VPP kullanmaya başlamadan önce diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan tüm var olan VPP kullanıcı hesaplarını kaldırın. Intune bu kullanıcı hesaplarını bir güvenlik önlemi olarak Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmetinden verileri eşitler.
* iOS VPP uygulamalarını Cihaz Kayıt Protokolü (DEP) kullanarak kullanıcının kaydedilen cihazlarına dağıtabilmeniz için cihazın kullanıcı benzeşiminin yapılandırılmış olması gerekir.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Yönetim** &gt; **iOS ve Mac OS X** &gt; **Volume Purchase Program**’ı seçin.

2.  **Apple VPP Hesabı** bağlantısını seçin. Henüz yapmadıysanız İş için Toplu Satın Alma Programı’na kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin.

3.  Intune konsolunun **Apple Volume Purchase Program (VPP) Yönetimi** sayfasında **VPP belirtecini karşıya yükle**’yi seçin.

4.  **VPP belirtecini karşıya yükle** iletişim kutusunda, VPP belirteç adını ve Apple Kimliğinizi girin veya yapıştırın ve sonra **Karşıya Yükle**’yi seçin.

5.  Uyarı iletişim kutusunda, ileride başka bir VPP hesabına geçemeyeceğinizi anladığınızı gösteren kutuyu işaretleyin ve sonra **Evet**’i seçin.

**Toplu Satın Alma Programı** sayfasında bundan böyle Apple VPP hakkında en son ne zaman güncelleştirildiği, ne zaman sona ereceği ve Intune ile en son ne zaman eşitlendiği gibi bilgileri görüntüleyebilirsiniz.

İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## <a name="to-deploy-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı dağıtmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Uygulamalar** &gt; **Uygulamalar** &gt; **Toplu Satın Alınmış uygulamalar**’ı seçin. Bu listede, Apple VPP hizmetinden eşitlenmiş olan tüm uygulamalar gösterilir.

2.  Dağıtmak istediğiniz uygulamayı seçin, **Dağıtımı Yönet**’i seçin ve sonra uygulamayı karşıya yüklemeyi, oluşturmayı ve dağıtmayı tamamlamak için [Microsoft Intune’da uygulama dağıt](deploy-apps-in-microsoft-intune.md) konusundaki yönergeleri kullanın.

> [!TIP]
> **Gerekli** şeklinde bir dağıtım eylemi seçmeniz gerekir. Kullanılabilir yüklemeler şu anda desteklenmiyor. Ayrıca, uygulamayı yalnızca kullanıcı gruplarına dağıtabilirsiniz.

Uygulamayı **Gerekli** bir yükleme olarak dağıttığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır.

Bir lisansı geri kazanmak için dağıtım eylemini **Kaldır** olarak değiştirmeniz gerekir. Uygulama kaldırıldıktan sonra lisans geri kazanılır.

Uygun cihaza sahip bir kullanıcı ilk olarak bir VPP uygulaması yüklemeye çalıştığında kullanıcıdan Apple Toplu Satın Alma programına katılması istenir. Uygulama yüklemesi devam etmeden önce bunu yapmaları gerekir.

Daha fazla kullanılabilir lisans yoksa dağıtım başarısız olur.

## <a name="to-monitor-apple-vpp-apps"></a>Apple VPP uygulamalarını izlemek için
Hangi VPP uygulamalarının dağıtıldığını ve kaç lisansın kullanıldığını **Toplu Satın Alınmış Uygulamalar** düğümündeki **Uygulamalar** çalışma alanından izleyebilirsiniz.

> [!TIP]
> Her bir uygulama yüklemesinin durumunu incelemek için uygulama **Filtreleri**’ni de kullanabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune'da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md)
