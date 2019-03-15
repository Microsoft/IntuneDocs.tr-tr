---
title: Windows bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma | Microsoft Intune
description: Microsoft Intune ile Windows Bilgi Koruması (WIP) uygulama koruma ilkesi oluşturma ve dağıtma
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e3751456e5a889134cfc44a4fec3cfffa7e41cd
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57390091"
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Intune ile Windows Information Protection (WIP) uygulama koruma ilkesi oluşturma ve dağıtma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulamaları cihaz kaydı olmaksızın korumak için Windows 10 uygulamaları ile uygulama koruma ilkeleri kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Bir WIP ilkesi eklerken kullanılan birkaç kavramı anlamanız gerekir:

### <a name="list-of-allowed-and-exempt-apps"></a>İzin verilen ve muaf uygulamaların listesi

-   **Korumalı uygulamalar:** Bu uygulamalar, bu ilkeye bağlı kalması gereken uygulamalardır.

-   **Muaf uygulamalar:** Bu uygulamalar bu ilkeden muaftır ve kurumsal verilere Kısıtlamasız erişebilir.

### <a name="types-of-apps"></a>Uygulama türleri

-   **Önerilen uygulamalar:** Önceden doldurulmuş uygulama listesi (çoğunlukla Microsoft Office) uygulamaların kolayca izin ilkesine içeri aktarabilir.
-   **Store uygulamaları için:** Herhangi bir uygulamayı Windows Mağazası'ndan ilkeye ekleyebilirsiniz.
-   **Windows Masaüstü uygulamaları:** (Örneğin, .exe, .dll) ilkeye tüm geleneksel Windows Masaüstü uygulamalarını ekleyebilirsiniz

## <a name="prerequisites"></a>Önkoşullar

Bir WIP uygulama koruma ilkesi oluşturabilmeniz için önce MAM sağlayıcısını yapılandırmanız gerekir. [MAM sağlayıcınızı Intune ile yapılandırma](app-protection-policies-configure-windows-10.md) hakkında daha fazla bilgi edinin.  

> [!IMPORTANT]
> WIP birden çok kimliği desteklemez; aynı anda yalnızca bir yönetilen kimlik olabilir.

Ayrıca aşağıdaki lisans ve güncelleştirmeye de sahip olmanız gerekir:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) lisansı
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)





## <a name="to-add-a-wip-app-protection-policy"></a>WIP uygulama koruma ilkesi ekleme

Kuruluşunuzda Intune'u kurduktan sonra WIP’ye özel bir ilke oluşturabilirsiniz.

> [!TIP]  
> Intune için WIP ilkeleri oluşturma hakkında, kullanılabilecek ayarlar ve bunların nasıl yapılandırıldığı dahil konuyla ilgili bilgiler için Windows Güvenlik belgeleri kitaplığındaki [Microsoft Intune için Azure portalını kullanarak MAM ile Windows Bilgi Koruması (WIP) ilkesi oluşturma](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-mam-intune-azure) konusuna bakın. 


1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm Hizmetler** > **Intune**’u seçin.
3. **Microsoft Intune** dikey penceresinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** dikey penceresinde **Uygulama koruma ilkeleri**’ni seçin.
5. **İlke ekle** dikey penceresini görüntülemek için **İlke ekle**’yi seçin.
6. Aşağıdaki değerleri ekleyin:
    - **Adı:** (Yeni ilkeniz için gereklidir) bir ad yazın.
    - **Açıklama:** (İsteğe bağlı) Bir açıklama yazın.
    - **Platform:** Seçin **Windows 10** uygulama koruma ilkesi için desteklenen platform olarak.
    - **Kayıt durumu:** Seçin **kayıtsız** ilkeniz için kayıt durumu olarak.
7.  **Oluştur**’u seçin. İlke oluşturulur ve **Uygulama koruma ilkeleri** dikey penceresindeki tabloda görüntülenir.

## <a name="to-add-recommended-apps-to-your-protected-apps-list"></a>Korunan uygulamalar listenize önerilen uygulamalar eklemek için

