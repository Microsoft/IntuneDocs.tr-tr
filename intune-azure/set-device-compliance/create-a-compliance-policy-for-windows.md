---
title: "Windows için uyumluluk ilkesi oluşturma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Windows cihazları için uyumluluk ilkesi oluşturmayı öğrenin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: 58ed00fe7070d81d9d64c70ff7ffe9854c05eac9


---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde Windows cihazları için cihaz uyumluluk ilkesi oluşturma


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Uyumluluk ilkeleri her platform için oluşturulur.  Uyumluluk ilkesini Azure Portal’da oluşturabilirsiniz. Uyumluluk ilkesinin ne olduğu hakkında daha fazla bilgi edinmek için, [Uyumluluk ilkesi nedir](what-is-device-compliance.md) konusuna bakın. Uyumluluk ilkesi oluşturmadan önce ilgilenmeniz gereken önkoşullar hakkında bilgi edinmek için, [Cihaz uyumluluğuyla çalışmaya başlama](get-started-with-device-compliance.md) konusuna bakın.

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

---------------------------

| **İlke ayarı** | **Windows 8.1 ve üzeri** | **Windows Phone 8.1 ve üzeri** |
|----| ----| --- |
| **PIN veya Parola yapılandırması** | Çözümlendi | Çözümlendi |   
| **Cihaz şifrelemesi** | Uygulanamaz | Çözümlendi |   
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Uygulanamaz | Uygulanamaz |  
| **E-posta profili** | Uygulanamaz | Uygulanamaz |   
| **En düşük işletim sistemi sürümü** | Karantinaya Alındı | Karantinaya Alındı |   
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı | Karantinaya Alındı |   
| **Windows durum kanıtlama** | Karantinaya alındı: Windows 10 ve Windows 10 Mobile|Uygulanamaz: Windows 8.1 |

-------------------------------

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)+

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihazlar uyumsuz olduğunda, aşağıdaki işlemler yapılır:+

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal’da uyumluluk ilkesi oluşturma

1. **Intune** dikey penceresinde **Cihaz uyumluluğunu ayarla**’yı seçin. **Yönet**’in altında **Tüm cihaz uyumluluk ilkeleri**’ni ve sonra da **Oluştur**’u seçin.
2. Ad ve açıklama yazın, bu ilkenin uygulanmasını istediğiniz platformu seçin.
3. **Uyumluluk gereksinimleri**’ni seçerek uyumluluk gereksinimleri dikey penceresini açın.  Burada **Güvenlik**, **Cihaz durumu** ve **Cihaz özelliği** ayarlarını belirtebilirsiniz. Bitirdiğinizde, **Tamam**’ı seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Uyumluluk – ilkeler** dikey penceresinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz dikey pencereyi açar.
2. Azure AD güvenlik gruplarının görüntülendiği dikey pencereyi açmak için **Grupları seçin** öğesini seçin.  **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

İlkeyi kullanıcılara uyguladınız.  İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenecek.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın.
- **Basit parolalara izin ver:** Kullanıcıların '**1234**' veya '**1111**' gibi basit parolalar oluşturmalarına izin vermek için bunu **Evet** olarak ayarlayın.
- **Minimum parola uzunluğu:** Kullanıcı parolasının içermesi gereken rakam veya karakter sayısı alt sınırını belirtin.
- **Gerekli parola türü:** Kullanıcıların oluşturacağı parolanın **Alfasayısal** mı, yoksa **Sayısal** mı olacağını belirtin.

Windows çalıştıran ve Microsoft Hesabı ile erişilen cihazlarda, minimum parola uzunluğu sekiz karakterden fazlaysa veya minimum karakter kümesi sayısı ikiden büyükse, uyumluluk ilkesi düzgün değerlendirme yapamaz.

- **Karakter kümesi sayısı alt sınırı:** **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
  - Küçük harfler
  - Büyük harfler
  - Simgeler
  - Sayılar

Bu ayar için daha yüksek bir sayı ayarlandığında, kullanıcıların daha karmaşık parolalar oluşturması zorunlu tutulur. Windows çalıştıran ve Microsoft Hesabı ile erişilen cihazlarda, minimum parola uzunluğu sekiz karakterden fazlaysa veya minimum karakter kümesi sayısı ikiden büyükse, uyumluluk ilkesi düzgün değerlendirme yapamaz.

