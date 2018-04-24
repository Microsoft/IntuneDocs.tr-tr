---
title: Intune ile Windows Information Protection (WIP) uygulama koruma ilkesi oluşturma ve dağıtma
description: Intune ile WIP uygulama koruma ilkesi oluşturma ve dağıtma
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 9/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fec1d11320e47c3c0678f96bf6c2ffa6c4b18fec
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Intune ile Windows Information Protection (WIP) uygulama koruma ilkesi oluşturma ve dağıtma

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

Intune 1704 sürümden itibaren, Windows 10’da kaydolmasız mobil uygulama yönetimi (MAM) senaryosunda uygulama koruma ilkeleri kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Bir WIP ilkesi eklerken kullanılan birkaç kavram hakkında konuşalım.

### <a name="list-of-allowed-and-exempt-apps"></a>İzin Verilen ve Muaf uygulamaların listesi

-   **İzin verilen uygulamalar:** Bunlar, bu ilkeye bağlı kalması gereken uygulamalardır.

-   **Muaf uygulamalar:** Bu uygulamalar bu ilkeden muaftır ve kurumsal verilere kısıtlamasız erişebilir.

### <a name="types-of-apps"></a>Uygulama türleri

-   **Önerilen uygulamalar:** yöneticilerin ilkeye kolayca içe aktarmalarına izin veren (çoğu Microsoft Office) uygulamaların önceden doldurulmuş bir listesi.

-   **Mağaza uygulamalar:** Yönetici, Windows mağazasındaki tüm uygulamaları ilkeye ekleyebilir.

-   **Windows masaüstü uygulamaları:** Yönetici ilkeye geleneksel Windows masaüstü uygulamalarını ekleyebilir (exe, dll vs.)

## <a name="pre-requisites"></a>Ön koşullar

Bir WIP uygulama koruma ilkesi oluşturabilmeniz için önce MAM sağlayıcısını yapılandırmanız gerekir.

-   [MAM sağlayıcınızı Intune ile yapılandırma](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10) hakkında daha fazla bilgi edinin.

Ayrıca, aşağıdakilere de sahip olmanız gerekir:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) lisansı.
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP birden çok kimliği desteklemez; aynı anda yalnızca bir yönetilen kimlik olabilir.

## <a name="to-add-a-wip-policy"></a>Bir WIP ilkesi eklemek için

Kuruluşunuzda Intune'u kurduktan sonra [Azure portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) aracılığıyla WIP’ye özel bir ilke oluşturabilirsiniz.

1.  **Intune mobil uygulama yönetimi panosuna** gidin, **Tüm ayarlar**’ı, ardından **Uygulama ilkesi**’ni seçin.

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

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>İzin verilen uygulamalar listenize bir Masaüstü uygulaması ekleme

**Bir Masaüstü uygulaması ekleme**

1.  **Uygulama ilkesi** dikey penceresinden, ilkenizin adını, ardından **İzin verilen uygulamalar**’ı seçin. **İzin verilen uygulamalar** dikey penceresi açılarak size bu uygulama koruma ilkesi için daha önceden listeye eklenmiş tüm uygulamaları gösterir.

2.  **İzin verilen uygulamalar** dikey penceresinden **Uygulama ekle**’yi seçin.

3.  **Uygulama ekle** dikey penceresinde, aşağı açılan listeden **Masaüstü uygulamalar**’ı seçin.

4.  Alanlara bilgileri girdikten sonra uygulamayı **İzin verilen uygulamalar** listenize eklemek için **Tamam**’ı seçin.

> [!NOTE]
> Aynı anda birden fazla **Masaüstü uygulaması** eklemek için, uygulama satırının sonundaki **(…)** menüsüne tıklayabilir, sonra başka uygulamalar eklemeye devam edebilirsiniz. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="windows-information-protection-wip-learning"></a>Windows Bilgi Koruması (WIP) Öğrenme

WIP ile korumak istediğiniz uygulamaları ekledikten sonra, **WIP Öğrenme** kullanarak bir koruma modu uygulamanız gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

Windows Bilgi Koruması (WIP) Öğrenme, yöneticilerin WIP bilinmeyen uygulamalarını izlemelerini sağlayan bir rapordur. Bilinmeyen uygulamalar, kuruluşunuzun BT departmanı tarafından dağıtılmayan uygulamalardır. Yönetici, üretkenliğin kesintiye uğramaması için, WIP’yi “Geçersiz Kılmayı Gizle” modunda uygulatmadan önce bu uygulamaları rapordan dışa aktarıp kendi WIP ilkesine ekleyebilir.

