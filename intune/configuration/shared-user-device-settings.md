---
title: Microsoft Intune-Azure 'da paylaşılan veya çok kullanıcılı cihaz ayarları | Microsoft Docs
description: Microsoft Intune ' de birden çok kullanıcı tarafından paylaşılan veya kullanılan Windows 10 ve Windows holographic for Business cihazlarını ekleyin ve kullanın. Microsoft HoloLens dahil olmak üzere tüm ayarların ve cihazlarda ne yaptıkları hakkında bir liste görürsünüz. Konuk hesaplarını denetleme, hesapları yönetme ve etkin olmayan hesapları silme, yerel depolama alanına kaydetmeye izin verme veya bunu engelleme, güç ve uyku seçeneklerini ayarlama, güncelleştirmelerin ne zaman yükleneceğini seçme ve cihaz yapılandırma profilindeki eğitim ortamlarında cihazları kullanma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc1fca439f0edf4a5d4caaad4ff4f9e0bae5972b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730509"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Intune kullanarak paylaşılan bılgısayar veya çok kullanıcılı cihazlarda erişimi, hesapları ve güç özelliklerini denetleme

Birden çok kullanıcısı olan cihazlara paylaşılan cihaz denir ve mobil cihaz yönetimi (MDM) çözümlerinin yaygın bir parçasıdır. Microsoft Intune kullanarak, aşağıdaki platformları çalıştıran paylaşılan cihazları özelleştirebilirsiniz:

- Windows 10 Professional ve üzeri
- Windows 10 Enterprise ve daha yeni
- Windows holographic for Business, HoloLens gibi

Örneğin, okulların genellikle birçok öğrenci tarafından kullanılan cihazları vardır. Bu ayar ile, okul Intune Yöneticisi paylaşılan bılgısayar özelliğini açıp tek seferde bir kullanıcıya izin verebilir. Öğrenciler cihazdaki farklı oturum açma hesapları arasında geçiş yapamıyor. Öğrenci oturumu kapattığında, kullanıcıya özgü tüm ayarları da kaldırmayı tercih edersiniz.

Son kullanıcılar, bu paylaşılan cihazlarda Konuk hesabıyla oturum açabilirler. Kullanıcılar oturum açtıktan sonra, kimlik bilgileri önbelleğe alınır. Cihaz kullandıkları için, son kullanıcılar yalnızca izin verilen özelliklere erişim sağlar. Örneğin, kullanıcıların dosyaları yerel olarak görüp kaydedebilen, güç yönetimi ayarlarını etkinleştirebilen veya devre dışı bırakabilen, cihazın uyku moduna geçme ve daha fazlasını tercih edebilirsiniz. Ayrıca, bir eşiğe ulaşıldığında, Konuk hesabının kullanıcı oturumunu kapattığında veya etkin olmayan hesapları sildiğinden de kontrol edersiniz.

Bu makalede bir yapılandırma profili oluşturma ve açıklamalarını içeren kullanılabilir ayarların bağlantılarını ekleme işlemlerinin nasıl yapılacağı gösterilir.

Profil Intune 'da oluşturulduğunda, profilinizi kuruluşunuzdaki cihaz gruplarına dağıtır veya atarsınız. Bu profili Ayrıca, karma cihaz türleri ve işletim sistemi (OS) sürümleriyle cihaz gruplarına da atayabilirsiniz.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: **Windows 10 ve üstünü**seçin.
   - **Profil türü**: **paylaşılan çok kullanıcılı cihaz**' ı seçin.

4. [Windows 10 ve üzeri](shared-user-device-settings-windows.md) ya da [Windows holographic for Business](shared-user-device-settings-windows-holographic.md)için ayarları yapılandırın.

5. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

Profiliniz oluşturuldu ve listede gösteriliyor, ancak henüz bir şey gerçekleştirmiyor. Profili kuruluşunuzdaki cihaz gruplarına [atadığınızdan](device-profile-assign.md) emin olun.

## <a name="next-steps"></a>Sonraki adımlar

- [Windows 10 ve daha yeni](shared-user-device-settings-windows.md) ve [Windows holographic for Business](shared-user-device-settings-windows-holographic.md)için tüm ayarları görüntüleyin.
- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
