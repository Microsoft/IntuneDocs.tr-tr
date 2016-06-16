---
# required metadata

title: Sertifika altyapısını yapılandırma | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Sertifika altyapısını yapılandırma
Bu konu başlığı altında, sertifika profillerini oluşturmak ve dağıtmak için nelere ihtiyacınız olduğu açıklanır.

Kuruluşunuzda sertifika tabanlı kimlik doğrulamaları yapmak için, bir Kuruluş Sertifika Yetkiliniz olmalıdır.

Kuruluş Sertifika Yetkilisine ek olarak SCEP sertifika profillerini de kullanmak için, aşağıdakiler gerekir:

-   Ağ Cihazı Kayıt Hizmeti çalıştıran bir sunucu

-   NDES’yi çalıştıran Windows Server 2012 R2 sunucusuna yüklenen Intune Sertifika Bağlayıcısı

Kuruluş Sertifika Yetkilisine ek olarak .PFX Sertifika profillerini de kullanmak için, aşağıdakiler gerekir:

-  Sertifika Yetkilisi ile iletişim kurabilen bir bilgisayarı veya Sertifika Yetkilisi bilgisayarını kullanın.

-  Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalışan Intune Sertifika Bağlayıcısı.

## Şirket içi altyapı


-    **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucular (Web Uygulaması Ara Sunucusu hariç), Active Directory etki alanınıza katılmalıdır.

