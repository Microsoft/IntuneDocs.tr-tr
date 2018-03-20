---
title: "Microsoft Intune - Azure'da Android cihazları için özel ayarlar ekleme | Microsoft Docs"
description: "Microsoft Intune'da önceden paylaşılmış bir anahtarla WiFi profili oluşturmak, uygulama başına VPN profili oluşturmak veya Samsung Knox Standard cihazlarında uygulamalara izin vermek/engellemek için, Android cihazlarına bir özel profil ekleyin veya oluşturun"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa105cc96cd0fa7d8c6beb32cdb80b7782d9828c
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="custom-settings-for-android-devices---intune"></a>Android cihazları için özel ayarlar - Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Özel profiller Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak Android cihazlarındaki farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından cihazdaki özellikleri denetlemek için kullanılır.

Özel profil kullanarak, aşağıdaki Android ayarlarını yapılandırabilir ve atayabilirsiniz. Bu ayarlar Intune ilkelerinde yerleşik olarak bulunmaz:

- [Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma](/intune/wi-fi-profile-shared-key)
- [Uygulama başına VPN profili oluşturma](/intune/android-pulse-secure-per-app-vpn)
- [Samsung Knox Standard cihazlarında uygulamalara izin verme veya bunları engelleme](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Yalnızca listelenen ayarlar bu profil türü tarafından yapılandırılabilir. Android cihazları, yapılandırabileceğiniz OMA-URI ayarlarının tam bir listesini sunmaz. Diğer ayarları görmek istiyorsanız, [Intune Uservoice sitesinde](https://microsoftintune.uservoice.com/forums/291681-ideas) diğer ayarlar için oy verin.

## <a name="custom-profile-settings-for-android-devices"></a>Android cihazları için özel profil ayarları

1. [Azure portalı](https://portal.azure.com)’nda oturum açın. 
2. **Tüm Hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. Android platformunu kullanarak özel profil oluşturun. [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında adımlar listelenir.
4. **Özel OMA-URI Ayarları**'nda **Ekle**'yi ve sonra da **Satır Ekle**'yi seçin.
5. Aşağıdaki özellikleri girin:

  - **Ad** - Kolayca bulabilmek için OMA-URI ayarına benzersiz bir ad girin.
  - **Açıklama** - Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
  - **Veri türü** - Bu OMA-URI ayarı için kullandığınız veri türünü girin. **Dize**, **Dize (XML)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta** ve **Boole değeri** seçeneklerinden birini belirtin.
  - **OMA-URI** - İstediğiniz OMA-URI değerini girin.
  - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz değeri girin.

6. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Gerekirse diğer ayarları eklemeye devam edin.

## <a name="next-steps"></a>Sonraki adımlar

Ayarları tamamladığınızda profil oluşturulur ve listede görüntülenir. Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).