1. **Microsoft Intune** dikey penceresinde **İstemci uygulamaları**’nı seçin.
2. **İstemci uygulamaları** dikey penceresinde **Uygulama koruma ilkeleri**’ni seçin.
3. **Uygulama koruma ilkeleri** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. **Intune Uygulama Koruması** dikey penceresi görüntülenir.
4. **Intune Uygulama Koruması** dikey penceresinden **Korunan uygulamalar**’ı seçin. **Korunan uygulamalar** dikey penceresi açılarak size bu uygulama koruma ilkesi için daha önceden listeye eklenmiş tüm uygulamaları gösterir.
5. **Uygulama ekle**’yi seçin. **Uygulama ekle** bilgileri uygulamaların filtrelenmiş bir listesini gösterir. Dikey pencerenin üst kısmındaki liste, liste filtresini değiştirmenize izin verir.
6. Şirket verilerinize erişmesine izin vermek istediğiniz her uygulamayı seçin.
7. **Tamam**'ı tıklatın. **Korunan uygulamalar** dikey penceresi güncelleştirilerek seçilen tüm uygulamaları gösterir.
8. **Kaydet**’e tıklayın.

## <a name="add-a-store-app-to-your-protected-apps-list"></a>Korunan uygulamalar listenize bir Store uygulaması eklemek için

**Bir Mağaza uygulaması eklemek için**
1. **Microsoft Intune** dikey penceresinde **İstemci uygulamaları**’nı seçin.
2. **İstemci uygulamaları** dikey penceresinde **Uygulama koruma ilkeleri**’ni seçin.
3. **Uygulama koruma ilkeleri** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. **Intune Uygulama Koruması** dikey penceresi görüntülenir.
4. **Intune Uygulama Koruması** dikey penceresinden **Korunan uygulamalar**’ı seçin. **Korunan uygulamalar** dikey penceresi açılarak size bu uygulama koruma ilkesi için daha önceden listeye eklenmiş tüm uygulamaları gösterir.
5. **Uygulama ekle**’yi seçin. **Uygulama ekle** bilgileri uygulamaların filtrelenmiş bir listesini gösterir. Dikey pencerenin üst kısmındaki liste, liste filtresini değiştirmenize izin verir.
6. Listeden **Mağaza uygulamaları**’nı seçin.
7. **Ad**, **Yayımcı**, **Ürün Adı** ve **Eylem** için değerleri girin. Uygulamanın şirket verilerinize erişebilmesi için **Eylem** değerini **İzin Ver** olarak ayarladığınızdan emin olun.
9. **Tamam**'ı tıklatın. **Korunan uygulamalar** dikey penceresi güncelleştirilerek seçilen tüm uygulamaları gösterir.
10. **Kaydet**’e tıklayın.

## <a name="add-a-desktop-app-to-your-protected-apps-list"></a>Korunan uygulamalar listenize bir masaüstü uygulaması eklemek için

**Bir masaüstü uygulaması ekleme**
1. **Microsoft Intune** dikey penceresinde **İstemci uygulamaları**’nı seçin.
2. **İstemci uygulamaları** dikey penceresinde **Uygulama koruma ilkeleri**’ni seçin.
3. **Uygulama koruma ilkeleri** dikey penceresinde değiştirmek istediğiniz ilkeyi seçin. **Intune Uygulama Koruması** dikey penceresi görüntülenir.
4. **Intune Uygulama Koruması** dikey penceresinden **Korunan uygulamalar**’ı seçin. **Korunan uygulamalar** dikey penceresi açılarak size bu uygulama koruma ilkesi için daha önceden listeye eklenmiş tüm uygulamaları gösterir.
5. **Uygulama ekle**’yi seçin. **Uygulama ekle** bilgileri uygulamaların filtrelenmiş bir listesini gösterir. Dikey pencerenin üst kısmındaki liste, liste filtresini değiştirmenize izin verir.
6. Listeden **Masaüstü uygulamaları**’nı seçin.
7. **Ad**, **Yayımcı**, **Ürün Adı**, **Dosya**, **En Düşük Sürüm**, **En Yüksek Sürüm** ve **Eylem** için değerler girin. Uygulamanın şirket verilerinize erişebilmesi için **Eylem** değerini **İzin Ver** olarak ayarladığınızdan emin olun.
9. **Tamam**'ı tıklatın. **Korunan uygulamalar** dikey penceresi güncelleştirilerek seçilen tüm uygulamaları gösterir.
10. **Kaydet**’e tıklayın.

