---
title: REST istemcisi ile Veri Ambarı API’sinden veri alma
titlesuffix: Microsoft Intune
description: Bir RESTful API’si kullanarak Intune Veri Ambarı’ndan veri alın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: e5040626a27f50fae4df2ec2472d167269a282e4
ms.sourcegitcommit: 8019bdd8117806c6a3a73a8c6d40af1a3def6d90
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53247280"
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>REST istemcisi ile Intune Veri Ambarı API’sinden veri alma

Intune Veri Ambarı veri modeline, RESTful uç noktaları yoluyla erişebilirsiniz. Verilerinize erişim kazanmak için istemcinizin OAuth 2.0 kullanarak Microsoft Azure Active Directory’de (Azure AD) yetkilendirilmesi gerekir. Erişime izin vermek için önce Azure’da yerel bir uygulama ayarlayın ve Microsoft Intune API’sine izinler verin. Yerel istemciniz yetkilendirilir ve yerel uygulama aracılığıyla Veri Ambarı uç noktalarıyla iletişim kurabilir.

Veri Ambarı API’sinden veri almak üzere istemci ayarlama adımları şunları gerektirir:

1. Azure’da yerel uygulama olarak bir istemci uygulaması oluşturma
3. İstemci uygulamasına Microsoft Intune API erişimi verme
3. Verileri almak için yerel bir REST istemcisi oluşturma

