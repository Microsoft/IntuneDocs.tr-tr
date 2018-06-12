---
title: Microsoft Intune - Azure’da Windows Defender ATP kullanma | Microsoft Docs
description: ATP’yi Intune ve Windows Defender Güvenlik Merkezi’nden (ATP portalı) açma, bir ATP yapılandırma profili kullanarak cihaz ekleme, Intune cihaz uyumluluk ilkeleri oluşturma, Azure AD koşullu erişim ilkeleri oluşturma ve cihaz uyumluluğunu izlemeyi içeren Windows Defender Gelişmiş Tehdit Koruması’nı (ATP) uçtan uca bir senaryoda etkinleştirmeyi öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 99d848fb1efea2ea2d557ab8d4f19881705ec991
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744678"
---
# <a name="enable-windows-defender-atp-with-conditional-access-in-intune"></a>Intune’da Windows Defender ATP’yi koşullu erişim ile etkinleştirme

Windows Defender Gelişmiş Tehdit Koruması (ATP) ve Microsoft Intune, bir kuruluşta güvenlik ihlallerini önlemeye ve ihlallerin etkisini sınırlamaya yardımcı olmak için birlikte çalışır.

Bu özellik şunlarda geçerlidir: Windows 10 cihazlar

Örneğin biri, kuruluşunuzdaki bir kullanıcıya kötü amaçlı kod içeren bir Word eki gönderir. Kullanıcı eki açar ve içeriği etkinleştirir. Bir yükseltilmiş ayrıcalık saldırısı başlar ve uzak makinedeki saldırgan, kurbanın cihazında yönetici haklarına sahip olur. Daha sonra saldırgan, kullanıcının diğer cihazlarına uzaktan erişir.

Bu güvenlik ihlali tüm kuruluşu etkileyebilir.

Windows Defender ATP, bu senaryo gibi güvenlik olaylarını çözebilir. Windows Defender Güvenlik Merkezi (ATP konsolu), cihazları “yüksek riskli” olarak raporlar ve şüpheli etkinlik hakkında ayrıntılı bir rapor çıkarır. Verdiğimiz örnekte Windows Defender ATP; cihazın olağan dışı bir kod yürüttüğünü, işlem ayrıcalığı yükseltmesi yaşadığını, kötü amaçlı bir kod eklediğini ve şüpheli bir uzak kabuk verdiğini algılar. Windows Defender ATP daha sonra tehdidi yok etmeniz için size seçenekler sunar.

Intune kullanarak kabul edilebilir risk düzeyi belirleyen bir uyumluluk ilkesi oluşturabilirsiniz. Bir cihaz bu riski aştığında uyumsuz hale gelir. Azure Active Directory (AD) Koşullu Erişim ile birlikte kullanıldığında, kullanıcının şirket kaynaklarına erişimi engellenir.

Bu makale, şunları nasıl yapacağınızı gösterir:

- Intune’da ATP’yi ve ATP’de Intune’u etkinleştirme. Bu görevler, Intune ve Windows Defender ATP arasında hizmetten hizmete bağlantı oluşturur. Bu bağlantı sayesinde Windows Defender ATP, Intune cihazlarınız için makine riskini yazar.
- Intune’da uyumluluk ilkesi oluşturma.
- Cihazlarda, cihaz tehdit düzeyine göre Azure Active Directory (AD) koşullu erişimi etkinleştirin.

## <a name="prerequisites"></a>Önkoşullar

ATP’yi Intune ile birlikte kullanmak için aşağıdakilerin yapılandırılmış ve kullanıma hazır olduğundan emin olun:

- Enterprise Mobility + Security E5 ve Windows E5 (veya Microsoft 365 Kurumsal E5) için lisanslı kiracı
- Azure AD’ye katılmış [Intune tarafından yönetilen](windows-enroll.md) Windows 10 cihazların olduğu Microsoft Intune ortamı
- [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) ve Windows Defender Güvenlik Merkezi (ATP portalı) erişimi