- **Parola istenmeden önceki bekleme süresi (dakika olarak:** Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtir.
- **Parola kullanım süresi (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.
- **Önceki parolaların yeniden kullanılmasını engelle:** **Parola geçmişini anımsa** seçeneği belirlenirse, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.
- **Cihaz boşta durumundan çıkarken parola iste:** Bu ayar, **Parola istenmeden önceki bekleme süresi (dakika olarak)** ayarıyla birlikte kullanılmalıdır. **Parola istenmeden önceki bekleme süresi (dakika olarak)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcılardan bir parola girmesi istenir.

**Bu ayar yalnızca Windows 10 Mobile cihazları için geçerlidir.**

### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir:** Cihazın kaynaklara bağlanmak için şifrelenmesini gerektirmek için bunu **Evet** olarak ayarlayın.



## <a name="device-health-settings"></a>Cihaz durumu ayarları

- **Cihazların sağlam olarak bildirilmesini gerektir:** **Windows 10 Mobile** cihazlarının yeni veya var olan Uyumluluk İlkelerinde sağlıklı olarak bildirilmesini gerektiren bir kural ayarlayabilirsiniz. Bu ayar etkinse, Windows 10 cihazları aşağıdaki veri noktaları için Durum Kanıtlama Hizmeti (HAS) aracılığıyla değerlendirilir:
  - **BitLocker etkin:** BitLocker açık olduğunda, sistemin kapalı olduğu veya hazırda beklemeye girdiği durumlarda cihaz sürücüye depolanmış verileri yetkisiz erişimden koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumak ve bir bilgisayarın katılımsız bırakılması, kaybolması veya çalınması durumunda bile kurcalanmadığından emin olmak üzere TPM’yi kullanır. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulayana kadar anahtarlara erişilemez.
  - **Kod bütünlüğü etkin:** Kod bütünlüğü bir sürücünün veya sistem dosyasının belleğe yüklendiği her durumda bütünlüğünü doğrulayan bir özelliktir. Kod bütünlüğü, çekirdeğe imzasız bir sürücünün veya sistem dosyasının yüklenip yüklenmediğini veya bir sistem dosyasının yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılan kötü amaçlı yazılım tarafından değiştirilip değiştirilmediğini algılar.
  - **Güvenli Önyükleme etkin:** Güvenli Önyükleme etkinleştirildiğinde sistem güvenilen fabrika durumuna önyüklenmeye zorlanır. Ayrıca, Güvenli Önyükleme etkinleştirildiğinde makineyi önyüklemek için kullanılan çekirdek bileşenleri cihazı üreten kuruluş tarafından güvenilen doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı makinenin başlatılmasına izin vermeden önce bunu doğrular. Herhangi dosya ile imzalarını bozacak şekilde oynanmışsa sistem önyüklemesi gerçekleşmez.

HAS hizmetinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Durum Kanıtlama CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.
- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Minimum parola uzunluğu:** - Windows 8.1’de desteklenir.

Kullanıcı parolasının içermesi gereken rakam veya karakter sayısı alt sınırını belirtin.

Microsoft Hesabı ile güvenliği sağlanan cihazlar için, **Minimum parola uzunluğu** 8 karakterden fazlaysa veya **Minimum karakter kümesi sayısı** iki karakterden büyükse, uyumluluk ilkesi düzgün değerlendirme yapamaz.

- **Gerekli parola türü** - Windows RT, Windows RT 8.1 ve Windows 8.1'de desteklenir.

Kullanıcıların **Alfasayısal** parola mı yoksa **Sayısal** parola mı oluşturması gerektiğini belirtin.

- **Karakter kümesi sayısı alt sınırı** - Windows RT, Windows RT 8.1 ve Windows 8.1'de desteklenir. **Gerekli parola türü** **Alfasayısal** olarak ayarlanırsa bu ayar parolanın içermesi gereken en az karakter kümesi sayısını belirtir. Dört karakter kümesi şunlardır:
  - Küçük harfler
  - Büyük harfler
  - Simgeler
  - Sayılar: Bu ayar için daha yüksek bir sayı ayarlandığında, kullanıcıların daha karmaşık parolalar oluşturması zorunlu tutulur.

Microsoft Hesabı ile güvenliği sağlanan cihazlar için, **Minimum parola uzunluğu** 8 karakterden fazlaysa veya **Minimum karakter kümesi sayısı** 2 karakterden büyükse, uyumluluk ilkesi düzgün değerlendirme yapamaz.

- **Parola istenmeden önceki bekleme süresi (dakika olarak):** - Windows RT, Windows RT 8.1 ve Windows 8.1’de desteklenir.

Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.

- **Parola kullanım süresi (gün)** - Windows RT, Windows RT 8.1 ve Windows 8.1'de desteklenir.

Kullanıcının parolasının süresi dolup yeni bir parola oluşturmaları gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Parola geçmişini anımsa:** - Windows RT, Windows RT 8.1 ve Windows 8.1’de desteklenir.

Kullanıcının önceden kullanılan parolaları oluşturmasını sınırlamak için bu ayarı **Önceki parolaların yeniden kullanılmasını engelle** ile birlikte kullanın.

- **Önceki parolaların yeniden kullanılmasını engelle:** - Windows RT, Windows RT 8.1 ve Windows 8.1’de desteklenir.

**Parola geçmişini anımsa** ayarı seçilirse, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.


## <a name="device-health-settings"></a>Cihaz durumu ayarları

- **Cihazların sağlam olarak bildirilmesini gerektir:** - Windows 10 cihazlarında desteklenir. Windows 10 cihazlarının yeni veya var olan Uyumluluk İlkelerinde sağlıklı olarak bildirilmesini gerektiren bir kural ayarlayabilirsiniz. Bu ayar etkinse, Windows 10 cihazları aşağıdaki veri noktaları için Durum Kanıtlama Hizmeti (HAS) aracılığıyla değerlendirilir:
  - **BitLocker etkin:** BitLocker açık olduğunda, sistemin kapalı olduğu veya hazırda beklemeye girdiği durumlarda cihaz sürücüye depolanmış verileri yetkisiz erişimden koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumak ve bir bilgisayarın katılımsız bırakılması, kaybolması veya çalınması durumunda bile kurcalanmadığından emin olmak üzere TPM’yi kullanır. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulayana kadar anahtarlara erişilemez.
  - **Kod bütünlüğü etkin:** Kod bütünlüğü bir sürücünün veya sistem dosyasının belleğe yüklendiği her durumda bütünlüğünü doğrulayan bir özelliktir. Kod bütünlüğü, çekirdeğe imzasız bir sürücünün veya sistem dosyasının yüklenip yüklenmediğini veya bir sistem dosyasının yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılan kötü amaçlı yazılım tarafından değiştirilip değiştirilmediğini algılar.
  - **Güvenli Önyükleme etkin:** Güvenli Önyükleme etkinleştirildiğinde sistem güvenilen fabrika durumuna önyüklenmeye zorlanır. Ayrıca, Güvenli Önyükleme etkinleştirildiğinde makineyi önyüklemek için kullanılan çekirdek bileşenleri cihazı üreten kuruluş tarafından güvenilen doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı makinenin başlatılmasına izin vermeden önce bunu doğrular. Herhangi dosya ile imzalarını bozacak şekilde oynanmışsa sistem önyüklemesi gerçekleşmez.
  - **Erken başlatılan kötü amaçlı yazılımdan koruma etkin:** Erken başlatılan kötü amaçlı yazılımdan koruma (ELAM), ağınızdaki bilgisayarlar başlatıldığında ve üçüncü taraf sürücüler başlatılmadan önce koruma sağlar.

HAS hizmetinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Durum Kanıtlama CSP](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **Gereken en düşük işletim sistemi:** - Windows 8.1 ve Windows 10’da desteklenir.

Burada birincilsürüm.ikincilsürüm.yapı numarasını belirtin. Sürüm numarası, ```winver``` komutu tarafından döndürülen sürüme karşılık gelmelidir.

Cihazdaki işletim sistemi belirtilen sürümden önceki bir sürümdeyse, cihazın uyumsuz olduğu bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **İzin verilen en yüksek işletim sistemi sürümü:** - Windows 8.1 ve Windows 10’da desteklenir.

Bir cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişimi engellenir ve kullanıcıdan BT yöneticisi ile iletişim kurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

**Gereken en düşük işletim sistemi sürümü** ve **İzin verilen en yüksek işletim sistemi sürümü** ayarlarında kullanılacak işletim sistemi sürümünü bulmak için, komut isteminde **winver** komutunu çalıştırın. Bu winver komutu, işletim sisteminin bildirilen sürümünü döndürür.+

- Windows 8.1 bilgisayarları **3** sürümünü döndürür. Windows için işletim sistemi sürüm kuralı Windows 8.1’e ayarlanırsa, cihaz Windows 8.1’e sahip olsa bile uyumsuz olarak bildirilir.
- Windows 10 çalıştıran bilgisayarlarda, sürüm &quot;10.0&quot;+ winver komutuyla döndürülen İS Derleme numarasına ayarlanmalıdır.

<!--- ## Next steps

[How to monitor device compliance](monitor-device-compliance.md)--->



<!--HONumber=Feb17_HO1-->


