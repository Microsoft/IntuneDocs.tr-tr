---
title: "Intune ekleme işlemi | Microsoft Docs"
description: "Bu makalede, Intune yalnızca bulut çözümünü ortamınıza eklerken göz önünde bulundurmanız gereken tüm ayrıntılar sağlanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa33bd3833f7f7198eed3f4f486c27bae3ba47d7
ms.openlocfilehash: 87832ec7f295c08678052d19164af9a8db051f9f


---

# <a name="intune-implementation"></a>Intune’un uygulanması

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Ekleme aşaması sırasında Intune’u üretim ortamınıza uygulayacaksınız. Uygulama işlemi, bu kılavuzun daha önceki bölümlerinde incelenen [kullanım örneği gereksinimlerinize](section-3-determine-use-case-requirements.md) dayalı olarak Intune ve (gerekirse) dış bağımlılıkların kurulması ve yapılandırılmasından oluşur.

Aşağıdaki bölümde, gereksinimleri ve üst düzey görevleri içeren Intune’un uygulanma işlemine genel bir bakış sağlanır.

>[!TIP]
> Intune’un uygulanma işlemi hakkında daha fazla bilgi için [Ek kaynaklar](additional-resources.md)’a göz atın.

## <a name="intune-requirements"></a>Intune gereksinimleri

Tek başına Intune için temel gereksinimler aşağıda verilmiştir:

-   EMS/Intune aboneliği

-   Office 365 aboneliği (Office uygulamaları ve MAM ilkesiyle yönetilen uygulamalar için)

-   Apple APNs Sertifikası (iOS cihaz platformu yönetimini etkinleştirmek için)

-   Azure AD Connect (dizin eşitleme için)

-   Exchange için Intune Şirket İçi Bağlayıcısı (gerekirse Şirket İçi Exchange için CA)

-   Intune Sertifika Bağlayıcısı (gerekirse SCEP sertifika dağıtımı için)

