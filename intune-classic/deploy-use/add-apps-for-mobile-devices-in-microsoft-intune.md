---
title: Kaydolmuş cihazlar için uygulama ekleme
description: Bir uygulamayı dağıtabilmeniz için, onu önce Intune'a eklemeniz gerekir. Ardından Intune konsolunda kullanılabilir hale gelir, buradan dağıtabilir ve yönetebilirsiniz.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 01/11/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f5fec22a17eef39819b38567793a2f579815e59
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="add-apps-for-enrolled-devices-to-intune"></a>Kaydolmuş cihazlar için Intune’a uygulamalar ekleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir uygulamayı dağıtabilmeniz veya yönetebilmeniz için, onu önce Microsoft Intune’a eklemeniz gerekir. Bu konuda, kayıtlı cihazlar için nasıl uygulama ekleyeceğiniz gösterilir.


> [!IMPORTANT]
> Bu konu başlığı altında verilen bilgiler, kayıtlı cihazlara ve kayıtlı Windows bilgisayarlarına dağıtmak istediğiniz uygulamaları eklemenize yardımcı olur. Uygulamaları, Intune istemci yazılımını kullanarak yönettiğiniz Windows bilgisayarlarına eklemek istiyorsanız, [Microsoft Intune’da Windows bilgisayarları için uygulama ekleme](add-apps-for-windows-pcs-in-microsoft-intune.md) konusuna göz atın.

## <a name="add-the-app"></a>Uygulama ekleme
Uygulamanın özelliklerini yapılandırmak ve uygulamayı bulut depolama alanınıza yüklemek için (uygunsa) Intune Yazılım Yayımcısı’nı kullanacaksınız. Aşağıdaki yordamı kullanın:

