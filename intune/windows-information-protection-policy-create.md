---
title: "Intune ile Windows Information Protection (WIP) uygulama koruma ilkesi oluşturma ve dağıtma"
titlesuffix: Azure portal
description: "Intune ile WIP uygulama koruma ilkesi oluşturma ve dağıtma"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f56752dc77289333fae69a81e2eb04d8b2e278f7
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/30/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Intune ile Windows Information Protection (WIP) uygulama koruma ilkesi oluşturma ve dağıtma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune 1704 sürümünden itibaren, uygulamaları cihaz kaydı olmaksızın korumak için Windows 10 ile uygulama koruma ilkeleri kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Bir WIP ilkesi eklerken kullanılan birkaç kavram hakkında konuşalım.

### <a name="list-of-allowed-and-exempt-apps"></a>İzin verilen ve muaf uygulamaların listesi

-   **İzin verilen uygulamalar:** Bunlar, bu ilkeye bağlı kalması gereken uygulamalardır.

-   **Muaf uygulamalar:** Bu uygulamalar bu ilkeden muaftır ve kurumsal verilere kısıtlamasız erişebilir.

### <a name="types-of-apps"></a>Uygulama türleri

-   **Önerilen uygulamalar:** İlkeye kolayca içe aktarmanıza izin veren (çoğu Microsoft Office) uygulamaların önceden doldurulmuş bir listesi. <!---I really don't know what you mean by "easily import into policy"--->

-   **Mağaza uygulamaları:** Windows mağazasındaki tüm uygulamaları ilkeye ekleyebilirsiniz.

-   **Windows masaüstü uygulamaları:** İlkeye tüm geleneksel Windows masaüstü uygulamalarını ekleyebilirsiniz (örneğin .exe, .dll)

## <a name="pre-requisites"></a>Ön koşullar

Bir WIP uygulama koruma ilkesi oluşturabilmeniz için önce MAM sağlayıcısını yapılandırmanız gerekir. [MAM sağlayıcınızı Intune ile yapılandırma](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md) hakkında daha fazla bilgi edinin.

Ayrıca, aşağıdakilere de sahip olmanız gerekir:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) lisansı.
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP birden çok kimliği desteklemez; aynı anda yalnızca bir yönetilen kimlik olabilir.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>Bir WIP ilkesi eklemek için

Kuruluşunuzda Intune'u kurduktan sonra [Azure portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) aracılığıyla WIP’ye özel bir ilke oluşturabilirsiniz. <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  **Intune mobil uygulama yönetimi panosuna** gidin, **Tüm ayarlar**, > **Uygulama ilkesi**’ni seçin.

2.  **Uygulama ilkesi** dikey penceresinde, **İlke ekle**’yi seçin, ardından aşağıdaki değerleri girin:

    a.  **Adı:** Yeni ilkeniz için bir ad yazın (gereklidir).

    b.  **Açıklama:** İsteğe bağlı bir açıklama yazın.

    c.  **Platform:** Uygulama koruma ilkeniz için desteklenen platform olarak **Windows 10**’u seçin.

    d.  **Kayıt durumu:** İlkeniz için kayıt durumu olarak **Kayıt olmadan**’ı seçin.

3.  **Oluştur**’u seçin. İlke oluşturulur ve **Uygulama İlkesi** dikey penceresindeki tabloda görüntülenir.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>İzin verilen uygulamalar listenize önerilen uygulamalar eklemek için

1.  **Uygulama ekle** dikey penceresinden, ilkenizin adını seçinl, ardından **İlke ekle** dikey penceresinden **İzin verilen uygulamalar**’ı seçin. **İzin verilen uygulamalar** dikey penceresi açılarak daha önceden bu uygulama koruma ilkesinin listesinde yer alan tüm uygulamalar gösterilir.

2.  **İzin verilen uygulamalar** dikey penceresinden **Uygulama ekle**’yi seçin. **Uygulama ekleme** dikey penceresi açılarak bu listenin parçası olan tüm uygulamalar gösterilir.

3.  Şirket verilerinize erişmesini istediğiniz uygulamaları ve ardından **Tamam**’ı seçin. **İzin verilen uygulamalar** dikey penceresi güncelleştirilerek seçilen uygulamaları gösterir.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>İzin verilen uygulamalar listenize bir Mağaza uygulaması ekleme

**Bir Mağaza uygulaması eklemek için**

1.  **Uygulama ilkesi** dikey penceresinden ilkenizin adını seçin, sonra bu uygulama koruma ilkesinin listesinde daha önceden bulunan tüm uygulamaları gösteren menüden **İzin verilen uygulamalar**’ı seçin.

2.  **İzin verilen uygulamalar** dikey penceresinden **Uygulama ekle**’yi seçin.

3.  **Uygulama ekle** dikey penceresinde, aşağı açılan listeden **Mağaza uygulamaları**’nı seçin. Dikey pencere değişerek bir **yayımcı** ve bir uygulama **adı** eklemeniz için size kutular gösterir.

4.  Uygulamanın ve yayımcısının adlarını yazın ve **Tamam**’ı seçin.

    > [!TIP]
    > Aşağıdaki örnekte **Yayımcı** *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* ve Ürün **adı** *Microsoft.MicrosoftAppForWindows* değerleridir.

5.  Alanlara bilgileri girdikten sonra uygulamayı **İzin verilen uygulamalar** listenize eklemek için **Tamam**’ı seçin.

> [!NOTE]
> Aynı anda birden fazla Mağaza uygulaması eklemek için, uygulama satırının sonundaki **(…)** menüsüne tıklayabilir, sonra başka uygulamalar eklemeye devam edebilirsiniz. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>İzin verilen uygulamalar listenize bir masaüstü uygulaması ekleme

