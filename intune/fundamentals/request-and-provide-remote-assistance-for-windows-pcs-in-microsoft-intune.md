---
title: Windows bilgisayarlar için uzaktan yardım isteme ve sağlama
titleSuffix: Microsoft Intune
description: Bilgisayar olarak yönetilen Windows masaüstü cihazlarına uzaktan yardım için gereken son kullanıcı ve BT yöneticisi adımlarını ve bir bilgisayarı uzaktan başlatma adımlarını açıklar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26df7250aefa519c20708879b68af7c35113814f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509868"
---
# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a>Windows bilgisayarlar için uzaktan yardım isteme ve sağlama

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Bu konudaki bilgiler, yalnızca Intune yazılım istemcisini kullanarak bilgisayar olarak yönettiğiniz Windows masaüstü cihazlar için geçerlidir.

Intune, yazılım istemcisini çalıştıran kullanıcılarınıza uzaktan yardım vermenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Kullanıcı Microsoft Intune Center’dan yardım isteğinde bulunduğunda, bu durum bir uyarıyla size bildirilir; siz bu isteği kabul edebilir ve yardım sağlarsınız. Bu işlevsellik, Intune’da var olan Windows Uzaktan Yardım işlevselliğinin yerini alır.


## <a name="before-you-start"></a>Başlamadan önce

Uzaktan yardım isteklerine hazırlanmaya ve bu istekleri yanıtlamaya başlayabilmeniz için önce aşağıdaki önkoşulların karşılandığından emin olun:

- TeamViewer web sitesinde oturum açmak için [bir TeamViewer hesabına kaydolmuş](https://login.teamviewer.com/LogOn#register) olmanız gerekir.
- Yönetmek istediğiniz Windows bilgisayarların [Windows yazılım istemcisiyle yönetiliyor](../manage-windows-pcs-with-microsoft-intune.md) olması gerekir
- Intune tarafından desteklenen tüm Windows bilgisayarı işletim sistemleri yönetilebilir.

## <a name="configure-the-teamviewer-connector"></a>TeamViewer Bağlayıcısı'nı yapılandırma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetici**’yi seçin.
2. **Yönetici** çalışma alanında **TeamViewer**’ı seçin.
3. **TeamViewer** sayfasındaki **TeamViewer Bağlayıcısı**’nın altında **Etkinleştir**’i seçin.
4. **TeamViewer’ı Etkinleştir** iletişim kutusunda lisans koşullarını görüntüleyin ve **Kabul Et**’i seçin. Zaten bir TeamViewer lisansınız yoksa, **TeamViewer lisansı satın alın** öğesini seçin.
5. TeamViewer tarayıcı penceresi açıldıktan sonra, TeamViewer kimlik bilgilerinizle sitede oturum açın.
6. TeamViewer sitesinde, Intune’un TeamViewer’a bağlanmasına izin verme seçeneklerini okuyun ve sonra da kabul edin.
7. Intune konsolunda, **TeamViewer Bağlayıcısı** öğesinin **Etkin** durumda gösterildiğinden emin olun.


## <a name="open-a-remote-assistance-request-end-user"></a>Uzaktan yardım isteği açma (son kullanıcı)

1. İstemci Windows bilgisayarında **Microsoft Intune Center**’ı açın.
2. **Uzaktan Yardım**’ın altında **Uzaktan Yardım İste**’yi seçin.
3. Siz isteği onayladıktan sonra (aşağıya bakın), istemcide TeamViewer açılır. Kullanıcı, web tarayıcısının TeamViewer uygulamasını açmaya çalıştığını bildiren tüm iletileri kabul etmelidir.
4. Kullanıcı, bilgisayarını denetleyip denetleyemeyeceğinizi soran bir ileti görür. Devam etmek için bu iletiyi kabul etmesi gerekir.
5. Uzaktan yardım oturumu boyunca, kullanıcı sizin bağlı olduğunuzu gösteren bir pencere görür. Bu pencereyi kapatırsa, uzak oturum sona erer.

## <a name="respond-to-a-remote-assistance-request"></a>Uzaktan yardım isteğini yanıtlama

1. Kullanıcı bir uzaktan yardım isteği gönderdiğinde, bu isteği **Uyarılar** çalışma alanındaki **İzleme** > **Uzaktan Yardım**’ın altında görebilirsiniz. Örneğin:
   > ![Uzaktan yardım isteğinin ekran görüntüsü](./media/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune/team-viewer.png)

<br>İstek 4 saatten uzun süre yanıtlanmadan kalırsa, kaldırılır.
2. İsteği kabul etmek için, **İsteği onaylayın ve Uzaktan Yardım’ı başlatın** öğesini seçin.
3. **Yeni Bir Uzaktan Yardım İsteği Bekliyor** iletişim kutusunda **Uzaktan yardım isteğini kabul et**’i seçin. Zaten yüklü değilse TeamViewer tüm gerekli uygulamaları bilgisayarınıza yükler.
4. Ardından TeamViewer, bilgisayarının denetimini almak istediğinizi son kullanıcıya bildirir. Kullanıcı isteği kabul ettikten sonra, TeamViewer penceresi açılır ve bilgisayarın denetimini alabilirsiniz.

Uzaktan yardım oturumu sırasında, uzak bilgisayarı denetlemek için tüm sağlanan TeamViewer komutlarını kullanabilirsiniz. Bu komutlar hakkında yardım için, TeamViewer web sitesinden [Uzaktan kontrol kılavuzu](http://www.teamviewer.com/en/support/documents/)’nu indirin.

## <a name="close-the-remote-assistance-session"></a>Uzaktan yardım oturumunu kapatma

**TeamViewer** penceresinin **Eylemler** penceresinde **Oturumu Sonlandır**’ı seçin.

## <a name="remotely-restart-a-windows-pc"></a>Windows bilgisayarını uzaktan yeniden başlatma
Kullanıcıların sorunlarına yardımcı olurken, bilgisayarlarını ara sıra uzaktan yeniden başlatmanız gerekebilir. Bir Windows bilgisayarı uzaktan yeniden başlatmak için aşağıdaki adımları kullanın.

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya yeniden başlatmak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2. Bir veya birden çok bilgisayar seçin ve ardından **Uzak Görevler** &gt; **Bilgisayarı Yeniden Başlat**’ı seçin.

3. Görev durumunu görüntülemek için, sayfanın sağ alt köşesinde **Uzak Görevler**'i seçin.

4. **Görev Durumu** iletişim kutusunda, geçerli uzak görevler, görev durumu, cihaz adı ve bildirilen hataları gözden geçirin.

## <a name="see-also"></a>Ayrıca bkz:

[Intune yazılım istemcisi ile genel Windows bilgisayar yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
