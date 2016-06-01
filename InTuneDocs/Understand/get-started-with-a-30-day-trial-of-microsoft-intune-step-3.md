---
# required metadata

title: Değerlendirme aboneliği kullanıcılarını ve cihazlarını düzenlemek için gruplar oluşturun | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Değerlendirme aboneliği kullanıcılarını ve cihazlarını düzenlemek için gruplar oluşturun
Intune’daki gruplar, cihazlarınızı ve kullanıcılarınızı yönetmek için büyük esneklik sağlar. Grupları kuruluş gereksinimlerinize (örneğin, coğrafi konum, bölüm veya donanım özelliklerine göre) uygun şekilde ayarlayabilir ve bunları bir kullanıcı kümesi için ilke ayarlamaktan bir cihaz kümesi için uygulama dağıtmaya kadar çeşitli yönetim görevlerini gerçekleştirmek için kullanabilirsiniz.

## Bir cihaz grubu oluşturma
Yazılım ve güncelleştirme dağıtmak ve Microsoft Intune Aracısı Ayarları ile Windows Güvenlik Duvarı Ayarları ilkelerini yapılandırmak için cihaz gruplarını kullanabilirsiniz. Örneğin, aşağıdaki adımları kullanarak bir "Deneme Cihazlarım" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin

2.  **Grup adı**için, “Deneme Cihazlarım” yazın, üst grup listesinden **Tüm Cihazlar**'ı seçin ve ardından **İleri**'yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında, **Tüm cihazlar** 'ı seçerek grubun hem mobil cihazları hem bilgisayarları içerdiğini belirtin.

4.  **Doğrudan Üyeliği Tanımla** sayfasında, **İleri**'yi seçin. Önceden tüm cihazları içermeyen bir grup oluşturduysanız ve yeni grubunuza belirli cihazları eklemek istiyorsanız, bunu burada yapabilirsiniz.

5.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Tüm Cihazlar** bölümündeki **Gruplar**listesinde bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

## Bir kullanıcı grubu oluşturma
Yazılım ve cihaz ilkelerini dağıtmak için kullanıcı gruplarını kullanın. Örneğin, aşağıdaki adımları kullanarak bir "Deneme Kullanıcılarım" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Genel Bakış** &gt; **Grup Oluştur**’u seçin

2.  **Grup adı** için, “Deneme Kullanıcılarım” yazın, üst grup listesinden **Tüm Kullanıcılar**’ı seçin ve ardından **İleri**’yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında **Şununla grup üyeliği başlat:** seçeneğini **Üst gruptaki tüm kullanıcılar**olarak ayarlayın

4.  **Şu güvenlik gruplarındaki üyeleri çıkar:**seçeneğinin yanında **Gözat**’ı seçin ve ardından **Şirket Yöneticisi**'ni seçin. Bu dışlama, Şirket Yöneticisi hesabını (kiracı yönetici olarak da bilinir) etkilenmeden Deneme Kullanıcılarım grubunu yönetmenize olanak verir.

5.  **Doğrudan Üyeliği Tanımla** sayfasında, **İleri**'yi seçin. Deneme Kullanıcılarım grubunun Şirket Yöneticisi dışında tüm kullanıcıları içermesini istediğinizden, burada bir şey yapmanız gerekmez.

6.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Tüm Kullanıcılar** bölümündeki **Gruplar**listesinde bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

Grupları kullanma hakkında daha fazla bilgi için, bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune)

### Sonraki adımlar
Tebrikler! *Microsoft Intune değerlendirme* gözden geçirmesinin 3. adımını tamamladınız.

>[!div class="step-by-step"]

>[&larr; **Kullanıcı ekleme**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md)     [**İlkeler oluşturma** &larr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  


<!--HONumber=May16_HO2-->


