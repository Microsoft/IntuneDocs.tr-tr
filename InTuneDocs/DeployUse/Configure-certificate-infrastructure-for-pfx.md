---
title: "PFX için sertifika altyapısını yapılandırma |Microsoft Intune|"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 05/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6edb37708d26033358af30c47e955b20caedb6fd
ms.openlocfilehash: 51def9dc80043bbf5a71578fb44cae9259fd48b1



---
# Sertifika altyapısını yapılandırma
Bu konu başlığı altında, sertifika profillerini oluşturmak ve dağıtmak için nelere ihtiyacınız olduğu açıklanır.

Kuruluşunuzda sertifika tabanlı kimlik doğrulamaları yapmak için, bir Kuruluş Sertifika Yetkiliniz olmalıdır.

Kuruluş Sertifika Yetkilisine ek olarak .PFX Sertifika profillerini de kullanmak için, aşağıdakiler gerekir:

-   Sertifika Yetkilisi ile iletişim kurabilen bir bilgisayarı veya Sertifika Yetkilisi bilgisayarını kullanabilirsiniz.

 -  Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalışan Intune Sertifika Bağlayıcısı.

## Şirket içi altyapı açıklaması


-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi** (CA): Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

 -  **Sertifika Yetkilisiyle iletişim kurabilen bilgisayar**: Alternatif olarak, Sertifika Yetkisi bilgisayarının kendisini kullanın.
-  **Microsoft Intune Sertifika Bağlayıcısı**: **Sertifika Bağlayıcısı** yükleyicisini (**ndesconnectorssetup.exe**) indirmek için Intune yönetim konsolunu kullanırsınız. Ardından, Sertifika Bağlayıcısı'nı yüklemek istediğiniz bilgisayarda **ndesconnectorssetup.exe** dosyasını çalıştırabilirsiniz. .PFX Sertifika profilleri için, Sertifika Bağlayıcısı’nı Sertifika Yetkilisi ile iletişim kurabilen bilgisayara yükleyin.
-  **Web Uygulaması Ara Sunucusu** (isteğe bağlı): Web Uygulaması Ara Sunucusu (WAP) olarak Windows Server 2012 R2 veya üstünü çalıştıran bir sunucu kullanabilirsiniz. Bu yapılandırma:
    -  Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
    -  Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.

 > [!NOTE]           
> -    WAP'ı barındıran sunucular, Ağ Cihazı Kayıt Hizmeti tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) . Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](http://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](http://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
>-  Ayrıca, WAP’yi barındıran sunucuda, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.
    WAP sertifikaları hakkında bilgi için, [Web Uygulaması Ara Sunucusu Kullanarak Uygulama Yayınlamayı Planlama](https://technet.microsoft.com/library/dn383650.aspx) konusunun **Sertifikaları planlama** bölümüne bakın. WAP sunucuları hakkında genel bilgi için bkz. [Web Uygulaması Ara Sunucusu ile çalışma](http://technet.microsoft.com/library/dn584113.aspx).|


### Sertifikalar ve Şablonlar

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırabilirsiniz.|
|**Güvenilen Kök CA sertifika**|Bunu sertifika veren CA'dan veya ona güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara dağıtabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|


## Altyapınızı yapılandırın
Sertifika profillerini yapılandırmadan önce Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektiren aşağıdaki görevleri tamamlamanız gerekir:

**Görev 1** - Sertifika yetkilisinde sertifika şablonlarını yapılandırma **Görev 2** - Intune Sertifika Bağlayıcısı’nı etkinleştirme, yükleme ve yapılandırma

### Görev 1 - Sertifika yetkilisinde sertifika şablonları yapılandırma
Bu görevde, sertifika şablonunu yayımlayacaksınız

##### Sertifika yetkilisini yapılandırmak için

1.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak yeni bir özel şablon oluşturun veya var olan bir şablonu kopyalayın ve ardından, var olan şablonu (Kullanıcı şablonu gibi) .PFX ile kullanılmak üzere düzenleyin.

    Şablonun aşağıdaki yapılandırmalara sahip olması gerekir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT]
        > iOS ve Mac OS X sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.


3.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT]
    > iOS ve Mac OS X platformları, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

    CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için CA'da aşağıdaki komutları çalıştırın:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.

    1.  **Sertifika Şablonları** düğümünü seçin, **Eylem**--&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

    2.  Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.

5.  CA bilgisayarında, Intune Sertifika Bağlayıcısı’nı barındıran bilgisayarın .PFX profilini oluştururken kullanılan şablona erişebilmesi için kayıt izni olduğundan emin olun. CA bilgisayarı özelliklerindeki **Güvenlik** sekmesinde bu izni ayarlayın.

### Görev 2 - Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma
Bu görevde şunları yapacaksınız:

Sertifika Bağlayıcısı'nı indirme, yüklemek- ve yapılandırma

##### Sertifika Bağlayıcısı desteğini etkinleştirmek için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **Yönetim** &gt; **Sertifika Bağlayıcısı**’na tıklayın.

2.  **Şirket İçi Sertifika Bağlayıcısını Yapılandır**'a tıklayın.

3.  **Sertifika Bağlayıcısı'nı Etkinleştir**'i seçin ve ardından **Tamam**'a tıklayın.

##### Sertifika Bağlayıcısı'nı indirmek, yüklemek ve yapılandırmak için

1.  [Intune yönetim konsolunu açın](https://manage.microsoft.com) ve ardından **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Sertifika Bağlayıcısı** &gt; **Sertifika Bağlayıcısı’nı İndir**’e tıklayın.

2.  Yükleme tamamlandıktan sonra, indirilen yükleyiciyi (**ndesconnectorssetup.exe**) çalıştırın:

  Yükleyiciyi, Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalıştırın. .PFX Dağıtımı seçeneğini belirtin, sonra Yükle’ye tıklayın. Yükleme tamamlandığında, [Sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konusunda açıklandığı gibi bir sertifika profili oluşturarak devam edin.

   <!-- Not sure about step 3 below -->

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç**'e tıklayıp Görev 3'te yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri** 'ye tıklayın. Ardından **İleri**'ye ve **Yükle**'ye tıklayın.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    **Oturum Aç**'a tıklayın ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    **Gelişmiş** sekmesini seçin ve ardından, Sertifika Verme Yetkilisi'nde **Sertifika Ver ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın ve **Uygula**'ya tıklayın.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açıp **services.msc** yazın ve **Enter** tuşuna basın, sonra **Intune Bağlayıcı Hizmeti**'ne sağ tıklayın ve **Yeniden Başlat**'a tıklayın.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve bir **403** hatası döndürmesi gereken aşağıdaki URL'yi girin:

**http:// &lt;NDES_sunucunuzun_FQDN_değeri&gt;/certsrv/mscep/mscep.dll**

### Sonraki adımlar
Artık, [Sertifika profillerini yapılandırma](Configure-Intune-certificate-profiles.md) konusunda açıklandığı gibi sertifika profillerinizi yapılandırmaya hazırsınız.



<!--HONumber=Jun16_HO4-->


