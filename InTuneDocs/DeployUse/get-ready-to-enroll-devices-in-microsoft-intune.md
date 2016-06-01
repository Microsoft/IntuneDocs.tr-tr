---
# required metadata

title: Microsoft Intune’da cihazları kaydetmeye hazırlanma | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da cihazları kaydetmeye hazırlanma
Çalışanların mobil cihazları (Android, iOS ve Windows Phone ile Windows bilgisayarlar) Intune’a kaydetmesine olanak sağlamak için, cihaz kaydını etkinleştirmeniz gerekir. Kayda izin vermek için, bir mobil cihaz yönetimi yetkilisi ayarlamanız, Intune Şirket Portalı’nı yapılandırmanız, lisanslar atamanız ve cihaz platformu için kaydı etkinleştirmeniz gerekir.

## <a name="BKMK_Set_MDM_Authority"></a>Mobil cihaz yönetimi yetkilisini ayarlama
MDM yetkilisi, bir grup cihazı yönetme iznine sahip olan yönetim hizmetini tanımlar. MDM yetkilisi seçenekler arasında Intune’un kendisi ve Intune ile Configuration Manager vardır. Configuration Manager’ı yönetim yetkilisi olarak ayarlarsanız, mobil cihaz yönetimi için başka bir hizmet kullanılamaz.

>[!IMPORTANT]
> Mobil cihazları yalnızca Intune kullanarak mı (çevrimiçi hizmet) yoksa Intune ile System Center Configuration Manager kullanarak mı (çevrimiçi hizmetle birlikte şirket içi yazılım çözümü) yönetmek istediğinizi dikkatlice düşünün. Mobil cihaz yönetim yetkilisini ayarlandıktan sonra, bu değiştirilemez.



1.  [Microsoft Intune yönetim konsolunda,](http://manage.microsoft.com) **Yönetici** &gt; **Mobil Cihaz Yönetimi**’e tıklayın

2.  **Görevler** listesinde **Mobil Cihaz Yönetimi Yetkilisini Ayarla**öğesine tıklayın. **MDM Yetkilisini Ayarla** iletişim kutusu açılır.

    ![MDM yetkilisi ayarla iletişim kutusu](../media/intune-mdm-authority.png)

3.  Intune, Intune’u MDM yetkiliniz olarak isteyip istemediğinizi onaylamanızı ister. Mobil cihazları yönetmek için Microsoft Intune kullanmak istiyorsanız kutuyu işaretleyin ve ardından **Evet** 'e tıklayın.

## Intune Şirket Portalı’nı yapılandırma ve lisans atama
Intune Şirket Portalı, kullanıcıların uygulamalar gibi şirket kaynaklarına erişmesine, yardım masası bilgilerini bulmasına ve cihaz kaydetmesine ve kaydını kaldırmasına yardımcı olur. Cihazları kaydetmeden önce, [Şirket Portalı'nı yapılandırmanız](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7) gerekir. Ayrıca, Intune’a erişime olanak sağlamak için [kullanıcı lisansları atamanız](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) da gerekir.

## Cihaz yönetimi ayarlama
MDM yetkilisini ayarladıktan sonra, kuruluşunuzun desteklemek istediği işletim sistemleri için cihaz yönetimi ayarlamanız gerekir. Cihaz yönetimi ayarlamak için gerekli adımlar, işletim sistemine göre farklılık gösterir. Örneğin, Android işletim sistemi, Intune yönetim konsolunda herhangi bir şey yapmanızı gerektirmez. Diğer taraftan, Windows ve iOS, yönetime olanak sağlamak için cihazlar ve Intune arasında bir güven ilişkisi gerektirir.

> [!div class="op_single_selector"]
- [Microsoft Intune ile Android yönetimini ayarlama](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Microsoft Intune ile Windows Phone yönetimin ayarlama](set-up-windows-phone-management-with-microsoft-intune.md)
- [Microsoft Intune ile Windows cihazı yönetimini ayarlama](set-up-windows-device-management-with-microsoft-intune.md)

Ayrıca şunları yapabilirsiniz:
 - Birçok cihaz kaydetmek için, [cihaz kaydı yöneticisi hesabını](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) kullanabilirsiniz
 - Cihazları kaydetmeye ve hedef ilkeye yardımcı olmak için [IMEI numaraları kullanarak şirkete ait cihazlar belirtebilirsiniz](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO2-->


