---
title: "Android for Work için Intune cihaz kısıtlama ayarları | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Android for Work cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 857522ef4931407accf98b2a2ad97334278c138f
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Android for Work cihaz kısıtlama ayarları

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="work-profile-settings"></a>İş profili ayarları
-     **İş ve kişisel profiller arasında veri paylaşımı** - İş profilindeki uygulamaların kişisel profildeki uygulamalarla veri paylaşıp paylaşamayacağını denetlemek için bu ayarı kullanın. Aşağıdakilerden birini seçin:
    - **Varsayılan paylaşım kısıtlamaları** - Bu, cihazın çalıştırdığı Android sürümüne göre farklılık gösteren varsayılan paylaşım davranışıdır. Varsayılan olarak, kişisel profilden iş profiline paylaşıma izin verilir. Varsayılan olarak, iş profilinden kişisel profile paylaşım ise engellenir. Bu, işten kişisel profile veri sızıntısını önler. Google, 6.0 öncesi sürümleri çalıştıran cihazlarda kişisel profilden iş profiline giden verileri engellemek için bir yol sunmaz.  
    - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir** - Kişisel profilden iş profiline paylaşıma izin veren bu yerleşik Android özelliğini etkinleştirmek için bu seçeneği kullanın. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gönderilen bir paylaşım isteği, iş profilindeki uygulamalarda paylaşım yapabilir. Bu, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
    - **Kişisel profildeki uygulamalar iş profilinden gelen paylaşım isteklerini işleyebilir** - İş profili sınırında her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki yönetilmeyen uygulamalar ile veri paylaşabilir.  Bu seçenek iş profilindeki yönetilen verilerin cihazın yönetilmeyen kısmına aktarılmasına izin verdiğinden, bu ayarı dikkatli kullanın.


-     **Cihaz kilitliyken iş profili bildirimleri** - Cihaz kilitliyken iş profilindeki uygulamaların ekranda bildirimler gösterip gösteremeyeceğini denetleyin.
-     **Varsayılan uygulama izinleri** - İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6'dan başlayarak, uygulamaların gerektirdiği bazı izinler çalışma zamanında son kullanıcıdan istenir. Bu ilke ayarı, iş profilinde kullanıcılardan izin vermelerinin istenip istenmeyeceğine veya nasıl isteneceğine karar vermenize olanak tanır.
Örneğin, iş profiline konum erişimi gerektiren bir uygulama gönderebilirsiniz. Normalde bu uygulama, kullanıcıya konum erişimi izni vermek isteyip istemediğini sorar ve kullanıcı bunu kabul edebilir veya reddedebilir. Bu ilke, tüm izinlerin istem olmadan otomatik olarak verilip verilmeyeceği, istem olmadan otomatik olarak reddedilip reddedilmeyeceği veya kararın son kullanıcıya bırakılması seçeneklerinden birini belirlemenizi sağlar. Aşağıdakilerden birini seçin:
    -     **Cihaz varsayılanı**
    -     **Sor**
    -     **Otomatik olarak izin ver**
    -     **Otomatik olarak reddet**

## <a name="password"></a>Parola

- **En düşük parola uzunluğu** - Kullanıcı parolalarının içermesi gereken en düşük rakam veya karakter sayısını belirtin (**4**-**14** arası)
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçmesi gereken süreyi seçin.
- **Cihaz silinmeden önceki oturum açma hatası sayısı** - Tüm veriler cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)** - Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
- **Gerekli parola türü** - Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
    - **Cihaz varsayılanı**
    - **Düşük güvenlik biyometriği**
    - **Gerekli**
    - **En az sayısal**
    - **Sayısal karmaşık** - ('1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez)
    - **En az alfabetik**
    - **En az alfasayısal**
    - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle** -Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak izi ile kilit açma** - Bir son kullanıcının cihaz kilidini açmak için parmak izi tarayıcısını kullanmasını engeller.
- **Akıllı Kilit ve diğer güven aracıları** - Uyumlu cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı, kullanıcıların Akıllı Kilit’i yapılandırmasını önlemek için kullanabilirsiniz.

## <a name="custom-policy-settings"></a>Özel ilke ayarları
Android for Work cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını atamak için Microsoft Intune **Android for Work özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılamayan Android ayarlarını atamanıza olanak sağlamak için tasarlanmıştır.
Intune, şu anda sınırlı sayıda Android özel ilkesi destekler. Hangi ilkeleri yapılandırabileceğinizi öğrenmek için bu konu başlığındaki örneklere bakın.

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad** |Intune konsolunda tanımlamanıza yardımcı olması için Android özel ilkesine benzersiz bir ad girin.|
    |**Açıklama** |Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### <a name="oma-uri-settings"></a>OMA-URI ayarları

  |Ayar adı|Ayrıntılar|
  |--------|--------------------|
  |**Ad** |Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
  |**Açıklama** |Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**OMA-URI (büyük küçük harfe duyarlı)** |Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
  |**Veri türü** |Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize, Dize (XML), Tarih ve saat, Tamsayı, Kayan nokta** veya **Boole değeri** seçeneklerinden birini belirleyin.|
  |**Değer** |Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

