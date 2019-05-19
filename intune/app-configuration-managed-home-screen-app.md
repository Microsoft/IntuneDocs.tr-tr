---
title: Yapılandırma Microsoft yönetilen giriş ekranı uygulaması
titleSuffix: Microsoft Intune
description: Microsoft yönetilen giriş ekranlı bir uygulama yapılandırmayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d28ac5f7964fa7b2ddb5ec9be1878ccdd3dadbd
ms.sourcegitcommit: 5fec35341d83b16023a92fc4b2b3e9237fc6c9ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65853931"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Yapılandırma Microsoft yönetilen Android Enterprise için giriş ekranı uygulaması

Yönetilen giriş ekranı aracılığıyla Intune'a kayıtlı ve çoklu uygulama bilgi noktası modunda çalışan şirkete ait adanmış Android kuruluş cihazlarının için kullanılan bir uygulamadır. Bu cihazlar için yönetilen giriş ekranı üzerinde çalıştırmak diğer onaylı uygulamalar için Başlatıcı gibi davranır. Yönetilen giriş ekranı BT yöneticilerinin cihazlarını özelleştirmek için ve son kullanıcının erişebildiği özellikleri kısıtlama olanağı sağlar. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Ne zaman Microsoft yönetilen giriş ekranı uygulamayı yapılandırma

Genellikle, ayarları aracılığıyla cihaz yapılandırması kullanılabilir ise ayarlarını yapılandırın. Bunu size zaman kazandırır yapılması, hataları en aza indirmek ve daha iyi bir Intune destek deneyimi sunacak. Ancak, bazı yönetilen giriş ekranı ayarları şu anda yalnızca aracılığıyla kullanılabilir **uygulama yapılandırma ilkeleri** Intune konsolunda dikey. Yapılandırma Tasarımcısı veya JSON betiği kullanarak farklı ayarlarının nasıl yapılandırılacağını öğrenmek için bu belgeyi kullanın. 

