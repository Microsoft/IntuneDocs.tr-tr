---
title: "Android for Work için Intune özel profil ayarları"
titlesuffix: Azure portal
description: "Android for Work cihazları için Intune özel profil ayarları oluşturmayı öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54365f03df39d879583bd8806b5cc6513a8c4dfb
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Android for Work cihazları için Intune özel profil ayarları oluşturma

Android for Work cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını atamak için Intune Android for Work özel yapılandırma ilkesini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılamayan Android ayarlarını atamanıza olanak sağlamak için tasarlanmıştır. Intune, şu anda sınırlı sayıda Android özel ilkesi destekler. Hangi ilkeleri yapılandırabileceğinizi öğrenmek için bu konu başlığındaki örneklere bakın.

## <a name="create-a-custom-profile"></a>Özel profil oluşturma

1. Başlamak için, [Özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) konusunda verilen yönergeleri kullanın.
2. Yeni ayar eklemek için **Özel OMA-URI Ayarları** dikey penceresinde **Ekle**’yi seçin.
3. **Satır Ekle** dikey penceresinde aşağıdakileri yapılandırın:
    - **Ad** - Azure portalında tanımlamanıza yardımcı olması için Android for Work özel ayarlarına benzersiz bir ad girin.
    - **Açıklama** - Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi girin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Dize (XML dosyası)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta**, **Boole** veya **Base64 (dosya)** seçeneklerinden birini belirleyin.
    - **Değer** - Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin. Bu değeri sağlamak için kullandığınız yöntem, seçtiğiniz veri türüne göre farklılık gösterir. Örneğin, **Tarih ve saat**’i seçerseniz, değeri tarih seçiciden belirlersiniz.
4. İşiniz bittiğinde **Özel OMA-URI Ayarları**’na dönmek için Tamam’ı seçin ve ardından daha fazla seçenek ekleyin veya özel profili oluşturmak için **Oluştur**’u seçin.


## <a name="example"></a>Örnek

Bu örnekte yönetilen Android for Work cihazlarında izin verilen iş uygulamaları ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlamak için kullanılabilecek özel bir profil oluşturacaksınız.

1. Aşağıdaki değerleri kullanarak Android for Work cihazları için özel bir profil oluşturmak üzere bu konu başlığındaki yordamı kullanın:
    - **Ad** - "Kopyala ve yapıştır eylemini engelle" veya istediğiniz bir metni girin.
    - **Açıklama** - "İş uygulamaları ve kişisel uygulamalar arasında kopyala/yapıştır eylemini engelle" veya istediğiniz bir metni girin.
    - **OMA-URI** - **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** girin.
    - **Veri türü** - Bu OMA-URI değerinin **True** veya **False** olduğunu belirtmek için **Boole** seçeneğini belirleyin.
    - **Değer**: **True**’yu seçin.
2. Bu resme benzer bir ayar görmeniz gerekir.
![Android for Work için kopyala ve yapıştır eylemini engelleyin.](./media/custom-policy-afw-copy-paste.png)
3. Bu özel profili yönettiğiniz Android for Work cihazlarına atadığınızda, kopyala ve yapıştır eylemleri iş uygulamaları ve kişisel profiller arasında engellenir.