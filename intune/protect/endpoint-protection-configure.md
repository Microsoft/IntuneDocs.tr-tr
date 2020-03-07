---
title: Microsoft Intune - Azure’da Endpoint Protection ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da bir macOS veya Windows 10 cihaz profili oluşturduğunuzda Endpoint Protection ayarları oluşturun.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 45cdbfe98bca8f7b0e307ed47ad3f78193e6d04c
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78370105"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Intune’da Endpoint Protection ayarları ekleme

Intune ile, cihazlarda aşağıdakiler de dahil olmak üzere ortak uç nokta koruma güvenlik özelliklerini yönetmek için cihaz yapılandırma profillerini kullanabilirsiniz:

- Güvenlik Duvarı
- BitLocker
- Uygulamalara izin verme ve bunları engelleme
- Microsoft Defender ve şifreleme

Örneğin yalnızca macOS kullanıcılarının Mac App Store’dan uygulama indirmesine izin veren bir Endpoint Protection profili oluşturabilirsiniz. Veya Windows 10 cihazlarda uygulama çalıştırırken Windows SmartScreen’i etkinleştirebilirsiniz.

Bir profil oluşturmadan önce, Intune 'un desteklenen her platform için yöneteceği Endpoint Protection ayarlarını ayrıntılandırın aşağıdaki makalelerini gözden geçirin:

- [macOS ayarları](endpoint-protection-macos.md)
- [Windows 10 ayarları](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection ayarlarını içeren bir cihaz profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. Endpoint Protection profili için bir **Ad** ve **Açıklama** girin.

4. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:

   - **macOS**
   - **Windows 10 ve üzeri**

5. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin.

6. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Bkz.

   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)

7. Geçerli ayarları yapılandırdıktan sonra **Profil oluştur** sayfasında **Oluştur** ' u seçin.

   Profil oluşturulur ve profil listesi sayfasında görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](../configuration/device-profile-assign.md).

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Windows 10 cihazları için özel güvenlik duvarı kuralları ekleme

Microsoft Defender güvenlik duvarını Windows 10 için Endpoint Protection kurallarını içeren bir profilin parçası olarak yapılandırdığınızda güvenlik duvarları için özel kurallar yapılandırabilirsiniz. Özel kurallar, Windows 10 için desteklenen önceden tanımlanmış güvenlik duvarı kuralları kümesini genişletmenizi sağlar.

Özel güvenlik duvarı kuralları içeren profiller için plan yaparken, profillerinizin güvenlik duvarı kurallarını nasıl seçecağınızı etkileyebilecek aşağıdaki bilgileri göz önünde bulundurun:

- Her profil en fazla 150 güvenlik duvarı kuralını destekler. 150 'den fazla kural kullandığınızda, her biri 150 kuralla sınırlı ek profiller oluşturun.

- Her profil için, tek bir kural uygulanamazsa, bu profildeki tüm kurallar başarısız olur ve kurala hiçbiri cihaza uygulanmaz.

- Bir kural uygulanamazsa, profildeki tüm kurallar başarısız olarak bildirilir. Intune hangi bağımsız kuralın başarısız olduğunu tanımlayamıyor.  

Intune 'un yönetebileceği güvenlik duvarı kuralları, Windows [güvenlik duvarı yapılandırma hizmeti sağlayıcısı]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) 'nda (CSP) ayrıntılı olarak açıklanmıştır. Intune 'un desteklediği Windows 10 cihazlarının özel güvenlik duvarı ayarlarının listesini gözden geçirmek için bkz. [özel güvenlik duvarı kuralları](endpoint-protection-windows-10.md#firewall-rules).

### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Uç nokta koruma profiline özel güvenlik duvarı kuralları eklemek için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. *Platform*için **Windows 10 ve üzeri**' i seçin ve ardından *profil türü* için **Endpoint Protection**' ı seçin.

4. Yapılandırma sayfasını açmak için **Microsoft Defender güvenlik duvarı** ' nı seçin ve ardından *güvenlik duvarı kuralları* için **Ekle** ' yi seçerek **kural oluştur** sayfasını açın.

5. Güvenlik duvarı kuralı için ayarları belirtin ve sonra kaydetmek için **Tamam** ' ı seçin. Belgelerde bulunan özel güvenlik duvarı kuralı seçeneklerini gözden geçirmek için bkz. [özel güvenlik duvarı kuralları](endpoint-protection-windows-10.md#firewall-rules).

6. Kuralı kaydettikten sonra, kural listesindeki *Microsoft Defender güvenlik duvarı* sayfasında görünür.

7. Bir kuralı değiştirmek için listeden kuralı seçin, kuralı **Düzenle** sayfasını açın.

8. Bir profilden bir kuralı silmek için, kural için üç nokta **(...)** simgesini seçin ve **Sil**' i seçin.

9. Kuralların görüntülenme sırasını değiştirmek için, kural listesinin en üstündeki *yukarı ok, aşağı ok* simgesini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bir profili gruplara atamak için bkz. [cihaz profillerini atama](../configuration/device-profile-assign.md).