## <a name="wip-learning"></a>WIP Öğrenme
WIP ile korumak istediğiniz uygulamaları ekledikten sonra, **WIP Öğrenme** kullanarak bir koruma modu uygulamanız gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

WIP Öğrenme, WIP etkin ve WIP bilinmeyen uygulamalarınızı izlemenize olanak tanıyan bir rapordur. Bilinmeyen uygulamalar, kuruluşunuzun BT departmanı tarafından dağıtılmayan uygulamalardır. "Blok" modunda WIP uygulamasını zorlamadan önce bu uygulamaları raporunuzdan dışa aktarabilir ve üretkenliğin kesintiye uğramaması için WIP ilkelerinize ekleyebilirsiniz.

<!-- 1631908 -->
WIP’in etkinleştirildiği uygulamalar hakkındaki bilgileri görüntülemeye ek olarak, web siteleriyle paylaşılan iş verilerine sahip cihazların özetini de görüntüleyebilirsiniz. Bu bilgilerle, grup ve kullanıcı WIP ilkelerine hangi web sitelerinin eklenmesi gerektiğini saptayabilirsiniz. Özet, WIP özellikli uygulamalar tarafından hangi web sitesi URL'lerine erişildiğini gösterir.

WIP etkin ve WIP bilinmeyen uygulamalarla çalışırken, **Sessiz** veya **Geçersiz Kılmalara İzin Ver** ile başlayarak korunan uygulamalar listenizde doğru uygulamalar bulunduğunu küçük bir grupla doğrulamanızı öneririz. Bu denemeyi bitirdikten sonra, son uygulatma ilkenizi **Blok** olarak değiştirebilirsiniz.

### <a name="what-are-the-protection-modes"></a>Koruma modları nelerdir?

#### <a name="block"></a>Engelle
WIP, uygunsuz veri paylaşımı durumları arar ve kullanıcının işlemi tamamlamasını engeller. Engellenen eylemler için kurumsal olarak korunmayan uygulamalar arasında bilgi paylaşımı ve kuruluşunuz dışındaki kişi ve cihazlarla kurumsal veri paylaşımı sayılabilir.

#### <a name="allow-overrides"></a>Geçersiz Kılmalara İzin Ver
WIP, uygunsuz veri paylaşımını arayarak, güvensiz olabilecek bir şey yaptığında kullanıcıları uyarır. Ancak bu mod kullanıcının ilkeyi geçersiz kılıp veri paylaşmasına izin vererek işlemi denetleme günlüğünüze kaydeder.

#### <a name="silent"></a>Sessiz
WIP sessiz çalışarak uygunsuz veri paylaşımını, Geçersiz Kılma modunda çalışandan işlem yapmasının istenmesine neden olabilecek herhangi bir şeyi engellemeden günlüğe kaydeder. Uygulamaların bir ağ kaynağına veya WIP ile korunan verilere uygunsuz bir şekilde erişmeye çalışması gibi izin verilmeyen eylemler yine durdurulur.

#### <a name="off-not-recommended"></a>Kapalı (önerilmez)
WIP kapalıdır ve verilerinizin korunmasına veya denetlenmesine yardımcı olmaz.

WIP’yi kapatmanızdan sonra yerel olarak bağlı sürücülerde WIP ile etiketlenmiş dosyaların şifrelemesi çözülmeye çalışılır. WIP’yi tekrar açarsanız daha önceki şifreleme ilkesinin otomatik olarak yeniden uygulanmadığını unutmayın.

