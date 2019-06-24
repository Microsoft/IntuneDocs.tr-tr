---
title: Bir Microsoft Intune cihazın birincil kullanıcıyı bulun.
titleSuffix: ''
description: Birincil kullanıcı (veya kullanıcı cihaz benzeşimi) bir Intune cihaz bulun.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b6a20ccec2ef0cbaba87637b3c44c2cc2be094ab
ms.sourcegitcommit: b3a1c5b0b24f0e52cf318defe10f3d27a2770009
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67322869"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Birincil kullanıcının bir Intune cihaz bulma

Birincil kullanıcı, kullanıcı cihaz benzeşim olarak da bilinir, her Intune cihaz özelliğidir. Bir Intune cihaz, sıfır veya bir birincil kullanıcı kendisine atanmış olabilir. Birincil atanan kullanıcı olduğunda, cihaz, bir "paylaşılan cihaz" olarak adlandırılır.

## <a name="how-to-find-a-devices-primary-user"></a>Bir cihazın birincil kullanıcısı bulma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Seçin **cihazları** > bir cihaz seçin.
3. Üzerinde **genel bakış** sayfasında **daha fazla bilgi bkz** listelenen birincil kullanıcı göreceksiniz.

## <a name="what-is-the-primary-user"></a>Birincil kullanıcı nedir?
Birincil kullanıcı özelliği, lisanslı bir Intune kullanıcı cihazlarını eşleştirmek için kullanılır:
- Şirket portalı uygulaması
- Son kullanıcı Web sitesi
- BT sayfaları Azure Portalı'nda sorun giderme gibi pro deneyimleri. Bu sayfalar, kullanıcı hesaplarını kullanarak birincil kullanıcı tarafından cihazlara eşleyin.    

### <a name="company-portal-app"></a>Şirket Portalı uygulaması
Şirket portalı uygulaması, şirket portalında oturum açmıştır kullanıcı hesabının bu cihazın birincil kullanıcısı olduğunu bekliyor. Birincil kullanıcı olarak atanmış olan başka bir kullanıcı, Şirket portalı, bir uyarı gösterir:

"Bu cihaz zaten kuruluşunuzdaki birisi atanır. Birincil cihaz kullanıcısının olma hakkında iletişim şirketinizin destek birimi. Şirket portalı kullanmaya devam edebilirsiniz ancak işlevselliği sınırlı olur."

Ardından birincil kullanıcıya atanan Intune cihaz varsa Şirket portalı uygulaması, paylaşılan cihazlar algılar. Paylaşılan cihazlar "paylaşılan" etiketli cihaz kutucuğuna görünen bir görsel olarak tanımlanabilir. Bu modda, Şirket portalı hala istemek ve mevcut uygulamaları için kullanılabilir. Bununla birlikte, Self Servis bir Eylemler (sıfırlama/yeniden adlandırma/devre dışı bırakma) kullanılamaz.  

Kullanılabilir uygulamalar, paylaşılan cihazlar üzerindeki şirket Portalı'nda görünmesi için bir kullanıcı grubuna atanmalıdır. Bunlar Sistem bağlamında ya da uygulama BT yöneticiniz tarafından yapılandırılan nasıl bağlı olarak kullanıcı bağlamı, yüklü olması. Uygulama Bağlamı hakkında daha fazla bilgi için bkz. [Windows 10 cihazlarda uygulama yükleme](apps-windows-10-app-deploy.md#installing-apps-on-windows-10-devices). Şirket portalı sürümü 10.3.4651.0 veya daha sonra bu özelliği kullanmak için gereklidir.


## <a name="who-is-assigned-as-the-primary-user"></a>Birincil kullanıcı olarak atanan kişi?
Intune otomatik olarak birincil kullanıcı cihazlarına sırasında veya hemen sonra kayıt ekler. Kayıt yöntemi, bir cihaz için birincil kullanıcı eklendiğinde belirler.

| Platform | Kayıt yöntemi | Atanan birincil kullanıcı | Birincil kullanıcı olarak atanan |
| ---- | ---- | ---- | ---- |
| Windows | İş veya Okul (kullanıcı tabanlı) Ekle | Kullanıcı kaydetme | Kayıt sırasında |   
| Windows | Modern uygulama oturum açma (kullanıcı temelli) | Kullanıcı kaydetme | Kayıt sırasında | 
| Windows | MDM'ye yalnızca (kullanıcı güdümlü) kaydetme | Kullanıcı kaydetme | Kayıt sırasında | 
| Windows | Azure AD'ye katılım (dışı deneyimini) | Kullanıcı kaydetme | Kayıt sırasında | 
| Windows | Azure AD'ye katılım (Autopilot deneyimini dışında) | Kullanıcı kaydetme | Kayıt sırasında | 
| Windows | Yalnızca MDM sistemine kaydetme | Kullanıcı kaydetme | Kayıt sırasında | 
| Windows | Hybrid AADJ + automatic enrollment GPO | İlk kullanıcı, oturum açmak için | İlk kullanıcı, oturum açtığında | 
| Windows | Ortak yönetim | İlk kullanıcı, oturum açmak için | İlk kullanıcı, oturum açtığında | 
| Windows | Azure AD'ye katılım (toplu kayıt belirteç) | None | Geçerli değil | 
| Windows | Azure AD'ye katılım (şirket içinde dağıtma Autopilot mod) | Yok. | Geçerli değil | 
| Platformlar arası | Şirket portalı uygulaması ile kullanıcı odaklı kaydı | Kullanıcı kaydetme | Kayıt sırasında |
| Platformlar arası | Cihaz kayıt Yöneticisi (DEM) | DEM kullanıcısı kaydetme | Kayıt sırasında |
| iOS, macOS | Apple cihaz kaydı (kullanıcı benzeşimi ile DEP'in otomatik | Kullanıcı kaydetme | Kayıt sırasında |
| iOS, macOS | Apple cihaz kaydı'nı (DEP kullanıcı benzeşimi olmadan) otomatik | None | Geçerli değil |
| Android | Android şirketin sahip olduğu ve ayrılmış cihazları | Yok. | Geçerli değil |

## <a name="primary-user-and-azure-ad-device-owner"></a>Birincil kullanıcı ve Azure AD cihaz sahibi
Bazı durumlarda, Intune birincil kullanıcı Azure AD cihazın farklı olabilir **sahibi** özelliği (altında görüntülenebilir **cihazları** > **Azure AD cihazları**). Azure AD cihaz sahibi, Azure Active Directory cihaz kaydı sırasında eklenir.

## <a name="next-steps"></a>Sonraki adımlar
[Intune cihazlarınızı yönetin.](device-management.md)
