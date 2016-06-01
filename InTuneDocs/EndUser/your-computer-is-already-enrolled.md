---
# required metadata

title: Bilgisayarınız zaten kayıtlı | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Bilgisayarınız zaten kayıtlı
Intune istemci yazılımı için Kurulum'u çalıştırdığınız için bu sayfayı görüyorsunuz. Ancak, yazılım bilgisayarınızda zaten yüklü ve Kurulum devam edemiyor.

Bunun nedeni şunlardan biri olabilir:

-   İstemci yazılımı daha önce yüklenmiştir ve Kurulum tekrar çalıştırılmıştır.

-   Kurulum, bir BT yöneticisi cihazınızı Intune’da devre dışı bıraktıktan sonra çalıştırılmıştır. Cihazınız kullanımdan kaldırıldıktan sonra istemci yazılımının bilgisayarınızdan kaldırılması birkaç saat sürebilir.

-   Kurulum, kısa bir süre önce gerçekleşen başarısız bir yükleme algılamıştır veya istemci yazılımı kaldıramamıştır.

## Kurulum bilgisayarınıza ne yükler
Kurulum, Intune istemcisini yükler. Kurulum tamamlandıktan sonra, istemci yazılımı arka planda çalışmaya devam ederek bilgisayarınızı Intune’la kullanım için yapılandırır. Bu işlemin tamamlanması biraz zaman alabilir ve şunları içerir:

-   Bilgisayarınızı Intune’a kaydetme

-   Bilgisayar donanımı ve yüklü yazılımlar hakkında envanter gönderme

-   Endpoint Protection'ın yüklenmesi (yapılandırıldıysa) de dahil olmak üzere Intune ilkesini yapılandırma

-   Intune Center’ı yükleme

Intune Center yüklendikten sonra, bunu kullanarak şirket portalına erişebilir ve burada bilgisayarınızı iş hesabınıza bağlayabilirsiniz.

## Microsoft Intune Center
Intune Center, istemci yazılımı başarıyla yüklendikten sonra bilgisayarınızda bir uygulama olarak yüklenir ve bilgisayarınızı Intune’a kaydeder. Intune Center’ı kullanarak şunları yapabilirsiniz:

-   **Şirket portalından uygulamalara erişme** - BT yöneticiniz tarafından dağıtılan uygulamaları bulun ve yükleyin. Şirket portalına yeni kaydedilen bir bilgisayarda ilk kez oturum açtığınızda, iş hesabınızı bu bilgisayara bağlama seçeneğine sahip olursunuz.

-   **Yazılım güncelleştirmelerini denetleme** – Intune yöneticiniz tarafından dağıtılan yazılım güncelleştirmelerini bulun.

-   **Bilgisayarınızın bir Endpoint Protection taramasını başlatma** – Bilgisayarınızda kötü amaçlı yazılım taraması başlatabilirsiniz.

-   **Uzaktan yardım isteme** – Bu seçenek, yalnızca, bilgisayarınızın işletim sistemi uzaktan yardımı destekliyorsa kullanılabilir.

## İstemci yazılımının yüklü veya kaldırılmış olduğunu doğrulama
**İstemci yüklü olduğunu doğrulama:**
Intune istemci yüklemesi, aşağıdaki uygulamalar bilgisayarda kullanılabilir hale geldiğinde tamamlanır:

-   **Intune Center**

-   **Intune Endpoint Protection** (BT yöneticiniz tarafından Endpoint Protection etkinleştirildiyse)

Görev Yöneticisi'ni rahatça kullanabiliyorsanız, çalışıyor olması gereken Intune istemci hizmetini arayabilirsiniz:

-   **OmcSvc**

**İstemcinin kaldırıldığını doğrulama:**
Intune istemcisi bir bilgisayardan kaldırıldıktan sonra, Intune Center da dahil olmak üzere istemci yüklenirken yüklenen uygulamalar kaldırılır.

Intune istemci hizmeti **OmcSvc** kaldırılır.

## İstemci yazılımı bilgisayardan kaldırma
Varsayılan olarak, BT yöneticiniz bilgisayarınızı Intune yönetim konsolundan kaldırdıktan sonra, Intune istemci yazılımı kaldırılır.

Intune istemci yazılımını bir bilgisayardan el ile kaldırmak için, kaldırmayı zorlamak üzere aşağıdaki adımları kullanabilirsiniz:

1.  Bilgisayarı açın, yönetici modunda bir komut istemi açın.

2.  **%programfiles%\Microsoft\OnlineManagement\Common** klasörüne gidin.

3.  Şu komutu çalıştırın: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

Bu, istemci yazılımın kaldırılmasını zamanlar.



<!--HONumber=May16_HO1-->


