---
title: Microsoft Intune Windows 10 için Microsoft Edge ekleyin
titleSuffix: ''
description: Windows için Microsoft Edge 'i Microsoft Intune 'e ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d5082376c42ff3b92e3979a53b6deac3e59c88e
ms.sourcegitcommit: 32391f74241ee3289a76ccd5319fe700b800d427
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2020
ms.locfileid: "77075816"
---
# <a name="add-microsoft-edge-for-windows-10-to-microsoft-intune"></a>Microsoft Intune Windows 10 için Microsoft Edge ekleyin

Uygulamaları dağıtmadan, yapılandırmadan, izleyebilmeniz veya koruyabilmeniz için önce bunları Intune 'a eklemeniz gerekir. Kullanılabilir [uygulama türlerinden](~/apps/apps-add.md#app-types-in-microsoft-intune) biri Microsoft Edge *Sürüm 77 ve üzeri*. Intune 'da bu uygulama türünü seçerek, Microsoft Edge *sürüm 77 ve üstünü* Windows 10 çalıştıran yönettiğiniz cihazlara atayabilir ve yükleyebilirsiniz.

> [!IMPORTANT]
> Bu uygulama türü **genel önizlemede** bulunur ve Windows 10 için kararlı, Beta ve geliştirme kanalları sunmaktadır. Dağıtım yalnızca Ingilizce (EN) ' dir, ancak son kullanıcılar tarayıcıdaki görüntüleme dilini **ayarlar** > **dilleri**altında değiştirebilir. Microsoft Edge, sistem bağlamında ve benzer mimarilere (x86 IŞLETIM sisteminde x86 uygulaması ve x64 IŞLETIM sisteminde x64 uygulaması) yüklenen bir Win32 uygulamasıdır. Intune, önceden varolan Microsoft Edge yüklemelerini algılar. Kullanıcı bağlamında yüklüyse, bir sistem yüklemesi bu dosyanın üzerine yazar. Sistem bağlamına yüklenirse, ınstallıon başarısı raporlanır. Ayrıca, Microsoft Edge 'in otomatik güncelleştirmeleri varsayılan olarak **Açık** .

> [!NOTE]
> Microsoft Edge *sürüm 77 ve üzeri* , MacOS için de kullanılabilir.
> 
> Çalışma alanına katılma bilgisayarları için Microsoft Edge 'in yerleşik uygulama dağıtımını kullanamazsınız. Yerleşik uygulama dağıtımı, yalnızca AAD 'ye katılmış cihazlar için mevcut olan Intune yönetim uzantısını gerektirir. Microsoft Edge *sürüm 77 ve üstünü* **uygulamalara**yüklenmiş bir *. msi* kullanarak dağıtmaya devam edebilirsiniz. [Microsoft Intune için Windows iş kolu uygulaması ekleme](~/apps/lob-apps-windows.md)bölümüne bakın.

## <a name="prerequisites"></a>Önkoşullar
- Windows 10 RS2 ve üzeri gereklidir.
- Kullanıcı bağlamlarındaki tüm kanallar için Microsoft Edge *sürüm 77 ve üzeri* sürümlerin önceden yüklenmiş sürümlerinin, sistem bağlamında yüklü olan bir kenara üzerine yazılır.

## <a name="configure-the-app-in-intune"></a>Uygulamayı Intune 'da yapılandırma
Aşağıdaki adımları kullanarak Intune 'a bir Microsoft Edge sürüm 77 ve üzeri ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Microsoft Edge, sürüm 77 ve üzeri**altındaki **uygulama türü** listesinde **Windows 10**' u seçin.

## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma
Bu adımda, bu uygulama dağıtımı hakkında bilgi sağlarsınız. Bu bilgiler, uygulamayı Intune 'da tanımanıza yardımcı olur ve kullanıcıların uygulamayı şirket portalı 'nda bulmasına yardımcı olur.

1. **Uygulama bilgileri bölmesini göstermek** için **uygulama bilgileri** ' ne tıklayın.
2. **Uygulama bilgileri** bölmesinde, bu uygulama dağıtımı hakkında bilgi sağlarsınız. Bu bilgiler, uygulamayı Intune 'da tanımanıza yardımcı olur ve kullanıcıların uygulamayı şirket portalı 'nda bulmasına yardımcı olur.
    - **Ad**: uygulamanın şirket portalında görüntülenecek olan adını girin. Tüm adların benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Örneğin, açıklamada hedeflenen kullanıcıları listeleyebilirsiniz.
    - **Yayımcı**: Yayımcı olarak Microsoft gösterilir.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Bu ayar, kullanıcıların şirket portalına gözatarken uygulamayı bulmasını kolaylaştırır.
    - **Bunu şirket portalı öne çıkan uygulama olarak görüntüle**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde göstermek için bu seçeneği belirleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: Geliştirici olarak Microsoft gösterilir.
    - **Sahip**: Sahip olarak Microsoft gösterilir.
    - **Notlar**: İsteğe bağlı olarak bu uygulamayla ilişkilendirmek istediğiniz notları girin.
3. **Tamam**’ı seçin.

## <a name="configure-app-settings"></a>Uygulama ayarlarını yapılandırma
Bu adımda, uygulama için yükleme seçeneklerini yapılandırın.

