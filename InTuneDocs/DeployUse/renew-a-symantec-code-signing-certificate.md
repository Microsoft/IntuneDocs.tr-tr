---
title: "Intune ile kullanılacak Symantec kurumsal kod imzalama sertifikasını yenileme | Microsoft Intune"
description: "Belirli Windows ve Windows Phone mobil cihazlarını yönetmek için kullanılan Symantec sertifikalarını yenileme rehberi"
keywords: 
author: staciebarker
manager: stabar
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8fd2a90025ae9310a214978cd2d42ea7ad035fa3
ms.openlocfilehash: 2479f8065a2bb46e63b0e3971700a8d2c0982755


---

# <a name="renew-a-symantec-enterprise-codesigning-certificate-for-windows-devices"></a>Windows cihazlar için Symantec enterprise kod imzalama sertifikasını yenileme

Belirli Windows ve Windows Phone mobil uygulamalarını dağıtmak için kullanılan Symantec sertifikasının düzenli aralıklarla yenilenmesi gerekir.

## <a name="how-to-renew-the-symantec-enterprise-codesigning-certificate"></a>Symantec kurumsal kod imzalama sertifikasını yenileme

1.  Sertifikanın süresi dolmadan yaklaşık 14 gün önce Symantec tarafından gönderilen yenileme e-postasını bulun. Bu e-posta, kurumsal sertifikanızı yenileme hakkında Symantec tarafından gönderilen yönergeleri içerir.

    Symantec sertifikaları hakkında ek bilgi için [www.symantec.com](http://www.symantec.com) adresini ziyaret edin veya 1-877-438-8776 ya da 1-650-426-3400 numaralı telefonları arayın.

2.  Web sitesine gidin (örnek: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) ve sertifikayla ilişkili Symantec Yayımcı Kimliği ve e-posta adresiyle oturum açın. Yenileme işlemini başlatmak için, sertifika indirmek için kullanacağınız makineyle aynı makineyi kullanmayı unutmayın.

3.  Yenileme onaylandıktan ve ücreti ödenen sonra, sertifikayı indirin.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-80"></a>Windows Phone 8.0 için güncelleştirilmiş sertifika yükleme

1.  Burada bulunan en son Windows Phone Şirket Portalı’nı indirip imzalayın: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Intune Yönetim Konsolu'nuzu ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) açın ve **Yönetici**, **Mobil Cihaz Yönetimi** &gt; **Windows Phone** bölümüne gidip **İmzalı Uygulamayı Karşıya Yükle**’ye tıklayın.

3.  Yeni imzalanan Şirket Portalı'nı karşıya yükleyin. Yeni imzalanan SSP.xap ile Symantec'ten aldığınız yeni .PFX dosyasına ya da bu yeni .PFX dosyasıyla oluşturulmuş uygulama kayıt belirtecine ihtiyacınız olacaktır.

4.  Karşıya yükleme tamamlandığında, eski Şirket Portalı sürümünü Intune Yönetim Konsolu'ndaki **Yazılım** çalışma alanından kaldırın.

5.  Tüm kurumsal satır iş kolu uygulamalarını aynı sertifikayı kullanarak yeniden imzalayın ve karşıya yükleyip var olan uygulamalarla değiştirin.

Güncelleştirilmiş kod imzalama sertifikasını sağlamanın şu an için tek yolu imzalı bir SSP.xap dosyası sağlamaktır. İmzalı iş kolu uygulamalarını desteklemek için, kullanıcılarınız Şirket Portalı uygulamasını mağazadan yüklese bile bir Şirket Portalı uygulamasını imzalayıp karşıya yüklemeniz gerekir.

## <a name="how-to-install-the-updated-certificate-for-windows-phone-81-and-later-devices"></a>Windows Phone 8.1 ve üstü cihazlar için güncelleştirilmiş sertifika yükleme

1.  Burada bulunan İndirme Merkezi’nden en son Windows Phone Şirket Portalı’nı indirip imzalayın: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  [Intune Yönetim Konsolu'nuzu](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) açın ve **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone** bölümüne gidip **İmzalı Uygulamayı Karşıya Yükle**’ye tıklayın.

3.  Yeni imzalanan Şirket Portalı'nı karşıya yükleyin. Yeni imzalanan SSP.xap ile Symantec'ten aldığınız yeni .PFX dosyasına ya da bu yeni .PFX dosyasıyla oluşturulmuş uygulama kayıt belirtecine ihtiyacınız olacaktır.

4.  Karşıya yükleme tamamlandığında, eski Şirket Portalı sürümünü **Yazılımlar** çalışma alanından kaldırın.

5.  Yeni sertifikayı kullanarak tüm yeni ve güncelleştirilmiş kurumsal iş kolu uygulamalarını imzalayın. Mevcut uygulamaların yeniden imzalanması ve dağıtılması gerekmez.


### <a name="see-also"></a>Ayrıca bkz.
[Windows Phone 8.0 yönetimini ayarlama](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Windows Phone yönetimini ayarlama](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


