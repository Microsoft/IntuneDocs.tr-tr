---
title: "Intune ağ bant genişliğini kullanma | Microsoft Intune"
description: "Intune ağ bant genişliği kullanımı"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: 6534eb7bbff2fba39e1dfa9be4ad01196156cc15


---

# Intune ağ bant genişliğini kullanma

[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]’u ayarlamadan önce bu konuyu ve [Microsoft Intune’u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md) başlığı altında listelenen diğer gereksinimleri gözden geçirin.

[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] istemcilerinin ağ trafiğini planlamak için aşağıdaki bölümlerde yer alan bilgileri kullanın.

## Ortalama ağ trafiği
Aşağıdaki tabloda her istemci için ağ üzerinden geçen ortak içeriğin yaklaşık boyutu ve sıklığı listelenmiştir.

> [!NOTE]
> Bilgisayarların ve mobil cihazların gerekli güncelleştirmeleri ve içerikleri [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetinden almasını sağlamak için bunların İnternet'e düzenli aralıklarla bağlanması gerekir. Güncelleştirmeleri veya içeriği almak için geçen süre farklılık gösterir, ancak her gün en az 1 saat boyunca kesintisiz olarak İnternet'e bağlı kalmaları gerekir.

|İçerik türü|Yaklaşık boyut|Sıklık ve ayrıntılar|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemci yüklemesi<br /><br />**Aşağıdaki gereksinimler [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemci yüklemesine ek niteliğindedir**|125 MB|**Bir kez**<br /><br />İstemcinin boyutu, istemci bilgisayarın işletim sistemine bağlı olarak değişir.|
|İstemci kayıt paketi|15 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Endpoint Protection aracısı|65 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Operations Manager aracısı|11 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|İlke aracısı|3 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Microsoft Easy Assist aracısı üzerinden Uzak Yardım|6 MB|**Bir kez**<br /><br />Bu içerik türü için güncelleştirmeler olduğunda ek indirmeler yapılabilir.|
|Günlük istemci işlemleri|6 MB|**Günlük**<br /><br />[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemcisi güncelleştirmeleri ve ilkeleri denetlemek ve istemcinin durumunu hizmete raporlamak üzere [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetiyle düzenli olarak iletişim kurar.|
|Endpoint Protection kötü amaçlı yazılım tanımı güncelleştirmeleri|Değişir<br /><br />Genellikle 40 KB ile 2 MB arasında|**Günlük**<br /><br />Günde en fazla üç kez.|
|Endpoint Protection altyapı güncelleştirmesi|5 MB|**Aylık**|
|Yazılım güncelleştirmeleri|Değişir<br /><br />Boyut, dağıttığınız güncelleştirmelere bağlıdır.|**Aylık**<br /><br />Genellikle, yazılım güncelleştirmeleri her ayın ikinci Salı günü yayınlanır.<br /><br />Yeni kaydedilen veya dağıtılan bir bilgisayar, daha önce yayınlanmış güncelleştirmelerinin tamamını indirirken daha fazla ağ bant genişliği kullanabilir.|
|Hizmet paketleri|Değişir<br /><br />Boyut, dağıttığınız her bir hizmet paketi için değişir.|**Değişir**<br /><br />Hizmet paketlerini ne zaman dağıttığınızda bağlıdır.|
|Yazılım dağıtımı|Değişir<br /><br />Boyut, dağıttığınız yazılıma bağlıdır.|**Değişir**<br /><br />Yazılımı ne zaman dağıttığınızda bağlıdır.|

## Ağ bant genişliği kullanımını azaltmanın yolları
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemcilerinin ağ bant genişliği kullanımını azaltmak için aşağıdaki yöntemlerden birini veya daha fazlasını kullanabilirsiniz.

### İçerik isteklerini önbelleğe almak için proxy sunucusu kullanma
Yinelenen indirmeleri ve İnternet'ten içerik isteyen istemcilerin ağ bant genişliği kullanımını azaltmak için içeriği önbelleğe alan bir proxy sunucu kullanabilirsiniz.

Önbelleğe alan proxy sunucusu, ağınızdaki istemci bilgisayarlardan içerik ister, İnternet'ten içerik alır ve ardından her iki HTTP yanıtını ve ikili indirmelerini önbelleğe alabilir. Sunucu, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemci bilgisayarlarından gelen sonraki istekleri yanıtlamak için önbelleğe alınan bilgileri kullanır.

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemcileri için içerikleri önbelleğe alan bir proxy sunucunun kullandığı genel ayarlar aşağıda verilmiştir.

|Ayar|Önerilen değer|Ayrıntılar|
|-----------|---------------------|-----------|
|Önbellek boyutu|5 GB ila 30 GB|Bu değer, ağınızdaki istemci bilgisayarların sayısına ve kullandığınız yapılandırmalara bağlı olarak değişir. Dosyaların çok kısa sürede silinmesini önlemek için ortamınıza yönelik önbellek boyutunu ayarlayın.|
|Tek önbellek dosyası boyutu|950 MB|Bu ayar, tüm önbelleğe alan proxy sunucularında kullanılamayabilir.|
|Önbelleğe alınacak nesne türleri|HTTP<br /><br />HTTPS<br /><br />BİT|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] paketleri HTTP üzerinden Arka Plan Akıllı Aktarım Hizmeti (BITS) indirmesi tarafından alınan CAB dosyalarıdır.|
Önbelleğe içerik almak için proxy sunucu kullanma hakkında bilgi için proxy sunucunuzun çözümünü içeren belgelere bakın.

### Bilgisayarlarda Arka Plan Akıllı Aktarım Hizmeti'ni kullanma
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] , yapılandırma yaptığınız saatlerde kullanılan ağ bant genişliğini azaltmak üzere bir Windows bilgisayarda Arka Plan Akıllı Aktarım Hizmeti'nin (BITS) kullanılmasını destekler. BITS ilkesini [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Aracısı ilkesinin **Ağ bant genişliği** sayfasında yapılandırabilirsiniz.

BITS ve Windows bilgisayarlar hakkında daha fazla bilgi için TechNet Kitaplığında [Arka Plan Akıllı Aktarım Hizmeti](http://technet.microsoft.com/library/bb968799.aspx) konusuna bakın.

### Bilgisayarlarda BranchCache kullanma
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemcileri geniş alan ağı (WAN) trafiğini azaltmak için BranchCache kullanabilir. İstemci olarak desteklenen aşağıdaki işletim sistemleri de BranchCache özelliğini destekler:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

BranchCache özelliğini kullanmak için istemci bilgisayarda BranchCache etkin olmalı ve ardından **dağıtılmış önbellek modu** için yapılandırılmalıdır.

BranchCache ve dağıtılmış önbellek modu, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] istemcisi yüklü olduğunda bilgisayarda varsayılan olarak etkinleştirilir. Ancak, istemci BranchCache özelliğini devre dışı bırakan Grup İlkesine zaten sahipse, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] bu ilkeyi geçersiz kılmaz ve BranchCache söz konusu bilgisayarda devre dışı kalır.

BranchCache kullanıyorsanız, BranchCache özelliğini veya Güvenlik Duvarı özel durumlarını devre dışı bırakan ilkeyi dağıtmadıklarından emin olmak üzere kuruluşunuzda Grup İlkesini ve [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] Güvenlik Duvarı ilkesini yöneten diğer yöneticilerle iletişim kurmanız gerekir. BranchCache hakkında daha fazla bilgi için bkz. [BranchCache Özelliğine Genel Bakış](http://technet.microsoft.com/library/hh831696.aspx).

### Ayrıca bkz.
[Microsoft Intune'u başlatmadan önce bilinmesi gerekenler](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


