---
title: "Bilgisayar istemci yazılımını yükleme | Microsoft Intune"
description: "Windows bilgisayarlarınızın Microsoft Intune istemci yazılımıyla yönetilmesini sağlamanıza yardımcı olması için bu kılavuzu kullanın."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 13fa09a2b029818467062a5c589292c5f0bd0a58


---

# Windows bilgisayarlara Intune yazılım istemcisini yükleme
Windows bilgisayarlar Intune istemci yazılımı yüklenerek kaydedilebilir. Intune istemci yazılımı aşağıdaki yollar kullanılarak yüklenebilir:

- El ile yükleme
- Grup ilkesi kullanarak yükleme
- Disk görüntüsüne dahil etme
- Kullanıcıların yüklemesi

## Intune istemci yazılımını indirme

Intune istemci yazılımını kullanıcıların kendilerinin yüklemesi dışındaki tüm yöntemler, dağıtılabilmesi için yazılımı indirmenizi gerektirir.

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** &gt; **İstemci Yazılımını İndir**’e tıklayın

  ![Intune bilgisayar istemcisini indirme](../media/pc-sa-client-download.png)

2.  **İstemci Yazılımını İndir** sayfasında, **İstemci Yazılımını İndir**'e tıklayın ve yazılımı içeren **Microsoft_Intune_Setup.zip** paketini ağınızda güvenli bir konuma kaydedin.

    > [!NOTE]
    > Intune istemci yazılımı yükleme paketi, hesabınız hakkında bilgiler içerir. Yetkisiz kullanıcılar yükleme paketini erişirse, bu kişiler, katıştırılmış sertifikası tarafından temsil edilen hesaba kendi bilgisayarını kaydedebilir.

3.  Yükleme paketinin içeriğini ağınızda güvenli bir konuma ayıklayın.

    > [!IMPORTANT]
    > Ayıklanan **ACCOUNTCERT** dosyasını yeniden adlandırmayın veya kaldırmayın, aksi takdirde istemci yazılımının yüklenmesi başarısız olur.

## El ile dağıtma

1.  Bir bilgisayarda, istemci yazılımı yükleme dosyalarının bulunduğu klasöre göz atın ve ardından, istemci yazılımını yüklemek için **Microsoft_Intune_Setup.exe**'yi çalıştırın.

    > [!NOTE]
    > İstemci bilgisayarın görev çubuğundaki simgenin üzerine geldiğinizde yükleme durumu görüntülenir.

## Grup İlkesi kullanarak dağıtma

1.  **Microsoft_Intune_Setup.exe** ve **MicrosoftIntune.accountcert** dosyalarını içeren klasörde, 32 bit ve 64 bit bilgisayarlar için Windows Installer tabanlı yükleme programlarını ayıklamak için aşağıdaki komutu çalıştırın:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  **Microsoft_Intune_x86.msi** dosyasını, **Microsoft_Intune_x64.msi** dosyasını ve **MicrosoftIntune.accountcert** dosyasını, istemci yazılımın yükleneceği tüm bilgisayarlar tarafından erişilebilen bir ağ konumuna kopyalayın.

    > [!IMPORTANT]
    > Dosyaları ayırmayın veya yeniden adlandırmayın, aksi takdirde yazılım yüklemesi başarısız olur.

3.  Yazılımı ağınızdaki bilgisayarlara dağıtmak için Grup İlkesi'ni kullanın.

    Otomatik olarak yazılım dağıtmak için Grup İlkesi'ni kullanma hakkında daha fazla bilgi için Windows Server belgelerinize bakın.

## Bir görüntünün parçası olarak yükleme
Aşağıdaki örnek yordamı temel olarak kullanabilir ve Intune istemci yazılımını bir işletim sistemi görüntüsünün parçası olarak bilgisayarlara dağıtabilirsiniz:

1.  İstemci yükleme dosyaları **Microsoft_Intune_Setup.exe** ve **MicrosoftIntune.accountcert**'i başvuru bilgisayarındaki **%Systemdrive%\Temp\Microsoft_Intune_Setup** klasörüne kopyalayın.

