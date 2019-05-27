---
title: Microsoft Intune - Azure’da macOS cihazlara Endpoint Protection ekleme | Microsoft Docs
description: macOS cihazlarda, Mac Apple Store dahil olmak üzere uygulamaların nereye yükleneceğini belirlemek için ağ geçidi denetleyicisini kullanın. Microsoft Intune kullanarak belirli uygulamalara izin vermek, belirli uygulamaları engellemek, gizli mod kullanmak ve hatta bazı gelen bağlantı türlerini engellemek için bir güvenlik duvarı etkinleştirin veya yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e050d188d4508225ef384fbf557e7724efacab18
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047732"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Intune’da macOS Endpoint Protection ayarları

Bu makale, macOS çalıştıran cihazlar için yapılandırabileceğiniz Endpoint Protection ayarlarını gösterir. Bu ayarlar arasında bu cihazlardaki ağ geçidi denetleyicisi ve güvenlik duvarı ayarları bulunur ve bunlar, Microsoft Intune’da bir cihaz profili kullanılarak yapılandırılabilir.

## <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

- **Bu konumlardan indirilen uygulamalara izin verin**: Uygulamaları, indirildikleri yere bağlı olarak uygulamaları sınırlayın. Buradaki amaç, cihazları kötü amaçlı yazılımlardan korumak ve yalnızca güvendiğiniz kaynaklardan gelen uygulamalara izin vermektir. İzin verebileceğiniz seçenekler şunlardır: 
  - **Mac App Store**
  - **Mac App Store ve tanımlı geliştiriciler**
  - **Her yer**

- **Kullanıcı ağ geçidi denetleyicisini geçersiz kılabilir**: Kullanıcılar, ağ geçidi geçersiz kılmasını önler ayarlama ve kullanıcıların uygulamayı yüklemek için'ı tıklatarak denetiminden engeller. Etkinleştirildiğinde, kullanıcılar Control tuşuna tıklama ile herhangi bir uygulamayı yükleyebilir.

## <a name="firewall"></a>Güvenlik Duvarı

Bağlantı noktası yerine uygulama başına bağlantıları denetlemek için güvenlik duvarı kullanın. Uygulama başına ayarlar kullanmak, güvenlik duvarı korumasından faydalanmayı kolaylaştırır. Ayrıca istenmeyen uygulamaların, güvenilen uygulamalara açık olan ağ bağlantı noktalarının kontrolünü ele geçirmelerini önler.

- **Güvenlik duvarı kullanarak bağlantıları uygulama başına denetleyin ve cihazları yetkilendirilmemiş ağ erişiminden koruyun.**
  - **Güvenlik Duvarı**: Gelen bağlantıları yapılandırmak Güvenlik Duvarı'nı etkinleştirme, ortamınızda işlenir.
  - **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gereken bağlantılar dışında tüm gelen bağlantıları engelleyin. Bu özellik ayrıca, Dosya Paylaşımı ve Ekran Paylaşımı gibi tüm paylaşım hizmetlerini engeller. Paylaşım cihazları kullanıyorsanız bu ayarı **Yapılandırılmadı** olarak bırakın.

- **Belirli uygulamalar için gelen bağlantılara izin ver veya bağlantıları engelle**
  - **İzin verilen uygulamalar**: Gelen bağlantıları alması için açıkça izin verilen uygulamaları seçin.
  - **Engellenen uygulamalar**: Gelen bağlantıları Engellemesi gereken uygulamaları seçin.
  - **Gizli mod**: Bilgisayarın yoklama isteklerine yanıt vermesini önlemek için gizli modu etkinleştirin. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.
