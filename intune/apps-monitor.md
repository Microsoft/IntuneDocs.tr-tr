---
title: Uygulama bilgilerini ve atamaları izleme
titlesuffix: Microsoft Intune
description: Kullanıcılara veya cihazlara uygulama atadıktan sonra, atamanın durumunu izlemenize yardımcı olması için bu bilgileri kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01b7972a6a4dbb641f4c656190324d8572f9010c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, yönettiğiniz uygulamanın özelliklerini ve bunların atama durumunu izleyebilmeniz için çeşitli yollar sağlar.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** grubunda bulunur.
3. **Mobil Uygulamalar**’ı seçin, ardından **Yönet** grubunda **Uygulamalar**’ı seçin.
5. Uygulama listesinde izlemek istediğiniz bir uygulamayı seçin. Cihaz durumu ve kullanıcı durumuna genel bakışı içeren uygulama dikey penceresini göreceksiniz.

## <a name="app-overview-blade"></a>Uygulamaya genel bakış dikey penceresi

Ortamınızdaki bir uygulamanın durumu hakkındaki ayrıntıları gözden geçirmek için bu uygulamanın uygulama dikey penceresini kullanabilirsiniz.

### <a name="essentials"></a>Temel Parçalar
**Temel Parçalar** bölümünde, uygulama hakkında aşağıdaki bilgiler yer alır:

 | **Uygulama Ayrıntıları**            | **Açıklama**                                                      |
|------------------------|------------------------------------------------------------------|
| **Yayımcı**          | Uygulama yayımcısı.                                            |
| **İşletim sistemi**   | Uygulamanın işletim sistemi (Windows, iOS, Android vb.) |
| **Oluşturma Tarihi**             | Düzeltmenin oluşturulduğu tarih ve saat.                         |
| **Atanan**           | Uygulama atandıysa **Evet** veya **Hayır**.                  |

### <a name="device-and-user-status-graphs"></a>Cihaz ve kullanıcı durum grafikleri
Grafikler aşağıdaki durumların sayısını gösterir:

| **Cihaz Durumu**       | **Açıklama**                                       |
|-----------------------|-------------------------------------------------------|
| **Yüklendi**         | Yüklenen uygulamaların sayısı.                         |
| **Yüklü Değil**     | Yüklenmemiş uygulamaların sayısı.                     |
| **Başarısız**            | Başarısız olan yüklemelerin sayısı.                   |
| **Yükleme Bekletiliyor**   | Yüklenme sürecinde olan uygulamaların sayısı. |
| **Uygulanamaz**           | Durumun uygulanamadığı uygulama sayısı.            |

### <a name="device-install-status"></a>Cihaz yükleme durumu

**İzleme** bölümünde **Cihaz yükleme durumu**’nu seçtiğinizde cihaz durum listesi görüntülenir. Ayrıntı tablosunda aşağıdaki sütunlar vardır:

| **Cihaz Sütunu**      | **Açıklama**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Cihaz adı**      | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılamaz.                                                                       |
| **Kullanıcı adı**        | Kullanıcının adı.                                                                                                                                                                                                                                      |
| **Platform**         | Cihazın işletim sistemi (Windows, iOS, Android, vb.)                                                                                                                                                                                           |
| **Sürüm**          | Uygulamanın sürüm numarası. İş kolu uygulamaları için, uygulamanın tam sürüm numarası görüntülenir. Tam sürüm numarası, uygulamanın belirli bir yayınını tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin 2.2(2.2.17560800) |
| **Durum**           | Uygulamanın durumu.                                                                                                                                                                                                                                     |
| **Durum ayrıntıları**   | Durumun ayrıntıları.                                                                                                                                                                                                                                     |
| **Son iade etme**    | Cihazın Intune ile son eşitlendiği tarih.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Kullanıcı yükleme durumu

**İzleme** bölümünde **Kullanıcı yükleme durumu**’nu seçtiğinizde kullanıcı durum listesi görüntülenir. Ayrıntı tablosunda aşağıdaki sütunlar vardır:

| **Kullanıcı Sütunu**     | **Açıklama**                           |
|---------------------|-------------------------------------------|
| **Ad**            | Kullanıcının Azure AD'deki adı.         |
| **Kullanıcı adı**       | Kullanıcının benzersiz adı.              |
| **Yüklemeler**   | Kullanıcı tarafından kullanılan uygulama yüklemelerinin sayısı. |
| **Hatalar**        | Kullanıcıya göre başarısız yükleme sayısı.     |
| **Yüklü değil**   | Kullanıcıya göre yüklenmemiş uygulamaların sayısı. |


## <a name="next-steps"></a>Sonraki adımlar

- Intune verilerinizle çalışma hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı'nı kullanma](reports-nav-create-intune-reports.md).
- Uygulama yapılandırma ilkeleri hakkında bilgi edinmek için bkz. [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).