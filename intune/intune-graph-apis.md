---
title: Microsoft Graph’ta Intune API’lerine erişmek için Azure AD kullanma
titlesuffix: Microsoft Intune
description: Microsoft Graph’ta Intune API’lerine erişmek üzere Azure AD kullanmak için uygulamalarda gereken adımları açıklar.
keywords: intune graphapi c# powershell permission roles
author: dougeby
manager: dougeby
ms.author: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ca5b09d415466d2ab6ce2f70a53f7fd8444d28f
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-azure-ad-to-access-the-intune-apis-in-microsoft-graph"></a>Microsoft Graph’ta Intune API’lerine erişmek için Azure AD kullanma

[Microsoft Graph API](https://developer.microsoft.com/graph/)’si artık belirli API’ler ve izin rolleriyle Microsoft Intune’u destekliyor.  Microsoft Graph API’si, kimlik doğrulama ve erişim denetimi için Azure Active Directory (Azure AD) kullanır.  
Microsoft Graph’ta Intune API’lerine erişmek için Azure AD kullanma gereksinimleri şu şekildedir:

- Aşağıdakileri içeren bir uygulama kimliği:

    - Azure AD ve Microsoft Graph API’lerini çağırma izni.
    - Belirli uygulama görevleri ile ilgili izin kapsamları.

- Aşağıdaki özelliklere sahip kimlik bilgilerini kullanın:

    - Uygulama ile ilişkili Azure AD kiracısına erişim izni.
    - Rol izinleri, uygulama izin kapsamlarını desteklemek için gereklidir.

- Son kullanıcı Azure kiracısı için uygulama görevleri gerçekleştirmesi üzere uygulamaya izin verir.

Bu makalede:

- Microsoft Graph API’si ve ilgili izin rollerine erişimi olan bir uygulamanın nasıl kaydedileceği gösterilir.

- Intune API’si izin rolleri açıklanır.

- C# ve PowerShell için Intune API’si kimlik doğrulama örnekleri verilir.

- Birden çok kiracının nasıl destekleneceği açıklanır.

Daha fazla bilgi için bkz:

- [OAuth 2.0 ve Azure Active Directory kullanarak web uygulamalarına erişim yetkisi verme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [Azure AD kimlik doğrulamasına başlarken](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [Uygulamaları Azure Active Directory ile tümleştirme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [OAuth 2.0’ı anlama](https://oauth.net/2/)

## <a name="register-apps-to-use-the-microsoft-graph-api"></a>Uygulamaları Microsoft Graph API kullanmak üzere kaydetme

Uygulamaları Microsoft Graph API kullanmak üzere kaydetmek için:

1.  Yönetici kimlik bilgilerini kullanarak [Azure portalında](https://portal.azure.com) oturum açın.

    Uygun olacak şekilde şunları kullanabilirsiniz:
    - Kiracı yönetici hesabı.
    - **Kullanıcılar uygulamaları kaydedebilir** ayarı etkin şekilde bir kiracı kullanıcı hesabı.

2.  Menüden **Azure Active Directory** &gt; **Uygulama Kayıtları**’nı seçin.

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  Yeni bir uygulama oluşturmak için **Yeni uygulama kaydı**’nı veya mevcut bir uygulamayı seçin.  (Mevcut bir uygulamayı seçerseniz, sonraki adımı atlayın.)

4.  **Oluştur** dikey penceresinde aşağıdakileri belirtin:

    1.  Uygulama için bir **Ad** (kullanıcılar oturum açtığında görüntülenir).

    2.  **Uygulama türü** ve **Yeniden yönlendirme URI'si** değerleri.

        Bunlar, gereksinimlerinize göre farklılık gösterir. Örneğin, Azure AD [Kimlik Doğrulama Kitaplığı](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) kullanıyorsanız **Uygulama Türü**’nü `Native` ve **Yeniden Yönlendirme URI'sini** `urn:ietf:wg:oauth:2.0:oob` olarak ayarlayın.

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        Daha fazla bilgi için bkz. [Azure AD İçin Kimlik Doğrulama Senaryoları](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

5.  Uygulama dikey penceresinden:

    1.  **Uygulama Kimliği** değerini not edin.

    2.  **Ayarlar** &gt; **API erişimi** &gt; **Gerekli izinler**’i seçin.

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  **Gerekli İzinler** dikey penceresinden, **Ekle** &gt; **API erişimi ekle** &gt; **Bir API seçin**’i belirleyin.

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  **Bir API seçin** dikey penceresinden, **Microsoft Graph** &gt; **Seçin** öğelerini belirleyin.  **Erişimi etkinleştir** dikey penceresi açılır ve uygulamanızda kullanılabilen izin kapsamları listelenir.

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    İlgili adların soluna onay işareti koyarak uygulamanız için gereken rolleri seçin.  Belirli Intune izin kapsamları hakkında bilgi edinmek için bkz. [Intune izin kapsamları](#intune-permission-scopes).  Diğer Graph API'si izin kapsamları hakkında bilgi edinmek için bkz. [Microsoft Graph izinleri başvurusu](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).

    En iyi sonuçlar için, uygulamanızı uygulamak için gereken en düşük rolü seçin.

    Tamamlandığında, değişikliklerinizi kaydetmek için **Seçin** ve **Bitti**’yi seçin.

Bu noktada, ayrıca:

- Uygulamanın kimlik bilgileri sağlamadan kullanılabilmesi için tüm kiracı hesaplarına izin vermeyi seçebilirsiniz.  

    Bunu yapmak için, **İzinleri ver**’i seçin ve onaylayın.

    Uygulamayı ilk kez çalıştırdığınızda, seçili rolleri gerçekleştirmek için uygulama izni vermeniz istenir.

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- Uygulamayı kiracınızın dışındaki kullanıcılar için kullanılabilir hale getirin.  (Bu genellikle yalnızca birden çok kiracı/kuruluş destekleyen iş ortakları için gereklidir.)  

    Bunu yapmak için:

  1. Uygulama dikey penceresinden **Bildirim**’i seçin; böylece **Bildirimi Düzenle** dikey penceresi açılır.

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. `availableToOtherTenants` ayarının değerini `true` olarak değiştirin.

  3. Yaptığınız değişiklikleri kaydedin.

## <a name="intune-permission-scopes"></a>Intune izin kapsamları

Azure AD ve Microsoft Graph, kurumsal kaynaklara erişimi denetlemek için izin kapsamlarını kullanır.  

İzin kapsamları (_OAuth kapsamları_ olarak da bilinir) belirli Intune varlıkları ve bunların özelliklerine erişimi denetler. Bu bölümde Intune API’si özellikleri için izin kapsamları özetlenir.

Daha fazlasını öğrenin:
- [Azure AD kimlik doğrulaması](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [Uygulama izin kapsamları](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

Microsoft Graph’a izin verdiğinizde, Intune özelliklerine erişimi denetlemek için aşağıdaki kapsamları belirtebilirsiniz: Intune API’si izin kapsamları aşağıdaki tabloda özetlenmiştir.  İlk sütun özelliğin adını Azure portalında görüntülenen şekliyle gösterir ve ikinci sütun izin kapsam adını sağlar.

_Erişimi Etkinleştir_ ayarı | Kapsam adı
:--|:--
__Microsoft Intune cihazlarında kullanıcıları etkileyen uzak eylemler gerçekleştirme__ | [DeviceManagementManagedDevices.PrivilegedOperations.All](#mgd-po)
__Microsoft Intune cihazlarını okuma ve yazma__ | [DeviceManagementManagedDevices.ReadWrite.All](#mgd-rw)
__Microsoft Intune cihazlarını okuma__ | [DeviceManagementManagedDevices.Read.All](#mgd-ro)
__Microsoft Intune RBAC ayarlarını okuma ve yazma__ | [DeviceManagementRBAC.ReadWrite.All](#rac-rw)
__Microsoft Intune RBAC ayarlarını okuma__ | [DeviceManagementRBAC.Read.All](#rac=ro)
__Microsoft Intune uygulamalarını okuma ve yazma__ | [DeviceManagementApps.ReadWrite.All](#app-rw)
__Microsoft Intune uygulamalarını okuma__ | [DeviceManagementApps.Read.All](#app-ro)
__Microsoft Intune Cihaz Yapılandırması ve İlkelerini okuma ve yazma__ | [DeviceManagementConfiguration.ReadWrite.All](#cfg-rw)
__Microsoft Intune Cihaz Yapılandırması ve İlkelerini okuma__ | [DeviceManagementConfiguration.Read.All](#cfg-ro)
__Microsoft Intune yapılandırmasını okuma ve yazma__ | [DeviceManagementServiceConfig.ReadWrite.All](#svc-rw)
__Microsoft Intune yapılandırmasını okuma__ | [DeviceManagementServiceConfig.Read.All](#svc-ra)

Tablo, ayarları Azure portalında göründükleri sırayla listeler. Aşağıdaki bölümlerde kapsamlar alfabetik sırayla açıklanır.

Şu anda tüm Intune izin kapsamları yönetici erişimi gerektirir.  Başka bir deyişle, Intune API’si kaynaklarına erişen uygulamaları veya betikleri çalıştırırken ilgili kimlik bilgilerine sahip olmanız gerekir.

### <a name="app-ro"></a>DeviceManagementApps.Read.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune uygulamalarını okuma__

- Aşağıdaki varlık özelliklerine ve durumuna okuma erişimi verir:
    - Mobil Uygulamalar
    - Mobil Uygulama Kategorileri
    - Uygulama Koruma İlkeleri
    - Uygulama Yapılandırmaları

### <a name="app-rw"></a>DeviceManagementApps.ReadWrite.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune uygulamalarını okuma ve yazma__

- __DeviceManagementApps.Read.All__ ile aynı işlemlere izin verir

- Ayrıca aşağıdaki varlıklarda değişiklik yapmaya izin verir:

    - Mobil Uygulamalar
    - Mobil Uygulama Kategorileri
    - Uygulama Koruma İlkeleri
    - Uygulama Yapılandırmaları

### <a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune cihaz yapılandırması ve ilkelerini okuma__

- Aşağıdaki varlık özelliklerine ve durumuna okuma erişimi verir:
    - Cihaz Yapılandırması
    - Cihaz Uyumluluğu İlkesi
    - Bildirim İletileri

### <a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune cihaz yapılandırması ve ilkelerini okuma ve yazma__

- __DeviceManagementConfiguration.Read.All__ ile aynı işlemlere izin verir

- Uygulamalar ayrıca aşağıdaki varlıkları oluşturabilir, atayabilir, silebilir ve değiştirebilir:
    - Cihaz Yapılandırması
    - Cihaz Uyumluluğu İlkesi
    - Bildirim İletileri

### <a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune cihazlarda kullanıcıları etkileyen uzak eylemler gerçekleştirme__

- Aşağıdaki uzak eylemlere yönetilen bir cihazda izin verir:
    - Devre dışı bırakma
    - Silme
    - Geçiş Kodu Sıfırlama/Kurtarma
    - Uzaktan Kilitleme
    - Kayıp Modunu Etkinleştirme/Devre Dışı Bırakma
    - Bilgisayarı Temizleme
    - Yeniden başlat
    - Paylaşılan Cihazdan Kullanıcı Silme

### <a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune cihazlarını okuma__

- Aşağıdaki varlık özelliklerine ve durumuna okuma erişimi verir:
    - Yönetilen Cihaz
    - Cihaz Kategorisi
    - Algılanan Uygulama
    - Uzak eylemler
    - Kötü amaçlı yazılım bilgileri

### <a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune cihazlarını okuma ve yazma__

- __DeviceManagementManagedDevices.Read.All__ ile aynı işlemlere izin verir

- Uygulamalar ayrıca aşağıdaki varlıkları oluşturabilir, silebilir ve değiştirebilir:
    - Yönetilen Cihaz
    - Cihaz Kategorisi

- Aşağıdaki uzak eylemlere de izin verilir:
    - Cihaz bulma
    - Etkinleştirme kilidini atlama
    - Uzaktan yardım isteme

### <a name="rac-ro"></a>DeviceManagementRBAC.Read.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune RBAC ayarlarını okuma__

- Aşağıdaki varlık özelliklerine ve durumuna okuma erişimi verir:
    - Rol Atamaları
    - Rol Tanımları
    - Kaynak İşlemleri

### <a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune RBAC ayarlarını okuma ve yazma__

- __DeviceManagementRBAC.Read.All__ ile aynı işlemlere izin verir

- Uygulamalar ayrıca aşağıdaki varlıkları oluşturabilir, atayabilir, silebilir ve değiştirebilir:
    - Rol Atamaları
    - Rol Tanımları

### <a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune yapılandırmasını okuma__

- Aşağıdaki varlık özelliklerine ve durumuna okuma erişimi verir:
    - Aygıt Kaydetme
    - Apple Anında İletilen Bildirim Servisi Sertifikası
    - Apple Cihaz Kaydı Programı
    - Apple Volume Purchase Program
    - Exchange Connector
    - Hüküm ve Koşullar
    - Telekom Gider Yönetimi
    - Bulut PKI
    - Markalama
    - Mobile Threat Defense

### <a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All

- **Erişimi Etkinleştir** ayarı: __Microsoft Intune yapılandırmasını okuma ve yazma__

- DeviceManagementServiceConfig.Read.All_ ile aynı işlemlere izin verir

- Uygulamalar, aşağıdaki Intune özelliklerini de yapılandırabilir:
    - Aygıt Kaydetme
    - Apple Anında İletilen Bildirim Servisi Sertifikası
    - Apple Cihaz Kaydı Programı
    - Apple Volume Purchase Program
    - Exchange Connector
    - Hüküm ve Koşullar
    - Telekom Gider Yönetimi
    - Bulut PKI
    - Markalama
    - Mobile Threat Defense

## <a name="azure-ad-authentication-examples"></a>Azure AD kimlik doğrulaması örnekleri

Bu bölümde Azure AD’nin C# ve PowerShell projelerinize nasıl dahil edileceği gösterilir.

Her örnekte, en az `DeviceManagementManagedDevices.Read.All` izni kapsamına (daha önce açıklanmıştır) sahip bir uygulama kimliği belirtmeniz gerekir.

Her iki örnek sınanırken, aşağıdakine benzer HTTP durumu 403 (Yasak) hataları alabilirsiniz:

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

Bu durumda, aşağıdakileri doğrulayın:

- Uygulama kimliğini, Microsoft Graph API’si ve `DeviceManagementManagedDevices.Read.All` izni kapsamını kullanmaya yetkili biri için güncelleştirdiniz.

- Kiracı kimlik bilgileriniz yönetimsel işlevleri destekliyor.

- Kodunuz görüntülenen örneklere benzer.


### <a name="authenticate-azure-ad-in-c"></a>Azure AD kimlik doğrulamasını C\# içinde gerçekleştirme

Bu örnek, Intune hesabınızla ilişkili cihazların bir listesini almak için C#’nin nasıl kullanılacağını gösterir.

1.  Visual Studio'yu başlatın ve ardından yeni bir Visual C# Konsol uygulaması (.NET Framework) projesi oluşturun.

2.  Projeniz için bir ad girin ve diğer ayrıntıları istediğiniz gibi sağlayın.

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  Microsoft ADAL NuGet paketini projeye eklemek için Çözüm Gezgini’ni kullanın.

    1.  Çözüm Gezgini’ne sağ tıklayın.
    2.  **NuGet Paketlerini Yönet...**’i seçin &gt; **Gözat**.
    3.  `Microsoft.IdentityModel.Clients.ActiveDirectory` seçeneğini belirleyin ve **Yükle**’yi seçin.

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  Aşağıdaki deyimleri **Program.cs**’nin en üst kısmına ekleyin:

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  Yetkilendirme üst bilgisi oluşturmak için bir yöntem ekleyin:

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    Daha önce açıklandığı gibi, en az `DeviceManagementManagedDevices.Read.All` izin kapsamı iznine sahip olan biriyle eşleştirmek üzere `application_ID` değerini değiştirmeyi unutmayın.

6. Cihaz listesini almak için bir yöntem ekleyin:

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  **Ana**’yı güncelleştirerek **GetMyManagedDevices**’ı çağırın:

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  Derleyin ve programınızı çalıştırın.  

Programınızı ilk kez çalıştırdığınızda, iki istem almanız gerekir.  İlk istem kimlik bilgilerinizi ister ve ikincisi `managedDevices` isteği için izinler verir.  

Başvuru için tamamlanmış program şöyledir:

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a>Azure AD Kimlik Doğrulaması (PowerShell)

Aşağıdaki PowerShell betiği, kimlik doğrulaması için AzureAD PowerShell modülü kullanır.  Daha fazla bilgi için bkz. [Azure Active Directory PowerShell Sürüm 2](https://docs.microsoft.com/powershell/azure/install-adv2?view=azureadps-2.0) ve [Intune PowerShell örnekleri](https://github.com/microsoftgraph/powershell-intune-samples).

Bu örnekte, geçerli bir uygulama kimliği eşleştirmek için `$clientID` değerini güncelleştirin.

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a>Birden çok kiracı ve iş ortağı destekleme

Kuruluşunuz, kuruluşları kendi Azure AD kiracıları ile destekliyorsa, istemcilerinize uygulamanızı ilgili kiracıları ile kullanacakları şekilde izin vermek isteyebilirsiniz.

Bunu yapmak için:

1.  İstemci hesabının hedef Azure AD kiracısında mevcut olduğunu doğrulayın.

2.  Kiracı hesabınızın kullanıcıların uygulama kaydetmelerine izin verdiğinden emin olun (bkz **Kullanıcı ayarları**).

3.  Her kiracı arasında bir ilişki oluşturun.  

    Bunu yapmak için aşağıdaki seçeneklerden birini kullanın:

    a. İstemciniz ve e-posta adresi arasında bir ilişki tanımlamak için [Microsoft İş Ortağı Merkezi](https://partnercenter.microsoft.com/)’ni kullanın.

    b. Kullanıcıyı kiracınızın konuğu olmaya davet edin.

Kullanıcıyı kiracınızın konuğu olmaya davet etmek için:

1.  **Hızlı görevler** panelinden **Konuk kullanıcı ekle**’yi seçin.

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  İstemcinin e-posta adresini girin ve (isteğe bağlı olarak) davet için kişisel bir ileti ekleyin.

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  **Davet et**’i seçin.

Bu, kullanıcıya bir davet gönderir.

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   Kullanıcının daveti kabul etmek için **Başlarken** bağlantısını seçmesi gerekir.

İlişki oluşturulduğunda (veya davetiniz kabul edildiğinde), kullanıcı hesabını **Dizin rolü** kısmına ekleyin.

Gerekirse kullanıcıyı diğer rollere de eklemeyi unutmayın. Örneğin, kullanıcının Intune ayarlarını yönetmesine izin vermek için kullanıcıların ya bir **Genel Yönetici** ya da bir **Intune Hizmet yöneticisi** olması gerekir.

Ayrıca:

- Kullanıcı hesabınıza bir Intune lisansı atamak için https://portal.office.com adresini kullanın.

- Uygulama kodunu kendinizin değil, istemcinin Azure AD kiracısı etki alanının kimlik doğrulaması için güncelleştirin.

    Örneğin, kiracı etki alanınızın `contosopartner.onmicrosoft.com` ve istemcinin kiracı etki alanının `northwind.onmicrosoft.com` olduğunu varsayalım, kodunuzu istemcinizin kiracı kimlik doğrulaması için güncelleştirmeniz gerekir.

    Önceki örnekte olduğu gibi bir C# uygulamasında bunu yapmak için `authority` değişkeninin değerini değiştirmeniz gerekir:

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    seçeneğini

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
