---
title: Intune ile cihaz tabanlı koşullu erişim ayarlama
titleSuffix: Microsoft Intune
description: Microsoft Intune cihaz uyumluluğu ve mobil uygulama yönetimi temelinde cihaz tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fde15da898a70e9557aabb9ed7a7ae8324cfb304
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188340"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Cihaz tabanlı koşullu erişim ilkesi oluşturma

Intune ile, erişim denetimlerine mobil cihaz uyumluluğu ekleyerek Azure Active Directory Koşullu erişimi geliştirin. Cihazların uyumlu olması için gereksinimleri tanımlayan Intune uyumluluk ilkesiyle, uygulama ve hizmetlerinize erişime izin vermek veya erişimi engellemek için bir cihazın uyumluluk durumunu kullanabilirsiniz. Bunu, **cihazın uyumlu olarak Işaretlenmesini gerektir**ayarını kullanan bir koşullu erişim ilkesi oluşturarak yapabilirsiniz.

Koşullu erişim ilkesi, korumak istediğiniz uygulama veya Hizmetleri, uygulama veya hizmetlere erişilebilen koşulları ve ilkenin uygulandığı kullanıcıları belirler. Koşullu erişim bir Azure AD Premium özelliği olsa da, *Intune* 'Dan eriştiğiniz koşullu erişim düğümü, *Azure AD*'den erişildiği şekilde aynı düğümdür.

