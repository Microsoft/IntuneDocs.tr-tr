---
title: "Kullanıcıları ve cihazları düzenlemek için grup oluşturma | Microsoft Docs"
description: "Intune aboneliğiniz için kullanıcı ve grup oluşturma"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: 446156265047994f0a15890d7699991d032c0bd5


---


# <a name="create-groups-to-organize-users-and-devices"></a>Kullanıcıları ve cihazları düzenlemek için grup oluşturma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune’daki gruplar, cihazlarınızı ve kullanıcılarınızı yönetmek için büyük esneklik sağlar. Grupları kuruluş gereksinimlerinize (örneğin, coğrafi konum, bölüm veya donanım özelliklerine göre) uygun şekilde ayarlayabilir ve bunları bir kullanıcı kümesi için ilke dağıtmaktan bir cihaz kümesine uygulama dağıtmaya kadar çeşitli yönetim görevlerini gerçekleştirmek için kullanabilirsiniz.

## <a name="group-management-moving-to-azure-ad"></a>Grup yönetimi Azure AD'ye taşınıyor

**Kasım 2016'dan itibaren**, yeni hesaplar kullanıcı ve cihaz gruplarını Azure Active Directory (AD) portalında yönetecektir. Aralık 2016’da, Intune ürün ekibi mevcut müşterileri yeni Azure AD tabanlı grup yönetimi deneyimine geçirmeye başlayacaktır. Tüm kullanıcı ve cihaz grupları Azure AD güvenlik gruplarına geçirilecektir. Günlük çalışmalarınız üzerindeki etkisini en aza indirmeden ve kullanıcılarınızı hiçbir şekilde etkilemeyeceğini düşünene kadar geçiş işlemlerine başlamayacağız. Hesabınızı taşımadan önce bildirimde de bulunacağız.


>[!IMPORTANT]
>
>Intune portalında Gruplar çalışma alanını açar ve Azure Active Directory portalına bağlantı içeren **Intune kullanıcı grupları artık Azure Active Directory'de gruplar olarak yönetiliyor** iletisi görürseniz, Intune'da grup yönetimi için *yeni* Azure AD güvenlik gruplarını kullanıyorsunuz demektir. Grup oluşturmayı öğrenmek için bkz. [Azure Active Directory'de grupları yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
>
>Azure AD portalı bağlantısını görmüyorsanız, grup yönetimi için Intune portalını kullanıyorsunuz demektir.

## <a name="group-management-in-the-intune-portal"></a>Intune portalında grup yönetimi

Hem cihaz hem de kullanıcı grupları Intune yönetim konsolunun GRUPLAR çalışma alanında oluşturulur.

![Yönetim konsolu gruplar çalışma alanı](./media/groups.png)


> [!TIP]
> Grupları kullanma hakkında daha fazla bilgi için, bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).


## <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma
Uygulamalar ve güncelleştirmeler dağıtmak ve diğer özellikleri yapılandırmak için cihaz gruplarını kullanın. Örneğin, aşağıdaki adımları kullanarak bir "Cihazlarım" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** > **Genel Bakış** > **Grup Oluştur**’u seçin.

2.  **Grup adı** olarak "Cihazlarım" yazın, üst grup listesinden **Tüm Cihazlar**'ı seçin ve ardından **İleri**'yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında, **Tüm cihazlar** 'ı seçerek grubun hem mobil cihazları hem bilgisayarları içerdiğini belirtin.

4.  **Doğrudan Üyeliği Tanımla** sayfasında **İleri**'yi seçin. Önceden tüm cihazları içermeyen bir grup oluşturduysanız ve yeni grubunuza belirli cihazları eklemek istiyorsanız, bunu burada yapabilirsiniz.

5.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

**Gruplar** çalışma alanının **Tüm Cihazlar** bölümündeki **Gruplar** listesinde yeni oluşturulan grubu bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

## <a name="create-a-user-group"></a>Bir kullanıcı grubu oluşturma
Yazılım ve cihaz ilkelerini dağıtmak için kullanıcı gruplarını kullanın. Örneğin, aşağıdaki adımları kullanarak bir "Intune Kullanıcıları" grubu oluşturun:

1.  [Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** > **Genel Bakış** > **Grup Oluştur**’u seçin.

2.  **Grup adı** olarak "Intune Kullanıcıları" yazın, üst grup listesinden **Tüm Kullanıcılar**'ı seçin ve ardından **İleri**'yi seçin.

3.  **Üyelik Ölçütlerini Tanımla** sayfasında **Şununla grup üyeliği başlat:** seçeneğini **Üst gruptaki tüm kullanıcılar**olarak ayarlayın.

4.  **Şu güvenlik gruplarındaki üyeleri çıkar:**seçeneğinin yanında **Gözat**’ı seçin ve ardından **Şirket Yöneticisi**'ni seçin. Bu dışlama, Şirket Yöneticisi hesabını (kiracı yönetici olarak da bilinir) etkilemeden Intune Kullanıcıları grubunu yönetmenize olanak verir.

5.  **Doğrudan Üyeliği Tanımla** sayfasında **İleri**'yi seçin. Intune Kullanıcıları grubunun, Şirket Yöneticisi dışında tüm kullanıcıları içermesini istediğinizden, burada bir şey yapmanız gerekmez.

6.  **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Son**'u seçin.

Yeni oluşturulan grubu **Gruplar** çalışma alanının **Tüm Kullanıcılar** bölümündeki **Gruplar** listesinde bulabilirsiniz. Ayrıca, buradan grubu düzenleyebilir veya silebilirsiniz.

>[!div class="step-by-step"]

>[&larr; **Intune lisanslarını yönetme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**İlkeler ve uygulamalar oluşturma** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  



<!--HONumber=Jan17_HO2-->