REST istemcisi ile API’yi yetkilendirme ve buna erişmeyi öğrenmek için aşağıdaki adımları izleyin. Önce Postman kullanarak genel bir REST istemcisi kullanacaksınız. Postman, REST istemcilerinde sorun gidererek ve bu istemcileri geliştirerek istemcilerin API’lerle çalışmasını sağlayan yaygın olarak kullanılan bir araçtır. Postman hakkında daha fazla bilgi için [Postman](https://www.getpostman.com) sitesine bakın. Daha sonra bir C# kod örneğine bakabilirsiniz. Örnek, bir istemci yetkilendirmesi ve API’den verileri almak için bir örnek sağlar.

## <a name="create-a-client-app-as-a-native-app-in-azure"></a>Azure’da yerel uygulama olarak bir istemci uygulaması oluşturma

Azure’da yerel bir uygulama oluşturun. Bu yerel uygulama, istemci uygulamadır. Yerel makinenizde çalışan istemci, yerel istemci kimlik bilgileri istediğinde Intune Veri Ambarı API’sine başvurur.

1. Kiracınız için Azure portalında oturum açın. **Uygulama kayıtları** bölmesini açmak için **Azure Active Directory** > **Uygulama Kayıtları**’nı seçin.
2. **Yeni uygulama kaydı**’nı seçin.
3. Uygulama ayrıntılarını yazın.
    1.  **Ad** kısmına, Intune Veri Ambarı İstemcisi gibi kolay bir ad yazın.
    2.  **Uygulama türü** için **Yerel**’i seçin.
    3.  **Oturum açma URL’si** için bir URL girin. Oturum açma URL’si belirli bir senaryoya bağlıdır ancak Postman kullanmayı planlıyorsanız `https://www.getpostman.com/oauth2/callback` yazın. Azure AD’de kimlik doğrularken istemci kimlik doğrulaması adımı için geri aramayı kullanacaksınız.
4.  **Oluştur**’u seçin.

     ![Intune Veri Ambarı API’si](./media/reports-get_rest_data_client_overview.png)

5. Bu uygulamanın **Uygulama kimliğini** not edin. Bu kimliği sonraki bölümde kullanacaksınız.

## <a name="grant-the-client-app-access-to-the-microsoft-intune-api"></a>İstemci uygulamasına Microsoft Intune API erişimi verme

Artık Azure’da tanımlanan bir uygulamanız var. Yerel uygulamadan Microsoft Intune API’sine erişim verin.

1.  Yerel uygulamaya tıklayın. Uygulamanızın adı **Intune Veri Ambarı İstemcisi** benzeri bir ada sahip olmalıdır.
2.  **Ayarlar** bölmesinde **Gerekli izinler**’i seçin
3.  **Gerekli izinler** bölmesinde **Ekle**’yi seçin.
4.  **Bir API Seç**’e tıklayın.
5.  Web uygulaması adını aratın. Bu uygulamanın adı **Microsoft Intune API’sidir**.
6.  Listeden uygulamaya tıklayın.
7.  Seçin **seçin**.
8.  **Microsoft Intune’dan veri ambarı bilgileri almak** için **Temsilcili İzinler**’e tıklayın.

    ![Erişimi etkinleştirme - Microsot Intune API'si](./media/reports-get_rest_data_client_access.png)

9.  Seçin **seçin**.
10.  **Done** (Bitti) öğesini seçin.
11.  İsteğe bağlı olarak Gerekli izinler bölmesinde **İzin Ver**’i seçin. Böylece geçerli dizindeki tüm hesaplara erişim verirsiniz. Bu, kiracıdaki her kullanıcı için bir onay iletişim kutusu oluşturmayı önler. Daha fazla bilgi için bkz. [Uygulamaları Azure Active Directory ile tümleştirme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
12.  **Evet**’i seçin.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Microsoft Intune API’sinden Postman ile veri alma

Postman gibi genel bir REST istemcisi kullanarak Intune Veri Ambarı API’siyle çalışabilirsiniz. Postman, API’nin özelliklerine ve altındaki OData veri modeline öngörü sağlayabilir ve API kaynaklarıyla olan bağlantınızda sorun giderebilir. Bu bölümde, yerel istemciniz için Auth2.0 belirteci oluşturma hakkında bilgi bulabilirsiniz. İstemcinin, Azure AD’de kimlik doğrulaması ve API kaynaklarına erişmesi için belirtece ihtiyacı vardır.

### <a name="information-you-will-need-to-make-the-call"></a>Aramayı yapmanız için gereken bilgiler

Postman kullanarak REST araması yapmak için aşağıdaki bilgilere ihtiyacınız vardır:

| Öznitelik        | Açıklama                                                                                                                                                                          | Örnek                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Geri Çağırma URL’si     | Uygulama ayarları sayfasında bunu, geri arama URL’si olarak ayarlayın.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Belirteç Adı       | Kimlik bilgilerini Azure uygulamasına geçirmek için kullanılan dize. İşlem, belirtecinizi oluşturur ve böylece Veri Ambarı API’sine arama yapabilirsiniz.                          | Taşıyıcı                                                                                        |
| Kimlik Doğrulama URL’si         | Bu, kimlik doğrulama için kullanılan URL’dir. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/ |
| Erişim Belirteci URL’si | Bu, belirteci vermek için kullanılan URL’dir.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| İstemci Kimliği        | Bu kimliği, Azure’da yerel uygulamayı oluştururken oluşturup not etmiştiniz.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Kapsam (İsteğe Bağlı) | Boş                                                                                                                                                                               | Bu alanı boş bırakabilirsiniz.                                                                     |
| Veriliş Türü       | Belirteç bir yetkilendirme kodudur.                                                                                                                                                  | Yetkilendirme kodu                                                                            |

### <a name="odata-endpoint"></a>OData uç noktası

Uç nokta da gerekir. Veri Ambarı uç noktanızı almak için özel akış URL’si gereklidir. OData uç noktasını Veri Ambarı bölmesinden alabilirsiniz.

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Diğer görevler** altında bulunan **Intune Veri Ambarı’nı Ayarlama**’yı seçin.
4. **Üçüncü taraf raporlama hizmetleri kullan** altında özel akış URL’sini kopyalayın. Bu, şuna benzer olmalıdır: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`

Uç nokta şu biçimdedir: `https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`.

Örneğin **tarihler** varlığı şuna benzerdir: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`

Daha fazla bilgi için bkz. [Intune Veri Ambarı API’si uç noktası](reports-api-url.md).

### <a name="make-the-rest-call"></a>REST araması yapma

Postman için yeni bir erişim belirteci almak üzere Azure AD yetkilendirme URL’sini, İstemci kimliğinizi ve Gizli Anahtarı eklemeniz gerekir. Postman, kimlik bilgilerinizi gireceğiniz yetkilendirme sayfasını yükleyecektir.

#### <a name="add-the-information-used-to-request-the-token"></a>Belirteç istemek için gereken bilgileri ekleme

1.  Daha önce yüklemediyseniz Postman’i indirin. Postman’i indirmek için bkz. [www.getpostman](https://www.getpostman.com).
2.  Postman’i açın. **AL** HTTP işlemini seçin.
3.  Uç nokta URL’sini adrese yapıştırın. Bu, aşağıdakine benzer olmalıdır:  

    `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  **Yetkilendirme** sekmesini seçin ve **Tür** listesinden **OAuth 2.0**’ı seçin.
5.  Seçin **yeni erişim belirteci alın**.
6.  Azure’da uygulamanıza Geri Arama URL’si eklediğinizi doğrulayın. Geri Çağırma URL’si şudur: `https://www.getpostman.com/oauth2/callback`.
7.  **Belirteç Adı** için Taşıyıcıyı yazın.
8.  **Kimlik Doğrulama URL’sini** ekleyin. Bu, aşağıdakine benzer olmalıdır:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/`
9.  **Erişim Belirteci URL’sini** ekleyin. Bu, aşağıdakine benzer olmalıdır:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Azure’da oluşturup `Intune Data Warehouse Client` olarak adlandırdığınız yerel uygulamanın **İstemci kimliğini** ekleyin. Bu, aşağıdakine benzer olmalıdır:  

     `88C8527B-59CB-4679-A9C8-324941748BB4`

11. **Yetkilendirme Kodu**’nu ve Erişim belirtecini yerel olarak iste’yi seçin.

12. **Belirteç İste**’ye tıklayın.

    ![Belirteç için bilgiler](./media/reports-postman_getnewtoken.png)

13. Active AD yetkilendirme sayfasında kimlik bilgilerinizi girin. Postman’deki belirteçler listesinde artık `Bearer` adlı belirteç de yer alır.
14. **Belirteç Kullan**’a tıklayın. Üst bilgiler listesi, yeni Yetkilendirme anahtar değeri ve `Bearer <your-authorization-token>` değerini barındırır.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Postman kullanarak aramayı uç noktaya gönderme

1.  **Gönder**’i seçin.
2.  Dönüş verileri Postman yanıt gövdesi içinde görüntülenir.

    ![Postman 200OK](./media/reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Intune Veri Ambarı API’sinden veri almak için bir REST istemcisi (C#) oluşturma

Aşağıdaki örnek, bir basit REST istemcisi içerir. Kod, .Net kitaplığından **httpClient** sınıfını kullanır. İstemci, Azure AD kimlik bilgilerini aldıktan sonra Veri ambarı API’sinden tarihler varlığını almak için bir GET REST araması oluşturur.

> [!Note]  
> Aşağıdaki kod [örneğine GitHub’dan](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs) ulaşabilirsiniz. Örnekteki son değişiklikler ve güncelleştirmeler için GitHub deposuna başvurun.

1. **Microsoft Visual Studio**’yu açın.
2. **Dosya** > **Yeni Proje**’yi seçin. **Visual C#**’yi genişletin ve **Konsol Uygulaması (.Net Framework)** öğesini seçin.
3. Projeyi ` IntuneDataWarehouseSamples` olarak adlandırın, projeyi kaydetmek istediğiniz konuma göz atın ve **Tamam**’a tıklayın.
4. Çözüm Gezgini’nde çözümün adına sağ tıklayın ve daha sonra **Çözüm için NuGet Paketlerini Yönetme**’ye tıklayın. **Gözat**’a tıklayın, daha sonra arama kutusuna `Microsoft.IdentityModel.Clients.ActiveDirectory` yazın.
5. Paketi seçin, Çözümünüz için Paketleri Yönetme altında **IntuneDataWarehouseSamples**’a tıklayın ve daha sonra **Yükle**’yi seçin.
6. NuGet paket lisansını kabul etmek için **Kabul Ediyorum**’a tıklayın.
7. Çözüm Gezgini’nde `Program.cs` öğesini açın.

    ![Visual Studio’da Proje](./media/reports-get_rest_data_in.png)

8. Program.cs’deki kodu aşağıdaki kodla değiştirin:  
   ```csharp
   namespace IntuneDataWarehouseSamples
   {
   using System;
   using System.Net.Http;
   using System.Net.Http.Headers;
   using Microsoft.IdentityModel.Clients.ActiveDirectory;

   class Program
   {
    static void Main(string[] args)
   {
   /**
   * TODO: Replace the below values with your own.
   * emailAddress - The email address of the user that you will authenticate as.
   *
   * password  - The password for the above email address.
   *    This is inline only for simplicity in this sample. We do not
   *    recommend storing passwords in plaintext.
   *
   * applicationId - The application ID of the native app that was created in AAD.
   *
   * warehouseUrl   - The data warehouse URL for your tenant. This can be found in
   *      the Azure portal.
   *
   * collectionName - The name of the warehouse entity collection you would like to
   *      access.
   */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
   resource: "https://api.manage.microsoft.com/",
   clientId: applicationId,
   userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
   }
   }
   ```

9. Örnek koddaki `TODO` öğelerini değiştirin.
10. Intune.DataWarehouseAPIClient istemcisini derlemek ve Hata Ayıklama modunda yürütmek için **Ctrl + F5**’e basın.

    ![JSON biçiminde alınan tarih varlığı.](./media/reports-get_rest_data_output.png)

11. Konsol çıkışını gözden geçirin. Çıkış, Intune kiracınızdaki **tarihler** varlığından çekilen verileri JSON biçiminde barındırır.

## <a name="next-steps"></a>Sonraki adımlar

Yetkilendirme, API URL yapısı ve OData uç noktaları hakkında ayrıntıları [Intune Veri Ambarı API’sini kullanma](reports-api-url.md) sayfasında bulabilirsiniz.

Ayrıca API’de bulunan veri varlıklarını bulmak için Intune Veri Ambarı Veri Modeli’ne de başvurabilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı API’si Veri Modeli](reports-ref-data-model.md)