## <a name="enable-windows-defender-atp-in-intune"></a>Intune’da Windows Defender ATP’yi etkinleştirme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz uyumluluğu** > **Windows Defender ATP** > **Windows Defender Güvenlik Merkezi'ni açın** öğesini seçin.

    ![Windows Defender Güvenlik Merkezi’ni açın](./media/atp-device-compliance-open-windows-defender.png)

4. **Windows Defender Güvenlik Merkezi**’nde:
    1. **Ayarlar** > **Gelişmiş özellikler**’i seçin.
    2. **Microsoft Intune bağlantısı** için **Açık** seçeneğini belirleyin:

        ![Intune bağlantısını etkinleştirme](./media/atp-security-center-intune-toggle.png)

    3. **Tercihleri kaydet**’i seçin.

5. Intune’da **Cihaz uyumluluğu** > **Windows Defender ATP**’ye geri gidin. **10.0.15063 ve üstü sürümü Windows cihazları Windows Defender ATP bağlayıcısına bağla** ayarını **Açık** olarak ayarlayın.
6. **Kaydet**’i seçin.

Bu görevi genellikle bir kez yaparsınız. Bu nedenle Intune kaynağınızda ATP zaten etkinse bunu tekrar yapmanız gerekmez.

## <a name="onboard-devices-using-a-configuration-profile"></a>Bir yapılandırma profili kullanarak cihaz ekleme

Windows Defender, cihazlarda yüklü bir ekleme yapılandırma paketi içerir. Bu paket yüklediğinde, [Windows Defender ATP hizmetleri](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) ile iletişime geçerek dosyaları tarar, tehditleri algılar ve riski Windows Defender ATP’ye rapor eder. Intune ile bu yapılandırma paketini kullanan bir yapılandırma profili oluşturabilirsiniz. Daha sonra ilk kez eklediğiniz cihazlara bu profili atarsınız.

Yapılandırma paketini kullanarak bir cihaz ekledikten sonra bunu tekrar yapmanız gerekmez. Bu genellikle tek seferlik bir görevdir.

[Bir grup ilkesi veya System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection) kullanarak da cihaz ekleyebilirsiniz.

Sıradaki adımlarda, Intune kullanarak uygulama ekleme gösterilecektir.

#### <a name="download-configuration-package"></a>Yapılandırma paketi indirme

