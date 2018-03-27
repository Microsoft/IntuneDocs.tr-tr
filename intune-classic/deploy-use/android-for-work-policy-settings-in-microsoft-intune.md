---
title: Android for Work ilke ayarları
description: Intune ile yönettiğiniz Android for Work cihazlarda ayarları ve özellikleri denetleyen ilkeler oluşturun.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e42d33b4cc69e6b2cc836e2236c508d97c2245fe
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android for Work ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, [Android for Work cihazlarda](android-for-work.md) yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar.

## <a name="general-configuration-policy"></a>Genel yapılandırma ilkesi

Android for Work cihazlarınızda güvenlik ve iş profili ayarlarını yapılandırmak için Intune **Android for Work genel yapılandırma ilkesi** kullanın.

Aradığınız ayar bu konuda çıkmıyorsa, cihazı denetlemek için OMA-URI ayarları kullanmanıza izin veren bir Android özel ilkesi kullanarak ayar oluşturabilirsiniz. Daha fazla bilgi için bu konunun devamındaki [Özel ilke ayarları](#custom-policy-settings)’na gidin.

> [!TIP]
> Bir iş profili sağlarken, cihazlar otomatik olarak şifrelenir. Bu ayarı değiştiremezsiniz.

### <a name="password-settings"></a>Parola ayarları

|Ayar adı|Ayrıntılar|
|----------------|-|
|**Mobil cihazların kilidini açmak için bir parola iste**|Yönetilen cihazlarda parola gerekip gerekmediğini belirtir. Aşağıdakilerden birini seçin:<br><br>- **Karmaşık** – en az bir harf, rakam ve simge gerektirir<br>- **Alfasayısal** – en az bir rakam ve alfabetik bir karakter gerektirir<br>- **Alfabetik** – en az harf veya semboller gerektirir<br>- **Sayısal karmaşık** – Yinelenen veya ardışık olmayan sayısal karakterler gerektirir<br>- **Sayısal**<br><br>Bu ayar etkin değilse, karmaşıklık gereksinimleri yoktur.|
|**En düşük parola uzunluğu**|Parolada bulunacak en düşük karakter veya rakam sayısını belirtir.|
|**Cihaz kilitlenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Cihaz otomatik olarak kilitlenmeden önce kullanıcının işlem yapmadığı dakika sayısını belirtir.|
|**Akıllı Kilit ve diğer güven aracılarına izin ver**<br>(Android 6 ve üzeri)|Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize izin verir. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.|
|**İş profili kaldırılmadan önce yinelenen oturum açma hatası sayısı**|Cihazdaki iş profili kaldırılmadan önce izin verilen başarısız oturum açma sayısını belirtir. Bu, cihazı tamamen silme işlemi gerçekleştirmez.|
|**Parola geçmişini anımsa**|Daha önce kullanılan parolaların yeniden kullanılmasını engeller.|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Daha önce kullanılan parolalardan kaç tanesinin hatırlanacağını belirtir.|
|**Parola kullanım süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|
|**Parmak izi ile kilit açmaya izin ver**<br>(Android 6 ve üzeri)|Bu özelliğe sahip cihazların kilidini açmak için parmak izi kullanmanıza olanak sağlar.|


### <a name="work-profile-settings"></a>İş profili ayarları

|Ayar adı|Ayrıntılar|
|----------------|-|
|**İş profili ve kişisel profil arasında veri paylaşımına izin ver**|İş profilindeki uygulamaların kullanıcıların kişisel profiliyle veri paylaşmasına izin verir. Aşağıdakilerden birini seçin:<br><br>- **Sınırlar arasında tüm paylaşımları engelle**<br>- **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir**<br>- **Paylaşım kısıtlaması yok**|
|**Cihaz kilitliyken iş profili bildirimlerini gizle**<br>(Android 6 ve üzeri)|Cihaz kilitliyken iş profilinde herhangi bir bildirim gösterilip gösterilmeyeceğini denetler.|
|**Varsayılan uygulama izni ilkesini ayarla**<br>(Android 6 ve üzeri)|İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6'dan başlayarak, uygulamaların gerektirdiği bazı izinler çalışma zamanında son kullanıcıdan istenir.  Bu ilke ayarı, iş profilinde kullanıcılardan izin vermelerinin istenip istenmeyeceğine veya nasıl isteneceğine BT’nin karar vermesine olanak tanır. <br/><br/>Örneğin, BT, iş profiline konum erişimi gerektiren bir uygulama gönderebilir.  Normalde bu uygulama, kullanıcıya konum erişimi izni vermek isteyip istemediğini sorar ve kullanıcı bunu kabul edebilir veya reddedebilir.  Bu ilke, tüm izinlerin istem olmadan otomatik olarak verilip verilmeyeceğine, istem olmadan otomatik olarak reddedilip reddedilmeyeceğine veya son kullanıcının karar vermesine BT’nin karar vermesine olanak tanır.|


## <a name="custom-policy-settings"></a>Özel ilke ayarları
Android for Work cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune **Android for Work özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılabilir olmayan Android ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.
Intune, şu anda sınırlı sayıda Android özel ilkesi destekler. Hangi ilkeleri yapılandırabileceğinizi öğrenmek için bu konu başlığındaki örneklere bakın.

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için Android özel ilkesine benzersiz bir ad girin.|
    |**Açıklama**|Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### <a name="oma-uri-settings"></a>OMA-URI ayarları

   |Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar Adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize, Dize (XML), Tarih ve saat, Tamsayı, Kayan nokta** veya **Boole değeri** seçeneklerinden birini belirleyin.|
    |**OMA-URI (büyük küçük harfe duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### <a name="examples"></a>Örnekler

- [Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma](pre-shared-key-wi-fi-profile.md)
- [Özel ilke kullanarak Android cihazları için uygulama başına VPN profili oluşturma](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
