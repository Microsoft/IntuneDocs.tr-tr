---
title: Microsoft Intune - Azure’da Endpoint Protection ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da bir macOS veya Windows 10 cihaz profili oluşturduğunuzda Endpoint Protection ayarları oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: cbac3627a17fb28f7ec0bf06898038a6c6001ac8
ms.sourcegitcommit: f8bbd9bac2016a77f36461bec260f716e2155b4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65733048"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Intune’da Endpoint Protection ayarları ekleme

Intune ile cihaz yapılandırma profilleri cihazlarda da dahil olmak üzere ortak uç nokta koruma güvenlik özelliklerini yönetmek için kullanabilirsiniz:
- Güvenlik Duvarı 
- BitLocker
- İzin verme ve uygulamaları engelleme  
- Windows Defender ve şifreleme

Örneğin yalnızca macOS kullanıcılarının Mac App Store’dan uygulama indirmesine izin veren bir Endpoint Protection profili oluşturabilirsiniz. Veya Windows 10 cihazlarda uygulama çalıştırırken Windows SmartScreen’i etkinleştirebilirsiniz.

Bir profili oluşturmadan önce desteklenen her platform için Intune endpoint protection ayarları yönetebilir, ayrıntı aşağıdaki makaleleri inceleyin: 
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection ayarlarını içeren bir cihaz profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Endpoint Protection profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
   - **macOS**
   - **Windows 10 ve üzeri**
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Bkz.
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)  

8. Uygun ayarları yapılandırdıktan sonra seçin **Oluştur** üzerinde **profili oluşturma** sayfası.

   Profil oluşturulur ve profil listesi sayfasında görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

## <a name="add-custom-firewall-rules-for-windows-10-devices"></a>Windows 10 cihazlar için özel güvenlik duvarı kuralları ekleme  

Windows 10 için uç nokta koruma kuralları içeren bir profili bir parçası olarak, Windows Defender güvenlik duvarı yapılandırdığınızda, güvenlik duvarları için özel kurallar yapılandırabilirsiniz. Özel kurallar, Windows 10 için desteklenen güvenlik duvarı kuralları önceden tanımlı bir dizi üzerinde genişletin sağlar.  

Özel güvenlik duvarı kuralları ile profilleri için planlama yaparken, güvenlik duvarı kurallarını gruplandırmak için profilinizde nasıl yararlanacağınız etkileyebilecek aşağıdaki bilgileri göz önünde bulundurun:  
- Her bir profil en fazla 150 güvenlik duvarı kurallarını destekler. 150'den fazla kuralları kullandığınızda, ek profilleri, her sınırlı 150 kuralları oluşturun.  
- Her profil tek bir kural uygulamak, tüm kuralları profil işlemi başarısız oldu, başarısız olursa ve kuralların hiçbiri için cihaza uygulanır.  
- Uygulamak bir kural başarısız olduğunda, tüm kuralları profilinde başarısız olarak raporlanır. Intune, hangi bireysel kural başarısız tanımlanamıyor. 

Windows Intune'u yönetmek güvenlik duvarı kuralları ayrıntılandırılmıştır [güvenlik duvarı yapılandırma hizmet sağlayıcısı]( https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) (CSP). Intune'un desteklediği Windows 10 cihazları için özel güvenlik duvarı ayarları listesini gözden geçirmek için bkz: [özel güvenlik duvarı kuralları](endpoint-protection-windows-10.md#custom-firewall-rules).   

#### <a name="to-add-custom-firewall-rules-to-an-endpoint-protection-profile"></a>Özel güvenlik duvarı kuralları için Endpoint protection profili eklemek için  

1. Intune'da Git **cihaz Yapılandırması** > **profilleri** > **profili oluştur**.  

2. İçin *Platform*seçin **Windows 10 ve üzeri**ve ardından *profil türü* seçin **uç nokta koruma**.  

3. Seçin **Windows Defender Güvenlik Duvarı** yapılandırma sayfasını açın ve ardından *güvenlik duvarı kuralları* seçin **Ekle** açmak için **Create Rule**sayfası.  

4. Güvenlik duvarı kuralı kümesi ayarlarını belirtin ve ardından **Tamam** kaydetmek için. Belgelerde kullanılabilir özel güvenlik duvarı kuralı seçeneklerini gözden geçirmek için bkz. [özel güvenlik duvarı kuralları](endpoint-protection-windows-10.md#custom-firewall-rules).  

5. Kural kaydettikten sonra göründüğü *Windows Defender Güvenlik Duvarı* kurallar listesi sayfasında.  

6. Bir kuralı değiştirmek için kural açmak için listeden seçin **kuralını Düzenle** sayfası.  

7. Bir kural bir profilden silmek için üç noktayı seçin **(...)**  kural ve ardından **Sil**.  

8. Hangi kuralları görüntüleme sırasını değiştirmek için seçin *Yukarı Ok Aşağı ok* simgesine kuralının listenin üst kısmındaki.  





## <a name="next-steps"></a>Sonraki adımlar  

Bir profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).
