---
title: "TeamViewer kullanarak Android cihazları uzaktan yönetme"
titlesuffix: Azure portal
description: "TeamViewer kullanarak Android cihazları uzaktan yönetmeyi öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a6286760e1e49cdb090736e9444fe8ce18ddeb7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Intune ile yönetilen Android cihazlar için uzaktan yardım sağlama

Intune, Android cihazı kullanıcılarına uzaktan yardım etmenizi sağlamak için ayrı satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Başlamak için bu konu başlığındaki bilgileri kullanın.

## <a name="before-you-start"></a>Başlamadan önce

### <a name="required-permissions"></a>Gerekli izinler

Azure portalının kullanıcısına bir [Intune rolü](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) olarak aşağıdaki izinlerin atandığından emin olun:
- Yöneticinin TeamViewer bağlayıcısı ayarlarını değiştirmesine izin vermek için **Uzaktan Yardımı Güncelleştirme** iznini verin.
- Yöneticinin yeni uzaktan yardım isteği oluşturmasına izin vermek için **Uzaktan Yardım İsteme** izni verin. **Uzaktan Yardım İsteme** iznine sahip kullanıcılar herhangi bir kullanıcı için bir oturum başlatma isteğinde bulunabilir. Herhangi bir Intune rol atama kapsamı tarafından sınırlanmazlar. Intune rol atama kapsamları, Uzaktan Yardım isteklerinin başlatılabileceği cihaz veya kullanıcıları sınırlamaz.

>[!NOTE]
>TeamViewer'ı etkinleştirerek TeamViewer for Intune Connector'ın TeamViewer oturumları oluşturmasına, Active Directory verilerini okumasına ve TeamViewer hesap erişim belirtecini kaydetmesine izin vermiş olursunuz.

### <a name="configure-the-intune-teamviewer-connector"></a>Intune TeamViewer bağlayıcısını yapılandırma

Android cihazlara uzaktan yardım sağlayabilmeniz için önce Intune TeamViewer bağlayıcısını, aşağıdaki adımları kullanarak yapılandırmanız gerekir:


1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde, **Kur** > **TeamViewer Connector**'ı seçin.
5. **TeamViewer Connector** dikey penceresinde, **Etkinleştir**'e tıklayın, ardından TeamViewer hizmet lisans anlaşmasını görüntüleyip kabul edin.
6. **TeamViewer'da Oturum Aç ve Yetkilendir**'i seçin.
7. TeamViewer sitesine bir web sayfası açılır. TeamViewer lisansı kimlik bilgilerinizi girin ve ardından **Oturum Aç**'a tıklayın.


## <a name="how-to-remotely-administer-an-android-device"></a>Bir Android cihazı uzaktan yönetme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinde **Yönet** > **Tüm cihazlar**'ı seçin.
5. Uzaktan yönetmek istediğiniz cihazı seçin, ardından cihaz özellikleri dikey penceresinde **Diğer** > **Yeni Uzak Yardım Oturumu**'nu seçin.
6. Intune TeamViewer hizmetine bağlandıktan sonra, Android cihaz hakkında bazı bilgiler göreceksiniz. Uzak oturumu başlatmak için **Bağlan**'ı seçin.

![Android TeamViewer Pencereleri](./media/android-teamviewer.png)

TeamViewer penceresinde, Android cihazda, cihazın uzaktan kontrol edilmesi dahil bir dizi uzak eylem gerçekleştirebilirsiniz. Gerçekleştirebileceğiniz eylemlerin tam ayrıntıları için bkz: [TeamViewer belgeleri](https://www.teamviewer.com/support/documents/).

İşiniz bittiğinde TeamViewer penceresini kapatın.

## <a name="end-user-notifications"></a>Son kullanıcı bildirimleri

Son kullanıcı, cihazındaki Intune Şirket Portalı uygulaması simgesinde bir bildirim bayrağı ve uygulamayı açtığında da bir bildirim görür. Daha sonra bu uzaktan yardım isteğini kabul edebilir.