> [!IMPORTANT]
> Koşullu erişimi ayarlamadan önce, cihazları belirli gereksinimleri karşılayıp karşılamadığını temel alarak değerlendirmek için Intune cihaz uyumluluk ilkelerini ayarlamanız gerekir. Bkz. [Intune 'da cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Yeni ilke** > **koşullu erişim** > **ilkeleri** > **cihazları** seçin.
  Yeni bir koşullu erişim ilkesi oluşturmak ![](./media/create-conditional-access-intune/create-ca.png)

3. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin.

4. **Dahil et** sekmesinde, bu koşullu erişim ilkesinin uygulandığı kullanıcıları veya grupları tanımla. Grupları veya kullanıcıları dahil etmek üzere seçtikten sonra, bu ilkeden dışlamak istediğiniz herhangi bir Kullanıcı, rol veya grup varsa **dışlama** sekmesini kullanın.

   - **Tüm kullanıcılar**: ilkeyi iç ve Konuk kullanıcılar dahil tüm kullanıcılara ve gruplara uygulamak için bu seçeneği belirleyin.

   - **Kullanıcıları ve grupları seçin**: Bu seçeneği belirleyin ve aşağıdaki seçeneklerden birini veya birkaçını belirtin:
  
     1. **Tüm konuk kullanıcılar**: dış Konuk kullanıcıları dahil etmek veya hariç tutmak için bu seçeneği belirleyin (örneğin, iş ortakları, dış ortak çalışanlar)

     2. **Dizin rolleri**: bu rollere atanmış kullanıcıları dahil etmek veya hariç tutmak için bir veya daha fazla Azure AD rolü seçin.

     3. **Kullanıcılar ve gruplar**: dahil etmek veya dışlamak istediğiniz bireysel kullanıcıları veya grupları aramak ve seçmek için bu seçeneği belirleyin.

        > [!TIP]
        > İlkeyi, beklendiği gibi çalıştığından emin olmak için daha küçük bir kullanıcı grubuna göre test edin.

5. **Bitti**’yi seçin.

6. **Atamalar**' ın altında **bulut uygulamaları veya eylemler**' i seçin.

7. **Dahil et** sekmesinde, bu koşullu erişim ilkesiyle korumak istediğiniz uygulamaları ve hizmetleri tanımlamak için kullanılabilir seçenekleri kullanın. Ardından, bu ilkeden dışlamak istediğiniz herhangi bir uygulama veya hizmet varsa **dışlama** sekmesini kullanabilirsiniz.

   - **Tüm bulut uygulamaları**: ilkeyi tüm uygulamalara uygulamak için bu seçeneği belirleyin.
     > [!IMPORTANT]
     > Azure portal erişim için Microsoft Azure yönetim uygulaması bu listeye dahildir. (Veya tanımladığınız Kullanıcı veya grupların) Azure portal oturum açabildiğinizden emin olmak için, burada veya **Kullanıcı ve gruplar** seçeneklerinde **hariç tut** sekmesini kullandığınızdan emin olun. 

   - **Uygulamalar**' ı seçin: Bu seçeneği belirleyin, **Seç**' i seçin ve ardından, korumak istediğiniz uygulamaları veya hizmetleri aramak ve seçmek için uygulamalar listesini kullanın.

   Hazırlanıyor, **bitti**' yi seçin.

8. **Atamalar**' ın altında **koşullar**' ı seçin.

   - **Oturum açma riski**: Bu ilkeyle oturum açma riskini algılama Azure AD kimlik koruması kullanmak için *Evet* ' i seçin ve ardından ilkenin uygulanması gereken oturum açma risk düzeylerini seçin.

   - **Cihaz platformları**: **ekleme** sekmesinde, bu koşullu erişim ilkesinin uygulanmasını istediğiniz cihaz platformlarını yapın. Platformları bu ilkeden dışlamak için **Dışla** sekmesini kullanın.

   - **Konumlar**: **ekleme** sekmesinde, ilkenin uygulanıp uygulanmadığını belirtin:
     - Herhangi bir konum
     - BT departmanınızın denetimi altında olan güvenilen ağ konumları
     - Belirli ağ konumları.

     Ağ konumlarını bu ilkeden dışlamak için **Dışla** sekmesini kullanın.

   - **İstemci uygulamaları**: ilkenin tarayıcı uygulamaları, mobil uygulamalar ve Masaüstü istemcilerine uygulanması gerekip gerekmediğini belirtmek için *Evet* ' i seçin.

   - **Cihaz durumu**: koşullu erişim Ilkesi, Evet ' i seçmediğiniz ve özellikle de durum cihazı karma Azure AD 'ye katılmış ya da uyumlu olarak işaretlenmiş cihaz (veya her ikisi) hariç tutmadığınız sürece tüm cihaz durumlarına uygulanır.

     > [!TIP]
     > Hem **modern kimlik doğrulama** istemcilerini hem de **Exchange ActiveSync istemcilerini**korumak istiyorsanız, her istemci türü için bir tane olmak üzere iki ayrı koşullu erişim ilkesi oluşturun. Exchange ActiveSync modern kimlik doğrulamasını desteklese de, Exchange ActiveSync tarafından desteklenen tek koşul platformudur. Multi-Factor Authentication dahil diğer koşullar desteklenmez. Exchange ActiveSync 'ten Exchange Online 'a erişimi etkili bir şekilde korumak için, Cloud App Office 365 Exchange Online 'ı ve istemci uygulaması Exchange ActiveSync 'i yalnızca desteklenen platformlara Uygula seçiliyken belirten bir koşullu erişim ilkesi oluşturun.

9. **Bitti**’yi seçin.

10. **Erişim denetimleri** altında **Ver**’i seçin. Ayarladığınız koşullara göre ne olacağını yapılandırın.  Aşağıdaki seçeneklerden seçim yapabilirsiniz:

    - **Erişimi engelle**: Bu ilkede belirtilen kullanıcıların, belirttiğiniz koşullarda uygulamalara erişimi reddedilir.
    - **Erişim Izni ver**: Bu ilkede belirtilen kullanıcılara erişim verilecek, ancak aşağıdaki diğer eylemlerden herhangi birini zorunlu kılabilirsiniz:
      - **Multi-Factor Authentication gerektir**: Kullanıcı, telefon araması veya metin gibi ek güvenlik gereksinimlerini tamamlamalıdır.
      - **Cihazın uyumlu olarak Işaretlenmesini gerektir**: cihazın Intune ile uyumlu olması gerekir. Cihaz uyumsuzsa, kullanıcıya cihazı Intune 'a kaydetme seçeneği verilir.
      - **Karma Azure AD 'ye katılmış cihaz gerektir**: cihazların HIBRIT Azure AD 'ye katılmış olması gerekir.
      - **Onaylanan istemci uygulaması gerektir**: cihazın onaylanan istemci uygulamaları kullanması gerekir. 
      - **Birden çok denetim için**: bir cihaz uygulamaya erişmeyi denediğinde tüm gereksinimlerin **uygulanması için tüm seçili denetimleri gerektir** ' i seçin.

      ![Erişim denetimleri Izin ayarları](./media/create-conditional-access-intune/create-ca-grant-access-settings.png)

11. **İlkeyi etkinleştir** altında **Açık**’ı seçin.

12. **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)

[Intune koşullu erişim sorunlarını giderme](https://support.microsoft.com/help/4456106)
