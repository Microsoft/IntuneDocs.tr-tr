---
title: Microsoft Intune - Azure’da macOS cihazlara Endpoint Protection ekleme | Microsoft Docs
description: macOS cihazlarda, Mac Apple Store dahil olmak üzere uygulamaların nereye yükleneceğini belirlemek için ağ geçidi denetleyicisini kullanın. Microsoft Intune kullanarak belirli uygulamalara izin vermek, belirli uygulamaları engellemek, gizli mod kullanmak ve hatta bazı gelen bağlantı türlerini engellemek için bir güvenlik duvarı etkinleştirin veya yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a9828f1b8a24e4f7d871f9e6e6f67e9f6c6fb197
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182780"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune’da macOS Endpoint Protection ayarları

Bu makale, macOS çalıştıran cihazlar için yapılandırabileceğiniz Endpoint Protection ayarlarını gösterir. Bu ayarlar arasında bu cihazlardaki ağ geçidi denetleyicisi ve güvenlik duvarı ayarları bulunur ve bunlar, Microsoft Intune’da bir cihaz profili kullanılarak yapılandırılabilir.

## <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

- **Şu konumlardan indirilen uygulamalara izin ver**: Uygulamaları, indirildikleri yere göre sınırlayın. Buradaki amaç, cihazları kötü amaçlı yazılımlardan korumak ve yalnızca güvendiğiniz kaynaklardan gelen uygulamalara izin vermektir. İzin verebileceğiniz seçenekler şunlardır: 
  - **Mac App Store**
  - **Mac App Store ve tanımlı geliştiriciler**
  - **Her yer**

- **Kullanıcı Ağ Geçidi Denetleyicisini geçersiz kılabilir**: Kullanıcıların Ağ Geçidi Denetleyicisi ayarını geçersiz kılmalarını ve Control tuşuna tıklayıp bir uygulamayı yüklemelerini önler. Etkinleştirildiğinde, kullanıcılar Control tuşuna tıklama ile herhangi bir uygulamayı yükleyebilir.

## <a name="firewall"></a>Güvenlik Duvarı

Bağlantı noktası yerine uygulama başına bağlantıları denetlemek için güvenlik duvarı kullanın. Uygulama başına ayarlar kullanmak, güvenlik duvarı korumasından faydalanmayı kolaylaştırır. Ayrıca istenmeyen uygulamaların, güvenilen uygulamalara açık olan ağ bağlantı noktalarının kontrolünü ele geçirmelerini önler.

- **Güvenlik duvarı kullanarak bağlantıları uygulama başına denetleyin ve cihazları yetkilendirilmemiş ağ erişiminden koruyun.**
  - **Güvenlik Duvarı**: Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırmak için Güvenlik Duvarı’nı etkinleştirin.
  - **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel İnternet hizmetleri için gereken bağlantılar dışında tüm gelen bağlantıları engelleyin. Bu özellik ayrıca, Dosya Paylaşımı ve Ekran Paylaşımı gibi tüm paylaşım hizmetlerini engeller. Paylaşım cihazları kullanıyorsanız bu ayarı **Yapılandırılmadı** olarak bırakın.

- **Belirli uygulamalar için gelen bağlantılara izin ver veya bağlantıları engelle**
  - **İzin verilen uygulamalar**: Gelen bağlantıları almak için açıkça izin verilen uygulamaları seçin.
  - **Engellenen uygulamalar**: Gelen bağlantıları engellemesi gereken uygulamaları seçin.
  - **Gizli mod**: Bilgisayarın yoklama isteklerine yanıt vermesini önlemek için gizli modu etkinleştirin. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.