>[!TIP]
> Tek başına Intune gereksinimleri hakkında daha fazla bilgiyi [burada](https://docs.microsoft.com/intune/get-started/what-to-know-before-you-start-microsoft-intune) bulabilirsiniz.

## <a name="intune-implementation-process"></a>Intune’un uygulanma işlemi

### <a name="overview-of-implementation-tasks"></a>Uygulama görevlerine genel bakış

Intune’un uygulanması sırasındaki her göreve genel bir bakış aşağıdadır.

#### <a name="task-1-add-intune-subscription"></a>Görev 1: Intune aboneliği ekleme

Önceki gereksinimler bölümünde tanımlandığı gibi bir EMS veya Intune aboneliği gereklidir. Kuruluşunuz bir EMS veya Intune aboneliğine sahip değilse Enterprise Mobility + Security (EMS) veya Intune satın almak için lütfen Microsoft ile veya Microsoft Hesap Ekibinizle temasa geçin.

-   [Microsoft Intune satın alma](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-pricing) hakkında daha fazla bilgi edinin.

#### <a name="task-2-add-office-365-subscription"></a>Görev 2: Office 365 aboneliği ekleme

Bu adım isteğe bağlıdır. Önceki gereksinimler bölümünde tanımlandığı gibi, Exchange Online kullanmayı ve Office mobil uygulamalarını MAM ilkesiyle yönetmeyi planlıyorsanız bir Office 365 aboneliği gereklidir. Kuruluşunuz bir Office 365 aboneliğine sahip değilse Office 365 satın almak için lütfen Microsoft ile veya Microsoft hesap ekibinizle temasa geçin.

-   [Office 365 satın alma](https://products.office.com/business/compare-office-365-for-business-plans) hakkında daha fazla bilgi edinin.

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Görev 3: Azure AD'de kullanıcı grupları ekleme

Intune dağıtımı kullanım örneği senaryolarına ve gereksinimlerine bağlı olarak AD veya AAD’ye kullanıcı veya güvenlik grupları eklemeniz gerekebilir. Active Directory veya Azure Active Directory’deki mevcut kullanıcılarınızı ve güvenlik gruplarınızı gözden geçirerek gereksinimlerinizi tam olarak karşılayıp karşılamadıklarını belirlemelisiniz. Yeni kullanıcılar ve güvenlik grupları, Active Directory'ye en yaygın olarak Azure AD Directory Connect kullanılarak eklenir ve Azure Active Directory ile eşitlenir.

-   [Intune'a kullanıcılar/gruplar ekleme](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) hakkında daha fazla bilgi edinin.

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Görev 4: Intune ve Office 365 kullanıcı lisansları atama

EMS/Intune ve Office 365 dağıtımı için hedeflenen tüm kullanıcıların kendilerine atanmış bir lisansı olması gerekir. EMS/Intune ve Office 365 lisans ataması, Office 365 Yönetim Merkezi Portalında yapılabilir.

-   [Intune lisansları atama](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4) hakkında daha fazla bilgi edinin.

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Görev 5: Mobil Cihaz Yönetimi Yetkilisi Olarak Intune’u Ayarlama

Intune kullanarak cihazları kurma, yapılandırma, yönetme ve kaydetmeye başlamadan önce Cihaz Yönetimi Yetkilisi olarak Intune’u ayarlamanız gerekir. Cihaz Yönetimi Yetkilisi ayarlama görevi, Intune Yönetim Portalı'ndan yönetim çalışma alanında gerçekleştirilir.

-   [Cihaz Yönetimi Yetkilisini ayarlama](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority) hakkında daha fazla bilgi edinin.

#### <a name="task-6-enable-device-platforms"></a>Görev 6: Cihaz platformlarını etkinleştirme

Varsayılan olarak, Intune Yönetim konsolunda Apple cihazları (iOS ve Mac) dışında çoğu cihaz platformu etkinleştirilmiştir. iOS cihazlarını Intune’a kaydetmek ve Intune ile yönetmek için önce cihaz platformunun etkinleştirilmesi gerekir. iOS cihaz platformunu etkinleştirme işlemi üç adımdan oluşur: APNs sertifikasını oluşturmak ve indirmek, APNs sertifikasını Intune'a yüklemek.

-   [iOS ve Mac cihaz yönetimi kurulumunun nasıl çalıştığı](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Görev 7: Hüküm ve koşullar ilkeleri ekleme ve dağıtma

Microsoft Intune hüküm ve koşullar ilkelerinin eklenmesini ve dağıtılmasını destekler. Hüküm ve koşullar ilkelerinin eklenmesi ve dağıtılması, Intune Yönetim Portalı'nda İlke çalışma alanında gerçekleştirilir. Hüküm ve koşullar ilkelerini gerektiği gibi ekleyin ve Intune dağıtım kullanım örneklerinize ve gereksinimlerinize göre hedeflenen gruplara dağıtın.

-   [Hüküm ve koşullar ilkeleri ekleme ve dağıtma](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Görev 8: Yapılandırma ilkeleri ekleme ve dağıtma

Microsoft Intune iki tür Yapılandırma ilkesi eklenmesini ve dağıtılmasını destekler: Genel ve Özel. Yapılandırma ilkelerinin eklenmesi ve dağıtılması, Intune Yönetim Portalı'nda İlke çalışma alanında gerçekleştirilir. Yapılandırma ilkelerini gerektiği gibi ekleyin ve Intune dağıtım kullanım örneklerinize ve gereksinimlerinize göre hedeflenen gruplara dağıtın.

-   [Yapılandırma ilkeleri ekleme ve dağıtma](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) hakkında daha fazla bilgi edinin.

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Görev 9: Kaynak profilleri ekleme ve dağıtma

Microsoft Intune E-posta, Wi-Fi ve VPN profillerini destekler. Profillerin eklenmesi ve dağıtılması Intune Yönetim Portalı'nda, İlke çalışma alanında gerçekleştirilir. E-posta/Wi-Fi/VPN profillerini gerektiği gibi ekleyin ve Intune dağıtım kullanım örneklerinize ve gereksinimlerinize göre hedeflenen gruplara dağıtın.

-   [Intune ile şirket kaynaklarına erişimi etkinleştirme](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="task-10-add-and-deploy-apps"></a>Görev 10: Uygulama ekleme ve dağıtma

Microsoft Intune; Web, LOB ve Genel Mağaza Uygulamalarının dağıtımını destekler. Ek olarak, MAM ilkeleriyle ilişkilendirerek Intune SDK’sını tümleştiren uygulamaların yönetimi de desteklenir. Uygulamaların eklenmesi ve dağıtılması, Intune Yönetim Portalı'nda Uygulama çalışma alanında gerçekleştirilir. MAM ilkelerinin eklenmesi ve dağıtılması, Intune Yönetim Portalı'nda İlke çalışma alanında gerçekleştirilir. Uygulamaları gerektiği gibi ekleyin ve Intune dağıtım kullanım örneklerinize ve gereksinimlerinize göre hedeflenen gruplara dağıtın.

-   [Uygulama ekleme ve dağıtma](https://docs.microsoft.com/en-us/intune/deploy-use/deploy-apps) hakkında daha fazla bilgi edinin.

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Görev 11: Uyumluluk ilkelerini ekleme ve dağıtma

Microsoft Intune, Uyumluluk ilkelerini destekler. Uyumluluk ilkelerinin eklenmesi ve dağıtılması, Intune Yönetim Portalı'nda İlke çalışma alanında gerçekleştirilir. Uyumluluk ilkelerini gerektiği gibi ekleyin ve Intune dağıtım kullanım örneklerinize ve gereksinimlerinize göre hedeflenen gruplara dağıtın.

-   [Uyumluluk ilkeleri](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="task-12-enable-conditional-access-policies"></a>Görev 12: Koşullu Erişim İlkelerini Etkinleştirme

Microsoft Intune Exchange Online ve Şirket İçi Exchange, SharePoint Online, Skype Kurumsal Çevrimiçi Sürüm ve Dynamics CRM Online için Koşullu Erişimi destekler. Koşullu Erişim ilkeleri, Intune Yönetim Portalında İlke çalışma alanında etkinleştirilir. Koşullu Erişimi [Intune dağıtım kullanım örneklerinize ve gereksinimlerinize](section-3-determine-use-case-requirements.md) göre uygun şekilde etkinleştirin ve yapılandırın.

-   [Koşullu erişim](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) hakkında daha fazla bilgi edinin.

#### <a name="task-13-enroll-devices"></a>Görev 13: Cihazları kaydetme

Intune; iOS, Mac OS, Android, Windows masaüstü ve Windows mobil cihaz platformlarını destekler. Mobil cihaz platformlarını Intune dağıtımı kullanım örneklerinize ve gereksinimlerinize göre uygun şekilde kaydedin.

-   [Cihazları kaydetme](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune) hakkında daha fazla bilgi edinin.

>[!TIP]
> Intune’un uygulanma işlemi hakkında daha fazla bilgi için bu [Microsoft Sanal Akademi Intune oturumu modülüne](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) göz atın.

## <a name="next-section"></a>Sonraki Bölüm

Sonraki bölüm [Intune dağıtımınızı sınama ve doğrulama](section-9-test-and-validation.md) hakkında yönergeler sağlar.



<!--HONumber=Dec16_HO5-->


