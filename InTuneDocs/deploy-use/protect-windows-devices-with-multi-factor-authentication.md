---
title: "Windows için Multi Factor Authentication | Microsoft Intune"
description: "Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak için, Multi Factor Authentication’ı (MFA) tümleştirir."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ab9ad1fb42176f2fc2babaa6fa3c91cea40b4ca5
ms.openlocfilehash: 1bfd17f9fcc73049254bc77351eae48da874fb4c


---

# <a name="protect-windows-devices-with-multifactor-authentication"></a>Windows cihazlarını Multi-Factor Authentication ile koruma
Microsoft Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak için, Multi Factor Authentication’ı (MFA) tümleştirir. MFA, metin kimlik doğrulamasının yanı sıra kullanıcı adları ve parolalar gibi kimlik doğrulama faktörleri de gerektirir. Intune, Windows 8.1 veya üzerinde, Windows Phone 8.1 veya Windows 10 Masaüstü ve Mobil cihazlarının kaydı sırasında MFA kullanımını destekler.

## <a name="onpremises-infrastructure-requirements-for-adfs-mfa"></a>ADFS MFA için şirket içi altyapı gereksinimleri
Multi Factor Authentication'ı kurmak için şunlar gerekir:

-   [Windows cihaz yönetimini ayarlama](set-up-windows-device-management-with-microsoft-intune.md) bölümünde açıklandığı gibi otomatik kayıt.
-   **ADFS sunucusunun katıldığı bir Active Directory etki alanı.**

-   **MFA için yapılandırılmış Active Directory Federasyon Hizmetleri (ADFS) sunucusu.** Windows Server 2012 R2 çalıştıran ve bir ADFS sunucusu olarak ayarlanmış olan sunucu. Daha fazla bilgi için, bkz. [Windows Server 2012 R2 AD FS ile Azure Multi Factor Authentication Sunucusu kullanarak bulut ve şirket içi kaynakları güvenli hale getirme](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Sunucular, [Windows Server 2012 R2 için Sistem Gereksinimleri ve Yükleme Bilgileri](http://technet.microsoft.com/library/dn303418.aspx) bölümündeki sistem gereksinimlerini karşılamalıdır.

 


#### <a name="mfa-with-intune"></a>Intune ile MFA
Kuruluşunuzda Active Directory Federasyon Hizmetleri’nin (ADFS) bulunduğu bir Active Directory etki alanı içeren bir şirket içi BT altyapısı varsa, federasyon sunucunuzda MFA'yı ayarlayabilir ve ardından Intune kaydı için MFA’yı etkinleştirebilirsiniz. Intune’da MFA yapılandırıldığında, kullanıcılar kayıt sırasında bir kez kimlik doğrulaması yapabilir ve ardından MFA işlemini her seferinde tekrarlamadan şirket kaynaklarını kullanabilir.

>[!NOTE]
>MFA, ADFS sunucusunda kullanıcı başına veya grup başına temelinde gerekli olabilir.  

#### <a name="mfa-without-intune"></a>Intune olmadan MFA
MFA’yı federasyon sunucunuzda ayarlar ancak Intune’da kayıt için etkinleştirmezseniz, kullanıcıların (yalnızca cihaz kaydında değil) şirket kaynaklarına erişirken her seferinde MFA’yı kullanmaları gerekir.

Ayrıca, kullanıcı başına temelinde, kullanıcılar şirket kaynaklarına her eriştiğinde MFA’yı kullanmalarını gerekli kılmak için, Azure Active Directory (Azure AD) MFA’sını kullanabilirsiniz. Azure AD MFA, şirket içi BT altyapısı gerektirmeyen bir bulut hizmetidir. Azure AD MFA'yı ayarlama hakkında bilgi edinmek için bkz. [Bulutta Azure Multi Factor Authentication kullanmaya başlarken](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## <a name="requiring-adfs-mfa-during-enrollment-of-windows-devices"></a>Windows cihazlarının kaydı sırasında ADFS MFA gerektirme
ADFS'de MFA'yı etkinleştirme hakkında bilgi için bkz. [Hassas Uygulamalar için Ek Multi Factor Authentication ile Risk Yönetimi](http://technet.microsoft.com/library/dn280949.aspx).

## <a name="set-up-device-enrollment-mfa-in-intune"></a>Intune’da cihaz kaydı MFA’sı ayarlama
>[!Important]  
>Windows cihazlarının Intune kaydı için MFA’yı gerektirmeden önce, Azure AD kiracınızda veya şirket içi ortamınızda MFA’yı etkinleştirin. Bunu yapmazsanız ve Azure AD Katılım sırasında otomatik kayıt ayarlandıysa, Windows cihazlarını kaydetmeyi deneyen veya cihazlarının Azure AD’ye katılmasını sağlamaya çalışan kullanıcılar hata iletisi alır.

1.  Intune yönetici konsolunda, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Multi-factor authentication**'ı seçin.

2.  **Multi-factor Authentication’ı Yapılandır**’ı ve ardından **Multi-factor Authentication'ı Etkinleştir**’i seçin.



<!--HONumber=Nov16_HO1-->


