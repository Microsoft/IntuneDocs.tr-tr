---
title: Microsoft Intune'da ağ konumuna göre Android cihazlarını bağlama - Azure | Microsoft Docs
description: Android cihazları için Microsoft Intune'da ağ konumlarını oluşturun veya yapılandırın. Cihazları bulundukları ağ konumuna göre uyumsuz olarak işaretleyebilirsiniz. Cihaz ağ konumunun dışına çıkarsa, şirket kaynaklarına erişimi engelleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: edc1a241d327bd98db8ae50187b1e1aed5e00e71
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503561"
---
# <a name="use-locations-network-fence-in-intune"></a>Intune'da Konumları (ağ yalıtımı) kullanma

Cihaz bir konumdan ayrıldığında şirket ağına erişimini engelleyebilirsiniz. Intune'da **Konumlar** özelliği bu işlevselliği sağlar. 

Ağ yalıtımı olarak da bilinen, ağ konumu tabanlı bir uyumluluk ilkesi oluşturabilirsiniz. İlke, cihazların uyumlu olabilmesi için iş ağına bağlı olmasını zorunlu tutar. Bu ilke koşullu erişim ilkeleriyle birlikte kullanılabilir, böylece cihazların *yalnızca* cihaz iş ağına bağlıyken iş kaynaklarına erişimi olur. İş ağına bağlı olmayan cihaz, uyumsuz duruma geçer ve iş kaynaklarına erişimi kaybeder.

Aşağıdaki senaryoyu göz önünde bulundurun:

Üretim tesisinizde bazı çalışanlar Android cihazını kullanıyor. Bir çalışan Android cihazını tesisin dışına çıkarıyor. Yetkisiz erişimi önlemeye yardımcı olmak için şunları yapabilirsiniz:

1. IPv4 aralığıyla **Üretim katı** adlı bir konum oluşturun.
2. Bu cihazların şirket ağınıza bağlı olmasını gerektiren bir uyumluluk ilkesi oluşturun ve bu ilkeyi atayın.
3. Cihaz üretim tesisinin dışına çıkarsa uyumsuz kabul edilir ve şirket kaynaklarına erişimi olmaz.

Ayrıca [uyumsuzluk için eylemler](#configure-the-actions-for-noncompliance) de ekleyebilirsiniz. Cihaz, yeniden şirket içine ve ağ konumuna geldiğinde şirket kaynaklarına yeniden erişim kazanır.

## <a name="prerequisites"></a>Önkoşullar

Konum tabanlı bir uyumluluk ilkesi oluşturmak için:

- Cihazın bağlandığı Ağ Geçidi Sunucusu, DHCP sunucusu ve/veya DNS sunucusu için IPv4 ağ aralıkları olarak bir ağ konumu oluşturun
- Bu konumları kullanan ve cihaz artık ağ konumuna bağlı olmadığında gerçekleştirilecek eylemi tanımlayan uyumluluk ilkesini oluşturun
- Android cihazlar 6.0 ve üzeri, güncelleştirilmiş Şirket Portalı uygulaması ile

## <a name="create-a-location"></a>Konum oluşturma

1. Intune'da **Cihaz uyumluluğu** > **Konumlar** > **Oluştur**'u seçin.

2. Aşağıdaki özellikleri girin:  

   - Gerekli. Konum için **Üretim katı** veya **Bina 44-güvenli** gibi bir **Ad** girin.
   - İsteğe bağlı. CIDR (Sınıfsız Etki Alanları Arası Yönlendirme) gösterimiyle `aaa.bbb.ccc.ddd/n` gibi bir **IPv4 Aralığı** girin.
   - İsteğe bağlı. `aaa.bbb.ccc.ddd` gibi bir **IPv4 Ağ Geçidi** adresi girin.
   - İsteğe bağlı. `aaa.bbb.ccc.ddd` gibi bir **IPv4 DHCP Sunucusu** adresini girin.
   - İsteğe bağlı. **IPv4 DNS Sunucuları** adres listesini girin. Bu ayar **alt küme eşleştirmesi** kullanır. Cihazdaki IPv4 DNS Sunucuları tanımlanan değerlerin alt kümeleriyse, cihaz yalıtımın içinde olarak kabul edilir. Her satıra bir adres girdiğinizden emin olun; örneğin:  
     `aaa.bbb.ccc.ddd`  
     `aaa.bbb.ccc.ddd`
   - İsteğe bağlı. **DNS Sonekleri** listesini girin. Bu ayar **alt küme eşleştirmesi** kullanır. Cihazdaki DNS Sonekleri tanımlanan değerlerin alt kümeleriyse, cihaz yalıtımın içinde olarak kabul edilir. Her satıra tek bir etki alanı adı girdiğinizden emin olun; örneğin:  
     `contoso.com`  
     `contoso.org`

3. Yaptığınız değişiklikleri **kaydedin**.

## <a name="create-the-location-compliance-policy"></a>Konum uyumluluk ilkesini oluşturma

Uyumluluk ilkesini oluşturduğunuzda, **Platform** için **Android**'i seçin. **Konumlar**'da, eklediğiniz ağ konumlarından birini veya birden çoğunu seçin. Bu konumlar, cihazlarınız için oluşturduğunuz ağ yalıtımının parçasıdır.

[Uyumluluk ilkesi temelinde ağ konumu oluşturma](compliance-policy-create-android.md#locations) altında bazı yönergeler sağlanır.

## <a name="configure-the-actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemleri yapılandırma

Uyumluluk ilkesi oluşturulduktan sonra, uyumsuzluğa yönelik varsayılan eylem cihaza uyarlanır. Daha fazla eylem ekleyebilirsiniz. Örneğin, cihaz artık konumlarla uyumlu olmadığında kullanıcıya e-posta gönderen bir eylem ekleyin.

[Uyumsuzluğa yönelik eylemler ekleme](actions-for-noncompliance.md) altında bazı yönergeler sağlanır.

## <a name="company-portal-app"></a>Şirket Portalı uygulaması

Cihaz konumlarınıza bağlandığında, Şirket Portalı uygulamasında uyumlu olarak gösterilir. Cihaz konumlarınızdan birine bağlı olmadığında uyumsuz olarak gösterilir.

## <a name="next-steps"></a>Sonraki adımlar
[Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)  
[Uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)
