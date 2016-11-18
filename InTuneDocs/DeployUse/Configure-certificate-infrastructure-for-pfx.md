---
title: "PFX için sertifika altyapısını yapılandırma |Microsoft Intune|"
description: ".PFX sertifika profillerini oluşturun ve dağıtın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7d1f37a2ba2e634fb75058d33eaaccf3aa5845b0
ms.openlocfilehash: 8fc1cc718fd0edae8b8ec4a0a8dc25487eafda2b



---
# <a name="configure-certificate-infrastructure"></a>Sertifika altyapısını yapılandırma
Bu konu başlığı altında, .PFX sertifika profillerini oluşturmak ve dağıtmak için nelere ihtiyacınız olduğu açıklanır.

Kuruluşunuzda sertifika tabanlı kimlik doğrulamaları yapmak için, bir Kuruluş Sertifika Yetkiliniz olmalıdır.

Kuruluş Sertifika Yetkilisine ek olarak .PFX Sertifika profillerini de kullanmak için, aşağıdakiler gerekir:

-   Sertifika Yetkilisi ile iletişim kurabilen bir bilgisayarı veya Sertifika Yetkilisi bilgisayarını kullanabilirsiniz.

-  Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalışan Intune Sertifika Bağlayıcısı.

## <a name="onpremises-infrastructure-description"></a>Şirket içi altyapı açıklaması


-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi**: Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

-  **Sertifika Yetkilisiyle iletişim kurabilen bilgisayar**: Alternatif olarak, Sertifika Yetkisi bilgisayarının kendisini kullanın.
-  **Microsoft Intune Sertifika Bağlayıcısı**: **Sertifika Bağlayıcısı** yükleyicisini (**ndesconnectorssetup.exe**) indirmek için Intune yönetim konsolunu kullanırsınız. Ardından, Sertifika Bağlayıcısı'nı yüklemek istediğiniz bilgisayarda **ndesconnectorssetup.exe** dosyasını çalıştırabilirsiniz. .PFX Sertifika profilleri için, Sertifika Bağlayıcısı’nı Sertifika Yetkilisi ile iletişim kurabilen bilgisayara yükleyin.
-  **Web Uygulaması Proxy sunucusu** (isteğe bağlı): Web Uygulaması Proxy (WAP) sunucusu olarak Windows Server 2012 R2 veya üzerini çalıştıran bir sunucu kullanabilirsiniz. Bu yapılandırma:
    -  Cihazların bir İnternet bağlantısını kullanarak sertifikaları almasını sağlar.
    -  Cihazlar sertifikaları almak ve yenilemek için İnternet üzerinden bağlanıyorsa güvenlik açısından önerilir.

 > [!NOTE]           