1.  Intune Yazılım Yayımcısını başlatmak için [Microsoft Intune yönetim konsolu](https://manage.microsoft.com)’nda **Uygulamalar** &gt; **Uygulama Ekle**‘yi seçin.

    > [!TIP]
    > Yayımcının başlatılması için önce Intune kullanıcı adınızı ve parolanızı girmeniz gerekebilir.

2.  Yayımcının **Yazılım kurulumu** sayfasında, **Bu yazılımın cihazlar için kullanılabilir duruma nasıl getirileceğini seçin** alanında aşağıdaki seçeneklerden birini belirtin:
    - **Yazılım yükleyicisi**, uzantısı **.msi** olan uygulamalar için:
        - **Yazılım yükleyicisi dosya türünü seçin**. Bu, dağıtmak istediğiniz yazılım türünü belirtir. Örneğin bir iOS uygulamasını yüklemek istiyorsanız, **iOS için Uygulama Paketi (&#42;.ipa dosyası)** öğesini seçin.
        - **Yazılım kurulum dosyalarının konumunu belirtin**. Yükleme dosyalarının konumunu girin veya **Gözat**’ı seçerek bir listeden konumu seçin.
        - **Aynı klasörden başka dosya ve alt klasör ekleme**. Bu seçenek yalnızca **Windows Installer** dosya türü içindir.<br>Windows Installer’ı kullanan bazı yazılımlar için genellikle yükleme dosyalarıyla aynı klasörde yer alan destek dosyaları gerekir. Bu dosyaları dağıtmak istiyorsanız bu seçeneği belirtin.<br>Bu yükleme türünde, bulut depolama alanınızın bir bölümü kullanılır.

  -   **Dış bağlantı**; uygulama mağazasının bağlantısını belirterek oluşturmak istediğiniz uygulamalar için:

        - **URL’yi belirtin**. Aşağıdakilerden birinin URL'sini belirtin:
            - Dağıtmak istediğiniz uygulamanın uygulama mağazası URL’si. Örneğin Android için Microsoft Uzak Masaüstü uygulamasını dağıtmak istiyorsanız, **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android** seçeneğini belirtin.<br>Uygulamanın URL’sini bulmak için bir arama motoru kullanarak uygulamayı içeren mağaza sayfasını bulun. Örneğin, Uzak Masaüstü uygulamasını bulmak için **Microsoft Uzak Masaüstü Android** araması yapabilirsiniz.
            - Bir web sitesi. Intune, cihaza sitenin bir kısayol simgesini (web klibi olarak bilinir) dağıtır.
            - Web üzerinde bir uygulama. Intune, cihaza uygulamanın bir kısayol simgesini dağıtır.
        - **Bu bağlantıyı açmak için yönetilen bir tarayıcı isteyin (yalnızca Android ve iOS için)**. Kullanıcılara bir web sitesi veya web uygulamasının bağlantısını dağıttığınızda bunu yalnızca Intune ile yönetilen tarayıcıda açabilirler. Bu tarayıcı cihazlarında yüklü olmalıdır.<br>Yönetilen tarayıcı hakkında daha fazla bilgi için bkz. [Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).<br>Bu yükleme türünde, bulut depolama alanınızın hiçbir bölümü kullanılmaz.

  -   **Uygulama mağazasından yönetilen iOS uygulaması**; iTunes mağazasından ücretsiz sağlanan ve mobil uygulama yönetimi MAM ilkeleriyle yönetmek istediğiniz uygulamalar için aşağıdakileri belirtin:

        - **URL’yi belirtin**. Dağıtmak istediğiniz uygulamanın uygulama mağazası URL’sini girin. Örneğin iOS için Microsoft Çalışma Klasörleri uygulamasını dağıtmak istiyorsanız, **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8** seçeneğini belirtin.<br>Bu yükleme türünde, bulut depolama alanınızın hiçbir bölümü kullanılmaz.

        Örneğin, cihazlara iTunes mağazasından Microsoft Word uygulamasını dağıtmak istiyorsanız, sayfa şuna benzer görünür:

        ![Intune Software Publisher](./media/publisher-for-mobile.png)

> [!NOTE]
> Bir mağazadan uygulama eklediğinizde ve dağıttığınızda, son kullanıcıların uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.

3.  **Yazılım açıklaması** sayfasında aşağıdakileri yapılandırın:

    > [!TIP]
    > Kullanmakta olduğunuz yükleyici türüne bağlı olarak, bu değerlerden bazıları otomatik olarak girilmiş olabilir.

    - **Yayımcı**. Uygulama yayımcısının adını girin.
    - **Ad**. Uygulamanın şirket portalında görüntülenecek olan adını girin.<br>Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama**. Uygulama için bir açıklama girin. Bu, şirket portalında kullanıcılara görüntülenir.
    - **Yazılım bilgileri URL'si**. Yalnızca **Yazılım yükleyicisini** seçtiğinizde kullanılabilir. İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**. Yalnızca **Yazılım yükleyicisini** seçtiğinizde kullanılabilir. İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Kategori** (isteğe bağlı). Yerleşik uygulama kategorilerinden birini seçin. Bu, kullanıcıların şirket portalına göz atarken uygulamaları daha kolay bulabilmesini sağlar.
    - **Şirket portalında bu uygulamayı öne çıkan uygulama olarak görüntüleyin ve vurgulayın**. Kullanıcılar uygulamalara göz attığında, uygulamayı şirket portalının ana sayfasında önce çıkacak şekilde görüntüleyin.
    - **Simge** (isteğe bağlı). Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenecek olan simgedir.

        Bu örnekte, iOS için Microsoft Word uygulamasının açıklamasını yapılandırdınız:

        ![Yazılım açıklaması örneği](./media/ios-software-description.png)

4.  **Gereksinimler** sayfasında uygulamanın cihaza yüklenmesinden önce karşılanması gereken gereksinimleri belirtin. Örneğin, iOS uygulama paketi için gerekli en düşük iOS sürümünü seçebilirsiniz. Ayrıca uygulamanın yükleneceği cihazı seçebilirsiniz (iPhone ya da iPad gibi).

    > [!TIP]
    > **Gereksinimler** sayfası tüm uygulama türleri için görüntülenmez.

5.  **Windows Installer** dosya türünü seçtiğinizde başka sihirbaz sayfaları da görüntülenir. Windows 10 veya sonrasını çalıştıran ve Intune’a kayıtlı bilgisayarlara yazılım dağıttığınızda bu dosya türü kullanılır.

6.  **Özet** sayfasında, belirttiğiniz bilgileri gözden geçirin. Hazır olduğunuzda **Karşıya Yükle**’yi seçin.

7.  Bitirmek için **Kapat**’a tıklayın.

Uygulama, **Uygulamalar** çalışma alanının **Uygulamalar** düğümünde görüntülenir.

## <a name="example---deploying-msi-applications-to-windows-10-devices"></a>Örnek - Windows 10 cihazlarına .msi uygulamalarını dağıtma
Bu dört dakikalık videoda, Windows 10 çalıştıran kayıtlı cihazlar için Windows Installer (.msi) uygulamaların nasıl dağıtılacağı hakkında bilgi edineceksiniz.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## <a name="next-steps"></a>Sonraki adımlar

Bir uygulama oluşturduktan sonra, sonraki adım uygulamayı dağıtmaktır. Daha fazlası için [Microsoft Intune’da uygulamaları dağıtma](deploy-apps.md) konusuna göz atın.