1. [Windows Defender Güvenlik Merkezi](https://securitycenter.windows.com)’nde **Ayarlar** > **Ekleme**’yi seçin.
2. Aşağıdaki ayarları girin:
  - **İşletim sistemi**: Windows 10
  - **Bir makine ekle** > **Dağıtım yöntemi**: Mobil Cihaz Yönetimi / Microsoft Intune
3. **Paket indir**’i seçin ve **WindowsDefenderATPOnboardingPackage.zip** dosyasını kaydedin. Dosyayı ayıklayın.

Bu zip dosyası, sonraki adımlarda ihtiyaç duyacağınız **WindowsDefenderATP.onboarding** dosyasını içerir.

#### <a name="create-the-atp-configuration-profile"></a>ATP yapılandırma profili oluşturma

Bu profil, önceki adımlarda indirdiğiniz ekleme paketini kullanır.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz Yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzeri**’ni seçin
5. **Profil türü** olarak **Windows Defender ATP (Windows 10 Masaüstü)**’nü seçin.
6. Şu ayarları yapılandırın:

  - **Ekleme Yapılandırma Paketi**: İndirdiğiniz **WindowsDefenderATP.onboarding** dosyasına göz atın ve dosyayı seçin. Bu dosya, cihazların Windows Defender ATP hizmetine rapor vermesini sağlayan bir ayarı etkinleştirir.
  - **Tüm dosyalar için örnek paylaşımı**: Örneklerin toplanmasına ve Windows Defender ATP ile paylaşılmasına izin verir. Örneğin şüpheli bir dosya görürseniz, bunu ayrıntılı analiz için Windows Defender ATP’ye gönderebilirsiniz.
  - **Telemetri raporlama sıklığını artırma**: Yüksek riskli cihazlarda bu ayarı etkinleştirerek cihazların Windows Defender ATP hizmetine daha sık telemetri raporlamasını sağlayın.
  - **Yapılandırma Paketi Çıkarma**: Windows Defender ATP izlemeyi kaldırmak veya “boşaltmak” istiyorsanız [Windows Defender Güvenlik Merkezi](https://securitycenter.windows.com)’nde bir Boşaltma paketi indirebilir ve bunu ekleyebilirsiniz. Aksi takdirde bu özelliği atlayın.

    [System Center Configuration Manager kullanarak Windows 10 makineler ekleme](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection) makalesi, bu Windows Defender ATP ayarları hakkında daha fazla bilgi içermektedir.

7. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin, böylece profil oluşturulur.

## <a name="create-the-compliance-policy"></a>Uyumluluk ilkesini oluşturma
Uyumluluk ilkesi, cihazda kabul edilebilir bir risk düzeyi belirler.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur**’u seçin.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzerini** seçin.
5. **Windows Defender ATP** ayarlarında **Cihazın şu makine risk puanında veya bu değerin altında olmasını gerektirin** seçeneğini dilediğiniz düzeye ayarlayın:

  - **Temiz**: En güvenli düzeydir. Cihazda mevcut bir tehdit olamaz ancak cihaz şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Orta veya yüksek tehdit düzeyindeki cihazlar uyumsuzdur.
  - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu düzey en düşük güvenliğe sahiptir. Yüksek, orta ve düşük tehdit düzeyindeki cihazlar uyumlu olarak değerlendirilir.

6. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).

## <a name="assign-the-policy"></a>İlke atama

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz uyumluluğu** > **İlkeler**’i ve ardından Windows Defender ATP uyumluluk ilkenizi seçin.
3. **Atamalar**’ı seçin.
4. Azure AD gruplarınıza ilkeyi atamak için grupları dahil edin veya hariç tutun.
5. İlkeyi gruplara dağıtmak için **Kaydet**’i seçin. İlkenin hedeflediği kullanıcı cihazlarında uyumluluk denetlenir.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Azure AD koşullu erişim ilkesi oluşturma
Cihaz *uyumsuzsa* koşullu erişim ilkesi, kaynaklara erişimi engeller. Yani bir cihaz, tehdit düzeyini aşarsa SharePoint veya Exchange Online gibi şirket kaynaklarına erişimi engelleyebilirsiniz.

1. [Azure portalı](https://portal.azure.com)’nda **Azure Active Directory** > **Koşullu erişim** > **Yeni ilke**’yi seçin.
2. İlke için bir **Ad** girin ve **Kullanıcılar ve gruplar**’ı seçin. İlke için grupları eklemek üzere Dahil Et veya Hariç Tut seçeneklerini kullanın ve **Bitti**’yi seçin.
3. **Bulut uygulamaları**’nı ve ardından hangi uygulamaların korunacağını seçin. Örneğin **Uygulama seçin**’e tıklayın, **Office 365 SharePoint Online** ve **Office 365 Exchange Online**’ı seçin.

    Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

4. **Koşullar** > **İstemci uygulamaları**’nı seçerek ilkeyi uygulamalara ve tarayıcılara uygulayın. Örneğin **Evet**’i seçin ve ardından **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i etkinleştirin.

    Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

5. Cihaz uyumluluğuna göre koşullu erişim uygulamak için **İzin Ver**’i seçin. Örneğin **Erişim ver** > **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin.

    Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.

6. **İlkeyi etkinleştir**’i ve **Oluştur**’u seçerek değişikliklerinizi kaydedin.

[Koşullu erişim nedir?](conditional-access.md) iyi bir kaynaktır.

## <a name="monitor-device-compliance"></a>Cihaz uyumluluğunu izleme
Ardından Windows Defender ATP uyumluluk ilkesine sahip cihazların durumunu izleyin.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz uyumluluğu** > **İlke uyumluluğu**’nu seçin.
3. Listede Windows Defender ATP ilkenizi bulun ve hangi cihazların uyumlu, hangilerinin uyumsuz olduğuna bakın.

## <a name="more-good-stuff"></a>Daha fazla iyi hizmet
[Windows Defender ATP koşullu erişim](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/conditional-access-windows-defender-advanced-threat-protection)  
[Windows Defender ATP risk panosu](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection)  
[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)  
[Azure AD’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)