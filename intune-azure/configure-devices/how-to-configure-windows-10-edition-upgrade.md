---
title: "Intune ile Windows 10 sürüm yükseltmelerini yapılandırma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Yönettiğiniz Windows 10 cihazlarını yükseltmek için Intune’u kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 9ce16ea61da87aa5087fafeb5c1eaf743fef4a14


---

# <a name="how-to-configure-windows-10-edition-upgrades"></a>Windows 10 sürüm yükseltmelerini yapılandırma 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Windows 10 sürüm yükseltme profilinin nasıl yapılandırılacağını öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Bu profil aşağıdaki Windows 10 sürümlerinden birini çalıştıran cihazları daha yeni bir sürüme otomatik olarak yükseltmenizi sağlar:

- Windows 10 Masaüstü
- Windows 10 Holographic
- Windows 10 Mobile

Aşağıdaki yükseltme yolları desteklenmektedir:

- Windows 10 Pro'dan Windows 10 Enterprise'a
- Windows 10 Home'dan Windows 10 Education'a
- Windows 10 Mobile'dan Windows 10 Mobile Enterprise'a
- Windows 10 Holographic Pro'dan Windows 10 Holographic Enterprise'a

## <a name="before-you-start"></a>Başlamadan önce
Cihazları en son sürüme yükseltmeye başlamadan önce aşağıdakilerden birine sahip olmanız gerekir:

- İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). Çoklu Etkinleştirme Anahtarları (MAK) veya Anahtar Yönetimi Sunucusu (KMS) anahtarlarından herhangi birini kullanabilirsiniz. veya İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
- Hedeflediğiniz Windows 10 cihazları Microsoft Intune’a kayıtlı olmalıdır. Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlar ile sürüm yükseltme ilkesini kullanamazsınız.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, sürüm yükseltme profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinde **Sürüm yükseltme**’yi seçin.
7. **Sürüm Yükseltme** dikey penceresinde aşağıdakileri yapılandırın:
    - **Yükseltmenin uygulanacağı sürüm** - Açılan listeden, cihazlarda yükseltmek istediğiniz Windows 10 sürümünü seçin.
    - **Yükseltilecek sürüm** - Açılan listede, hedeflenen cihazları yükseltmek istediğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
    - **Ürün Anahtarı** - Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını belirtin.<br>.Ürün anahtarı içeren bir ilke oluşturduğunuzda, ürün anahtarını daha sonra düzenleyemezsiniz. Bunun nedeni, anahtarın güvenlik nedeniyle engellenmesidir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girmeniz gerekir.
    - **Lisans Dosyası** - Microsoft’tan aldığınız ve hedeflenen cihazları yükseltmek istediğiniz Windows Holographic veya Windows 10 Mobile sürümünün lisans bilgilerini içeren lisans dosyasını belirlemek için **Gözat**’ı seçin.
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).




<!--HONumber=Feb17_HO1-->


