<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulaması ve yetkilendirme, Azure AD kimlik bilgileri ve Intune rol tabanlı erişim denetimine (RBAC) bağlıdır. Varsayılan olarak kiracınızdaki tüm genel yöneticiler ve Intune hizmet yöneticilerinin Veri ambarına erişimi vardır. Intune rolleri ile kullanıcılara **Intune veri ambarı** kaynağı erişimi vererek daha fazla kullanıcıya erişim sağlayabilirsiniz.

API dahil olmak üzere Intune Veri Ambarı’na erişim önkoşulları şöyledir:

  -  Kullanıcı şunlardan biri olmalıdır:
      -  Azure AD genel yöneticisi
      -  Intune hizmet yöneticisi
      -  **Intune veri ambarı** kaynağına rol tabanlı erişimi olan kullanıcı
      -  [Yalnızca uygulama kimlik doğrulaması](../data-warehouse-app-only-auth.md) kullanılan kullanıcısız kimlik doğrulaması 
