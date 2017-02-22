---
title: "Apple Configurator seri numaralarını ekleme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Learn Apple Configurator kullanarak şirkete ait iOS cihazlarına seri numaraları eklemeyi öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: 71d29a245f8f900a7427528167bae0b52565d42b


---

# <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator seri numaraları ekleme 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

[Kurulum Yardımcısı’yla Apple Configurator kullanarak şirkete ait iOS cihazlarını kaydetmek]((enroll-ios-devices-with-apple-configurator-and-setup-assistant.md) istediğinizde Intune’a seri numaralarını eklemek için bu adımları kullanın. Seri numaralarını birer birer ekleyebileceğiniz gibi, seri numaralarını içeren bir virgülle ayrılmış değerler (CSV) dosyasını da karşıya yükleyebilirsiniz. Seri numaralarını ekledikten sonra, bunlara profil atayabilirsiniz. Profil, cihazlara uygulamak istediğiniz belirli yönetim ayarlarını içerir. 

iOS cihazlarını kaydetmeye yönelik diğer yöntemler, [Intune’da iOS cihazlarının nasıl kaydedileceğini seçme](choose-ios-enrollment-method.md) başlığı altında açıklanır.

**Intune’a Apple Configurator seri numaralarını eklemek için**

1. İki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Liste için geçerli üst sınır 500 satırdır. Metin düzenleyicisinde, .csv listesi aşağıdaki gibi görünür:

    F7TLWCLBX196,cihaz ayrıntıları</br>
    DLXQPCWVGHMJ,cihaz ayrıntıları

2. Azure Portal’da **Diğer Hizmetler**’i seçin, metin kutusuna **Intune** girin ve sonra **Diğer** > **Intune**’u seçin.

3.  Intune dikey penceresinde, **Cihazları kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

4. **Apple Configurator Kayıt Ayarlarını Yönet**’in altında, **Apple Configurator Seri Numaraları**’nı seçin.

5. **Apple Configurator Seri Numaraları** dikey penceresinde **Ekle**’yi seçin.

6. **Seri Numarası Ekle** dikey penceresinde, içeri aktardığınız seri numaralarına uygulamak için bir profil seçin. Mevcut ayrıntıların üzerine yazılacak yeni ayrıntılar içeren bir dosyayı içeri aktarıyorsanız, mevcut ayrıntıların yerini yenilerinin alması için Mevcut tanımlayıcıların ayrıntılarının üzerine yazın seçeneğini kullanın.

7. Seri numaralarının bulunduğu .csv dosyasına gidin ve **Ekle**’yi seçin.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Belirli seri numaralarına profil atama

Intune, Azure Portal’da iki farklı konumdan profil atamanıza olanak tanır. Aşağıdaki adımları kullanabilir veya profili oluşturduğunuz yer olan Apple Configurator Kayıt Profilleri dikey penceresinde profilleri atayabilirsiniz (bkz. [Kurulum Yardımcısı’nı kullanarak Apple Configurator ile iOS cihazlarını kaydetme](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Aşağıdaki adımları kullanarak profil atayabilmeniz için, profili zaten oluşturmuş olmanız gerekir.

1. Intune dikey penceresinde, **Cihazları kaydet**’i ve ardından **Apple Kaydı**’nı seçin.

2. **Apple Configurator Seri Numaraları** dikey penceresinde, profil atamak istediğiniz seri numaralarını, sonra da **Profil Ata**’yı seçin.

3. **Profil Ata** dikey penceresinde atamak istediğiniz profili, sonra da **Ata**’yı seçin.

## <a name="delete-serial-numbers"></a>Seri numaralarını silme
Daha önce içeri aktarmış olduğunuz seri numaralarını silebilirsiniz. Seri numaralarını silebilmeniz için önce cihazın kaydı silinmelidir. Seri numarasını kaldırdığınızda, yeniden eklemediğiniz sürece Kurulum Yardımcısı yoluyla Apple Configurator’ı kullanamazsınız.

## <a name="view-the-state-of-a-device"></a>Cihazın durumunu görüntüleme
Cihaz seri numaralarını iki durumdan birinde olabilir:

- Kaydedildi - cihaz kaydedilmiş ve Intune hizmetine bağlanmıştır
- Bağlantı Kurulmadı - cihaz hiçbir zaman Intune hizmetine bağlanmamıştır.
- Sıfırlanmayı Bekliyor - cihaz kaydedilmiş ancak bir değişiklik yapılmıştır (örneğin, kayıt ayarları veya uygulanan DEP profili değiştirilmiştir). Cihazın DEP profilini değiştirirseniz, cihazın kaydı silinip yeniden kaydedilene kadar değişiklikler uygulanmaz.

**Seri numarasının durumunu görüntülemek için**

**Apple Configurator Seri Numaraları** dikey penceresinde, durumunu görmek istediğiniz seri numarasını seçin ve **Durum** öğesinin altına bakın.



<!--HONumber=Feb17_HO1-->


