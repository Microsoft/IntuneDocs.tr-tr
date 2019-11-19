---
title: Jamf cihazları için cihaz uyumluluk ilkesi
titleSuffix: Microsoft Intune
description: JAMF tarafından yönetilen cihazların güvenliğini sağlamaya yardımcı olmak için Azure Active Directory Koşullu erişimle Microsoft Intune uyumluluk ilkeleri kullanın.
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
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b09b30fd32caace9ed3259350c01548d5e5fae15
ms.sourcegitcommit: 93265c2491058afde7168134075bed77031b9311
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74161598"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Jamf Pro ile yönetilen Mac bilgisayarları üzerinde uyumluluğu zorla

[JAMF Pro 'Yu Intune ile tümleştirdiğinizde](conditional-access-integrate-jamf.md), Kurumsal gereksinimlerinize göre Mac cihazlarınızda uyumluluğu zorlamak Için koşullu erişim ilkelerini kullanabilirsiniz.  Bu makale aşağıdaki görevlerde size yardımcı olur:  

- Koşullu erişim ilkeleri oluşturun.
- JAMF Pro 'Yu, Intune Şirket Portalı uygulamayı JAMF ile yönettiğiniz cihazlara dağıtmak üzere yapılandırın.
- Cihaz kullanıcısı JAMF self servis uygulamasının içinden başlattıkları Şirket Portalı uygulamada oturum açtığında cihazları Azure AD 'ye kaydedecek şekilde yapılandırın. Cihaz kaydı, Azure AD 'de cihazın şirket kaynaklarına erişim için koşullu erişim ilkeleriyle değerlendirilmesini sağlayan bir kimlik oluşturur.  
 
Bu makaledeki yordamlar hem Intune hem de JAMF Pro konsollarına erişim gerektirir.

## <a name="set-up-device-compliance-policies-in-intune"></a>Intune'da cihaz uyumu politikaları oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Uyumluluk ilkeleri** > **cihazları** seçin. Daha önce oluşturulmuş bir ilke kullanıyorsanız, konsolda Bu ilkeyi seçin ve sonra bu yordamın sonraki adımına gidin. Yeni bir ilke oluşturmak için, **Ilke oluştur** ' u seçin ve ardından **MacOS** *platformuyla* bir ilkenin ayrıntılarını belirtin. Kurumsal gereksinimlerinizi karşılamak için *uyumsuzluk Için* *ayarları* ve eylemleri yapılandırın ve ardından ilkeyi kaydetmek için **Oluştur** ' u seçin.

3. İlkelere *genel bakış* bölmesinde **atamalar**' ı seçin. Bu ilkeyi hangi Azure Active Directory (Azure AD) kullanıcılarının ve güvenlik gruplarının alacağını yapılandırmak için kullanılabilir seçenekleri kullanın. Intune ile JAMF tümleştirmesi, cihaz gruplarını hedefleyen Uyumluluk ilkesini desteklemez.

4. **Kaydet**' i seçtiğinizde, ilke kullanıcılara dağıtılır.  

Dağıttığınız ilkeler, atanan kullanıcılar tarafından kullanılan cihazları hedefleyin. Bu cihazlar uyumluluk için değerlendirilir. Uyumlu cihazlar, Azure AD 'de "*cihazın uyumlu olarak Işaretlenmesini gerektir*" ayarı için uyumlu olarak işaretlenir.  

> [!NOTE]
> Intune, uyumlu olmak için tam disk şifrelemesi gerektirir.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Jamf Pro'da macOS için Şirket Portalı uygulamasını dağıtma

Intune Şirket Portalı dağıtmak için JAMF Pro 'da bir ilke oluşturun. Bu ilke, JAMF Self Service 'te kullanılabilmesi için şirket portalı uygulamasını dağıtır. Bu ilkeyi, kullanıcıların Azure AD 'ye cihaz kaydedebilmesi için JAMF Pro 'da ilke oluşturmadan önce oluşturun.  

Aşağıdaki yordamı gerçekleştirmek için bir macOS cihazına ve JAMF Pro portalına erişmeniz gerekir. 

### <a name="to-deploy-the-company-portal-app"></a>Şirket Portalı uygulamasını dağıtmak için  

1. MacOS cihazında, [MacOS için şirket portalı uygulamasının](https://go.microsoft.com/fwlink/?linkid=862280)güncel sürümünü indirin, ancak yüklemeyin. Uygulamanın yalnızca bir kopyasına ihtiyacınız olduğundan, uygulamayı JAMF Pro 'ya yükleyebilirsiniz.  

2. JAMF Pro 'Yu açın ve **bilgisayar yönetimi** > **paketlerine**gidin.

3. MacOS için Şirket Portalı uygulamayla yeni bir paket oluşturun ve ardından **Kaydet**' i seçin.

4. **Bilgisayarlar** > **İlkeler** ve ardından **Yeni**’yi seçin.

5. **Genel** yükünü kullanarak ilkenin ayarlarını yapılandırın. Bu ayarlar şöyle olmalıdır:
   - Tetikleyici: **Kayıt Tamamlandı** ve **Yinelenen İade Etme**'yi seçin
   - Yürütme Sıklığı: **Bilgisayar başına bir kez**'i seçin

6. **Paketler** yükünü seçin ve **Yapılandır**'ı tıklayın.

7. Şirket Portalı uygulamasıyla paketi seçmek için **Ekle**'yi tıklayın.

8. **Eylem** açılır menüsünden **yüklemeyi** seçin.
9. Paket için ayarları yapılandırın.

10. Şirket Portalı uygulamasının hangi bilgisayarlarda yüklenmesi gerektiğini belirtmek için **kapsam** sekmesini seçin. **Kaydet**’i seçin. İlke, seçilen tetikleyicinin bilgisayarda bir sonraki sefer gerçekleştiği sırada ve **genel** yükteki ölçütler karşılandığında kapsamlı cihazlarda çalışır.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Kullanıcıların cihazlarını Azure Active Directory'ye kaydetmesini sağlamak için Jamf Pro'da bir ilke oluşturma  

JAMF Pro Self Service aracılığıyla macOS için [Şirket portalı dağıttıktan](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) sonra, bir kullanıcının CIHAZıNı Azure AD 'ye kaydeden JAMF Pro ilkesini oluşturabilirsiniz. 

Cihaz kaydı, bir cihaz kullanıcısının JAMF Self Service içinden Intune Şirket Portalı uygulamasını el ile seçmesini gerektirir. [Son kullanıcılarınıza](../fundamentals/end-user-educate.md) e-posta, JAMF Pro bildirimleri veya kuruluşunuzun kullandığı başka yöntemler aracılığıyla, cihazlarını kaydetmek için bu eylemi tamamlamaya yönelik olarak iletişim kurmanız önerilir. 

> [!WARNING]
> Şirket Portalı uygulamasını el ile (uygulamalardan veya Indirmeler klasörlerinden) başlatmak cihazı kaydetmez. Cihaz kullanıcısı Şirket Portalı el ile başlatırsa, bir uyarı görür, **' AccountNotOnboarded '** .

### <a name="to-create-the-registration-policy"></a>Kayıt ilkesini oluşturmak için  

1. JAMF Pro 'da **bilgisayarlar** > **ilkeleri**' ne gidin ve ardından cihaz kaydı için yeni bir ilke oluşturun.

2. Tetikleyici ve yürütme sıklığı da dahil olmak üzere **Microsoft Intune Tümleştirmesi** yükünü yapılandırın.

3. **Kapsam** sekmesini seçin ve ardından ilkeyi hedeflenen tüm cihazlara kapsamını belirleyin.

4. İlkeyi JAMF Self Service 'te kullanılabilir hale getirmek için **self servis** sekmesini seçin. İlkeyi **Cihaz Uyumluluğu** kategorisine ekleyin. **Kaydet**'e tıklayın.

## <a name="validate-intune-and-jamf-integration"></a>Intune ve JAMF tümleştirmesini doğrulama  

JAMF Pro ve Microsoft Intune arasındaki iletişimin başarılı olduğunu onaylamak için JAMF Pro konsolunu kullanın. 

- JAMF Pro 'da **ayarlar** > **genel yönetim** > **Microsoft Intune tümleştirme**' e gidin ve ardından **Test**' i seçin.

    Konsol, bağlantının başarılı veya başarısız olduğunu belirten bir ileti görüntüler.  

JAMF Pro konsolundaki bağlantı testi başarısız olursa, JAMF yapılandırmasını gözden geçirin. 


## <a name="removing-a-jamf-managed-device-from-intune"></a>Jamf ile yönetilen bir cihazı Intune’dan kaldırma

JAMF ile yönetilen bir cihazı kaldırmak için Microsoft Endpoint Manager yönetim merkezini açın ve **cihazlar** > **tüm cihazlar**' ı seçin, cihazı seçin ve ardından **Sil**' i seçin.  Toplu cihaz silme işlemi birden çok cihaz seçip **Sil**’e tıklayarak etkinleştirilebilir.

JAMF [Pro belgelerinden JAMF ile yönetilen bir cihazı kaldırma](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information)hakkında bilgi alın. Ek Yardım için [JAMF desteğiyle](https://www.jamf.com/support/) bir destek bileti de oluşturabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Azure Active Directory Koşullu erişim ile çalışmaya başlama](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
