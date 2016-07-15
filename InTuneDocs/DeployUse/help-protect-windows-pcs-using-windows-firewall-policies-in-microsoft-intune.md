---
title: "Windows bilgisayarlar için güvenlik duvarı ilkeleri | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 9f338efe3ef40da3db40c12d1a18c4122e65dc5d


---

# Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma
Microsoft Intune, Intune istemcisiyle yönettiğiniz Windows bilgisayarlarını, bilgisayarlarda Windows Güvenlik Duvarı ayarlarını yapılandırmanıza olanak tanıyan ilkelerin kullanımı da dahil olmak üzere, çeşitli yollarla güvenli hale getirmenize yardımcı olabilir.

Intune Windows bilgisayarlar istemcisini henüz bilgisayarlarınıza yüklemediyseniz, bkz. [Microsoft Intune ile Windows bilgisayar istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).

Windows bilgisayarlarda Windows Güvenlik Duvarı ilkelerini yapılandırmanıza, dağıtmanıza ve izlemenize yardımcı olması için, aşağıdaki bölümlerde yer alan bilgileri kullanın.

## Windows Güvenlik Duvarı'nı yönetmek için Intune ilkeleri kullanma
Windows Güvenlik Duvarı ilkesi, yönetilen bilgisayarlarda Windows Güvenlik Duvarı'nı denetleyen ayarları oluşturmanıza ve dağıtmanıza olanak tanır. Windows Güvenlik Duvarı için özel durumları yönetemezsiniz ve bu ayarlar üçüncü taraf güvenlik duvarları etkilemez.