1. **Uygulama Ekle** bölmesinde **uygulama ayarları**' nı seçin.
2. Uygulama **ayarları** bölmesinde, uygulamayı hangi Edge kanalını dağıtacağınızı belirlemek için **Kanal** listesinden **Stable**, **Beta** veya **dev** ' ı seçin.
    - **Kararlı** kanal, kurumsal ortamlarda büyük ölçüde dağıtım için önerilen kanaldır. Her altı haftada bir güncelleştirilir, her sürüm beta kanalından geliştirmeler içerir.
    - **Beta** kanalı, en kararlı Microsoft Edge önizleme deneyimidir ve kuruluşunuzdaki tam bir pilot için en iyi seçenektir. Her sürüm altı haftada bir olan önemli güncelleştirmelerle, geliştirme kanalından dersleri ve geliştirmeleri içerir.
    - **Geliştirme** kanalı Windows, Windows Server ve MacOS 'ta kurumsal geri bildirimde bulunmak için hazırlayın. Her hafta güncelleştirilir ve en son geliştirmeleri ve düzeltmeleri içerir.

    > [!NOTE]
    > Microsoft Edge tarayıcı logosu, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.

3.  **Tamam**’ı seçin.

## <a name="select-scope-tags-optional"></a>Kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma.
1.  **Ekle** > **kapsam (Etiketler)** seçin.
2.  Kapsam etiketlerini aramak için **Seç** kutusunu kullanın.
3.  Bu uygulamaya atamak istediğiniz kapsam etiketlerinin yanındaki onay kutusunu işaretleyin.
4.  **Tamam** > **Seç** ' e tıklayın.

## <a name="add-the-app"></a>Uygulama ekleme
Uygulamayı yapılandırmayı tamamladığınızda, **uygulama uygulaması** bölmesinden **Ekle** ' yi seçin. 

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

> [!NOTE]
> Şu anda, Microsoft Edge dağıtımı atamasını kaldırırsanız cihazda kalır.

## <a name="uninstall-the-app"></a>Uygulamayı kaldırma

Kullanıcının cihazlarından Microsoft Edge 'i kaldırmanız gerektiğinde aşağıdaki adımları kullanın.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** *Microsoft Edge* uygulaması > **atamaları** **Grup Ekle** > ' yi seçin.
3. **Grup Ekle** bölmesinde **Kaldır**' ı seçin.

    > [!NOTE]
    > Intune, uygulamayı **Kayıtlı cihazlar Için kullanılabilir** veya aynı dağıtımı kullanarak **gerekli** atama yoluyla cihaza daha önce yükletiyse, seçilen gruplardaki cihazlardan kaldırılır.
4. Bu uygulama atamasından etkilenen Kullanıcı gruplarını seçmek için **dahil edilen gruplar** ' ı seçin.
5. Kaldırma atamasını uygulamak istediğiniz grupları seçin.
6. **Grupları seçin** bölmesinde **Seç** ' e tıklayın.
7. Atamayı ayarlamak için **ata** bölmesinde **Tamam** ' a tıklayın.
8. Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız, **Grupları Dışla**'yı seçin.
9. Herhangi bir grubu dışlamayı seçtiyseniz, **Grupları seçin** alanında **Seç** düğmesini seçin.
10. **Grup Ekle** bölmesinde **Tamam ' ı** seçin.
11. Uygulama **atamaları** bölmesinde **Kaydet** ' i seçin.

> [!IMPORTANT]
> Uygulamayı başarılı bir şekilde kaldırmak için, bunları kaldırılmak üzere atamadan önce yükleme için üye veya grup atamasını kaldırdığınızdan emin olun. Bir gruba bir uygulama yüklemek ve uygulamayı kaldırmak için bir grup atanmışsa, uygulama kalır ve kaldırılmaz.

## <a name="troubleshooting"></a>Sorun giderme
**Windows 10 için Microsoft Edge sürüm 77 ve üzeri:**<br>
Intune, Windows 10 cihazlarına atanan Microsoft Edge yükleyicisini indirmek ve dağıtmak için Intune yönetim uzantısını kullanır ve ardından Microsoft Edge tarayıcısını indiren ve yükleyen Microsoft Edge yükleyicisi ile dağıtım ayarlarını iletişim kurar doğrudan CDN 'den. [Intune yönetim uzantısının ön koşullarını](~/apps/intune-management-extension.md#prerequisites)ve ağ yapılandırmanızın Windows 10 cihazlarının bu konumlara erişmesine izin verdiğinden emin olmak Için Azure Update HIZMETINE ve CDN 'ye erişme bölümünde özetlenen en iyi yöntemleri başvuru. Ayrıca, tarayıcıyı yüklemek üzere bir CDN 'den yükleme dosyalarına erişim izni vermek için Windows Update uç noktalara erişime izin vermeniz gerekir. Daha fazla bilgi için, bkz. [Windows 10, sürüm 1809 – Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) ve [Microsoft Intune ağ uç noktaları](~/fundamentals/intune-endpoints.md)Için bağlantı uç noktalarını yönetme.

## <a name="next-steps"></a>Sonraki adımlar
- [Gruplara uygulama ekleme](~/apps/apps-deploy.md)
