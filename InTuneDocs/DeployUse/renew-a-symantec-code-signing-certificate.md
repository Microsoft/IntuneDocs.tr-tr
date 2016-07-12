---
title: "Microsoft Intune ile kullanmak için bir Symantec enterprise kod imzalama sertifikasını yenileme | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 566a226c19825990c6a34bffbbd9d1cd6a242ddb


---

# Windows cihazlar için Symantec enterprise kod imzalama sertifikasını yenileme

Belirli Windows ve Windows Phone mobil cihazlarını yönetmek için kullanılan Symantec sertifikasının düzenli aralıklarla yenilenmesi gerekir. Windows Phone 8.0 cihazlarının kaydı için imzalı bir Şirket Portalı uygulaması ve kod imzalama sertifikası gereklidir. Daha yeni Windows Phone cihazları, Mağaza'dan yüklenen şirket portalı uygulamasını kullanabilir. İş kolu uygulamalarını dağıtmak için de bir kod imzalama sertifikası gereklidir.

## Symantec kurumsal kod imzalama sertifikasını yenileme

1.  Sertifikanın süresi dolmadan yaklaşık 14 gün önce Symantec tarafından gönderilen yenileme e-postasını bulun. Bu e-posta, kurumsal sertifikanızı yenileme hakkında Symantec tarafından gönderilen yönergeleri içerir.

    Symantec sertifikaları hakkında ek bilgi için [www.symantec.com](http://www.symantec.com) adresini ziyaret edin veya 1-877-438-8776 ya da 1-650-426-3400 numaralı telefonları arayın.

2.  Web sitesine gidin (örnek: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) ve sertifikayla ilişkili Symantec Yayımcı Kimliği ve e-posta adresiyle oturum açın. Yenileme işlemini başlatmak için, sertifika indirmek için kullanacağınız makineyle aynı makineyi kullanmayı unutmayın.

3.  Yenileme onaylandıktan ve ücreti ödenen sonra, sertifikayı indirin.

## Windows Phone 8.0 için güncelleştirilmiş sertifika yükleme

1.  Burada bulunan en son Windows Phone Şirket Portalı’nı indirip imzalayın: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Intune Yönetim Konsolu'nuzu ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) açın ve **Yönetici**, **Mobil Cihaz Yönetimi** &gt; **Windows Phone** bölümüne gidip **İmzalı Uygulamayı Karşıya Yükle**’ye tıklayın.

3.  Yeni imzalanan Şirket Portalı'nı karşıya yükleyin. Yeni imzalanan SSP.xap ile Symantec'ten aldığınız yeni .PFX dosyasına ya da bu yeni .PFX dosyasıyla oluşturulmuş uygulama kayıt belirtecine ihtiyacınız olacaktır.

4.  Karşıya yükleme tamamlandığında, eski Şirket Portalı sürümünü Intune Yönetim Konsolu'ndaki **Yazılım** çalışma alanından kaldırın.

5.  Tüm kurumsal satır iş kolu uygulamalarını aynı sertifikayı kullanarak yeniden imzalayın ve karşıya yükleyip var olan uygulamalarla değiştirin.

Güncelleştirilmiş kod imzalama sertifikasını sağlamanın şu an için tek yolu imzalı bir SSP.xap dosyası sağlamaktır. İmzalı iş kolu uygulamalarını desteklemek için, kullanıcılarınız Şirket Portalı uygulamasını mağazadan yüklese bile bir Şirket Portalı uygulamasını imzalayıp karşıya yüklemeniz gerekir.

## Windows Phone 8.1 ve üstü cihazlar için güncelleştirilmiş sertifika yükleme

1.  Burada bulunan İndirme Merkezi’nden en son Windows Phone Şirket Portalı’nı indirip imzalayın: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  [Intune Yönetim Konsolu'nuzu](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) açın ve **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone** bölümüne gidip **İmzalı Uygulamayı Karşıya Yükle**’ye tıklayın.

3.  Yeni imzalanan Şirket Portalı'nı karşıya yükleyin. Yeni imzalanan SSP.xap ile Symantec'ten aldığınız yeni .PFX dosyasına ya da bu yeni .PFX dosyasıyla oluşturulmuş uygulama kayıt belirtecine ihtiyacınız olacaktır.

4.  Karşıya yükleme tamamlandığında, eski Şirket Portalı sürümünü **Yazılımlar** çalışma alanından kaldırın.

5.  Yeni sertifikayı kullanarak tüm yeni ve güncelleştirilmiş kurumsal iş kolu uygulamalarını imzalayın. Mevcut uygulamaların yeniden imzalanması ve dağıtılması gerekmez.


### Ayrıca bkz.
[Windows Phone 8.0 yönetimini ayarlama](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Windows Phone yönetimini ayarlama](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