> [!NOTE]
> Microsoft Intune ilkesi ve Grup İlkesi, bilgisayarda aynı ayarı yönetecek biçimde yapılandırıldıysa, Grup İlkesi ayarı Microsoft Intune ilkesini geçersiz kılar. Intune ilkeleri ve Grup İlkesi arasındaki çakışmaları önleme hakkında daha fazla bilgi için, bkz. [GPO ve Microsoft Intune ilkesi çakışmalarını çözümleme](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Windows Vista çalıştıran bilgisayarlara Windows Güvenlik Duvarı ayarlarını dağıtmak istiyorsanız, önce bu bilgisayarlarda [Düzeltme KB971800](http://support2.microsoft.com/kb/971800) 'ü yüklemelisiniz.

> [!IMPORTANT]
> Windows Güvenlik Duvarı'nı Intune hizmetini kullanarak yönetmek için, aşağıdaki iki hizmetin yöneteceğiniz bilgisayarlarda etkin olduğundan emin olmanız gerekir:
>
> -   Windows Güvenlik Duvarı
> -   IPsec İlke Aracısı

## Bir Windows Güvenlik Duvarı ilkesini yapılandırma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **İlke** &gt; **İlke Ekle**’yi seçin.

2.  Bir **Windows Güvenlik Duvarı Ayarları** ilkesi yapılandırın ve dağıtın. Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. İlke oluşturma ve dağıtma hakkında daha fazla bilgi için, bkz. [Microsoft Intune bilgisayar istemcisi ile genel Windows bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    Aşağıdaki bölümde, ilkede yapılandırabileceğiniz değerlerin yanı sıra, ilkeyi özelleştirmediğinizde kullanılacak varsayılan değerler listelenmektedir.

Bir Windows Güvenlik Duvarı ilkesi dağıttıktan sonra, bunun durumunu **İlke** çalışma alanının **Tüm İlkeler** sayfasında görüntüleyebilirsiniz.

## Windows Güvenlik Duvarı için ilke ayarları

### Windows Güvenlik Duvarını Açma

Bu ilke ayarları, bir etki alanına (örneğin, çalışma alanı), bir özel ağa (ev ağı gibi) veya güvenilir olmayan, bir ortak ağa (örneğin, bir kafeterya) bağlı yönetilen bilgisayarlarda Windows Güvenlik Duvarı'nı etkinleştirir. Bu ayarların her biri için varsayılan değer **Evet**’tir, bu en güvenli değerdir 



### İzin verilen programlar listesindekiler dahil tüm gelen bağlantıları engelleme

Bu ilke ayarları, Windows Güvenlik Duvarı'nı, yönetilen bilgisayar bir etki alanına (örneğin, çalışma alanı), bir özel (güvenilen) ağa (ev ağı gibi) veya güvenilir olmayan, bir ortak ağa (örneğin, bir kafeterya) bağlı olduğunda, gelen ağ trafiğini engellemek üzere yapılandırır. Bu ayarların her biri için varsayılan değer **Evet**’tir, bu en güvenli değerdir 

> [!IMPORTANT]
> Ortamınızda hizmet paketi yüklü olmayan Windows Vista çalıştıran yönetilen bilgisayarlar varsa, Microsoft Bilgi Bankası'nda [makale 971800](http://go.microsoft.com/fwlink/?LinkId=188405) ile ilişkili güncelleştirmeyi yüklemeniz ya da bu bilgisayarlara dağıtılan ilkelerdeki **Tüm gelen bağlantıları engelle** ilke ayarlarını devre dışı bırakmanız gerekir.

### Windows Güvenlik Duvarı yeni bir programı engellediğinde kullanıcıya bildirme

Bu ilke ayarları, Windows Güvenlik Duvarı'nın, yönetilen bilgisayar bir etki alanına (örneğin, çalışma alanı), bir özel (güvenilen) ağa (ev ağı gibi) veya güvenilir olmayan, bir ortak ağa (örneğin, bir kafeterya) bağlı olduğunda, gelen ağ trafiğini engellediğinde bilgisayar kullanıcısını bilgilendirip bilgilendirmeyeceğini yapılandırır. Bu ayarların her biri için varsayılan değer **Evet**’tir.


### Önceden Tanımlanmış Özel Durumlar

Yukarıdaki temel değerleri yapılandırdıktan sonra, belirli ağ trafiğine yukarıda yapılandırılan değerlere bakılmaksızın güvenlik duvarı üzerinden izin veren özel durumlar yapılandırabilirsiniz. Varsayılan olarak, bu ayarların hiçbiri yapılandırılmaz.

|Ayar adı|Ayrıntılar|
|------------------|--------------------|
|**BranchCache - İçerik Alma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin, dağıtılmış modda birbirlerinden ve barındırılan önbellek modunda barındırılan önbellekten içerik almak için HTTP kullanmasına izin verir. Bu ayar HTTP kullanır.|
|**BranchCache - Barındırılan Önbellek İstemcisi**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache - Barındırılan Önbellek Sunucusu**|BranchCache istemcilerinin diğer istemcilerle iletişim kurmak için barındırılan bir önbellek kullanmasına izin verir. Bu ayar HTTPS kullanır.|
|**BranchCache - Eş Düğüm Bulma**<br>(Windows 7 veya üzeri)|BranchCache istemcilerinin yerel alt ağda içerik kullanılabilirliği araması gerçekleştirmek için WS bulma protokolünü kullanmasına izin verir.|
|**BITS Eşler Arasında Önbelleğe Alma**|İstemcilerin aynı alt ağdaki istemcilerin BITS önbelleğinde depolanan dosyaları bulmak ve paylaşmak için Arka Plan Akıllı Aktarım Hizmeti (BITS) kullanmasına izin verir. Bu ayar WSDAPI ve RPC kullanır.|
|**Bir Ağ Projektörüne Bağlanma**|Kullanıcıların proje sunumları için kablolu veya kablosuz ağlar üzerinden projektörlere bağlanmasına izin verir. Bu ayar WSDAPI kullanır.|
|**Çekirdek Ağ**|İstemcilerin ağ kaynaklarına bağlanmak için IPv4 ve IPv6 kullanmasına izin verir.|
|**Dağıtılmış İşlem Düzenleyicisi**|Yönetilen bilgisayarların veritabanları, ileti kuyrukları ve dosya sistemleri gibi işlem korumalı kaynakları güncelleştiren işlemleri düzenlemesine olanak sağlar.|
|**Dosya ve Yazıcı Paylaşımı**|Kullanıcıların ağ üzerindeki diğer kullanıcılarla yerel dosya ve yazıcıları paylaşmasına izin verir. Bu ayar NetBIOS, LLMNR, SMB ve RPC kullanır.|
|**HomeGroup**<br>(Windows 7 veya üzeri)|Yönetilen bilgisayarların bir Ev Grubu'na katılmasına izin verir.|
|**iSCSI Hizmeti**|Yönetilen bilgisayarların iSCSI sunucularına ve cihazlarına bağlanmasına izin verir.|
|**Anahtar Yönetimi Hizmeti**|Kurumsal ortamlarda bilgisayarların lisans uyumluluğu için sayılmasına izin verir.|
|**Media Center Extenders**|Media Center Extender'larının Windows Media Center çalıştıran bilgisayarlar ile iletişim kurmasına izin verir. Bu ayar SSDP ve qWave kullanır.|
|**Netlogon Hizmeti**|Kullanıcıların ve hizmetlerin kimlik doğrulaması için etki alanı istemcileri ve etki alanı denetleyicisi arasında bir güvenlik kanalı yapılandırır. Bu ayar RPC kullanır.|
|**Ağ Bulma**|Bilgisayarların diğer cihazları bulmasına ve ağ üzerindeki diğer cihazlar tarafından bulunmasına izin verir. Bu ayar, Function Discovery Host ve Publication Services ve SSDP, NetBIOS, LLMNR ve UPnP ağ protokollerini kullanır.|
|**Performans Günlükleri ve Uyarılar**|Performans Günlükleri ve Uyarılar hizmetinin uzaktan yönetilmesine izin verir. Bu ayar RPC kullanır.|
|**Uzaktan Yönetim**|Bilgisayarın uzaktan yönetilmesine izin verir.|
|**Uzaktan Yardım**|Yönetilen bilgisayarların kullanıcılarının ağ üzerindeki diğer kullanıcılardan Uzaktan Yardım istemesine izin verir. Bu ayar SSDP, PNRP, Teredo ve UPnP ağ protokollerini kullanır.|
|**Uzak Masaüstü**|Bilgisayarın Uzak Masaüstü'nü kullanarak diğer bilgisayarlara erişmesine izin verir.|
|**Uzaktan Olay Günlüğü Yönetimi**|İstemci olay günlüklerinin uzaktan görüntülenmesine ve yönetilmesine izin verir. Bu ayar Named Pipes ve RPC kullanır.|
|**Uzaktan Zamanlanmış Görev Yönetimi**|Görev zamanlama hizmetinin uzak yönetilmesine izin verir. Bu ayar RPC kullanır.|
|**Uzaktan Hizmet Yönetimi**|İstemcilerdeki yerel hizmetlerin uzaktan yönetilmesine izin verir. Bu ayar Named Pipes ve RPC kullanır.|
|**Uzaktan Birim Yönetimi**|Uzak yazılım ve donanım disk birimi yönetimine izin verir. Bu ayar RPC kullanır.|
|**Yönlendirme ve Uzaktan Erişim**|Bilgisayarlara gelen VPN ve uzaktan erişim bağlantılarına izin verir.|
|**Güvenli Soket Tünel Protokolü**|Güvenli Yuva Tünel Protokolü (SSTP) kullanılarak yönetilen bilgisayarlara gelen VPN bağlantılarına izin verir. Bu ayar HTTPS kullanır.|
|**SNMP Trap**|Yönetilen bilgisayarların SNMP Yakalama hizmeti trafiği almasına izin verir.|
|**UPnP Framework**|Bilgisayarlardaki UPnP Çerçevesi hizmetini, bilgisayarların UPnP sertifikalı cihazları bulmasına ve kullanmasına olanak sağlayacak biçimde yapılandırır.|
|**Windows İşbirliği Bilgisayar Adı Kayıt Hizmeti**|Bilgisayarların Eş Adı Çözümleme Protokolü'nü kullanarak diğer bilgisayarları bulmasını ve bunlarla iletişim kurmasını sağlar. Bu ayar SSDP ve PNRP kullanır.|
|**Windows Media Player**|Kullanıcıların UDP üzerinden akış medyası almasına olanak sağlar.|
|**Windows Media Player Ağ Paylaşım Hizmeti**|Kullanıcıların bir ağ üzerinden medya paylaşmasına olanak sağlar. Bu ayar SSDP, qWave ve UPnP ağ protokollerini kullanır.|
|**Windows Media Player Ağ Paylaşım Hizmeti (İnternet)**<br>(Windows 7 veya üzeri)|Kullanıcıların İnternet üzerinden ev medyası paylaşmasına izin verir.|
|**Windows Toplantı Alanı**|Kullanıcıların ağ üzerinden işbirliği yaparak belge, program veya masaüstü paylaşmasına izin verir. Bu ayar DFSR ve P2P kullanır.|
|**Windows Eşler Arası İşbirliği Altyapısı**|Bunların bağlanmasına imkan sağlayacak çeşitli eşler arası programlar ve teknolojiler yapılandırır. Bu ayar SSDP ve PNRP kullanır.|
|**Windows Uzaktan Yönetim (Uyumluluk)**|İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management'ı kullanarak yönetilen bilgisayarların uzaktan yönetilmesine izin verir.|
|**Windows Uzaktan Yönetim**<br>(Windows 8 veya üzeri).|İşletim sistemleri ve cihazların uzaktan yönetimi için Web hizmeti tabanlı bir protokol olan WS-Management'ı kullanarak yönetilen bilgisayarların uzaktan yönetilmesine izin verir.|
|**Windows Virtual PC**<br>(Windows 7 veya üzeri)|Sanal makinelerin diğer bilgisayarlarla iletişim kurmasına olanak sağlar.|
|**Taşınabilir Kablosuz Cihazlar**|Medya Aktarım Protokolü'nü (MTP) kullanarak ağ bağlantısı etkin kamera veya medya cihazı verilerinin yönetilen bilgisayarlara aktarılmasına imkan sağlar. Bu ayar SSDP ve UPnP ağ protokollerini kullanır.|

### Ayrıca bkz.
[Windows bilgisayarlarını koruma ilkeleri](policies-to-protect-windows-pcs-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


