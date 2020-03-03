---
title: Intune ile Android Enterprise için Microsoft başlatıcısı yapılandırma
titleSuffix: ''
description: Microsoft başlatıcısı ile Intune yapılandırma ilkelerini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55f76b0c5c71f7828fed17233c2b81d6b066cc3b
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216119"
---
# <a name="configure-microsoft-launcher"></a>Microsoft Launcher’ı yapılandırma

Microsoft başlatıcısı, kullanıcıların telefonlarını kişiselleştirmesini, yolculuğuna devam etmenizi ve telefonlarından kendi PC 'lerine aktarılmasını sağlayan bir Android uygulamasıdır. 

Android kurumsal tam yönetilen cihazlarda, Başlatıcı, Kuruluş BT yöneticilerinin duvar kağıdı, uygulamalar ve simge konumlarını seçerek yönetilen cihaz giriş ekranlarını özelleştirmesini sağlar. Bu, farklı OEM cihazlarındaki ve sistem sürümlerindeki tüm yönetilen Android cihazlarının görünümünü standartlaştırır. 

## <a name="how-to-configure-the-microsoft-launcher-app"></a>Microsoft başlatıcısı uygulamasını yapılandırma 

[Microsoft Endpoint Manager yönetim merkezine](https://go.microsoft.com/fwlink/?linkid=2109431) gidin ve **uygulama yapılandırma ilkeleri** > **uygulamalar** ' ı seçin. **Android** çalıştıran **yönetilen cihazlar** için bir yapılandırma ilkesi ekleyin ve Ilişkili uygulama olarak **Microsoft başlatıcısı** ' nı seçin. Kullanılabilir farklı Microsoft başlatıcısı ayarlarını yapılandırmak için **yapılandırma ayarları** ' na tıklayın. 

## <a name="choosing-a-configuration-settings-format"></a>Yapılandırma ayarları biçimi seçme 

Microsoft başlatıcısı yapılandırma ayarlarını tanımlamak için kullanabileceğiniz iki yöntem vardır: 

- **Yapılandırma Tasarımcısı** , özellikleri açık veya kapalı ve değerleri ayarlamanıza olanak tanıyan kullanımı kolay bir kullanıcı arabirimi ile ayarları yapılandırmanıza olanak tanır. Bu yöntemde, paket Learray değer türünde birkaç devre dışı yapılandırma anahtarı vardır. Bu yapılandırma anahtarları yalnızca JSON verileri girilerek yapılandırılabilir. 

- **JSON verileri** , bir JSON betiği kullanarak tüm olası yapılandırma anahtarlarını tanımlamanızı sağlar. 

**Yapılandırma tasarlayıcısıyla**Özellikler eklerseniz, aşağıda gösterildiği gibi **yapılandırma ayarları BIÇIM** açılır listesinden **JSON verisi gir** ' i seçerek bu özellikleri JSON 'a dönüştürebilirsiniz.

   ![Yapılandırma ayarları biçimi-yapılandırma tasarımcısını kullan](./media/configure-microsoft-launcher/configure-microsoft-launcher-01.png)

## <a name="using-configuration-designer"></a>Yapılandırma tasarımcısını kullanma

Yapılandırma Tasarımcısı, önceden doldurulmuş ayarları ve bunlarla ilişkili değerleri seçmenizi sağlar.

   ![Yapılandırma ayarları biçimi-JSON verilerini girin](./media/configure-microsoft-launcher/configure-microsoft-launcher-02.png)

Aşağıdaki tabloda, Microsoft başlatıcısı kullanılabilir yapılandırma anahtarları, değer türleri, varsayılan değerler ve açıklamalar listelenmektedir. Açıklama, seçilen değerlere göre beklenen cihaz davranışını sağlar. Yapılandırma tasarımcısında devre dışı bırakılan yapılandırma anahtarları tabloda listelenmez.

|    Yapılandırma Anahtarı    |    Değer türü    |    Varsayılan değer    |    Açıklama     |
|---------------------------------------------------|------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Kayıt türü    |    Dize     |    Varsayılan    |    Bu ilkenin uygulanması gereken kayıt türünü ayarlamanıza olanak sağlar. Şu anda **varsayılan** değer **CorporateOwnedBuisnessOnly**' e başvurur. Var olan başka bir desteklenen kayıt türü yok.        JSON anahtar adı: management_mode_key        |
|    Giriş ekranı uygulama siparişi kullanıcı değişikliğine Izin verildi    |    Boole değeri    |    Doğru    |    **Giriş ekranı uygulama sırası** ayarının Son Kullanıcı tarafından değiştirilip değiştirilemeyeceğini belirtmenize olanak tanır.<ul><li>**True**olarak ayarlanırsa, ilkede tanımlanan uygulama sırası yalnızca ilk dağıtım için zorlanır. Daha sonra, Kullanıcı yapmış olabileceği değişikliklere göre ilke zorlanmaz.</li><li>**False**olarak ayarlanırsa, uygulama sırası her eşitlemede zorlanır.</li></ul><br>**Note:** Giriş ekranı uygulama sırası yalnızca JSON Düzenleyicisi aracılığıyla yapılandırılabilir.<br><br>JSON anahtar adı:<br>`com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed`    |
|    Izgara boyutunu ayarla    |    Dize    |    Otomatik    |    Ana ekranda konumlandırılmış uygulamaların kılavuz boyutunu ayarlamanıza olanak sağlar. Kılavuz boyutunu tanımlamak için uygulama satır ve sütun sayısını şu biçimde ayarlayabilirsiniz: `columns;rows`. Kılavuz boyutunu tanımlarsanız, giriş ekranındaki bir satırda gösterilecek en fazla uygulama sayısı, ayarladığınız satır sayısı ve giriş ekranındaki bir sütunda gösterilecek en fazla uygulama sayısı, ayarladığınız sütun sayısı olacak şekilde değişir.<br><br>        JSON anahtar adı:<br>`com.microsoft.launcher.HomeScreen.GridSize`    |
|    Cihaz duvar kağıdını ayarla    |    Dize    |    Null    |    Duvar kağıdı olarak ayarlamak istediğiniz görüntünün URL 'sini girerek tercih ettiğiniz bir duvar kağıdını ayarlamanıza olanak sağlar.<br><br>JSON anahtar adı:<br>`com.microsoft.launcher.Wallpaper.URL`    |
|    Cihaz duvar kağıdı kullanıcı değişikliğine Izin verildi    |    Bool    |    Doğru    |    Cihazın duvar kağıdını ayarla ayarının Son Kullanıcı tarafından değiştirilip değiştirilemeyeceğini belirtmenize olanak tanır.<ul><li>**True**olarak ayarlanırsa, ilkedeki duvar kağıdı yalnızca ilk dağıtım için zorunlu kılınır. Daha sonra, Kullanıcı yapmış olabileceği değişikliklere göre ilke zorlanmaz.</li><li>**False**olarak ayarlanırsa, bu duvar kağıdı her eşitlemede zorlanır.</li></ul><br>JSON anahtar adı:<br>`com.microsoft.launcher.Wallpaper.URL.UserChangeAllowed`        |
|    Akış etkinleştir    |    Boole değeri    |    Doğru    |    Kullanıcı ana ekranda sağa doğru geldiğinde, cihazda Başlatıcı akışını etkinleştirmenizi sağlar.<ul><li>**True**olarak ayarlanırsa akış etkinleştirilir.</li><li>**False**olarak ayarlanırsa akış devre dışı bırakılır.</li></ul><br>JSON anahtar adı:<br>`com.microsoft.launcher.Feed.Enabled`    |
|    Akış etkinleştirme kullanıcı değişikliğine Izin verildi    |    Boole değeri    |    Doğru    |     **Akış etkinleştirme** ayarının Son Kullanıcı tarafından değiştirilip değiştirilemeyeceğini belirtmenize olanak tanır.<ul><li>**True**olarak ayarlanırsa, akış yalnızca ilk dağıtım için zorlanır. Daha sonra, Kullanıcı yapmış olabileceği değişikliklere göre ilke zorlanmaz.</li><li>**False**olarak ayarlanırsa, akış her eşitlemede zorlanır.</li></ul><br>JSON anahtar adı:`com.microsoft.launcher.Feed.Enabled.UserChangeAllowed`    |

## <a name="enter-json-data"></a>JSON verilerini girin

Microsoft başlatıcısı için tüm kullanılabilir ayarları ve **yapılandırma tasarımcısında**devre dışı bırakılan ayarları aşağıda gösterildiği gibi YAPıLANDıRMAK için JSON verilerini girin.

   ![Yapılandırma Tasarımcısı-JSON verileri](./media/configure-microsoft-launcher/configure-microsoft-launcher-03.png)

Yapılandırma Tasarımcısı tablosunda (yukarıda) listelenen yapılandırılabilir ayarların listesine ek olarak, aşağıdaki tablo yalnızca JSON verileri aracılığıyla yapılandırabileceğiniz yapılandırma anahtarlarını sağlar.

|    Yapılandırma Anahtarı    |    Değer türü    |    Varsayılan değer    |    Açıklama     |
|----------------------------------------------------------------------------------------------------|-------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Izin verilen uygulamaları ayarla<br>JSON anahtarı:`com.microsoft.launcher.HomeScreen.Applications`    |    Paketleme Learray    | Bkz. [izin verilen uygulamaları ayarla](configure-microsoft-launcher.md#set-allow-listed-applications)</sup>    |    , Cihazda yüklü uygulamalar arasından giriş ekranında görünür olan uygulama kümesini tanımlamanızı sağlar. Uygulamaları, görünür hale getirmek istediğiniz uygulamaların uygulama paketi adını girerek tanımlayabilirsiniz; Örneğin, `com.android.settings`, ana ekranda ayarları erişilebilir hale getirir. Bu bölümde izin verilen uygulamaların, ana ekranda görünür olması için cihazda zaten yüklü olması gerekir.<p>Özelliklerinin<ul><li>**Paket:** Uygulama paketi adı</li><li>**Sınıf:** Belirli bir uygulama sayfasına özgü olan uygulama etkinliği. Bu değer boşsa varsayılan uygulama sayfasını kullanır.</li></ul>      |
|    Ana ekran uygulama sırası<br>JSON anahtarı: `com.microsoft.launcher.HomeScreen.AppOrder`    |    Paketleme Learray    |    Bkz: [giriş ekranı uygulama sırası](configure-microsoft-launcher.md#home-screen-app-order)      |    Ana ekranda uygulama sırasını belirtmenize izin verir.<p>Özelliklerinin<br><ul><li>**Şunu yazın:** Desteklenen tek tür `application`.</li><li>**Konum:** Ana ekrandaki uygulama simge yuvası. Bu, sol üstteki konum 1 ' den başlar ve yukarıdan aşağıya doğru aşağı doğru ilerler.</li><li>**Paket:** Uygulama paketi adı.</li><li>**Sınıf:** Belirli bir uygulama sayfasına özgü olan uygulama etkinliği. Varsayılan uygulama sayfası, bu değer boşsa kullanılacaktır.</li></ul>    |

### <a name="set-allow-listed-applications"></a>İzin verilen uygulamaları ayarla

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.Applications",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

### <a name="home-screen-app-order"></a>Ana ekran uygulama sırası

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.AppOrder",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "type",
                    "valueString": "application"
                },
                {
                    "key": "position",
                    "valueInteger": 0
                },
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

Aşağıda, tüm kullanılabilir yapılandırma anahtarlarının dahil olduğu bir JSON betiği verilmiştir:

```JSON
{
    "kind": "androidenterprise#managedConfiguration", 
    "productId": "app:com.microsoft.launcher", 
    "managedProperty": [
        {
            "key": "management_mode_key", 
            "valueString": "Default"
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable", 
            "valueBool": true
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url", 
            "valueBool": "http://www.contoso.com/wallpaper.png"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.GridSize", 
            "valueString": "5;5"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.Applications", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 17
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 18
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 19
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="next-steps"></a>Sonraki adımlar

- Android kurumsal tam olarak yönetilen cihazlar hakkında daha fazla bilgi için bkz. [Intune 'Da Android Enterprise tam yönetme cihazlarını ayarlama](../enrollment/android-fully-managed-enroll.md).
