---
title: Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama
titleSuffix: Microsoft Intune
description: Bu konuda, Microsoft Intune için yalnızca veri ambarı uygulama kimlik doğrulaması açıklanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d7166563-6bb5-4624-b8c8-6b300a997c3a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa6dacf8b6498175e9e7658689bee3a527e684cc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490720"
---
# <a name="intune-data-warehouse-application-only-authentication"></a>Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama

Azure Active Directory (Azure AD) kullanarak bir uygulamayı ayarlayabilir ve Intune Veri Ambarı’nda kimlik doğrulayabilirsiniz. Bu işlem web siteleri, uygulamalar ve uygulamanın kullanıcı kimlik bilgilerine erişmemesi gereken arka plan işlemlerinde işe yarar. Aşağıdaki adımları izlediğinizde OAuth 2.0 kullanarak uygulamanızı Azure AD’de yetkilendirirsiniz.

## <a name="authorization"></a>Yetkilendirme

Azure Active Directory (Azure AD), OAuth 2.0’ı kullanarak Azure AD kiracınızdaki web uygulamalarına ve web API’lerine erişim yetkisi vermenize olanak tanır. Bu kılavuz, uygulamanızın kimliğini C# kullanarak nasıl doğrulayacağınızı gösterir. OAuth 2.0 yetkilendirme kod akışı, OAuth 2.0 belirtiminin 4.1. bölümünde açıklanmıştır. Daha fazla bilgi için bkz. [OAuth 2.0 ve Azure Active Directory kullanarak web uygulamalarına erişim yetkisi verme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).


## <a name="azure-keyvault"></a>Azure KeyVault

