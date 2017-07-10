---
title: "Yazılım güncelleştirmesi sorunlarını giderme"
description: "Microsoft Intune’da yazılım güncelleştirmesi sorunlarını çözün."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b33c5978c2cb27eb7e486d139e71937c41f48b28
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Microsoft Intune’da yazılım güncelleştirmesi sorunlarını giderme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune’da karşılaşabileceğiniz yazılım güncelleştirmesi sorunlarını çözmek için bu bölümdeki bilgileri kullanın.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## <a name="update-agent-error-codes"></a>Güncelleştirme aracısı hata kodları

Aşağıdaki tabloda Intune **Güncelleştirme Aracısı** hata kodları listelenmektedir. Belirli bir kodu bu tabloda bulamazsanız, bkz. [Windows Update Aracısı Sonuç Kodları](http://go.microsoft.com/fwlink/?LinkID=221542).

|Hata kodu|Simgesel adı|Daha fazla bilgi|
|--------------|-----------------|--------------------|
|**0x00cf0001**|OM_S_SERVICE_STOP|Aracı başarıyla durduruldu.|
|**0x00cf0003**|OM_S_UPDATE_ERROR|İşlem başarıyla tamamlandı, ancak güncelleştirmelerin uygulanması sırasında hatalar oluştu.|
|**0x00cf0004**|OM_S_MARKED_FOR_DISCONNECT|İşlemin bağlantısını kesme isteği bir geri çağırma işlemi çalışırken oluştuğundan, bir geri çağırma daha sonra bağlantısı kesilmek için işaretlendi.|
|**0x00cf0005**|OM_S_REBOOT_REQUIRED|Güncelleştirmelerin yüklenmesini tamamlamak için sistemin yeniden başlatılması gerekir.|
|**0x00cf0006**|OM_S_ALREADY_INSTALLED|Yüklenecek güncelleştirme sistemde zaten yüklü.|
|**0x00cf0007**|OM_S_ALREADY_UNINSTALLED|Kaldırılacak güncelleştirme sistemde yüklü değil.|
|**0x00cf2015**|OM_S_UH_INSTALLSTILLPENDING|Güncelleştirme yüklemesi devam ediyor.|
|**0x80cf0001**|OM_E_NO_SERVICE|Aracı hizmeti sağlayamadı.|
|**0x80cf0002**|OM_E_MAX_CAPACITY_REACHED|Hizmetin maksimum kapasitesi aşıldı.|
|**0x80cf0003**|OM_E_UNKNOWN_ID|Bir kimlik bulunamadı.|
|**0x80cf0004**|OM_E_NOT_INITIALIZED|Nesne başlatılamadı.|
|**0x80cf0007**|OM_E_INVALIDINDEX|Bir koleksiyon için dizin geçerli değil.|
|**0x80cf0008**|OM_E_ITEMNOTFOUND|Sorgulanan öğeye ait anahtar bulunamadı.|
|**0x80cf0009**|OM_E_OPERATIONINPROGRESS|Çakışan bir işlem devam ediyordu. Birden çok yükleme gibi bazı işlemler aynı anda gerçekleştirilemez.|
|**0x80cf000B**|OM_E_CALL_CANCELLED|İşlem iptal edildi.|
|**0x80cf000C**|OM_E_NOOP|Hiçbir işlem gerekli değildi.|
|**0x80cf000D**|OM_E_XML_MISSINGDATA|Aracı güncelleştirmenin XML verilerinde gerekli bilgileri bulunamadı.|
|**0x80cf000E**|OM_E_XML_INVALID|Aracının güncelleştirmenin XML verilerinde geçerli olmayan bilgiler buldu.|
|**0x80cf000F**|OM_E_CYCLE_DETECTED|Meta verilerde döngüsel güncelleştirme ilişkileri algılandı.|
|**0x80cf0010**|OM_E_TOO_DEEP_RELATION|Güncelleştirme ilişkileri değerlendirmek için çok fazla iç içe geçmiş.|
|**0x80cf0011**|OM_E_INVALID_RELATIONSHIP|Geçerli olmayan bir güncelleştirme ilişkisi bulundu.|
|**0x80cf0012**|OM_E_REG_VALUE_INVALID|Geçerli olmayan bir kayıt defteri değeri okundu.|
|**0x80cf0013**|OM_E_DUPLICATE_ITEM|İşlem bir listeye yinelenen bir öğe ekleme çalıştı.|
|**0x80cf0014**|OM_E_INVALID_INSTALL_REQUESTED|Çağrıyı yapan yükleme için istenen güncelleştirmeleri yükleyemez.|
|**0x80cf0016**|OM_E_INSTALL_NOT_ALLOWED|İşlem, başka bir yükleme devam ederken veya sistem zorunlu bir yeniden başlatmayı beklerken yüklemeyi denedi.|
|**0x80cf0017**|OM_E_NOT_APPLICABLE|Uygun güncelleştirme olmadığından işlem gerçekleştirilemedi.|
|**0x80cf0018**|OM_E_NO_USERTOKEN|Gerekli bir kullanıcı belirteci eksik olduğundan işlem başarısız oldu.|
|**0x80cf0019**|OM_E_EXCLUSIVE_INSTALL_CONFLICT|Özel bir güncelleştirme diğer güncelleştirmelerle aynı anda yüklenemez.|
|**0x80cf001A**|OM_E_POLICY_NOT_SET|Bir ilke değeri ayarlanmadı.|
|**0x80cf001D**|OM_E_INVALID_UPDATE|Bir güncelleştirme geçerli olmayan meta veriler içeriyor.|
|**0x80cf001E**|OM_E_SERVICE_STOP|Hizmet veya sistem kapatıldığından işlem tamamlanamadı.|
|**0x80cf001F**|OM_E_NO_CONNECTION|Kullanılabilir ağ bağlantısı olmadığından işlem tamamlanamadı.|
|**0x80cf0020**|OM_E_NO_INTERACTIVE_USER|Oturum açmış etkileşimli kullanıcı olmadığından işlem tamamlanamadı.|
|**0x80cf0021**|OM_E_TIME_OUT|İşlem zaman aşımına uğradığından tamamlanamadı.|
|**0x80cf0022**|OM_E_ALL_UPDATES_FAILED|Tüm güncelleştirmeler için işlem başarısız oldu.|
|**0x80cf0024**|OM_E_NO_UPDATE|Güncelleştirme yok.|
|**0x80cf0025**|OM_E_USER_ACCESS_DISABLED|Grup İlkesi ayarları Windows Update'e erişimi engelledi.|
|**0x80cf0026**|OM_E_INVALID_UPDATE_TYPE|Güncelleştirme türü geçerli değil.|
|**0x80cf0028**|OM_E_UNINSTALL_NOT_ALLOWED|İstek bir WSUS sunucusundan kaynaklanmadığından güncelleştirme kaldırılamadı.|
|**0x80cf0029**|OM_E_INVALID_PRODUCT_LICENSE|Arama bazı güncelleştirmeleri atlamış olabilir veya sistem üzerinde lisanssız bir uygulama olabilir.|
|**0x80cf002C**|OM_E_BIN_SOURCE_ABSENT|Delta sıkıştırmalı bir güncelleştirme, kaynağı gerektirdiğinden yüklenemedi.|
|**0x80cf002D**|OM_E_SOURCE_ABSENT|Bir tam dosya güncelleştirmesi, kaynağı gerektirdiğinden yüklenemedi.|
|**0x80cf002E**|OM_E_WU_DISABLED|Yönetilmeyen bir sunucuya erişime izin verilmez.|
|**0x80cf002F**|OM_E_CALL_CANCELLED_BY_POLICY|**DisableWindowsUpdateAccess** ilkesi ayarlanmadığından işlem tamamlanmadı.|
|**0x80cf0030**|OM_E_INVALID_PROXY_SERVER|Proxy listesi biçimi geçerli değil.|
|**0x80cf0031**|OM_E_INVALID_FILE|Dosya yanlış biçimde.|
|**0x80cf0032**|OM_E_INVALID_CRITERIA|Arama ölçütü dizesi geçerli değil.|
|**0x80cf0034**|OM_E_DOWNLOAD_FAILED|Güncelleştirme indirilemedi.|
|**0x80cf0035**|OM_E_UPDATE_NOT_PROCESSED|Güncelleştirme işlenmedi.|
|**0x80cf0036**|OM_E_INVALID_OPERATION|Nesnenin geçerli durumu işleme izin vermedi.|
|**0x80cf0037**|OM_E_NOT_SUPPORTED|İşlem desteklenmiyor.|
|**0x80cf0038**|OM_E_WINHTTP_INVALID_FILE|İndirilen dosya beklenmeyen bir içerik türüne sahip.|
|**0x80cf0039**|OM_E_TOO_MANY_RESYNC|Sunucu aracıdan çok fazla yeniden eşitleme istedi.|
|**0x80cf0043**|OM_E_NO_UI_SUPPORT|WUA kullanıcı arabirimi desteği yoktur.|
|**0x80cf0044**|OM_E_PER_MACHINE_UPDATE_ACCESS_DENIED|Yalnızca yöneticiler bu işlemi bilgisayar güncelleştirmesi başına gerçekleştirebilir.|
|**0x80cf0045**|OM_E_UNSUPPORTED_SEARCHSCOPE|Desteklenmeyen kapsama sahip bir arama denendi.|
|**0x80cf0046**|OM_E_BAD_FILE_URL|URL bir dosyaya işaret etmiyor.|
|**0x80cf0047**|OM_E_NOTSUPPORTED|İstenen işlem desteklenmiyor.|
|**0x80cf0049**|OM_E_OUTOFRANGE|Veriler aralık dışında kalıyor.|
|**0x80cf004A**|OM_E_INVALIDWUAVERSION|Veriler geçerli olmayan bir sürüm içeriyor.|
|**0x80cf004B**|OM_E_SEARCH_COMPLETED_WITH_SOME_FAILURES|Arama çağrısı tamamlandı, ancak bazı güncelleştirmeler algılanamadı.|
|**0x80cf004C**|OM_E_DOWNLOAD_COMPLETED_WITH_SOME_FAILURES|İndirme çağrısı tamamlandı, ancak bazı güncelleştirmeler indirilemedi.|
|**0x80cf004D**|OM_E_INSTALL_COMPLETED_WITH_SOME_FAILURES|Yükleme çağrısı tamamlandı, ancak bazı güncelleştirmeler yüklenemedi.|
|**0x80cf004E**|OM_E_WINUPDATE_CACHE_UNINITIALIZED|Windows Update önbelleği henüz başlatılmamış olduğundan boş.|
|**0x80cf0436**|OM_E_PT_CATALOG_SYNC_REQUIRED|Sunucu kategoriye özel aramayı desteklemiyor. Bunun yerine tam katalog araması yapılmalıdır.|
|**0x80cf0437**|OM_E_PT_SECURITY_VERIFICATION_FAILURE|Hizmetin yetkilendirilmesiyle ilgili bir sorun oluştu.|
|**0x80cf0438**|OM_E_PT_ENDPOINT_UNREACHABLE|Uç noktasına rota veya ağ bağlantısı yok.|
|**0x80cf0439**|OM_E_PT_INVALID_FORMAT|Alınan veriler veri sözleşmesi beklentilerini karşılamıyor.|
|**0x80cf043A**|OM_E_PT_INVALID_URL|URL geçerli değil.|
|**0x80cf043B**|OM_E_PT_NWS_NOT_LOADED|NWS çalışma zamanı yüklenemiyor.|
|**0x80cf043C**|OM_E_PT_PROXY_AUTH_SCHEME_NOT_SUPPORTED|Proxy kimlik doğrulaması şeması desteklenmiyor.|
|**0x80cf043D**|OM_E_SERVICEPROP_NOTAVAIL|İstenen hizmet özelliği kullanılamıyor.|
|**0x80cf043E**|OM_E_PT_ENDPOINT_REFRESH_REQUIRED|Uç noktası sağlayıcı eklentisi çevrimiçi yenileme gerektiriyor.|
|**0x80cf043F**|OM_E_PT_ENDPOINTURL_NOTAVAIL|İstenen hizmet uç noktası için bir URL kullanılamıyor.|
|**0x80cf0440**|OM_E_PT_ENDPOINT_DISCONNECTED|Hizmet uç noktası bağlantısı sonlandırıldı.|
|**0x80cf0441**|OM_E_PT_INVALID_OPERATION|Protokol konuşmacı uygunsuz bir durumda olduğundan işlem geçersiz.|
|**0x80cf0FFF**|OM_E_UNEXPECTED|Bir işlem başka bir işlem kodu tarafından açıklanmayan nedenlerle başarısız oldu.|
|**0x80cf1001**|OM_E_MSI_WRONG_VERSION|Windows Installer 3.1 sürümünden önceki bir sürüm olduğundan arama bazı güncelleştirmeleri atlamış olabilir.|
|**0x80cf1002**|OM_E_MSI_NOT_CONFIGURED|Windows Installer yapılandırılmadığından arama bazı güncelleştirmeleri atlamış olabilir.|
|**0x80cf1003**|OM_E_MSP_DISABLED|İlke Windows Installer'a düzeltme eki uygulamayı devre dışı bıraktığından arama bazı güncelleştirmeleri atlamış olabilir.|
|**0x80cf1004**|OM_E_MSI_WRONG_APP_CONTEXT|Uygulama kullanıcı başına yüklendiğinden bir güncelleştirme uygulanamadı.|
|**0x80cf2000**|OM_E_UH_REMOTEUNAVAILABLE|Uzak hiçbir işlem kullanılabilir olmadığından bir uzaktan güncelleştirme işleyicisi için bir istek tamamlanamadı.|
|**0x80cf2001**|OM_E_UH_LOCALONLY|İşleyici yalnızca yerel olduğundan uzak güncelleştirme işleyici için bir istek tamamlanamadı.|
|**0x80cf2003**|OM_E_UH_REMOTEALREADYACTIVE|Zaten bir tane olduğundan, uzak güncelleştirme işleyici oluşturulamadı.|
|**0x80cf2004**|OM_E_UH_DOESNOTSUPPORTACTION|Güncelleştirme yüklemeyi (kaldırmayı) desteklemediğinden, işleyici için bir güncelleştirme yükleme (kaldırma) isteği tamamlanmadı.|
|**0x80cf2005**|OM_E_UH_WRONGHANDLER|Yanlış işleyici belirtilmiş olduğundan işlem tamamlanamadı.|
|**0x80cf2006**|OM_E_UH_INVALIDMETADATA|Güncelleştirme geçersiz meta veriler içerdiğinden bir işleyici işlemi tamamlanamadı.|
|**0x80cf2007**|OM_E_UH_INSTALLERHUNG|Yükleyici zaman sınırını aştığından bir işlem tamamlanamadı. Kullanıcı etkileşimi gerektiren bir güncelleştirmenin dağıtım için onaylanmış olup olmadığını denetleyin. Bu durumda, sessiz yükleyebilmek için güncelleştirme yükleme parametrelerini düzeltmeniz gerekir.|
|**0x80cf2008**|OM_E_UH_OPERATIONCANCELLED|Güncelleştirme işleyici tarafından gerçekleştirilen bir işlem iptal edildi.|
|**0x80cf2009**|OM_E_UH_BADHANDLERXML|İşleyiciye özel meta veriler geçerli olmadığından işlem tamamlanamadı.|
|**0x80cf200B**|OM_E_UH_INSTALLERFAILURE|Yükleyici bir veya daha fazla güncelleştirmeyi yükleyemedi (kaldıramadı).|
|**0x80cf200D**|OM_E_UH_NEEDANOTHERDOWNLOAD|Yeniden yüklenmesi gerektiğinden güncelleştirme işleyici güncelleştirmeyi yüklemedi.|
|**0x80cf200E**|OM_E_UH_NOTIFYFAILURE|Güncelleştirme işleyici yüklemenin (kaldırmanın) durumu hakkında bildirim göndermedi.|
|**0x80cf2014**|OM_E_UH_POSTREBOOTSTILLPENDING|Güncelleştirme sonrası yeniden başlatma işlemi devam ediyor.|
|**0x80cf2015**|OM_E_UH_POSTREBOOTRESULTUNKNOWN|Güncelleştirme sonrası yeniden başlatma işleminin sonucu belirlenemedi.|
|**0x80cf2016**|OM_E_UH_POSTREBOOTUNEXPECTEDSTATE|Yeniden başlatma işlemi tamamlandıktan sonra güncelleştirmenin durumu beklenmiyor.|
|**0x80cf2017**|OM_E_UH_NEW_SERVICING_STACK_REQUIRED|Bu güncelleştirme indirilmeden veya yüklenmeden önce işletim sistemi hizmet yığınının güncelleştirilmesi gerekir.|
|**0x80cf2018**|OM_E_UH_CALLED_BACK_FAILURE|Bir geri çağırma yükleyicisi bir hatayla geri çağırdı.|
|**0x80cf2019**|OM_E_UH_CUSTOMINSTALLER_INVALID_SIGNATURE|Özel yükleyici imzası güncelleştirmenin gerektirdiği imzayla eşleşmedi.|
|**0x80cf201A**|OM_E_UH_UNSUPPORTED_INSTALLCONTEXT|Yükleyici yükleme yapılandırmasını desteklemiyor.|
|**0x80cf201B**|OM_E_UH_INVALID_TARGETSESSION|Yükleme için hedeflenen oturum geçerli değil.|
|**0x80cf2FFF**|OM_E_UH_UNEXPECTED|Bir güncelleştirme işleyici hatası başka bir OM_E_UH_&#42; kodu tarafından kapsanmıyor.|
|**0x80cf3FFD**|OM_E_NON_UI_MODE|UI dışı moddayken UI gösterilemez. Windows Update istemcisi kullanıcı arabirimi modülleri yüklenmemiş olabilir.|
|**0x80cf3FFE**|OM_E_WUCLTUI_UNSUPPORTED_VERSION|WU istemcisi kullanıcı arabirimi dışarı aktarılan işlevlerin bu sürümü desteklenmez.|
|**0x80cf3FFF**|OM_E_AUCLIENT_UNEXPECTED|Başka bir OM_E_AUCLIENT_&#42; hata kodu tarafından kapsanmayan bir kullanıcı arabirimi hatası oluştu.|
|**0x80cf4007**|OM_E_PT_SOAPCLIENT_SOAPFAULT|**SOAPCLIENT_SOAPFAULT** ile aynı. **OM_E_PT_SOAP_&#42;** hata kodu türünde bir SOAP hatası oluştuğundan SOAP istemcisi başarısız oldu.|
|**0x80cf4008**|OM_E_PT_SOAPCLIENT_PARSEFAULT|**SOAPCLIENT_PARSEFAULT_ERROR** ile aynı.  SOAP istemcisi SOAP hatasını ayrıştıramadı.|
|**0x80cf400A**|OM_E_PT_SOAPCLIENT_PARSE|**SOAPCLIENT_PARSE_ERROR** ile aynı.  SOAP istemcisi sunucudan yanıtı ayrıştıramadı.|
|**0x80cf400B**|OM_E_PT_SOAP_VERSION|**SOAP_E_VERSION_MISMATCH** ile aynı. SOAP istemcisi SOAP zarfı için tanınmayan bir ad alanı buldu.|
|**0x80cf400C**|OM_E_PT_SOAP_MUST_UNDERSTAND|**SOAP_E_MUST_UNDERSTAND** ile aynı. SOAP istemcisi bir üstbilgiyi yorumlayamadı.|
|**0x80cf400D**|OM_E_PT_SOAP_CLIENT|**SOAP_E_CLIENT** ile aynı. SOAP istemcisi iletinin hatalı biçimlendirildiğini buldu. Göndermeden önce düzeltin.|
|**0x80cf400E**|OM_E_PT_SOAP_SERVER|**SOAP_E_SERVER** ile aynı. Sunucu hatası nedeniyle SOAP iletisi işlenemedi. Daha sonra yeniden gönderin.|
|**0x80cf4010**|OM_E_PT_EXCEEDED_MAX_SERVER_TRIPS|Sunucuya gidiş dönüş sayısı maksimum sınırı aştı.|
|**0x80cf4012**|OM_E_PT_DOUBLE_INITIALIZATION|Nesne zaten başlatıldığı için başlatma başarısız oldu.|
|**0x80cf4013**|OM_E_PT_INVALID_COMPUTER_NAME|Bilgisayar adı belirlenemedi.|
|**0x80cf4015**|OM_E_PT_REFRESH_CACHE_REQUIRED|Sunucu yanıtı sunucunun değiştirildiğini veya tanımlama bilgisinin geçersiz olduğunu gösteriyor. İç önbelleği yenileyin ve yeniden deneyin.|
|**0x80cf4016**|OM_E_PT_HTTP_STATUS_BAD_REQUEST|**HTTP durum 400** ile aynı. Sözdizimi geçerli olmadığından sunucu isteği gerçekleştiremedi.|
|**0x80cf4017**|OM_E_PT_HTTP_STATUS_DENIED|**HTTP durum 401** ile aynı. İstenen kaynak kullanıcı kimlik doğrulaması gerektiriyor.|
|**0x80cf4018**|OM_E_PT_HTTP_STATUS_FORBIDDEN|**HTTP durum 403** ile aynı. Sunucu isteği anladı ancak gerçekleştirmeyi reddetti.|
|**0x80cf4019**|OM_E_PT_HTTP_STATUS_NOT_FOUND|**HTTP durum 404** ile aynı. Sunucu istenen URI'yi (Tekdüzen Kaynak Tanımlayıcısı) bulamıyor.|
|**0x80cf401A**|OM_E_PT_HTTP_STATUS_BAD_METHOD|**HTTP durum 405** ile aynı. HTTP yöntemine izin verilmez.|
|**0x80cf401B**|OM_E_PT_HTTP_STATUS_PROXY_AUTH_REQ|**HTTP durum 407** ile aynı. Proxy kimlik doğrulaması gereklidir.|
|**0x80cf401C**|OM_E_PT_HTTP_STATUS_REQUEST_TIMEOUT|**HTTP durum 408** ile aynı. Sunucu isteği beklerken zaman aşımına uğradı.|
|**0x80cf401D**|OM_E_PT_HTTP_STATUS_CONFLICT|**HTTP durum 409** ile aynı. Kaynağın geçerli durumu ile bir çakışma olduğundan istek tamamlanamadı.|
|**0x80cf401E**|OM_E_PT_HTTP_STATUS_GONE|**HTTP durum 410** ile aynı. İstenen kaynak sunucuda artık kullanılamıyor.|
|**0x80cf401F**|OM_E_PT_HTTP_STATUS_SERVER_ERROR|**HTTP durum 500** ile aynı. Sunucuda bir iç hata isteğin yerine getirilmesini engelledi.|
|**0x80cf4020**|OM_E_PT_HTTP_STATUS_NOT_SUPPORTED|**HTTP durum 500** ile aynı. Sunucu isteği yerine getirmek için gereken işlevselliği desteklemiyor.|
|**0x80cf4021**|OM_E_PT_HTTP_STATUS_BAD_GATEWAY|**HTTP durum 502** ile aynı. Sunucu, ağ geçidi veya proxy gibi davranırken eriştiği yukarı akış sunucusundan geçersiz bir yanıt aldı.|
|**0x80cf4022**|OM_E_PT_HTTP_STATUS_SERVICE_UNAVAIL|**HTTP durum 503** ile aynı. Hizmet geçici olarak aşırı yüklendi.|
|**0x80cf4023**|OM_E_PT_HTTP_STATUS_GATEWAY_TIMEOUT|**HTTP durum 503** ile aynı. İstek bir ağ geçidi beklenirken zaman aşımına uğradı.|
|**0x80cf4024**|OM_E_PT_HTTP_STATUS_VERSION_NOT_SUP|**HTTP durum 505** ile aynı. Sunucu istek için kullanılan HTTP protokolü sürümünü desteklemiyor.|
|**0x80cf4025**|OM_E_PT_FILE_LOCATIONS_CHANGED|İşlem değiştirilen dosya konumu nedeniyle başarısız oldu. İç durumu yenileyin ve yeniden gönderin.|
|**0x80cf4027**|OM_E_PT_NO_AUTH_PLUGINS_REQUESTED|Sunucu boş kimlik doğrulaması bilgi listesi döndürdü.|
|**0x80cf4028**|OM_E_PT_NO_AUTH_COOKIES_CREATED|Aracı geçerli kimlik doğrulaması tanımlama bilgileri oluşturamadı.|
|**0x80cf4029**|OM_E_PT_INVALID_CONFIG_PROP|Bir yapılandırma özellik değeri yanlıştı.|
|**0x80cf402A**|OM_E_PT_CONFIG_PROP_MISSING|Bir yapılandırma özellik değeri eksikti.|
|**0x80cf402B**|OM_E_PT_HTTP_STATUS_NOT_MAPPED|HTTP isteği tamamlanamadı ve neden, **OM_E_PT_HTTP_&#42;** hata kodlarından hiçbirine karşılık gelmedi.|
|**0x80cf402C**|OM_E_PT_WINHTTP_NAME_NOT_RESOLVED|**ERROR_WINHTTP_NAME_NOT_RESOLVED** ile aynı. Proxy sunucusu veya hedef sunucu adı çözülemiyor.|
|**0x80cf402F**|OM_E_PT_ECP_SUCCEEDED_WITH_ERRORS|Dış .cab dosyası işleme bazı hatalarla tamamlandı.|
|**0x80cf4030**|OM_E_PT_ECP_INIT_FAILED|Dış .cab işlemci başlatması tamamlanmadı.|
|**0x80cf4031**|OM_E_PT_ECP_INVALID_FILE_FORMAT|Meta veri dosyasının biçimi geçerli değil.|
|**0x80cf4032**|OM_E_PT_ECP_INVALID_METADATA|Dış cab işlemcisi geçersiz meta veriler buldu.|
|**0x80cf4033**|OM_E_PT_ECP_FAILURE_TO_EXTRACT_DIGEST|Dosya özeti dış .cab dosyasından ayıklanamadı.|
|**0x80cf4034**|OM_E_PT_ECP_FAILURE_TO_DECOMPRESS_CAB_FILE|Bir dış .cab dosyası açılamadı.|
|**0x80cf4035**|OM_E_PT_ECP_FILE_LOCATION_ERROR|Dış cab işlemcisi dosya konumlarını alamadı.|
|**0x80cf4FFF**|OM_E_PT_UNEXPECTED|Başka bir **OM_E_PT_&#42;** hata kodu tarafından kapsanmayan bir iletişim hatası oluştu.|
|**0x80cf6001**|OM_E_DM_URLNOTAVAILABLE|İstenen dosya bir URL'ye sahip olmadığı için bir yükleme yöneticisi işlemi tamamlanamadı.|
|**0x80cf6002**|OM_E_DM_INCORRECTFILEHASH|Dosya özeti tanınmadığından bir yükleme yöneticisi işlemi tamamlanamadı.|
|**0x80cf6003**|OM_E_DM_UNKNOWNALGORITHM|Dosya meta verileri tanınmayan bir karma algoritması istediğinden bir yükleme yöneticisi işlemi tamamlanamadı.|
|**0x80cf6005**|OM_E_DM_NONETWORK|Ağ bağlantısı kullanılamadığı için bir yükleme yöneticisi işlemi tamamlanamadı.|
|**0x80cf6007**|OM_E_DM_NOTDOWNLOADED|Güncelleştirme indirilmedi.|
|**0x80cf6008**|OM_E_DM_FAILTOCONNECTTOBITS|İndirme yöneticisi Arka Plan Akıllı Aktarım Hizmeti'ne (BITS) bağlanamadığından bir indirme yöneticisi hizmeti başarısız oldu.|
|**0x80cf6009**|OM_E_DM_BITSTRANSFERERROR|Belirtilmeyen bir Arka Plan Akıllı Aktarım Hizmeti (BITS) aktarım hatası nedeniyle bir indirme yöneticisi işi başarısız oldu.|
|**0x80cf600a**|OM_E_DM_DOWNLOADLOCATIONCHANGED|İndirme kaynak konumu değiştiği için bir indirmenin yeniden başlatılması gerekiyor.|
|**0x80cf600B**|OM_E_DM_CONTENTCHANGED|Yeni bir düzeltmede güncelleştirme içeriği değiştiğinden bir indirmenin yeniden başlatılması gerekiyor.|
|**0x80cf6FFF**|OM_E_DM_UNEXPECTED|Başka bir **OM_E_DM_&#42;** hata kodu tarafından kapsanmayan bir indirme yöneticisi hatası oluştu.|
|**0x80cf7003**|OM_E_INVALID_EVENT_PAYLOAD|Geçerli olmayan bir olay yükü belirtildi.|
|**0x80cf7004**|OM_E_INVALID_EVENT_PAYLOADSIZE|Gönderilen olay yükü boyutu geçerli değil.|
|**0x80cf7005**|OM_E_SERVICE_NOT_REGISTERED|Hizmet kayıtlı değil.|
|**0x80cf8000**|OM_E_DS_SHUTDOWN|Aracı kapatıldığından bir işlem başarısız oldu.|
|**0x80cf8001**|OM_E_DS_INUSE|Veri deposu kullanımda olduğundan işlem başarısız oldu.|
|**0x80cf8002**|OM_E_DS_INVALID|Veri deposunun geçerli ve beklenen durumları eşleşmiyor.|
|**0x80cf8003**|OM_E_DS_TABLEMISSING|Veri deposunda bir tablo eksik.|
|**0x80cf8004**|OM_E_DS_TABLEINCORRECT|Veri deposu beklenmeyen sütunlara sahip bir tablo içeriyor.|
|**0x80cf8005**|OM_E_DS_INVALIDTABLENAME|Tablo veri deposunda olmadığından açılamadı.|
|**0x80cf8006**|OM_E_DS_BADVERSION|Veri deposunun geçerli ve beklenen sürümleri eşleşmiyor.|
|**0x80cf8007**|OM_E_DS_NODATA|İstenen bilgiler veri deposunda değil.|
|**0x80cf8008**|OM_E_DS_MISSINGDATA|Veri deposunda gerekli bilgiler eksik veya null olmayan bir değer gerektiren bir tablo sütununda null değere sahip.|
|**0x80cf8009**|OM_E_DS_MISSINGREF|Veri deposunda gerekli bilgiler eksik veya eksik lisans koşulları, dosya, yerelleştirilmiş özellik ya da bağlı satıra başvuru içeriyor.|
|**0x80cf800A**|OM_E_DS_UNKNOWNHANDLER|Güncelleştirme işleyicisi tanınmadığından güncelleştirme işlenmedi.|
|**0x80cf800B**|OM_E_DS_CANTDELETE|Bir veya daha fazla hizmet tarafından hala başvurulduğundan güncelleştirme silinmedi.|
|**0x80cf800C**|OM_E_DS_LOCKTIMEOUTEXPIRED|Veri deposu bölümü ayrılan süre içinde kilitlenemedi.|
|**0x80cf800E**|OM_E_DS_ROWEXISTS|Var olan bir satır aynı birincil anahtara sahip olduğundan, satır eklenmedi.|
|**0x80cf800F**|OM_E_DS_STOREFILELOCKED|Başka bir işlem tarafından kilitlendiğinden veri deposu başlatılamadı.|
|**0x80cf8010**|OM_E_DS_CANNOTREGISTER|Veri deposunun geçerli işlemde COM ile kaydedilmesine izin verilmez.|
|**0x80cf8011**|OM_E_DS_UNABLETOSTART|Bir işlem başka bir işlemde bir veri deposu nesnesi oluşturamadı.|
|**0x80cf8013**|OM_E_DS_DUPLICATEUPDATEID|Sunucu istemciye aynı güncelleştirmeyi iki farklı düzeltme kimliğiyle gönderdi.|
|**0x80cf8014**|OM_E_DS_UNKNOWNSERVICE|Hizmet veri deposunda olmadığından işlem tamamlanamadı.|
|**0x80cf8015**|OM_E_DS_SERVICEEXPIRED|Hizmetin kayıt süresi dolduğundan bir işlem tamamlanamadı.|
|**0x80cf8016**|OM_E_DS_DECLINENOTALLOWED|Zorunlu bir güncelleştirme olduğundan veya bir son tarihle dağıtıldığından bir güncelleştirmeyi gizleme isteği reddedildi.|
|**0x80cf8017**|OM_E_DS_TABLESESSIONMISMATCH|Oturumla ilişkili olmadığından bir tablo kapatılmadı.|
|**0x80cf8018**|OM_E_DS_SESSIONLOCKMISMATCH|Oturumla ilişkili olmadığından bir tablo kapatılmadı.|
|**0x80cf8019**|OM_E_DS_NEEDWINDOWSSERVICE|Yerleşik bir hizmet olduğundan veya Otomatik Güncelleştirmeler başka bir hizmete dönemediğinden bir hizmeti kaldırma veya kaydını kaldırma isteği reddedildi.|
|**0x80cf801A**|OM_E_DS_INVALIDOPERATION|İşleme izin verilmediğinden istek reddedildi.|
|**0x80cf801B**|OM_E_DS_SCHEMAMISMATCH|Geçerli veri deposu şeması ve yedek XML belgesindeki bir tablodaki şema eşleşmiyor.|
|**0x80cf801C**|OM_E_DS_RESETREQUIRED|Veri deposu oturumu sıfırlamayı gerektiriyor. Oturumu serbest bırakın ve yeni bir oturumla yeniden deneyin.|
|**0x80cf801D**|OM_E_DS_IMPERSONATED|Temsili bir kimlikle istendiğinden dolayı bir veri deposu işlemi tamamlanamadı.|
|**0x80cf8FFF**|OM_E_DS_UNEXPECTED|Başka bir **OM_E_DS_&#42;** kodu tarafından kapsanmayan bir veri deposu hatası oluştu.|
|**0x80cfA000**|OM_E_AU_NOSERVICE|Otomatik Güncelleştirmeler gelen istekleri karşılayamadı.|
|**0x80cfA004**|OM_E_AU_PAUSED|Otomatik Güncelleştirmeler duraklatıldığından gelen istekleri işleyemedi.|
|**0x80cfA005**|OM_E_AU_NO_REGISTERED_SERVICE|Yönetilmeyen hiçbir hizmet Otomatik Güncelleştirmeler ile kayıtlı değil.|
|**0x80cfA006**|OM_E_AU_DETECT_SVCID_MISMATCH|Arama sırasında Otomatik Güncelleştirmeler ile kayıtlı varsayılan hizmet değiştirildi.|
|**0x80cfA007**|OM_E_AU_ALREADY_PROMPTING_FOR_REBOOT|Otomatik Güncelleştirmeler zaten kullanıcıdan yeniden başlatmasını istiyor.|
|**0x80cfAFFF**|OM_E_AU_UNEXPECTED|Başka bir **OM_E_AU_&#42;** kodu tarafından kapsanmayan bir Otomatik Güncelleştirmeler hatası oluştu.|
|**0x80cfE001**|OM_E_EE_UNKNOWN_EXPRESSION|Bir ifade tanınmadığından bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfE002**|OM_E_EE_INVALID_EXPRESSION|Bir ifade geçerli olmadığından bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfE003**|OM_E_EE_MISSING_METADATA|Bir ifade yanlış sayıda meta veri düğümü içerdiğinden bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfE004**|OM_E_EE_INVALID_VERSION|Seri duruma getirilmiş ifade verileri sürümü geçerli olmadığından bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfE005**|OM_E_EE_NOT_INITIALIZED|İfade değerlendiricisi başlatılamadı.|
|**0x80cfE006**|OM_E_EE_INVALID_ATTRIBUTEDATA|Bir öznitelik geçerli olmadığından bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfE007**|OM_E_EE_CLUSTER_ERROR|Bilgisayarın küme durumu belirlenemediğinden, bir ifade değerlendiricisi işlemi tamamlanamadı.|
|**0x80cfEFFF**|OM_E_EE_UNEXPECTED|Başka bir **OM_E_EE_&#42;** hata kodu tarafından kapsanmayan bir ifade değerlendiricisi hatası oluştu.|
|**0x80cfF001**|OM_E_REPORTER_EVENTCACHECORRUPT|Olay önbellek dosyası bozuktu.|
|**0x80cfF002**|OM_E_REPORTER_EVENTNAMESPACEPARSEFAILED|Olay ad alanı tanımlayıcısındaki XML ayrıştırılamadı.|
|**0x80cfF003**|OM_E_INVALID_EVENT|Olay ad alanı tanımlayıcısındaki XML geçerli değil.|
|**0x80cfF004**|OM_E_SERVER_BUSY|Sunucu meşgul olduğundan bir olayı reddetti.|
|**0x80cfFFFF**|OM_E_REPORTER_UNEXPECTED|Başka bir hata kodu tarafından kapsanmayan bir bildirici hatası oluştu.|
|**0x80af0005**|OMC_E_INSTALL_NOT_ALLOWED_REBOOT_REQUIRED|Bekleyen bir zorunlu yeniden başlatma olduğundan yükleme başarısız oldu.|
|**0x80af0006**|OMC_E_DOWNLOAD_CANCELLED|İndirme iptal edildi.|

## <a name="windows-7-based-computers-with-lots-of-superseded-updates-stop-reporting-to-the-microsoft-intune-console"></a>Yenisiyle değiştirilmiş çok fazla güncelleştirmesi olan Windows 7 tabanlı bilgisayarlarda Microsoft Intune konsoluna raporlama durduruluyor
**Sorun**: Microsoft Intune istemcilerinin aşağıdaki belirtilerden en az biriyle karşılaştığı durumlar yaşayabilirsiniz:
- Aniden Microsoft yönetim konsoluna raporlamayı durduruyorlar.  
- Yüksek CPU kullanımıyla karşılaşıyorlar.
- Intune portalı aracılığıyla yüklenen uygulamalar yavaş yükleniyor.
- Microsoft Intune Center şu hatayı tetikliyor: *Bilgisayarınız güncelleştirilirken bir hata oluştu. Hata bulundu: Kod 0x800705b4*.
- Intune Yönetim Konsolu > Gruplar > Tüm Cihazlar’ın altındaki durum alanında şu görüntüleniyor: *Bu bilgisayarda yüklü olan bir veya daha çok aracıda hatalar var. Bu bilgisayarla ilgili bilgiler doğru veya güncel olmayabilir*.

Yenisiyle değiştirilmiş güncelleştirmeler uzun bir süre reddedilmezse, bu sorun ortaya çıkabilir. Uygulama yükleme gibi bazı işlemler sırasında Windows yenisiyle değiştirilmiş tüm güncelleştirmeleri sırayla denetler; böylelikle güncelleştirmeler ve ardılları doğru bir şekilde eşlenir. Yenisiyle değiştirilen güncelleştirmeler listesi çok fazla büyürse, işlem yükü ve gereken süre nedeniyle bu denetim görevi yüksek CPU kullanımına neden olabilir. Bu sorun öncelikle Windows 7 çalıştıran istemcileri etkiler çünkü Windows 7 için yenisiyle değiştirilmiş çok fazla sayıda güncelleştirme vardır. Windows 8 ve sonraki işletim sistemlerinin yenisiyle değiştirilmiş o kadar çok güncelleştirmesi olmadığından, bu sorundan fazla etkilenmez.

**Çözüm**: Bu sorunu çözmek için şu adımları izleyin:
1. [Intune yönetim konsolunda](https://manage.microsoft.com) oturum açın.
2. **Güncelleştirmeler** > **Tüm Güncelleştirmeler**’i seçin.
3. Yenisiyle değiştirilen güncelleştirmeleri filtrelemek için, üst araç çubuğundaki filtre seçeneğini kullanın.
4. Windows 7’ye veya etkilenen istemcilere yüklenmiş olan uygulamalara (örneğin, Microsoft Office) uygulanabilecek, yenisiyle değiştirilmiş tüm güncelleştirmeleri reddedin.
5. Etkilenen istemcileri yeniden başlatın.

Buna ek olarak, Windows 7 çalıştırıyorsanız şu güncelleştirmeyi yüklediğinizden emin olun:[3050265 Windows 7 için Windows Update İstemcisi: Haziran 2015](https://support.microsoft.com/kb/3050265).

### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.
