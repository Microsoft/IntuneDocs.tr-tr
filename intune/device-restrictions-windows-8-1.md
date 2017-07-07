---
title: "Windows 8.1 için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "Windows 8.1 cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da190ddeda62ce3385aab4308595b473c3059ed6
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="windows-81-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 8.1 ve üzeri cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Genel
-   **Tüm yapılandırmaları Windows 10'a uygula** - Bu ilkedeki ayarların Windows 8.1 cihazlarına ek olarak Windows 10 cihazlarına da uygulanmasını etkinleştirir.
-   **Tanılama verisi gönderme** - Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.
-   **Güvenlik duvarı** - Windows Güvenlik Duvarı’nın açık olmasını gerektirir.
-   **Kullanıcı Hesabı Denetimi** - Cihazlarda Kullanıcı Hesap Denetimi’nin (UAC) kullanılmasını zorunlu tutar.
## <a name="password"></a>Parola
-   **Gerekli parola türü** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
-   **En az parola uzunluğu** - Parola için gereken uzunluk alt sınırını (karakter cinsinden) yapılandırır.
-   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Burada belirtilen sayıda oturum açma denemesi başarısız olursa, cihazı temizler.
-   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Kilidini açmak için parola gerekmeden önce cihazın ne kadar süreyle boşta kalacağını belirtir.
-   **Parola süresinin sonu (gün)** - Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.
-   **Önceki parolaların yeniden kullanılmasını engelle** - Kullanıcının önceden kullanılmış parolaları yapılandırıp yapılandıramayacağını belirtir.
-   **Resimli parola ve PIN** - Resimli parola veya PIN kullanımını etkinleştirir. Resimli parola, kullanıcının resimdeki hareketlerle oturum açmasına olanak tanır. PIN, kullanıcıların dört basamaklı bir kodla hızla oturum açmalarına olanak tanır.
-   **Şifreleme** - Cihazdaki dosyaların şifrelenmesini gerektirir.<br>Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](https://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.
Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft hesabı olmalıdır.
Şifrelemenin çalışması için, cihazın Microsoft [InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) donanım sertifika gereksinimlerini karşılaması gerekir.
Cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.     



## <a name="browser"></a>Tarayıcı
-   **Otomatik Doldurma** - Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
-   **Dolandırıcılık uyarıları** - Olası sahte web siteleriyle ilgili uyarıları etkinleştirir veya devre dışı bırakır.
-   **SmartScreen** - Olası sahte web siteleriyle ilgili uyarıları etkinleştirir veya devre dışı bırakır.
-   **JavaScript** - Tarayıcının Java betiği gibi betikleri çalıştırmasına olanak tanır.
-   **Açılır pencereler** - Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.
-   **Kullanıcıyı-izleme üst bilgileri gönderme** - Internet Explorer’da ziyaret edilen sitelere Do Not Track (İzleme) üst bilgisi gönderir.
-   **Eklentiler** - Kullanıcıların Internet Explorer’a eklenti ekleyebilmesine olanak tanır.
-   **İntranet sitesinde tek sözcüklü giriş** - Internet Explorer’ı Bing gibi bir web sitesine yönlendirmek için tek sözcük kullanımına olanak tanır.
-   **İntranet sitesini otomatik algılama** - Internet Explorer'da intranet sitelerinin güvenliği yapılandırmaya yardımcı olur.
-   **İnternet güvenlik düzeyi** - Internet Explorer'da İnternet sitelerinin güvenlik düzeyini ayarlar.
-   **Intranet güvenlik düzeyi** - Internet Explorer'da intranet sitelerinin güvenlik düzeyini ayarlar.
-   **Güvenilen siteler güvenlik düzeyi** - Güvenilen siteler bölgesi için güvenlik düzeyini yapılandırır.
-   **Kısıtlı siteler için yüksek güvenlik** - Yasak siteler bölgesi için güvenlik düzeyini yapılandırır.
-   **Kurumsal mod menü erişimi** - Kullanıcıların Internet Explorer’dan Kuruluş Modu menü seçeneklerine erişmesine olanak tanır.
Bu ayarı seçerseniz, kullanıcıların Kuruluş Modu erişimine açtıkları web sitelerinin gösterildiği bir raporun URL’sini içeren **Günlük raporunun konumunu** belirtebilirsiniz.
-   **Kurumsal mod site listesi konumu** - Etkin olduğunda Kuruluş Modu’nu kullanacak web siteleri listesinin bulunduğu konumu belirtir.
## <a name="cellular"></a>Hücresel
-   **Veri dolaşımı** - Cihaz cep telefonu şebekesindeyken veri dolaşımını etkinleştirir.
## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Çalışma klasörleri URL'si** - Belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar.
-   **Microsoft hesabı olmayan Windows Posta uygulamasına erişim** - Microsoft hesabı olmadan Windows Posta uygulamasına erişimi etkinleştirir.    
