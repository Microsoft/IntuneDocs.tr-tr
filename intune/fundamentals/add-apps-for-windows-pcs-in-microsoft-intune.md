---
title: Intune yazılım istemcisi çalıştıran Windows bilgisayarlarına uygulama ekleme
titleSuffix: Microsoft Intune
description: Windows bilgisayarlarına yönelik uygulamaları dağıtmadan önce Intune’a eklemeyi öğrenmek için bu konu başlığı altında verilen bilgileri kullanın.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/29/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 23868303d598be1bc2e45f0852edfd3cf8338ab3
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509148"
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Intune yazılım istemcisi çalıştıran Windows bilgisayarlarına uygulama ekleme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Uygulamaları dağıtmadan önce Intune’a eklemeyi öğrenmek için bu konu başlığı altında verilen bilgileri kullanın.

> [!IMPORTANT]
> Bu konu başlığı altında sağlanan bilgiler, Intune yazılım istemcisi kullanarak yönettiğiniz Windows bilgisayarlarına uygulama eklemenize yardımcı olur. Kayıtlı Windows bilgisayarları ve diğer mobil cihazlar için uygulama eklemek istiyorsanız bkz. [Microsoft Intune’a uygulama ekleme](../apps/apps-add.md).

Uygulamaların bilgisayarlara yüklenebilmesi için, hiçbir kullanıcı etkileşimi olmadan sessiz bir şekilde yüklenmeleri gerekir. Eğer böyle yapılmazsa yükleme başarısız olur.

## <a name="additional-security-settings-for-windows-installer"></a>Windows Installer için ek güvenlik ayarları
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabilirsiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebilirsiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılmıştır. 

## <a name="add-the-app"></a>Uygulama ekleme
Aşağıdaki yordamı izleyerek uygulamanın özelliklerini yapılandırmak ve uygulamayı bulut depolama alanınıza yüklemek için Intune Yazılım Yayımcısı’nı kullanacaksınız.

