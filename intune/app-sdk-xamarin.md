---
title: "Microsoft Intune Uygulama SDK'sı Xamarin Bileşeni"
description: 
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a684f7ab5841513e8e72a5e6c0af99f52e5fd207
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune Uygulama SDK'sı Xamarin Bileşeni

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](app-sdk-get-started.md) makalesini okumanız önerilir.



## <a name="overview"></a>Genel Bakış
[Intune App SDK’sı Xamarin bileşeni](https://components.xamarin.com/view/microsoft.intune.mam), Xamarin ile oluşturulan iOS ve Android uygulamalarındaki [Intune uygulama koruma ilkesini](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) etkinleştirir. Bu bileşen, geliştiricilerin Intune uygulama koruma özelliklerini Xamarin tabanlı uygulamalarına kolayca eklemesini sağlar.

Microsoft Intune Uygulama SDK’sı Xamarin Bileşeni, Intune uygulama koruma ilkelerini (APP veya MAM ilkeleri olarak da bilinir) Xamarin ile geliştirilen uygulamalarınıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="whats-supported"></a>Desteklenen özellikler

### <a name="developer-machines"></a>Geliştirici makineleri
* Mac OS


### <a name="mobile-app-platforms"></a>Mobil uygulama platformları
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune Mobil Uygulama Yönetimi senaryoları

* Intune MDM ile kaydedilen cihazlar
* Üçüncü taraf EMM ile kaydedilen cihazlar
* Yönetilmeyen cihazlar (herhangi bir MDM ile kaydedilmeyen)

Intune Uygulama SDK’sı Xamarin Bileşeni ile derlenen Xamarin uygulamaları artık, Intune mobil cihaz yönetimi (MDM) ile kaydedilen ve kaydedilmeyen cihazlarda Intune uygulama koruma ilkelerini alabilir.

## <a name="prerequisites"></a>Önkoşullar

* **[Yalnızca Android]** Cihazda en güncel Microsoft Intune Şirket Portalı uygulaması yüklü olmalıdır.

## <a name="get-started"></a>Başlarken

1.  **Xamarin-component.exe** dosyasını [buradan](https://components.xamarin.com/submit/xpkg) indirin ve ayıklayın.

2. Microsoft Intune MAM Xamarin Bileşeni [lisans koşullarını](https://components.xamarin.com/license/microsoft.intune.mam) okuyun.

3.  Intune Uygulama SDK'sı Xamarin Bileşeni klasörünü [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) veya [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam)'den indirin ve ayıklayın. 1. ve 3. adımlarda indirdiğiniz dosyaların aynı dizin düzeyinde olması gerekir.

4.  Komut satırında yönetici olarak `Xamarin.Component.exe install <.xam> file` komutunu çalıştırın.

5.  Visual Studio’da önceden oluşturduğunuz Xamarin projesinde **bileşenler** öğesine sağ tıklayın.

6.  **Bileşenleri Düzenle**'yi seçin ve bilgisayarınıza indirdiğiniz Intune Uygulama SDK'sı bileşenini ekleyin.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1.  Intune Uygulama SDK'sını başlatmak için `AppDelegate.cs` sınıfındaki API’lerden birini çağırmanız gerekir. Örneğin:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Bileşen ekleyip başlattınız. Şimdi Uygulama SDK'sını iOS mobil uygulamasına eklemek için gerekli genel adımları uygulayabilirsiniz. Yerel iOS uygulamalarını etkinleştirme hakkında ayrıntılı bilgileri [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md)'nda bulabilirsiniz.
3. **Önemli**: Xamarin tabanlı iOS uygulamalarınıza özgü birden fazla değişiklik vardır. Örneğin, anahtar zinciri gruplarını etkinleştirmek için, bileşene eklediğimiz Xamarin örnek uygulamasını dahil etmek üzere aşağıdakileri eklemeniz gerekir. Anahtar Zinciri Erişim gruplarınızda olması gereken grupların örneği aşağıda verilmiştir:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Bileşeni Xamarin tabanlı iOS uygulamanıza eklemek için gerekli adımları tamamladınız. Projenizi Xcode ile derliyorsanız, `Intune App SDK Settings.bundle` kullanabilirsiniz. Bu sayede derleme sırasında Intune ilke ayarlarını açıp kapatarak test ve hata ayıklama işlemlerini gerçekleştirebilirsiniz. Bu paketten faydalanmak için [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md)'ndaki adımları uygulayın ve [Xcode ile hata ayıklama](app-sdk-ios.md#status-result-and-debug-notifications) bölümünü okuyun.

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Android mobil uygulamanızda uygulama koruma ilkelerini etkinleştirme
UI çerçevesi kullanmayan Xamarin tabanlı Android uygulamaları için [Android Geliştiricisi için Intune Uygulama SDK’sı Kılavuzu](app-sdk-android.md) belgesini okumanız ve gerekli adımları uygulamanız gerekir. Xamarin tabanlı Android uygulamanız için sınıf, yöntem ve etkinlikleri kılavuzda yer alan [tabloya](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) göre MAM eşdeğerleriyle değiştirmeniz gerekir. Uygulamanızda `android.app.Application` sınıfı tanımlanmıyorsa bir tane oluşturup `MAMApplication` kaynağından devraldığından emin olmanız gerekir.

Xamarin.Forms ve diğer UI çerçeveleri için `MAM.Remapper` adında bir araç sunuyoruz. Bu araç, sınıf değişikliklerini sizin için yapacaktır. Ancak aşağıdaki adımları sizin uygulamanız gerekir:

1.  `Microsoft.Intune.MAM.Remapper.Tasks` NuGet paketi sürüm 0.1.0.0 veya üzeri için başvuru ekleyin.

2.  Android csproj dosyanıza şu satırı ekleyin:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Eklediğiniz `remapping-config.json` dosyasının derleme eylemini **RemappingConfigFile** olarak ayarlayın. Dahil edilen `remapping-config.json` yalnızca Xamarin.Forms ile çalışır. Diğer UI çerçeveleri için Remapper NuGet paketindeki Benioku dosyasına bakın.

## <a name="next-steps"></a>Sonraki adımlar

Bileşeni uygulamanıza eklemek için temel adımları tamamladınız. Şimdi Xamarin Android örnek uygulamasındaki adımları uygulayabilirsiniz. Biri Xamarin.Forms, diğeri Android için olmak üzere iki örnek sağladık.