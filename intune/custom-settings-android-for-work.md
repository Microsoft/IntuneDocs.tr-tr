---
title: Android iş profilleri için Intune özel profil ayarları
titlesuffix: Microsoft Intune
description: Android iş profili cihazlar için Microsoft Intune özel profil ayarları oluşturmayı öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905300"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Android iş profili cihazları için Intune özel profil ayarları oluşturma

Android iş profili cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını atamak için Intune Android iş profili özel yapılandırma ilkesini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılamayan Android ayarlarını atamanıza olanak sağlamak için tasarlanmıştır. Intune, şu anda sınırlı sayıda Android özel ilkesi destekler. Hangi ilkeleri yapılandırabileceğinizi öğrenmek için bu makaledeki örneklere bakın.

## <a name="create-a-custom-profile"></a>Özel profil oluşturma

1. Başlamak için, [Özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) konusunda verilen yönergeleri kullanın. **Platform** olarak **Android kurumsal**’ı ve **Profil türü** olarak **Özel**’i seçin.
2. Yeni ayar eklemek için **Özel OMA-URI Ayarları** dikey penceresinde **Ekle**’yi seçin.
3. **Satır Ekle** dikey penceresinde aşağıdakileri yapılandırın:
    - **Ad** - Azure portalında tanımlamanıza yardımcı olması için Android iş profili özel ayarlarına benzersiz bir ad girin.
    - **Açıklama** - Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi girin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Dize (XML dosyası)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta**, **Boole** veya **Base64 (dosya)** seçeneklerinden birini belirleyin.
    - **Değer** - Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin. Bu değeri sağlamak için kullandığınız yöntem, seçtiğiniz veri türüne göre farklılık gösterir. Örneğin, **Tarih ve saat**’i seçerseniz, değeri tarih seçiciden belirlersiniz.
4. İşiniz bittiğinde **Özel OMA-URI Ayarları**’na dönmek için Tamam’ı seçin ve ardından daha fazla seçenek ekleyin veya özel profili oluşturmak için **Oluştur**’u seçin.


## <a name="example"></a>Örnek

Bu örnekte, Android iş profili cihazlarında izin verilen iş uygulamaları ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlamak için kullanılabilecek özel bir profil oluşturacaksınız.

1. Aşağıdaki değerleri kullanarak Android iş profili cihazları için özel bir profil oluşturmak üzere bu makaledeki yordamı kullanın:
    - **Ad** - "Kopyala ve yapıştır eylemini engelle" veya istediğiniz bir metni girin.
    - **Açıklama** - "İş uygulamaları ve kişisel uygulamalar arasında kopyala/yapıştır eylemini engelle" veya istediğiniz bir metni girin.
    - **OMA-URI** - **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** girin.
    - **Veri türü** - Bu OMA-URI değerinin **True** veya **False** olduğunu belirtmek için **Boole** seçeneğini belirleyin.
    - **Değer**: **True**’yu seçin.
2. Bu resme benzer bir ayar görmeniz gerekir.
![Android iş profili için kopyala ve yapıştır eylemini engelleyin.](./media/custom-policy-afw-copy-paste.png)
3. Bu özel profili yönettiğiniz Android iş profili cihazlarına atadığınızda, iş uygulamaları ve kişisel profiller arasında kopyala ve yapıştır eylemleri engellenir.