> [!NOTE]
> Şu anda mümkün ve izin ver-listelenen uygulamalar ayarlamak için önerilir ve web bağlantıları aracılığıyla sabitlenmiş **istemci uygulamaları** ve **cihaz Yapılandırması**. Kullanılabilir ayarların tam listesi için **cihaz Yapılandırması** giriş ekranı yönetilen etkisi, bkz: [cihaz ayarları ayrılmış](device-restrictions-android-for-work.md#dedicated-device-settings).  

İlk olarak, Azure portalında Intune konsoluna gidin ve Git **istemci uygulamaları** > **uygulama yapılandırma ilkeleri**. İçin bir yapılandırma İlkesi Ekle **yönetilen cihazlar** çalıştıran **Android** ve **giriş ekranı yönetilen** ilişkili uygulama. Tıklayarak **yapılandırma ayarlarını** farklı kullanılabilir yönetilen giriş ekranı ayarlarını yapılandırmak için. 

## <a name="choosing-a-configuration-settings-format"></a>Yapılandırma ayarları biçimi seçme

Yönetilen giriş ekranı için yapılandırma ayarlarını tanımlamak için kullanabileceğiniz iki yöntem vardır:

- **Yapılandırma Tasarımcısı** açıp geçiş özellikleri ve değerlerini ayarlayabilirsiniz sağlayan kullanımı kolay Arabirimiyle ayarlarını yapılandırmanıza olanak tanır. Bu yöntemde, değer türü ile birkaç devre dışı bırakılan yapılandırma anahtarlarını vardır `BundleArray`. Bu yapılandırma anahtarları yalnızca JSON verilerini girerek yapılandırılabilir. 
- **JSON verilerini** JSON betik kullanarak tüm olası yapılandırma anahtarları tanımlamanızı sağlar. 

Yapılandırma Tasarımcısı ile özellikleri eklerseniz, otomatik olarak bu özellikleri JSON seçerek dönüştürebilirsiniz **girin JSON verilerini** gelen **yapılandırma ayarları biçimi** açılır.

![Ekran yapılandırmasını biçimi seçeneklerini ayarlama](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Yapılandırma Tasarımcısını kullanma

Yapılandırma Tasarımcısı önceden doldurulmuş ayarları ve ilişkili değerleri seçmenizi sağlar. 

![Ek yapılandırma ayarlarının ekran görüntüsü](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

Aşağıdaki tabloda, giriş ekranı yönetilen kullanılabilir yapılandırma anahtarları, değer türleri, varsayılan değerleri ve açıklamaları listeler. Seçili değerlerine göre beklenen cihaz davranışının açıklamayı sağlar. Yapılandırma Tasarımcısı'nda devre dışı bırakılan yapılandırma anahtarlarını tabloda listelenmemiştir.

| Yapılandırma anahtarı | Değer türü | Varsayılan Değer | Açıklama |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kılavuz boyutunu ayarlama | dize | Otomatik | Yönetilen giriş ekranında konumlandırılan uygulamalar için kılavuz boyutu ayarlamanıza olanak tanır. Uygulama satırları ve sütunları kılavuz boyutu şu biçimde tanımlamak için sayısını ayarlayabilirsiniz `columns;rows`. Izgara boyutunu tanımlarsanız, bir satır için giriş ekranınızdaki gösterilir uygulamaların en yüksek sayısı ayarladığınız satır sayısını olacaktır ve giriş ekranına sütununda gösterilen uygulama maksimum sayısı ayarladığınız sütun sayısı olacaktır. |
| Ekran başlığı etkinleştir | bool | TRUE | Üst başlık, akış veya akış kartlar gibi yönetilen giriş ekranına sunan farklı görünümleri sağlar. Bu ayarı etkinleştirirseniz, cihaz kullanıcılarının başlığı görürsünüz. |
| Cihaz durum çubuğu | bool | TRUE | Giriş ekranı (wifi ve vb. gibi geçerli bağlantılarını görüntüleyen üst çubuk.) durum çubuğunda sağlar. Bu yapılandırma anahtarı etkinleştirirseniz son kullanıcı bağlantıları ve etkin uygulamalar temsil eden durum çubuklarında görüntülenen simgeler görmeniz mümkün olacaktır. |
| Bildirimleri rozetini etkinleştir | bool | FALSE | Yeni bildirim sayısı gösteren uygulama bildirim rozet uygulama simgeleri için etkinleştirir. Bu ayarı etkinleştirirseniz, son kullanıcılar sahip olan uygulamalar üzerinde bildirim rozetleri görür okunmamış bildirimler. Son kullanıcı badged olabilecek uygulamalar için herhangi bir bildirim görürsünüz, bu yapılandırmanın anahtar devre dışı tutarsanız da değil okunmamış bildirimler. |
| Kilit giriş ekranı | bool | TRUE | Giriş ekranında uygulama simgeleri taşıma yeteneğini son kullanıcının kaldırır. Bu yapılandırma anahtarı etkinleştirirseniz, uygulama simgeleri için giriş ekranınızdaki kilitlenir ve son kullanıcı giriş ekranı farklı kılavuz konumlara sürükleyip mümkün olmaz. Etkinleştirdiyseniz `false`, son kullanıcılar yönetilen giriş ekranında uygulama ve Web bağlantısı simgeleri taşımak mümkün olacaktır.  |
| Cihaz duvar kağıdı ayarlayın | dize | Varsayılan | Duvar kağıdı olarak ayarlamak istediğiniz görüntünün URL'sini girerek bir duvar kağıdı, tercih ettiğiniz ayarlamanıza olanak tanır. |
| Uygulama simgesi boyutunu ayarlama | integer | 2 | Giriş ekranında görüntülenen uygulama için bir simge boyutu ayarlamanıza olanak tanır. Bu yapılandırma için farklı boyutlarda - 0 (en küçüğe), 1 (küçük), 2 (Regular), aşağıdaki değerleri seçin (büyük) 3 ve 4 (büyük). |
| Uygulama klasör simge Ayarla | integer | 0 | Giriş ekranında uygulama klasörü görünümünü tanımlamanızı sağlar. Görünüm aşağıdaki değerlerden birini seçebilirsiniz: Koyu Square(0);   Koyu Circle(1); Açık Square(2); Circle(3) açık. |
| Hareketleri etkinleştir | bool | FALSE | Son kullanıcının eylemleri geçirme yukarı ve aşağı kaydırma gibi farklı hareketler atama olanağı sağlar. Bu yapılandırma anahtarı devre dışı bırakırsanız, son kullanıcıların yalnızca ikinci bir sayfa ise geçirme sağa ve ana sayfaya dön mümkün olacaktır. |
| Dikey kaydırma etkinleştir | bool | FALSE | Yönetilen giriş ekranında dikey kaydırmayı etkinleştirir. Bu yapılandırma anahtarı etkinleştirirseniz son kullanıcı yalnızca farklı dikey yerine çekerek yatay olarak sayfalara mümkün olacaktır. |
| Kümesi giriş ekranı tema | dize | Theme.Light.Blue | Farklı renk temaları önceden tanımlanmış bir dizi tema için giriş ekranı seçmenize olanak sağlar. Dize değeri şu biçimde girerek aşağıdaki Temalar seçebilirsiniz.   Theme.Light.Green. Burada açık ile koyu bir koyu tema ve yeşil değiştirilebilir mavi, sarı, pembe, kırmızı, turuncu ve mor tarafından değiştirilebilir. |
| Dock'ı etkinleştir | bool | FALSE | Uygulama dock bölümünde giriş ekranının altındaki görüntülenen kalıcı uygulamalar ve tüm yüklü uygulamalar için giriş noktası sağlar. Bu yapılandırma anahtarı etkinleştirirseniz son kullanıcı uygulamaları dock'taki erişebilir ve ayrıca izin ver-listelenen olup olmadığını cihazlarda tüm yüklü uygulamalar listesine gitmek için tüm uygulama bölümüne erişmek olacaktır. |
| Ekran yönünü Ayarla | integer | 1 | Ana ekran yönünü yatay modda dikey modda veya Otomatik döndürme izin verir. Değerler 1 (için dikey modda) girerek yönlendirmesini ayarlayabilirsiniz (yatay modda için) 2, 3 (için Autorotate). |
| Giriş ekranı akışını etkinleştir | bool | FALSE | Akış, giriş ekranının sol geçirilerek görülebilir giriş ekranının sağlar. Bu akış, içerik haber, takvim, sık kullanıcı uygulamaları ve Cortana sesli Yardımcısını kart vb. gibi farklı türde görüntüler. Bunu etkinleştirmek, son kullanıcı için giriş ekranınızdaki sol geçirilerek akışa gidebilirsiniz olacaktır. |
| Genel Bakış modunu etkinleştir | bool | FALSE | Son kullanıcıların eklemek veya kaldırmak için giriş ekranınızdaki varsayılan ekranından sağ tarafından çekerek erişilebilir farklı sayfalar sağlar. Bu etkinleştirirseniz, son kullanıcının varsayılan sayfasının giriş ekranı sağa disk belleğine alınan eklemek mümkün olacaktır, varsayılan sayfasını değiştirmek mümkün olacaktır ve yönetilen ana ekran ayarlarına erişmek mümkün olacaktır. |
| Cihaz telemetrisini etkinleştir | bool | FALSE | Yönetilen giriş ekranı için yakalanan tüm telemetri sağlar. Microsoft, bu etkinleştirirseniz, belirli bir uygulamanın bu cihazda başlatılmadan kaç kez gibi cihaz kullanım telemetri yakalamak mümkün olacaktır. |
| Beyaz listeye uygulamaları ayarlama | bundleArray | FALSE | Görünür uygulamalar kümesi için giriş ekranınızdaki cihazda yüklü uygulamalar arasında tanımlamanızı sağlar. Uygulamaları görünür hale getirmek istediğiniz uygulamaları, uygulama paketi adı girerek tanımlayabilir, örneğin com.android.settings ayarları erişilebilir giriş ekranında hale getirir. Uygulamalar bu, izin verilenler listesi bu bölümdeki zaten giriş ekranında görünür için cihazda yüklü. |
| Sabitlenmiş kümesi web bağlantıları | bundleArray | FALSE | PIN Web sitelerine hızlı başlatma simgeler ana ekran olarak sağlar. Bu yapılandırma ile URL tanımlayabilir ve tek bir dokunuşla tarayıcıda başlatmak son kullanıcı için giriş ekranına ekleyin. |
| Arama çubuğunu etkinleştir | bool | FALSE | Giriş ekranı arama çubuğunda sağlar. Bu etkinleştirirseniz, cihazın kullanıcıları için giriş ekranınızdaki nerede bunlar ne olursa olsun, Web'de arama yapmak istediğiniz girmeniz mümkün olur arama çubuğu görürsünüz. |
| Ayarlar uygulamasında devre dışı bırak | bool | FALSE | Ayarlar sayfasında yönetilen giriş ekranında devre dışı bırakır. Bu devre dışı bırakırsanız, son kullanıcının cihazın giriş yönetilen ekranın ayarlarına almak mümkün olmayacaktır. |
| Ekran koruyucusunu etkinleştir | bool | FALSE | Ekran koruyucu modu veya etkinleştirmek için. Varsa ayarlamak true, yapılandırabileceğiniz **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver**, ve **media_detect_ screen_saver**. |
| Ekran koruyucu görüntüsü | dize |   | Ekran koruyucu görüntünün URL'sini ayarlayın. Hiçbir URL ayarlarsanız, ekran koruyucu etkin olduğunda varsayılan ekranı cihazlarını göstermeyecektir.  |
| Ekran koruyucu zamanı göster | integer | 0 | Ekran koruyucu modu sırasında ekran koruyucuyu süreyi saniye cinsinden aygıt ayarlamak için seçeneği verir görüntüler. Süresiz olarak cihaz etkin olana kadar 0 olarak ayarlanırsa, ekran koruyucuyu ekran koruyucu modu gösterilir.  |
| Ekran koruyucu etkinleştirmek için etkin olmayan zaman | integer | 30 | Ekran koruyucu tetiklemeden önce cihazı devre dışı kaldığı saniye sayısı. 0 olarak cihaz hiçbir zaman ekran koruyucu moduna geçer. |
| Ekran koruyucu göstermeden önce medya algılayın | bool | TRUE | Cihazda ses/video oynatma, cihaz ekranında ekran koruyucu göstermelidir olup olmadığını seçin. TRUE olarak cihaz değeri ne olursa olsun ses/video, çalışmaz, **inactive_time_to_show_scree_saver**. False olarak ayarlanırsa, cihaz ekranı Ekran koruyucu ayarlanan değere göre gösterilir, **inactive_time_to_show_screen_saver**.   |
| Sanal giriş düğmesini etkinleştir | bool | FALSE | Bu ayarı etkinleştirmek `True` son kullanıcı oldukları geçerli görev yönetilen giriş ekranına dönersiniz yönetilen giriş ekranı giriş düğmesi erişmesine izin vermek için.  |
| Sanal giriş düğmesi türü | dize | swipe_up | Kullanım **swipe_up** erişim giriş düğmesi ile bir çekme hareketi'kurmak için. Kullanım **float** , ekranın son kullanıcı tarafından taşınabilir bir Yapışkan, kalıcı giriş düğmesi erişmek için. |
| Pil ve sinyal gücü gösterge çubuğu | bool | Doğru  | Bu ayar dönüştürmeye `True` pil ve sinyal gücü göstergesi çubuğunu gösterir. |
| Çıkış kilit görev modu parolası | dize |   | Sorun giderme için kilit görev modundan geçici olarak bırakmak için kullanılacak bir 4-6 basamaklı kodu girin. |
| Wi-Fi ayar Göster | bool | FALSE | Bu ayar dönüştürmeye `True` Aç veya kapat Wi-Fi veya farklı bir Wi-Fi ağlarına bağlanmak için son kullanıcı sağlar.  |
| Bluetooth ayarı Göster | bool | FALSE | Bu ayar dönüştürmeye `True` Bluetooth açıp kapatabilir ve bağlanmak için farklı Bluetooth özellikli cihazlar için son kullanıcı sağlar.   |

## <a name="enter-json-data"></a>JSON verilerini gir

Giriş ekranı yönetilen tüm kullanılabilir ayarları yanı sıra, devre dışı bırakılmış ayarlarını yapılandırmak için JSON verilerini gir **yapılandırma Tasarımcısı**.

![Eklenen JSON verilerinin ekran görüntüsü](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Listelenen yapılandırılabilir ayarları listesi yanı sıra **yapılandırma Tasarımcısı** tablo (yukarıda), aşağıdaki tabloda, JSON verilerini yalnızca yapılandırabilirsiniz yapılandırma anahtarları sağlar.

|    Yapılandırma anahtarı    |    Değer türü    |    Varsayılan değer    |    Açıklama    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    İzin ver-listelenen uygulamaları ayarlama    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Görünür uygulamalar kümesi için giriş ekranınızdaki cihazda yüklü uygulamalar arasında tanımlamanızı sağlar. Görünür hale getirmek istediğiniz uygulamaları, uygulama paketi adı girerek uygulamaları tanımlayabilirsiniz, örneğin, com.android.settings ayarları erişilebilir giriş ekranında hale getirir. Uygulamalar bu, izin verilenler listesi bu bölümdeki zaten giriş ekranında görünür için cihazda yüklü.    |
|    Sabitlenmiş kümesi web bağlantıları    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    PIN Web sitelerine hızlı başlatma simgeler ana ekran olarak sağlar. Bu yapılandırma ile URL tanımlayabilir ve tek bir dokunuşla tarayıcıda başlatmak son kullanıcı için giriş ekranına ekleyin.    |
|    Uygulamaları gruplandırmak için yönetilen bir klasör oluşturun    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Oluşturma ve klasörleri ve bu klasörlerin içinde uygulama grubu adı sağlar. Son kullanıcılar klasörleri taşıma, klasörleri yeniden adlandırma veya klasörler uygulamaları taşımak mümkün olmayacaktır.   Klasörleri oluşturduğunuz sırada görünür ve uygulamaları klasörlerdeki alfabetik olarak görünür.         Not: klasörler halinde gruplandırmak istediğiniz tüm uygulamaları atanmalarının gerekli olduğu gibi aygıta gerekli ve yönetilen giriş ekranına eklenmesi gerekir.     |

JSON betiği dahil tüm kullanılabilir yapılandırma anahtarlara sahip bir örnek verilmiştir:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "grid_size",
            "valueString": "Auto"
        },
        {
            "key": "keep_page_header",
            "valueBool": true
        },
        {
            "key": "keep_status_bar",
            "valueBool": true
        },
        {
            "key": "show_notification_badge",
            "valueBool": false
        },
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "gesture_on",
            "valueBool": false
        },
        {
            "key": "vertical_scrolling",
            "valueBool": false
        },
        {
            "key": "theme",
            "valueString": "Theme.Light.Blue"
        },
        {
            "key": "dock_enable",
            "valueBool": false
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "feed_enable",
            "valueBool": false
        },
        {
            "key": "allow_overview_mode",
            "valueBool": false
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "search_bar",
            "valueBool": false
        },
        {
            "key": "hide_settings",
            "valueBool": false
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}

```
## <a name="next-steps"></a>Sonraki adımlar

- Android Kurumsal adanmış cihazlar hakkında daha fazla bilgi için bkz. [ayrılmış Android kuruluş cihazlarının Intune kaydını ayarlama](android-kiosk-enroll.md).
