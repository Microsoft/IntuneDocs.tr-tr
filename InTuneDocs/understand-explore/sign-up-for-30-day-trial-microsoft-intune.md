---
title: "Microsoft Intune&quot;un 30 günlük ücretsiz denemesine kaydolma | Microsoft Docs"
description: "Microsoft Intune&quot;un 30 günlük değerlendirmesine ücretsiz olarak kaydolun ve denemeyi kurun."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: a65ead23e62870647245120d1663706fc46810ac


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Microsoft Intune ücretsiz denemesine kaydolma
Bu makale, bir Intune denemesine kaydolmayı adım adım gösterir ve Intune'un mobil cihazları nasıl yönettiğini görmek üzere ilişkili değerlendirme kılavuzunu izleyebilmeniz için deneme sürümünüzde bazı kullanıcılar oluşturur. <!---or app data when devices are not enrolled in Intune.--->

## <a name="assumptions"></a>Varsayımlar
Bu kaydolma makalesi ve değerlendirme kılavuzu, denemeyi yalnızca değerlendirme amacıyla kullandığınızı ve abone olduğunuzda boş bir ortam ile başlayacağınızı varsayar.

Denemeye başlamanızı kolaylaştırmak için yalnızca Intune'u kullanan ve bunun (mobil cihaz yönetim yetkilisi olarak bilinen) tek cihaz yönetme yönteminiz olacağını varsayan çok basit bir ortam kurarız. Ancak kılavuz boyunca, daha fazlasını öğrenmek isterseniz sizi daha ayrıntılı içeriğe yönlendiririz.

Deneme sürümünde abonelik sürümünde yapabileceğiniz her şeyi yapabilirsiniz. Tek fark, deneme sürümünün 100 kullanıcı hesabı ile sınırlı olmasıdır.

## <a name="sign-up-for-your-trial"></a>Deneme sürümünüz için kaydolma
[Intune Kayıt](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) sayfasını ziyaret edin ve bir deneme aboneliğine kaydolmak için formu doldurun.

Bir iş veya okul hesabınız varsa ve Intune denemeniz için bu hesabı kullanmak istiyorsanız, bunun yerine [bu oturum açma yönergelerini](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) izleyin. Ancak bu makale ve değerlendirme kılavuzları bu tür bir hesabı kullanmadığınızı varsayar.

> [!TIP]
> BT işlemlerinizin ve kullanıcılarınızın çoğu sizinkinden başka bir bölgedeyse, performansı sınamak için denemenizde bu yerel ayarı yapmanız iyi olur.

### <a name="post-sign-up-considerations"></a>Kayıttan sonra dikkate alınacak noktalar
Deneme için kaydolduğunuzda, kayıt işlemi sırasında sağladığınız e-posta adresine hesap bilgilerinizi içeren bir e-posta iletisi gönderilir. Bu e-posta, denemenizin etkin olduğunu doğrular.

Kayıt işlemini tamamladıktan sonra, Office 365 yönetim merkezi aracılığıyla kullanıcı eklemek ve bu kişilere lisans atamak için kullanılan bir sayfaya yönlendirilirsiniz. Intune'da bir sonraki oturum açışınızda, otomatik olarak Intune yönetim konsoluna yönlendirilirsiniz.

