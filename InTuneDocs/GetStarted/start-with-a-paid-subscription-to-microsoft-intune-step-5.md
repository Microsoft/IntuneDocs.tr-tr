---
# required metadata

title: Kullanıcıları ve cihazları düzenlemek için grup oluşturma | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Kullanıcıları ve cihazları düzenlemek için grup oluşturma
Intune’daki gruplar, cihazlarınızı ve kullanıcılarınızı yönetmek için büyük esneklik sağlar. Grupları kuruluş gereksinimlerinize (örneğin, coğrafi konum, bölüm veya donanım özelliklerine göre) uygun şekilde ayarlayabilir ve bunları bir kullanıcı kümesi için ilke dağıtmaktan bir cihaz kümesine uygulama dağıtmaya kadar çeşitli yönetim görevlerini gerçekleştirmek için kullanabilirsiniz.

Hem cihaz hem de kullanıcı grupları Intune yönetim konsolunun GRUPLAR çalışma alanında oluşturulur.

![Yönetim konsolu gruplar çalışma alanı](./media/groups.png)


> Grupları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)


## Bir cihaz grubu oluşturma
Uygulamalar ve güncelleştirmeler dağıtmak ve diğer özellikleri yapılandırmak için cihaz gruplarını kullanın. Örneğin, aşağıdaki adımları kullanarak bir "Cihazlarım" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** > **Genel bakış** > **Grup Oluştur**’u seçin.

2.  **Grup adı** olarak "Cihazlarım" yazın, üst grup listesinden **Tüm Cihazlar**'ı seçin ve ardından **İleri**'yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında, **Tüm cihazlar** 'ı seçerek grubun hem mobil cihazları hem bilgisayarları içerdiğini belirtin.

4.  **Doğrudan Üyeliği Tanımla** sayfasında **İleri**'yi seçin. Önceden tüm cihazları içermeyen bir grup oluşturduysanız ve yeni grubunuza belirli cihazları eklemek istiyorsanız, bunu burada yapabilirsiniz.

5.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

**Gruplar** çalışma alanının **Tüm Cihazlar** bölümündeki **Gruplar** listesinde yeni oluşturulan grubu bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

## Bir kullanıcı grubu oluşturma
Yazılım ve cihaz ilkelerini dağıtmak için kullanıcı gruplarını kullanın. Örneğin, aşağıdaki adımları kullanarak bir "Intune Kullanıcıları" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** > **Genel bakış** > **Grup Oluştur**’u seçin.

2.  **Grup adı** olarak "Intune Kullanıcıları" yazın, üst grup listesinden **Tüm Kullanıcılar**'ı seçin ve ardından **İleri**'yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında **Şununla grup üyeliği başlat:** seçeneğini **Üst gruptaki tüm kullanıcılar** olarak ayarlayın.

4.  **Şu güvenlik gruplarındaki üyeleri çıkar:**seçeneğinin yanında **Gözat**’ı seçin ve ardından **Şirket Yöneticisi**'ni seçin. Bu dışlama, Şirket Yöneticisi hesabını (kiracı yönetici olarak da bilinir) etkilemeden Intune Kullanıcıları grubunu yönetmenize olanak verir.

5.  **Doğrudan Üyeliği Tanımla** sayfasında **İleri**'yi seçin. Intune Kullanıcıları grubunun, Şirket Yöneticisi dışında tüm kullanıcıları içermesini istediğinizden, burada bir şey yapmanız gerekmez.

6.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Tüm Kullanıcılar** bölümündeki **Gruplar** listesinde bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.



### Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* 5. adımını tamamlamış oldunuz.

>[!div class="step-by-step"]

>[&larr; **Intune lisanslarını yönetme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**İlkeler ve uygulamalar oluşturma** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  


<!--HONumber=May16_HO2-->


