---
title: Microsoft Intune cihazının birincil kullanıcısını bulun.
titleSuffix: ''
description: Bir Intune cihazının birincil kullanıcısını (veya Kullanıcı aygıtı benzeşimini) bulun.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6f594e20abf1a507d1d4e00641a4821fe1ba9b0
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509338"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>Intune cihazının birincil kullanıcısını bulma

Kullanıcı cihaz benzeşimi olarak da bilinen birincil Kullanıcı, her bir Intune cihazının bir özelliğidir. Bir Intune cihazında sıfır veya bir birincil kullanıcı atanmış olabilir. Hiç birincil Kullanıcı atanmamışsa, cihaza "paylaşılan cihaz" adı verilir.

## <a name="how-to-find-a-devices-primary-user"></a>Bir cihazın birincil kullanıcısını bulma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Cihaz seçin > **cihazları** seçin.
3. **Genel bakış** sayfasında, **daha fazla göster** ' i seçin ve birincil kullanıcının listelendiğini görürsünüz.

## <a name="what-is-the-primary-user"></a>Birincil Kullanıcı nedir?
Birincil Kullanıcı özelliği, lisanslı bir Intune kullanıcısını içindeki cihazlarıyla eşlemek için kullanılır:
- Şirket Portalı uygulaması
- Son Kullanıcı Web sitesi
- Azure portal sayfa sorunlarını giderme gibi BT uzmanı deneyimleri. Bu sayfalar, birincil Kullanıcı kullanılarak kullanıcı hesaplarını cihazlara eşler.    

### <a name="company-portal-app"></a>Şirket Portalı uygulaması
Şirket Portalı uygulaması, Şirket Portalı oturum açan kullanıcı hesabının o cihazın birincil kullanıcısı olmasını bekler. Birincil kullanıcı olarak başka bir Kullanıcı atanırsa, Şirket Portalı bir uyarı gösterir:

"Bu cihaz, kuruluşunuzdaki bir kişiye zaten atanmış. Birincil cihaz kullanıcısı olma hakkında şirket desteği ile iletişim kurun. Şirket Portalı kullanmaya devam edebilirsiniz, ancak işlevler sınırlı olacaktır. "

Bir Intune cihazında hiç birincil Kullanıcı atanmamışsa, Şirket Portalı uygulama onu paylaşılan bir cihaz olarak algılar. Paylaşılan cihazlar, cihaz kutucuğunda görüntülenen "paylaşılan" bir etiketle görsel olarak tanımlanabilir. Bu modda Şirket Portalı kullanılabilir uygulamaları talep etmek ve yüklemek için hala kullanılabilir. Ancak self servis eylemleri (sıfırlama/yeniden adlandırma/devre dışı bırakma) kullanılamaz.  

Paylaşılan cihazlardaki Şirket Portalı görünmesi için, kullanılabilir uygulamaların bir kullanıcı grubuna atanması gerekir. Uygulamanın BT Yöneticisi tarafından nasıl yapılandırıldığına bağlı olarak, sistem bağlamına veya Kullanıcı bağlamına yüklenir. Uygulama bağlamı hakkında daha fazla bilgi için bkz. [Windows 10 cihazlarına uygulama yükleme](../apps/apps-windows-10-app-deploy.md). Bu özelliği kullanmak için Şirket Portalı Version 10.3.4651.0 veya üzeri gereklidir.


## <a name="who-is-assigned-as-the-primary-user"></a>Birincil kullanıcı olarak kim atanır?
Intune, kayıt sırasında veya hemen sonrasında cihazlara birincil kullanıcı otomatik olarak ekler. Kayıt yöntemi, birincil kullanıcının bir cihaza ne zaman ekleneceğini belirler.

| Platfveyam | Kayıt yöntemi | Birincil Kullanıcı atandı | Birincil Kullanıcı atandı |
| ---- | ---- | ---- | ---- |
| Windows | İş veya okul ekleme (Kullanıcı odaklı) | Kullanıcı kaydediliyor | Kayıt sırasında |   
| Windows | Modern uygulama oturum açma (Kullanıcı tabanlı) | Kullanıcı kaydediliyor | Kayıt sırasında | 
| Windows | Yalnızca MDM 'ye kaydolma (Kullanıcı odaklı) | Kullanıcı kaydediliyor | Kayıt sırasında | 
| Windows | Azure AD katılımı (kullanıma hazır deneyim) | Kullanıcı kaydediliyor | Kayıt sırasında | 
| Windows | Azure AD katılımı (Autopilot of Box Experience) | Kullanıcı kaydediliyor | Kayıt sırasında | 
| Windows | Yalnızca MDM 'ye kaydolma | Kullanıcı kaydediliyor | Kayıt sırasında | 
| Windows | Karma ASıFATı + otomatik kayıt GPO 'SU | Windows 'da oturum açmak için ilk Kullanıcı | İlk Kullanıcı Windows 'da oturum açtığında| 
| Windows | Ortak yönetim | Windows 'da oturum açmak için ilk Kullanıcı | İlk Kullanıcı Windows 'da oturum açtığında | 
| Windows | Azure AD birleşimi (toplu kayıt belirteci) | Yok. | Not applicable | 
| Windows | Azure AD katılımı (Autopilot kendi kendine dağıtım modu) | Yok. | Not applicable | 
| Platformlar arası | Şirket Portalı uygulamayla Kullanıcı odaklı kayıt | Kullanıcı kaydediliyor | Kayıt sırasında |
| Platformlar arası | Cihaz Kayıt Yöneticisi (DEM) | DEM kullanıcısı kaydediliyor | Kayıt sırasında |
| iOS, macOS | Apple otomatik cihaz kaydı (Kullanıcı benzeşimi ile DEP | Kullanıcı kaydediliyor | Kayıt sırasında |
| iOS, macOS | Apple otomatik cihaz kaydı (Kullanıcı benzeşimi olmadan DEP) | Yok. | Not applicable |
| Android | Android şirkete ait, adanmış cihazlar | Yok. | Not applicable |

## <a name="primary-user-and-azure-ad-device-owner"></a>Birincil Kullanıcı ve Azure AD cihaz sahibi
Bazı durumlarda, Intune birincil Kullanıcı Azure AD cihazının **Owner** özelliğinden ( **cihazlarda**görüntülenebilir  > **Azure AD cihazlarından**) farklı olabilir. Azure AD cihaz sahibi, cihazın kaydı sırasında Azure Active Directory eklenir.

## <a name="next-steps"></a>Sonraki adımlar
[Intune cihazlarınızı yönetin.](device-management.md)
