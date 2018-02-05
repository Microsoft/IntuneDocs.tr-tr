---
title: "Uygulama bilgilerini ve atamaları izleme"
titlesuffix: Azure portal
description: "Kullanıcılara veya cihazlara uygulama atadıktan sonra, atamanın durumunu izlemenize yardımcı olması için bu bilgileri kullanın."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85ecc9729d7c03cb760c14bda0ca4d6321af548e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, yönettiğiniz uygulamanın özelliklerini ve bunların atama durumunu izleyebilmeniz için çeşitli yollar sağlar.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar** iş yükünde **Yönet** grubunda **Uygulamalar**’ı seçin.
5. Uygulama listesi dikey penceresinde bir uygulama seçin. <*uygulama adı*> **Cihaz yükleme durumu** dikey penceresi görüntülenir.

## <a name="app-overview-blade"></a>Uygulamaya genel bakış dikey penceresi

Ortamınızdaki uygulamanın durumu hakkındaki ayrıntıları gözden geçirmek için <*uygulama adı*> **Cihaz yükleme durumu** dikey penceresini kullanabilirsiniz.

### <a name="essentials"></a>Temel Parçalar

**Temel Parçalar** bölümünde, uygulama hakkında aşağıdaki bilgiler yer alır:

 - **Yayımcı**  
Uygulama yayımcısı.
 - **İşletim sistemi**  
Uygulamanın işletim sistemi (Windows, iOS, Android, vb.)
 - **Oluştur**  
Düzeltmenin oluşturulduğu zaman.
 - **Atanan**  
Uygulama atandıysa **Evet** veya **Hayır**.

### <a name="status"></a>Durum
Her graf, aşağıdaki durum için sayıları gösterir:

 - **Yüklendi**  
Yüklenen uygulamaların sayısı.
 - **Yüklü Değil**  
Yüklenmemiş uygulamaların sayısı.
 - **Yükleme Bekletiliyor**  
Yüklenme sürecinde olan uygulamaların sayısı.
 - **Başarısız**  
Başarısız olan yüklemelerin sayısı.
 - **Bilinmiyor**  
Durumu bilinmeyen uygulamaların sayısı.

### <a name="device-status"></a>Cihaz durumu

Cihaz durumu. Cihazlardaki uygulamanın yükleme durumunu görüntüleyen halka grafik. Cihaz durumu hakkındaki ayrıntı listesini açmak için grafiğe tıklayın. Ayrıntı tablosunda aşağıdaki sütunlar vardır:

 - **Cihaz adı**  
Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılabilir olamaz.
 - **Kullanıcı adı**  
Kullanıcının adı.
 - **Platform**  
Cihazın işletim sistemi (Windows, iOS, Android, vb.)
 - **Sürüm**  
Uygulamanın sürüm numarası. İş kolu uygulamaları için, uygulamanın tam sürüm numarası görüntülenir. Tam sürüm numarası uygulamanın belirli bir yayınını tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin, 2.2(2.2.17560800)
 - **Durum**  
Uygulamanın durumu.
 - **Durum ayrıntıları**  
Durumun ayrıntıları.
 - **Son iade etme**  
Cihazın Intune ile son eşitlendiği tarih.


### <a name="user-status"></a>Kullanıcı durumu

Kullanıcı durumu. Kullanıcılar için uygulamanın yükleme durumunu görüntüleyen halka grafik. Cihaz durumu hakkındaki ayrıntı listesini açmak için grafiğe tıklayın. Ayrıntı tablosunda aşağıdaki sütunlar vardır:
 - **Ad**  
Kullanıcının Azure AD'deki adı.
 - **Kullanıcı adı**  
Kullanıcının benzersiz adı.
 - **Yüklemeler**  
Kullanıcı tarafından kullanılan uygulama yüklemelerinin sayısı.
 - **Hatalar**  
Kullanıcıya göre başarısız yükleme sayısı.
 - **Yüklü değil**  
Kullanıcıya göre yüklenmemiş uygulamaların sayısı.


## <a name="next-steps"></a>Sonraki adımlar

Intune verilerinizle çalışma hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı'nı kullanma](reports-nav-create-intune-reports.md).