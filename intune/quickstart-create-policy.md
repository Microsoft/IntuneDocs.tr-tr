---
title: 'Hızlı Başlangıç: Windows 10 cihazları için cihaz uyumluluk ilkesi ekleme'
description: Bu hızlı başlangıcı şirket verilerini korumaya ve son kullanıcıların şirket kaynaklarına erişirken kullandıkları cihazları yönetmeye yardımcı olması için kullanın. Daha sonra ilkeleri gruplara atayın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73e1e0a27d128d567a924e6f2b343026b11f1a44
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581787"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Hızlı Başlangıç: Windows 10 cihazları için cihaz uyumluluk ilkesi ekleme
Windows için Intune cihaz uyumluluk ilkesi, Windows cihazlarının uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar. Bu ilkeleri şirket kaynaklarına erişime izin vermek veya bunu engellemek için [koşullu erişim](https://docs.microsoft.com/intune/conditional-access) ile kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz.

Bu hızlı başlangıçta bir Windows 10 cihazı için bir cihaz uyumluluk ilkesi oluşturacak ve bu ilkeye bir cihaz grubu atayacaksınız.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar
- Bu hızlı başlangıcı tamamlamak için önce [bir kullanıcı oluşturun](quickstart-create-user.md) ve [bir grup oluşturun](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Intune'da oturum açma
[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma
1. **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**'u seçin.
2. **Ad** için **Windows 10 uyumluluğu**, **Açıklama** için **Windows 10 için örnek uyumluluk ilkesi** girin.
3. **Platform** olarak **Windows 10 ve üzeri**'ni seçin.
4. **Ayarlar**’da **Sistem Güvenliği**’ni seçin, sonra **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli** olarak belirtin. İlkenizi ayarlamayı tamamladığınızda **Tamam**’ı seçin.
   ![Uyumluluk ilkesi](/intune/media/quickstart-create-policy/compliance-policy.png)
5. **Windows 10 uyumluluk ilkesi** bölmesini kapatın. 
6. **İlke oluştur** bölmesinde **Oluştur**'u seçin. Bu adım, ilkeyi oluşturur ve ilkenizi **Cihaz uyumluluğu** > **İlkeler**’de listeler.
7. Yeni ilkenizi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
8. Mevcut Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**'ı seçin. **Contoso Testçileri**'ni ve ilketi gruptaki kullanıcılara dağıtmak için **Kaydet**'i seçin. [Grup oluşturun](quickstart-create-group.md)'da bu grubu oluşturmadıysanız, tercih ettiğiniz grubu kullanın. 

## <a name="clean-up-resources"></a>Kaynakları temizleme
Artık gerekli olmadığında, ilkeyi silin. Bunu yapmak için **Windows 10 uyumluluğu** ilkesini seçin ve **Sil**'e tıklayın. 

## <a name="next-steps"></a>Sonraki adımlar
Bu hızlı başlangıçta basit bir cihaz uyumluluk ilkesi oluşturdunuz ve atadınız. İlkeyi alacak bir Windows 10 cihazı kaydetmek için otomatik kaydı kurmak üzere hızlı başlangıca geçin. 
 
> [!div class="nextstepaction"]
> [Intune'da otomatik kayıt kurma](quickstart-setup-auto-enrollment.md)