Aşağıdaki işlem, bir uygulama anahtarını işlemek ve dönüştürmek için gizli bir yöntem kullanır. Bu gizli yöntem SecureString olarak adlandırılmıştır. Alternatif olarak uygulaman anahtarını depolamak için Azure KeyVault kullanabilirsiniz. Daha fazla bilgi için bkz. [Key Vault](https://azure.microsoft.com/services/key-vault/).

## <a name="create-a-web-app"></a>Web uygulaması oluşturma

Bu bölümde, Intune’da yönlendirme yapmak istediğiniz Web uygulaması hakkında ayrıntılar sağlayacaksınız. Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Bu tür bir uygulama Web’de ayrı olarak korunur. Intune’a web uygulaması erişimi vermek için Intune’u kullanırsınız. Veri akışı, web uygulaması tarafından başlatılır. 

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. Azure portalının üst tarafında yer alan **Arama kaynakları, hizmetler ve belgeler** alanını kullanarak **Azure Active Directory**’yi aratın.
3. Açılan menüde **Hizmetler**’in altında **Azure Active Directory**’yi seçin.
4. **Uygulama kayıtları**’nı seçin.
5. **Yeni uygulama kaydı**’nı seçerek **Oluştur** dikey penceresini görüntüleyin.
6. **Oluştur** dikey penceresinde uygulama ayrıntılarınızı ekleyin:

    - Bir uygulama adı, örneğin *Intune Uygulaması-Yalnızca Auth*.
    - **Uygulama türü**. **Web uygulaması / API**’yi seçerek bir web uygulamasını, bir web API'sini veya her ikisini temsil eden bir uygulama ekleyin.
    - Uygulamanın **oturum açma URL’sini**. Bu, kullanıcıların kimlik doğrulama işlemi sırasında otomatik olarak gittiği konumdur. Söyledikleri kişi olduklarını kanıtlamaları gerekir. Daha fazla bilgi için bkz. [Uygulama erişimi ve Azure Active Directory ile çoklu oturum açma nedir?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

7. **Oluştur** dikey penceresinin alt kısmında **Oluştur**’a tıklayın.

    >[!NOTE] 
    > **Kayıtlı uygulama** dikey penceresindeki **Uygulama kimliği**’ni daha sonra kullanmak üzere kopyalayın.

## <a name="create-a-key"></a>Anahtar oluşturma

Bu bölümde Azure AD, uygulamanız için bir anahtar değeri oluşturur.

1. **Uygulama kayıtları** dikey penceresinde yeni oluşturulmuş uygulamanızı seçerek uygulama dikey penceresini görüntüleyin.
2. Dikey pencerenin üst kısmındaki **Ayarlar**’ı seçerek **Ayarlar** dikey penceresini görüntüleyin.
3. **Ayarlar** dikey penceresinde **Anahtarlar**’ı seçin.
4. Anahtar için **Açıklama**, **Bitiş** süresi ve **Değer** girin.
5. **Kaydet**’e tıklayarak uygulamanın anahtarlarını kaydedin ve güncelleştirin.
6. Oluşturulan anahtar değerini (şifreli base64) kopyalamanız gerekir.

    >[!NOTE] 
    > **Anahtarlar** dikey penceresinden çıktığınızda anahtar değeri kaybolur. Ve daha sonra anahtarı bu dikey pencereden alamazsınız. Daha sonra kullanmak üzere anahtarı burada kopyalayın.

## <a name="grant-application-permissions"></a>Uygulama izinleri verme

Bu bölümde, uygulamalara izinler vereceksiniz.

1. **Ayarlar** dikey penceresinde **Gerekli izinler**’i seçin.
2. **Ekle**' ye tıklayın.
3. **Bir API ekle**’yi seçerek **Bir API seç** dikey penceresini görüntüleyin.
4. **Microsoft Intune API (MicrosoftIntuneAPI)** ’yi seçin ve daha sonra **Bir API seç** dikey penceresinden **Seç**’e tıklayın. **İzinleri seç** adımı seçilir ve **Erişim Ver** dikey penceresi görüntülenir.
5. **Uygulama İzinleri** bölümüden **Microsoft Intune’dan veri ambarı bilgileri al**’ı seçin.
6. **Erişim Ver** dikey penceresinde **Seç**’e tıklayın.
7. **API erişimi ekle** dikey penceresinde **Tamam**’a tıklayın.
8. **Gerekli İzinler** dikey penceresinde **İzinleri Ver**’e tıklayın ve bu uygulamanın önceden sahip olduğu izinleri güncelleştirmeniz istendiğinde **Evet**’i seçin.

## <a name="generate-token"></a>Belirteç oluşturma

Visual Studio’yu kullanarak .NET Framework’ü destekleyen ve kodlama dili olarak C# kullanan bir Konsol Uygulaması (.NET Framework) projesi oluşturun.

1. **Dosya** > **Yeni** > **Proje**’yi seçerek **Yeni Proje** iletişim kutusunu görüntüleyin.
2. Sol tarafta **Visual C#** ’yi seçerek tüm .NET Framework projelerini görüntüleyin.
3. **Konsol Uygulaması (.NET Framework)** ’nı seçin, bir uygulama adı ekleyin ve **Tamam**’a tıklayarak uygulamayı oluşturun.
4. **Çözüm Gezgini**’nde **Program.cs**’yi seçerek kodu görüntüleyin.
5. Çözüm Gezgini, derleme `System.Configuration` ' a bir başvuru ekleyin.
6. Açılan menüde **Ekle** > **Yeni öğe**’yi seçin. **Yeni Öğe Ekle** iletişim kutusu görüntülenir.
7. Sol tarafta, **Visual C#** altında **Kod**’u seçin.
8. **Sınıf** seçin, sınıfın adını *IntuneDataWarehouseClass.cs* olarak değiştirin ve **Ekle**’ye tıklayın.
9. <code>Main</code> yönteminde aşağıdaki kodu ekleyin:

    ``` csharp
         var applicationId = ConfigurationManager.AppSettings["appId"].ToString();
         SecureString applicationSecret = ConvertToSecureStr(ConfigurationManager.AppSettings["appKey"].ToString()); // Load as SecureString from configuration file or secret store (i.e. Azure KeyVault)
         var tenantDomain = ConfigurationManager.AppSettings["tenantDomain"].ToString();
         var adalContext = new AuthenticationContext($"https://login.windows.net/" + tenantDomain + "/oauth2/token");
    
         AuthenticationResult authResult = adalContext.AcquireTokenAsync(
             resource: "https://api.manage.microsoft.com/",
             clientCredential: new ClientCredential(
                 applicationId,
                 new SecureClientSecret(applicationSecret))).Result;
    ``` 

10. Kod dosyasının üstüne aşağıdaki kodu ekleyerek ilave ad alanları ekleyin:

    ``` csharp
     using System.Security;
     using Microsoft.IdentityModel.Clients.ActiveDirectory;
     using System.Configuration;
    ``` 

11. <code>Main</code> yönteminden sonra, uygulama anahtarını işlemek ve dönüştürmek için aşağıdaki gizli yöntemi ekleyin:

    ``` csharp
    private static SecureString ConvertToSecureStr(string appkey)
    {
        if (appkey == null)
            throw new ArgumentNullException("AppKey must not be null.");
    
        var secureAppKey = new SecureString();
    
        foreach (char c in appkey)
            secureAppKey.AppendChar(c);
    
        secureAppKey.MakeReadOnly();
        return secureAppKey;
    }
    ```

12. **Çözüm Gezgini**’nde **Başvurular**’a sağ tıklayın ve daha sonra **NuGet Paketlerini Yönet**’i seçin.
13. *Microsoft.IdentityModel.Clients.ActiveDirectory*’yi aratın ve ilgili Microsoft NuGet paketini yükleyin.
14. **Çözüm Gezgini**’nde *App.config* dosyasını seçin ve açın.
15. xml’in aşağıdaki gibi görünmesi için <code>appSettings</code> kısmını ekleyin:

    ``` xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup> 
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <appSettings>
          <add key="appId" value="App ID created from 'Create a Web App' procedure"/>
          <add key="appKey" value="Key created from 'Create a key' procedure" />
          <add key="tenantDomain" value="contoso.onmicrosoft.com"/>
        </appSettings>
    </configuration>
    ``` 

16. Uygulama ile ilgili benzersiz değerlerinizle eşleşmesi için <code>appId</code>, <code>appKey</code> ve <code>tenantDomain</code> değerlerini güncelleştirin.
17. Uygulamanızı oluşturun.

    >[!NOTE] 
    > İlave uygulama kodunu görmek için bkz. [Intune-Veri-Ambarı kod örneği](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/CSharp ).

## <a name="next-steps"></a>Sonraki Adımlar
Azure Key Vault hakkında daha fazla bilgi edinmek için [Azure Key Vault nedir?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) bölümünü gözden geçirin.