**Sessiz** veya **Geçersiz Kılmalara İzin Ver** ile başlayarak izin verilen uygulamalar listenizde doğru uygulamalar bulunduğunu küçük bir grupla doğrulamanızı öneririz. Bu denemeyi bitirdikten sonra, son uygulatma ilkenizi **Geçersiz Kılmaları Gizle** olarak değiştirebilirsiniz.

#### <a name="what-the-protection-modes-are"></a>Koruma modları nelerdir?

- **Geçersiz Kılmaları Gizle:**
    - WIP, uygunsuz veri paylaşımı durumları arar ve kullanıcının işlemi tamamlamasını engeller.
    - Bunlar arasında kurumsal olarak korunmayan uygulamalar arasında bilgi paylaşımı ve kuruluşunuz dışındaki kişi ve cihazlarla kurumsal veri paylaşımı sayılabilir.
<br></br>

- **Geçersiz Kılmalara İzin Ver:**
    - WIP, uygunsuz veri paylaşımını arayarak, güvensiz olabilecek bir şey yapıyorlarsa kullanıcıları uyarır.
    - Ancak bu mod kullanıcının ilkeyi geçersiz kılıp veri paylaşmasına izin vererek işlemi denetleme günlüğünüze kaydeder.
<br></br>
- **Sessiz:**
    - WIP sessiz çalışarak uygunsuz veri paylaşımını, Geçersiz Kılma modunda çalışandan işlem yapmasının istenmesine neden olabilecek herhangi bir şeyi engellemeden günlüğe kaydeder.
    - Uygulamaların bir ağ kaynağına veya WIP ile korunan verilere uygunsuz bir şekilde erişmeye çalışması gibi izin verilmeyen eylemler yine durdurulur.
<br></br>
- **Kapalı (önerilmez):**
    - WIP kapalıdır ve verilerinizin korunmasına veya denetlenmesine yardımcı olmaz.
    - WIP’yi kapatmanızdan sonra yerel olarak bağlı sürücülerde WIP ile etiketlenmiş dosyaların şifrelemesi çözülmeye çalışılır. WIP’yi tekrar açarsanız, daha önceki şifreleme ilkenizin otomatik olarak yeniden uygulanmadığını unutmayın.

### <a name="to-add-a-protection-mode"></a>Koruma modu uygulamak için

1.  **İlke ekle** dikey penceresinden ilkenizin adını seçin, ardından **İlke Ekle** dikey penceresinden **Gerekli ayarlar**’a tıklayın.

    ![Öğrenme Modu ekran görüntüsü](../media/AppManagement/learning-mode-sc1.png)

1.  **Kaydet**’i seçin.

### <a name="to-use-wip-learning"></a>WIP Öğrenme’yi kullanmak için

1. Azure Panosuna gidin.

2. Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune**’u seçin, **Intune panosu** açılır; **Mobil Uygulamalar**’ı seçin.

4. **İzleme** bölümünden **WIP Öğrenme**’yi seçin. WIP Öğrenme tarafından günlüğe kaydedilmiş bilinmeyen uygulamalar görürsünüz.

> [!IMPORTANT]
> Uygulamaların WIP Öğrenme günlük raporunda görünmesini sağladıktan sonra bunları uygulama koruma ilkelerine alabilirsiniz.

## <a name="to-deploy-your-wip-app-protection-policy"></a>WIP uygulama koruma ilkenizi dağıtmak için

> [!IMPORTANT]
> Bu, kayıt senaryosu olmadan mobil uygulama yönetimi (MAM) ile WIP için geçerlidir.

WIP uygulama koruma ilkenizi oluşturduktan sonra, bu ilkeyi MAM’yi kullanarak kuruluşunuza dağıtmanız gerekir.

1.  **Uygulama ilkesi** dikey penceresinde, yeni oluşturduğunuz uygulama koruma ilkesini, **Kullanıcı grupları**’nı, ardından **Kullanıcı grubu ekle**’yi seçin.

    Azure Active Directory’nizdeki tüm güvenlik gruplarından oluşan kullanıcı grupları listesi, **Kullanıcı grubu ekle** dikey penceresinde açılır.

1.  İlkenizin uygulanmasını istediğiniz grubu seçin, ardından ilkeyi dağıtmak için **Seç**’e tıklayın.