2.   **SetupComplete.cmd** betiğine aşağıdaki komutu ekleyerek **WindowsIntuneEnrollPending** kayıt defteri girişini oluşturun:

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  /PrepareEnroll komut satırı bağımsız değişkeniyle kayıt paketini çalıştırmak için **setupcomplete.cmd**’ye aşağıdaki komutu ekleyin:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    >  **SetupComplete.cmd** betiği, bir kullanıcı oturum açmadan önce Windows Kur'un sistemde değişiklikler yapmasını sağlar. **/PrepareEnroll** komut satırı bağımsız değişkeni, Windows Kurulumu tamamlandıktan sonra, hedeflenen bir bilgisayarı Intune hizmetine otomatik olarak kaydolmaya hazırlar.

4.  **SetupComplete.cmd**'yi başvuru bilgisayarındaki **%Windir%\Setup\Scripts** klasörüne koyun.

5.  Başvuru bilgisayarının bir görüntüsünü yakalayın ve bu görüntüyü hedef bilgisayarlara dağıtın.

Windows Kur tamamlandıktan sonra hedef bilgisayar yeniden başlatıldığında, **WindowsIntuneEnrollPending** kayıt defteri anahtarı oluşturulur. Kayıt paketi, bilgisayarın kayıtlı olup olmadığını denetler. Bilgisayar kayıtlıysa, başka eyleme gerek yoktur. Bilgisayar kayıtlı değilse, kayıt paketi bir Microsoft Intune Otomatik Kayıt Görevi oluşturur.

Otomatik kayıt görevi bir sonraki zamanlanan saatte çalıştığında, **WindowsIntuneEnrollPending** kayıt defteri değerinin var olup olmadığını denetler ve hedeflenen bilgisayarı Intune’a kaydetmeye çalışır. Kayıt herhangi bir nedenden dolayı başarısız olursa, görev bir daha çalıştığında kayıt yeniden denenir. Yeniden deneme işlemleri bir ay boyunca devam eder.

Kayıt başarılı olduğunda veya bir ay sonra, Intune Otomatik Kayıt Görevi, **WindowsIntuneEnrollPending** kayıt defteri değeri ve hesap sertifikası hedeflenen bilgisayardan silinir.

## Kullanıcıdan kendi kendine kaydolmasını isteme

Kullanıcılar Intune istemci yazılımını [http://portal.manage.microsoft.com](http://portal..manage.microsoft.com) adresine giderek yükleyebilir. Web portalı cihazın bir Windows bilgisayar olduğunu algılayabiliyorsa, bilgisayarın Intune yazılım istemcisi indirilerek kaydedilmesi istenir. İndirildikten sonra kullanıcılar, bilgisayarlarını yönetime almak için yazılımı yükleyebilir.

![Intune Portalı’nın Intune yazılım istemcisinin indirilmesini istemesi](../media/software-client-download.png)

## Başarılı istemci dağıtımını izleme ve doğrulama
Başarılı istemci dağıtımını izlemenize ve doğrulamanıza yardımcı olması için aşağıdaki yordamlardan birini kullanın.

### Microsoft Intune yönetici konsolundan istemci yazılımının yüklendiğini doğrulamak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Bilgisayarlar**’a tıklayın.

2.  Intune’la iletişim kuran yönetilen bilgisayarları bulmak için bilgisayar listesini aşağı kaydırın veya **Cihazlarda ara** kutusuna bilgisayar adının tamamını ya da bir kısmını yazarak belirli bir yönetilen bilgisayarı arayın.

3.  Konsolun alt bölmesinden bilgisayarının durumunu inceleyin ve varsa hataları çözümleyin.

### Tüm kayıtlı bilgisayarları görüntülemek üzere bir bilgisayar envanteri raporu oluşturmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Raporlar** &gt; **Bilgisayar Envanteri Raporları**’na tıklayın.

2.   **Yeni Rapor Oluştur** sayfasında, tüm alanları varsayılan değerleriyle bırakın (filtre uygulamak istemediğiniz sürece) ve **Raporu Görüntüle**'ye tıklayın.

3.  **Bilgisayar Envanteri Raporu** sayfası, Intune’a başarılı bir şekilde kaydedilen tüm bilgisayarların görüntülendiği yeni bir pencerede açılır.

    > [!TIP]
    > Raporu herhangi bir sütunun içeriğine göre sıralamak için sütun başlığına tıklayın.


### Ayrıca Bkz.
[Microsoft Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md)
[İstemci kurulumu sorunlarını giderme](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)



<!--HONumber=Sep16_HO4-->