> -    WAP'ı barındıran sunucu, Ağ Cihazı Kayıt Hizmeti (NDES) tarafından kullanılan uzun URL'ler için destek sağlayan [bir güncelleştirmeyi yüklemelidir](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx). Bu güncelleştirmeyi [Aralık 2014 güncelleştirme paketi](http://support.microsoft.com/kb/3013769)ile birlikte veya [KB3011135](http://support.microsoft.com/kb/3011135)güncelleştirmesinden tek başına edinebilirsiniz.
>-  Ayrıca, WAP’yi barındıran sunucuda, dış istemcilere yayımlanan adla eşleşen bir SSL sertifikası olmalı ve NDES sunucusunda kullanılan SSL sertifikasına güvenilmelidir. Bu sertifikalar, WAP sunucusunun istemcilerden gelen SSL bağlantıyı sonlandırmasına ve NDES sunucusuna yeni bir SSL bağlantı oluşturmasına imkan sağlar.
    WAP sertifikaları hakkında bilgi için, [Web Uygulaması Ara Sunucusu Kullanarak Uygulama Yayınlamayı Planlama](https://technet.microsoft.com/library/dn383650.aspx) konusunun **Sertifikaları planlama** bölümüne bakın. WAP sunucuları hakkında genel bilgi için bkz. [Web Uygulaması Ara Sunucusu ile çalışma](http://technet.microsoft.com/library/dn584113.aspx).|


### <a name="certificates-and-templates"></a>Sertifikalar ve Şablonlar

|Nesne|Ayrıntılar|
|----------|-----------|
|**Sertifika Şablonu**|Bu şablonu sertifika veren CA'nız üzerinde yapılandırabilirsiniz.|
|**Güvenilen Kök CA sertifika**|Bunu sertifika veren CA'dan veya ona güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara dağıtabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|


## <a name="configure-your-infrastructure"></a>Altyapınızı yapılandırın
Sertifika profillerini yapılandırabilmeniz için önce aşağıdaki görevleri tamamlamanız gerekir. Bu görevler, Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektirir:

- **Görev 1** - Sertifika yetkilisinde sertifika şablonları yapılandırma.
- **Görev 2** - Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma.

### <a name="task-1-configure-certificate-templates-on-the-certification-authority"></a>Görev 1 - Sertifika yetkilisinde sertifika şablonları yapılandırma
Bu görevde, sertifika şablonunu yayımlayacaksınız.

##### <a name="to-configure-the-certification-authority"></a>Sertifika yetkilisini yapılandırmak için

1.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak .PFX ile kullanılmak üzere yeni bir özel şablon oluşturun veya var olan bir şablonu (Kullanıcı şablonu gibi) kopyalayın ve düzenleyin.

    Şablon şunları içermelidir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. 

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT]
        > iOS ve Mac OS X sertifika şablonlarında, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** seçeneğinin işaretli olmadığından emin olun.

2.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT]
    > iOS ve Mac OS X platformları, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

    CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için CA'da aşağıdaki komutları çalıştırın:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.

    a.  **Sertifika Şablonları** düğümünü seçin, **Eylem**-&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

    b.  Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.

4.  CA bilgisayarında, Intune Sertifika Bağlayıcısı’nı barındıran bilgisayarın, .PFX profili oluşturulurken kullanılan şablona erişebilmesi için kayıt izni olduğundan emin olun. CA bilgisayarı özelliklerindeki **Güvenlik** sekmesinde bu izni ayarlayın.

### <a name="task-2-enable-install-and-configure-the-intune-certificate-connector"></a>Görev 2 - Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma
Bu görevde şunları yapacaksınız:

Sertifika Bağlayıcısı'nı indirme, yükleme ve yapılandırma.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Sertifika Bağlayıcısı desteğini etkinleştirmek için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın ve **Yönetim** &gt; **Sertifika Bağlayıcısı**’nı seçin.

2.  **Şirket İçi Sertifika Bağlayıcısı’nı Yapılandır**'ı seçin.

3.  **Sertifika Bağlayıcısı'nı Etkinleştir**'i ve ardından **Tamam**'ı seçin.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Sertifika Bağlayıcısı'nı indirmek, yüklemek ve yapılandırmak için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın ve ardından **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Sertifika Bağlayıcısı** &gt; **Sertifika Bağlayıcısı’nı İndir**’i seçin.

2.  Yükleme tamamlandıktan sonra, indirilen yükleyiciyi (**ndesconnectorssetup.exe**) çalıştırın.

  Yükleyiciyi, Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalıştırın. .PFX Dağıtımı seçeneğini belirtin, sonra **Yükle**’ye tıklayın. Yükleme tamamlandığında, [Sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konusunda açıklandığı gibi bir sertifika profili oluşturarak devam edin.

   <!-- Not sure about step 3 below -->

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç**'i belirleyip, Görev 3'te yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri**'yi seçin. Sonra **İleri**’yi ve ardından **Yükle**’yi seçin.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP]
    > Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    a. **Oturum Aç**'ı seçin ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

    b. **Gelişmiş** sekmesini seçin ve ardından Sertifika Yetkiliniz’de **Sertifikaları Yayımla ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın.

    c. **Uygula**'yı seçin.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açın ve **services.msc** yazın. **Enter** tuşuna basın, **Intune Bağlayıcısı Hizmeti**’ne sağ tıklayın ve **Yeniden Başlat**’ı seçin.


### <a name="next-steps"></a>Sonraki adımlar
Artık sertifika profillerinizi, [Sertifika profillerini yapılandırma](Configure-Intune-certificate-profiles.md) konusunda anlatıldığı şekilde yapılandırmaya hazırsınız.



<!--HONumber=Nov16_HO3-->


