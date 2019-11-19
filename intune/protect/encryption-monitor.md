---
title: Microsoft Intune şifreli cihazlar için şifreleme raporu
titleSuffix: Microsoft Intune
description: İOS veya Windows cihaz şifreleme durumunuz hakkında bir rapor görüntüleyin ve Microsoft Intune portalından Filekasası ve BitLocker Kurtarma anahtarlarına erişin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5d9508c5d69b0790efa37ee633f8216bfd2bb30c
ms.sourcegitcommit: 15e099a9a1e18296580bb345610aee7cc4acd126
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74164665"
---
# <a name="monitor-device-encryption-with-intune"></a>Intune ile cihaz şifrelemesini izleme

Microsoft Intune şifreleme raporu, cihazın şifreleme durumu hakkındaki ayrıntıları görüntülemek ve cihaz kurtarma anahtarlarını yönetmek için seçenekleri bulmak için merkezi bir konumdur. Kullanılabilir kurtarma anahtarı seçenekleri, görüntülemekte olduğunuz cihazın türüne bağlıdır.

Raporu bulmak için [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın. **Cihazlar** > **İzleyicisi**' ni seçin ve sonra *yapılandırma*altında **şifreleme raporu**' nu seçin.

## <a name="view-encryption-details"></a>Şifreleme ayrıntılarını görüntüle

Şifreleme raporu, yönettiğiniz desteklenen cihazlar genelinde ortak ayrıntıları gösterir. Aşağıdaki bölümlerde, Intune 'un raporda sunduğu bilgiler hakkındaki ayrıntılar sağlanmaktadır.

### <a name="prerequisites"></a>Önkoşullar

Şifreleme raporu, aşağıdaki işletim sistemi sürümlerini çalıştıran cihazlarda raporlamayı destekler:

- macOS 10,13 veya üzeri
- Windows sürüm 1607 veya üzeri

### <a name="report-details"></a>Rapor ayrıntıları

Şifreleme raporu bölmesinde, bu cihazlarla ilgili üst düzey ayrıntılarla yönettiğiniz cihazların bir listesi görüntülenir. Ayrıntıya git ' i listeden bir cihaz seçebilir ve cihazlar [Cihaz şifreleme durumu](#device-encryption-status) bölmesinden ek ayrıntılar görüntüleyebilirsiniz.

- **Cihaz adı** -cihazın adı.
- **Işletim sistemi** – Windows veya MacOS gibi cihaz platformu.
- **Işletim sistemi sürümü** : cihazdaki Windows veya MacOS sürümü.
- **TPM sürümü** *(yalnızca Windows 10 için geçerlidir)* – Windows 10 cihazında Güvenilir Platform Modülü (TPM) yongasının sürümü.
- **Şifrelemeye hazır olma** : cihazların değerlendirilmesi, BitLocker veya filekasası Şifrelemesi gibi uygun bir şifreleme teknolojisini desteklemeye hazır olma. Cihazlar şu şekilde tanımlanır:
  - **Hazırlanıyor**: cihaz, cihazın aşağıdaki gereksinimleri KARŞıLAMASı gereken MDM ilkesi kullanılarak şifrelenebilir:

    **MacOS cihazları için**:
    - MacOS sürüm 10,13 veya üzeri

    **Windows 10 cihazları için**:
    - Sürüm 1703 veya üzeri, *iş*, *Kurumsal*, *eğitim*veya sürüm 1809 ya da *Pro* 'nun daha yeni sürümü
    - Cihazda bir TPM yongasının olması gerekir

    Daha fazla bilgi için Windows belgelerindeki [BitLocker yapılandırma hizmeti sağlayıcısına (CSP)](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) bakın.

  - **Yok**: cihazın tam şifreleme becerileri yoktur, ancak yine de şifrelemeyi destekler. Örneğin, bir Windows cihazı, bir kullanıcı tarafından el ile veya TPM olmadan şifrelemeye izin vermek üzere ayarlanabilir grup ilkesi aracılığıyla şifrelenmiş olabilir.
  - **Uygulanamaz**: Bu cihazı sınıflandırmak için yeterli bilgi yok.

- **Şifreleme durumu** – işletim sistemi sürücüsünün şifrelenip şifrelenmediği.

- **Kullanıcı asıl adı** -cihazın birincil kullanıcısı.

### <a name="device-encryption-status"></a>Cihaz şifreleme durumu

Şifreleme raporundan bir cihaz seçtiğinizde, Intune **Cihaz şifreleme durumu** bölmesini görüntüler. Bu bölme aşağıdaki ayrıntıları sağlar:

- **Cihaz adı** – görüntülemekte olduğunuz cihazın adı.

- **Şifreleme hazırlığı** -CIHAZLARıN değerlendirmesi MDM ilkesi aracılığıyla şifrelemeyi desteklemeye hazır.

  Örneğin: bir Windows 10 cihazının *hazır olmadığı hazır*olmadığında, şifrelemeyi desteklemeye devam edebilir. Hazırlama *atamasını sağlamak* Için, Windows 10 CIHAZıNıN bir TPM yongasına sahip olması gerekir. Şifrelemeyi desteklemek için TPM yongaları gerekli değildir. (Daha fazla bilgi için, önceki bölümde *şifreleme hazırlığı* bölümüne bakın.)

- **Şifreleme durumu** -işletim sistemi sürücüsünün şifreli olup olmadığı. Intune 'un bir cihazın şifreleme durumunu veya bu duruma yönelik bir değişikliği rapor etmek 24 saate kadar sürebilir. Bu süre, işletim sisteminin şifrelenmesi için zaman ve cihazın Intune 'a geri rapor olması için zaman içerir.

  Cihaz iade etme işlemi normalde gerçekleşmeden önce, Filekasası şifreleme durumunun raporlanmasını hızlandırmak için, şifreleme tamamlandıktan sonra kullanıcıların cihazlarını eşitlemesini sağlayabilirsiniz.

- **Profiller** – bu cihaza uygulanan ve aşağıdaki değerlerle yapılandırılmış olan *cihaz yapılandırma* profillerinin bir listesi:

  - MacOS
    - Profil türü = *Endpoint Protection*
    - Ayarlar > Filekasası > Filekasası = *Etkinleştir*

  - Windows 10:
    - Profil türü = *Endpoint Protection*
    - Ayarlar > Windows şifrelemesi > şifreleme cihazları = *iste*

  *Profil durumu özetinden* sorun olduğunu belirlemek için profil listesini tek tek gözden geçirmek için kullanabilirsiniz.

- **Profil durumu Özeti** : Bu cihaza uygulanan profillerin Özeti. Özet, uygulanabilir profiller genelinde en az iyi koşulu temsil eder. Örneğin, birkaç uygulanabilir profilden yalnızca biri bir hata ile sonuçlanırsa, *profil durumu Özeti* *hata*görüntüler.

  Bir durumun daha fazla ayrıntılarını görüntülemek için **ıntune** > **cihaz yapılandırması** > **profiller**' e gidin ve profili seçin. İsteğe bağlı olarak, **cihaz durumu** ' nu seçin ve ardından bir cihaz seçin.

- **Durum ayrıntıları** – cihazın şifreleme durumu hakkında gelişmiş ayrıntılar.

  > [!IMPORTANT]
  > Windows 10 cihazlarında, Intune yalnızca *Windows 10 nisan 2019 güncelleştirme* veya üstünü çalıştıran cihazların *durum ayrıntılarını* gösterir.

  Bu alan, algılanabildiği her bir hata için bilgileri görüntüler. Bu bilgileri, bir cihazın neden şifreleme için hazırlanamadığına ilişkin bir neden olduğunu anlamak için kullanabilirsiniz.

  Intune 'un rapor verebir durum ayrıntıları aşağıda verilmiştir:

  **MacOS**:
  - Kurtarma anahtarı henüz alınmadı ve henüz depolanmadı. Büyük olasılıkla, cihazın kilidi açık değil veya iade edilmedi.

    *Göz önünde bulundurun: Bu sonuç bir hata koşulunu temsil etmelidir, ancak cihazda, şifreleme isteği cihaza gönderilmeden önce kurtarma anahtarları için Emanet 'in ayarlanmış olması gereken, geçici bir durum olabilir. Bu durum Ayrıca cihazın kilitli kaldığını veya son zamanlarda Intune ile iade edilmedi olduğunu gösteriyor olabilir. Son olarak, bir cihaz takılıncaya kadar Filekasası şifrelemesi başlamadığı için, bir kullanıcının henüz şifrelenmeyen bir cihaz için kurtarma anahtarı alması mümkündür*.

  - Kullanıcı şifrelemeyi erteleniyor veya şu anda şifreleme sürecinde.

    *Göz önünde bulundurun: Kullanıcı, şifreleme isteğini aldıktan sonra henüz oturum açmamış, çünkü dosya kasasının cihazı şifreleyebilmesi için gerekli olan veya kullanıcının cihazı el ile şifresini açtığı durumda. Intune, bir kullanıcının cihazının şifresini çözmesini engellemez.*

  - Cihaz zaten şifrelendi. Devam etmek için cihazın Kullanıcı tarafından şifresinin çözülmesi gerekir.

    *Göz önünde bulundurun: Intune zaten şifrelenmiş bir cihazda Filekasasını ayarlayamıyorum. Bunun yerine, bir cihaz yapılandırma ilkesi ve Intune tarafından yönetilebilmesi için kullanıcının cihazının el ile şifresinin çözülmesi gerekir*.

  - Filekasasının, kullanıcının MacOS Catalina ve üzeri bir yönetim profilini onaylaması gerekir.

    *Göz önünde bulundurun: MacOS sürüm 10,15 (Catalina) Ile başlayarak, kullanıcının onayladığı kayıt ayarları, kullanıcıların dosya kasasını şifrelemeyi el ile onaylama gereksinimine neden olabilir. Daha fazla bilgi için bkz. Intune belgelerinde [Kullanıcı onaylı kayıt](../enrollment/macos-enroll.md)* .

  - Bilinmeyen.

    *Göz önünde bulundurun: bilinmeyen bir durumun nedeni, cihazın kilitlenmesinden ve Intune 'un Emanet veya şifreleme işlemini başlatamamasına neden olabilir. Cihazın kilidi açıldıktan sonra, ilerleme devam edebilir*.

  **Windows 10**:
  - BitLocker ilkesi için Kullanıcı onayı 'Nın, işletim sistemi biriminin şifrelemesini başlatmak üzere BitLocker Sürücü Şifrelemesi Sihirbazı 'Nı başlatması gerekir, ancak Kullanıcı onay vermedi.

  - İşletim sistemi biriminin şifreleme yöntemi BitLocker ilkesiyle eşleşmiyor.

  - BitLocker, işletim sistemi birimini korumak için bir TPM koruyucusu gerektirir, ancak TPM kullanılmaz.

  - BitLocker ilkesi, işletim sistemi birimi için salt TPM koruyucusu gerektirir, ancak TPM koruması kullanılmaz.

  - BitLocker ilkesi, işletim sistemi birimi için TPM + PIN koruması gerektirir, ancak TPM + PIN koruyucusu kullanılmaz.

  - BitLocker ilkesi, işletim sistemi birimi için TPM + başlangıç anahtarı koruması gerektirir, ancak TPM + başlangıç anahtarı koruyucusu kullanılmaz.

  - BitLocker ilkesi, işletim sistemi birimi için TPM + PIN + başlangıç anahtarı koruması gerektirir, ancak TPM + PIN + başlangıç anahtarı koruyucusu kullanılmaz.

  - İşletim sistemi birimi korumasız.

  - Kurtarma anahtarı yedeklemesi başarısız oldu.

  - Sabit bir sürücü korumasız.

  - Sabit sürücünün şifreleme yöntemi BitLocker ilkesiyle eşleşmiyor.

  - Sürücüleri şifrelemek için BitLocker ilkesi kullanıcının yönetici olarak oturum açmasını ya da cihazın Azure AD 'ye katılmasını gerektiriyorsa, AllowStandardUserEncryption ilkesinin 1 olarak ayarlanması gerekir.

  - Windows kurtarma ortamı (WinRE) yapılandırılmadı.

  - TPM, mevcut olmadığı, kayıt defterinde kullanılamaz hale getirilen ya da işletim sistemi çıkarılabilir bir sürücüde olan BitLocker için kullanılamaz.

  - TPM BitLocker için yok.

  - Ağ kullanılabilir değil, kurtarma anahtarı yedeklemesi için gereklidir.

## <a name="export-report-details"></a>Rapor ayrıntılarını dışarı aktar

Şifreleme Raporu bölmesini görüntülerken, rapor ayrıntılarının bir *. csv* dosyası indirmesi oluşturmak Için **dışarı aktar** ' ı seçebilirsiniz. Bu rapor, yönettiğiniz her cihaz için *şifreleme raporu* bölmesi ve *Cihaz şifreleme durumu* ayrıntılarının üst düzey ayrıntılarını içerir.

![Dışarı aktarma ayrıntıları](./media/encryption-monitor/export.png)

Bu rapor, cihaz gruplarıyla ilgili sorunları belirlemek için kullanılabilir. Örneğin, tüm rapor *Dosya kasasının Kullanıcı tarafından zaten etkinleştirilmiş olduğu*MacOS cihazlarının listesini tanımlamak için raporu kullanabilirsiniz. Bu, Intune 'un dosya Kasası Ayarlarını yönetebilmesi için el ile şifresinin çözülmesi gereken cihazları gösterir.

## <a name="filevault-recovery-keys"></a>Filekasası kurtarma anahtarları

Intune, bir macOS cihazını dosya kasası ile ilk kez şifrele, kişisel bir kurtarma anahtarı oluşturulur. Şifreleme sonrasında cihaz, kişisel anahtarı son kullanıcıya tek bir kez görüntüler.

Intune, yönetilen cihazlarda kişisel kurtarma anahtarının bir kopyasını sağlayabilir. Anahtarların Emanet, Intune yöneticilerinin cihazları korumaya yardımcı olmak için anahtarları döndürmesine ve kullanıcıların kayıp veya döndürülmüş bir kişisel kurtarma anahtarını kurtarmasına olanak sağlar.

Intune, kişisel kurtarma anahtarlarını döndürmek ve kurtarmak için birden çok seçeneği destekler. Geçerli kişisel anahtarın kaybolması veya risk altında olması düşünülmek, bir anahtarı döndürmenizi bir neden olur.

> [!IMPORTANT]
> Intune tarafından değil, kullanıcılar tarafından şifrelenen cihazlar Intune tarafından yönetilemez. Bu, Intune 'un bu cihazların kişisel kurtarmasını ve kurtarma anahtarı döndürmesini yönetemeyeceği anlamına gelir. Intune 'un cihaz için dosya kasasını ve kurtarma anahtarlarını yönetebilmesi için, kullanıcının cihazının şifresini çözmesine ve ardından Intune 'un cihazı şifrelemesine izin vermelidir.

### <a name="rotate-recovery-keys"></a>Kurtarma anahtarlarını döndür

- **Otomatik döndürme**: yönetici olarak, kişisel kurtarma anahtarı dönüşü için otomatik olarak yeni kurtarma anahtarı oluşturmak üzere filekasa ayarını yapılandırabilirsiniz. Bir cihaz için yeni bir anahtar oluşturulduğunda, anahtar kullanıcıya gösterilmez. Bunun yerine, kullanıcının anahtarı bir yöneticiden ya da Şirket Portalı uygulamasını kullanarak alması gerekir.

- **El ile döndürme**: yönetici olarak, Intune ile yönettiğiniz ve filekasasıyla şifrelenen bir cihazın bilgilerini görüntüleyebilirsiniz. Daha sonra, şirket cihazları için kurtarma anahtarını el ile döndürmeyi tercih edebilirsiniz. Kişisel cihazlar için kurtarma anahtarlarını döndüremezsiniz.

  Kurtarma anahtarını döndürmek için:

  1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
  
  2. **Tüm cihazlar**>  **cihazları** seçin.
  
  3. Cihaz listesinden, şifrelenen ve anahtarını döndürmek istediğiniz aygıtı seçin. Ardından Izleyici ' nin altında, **kurtarma anahtarları**' nı seçin.
  
  4. Kurtarma anahtarları bölmesinde, **Filekasası kurtarma anahtarını Döndür**' ü seçin.

     Cihazın Intune ile bir sonraki denetlemesi sırasında kişisel anahtar döndürülür. Gerektiğinde yeni anahtar, son kullanıcı tarafından Şirket portalı üzerinden alınabilir.

### <a name="recover-recovery-keys"></a>Kurtarma anahtarlarını kurtar

- **Yönetici**: Yöneticiler, filekasasıyla şifrelenen cihazların kişisel kurtarma anahtarlarını görüntüleyemez.

- **Son Kullanıcı**: son kullanıcılar herhangi bir cihazdan Şirket portalı Web sitesini kullanarak yönetilen cihazlarından herhangi biri için geçerli kişisel kurtarma anahtarını görüntüler. Şirket Portalı uygulamasından kurtarma anahtarlarını görüntüleyemezsiniz.

  Kurtarma anahtarını görüntülemek için:
  
  1. Herhangi bir cihazdan *Intune şirket portalı* Web sitesinde oturum açın.

  2. Portalda **cihazlar** ' a gidin ve filekasasıyla şifrelenen MacOS cihazını seçin.

  3. **Kurtarma anahtarını al**' ı seçin. Geçerli kurtarma anahtarı görüntülenir.

## <a name="bitlocker-recovery-keys"></a>BitLocker kurtarma anahtarları

Intune, Windows 10 cihazlarınızın BitLocker anahtar kimliklerini ve kurtarma anahtarlarını Intune portalından görüntüleyebilmeniz için BitLocker için Azure AD dikey penceresine erişim sağlar. Erişilebilir olması için cihazın, Azure AD 'ye yönelik anahtarları olması gerekir.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihazlar** > **Tüm cihazlar**’ı seçin.

3. Listeden bir cihaz seçin ve ardından *izleyici*altında **kurtarma anahtarları**' nı seçin.
  
   Azure AD 'de anahtarlar kullanılabilir olduğunda aşağıdaki bilgiler kullanılabilir:
   - BitLocker anahtar KIMLIĞI
   - BitLocker kurtarma anahtarı
   - Sürücü türü

   Anahtarlar Azure AD 'de olmadığında, Intune *Bu cihaz Için hiçbir BitLocker anahtarı bulunamadığını*gösterir.

BitLocker için bilgi, [BitLocker yapılandırma hizmeti sağlayıcısı](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP) kullanılarak elde edilir. BitLocker CSP, Windows 10 sürüm 1703 ve üzeri sürümlerde ve Windows 10 Pro sürüm 1809 ve üzeri sürümlerde desteklenir.

## <a name="next-steps"></a>Sonraki adımlar

Bir [cihaz uyumluluk](compliance-policy-create-windows.md) ilkesi oluşturun.