## <a name="keeping-the-admin-center-and-the-intune-administration-console-straight"></a>Yönetim merkezi ve Intune yönetim konsolunu düzenli tutma
Intune için kullanacağınız iki portal vardır: Office 365 Yönetim merkezi ([portal.office.com](https://portal.office.com)) ve Intune yönetim konsolu ([manage.microsoft.com](https://manage.microsoft.com)).

Normalde, işlerinizi Intune yönetim konsolunda aşağıda gösterildiği gibi yaparsınız. Burası; gruplarınızı, ilkelerinizi, cihazlarınızı ve uygulamalarınızı kurduğunuz ve yönettiğiniz sitedir.

![Intune yönetim konsolunun resmi](./media/sign-up/intune-admin-console.png)

Ancak kullanıcılarınızı ve hesabınızın faturalama ve destek gibi diğer yönlerini eklemek ve yönetmek için aşağıda gösterildiği gibi Office 365 Yönetim merkezini kullanırsınız.

![Office 365 Yönetim merkezinin resmi](./media/sign-up/office-admin-center.png)

Office 365 Yönetim merkezinden Intune yönetim konsoluna gidebilirsiniz. Yönetim merkezleri sol gezinme bölmesindeki son öğenin altındadır. Yeni bir sekmede Intune yönetim konsolunu açmak için **Intune**'u seçin.

![Intune yönetim konsoluna bağlantının resmi](./media/sign-up/link-to-intune.png)

Intune'dan Office 365 Yönetim merkezine geri dönmek için Gruplara Genel Bakış sayfasında **Kullanıcı Ekle** görevini seçin.

![Office 365 Yönetim merkezinin geri bağlantısının resmi](./media/sign-up/task-add-users.png)

## <a name="add-users"></a>Kullanıcı ekleme
Intune için Office 365 Yönetim merkezinden ayrılmadan önce deneme hesabınıza bazı kullanıcılar eklemeniz gerekir.

Office 365 Yönetim merkezinde kullanıcıları tek tek veya bir .csv dosyasını yükleyerek topluca ekleyebilirsiniz. Deneme sürümünüzü ayarlamak için her ikisini de yapacağız. Ancak üretim ortamınızda büyük olasılıkla Azure Active Directory kullanıcı hesaplarınızdan yararlanmak isteyeceksiniz. [Başlangıç kılavuzumuzdan](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) ve bu makalenin [Sonraki adımlar](#Next-steps) bölümünden bu hesaplar hakkında daha fazla bilgi alabilirsiniz.

### <a name="add-an-individual-user"></a>Tek bir kullanıcı ekleme
1. Kullanıcı ekleme seçeneklerinden birini seçerek kullanıcı oluşturmanıza izin veren formu açın. Yalnızca yıldızla (\*) işaretlenen öğeler gereklidir.
![Kullanıcı ekle düğmesi seçenekleri resmi](./media/sign-up/add-user.png)


2.  Kullanıcıyı eklediğinizde, son adım kullanıcıya geçici Intune parolasıyla bir e-posta göndermek olacaktır. Bu değerlendirmeyi yaparken, oturum açma bilgilerini almak ve kullanıcılarınızın alacağı e-postayı görmek için kendi iş hesabınızın e-posta adresini kullanın. Daha sonra sınama cihazları kaydetmek için bu kullanıcı kimliklerini kullanabilirsiniz.<br/>

 ![Kullanıcı ekle son adım resmi](./media/sign-up/new-user-2.png)

3. Bir kullanıcıyı oluşturduktan sonra kullanıcıya yönetim rolü atamak isterseniz, kullanıcı listenizden kullanıcı adını, sonra aralarından seçim yapıp bu kullanıcıya atayabileceğiniz kullanıcı rollerinin listesini görmek için Rol satırında **Düzenle**'yi seçerek Office 365 Yönetim merkezinde düzenleyebilirsiniz.

 ![Kullanıcı rolü seçenekleri resmi](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Birden fazla kullanıcıyı içeri aktarma
1. Birden fazla kullanıcıyı içeri aktarma sihirbazını **Daha fazla** listesinde bulabilirsiniz.

 ![Birden çok kullanıcı ekleme seçenekleri resmi](./media/sign-up/add-multiple-users.png)

2. .Csv dosyanızı doğru ayarlamanıza yardımcı olması için kullanıcı verileriniz ile doldurmak üzere bir şablon dosyası indirebilirsiniz. Her alana için tam olarak gereken veri türünü görmek üzere başlıklar ve örnek kullanıcı bilgileri içeren .csv dosyasını indirin.

 ![Toplu kayıt sihirbazının ilk adımının resmi](./media/sign-up/bulk-enroll-step-1.png)


3. .csv dosyanızı oluşturup kaydettikten sonra, dosyayı seçmek için **Gözat**'ı seçin. Doğrulayın ve **İleri**'yi seçin. Kullanıcılarınız yüklenir ve etkin kullanıcılar listenize eklenir.

Artık kullanıcılarınızı, bunların cihazlarını ve uygulamalarını yönetmeye başlamak için Intune yönetim konsoluna gidebilirsiniz.

> [!NOTE]
> Kullanıcılarınız, yönetilecek bir cihazı kaydedene kadar Intune'da görünmez.

## <a name="next-steps"></a>Sonraki adımlar
Değerlendirme senaryosu: [Microsoft Intune'da mobil cihaz yönetimini değerlendirme](mobile-device-management-trial-guide-microsoft-intune.md)

Azure Active Directory kullanıcı hesaplarınızı Intune ile kullanma hakkında daha fazla bilgi edinin:
- [Kimlik gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Çok faktörlü kimlik doğrulama gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

[Intune'u System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) ile kullanma hakkında daha fazla bilgi edinin



<!--HONumber=Dec16_HO2-->