### <a name="add-a-protection-mode"></a>Koruma modu ekleme

1.  **Uygulama ilkesi** dikey penceresinden, ilkenizin adını, ardından **Gerekli ayarlar**’ı seçin.

    ![Öğrenme modu bölmesinin ekran görüntüsü](./media/learning-mode-sc1.png)

1.  Bir ayar seçin ve ardından **Kaydet**’i seçin.

### <a name="use-wip-learning"></a>WIP Öğrenme’yi kullanma

1. [Azure portalı](https://portal.azure.com) açın. **Tüm hizmetler**’i seçin. Metin kutusu filtresine **Intune** yazın.

3. **Intune** > **İstemci uygulamaları**’nı seçin.

4. **Uygulama koruma durumu** > **Raporlar** > **Windows Bilgi Koruması öğrenme**’yi seçin.  

    Uygulamaların WIP Öğrenme günlük raporunda görünmesini sağladıktan sonra bunları uygulama koruma ilkelerinize ekleyebilirsiniz.

## <a name="allow-windows-search-indexer-to-search-encrypted-items"></a>Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver
Öğeler için dizin oluşturulmasına izin verir veya engeller. Bu anahtar, Windows Bilgi Koruması (WIP) tarafından korunan dosyalar gibi şifrelenmiş öğeler için dizin oluşturulup oluşturulmadığını kontrol eden Windows Search Dizin Oluşturucu içindir.

Bu uygulama koruma ilkesi seçeneği, Windows Bilgi Koruması ilkesinin **Gelişmiş ayarlar** bölümündedir. Uygulama koruma ilkesi, *Windows 10* platformuna ayarlanmalı ve uygulama ilkesi **Kayıt durumu**, **Kayıt ile** olarak ayarlanmalıdır.

İlke etkinleştirildiğinde, WIP korumalı öğelerin dizini oluşturulur ve bunlar hakkındaki meta veriler şifrelenmemiş bir konumda depolanır. Meta veriler, dosya yolu ve değiştirilme tarihi gibi veriler içerir.

İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Cihazda çok sayıda WIP korumalı medya dosyası varsa fotoğraflar ve Groove uygulamaları performansını da etkileyebilir.

## <a name="add-encrypted-file-extensions"></a>Şifrelenmiş dosya uzantıları ekleme

**Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver** seçeneğine ek olarak, bir dosya uzantıları listesi de belirtebilirsiniz. Bu uzantılara sahip dosyalar, ağ konumu listesinde tanımlandığı şekilde şirket sınırında bir Sunucu İleti Bloğu (SMB) paylaşımından kopyalanırken şifrelenir. Bu ilke belirtilmediğinde, mevcut otomatik şifreleme davranışı uygulanır. Bu ilke yapılandırıldığında, yalnızca listededeki uzantılara sahip dosyalar şifrelenir.

## <a name="deploy-your-wip-app-protection-policy"></a>WIP uygulama koruma ilkenizi dağıtma

> [!IMPORTANT]
> Bu bilgi, cihaz kaydı olmayan WIP için geçerlidir.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

WIP uygulama koruma ilkenizi oluşturduktan sonra, bu ilkeyi MAM’yi kullanarak kuruluşunuza dağıtmanız gerekir.

1.  **Uygulama ilkesi** dikey penceresinde, yeni oluşturduğunuz uygulama koruma ilkesini ve **Kullanıcı grupları** > **Kullanıcı grubu ekle**’yi seçin.

    Azure Active Directory’nizdeki tüm güvenlik gruplarından oluşan kullanıcı grupları listesi, **Kullanıcı grubu ekle** dikey penceresinde açılır.

2.  İlkenizin uygulanmasını istediğiniz grubu seçin, ardından ilkeyi dağıtmak için **Seç** öğesini belirleyin.

## <a name="next-steps"></a>Sonraki adımlar

Windows Bilgi Koruması hakkında daha fazla bilgi için bkz. [Windows Bilgi Koruması’nı (WIP) kullanarak kurumsal verilerinizi koruma](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).