1. Intune Yazılım Yayımcısını başlatmak için [Microsoft Intune yönetim konsolu](https://manage.microsoft.com)’nda **Uygulamalar** &gt; **Uygulama Ekle**‘yi seçin.

   > [!TIP]
   > Yayımcının başlatılması için önce Intune kullanıcı adınızı ve parolanızı girmeniz gerekebilir.

2. Yayımcının **Yazılım kurulumu** sayfasında, **bu yazılımın cihazlar için kullanılabilir duruma nasıl getirileceğini seçin** alanının altında **Yazılım yükleyicisini** seçin ve aşağıdakileri belirtin:

   - **Yazılım yükleyicisi dosya türünü seçin**. Bu, dağıtmak istediğiniz yazılım türünü belirtir. Windows bilgisayarları için, **Windows Installer**’ı seçin.
   - **Yazılım kurulum dosyalarının konumunu belirtin**. Yükleme dosyalarının konumunu girin veya **Gözat**’ı seçerek bir listeden konumu seçin.
   - **Aynı klasörden başka dosya ve alt klasör ekleme**. Windows Installer kullanan bazı yazılımlar destekleme dosyaları gerektirir. Bu dosyalar yükleme dosyası ile aynı klasörde bulunmalıdır. Bu destek dosyalarını dağıtmak istiyorsanız bu seçeneği belirtin.

   Örneğin, Intune’a Application.msi adlı bir uygulama yüklemek isterseniz sayfa şöyle görünür: ![Yayımcının yazılım kurulum sayfası](./media/add-apps-for-windows-pcs-in-microsoft-intune/publisher-for-pc.png)

   Bu yükleme türünde, bulut depolama alanınızın bir bölümü kullanılır.

3. **Yazılım açıklaması** sayfasında aşağıdakileri yapılandırın.

   > [!NOTE]
   > Kullanmakta olduğunuz yükleyici dosyasına bağlı olarak bu değerlerden bazıları otomatik olarak girilmiş olabilir veya gösterilmeyebilir.

   - **Yayımcı**. Uygulama yayımcısının adını girin.
   - **Ad**. Uygulamanın şirket portalında görüntülenecek olan adını girin.<br />Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
   - **Açıklama**. Uygulama için bir açıklama girin. Bu, şirket portalında kullanıcılara görüntülenir.
   - **Yazılım bilgileri URL’si** (isteğe bağlı). Bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
   - **Gizlilik URL’si** (isteğe bağlı). Bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
   - **Kategori** (isteğe bağlı). Yerleşik uygulama kategorilerinden birini seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
   - **Simge** (isteğe bağlı). Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.

4. **Gereksinimler** sayfasında uygulamanın cihaza yüklenmesinden önce karşılanması gereken gereksinimleri belirtin. Aşağıdakilerden birini seçin:

   - **Mimari**. Bu uygulamanın 32 bit işletim sistemlerine, 64 bit işletim sistemlerine veya ikisine de yüklenebileceğini belirtin.
   - **İşletim Sistemi**. Bu uygulamanın üzerine yüklenebileceği en düşük işletim sistemini seçin.

5. **Algılama kuralları** sayfasında yapılandırmakta olduğunuz uygulamanın bir bilgisayarda zaten yüklü olup olmadığını algılamak için kurallar yapılandırabilirsiniz. Veya varsayılan algılama kurallarını, önceden yüklenmiş tüm uygulama sürümlerinin otomatik olarak üzerine yazılması için kullanabilirsiniz. Bu seçenek Windows Installer içindir (yalnızca .exe dosyaları).

   Yapılandırabileceğiniz kurallar şunlardır:
   - **Dosya var**. Algılanmasını istediğiniz dosyanın yolunu belirtin. Bu yolu bilgisayarda **%ProgramFiles%** altında arayabileceğiniz gibi (**Program Files**\&lt;path&gt; ve **Program Files (x86)** \&lt;path&gt; altında arar), ya da **%SystemDrive%** altında da arayabilirsiniz (bilgisayarın kök sürücüsünde, genellikle C sürücüsü altında arar).
   - **MSI ürün kodu var**. **Gözat**’ı seçerek algılamak istediğiniz Windows Installer (.msi) dosyasını seçin.
   - <strong>Kayıt defteri anahtarı var</strong>. <strong>HKEY_LOCAL_MACHINE\</strong> ile başlayan bir kayıt defteri anahtarı belirtin. Hem 32 bit hem de 64 bit kayıt defteri yollarında arama yapılır. Belirttiğiniz anahtar iki konumdan birinde varsa, algılama kuralına uyulmuş olur.

   Uygulama yapılandırdığınız kurallardan herhangi birine uyuyorsa, yüklenmez.

6. Yalnızca **Windows Installer** dosya türü için (msi ve exe): **Komut satırı bağımsız değişkenleri** sayfasında, yükleyici için isteğe bağlı komut satırı bağımsız değişkenleri eklemek isteyip istemediğinizi belirtin.
   Aşağıdaki parametreler, Intune tarafından otomatik olarak eklenmiştir:
   - .exe dosyaları için, **/install** eklenmiştir.
   - .msi dosyaları için, **/quiet** eklenmiştir.
   Bu ayarların, yalnızca uygulama paketini oluşturan kişinin bu işlevi etkinleştirdiğinde çalışacağını unutmayın.

7. Yalnızca **Windows Installer** dosya türü için (yalnızca exe): **Dönüş kodları** sayfasında, uygulama yönetilen bir Windows bilgisayarına yüklenirken Intune tarafından yorumlanacak yeni hata kodları ekleyebilirsiniz.

   Intune, varsayılan olarak, bir uygulama paketi yüklemesinin başarılı veya başarısız olduğunu raporlamak için sektör standardı dönüş kodlarını kullanır: **0** (Başarılı) veya **3010** (Yeniden başlatma ile başarılı). Listeye kendi dönüş kodlarınızı da ekleyebilirsiniz. Dönüş kodları listesini belirtirseniz ve uygulama yüklemesi listede olmayan bir kod döndürürse, bu kod hata olarak yorumlanır.

8. **Özet** sayfasında, belirttiğiniz bilgileri gözden geçirin. Hazır olduğunuzda **Karşıya Yükle**’yi seçin.

9. Bitirmek için **Kapat**’a tıklayın.

Uygulama, **Uygulamalar** çalışma alanının **Uygulamalar** düğümünde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

Bir uygulama oluşturduktan sonra, sonraki adım uygulamayı dağıtmaktır. Daha fazla bilgi edinmek için bkz. [Microsoft Intune ile uygulamaları gruplara atama](../apps/apps-deploy.md).

Windows bilgisayarlara yazılım dağıtmak için ipuçları ve püf noktaları hakkında daha fazla edinmek isterseniz [Destek İpucu: Intune Yazılımının Bilgisayarlara Dağıtımı için En İyi Uygulamalar](https://support.microsoft.com/en-US/help/2583929) blog gönderisini inceleyin.
