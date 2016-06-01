---
# required metadata

title: GPO ve Intune ilke çakışmalarını çözme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Grup İlkesi Nesneleri (GPO) ve Microsoft Intune ilke çakışmalarını çözme
Intune yönettiğiniz bilgisayarlardaki ayarları yönetmenize yardımcı olmak için ilkeleri kullanır. Örneğin, bilgisayarlardaki Windows Güvenlik Duvarı ayarlarını denetlemek için bir ilke kullanabilirsiniz. Çoğu Intune ayarı Windows Grup İlkesi'yle yapılandırdığınız ayarlara benzer. Ancak, bazen iki yöntemin çakışması mümkündür.

Çakışmalar oluştuğunda, bilgisayarın etki alanında oturum açamadığı durumlar dışında, etki alanı düzeyi Grup İlkesi Intune ilkesinden önceliklidir. Böyle bir durumda, istemci bilgisayara Intune ilkesi uygulanır.

## Grup İlkesi kullanıyorsanız yapmanız gerekenler
Uyguladığınız herhangi bir ilkenin Grup İlkesi tarafından yönetilmediğini kontrol edin. Çakışmaları önlemek için aşağıdaki yöntemlerden bir veya birkaçını kullanabilirsiniz:

-   Intune istemcisini yüklemeden önce bilgisayarlarınızı Grup İlkesi ayarları uygulanmayan bir Active Directory kuruluş birimine (OU) taşıyın. Ayrıca Grup İlkesi ayarlarını uygulamak istemediğiniz Intune kaydı yapılmış bilgisayarlar içeren OU'larda Grup İlkesi devralmayı engelleyebilirsiniz.

-   GPO’ları yalnızca Intune tarafından yönetilmeyen bilgisayarlarla sınırlamak için bir WMI filtresi veya güvenlik filtresi kullanın. Bunun nasıl yapılacağı hakkında bilgi ve örnekler için aşağıdaki [Microsoft Intune ilkesiyle Çakışmaları önlemek için mevcut Grup İlkesi Nesnelerini filtreleme](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) bölümüne bakın.

-   Intune ilkeleriyle çakışan Grup İlkesi Nesnelerini devre dışı bırakın veya kaldırın.

Active Directory ve Windows Grup İlkesi hakkında daha fazla bilgi için, Windows Server Belgelerinize bakın.

## Intune ilkesiyle Çakışmaları önlemek için mevcut GPO’ları filtreleme
Intune ilkeleriyle çakışan ayarlara sahip GPO'lar olduğunu belirlediyseniz, bu GPO'ları yalnızca Intune tarafından yönetilmeyen bilgisayarlarla sınırlandırmak için aşağıdaki filtreleme yöntemlerinden birini kullanabilirsiniz.

### WMI filtrelerini kullanma
WMI filtreleri GPO'ları seçici bir şekilde bir sorgunun koşullarını karşılayan bilgisayarlara uygular. WMI filtresi uygulamak için, Intune hizmetine bilgisayar kaydetmeden önce kuruluştaki tüm bilgisayarlara bir WMI örneği dağıtın.

#### Bir GPO'ya WMI filtresi uygulamak için

1.  Aşağıdakileri bir metin dosyasında kopyalayıp yapıştırarak bir yönetim nesnesi dosyası oluşturun ve **WIT.mof** gibi uygun bir konuma kaydedin. Dosya, Intune hizmetine kaydetmek istediğiniz bilgisayarlara dağıttığınız WMI sınıf örneğini içerir.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Dosyayı dağıtmak için bir başlangıç betiği veya Grup İlkesi kullanın. Aşağıda başlangıç betiği için dağıtım komutu verilmiştir. WMI sınıf örneği, istemci bilgisayarlar Intune hizmetine kaydedilmeden önce dağıtılmalıdır.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;MOF dosyasının yolu&gt;\wit.mof**

3.  WMI filtrelerini oluşturmak için, filtre uygulamak istediğiniz GPO'nun Intune kullanılarak yönetilen bilgisayarlar veya Intune kullanılarak yönetilmeyen bilgisayarlar için geçerli olmasını istediğinize bağlı olarak aşağıdaki komutlardan birini çalıştırın.

    -   Intune kullanılarak yönetilmeyen bilgisayarlarda geçerli olan GPO'lar için aşağıdakini kullanın:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Intune’la yönetilen bilgisayarlarda geçerli olan GPO'lar için aşağıdakini kullanın:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Önceki adımda oluşturduğunuz WMI filtresini uygulamak için Grup İlkesi Yönetimi konsolundaki GPO'yu düzenleyin.

    -   Yalnızca Intune kullanarak yönetmek istediğiniz bilgisayarlara uygulanmasını istediğiniz GPO'lar için **WindowsIntunePolicyEnabled=1** filtresini uygulayın.

    -   Yalnızca Intune kullanarak yönetmek istemediğiniz bilgisayarlara uygulanmasını istediğiniz GPO'lar için **WindowsIntunePolicyEnabled=0** filtresini uygulayın.

Grup İlkesinde WMI filtrelerini uygulama hakkında daha fazla bilgi için, [Grup İlkesi Tercihlerinde Güvenlik Filtrelemesi, WMI Filtrelemesi ve Öğe Düzeyi Hedefleme](http://go.microsoft.com/fwlink/?LinkId=177883) blog gönderisine bakın.

### Güvenlik grubu filtrelerini kullanma
Grup İlkesi, GPO'ları yalnızca seçili bir GPO için Grup İlkesi Yönetimi konsolunun **Güvenlik Filtrelemesi** alanında belirtilen güvenlik gruplarına uygulamanızı sağlar. Varsayılan olarak, GPO'lar **Kimliği Doğrulanmış Kullanıcılara** uygulanır.

-   **Active Directory Kullanıcıları ve Bilgisayarları** ek bileşeninde, Intune kullanarak yönetmek istemediğiniz bilgisayarlar ve kullanıcı hesaplarını içeren yeni bir güvenlik grubu oluşturun. Örneğin, grubu **Microsoft Intune Dışında** olarak adlandırabilirsiniz.

-   Grup İlkesi Yönetimi konsolunda, seçili GPO için **Temsilci** sekmesinde, güvenlik grubundaki kullanıcılar ve bilgisayarlar için uygun **Okuma** ve **Grup İlkesi Uygulama** izinlerini vermek için yeni güvenlik grubuna sağ tıklayın. (**Grup İlkesi Uygulama** izinleri **Gelişmiş** iletişim kutusunda bulunur.)

-   Daha sonra yeni güvenlik grubu filtresini seçili bir GPO'ya uygulayın ve **Kimliği Doğrulanmış Kullanıcılar** varsayılan filtresini kaldırın.

Yeni güvenlik grubu Intune hizmet değişikliklerinde kayıt olarak korunmalıdır.

### Ayrıca bkz.
[Microsoft Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO2-->