**Bir masaüstü uygulaması ekleme**

1.  **Uygulama ilkesi** dikey penceresinden, ilkenizin adını, ardından **İzin verilen uygulamalar**’ı seçin. **İzin verilen uygulamalar** dikey penceresi açılarak size bu uygulama koruma ilkesi için daha önceden listeye eklenmiş tüm uygulamaları gösterir.

2.  **İzin verilen uygulamalar** dikey penceresinden **Uygulama ekle**’yi seçin.

3.  **Uygulama ekle** dikey penceresinde, aşağı açılan listeden **Masaüstü uygulamalar**’ı seçin.

4.  Alanlara bilgileri girdikten sonra uygulamayı **İzin verilen uygulamalar** listenize eklemek için **Tamam**’ı seçin.

> [!NOTE]
> Aynı anda birden fazla **masaüstü uygulaması** eklemek için uygulama satırının sonundaki **(…)** menüsüne tıklayabilir, sonra başka uygulamalar eklemeye devam edebilirsiniz. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="wip-learning"></a>WIP Öğrenme
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
WIP ile korumak istediğiniz uygulamaları ekledikten sonra, **WIP Öğrenme** kullanarak bir koruma modu uygulamanız gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

WIP Öğrenme, WIP-bilinmeyen uygulamalarınızı izlemenize olanak tanıyan bir rapordur. Bilinmeyen uygulamalar, kuruluşunuzun BT departmanı tarafından dağıtılmayan uygulamalardır. "Blok" modunda WIP uygulamasını zorlamadan önce bu uygulamaları raporunuzdan dışa aktarabilir ve üretkenliğin kesintiye uğramaması için WIP ilkelerinize ekleyebilirsiniz.

**Sessiz** veya **Geçersiz Kılmalara İzin Ver** ile başlayarak izin verilen uygulamalar listenizde doğru uygulamalar bulunduğunu küçük bir grupla doğrulamanızı öneririz. Bu denemeyi bitirdikten sonra, son uygulatma ilkenizi **Blok** olarak değiştirebilirsiniz.

### <a name="what-are-the-protection-modes"></a>Koruma modları nelerdir?

#### <a name="block"></a>Engelle
WIP, uygunsuz veri paylaşımı durumları arar ve kullanıcının işlemi tamamlamasını engeller. Bunlar arasında kurumsal olarak korunmayan uygulamalar arasında bilgi paylaşımı ve kuruluşunuz dışındaki kişi ve cihazlarla kurumsal veri paylaşımı sayılabilir.

#### <a name="allow-overrides"></a>Geçersiz Kılmalara İzin Ver
WIP, uygunsuz veri paylaşımını arayarak, güvensiz olabilecek bir şey yapıyorlarsa kullanıcıları uyarır. Ancak bu mod kullanıcının ilkeyi geçersiz kılıp veri paylaşmasına izin vererek işlemi denetleme günlüğünüze kaydeder.

#### <a name="silent"></a>Sessiz
WIP sessiz çalışarak uygunsuz veri paylaşımını, Geçersiz Kılma modunda çalışandan işlem yapmasının istenmesine neden olabilecek herhangi bir şeyi engellemeden günlüğe kaydeder. Uygulamaların bir ağ kaynağına veya WIP ile korunan verilere uygunsuz bir şekilde erişmeye çalışması gibi izin verilmeyen eylemler yine durdurulur.

#### <a name="off-not-recommended"></a>Kapalı (önerilmez)
WIP kapalıdır ve verilerinizin korunmasına veya denetlenmesine yardımcı olmaz.

WIP’yi kapatmanızdan sonra yerel olarak bağlı sürücülerde WIP ile etiketlenmiş dosyaların şifrelemesi çözülmeye çalışılır. WIP’yi tekrar açarsanız, daha önceki şifreleme ilkesinin otomatik olarak yeniden uygulanmadığını unutmayın.

### <a name="add-a-protection-mode"></a>Koruma modu ekleme

1.  **Uygulama ilkesi** dikey penceresinden, ilkenizin adını, ardından **Gerekli ayarlar**’ı seçin.

    ![Öğrenme Modu ekran görüntüsü](./media/learning-mode-sc1.png)

1.  **Kaydet**’i seçin.

### <a name="use-wip-learning"></a>WIP Öğrenme’yi kullanma

1. Azure Portalı’nı açın. **Diğer hizmetler**’i seçin. Metin kutusu filtresine **Intune** yazın.

3. **Intune** > **Mobil Uygulamalar**’ı seçin.

4. **Uygulama koruma durumu** > **Raporlar** > **Windows Bilgi Koruması öğrenme**’yi seçin.  
 
    Uygulamaların WIP Öğrenme günlük raporunda görünmesini sağladıktan sonra bunları uygulama koruma ilkelerinize ekleyebilirsiniz.

## <a name="deploy-your-wip-app-protection-policy"></a>WIP uygulama koruma ilkenizi dağıtma

> [!IMPORTANT]
> Bu, cihaz kaydı olmayan WIP için geçerlidir.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

WIP uygulama koruma ilkenizi oluşturduktan sonra, bu ilkeyi MAM’yi kullanarak kuruluşunuza dağıtmanız gerekir.

1.  **Uygulama ilkesi** dikey penceresinde, yeni oluşturduğunuz uygulama koruma ilkesini ve **Kullanıcı grupları** > **Kullanıcı grubu ekle**’yi seçin.

    Azure Active Directory’nizdeki tüm güvenlik gruplarından oluşan kullanıcı grupları listesi, **Kullanıcı grubu ekle** dikey penceresinde açılır.

1.  İlkenizin uygulanmasını istediğiniz grubu seçin, ardından ilkeyi dağıtmak için **Seç** öğesini belirleyin.