-  **Sertifika Yetkilisi** (CA): Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. Bir Sertifika Yetkilisi'ni nasıl ayarlayacağınız hakkında bilgi edinmek için bkz. [Sertifika Yetkilisi'ni Yükleme](http://technet.microsoft.com/library/jj125375.aspx).
    CA'nız Windows Server 2008 R2 çalıştırıyorsa, [KB2483564 ile gelen düzeltmeyi yüklemeniz](http://support.microsoft.com/kb/2483564/)gerekir.

-  **NDES Sunucusu** (yalnızca SCEP): Windows Server 2012 R2 veya üstünü çalıştıran bir sunucuya Ağ Cihazı Kayıt Hizmeti’ni (NDES) kurmalısınız. Intune, Kuruluş CA ile aynı sunucuda çalıştırılan NDES’nin kullanımını desteklemez. Windows Server 2012 R2’yi Ağ Cihazı Kayıt Hizmeti’ni barındıracak şekilde yapılandırma yönergeleri için bkz. [Ağ Cihazı Kayıt Hizmeti Kılavuzu](http://technet.microsoft.com/library/hh831498.aspx).|
-  **Sertifika Yetkilisiyle iletişim kurabilen bilgisayar** (yalnızca .PFX): Alternatif olarak, Sertifika Yetkisi bilgisayarının kendisini kullanın.
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
|**İstemci kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu sertifikayı NDES Sunucusu'na yüklersiniz.|
|**Sunucu kimlik doğrulama sertifikası**|Sertifika veren CA'nızdan veya genel CA'dan istenen bu SSL sertifikasını NDES Sunucusu'ndaki IIS'de yüklersiniz ve bağlarsınız.|
|**Güvenilen Kök CA sertifika**|Bunu sertifika veren CA'dan veya ona güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarabilir ve Güvenilen CA sertifika profilini kullanarak cihazlara dağıtabilirsiniz.<br /><br />İşletim sistemi platformu başına tek bir Güvenilen Kök CA sertifika kullanırsınız ve bu sertifikayı oluşturduğunuz her Güvenilen Kök Sertifika profili ile ilişkilendirirsiniz.<br /><br />Gerektiğinde ek Güvenilen Kök CA sertifikaları kullanabilirsiniz. Örneğin, Wi-Fi erişim noktalarınız için sunucu kimlik doğrulama sertifikalarını imzalayan bir CA'ya güven sağlamak için bunu yapabilirsiniz.|

### Hesaplar

|Ad|Ayrıntılar|
|--------|-----------|
|**NDES hizmet hesabı**|NDES Hizmet Hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı belirtirsiniz.|

## Altyapınızı yapılandırın
Sertifika profillerini yapılandırmadan önce Windows Server 2012 R2 ve Active Directory Sertifika Hizmetleri (ADCS) bilgisi gerektiren aşağıdaki görevleri tamamlamanız gerekir:

**Görev 1** - Sertifika yetkilisinde sertifika şablonlarını yapılandırma

**Görev 2** (yalnızca SCEP profili için) - NDES sunucusunda önkoşulları yapılandırma

**Görev 3** (yalnızca SCEP profili için) - NDES’yi Intune’la kullanılacak şekilde yapılandırma

**Görev 4** - Intune Sertifika Bağlayıcısı'nı etkinleştirme, yükleme ve yapılandırma

## Görev 1 - Sertifika yetkilisinde sertifika şablonları yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES hizmet hesabı oluşturma

    > [!NOTE] Sertifikaları iptal etmek için, NDES hizmet hesabının sertifika profili tarafından kullanılan her sertifika şablonu üzerinde *Sertifikaları Yayımlama ve Yönetme* hakları olmalıdır.

-   NDES için bir sertifika şablonu yapılandırma

-   NDES için oluşturulan sertifika şablonunu yayımlama

##### Sertifika yetkilisini yapılandırmak için

1.  NDES hizmet hesabı olarak kullanılacak bir etki alanı kullanıcı hesabı oluşturun. NDES'i yükleyip yapılandırmadan önce sertifika veren CA üstünde şablonları yapılandırırken bu hesabı belirteceksiniz.

2.  Sertifika veren CA'da, Sertifika Şablonları ek bileşenini kullanarak yeni bir özel şablon oluşturun veya var olan bir şablonunu kopyalayın ve ardından, var olan bir şablonu (Kullanıcı şablonu gibi) NDES ile kullanılmak üzere düzenleyin.

    Şablonun aşağıdaki yapılandırmalara sahip olması gerekir:

    -   Şablon için kolay bir **Şablon görünen adı** belirtin.

    -   **Konu Adı** sekmesinde, **İstekte sağla**'yı seçin. (Güvenlik, NDES için Intune ilke modülü tarafından zorunlu tutulur).

    -   **Uzantılar** sekmesinde, **Uygulama İlkeleri Açıklaması** 'nın **İstemci Kimlik Doğrulaması**'nı içerdiğinden emin olun.

        > [!IMPORTANT] iOS ve Mac OS X sertifika şablonları için, **Uzantılar** sekmesinde **Anahtar Kullanımı**'nı düzenleyin ve **İmza kaynağın delilidir** öğesinin seçili olmadığından emin olun.

    -   **Güvenlik** sekmesinde, NDES hizmet hesabını ekleyin ve bu hesaba şablon üzerinde **Kaydetme** izinleri verin.

3.  Şablonun **Genel** sekmesindeki **Geçerlilik süresi** 'ni gözden geçirin. Varsayılan olarak, Intune şablonda yapılandırılan değeri kullanır. Ancak, CA'yı istekte bulunan kişinin farklı bir değer belirtmesine izin verecek şekilde yapılandırma seçeneğiniz vardır ve bu değeri Intune yönetim konsolundan ayarlayabilirsiniz. Her zaman şablondaki değeri kullanmak istiyorsanız, bu adımın geri kalanını atlayın.

    > [!IMPORTANT] iOS ve Mac OS X platformları, yaptığınız diğer yapılandırmalar ne olursa olsun, her zaman şablonda ayarlanan değeri kullanır.

    CA'yı istekte bulunan kişinin geçerlilik süresini belirlemesine izin verecek şekilde yapılandırmak için CA'da aşağıdaki komutları çalıştırın:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Sertifika veren CA'da, sertifika şablonunu yayımlamak için Sertifika Yetkilisi ek bileşenini kullanın.

    1.  **Sertifika Şablonları** düğümünü seçin, **Eylem**--&gt; **Yeni** &gt; **Verilecek Sertifika Şablonu** öğesine tıklayın ve ardından 2. adımda oluşturduğunuz şablonu seçin.

    2.  Şablonu **Sertifika Şablonları** klasöründe görüntüleyerek yayımlandığını doğrulayın.

5.  .PFX profilleri için: CA bilgisayarında, Intune Sertifika Bağlayıcısı’nın .PFX profilini oluştururken kullanılan şablona erişebilmesi için kayıt izni olduğundan emin olun. CA bilgisayarı özelliklerindeki **Güvenlik** sekmesinde bu izni ayarlayın.

## Görev 2 (yalnızca SCEP profili için): NDES sunucusunda önkoşulları yapılandırma
Bu görevde şunları yapacaksınız:

-   NDES'i bir Windows Server'a ekleyin ve IIS'yi NDES'i destekleyecek biçimde yapılandırın

-   NDES Hizmet hesabını IIS_IUSR grubuna ekleyin

-   NDES hizmet hesabı SPN'yi ayarlayın

##### NDES Sunucusu'na yönelik önkoşulları yapılandırmak için

1.  NDES'i barındıracak sunucuda bir **Kuruluş Yöneticisi**olarak oturum açmanız ve sonra NDES'i yüklemek için [Rol ve Özellik Ekle Sihirbazı](https://technet.microsoft.com/library/hh831809.aspx) 'nı kullanmanız gerekir:

    1.  Sihirbaz'da, AD CS Rol Hizmetleri'ne erişmek için **Active Directory Sertifika Hizmetleri** 'ni seçin. **Ağ Cihazı Kayıt Hizmeti**'ni seçin, **Sertifika Yetkilisi**'nin işaretini kaldırın ve ardından sihirbazı tamamlayın.

        > [!TIP]
        > Sihirbazın **Kurulum ilerleme durumu** sayfasında **Kapat**'a tıklamayın. Bunun yerine, **Hedef sunucuda Active Directory Sertifika Hizmetleri'ni Yapılandır**bağlantısına tıklayın. Bu, sonraki görev için kullanacağınız **AD CS Yapılandırma** sihirbazını açar. AD CS Yapılandırması açıldıktan sonra, Rol ve Özellik Ekle sihirbazını kapatabilirsiniz.

    2.  NDES sunucuya eklendiğinde, sihirbaz tarafından IIS de yüklenir. IIS'nin aşağıdaki yapılandırmalara sahip olduğundan emin olun:

        -   **Web Sunucusu** &gt; **Güvenlik** &gt; **İstek Filtreleme**

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 3.5**. ASP.NET 3.5'in yüklendiğinde .NET Framework 3.5 yüklenir. .NET Framework 3.5'i yüklerken, hem çekirdek **.NET Framework 3.5** özelliğini hem de **HTTP Etkinleştirmesi**'ni yükleyin.

        -   **Web Sunucusu** &gt; **Uygulama Geliştirme** &gt; **ASP.NET 4.5**. ASP.NET 4.5 yüklendiğinde, .NET Framework 4.5 yüklenir. .NET Framework 4.5'i yüklerken, çekirdek **.NET Framework 4.5** özelliğini, **ASP.NET 4.5**'i ve **WCF Hizmetleri** &gt; **HTTP Etkinleştirmesi** özelliğini yükleyin.

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 Metatabanı Uyumluluğu**

        -   **Yönetim Araçları** &gt; **IIS 6 Yönetim Uyumluluğu** &gt; **IIS 6 WMI Uyumluluğu**

2.  Sunucuda, NDES hizmet hesabını **IIS_IUSR** grubunun bir üyesi olarak ekleyin.

3.  NDES hizmet hesabının SPN'sini ayarlamak için şu komutu çalıştırın:

    -   **setspn -s http/&lt;NDES Sunucusunun DNS adı&gt; &lt;Etki alanı adı&gt;\&lt;NDES Hizmeti hesap adı&gt;**

    Örneğin, NDES Sunucunuzun adlı **Server01**, etki alanınız **Contoso.com**ve hizmet hesabını **NDESService**ise, şunu kullanın:

    -   **setspn –s http/Server01.contoso.com contoso\NDESService**

## Görev 3 (yalnızca SCEP profili için) - NDES’yi Intune’la kullanılacak şekilde yapılandırma 
Bu görevde şunları yapacaksınız:

-   NDES'i sertifika veren CA ile kullanmak için yapılandırma

-   IIS'de sunucu kimlik doğrulaması (SSL) sertifikasını bağlama

-   IIS'de İstek Filtrelemeyi Yapılandırma

##### NDES’yi Intune’la kullanılacak şekilde yapılandırmak için

1.  NDES Sunucusunda, AD CS Yapılandırma sihirbazını açın ve aşağıdaki yapılandırmaları yapın.

    > [!TIP]
    > Önceki görevde bulunan bağlantıya tıkladıysanız bu sihirbaz zaten açıktır. Aksi takdirde, Active Directory Sertifika Hizmetleri için dağıtım sonrası yapılandırmaya erişmek için Sunucu Yöneticisi'ni açın.

    -   **Rol Hizmetleri** Sayfasında, **Ağ Cihazı Kayıt Hizmeti**'ni seçin.

    -   **NDES için Hizmet Hesabı** sayfasında, NDES Hizmet Hesabı'nı belirtin.

    -   **NDES için CA** sayfasında, **Seç**'e tıklayın ve ardından, sertifika şablonunu yapılandırdığınız yerde sertifika veren CA'yı seçin.

    -   **NDES için şifreleme** sayfasında, anahtar uzunluğunu şirket gereksinimlerinizi karşılayacak şekilde ayarlayın.

    **Onay** sayfasında, sihirbazı tamamlamak için **Yapılandır** 'a tıklayın.

2.  Sihirbaz tamamlandıktan sonra, NDES Sunucusu'nda aşağıdaki kayıt defteri anahtarını düzenleyin:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Bu anahtarı düzenlemek için sertifika şablonunun **Amaç** değerini, anahtarın **İstek İşleme** sekmesinde bulunan değerle tanımlayın ve ardından, kayıt defterindeki mevcut verileri sertifika şablonunun Görev 1'de belirttiğiniz adıyla (şablonun görünen adı değil) değiştirerek kayıt defterinde ilgili girişi düzenleyin. Aşağıdaki tabloda, sertifika şablonu amacı ile kayıt defterindeki değerler eşleştirilmiştir:

    |Sertifika şablonunun Amacı (İstek İşleme sekmesinde)|Düzenlenecek kayıt defteri değeri|SCEP profili için Intune yönetim konsolunda görünen değer|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |İmza|SignatureTemplate|Dijital İmza|
    |Şifreleme|EncryptionTemplate|Anahtar Şifrelemesi|
    |İmza ve şifreleme|GeneralPurposeTemplate|Anahtar Şifrelemesi<br /><br />Dijital İmza|
    Örneğin, sertifika şablonunuzun Amacı **Şifreleme**ise **EncryptionTemplate** değerini sertifika şablonunuzun adı olacak biçimde düzenleyin.

3.  Kayıt defterini düzenledikten sonra, sunucuda **iisreset** 'i çalıştırarak sunucuyu son yapılandırma değişikliklerini yakalamaya zorlayın.

##### NDES Sunucusu'nda sertifikaları yüklemek ve bağlamak için

1.  NDES Sunucunuzda, iç CA'nızdan veya genel CA'dan bir **sunucu kimlik doğrulaması** sertifikası isteyin ve yükleyin. Ardından bu SSL sertifikasını IIS'de bağlarsınız.

    > [!TIP]
    > SSL sertifikasını IIS'de bağladıktan sonra, bir de istemci kimlik doğrulama sertifikası yüklersiniz. Bu sertifika, NDES Sunucusu tarafından güvenilen bir CA tarafından verilebilir. En iyi yöntem olmasa da, sertifika her iki Gelişmiş Anahtar Kullanımları (EKU'lar) özelliğine de sahip olduğu sürece, aynı sertifikayı hem sunucu hem de istemci kimlik doğrulaması için kullanabilirsiniz. Bu kimlik doğrulama sertifikaları hakkında bilgi için aşağıdaki adımları gözden geçirin.

    1.  Sunucu kimlik doğrulama sertifikasını edindikten sonra **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından, **Eylemler** bölmesinden **Bağlamalar** 'a tıklayın.

    2.  **Ekle**'ye tıklayın, **Tür** 'ü **https**olarak ayarlayın ve sonra bağlantı noktasının **443**olduğundan emin olun. (Tek başına Intune için yalnızca bağlantı noktası 443 desteklenir).

    3.  **SSL sertifikası**için sunucu kimlik doğrulama sertifikasını belirtin.

        > [!NOTE] NDES sunucusu tek bir ağ adresi için hem iç hem de dış ad kullanıyorsa, sunucu kimlik doğrulama sertifikasının dış genel sunucu adına sahip bir **Konu Adı** ve iç sunucu adını içeren bir **Konu Diğer Adı** olmalıdır.

2.  NDES Sunucunuzda, iç CA'nızdan ya da genel bir sertifika yetkilisinden bir **istemci kimlik doğrulaması** sertifikası isteyin ve yükleyin. Bu sertifika, her iki özelliği de içeriyorsa sunucu kimlik doğrulama sertifikası ile aynı sertifika olabilir.

    İstemci kimlik doğrulama sertifikasının aşağıdaki özelliklere sahip olması gerekir:

    **Gelişmiş Anahtar Kullanımı** - Bu, **İstemci Kimlik Doğrulaması**'nı içermelidir.

    **Konu Adı** - Bu, sertifikayı yüklediğiniz sunucunun (NDES Sunucusu) DNS adına eşit olmalıdır.

##### IIS İstek Filtreleme'yi yapılandırmak için

1.  NDES Sunucusu'nda **IIS Yöneticisi**'ni açın, **Bağlantılar** bölmesinden **Varsayılan Web Sitesi** 'ni seçin ve ardından **İstek Filtreleme**'yi açın.

2.  **Özellik Ayarlarını Düzenle**'ye tıklayın ve ardından aşağıdakileri ayarlayın:

    **sorgu dizesi (Bayt)** = **65534**

    **URL uzunluğu üst sınırı (Bayt)** = **65534**

3.  Aşağıdaki kayıt defteri anahtarını inceleyin:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Aşağıdaki değerlerin DWORD girişleri olarak ayarlandığından emin olun:

    Ad: **MaxFieldLength**, **65534**'ün ondalık bir değeri ile

    Ad: **MaxRequestBytes**, **65534**'ün ondalık bir değeri ile

4.  NDES sunucusunu yeniden başlatın. Sunucu artık Sertifika Bağlayıcısı'nı desteklemeye hazırdır.

## Görev 4: Intune Sertifika Bağlayıcısı’nı etkinleştirme, yükleme ve yapılandırma - SCEP ve .PFX sertifikaları için.
Bu görevde şunları yapacaksınız:

Intune’da NDES desteğini etkinleştirme

NDES Sunucusu'nda Sertifika Bağlayıcısı'nı indirme, yükleme ve yapılandırma

##### Sertifika Bağlayıcısı desteğini etkinleştirmek için

1.  [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **Yönetim** &gt; **Sertifika Bağlayıcısı**’na tıklayın.

2.  **Şirket İçi Sertifika Bağlayıcısını Yapılandır**'a tıklayın.

3.  **Sertifika Bağlayıcısı'nı Etkinleştir**'i seçin ve ardından **Tamam**'a tıklayın.

##### Sertifika Bağlayıcısı'nı indirmek, yüklemek ve yapılandırmak için

1.  [Intune yönetim konsolunu açın](https://manage.microsoft.com) ve ardından **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Sertifika Bağlayıcısı** &gt; **Sertifika Bağlayıcısı’nı İndir**’e tıklayın.

2.  Yükleme tamamlandıktan sonra, indirilen yükleyiciyi (**ndesconnectorssetup.exe**) çalıştırın:

    -   .PFX sertifikaları için, yükleyiciyi Sertifika Yetkilisi ile iletişim kurabilen bilgisayarda çalıştırın. .PFX Dağıtımı seçeneğini belirtin, sonra Yükle’ye tıklayın. Yükleme tamamlandığında, [Sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konusunda açıklandığı gibi bir sertifika profili oluşturarak devam edin.

    -   SCEP sertifikaları için, yükleyiciyi bir Windows Server 2012 R2 sunucusunda çalıştırın

    SCEP seçeneği için, yükleyici NDES ve CRP Web Hizmeti için ilke modülünü de yükler. (CRP Web Hizmeti, CertificateRegistrationSvc, IIS'de bir uygulama olarak çalışır.)

    > [!NOTE]
    > Tek başına Intune için NDES yüklediğinizde, CRP hizmeti Sertifika Bağlayıcısı ile otomatik olarak yüklenir. Intune’u Configuration Manager ile kullandığınızda, Sertifika Kayıt Noktası'nı ayrı bir site sistem rolü olarak yüklersiniz.

3.  Sertifika Bağlayıcısı için istemci sertifikası istendiğinde, **Seç**'e tıklayıp Görev 3'te NDES Sunucunuza yüklediğiniz **istemci kimlik doğrulaması** sertifikasını seçin.

    İstemci kimlik doğrulaması sertifikasını seçtikten sonra, **Microsoft Intune Sertifika Bağlayıcısı için İstemci Sertifikası** yüzeyine dönersiniz. Seçtiğiniz sertifika gösterilmese de bu sertifikanın özelliklerini görüntülemek **İleri** 'ye tıklayın. Ardından **İleri**'ye ve **Yükle**'ye tıklayın.

4.  Sihirbaz tamamlandıktan sonra, sihirbazı kapatmadan önce, **Sertifika Bağlayıcısı Kullanıcı Arabirimini Başlat**'a tıklayın.

    > [!TIP] Sertifika Bağlayıcısı Kullanıcı Arabirimi'ni başlatmadan sihirbazı kapatırsanız, aşağıdaki komutu çalıştırarak yeniden açabilirsiniz:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  **Sertifika Bağlayıcısı** kullanıcı arabiriminde:

    **Oturum Aç**'a tıklayın ve Intune hizmet yöneticisi kimlik bilgilerinizi veya genel yönetim izni olan bir kiracı yöneticiye ait kimlik bilgilerini girin.

    Kuruluşunuz bir ara sunucu kullanıyorsa ve NDES sunucusunun İnternet'e erişmesi için ara sunucu gerekliyse, **Ara sunucuyu kullan**'a tıklayın ve bağlanmak için ara sunucu adını, bağlantı noktasını ve hesap kimlik bilgilerini girin.

    **Gelişmiş** sekmesini seçin ve ardından, Sertifika Verme Yetkilisi'nde **Sertifika Ver ve Yönet** iznine sahip olan bir hesabın kimlik bilgilerini sağlayın ve **Uygula**'ya tıklayın.

    Şimdi Sertifika Bağlayıcısı kullanıcı arabirimini kapatabilirsiniz.

6.  Bir komut istemi açıp **services.msc** yazın ve **Enter** tuşuna basın, sonra **Intune Bağlayıcı Hizmeti**'ne sağ tıklayın ve **Yeniden Başlat**'a tıklayın.

Hizmetin çalıştığını doğrulamak için bir tarayıcı açın ve bir **403** hatası döndürmesi gereken aşağıdaki URL'yi girin:

**http:// &lt;NDES_sunucunuzun_FQDN_değeri&gt;/certsrv/mscep/mscep.dll**

### Sonraki adımlar
Artık, [Sertifika profillerini yapılandırma](configure-intune-certificate-profiles.md) konusunda açıklandığı gibi sertifika profillerinizi yapılandırmaya hazırsınız.


<!--HONumber=Jun16_HO1-->


