---
title: Uygulama bilgilerini ve atamalarını izleme
titlesuffix: Microsoft Intune
description: Kullanıcılara veya cihazlara uygulama atadıktan sonra, uygulamanın durumunu izlemenize yardımcı olması için bu bilgileri kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e5471acaa6f2baa8d2de3a169da87d3799239887
ms.sourcegitcommit: d38ca1bf44e17211097aea481e00b6c1e87effae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58514489"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, yönettiğiniz uygulamanın özelliklerini izlemeniz ve uygulama atama durumunu yönetmeniz için birkaç yol sağlar.

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** menüsünde **İstemci uygulamaları**’nı seçin.
4. Menünün **Yönet** bölümünde **Uygulamalar**’ı seçin.
5. Uygulama listesinde, izlenecek uygulamayı seçin. Cihaz durumuna ve kullanıcı durumuna genel bakışı içeren uygulama bölmesini göreceksiniz.

> [!NOTE]
> Olarak dağıtılan android Store uygulamaları **kullanılabilir** ve Android LOB uygulamaları olarak dağıtılmış **kayıtlı veya Kayıtsız kullanılabilir** yükleme durumunu bildirmeyen.

## <a name="app-overview-pane"></a>Uygulamaya genel bakış bölmesi

Uygulama bölmesinde, ortamınızdaki bir uygulamanın durumu hakkındaki ayrıntıları gözden geçirebilirsiniz.

### <a name="essentials"></a>Essentials
**Temel Parçalar** bölümünde, uygulama hakkında aşağıdaki bilgiler yer alır:

 | **Uygulama ayrıntıları**            | **Açıklama**                                                      |
|------------------------|------------------------------------------------------------------|
| **Yayımcı**          | Uygulamanın yayımcısı.                                            |
| **İşletim Sistemi**   | Uygulamanın işletim sistemi (Windows, iOS, Android, vb.). |
| **Oluşturma Tarihi**             | Düzeltmenin oluşturulduğu tarih ve saat. <b>**Not**: Bu tarih değeri, bir BT yöneticisi uygulama meta verileri, uygulama kategorisi veya uygulama açıklaması değiştirme gibi değiştiğinde güncelleştirilir.                        |
| **Atanan**           | Uygulamanın atanıp atanmadığı (**Evet** veya **Hayır**).                  |

### <a name="device-and-user-status-graphs"></a>Cihaz ve kullanıcı durum grafikleri
Grafikler aşağıdaki durumlar için uygulamaların sayısını gösterir:

| **Cihaz durumu**       | **Açıklama**                                       |
|-----------------------|-------------------------------------------------------|
| **Yüklendi**         | Yüklenen uygulamaların sayısı.                         |
| **Yüklü Değil**     | Yüklenmemiş uygulamaların sayısı.                     |
| **Başarısız**            | Başarısız olan yüklemelerin sayısı.                   |
| **Yükleme Bekletiliyor**   | Yüklenme sürecinde olan uygulamaların sayısı. |
| **Uygulanamaz**           | Durumun uygulanamadığı uygulamaların sayısı.            |

> [!NOTE]
> Bulunan uygulamaların sayısı uygulama yükleme durumu sayısıyla eşleşmeyebilir. Tutarsızlıkların olası nedenleri:
>    - Yüklü yönetilen uygulamada bir hedefleme değişikliği, durum dikey penceresindeki yükleme sayısının azalmasına neden olabilir ama algılanan uygulamalarda bildirilmeye devam eder.
>    - Kiracıda aynı uygulamanın birden çok örneğinin hedeflenmesi, kullanıcı veya cihazların olası örtüşmesi nedeniyle farklı sayım sonuçları verebilir. Uygulamanın her örneği örtüşen kullanıcıları sayar ama bulunan uygulamaların yinelenen sayımları ortaya çıkar.
>    - Bulunan uygulamalarla uygulama durumu farklı zaman çerçevelerinde toplanır ve bu da uygulama sayılarında tutarsızlığa neden olabilir.
> 
> Ayrıca, Android uygulamaları olarak dağıtılan unutmayın **kayıtlı veya Kayıtsız kullanılabilir** yalnızca kayıtlı cihazlar için uygulama yükleme durumu raporu. Uygulama yükleme durumu, Intune'a kayıtlı olmayan cihazlar için kullanılabilir değil.

### <a name="device-install-status"></a>Cihaz yükleme durumu

Menünün **İzleme** bölümünde **Cihaz yükleme durumu**’nu seçtiğinizde cihaz durum listesi gösterilir. Ayrıntı tablosunda aşağıdaki sütunlar vardır:

| **Cihaz sütunu**      | **Açıklama**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Cihaz adı**      | Cihazı adlandırmaya izin veren platformlarda cihazın adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik başka hiçbir cihazda kullanılamaz.                                                                       |
| **Kullanıcı adı**        | Kullanıcının adı.                                                                                                                                                                                                                                      |
| **Platform**         | Cihazın işletim sistemi (Windows, iOS, Android, vb.).                                                                                                                                                                                           |
| **Sürüm**          | Uygulamanın sürüm numarası. İş kolu (LOB) uygulamaları için uygulamanın tam sürüm numarası gösterilir. Tam sürüm numarası uygulamanın belirli bir yayınını tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin, 2.2(2.2.17560800). Store uygulamaları için hiçbir sürümleri gösterilir. |
| **Durumu**           | Uygulamanın durumu.                                                                                                                                                                                                                                     |
| **Durum ayrıntıları**   | Durumun ayrıntıları.                                                                                                                                                                                                                                     |
| **Son iade etme**    | Cihazın Intune ile son eşitlenme tarihi.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Kullanıcı yükleme durumu

Menünün **İzleme** bölümünde **Kullanıcı yükleme durumu**’nu seçtiğinizde kullanıcı durum listesi gösterilir. Ayrıntı tablosunda aşağıdaki sütunlar vardır:

| **Kullanıcı sütunu**     | **Açıklama**                           |
|---------------------|-------------------------------------------|
| **Ad**            | Kullanıcının Azure Active Directory'deki adı.         |
| **Kullanıcı adı**       | Kullanıcının benzersiz adı.              |
| **Yüklemeler**   | Kullanıcı tarafından yüklenen uygulamaların sayısı. |
| **Hatalar**        | Kullanıcı için başarısız olan uygulama yüklemelerinin sayısı.     |
| **Yüklü değil**   | Kullanıcı tarafından yüklenmeyen uygulamaların sayısı. |


## <a name="next-steps"></a>Sonraki adımlar

- Intune verilerinizle çalışma hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı'nı kullanma](reports-nav-create-intune-reports.md).
- Uygulama yapılandırma ilkeleri hakkında bilgi edinmek için bkz. [Intune için uygulama yapılandırma ilkeleri](app-configuration-policies-overview.md).
