---
title: Paylaşılan veya birden çok kullanıcı cihaz ayarları Microsoft Intune - Azure | Microsoft Docs
description: Ekleyebilir ve Windows 10 ve Windows Holographic for Business, paylaşılan veya Microsoft Intune birden çok kullanıcı tarafından kullanılan cihazlar kullanabilirsiniz. Tüm ayarların bir listesi ve Microsoft HoloLens de dahil olmak üzere cihazlarda ne yaptıklarını görün. Konuk hesapları denetlemek, hesaplarını yönetme ve etkin olmayan hesaplar silmek, izin verme veya engelleme yerel depoya kaydetme, Ayarla güç ve uyku seçenekleri, ne zaman güncelleştirmeler yüklenir ve cihazları bir cihaz yapılandırma profili eğitim ortamlarında kullanmak seçin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c2cf06508cc21682a580c09e8207343b09e39eb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61506687"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Erişim denetimi, hesapları ve paylaşılan bir bilgisayar veya Intune kullanarak birden çok kullanıcı cihazları güç özellikleri

Birden çok kullanıcıya sahip cihazlar, paylaşılan cihazlar olarak adlandırılır ve mobil cihaz Yönetimi (MDM) çözümleri, ortak bir parçasıdır. Microsoft Intune kullanarak, paylaşılan cihazlar aşağıdaki platformları çalıştıran özelleştirebilirsiniz:

- Windows 10 Professional ve daha yeni
- Windows 10 Enterprise ve daha yeni
- Windows Holographic for Business, HoloLens gibi

Örneğin, okullar genellikle çok sayıda Öğrenciler tarafından kullanılan cihazları var. Bu ayar, okul Intune Yöneticisi bir kullanıcının aynı anda izin vermek için paylaşılan bilgisayar özelliğini etkinleştirebilirsiniz. Öğrenciler, cihazdaki farklı oturum açan hesaplar arasında geçiş yapamazsınız. Öğrenci oturumu kapattığında, ayrıca tüm kullanıcıya özgü ayarları kaldırmak için seçin.

Son kullanıcılar bu paylaşılan cihazlara bir konuk hesabıyla oturum açabilir. Kullanıcılar oturum açtıktan sonra kimlik bilgilerini önbelleğe alınır. Cihaz kullandıkları gibi son kullanıcılar yalnızca izin özellikleri erişim elde edin. Örneğin, cihaz modu, kullanıcıların bakın ve dosyaları yerel olarak kaydedin, etkinleştirebilir veya devre dışı bırakın ve güç yönetimi ayarlarını durumunda uyku moduna aşması durumunda seçin. Konuk hesabı ne zaman silerse ayrıca denetim kullanıcının oturumunu açtığında veya bir Eşiğe ulaşıldığında silme etkin olmayan hesaplar.

Bu makalede, bir yapılandırma profili oluşturma işlemini göstermektedir ve açıklamalarının mevcut ayarlarla bağlantılarını içerir.

Intune'da profili oluşturduğunuzda, dağıtmak veya profili, kuruluşunuzdaki cihaz gruplarına atayabilirsiniz. Ayrıca bu profili karma cihaz türleri ve işletim sistemi (OS) sürümleri ile cihaz gruplarına atayabilirsiniz.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Seçin **Windows 10 ve üzeri**.
   - **Profil türü**: Seçin **paylaşılan çok kullanıcılı cihaz**.

4. Yapılandırma ayarlarını [Windows 10 ve üzeri](shared-user-device-settings-windows.md) veya [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

Profilinizi oluşturulur ve listede gösterilen, ancak hiçbir şey henüz yapmakta olduğu değil. Mutlaka [profili atama](device-profile-assign.md) kuruluşunuzdaki cihaz gruplarına.

## <a name="next-steps"></a>Sonraki adımlar

- İçin tüm ayarları [Windows 10 ve üzeri sürümlerde](shared-user-device-settings-windows.md) ve [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
