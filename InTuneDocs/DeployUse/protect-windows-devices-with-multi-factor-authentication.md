---
title: "Windows için Multi Factor Authentication | Microsoft Intune"
description: "Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak için, Multi Factor Authentication’ı (MFA) tümleştirir."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: c2c1a35152dc0f9ec9464c056fed3300540bf33c


---

# Windows cihazlarını Multi-Factor Authentication ile koruma
Microsoft Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak için, Multi Factor Authentication’ı (MFA) tümleştirir. MFA, metin kimlik doğrulamasının yanı sıra kullanıcı adları ve parolalar gibi kimlik doğrulama faktörleri gerektirir. Intune, Windows 8.1 veya üzerinde, Windows Phone 8.1 veya Windows 10 Masaüstü ve Mobil cihazlarının kaydı sırasında MFA kullanımını destekler. 

## ADFS MFA için şirket içi altyapı gereksinimleri
Multi Factor Authentication'ı kurmak için şunlar gerekir:

-   **ADFS sunucusunun katıldığı bir Active Directory etki alanı.**

-   **MFA için yapılandırılmış Active Directory Federasyon Hizmetleri (ADFS) sunucusu.** Windows Server 2012 R2 çalıştıran, bir ADFS sunucusu olarak ayarlanmış bir sunucu. Daha fazla bilgi için, bkz. [Windows Server 2012 R2 AD FS ile Azure Multi Factor Authentication Sunucusu kullanarak bulut ve şirket içi kaynakları güvenli hale getirme](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Yukarıda listelenen tüm sunucular, [Windows Server 2012 R2 için Sistem Gereksinimleri ve Yükleme Bilgileri](http://technet.microsoft.com/library/dn303418.aspx)bölümünde sağlanan sistem gereksinimlerini karşılamalıdır.

#### Intune ile MFA
Kuruluşunuzun Active Directory Federasyon Hizmetleri (ADFS) olan bir Active Directory etki alanını içeren şirket içi BT altyapısı varsa, federasyon sunucunuzda MFA'yı yapılandırabilir ve ardından Intune kaydı için MFA’yı etkinleştirebilirsiniz. Intune’da MFA yapılandırarak, kullanıcıların kayıt sırasında bir kez kimlik doğrulamasına, ardından MFA işlemini her seferinde tekrarlamadan olmadan şirket kaynaklarına erişebilmesine olanak sağlarsınız.

>[!NOTE]
>MFA, ADFS sunucusunda kullanıcı başına veya grup başına temelinde gerekli olabilir.  

#### Intune olmadan MFA
MFA’yı federasyon sunucunuzda yapılandırır ancak Intune’da kayıt için yapılandırmazsanız, kullanıcıların şirket kaynaklarına erişirken her seferinde MFA’yı kullanmaları gerekir (yalnızca cihaz kaydında değil).

Ayrıca, kullanıcı başına temelinde, kullanıcılar şirket kaynaklarına her eriştiğinde MFA gerektirmek için, Azure Active Directory (AAD) MFA’sını kullanabilirsiniz. AAD MFA, şirket içi BT altyapısı gerektirmeyen bir bulut hizmetidir. AAD MFA'yı ayarlama hakkında bilgi edinmek için, bkz. [Bulutta Azure Multi Factor Authentication kullanmaya başlarken.](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Windows cihazlarının kaydı sırasında ADFS MFA gerektirme
ADFS'de MFA'yı etkinleştirme hakkında bilgi için bkz. [Hassas Uygulamalar için Ek Multi Factor Authentication ile Risk Yönetimi](http://technet.microsoft.com/library/dn280949.aspx).

## Intune’da cihaz kaydı MFA’sı ayarlama
>[!Important]  
>Windows cihazlarının Intune kaydı için MFA’yı gerektirmeden önce, Azure AD kiracınızda veya şirket içi ortamınızda MFA’yı etkinleştirin. Bunu yapmazsanız, kullanıcılar Windows cihazlarını kaydetmeye çalışırken veya Azure AD Birleştirme sırasında otomatik kayıt yapılandırılmışsa cihazlarını Azure AD birleştirmeye çalışırken bir hata iletisi alır.

1.  Intune yönetim konsolunda, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Multi-factor authentication**'a tıklayın.

2.  **Multi-factor Authentication’ı Yapılandır**’a ve ardından **Multi-factor Authentication'ı Etkinleştir**’e tıklayın.




<!--HONumber=Jul16_HO3-->


